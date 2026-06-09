# MupRemoveFileContext

- ea: `0x14001d2c0`
- end: `0x14001d35d`
- name: `MupRemoveFileContext`
- size: `157`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001c300`

## callees

- `0x140002700`
- `0x14001d2c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001d32d`
- `ntoskrnl!KeBugCheckEx` at `0x14001d32d`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001d2da`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001d2da`

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
0x14001d2c0  push    rbx
0x14001d2c2  sub     rsp, 30h
0x14001d2c6  mov     rdx, cs:MupDeviceObject; OwnerId
0x14001d2cd  mov     rbx, rcx
0x14001d2d0  mov     rcx, [rcx+90h]; FileObject
0x14001d2d7  xor     r8d, r8d; InstanceId
0x14001d2da  call    cs:__imp_FsRtlRemovePerFileObjectContext
0x14001d2e1  nop     dword ptr [rax+rax+00h]
0x14001d2e6  xor     edx, edx
0x14001d2e8  test    rax, rax
0x14001d2eb  lea     r9, [rax-8]
0x14001d2ef  cmovz   r9, rdx; BugCheckParameter3
0x14001d2f3  cmp     r9, rbx
0x14001d2f6  jnz     short loc_14001D31B
0x14001d2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d2ff  lea     rax, WPP_GLOBAL_Control
0x14001d306  cmp     rcx, rax
0x14001d309  jz      short loc_14001D314
0x14001d30b  test    dword ptr [rcx+2Ch], 4000000h
0x14001d312  jnz     short loc_14001D33A
0x14001d314  add     rsp, 30h
0x14001d318  pop     rbx
0x14001d319  retn
0x14001d31b  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x14001d320  mov     r8, rbx; BugCheckParameter2
0x14001d323  mov     edx, 2; BugCheckParameter1
0x14001d328  mov     ecx, 103h; BugCheckCode
0x14001d32d  call    cs:__imp_KeBugCheckEx
0x14001d33a  mov     r9, [rbx+90h]
0x14001d341  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001d348  mov     rcx, [rcx+18h]
0x14001d34c  mov     edx, 0Dh
0x14001d351  mov     [rsp+38h+BugCheckParameter4], rbx
0x14001d356  call    WPP_SF_qq
0x14001d35b  jmp     short loc_14001D314
```
