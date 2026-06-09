# MupRemoveFileContext

- ea: `0x14001d310`
- end: `0x14001d3ad`
- name: `MupRemoveFileContext`
- size: `157`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001c350`

## callees

- `0x140002700`
- `0x14001d310`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001d37d`
- `ntoskrnl!KeBugCheckEx` at `0x14001d37d`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001d32a`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001d32a`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall MupRemoveFileContext(ULONG_PTR BugCheckParameter2)
{
  PFSRTL_PER_FILEOBJECT_CONTEXT v2; // rax
  ULONG_PTR p_InstanceId; // r9
  PDEVICE_OBJECT *result; // rax

  v2 = FsRtlRemovePerFileObjectContext(*(PFILE_OBJECT *)(BugCheckParameter2 + 144), MupDeviceObject, 0);
  p_InstanceId = (ULONG_PTR)&v2[-1].InstanceId;
  if ( !v2 )
    p_InstanceId = 0;
  if ( p_InstanceId != BugCheckParameter2 )
    KeBugCheckEx(0x103u, 2u, BugCheckParameter2, p_InstanceId, 0);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    return (PDEVICE_OBJECT *)WPP_SF_qq(
                               WPP_GLOBAL_Control->AttachedDevice,
                               13,
                               WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
                               *(_QWORD *)(BugCheckParameter2 + 144),
                               BugCheckParameter2);
  }
  return result;
}

```

## disassembly

```asm
0x14001d310  push    rbx
0x14001d312  sub     rsp, 30h
0x14001d316  mov     rdx, cs:MupDeviceObject; OwnerId
0x14001d31d  mov     rbx, rcx
0x14001d320  mov     rcx, [rcx+90h]; FileObject
0x14001d327  xor     r8d, r8d; InstanceId
0x14001d32a  call    cs:__imp_FsRtlRemovePerFileObjectContext
0x14001d331  nop     dword ptr [rax+rax+00h]
0x14001d336  xor     edx, edx
0x14001d338  test    rax, rax
0x14001d33b  lea     r9, [rax-8]
0x14001d33f  cmovz   r9, rdx; BugCheckParameter3
0x14001d343  cmp     r9, rbx
0x14001d346  jnz     short loc_14001D36B
0x14001d348  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d34f  lea     rax, WPP_GLOBAL_Control
0x14001d356  cmp     rcx, rax
0x14001d359  jz      short loc_14001D364
0x14001d35b  test    dword ptr [rcx+2Ch], 4000000h
0x14001d362  jnz     short loc_14001D38A
0x14001d364  add     rsp, 30h
0x14001d368  pop     rbx
0x14001d369  retn
0x14001d36b  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x14001d370  mov     r8, rbx; BugCheckParameter2
0x14001d373  mov     edx, 2; BugCheckParameter1
0x14001d378  mov     ecx, 103h; BugCheckCode
0x14001d37d  call    cs:__imp_KeBugCheckEx
0x14001d38a  mov     r9, [rbx+90h]
0x14001d391  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001d398  mov     rcx, [rcx+18h]
0x14001d39c  mov     edx, 0Dh
0x14001d3a1  mov     [rsp+38h+BugCheckParameter4], rbx
0x14001d3a6  call    WPP_SF_qq
0x14001d3ab  jmp     short loc_14001D364
```
