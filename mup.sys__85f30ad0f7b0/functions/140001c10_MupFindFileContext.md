# MupFindFileContext

- ea: `0x140001c10`
- end: `0x140001c8a`
- name: `MupFindFileContext`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140013180`
- `0x1400140e0`
- `0x1400144d0`
- `0x140019598`
- `0x140019d10`
- `0x140019fb0`
- `0x14001a7b0`
- `0x14001b8b0`
- `0x14001d040`
- `0x14001e020`
- `0x14001ed00`
- `0x14001f210`

## callees

- `0x140001c10`
- `0x140002700`

## import_xrefs

- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x140001c27`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x140001c27`

## pseudocode

```c
PVOID *__fastcall MupFindFileContext(struct _FILE_OBJECT *a1)
{
  PFSRTL_PER_FILEOBJECT_CONTEXT v2; // rax
  PVOID *p_InstanceId; // rbx

  v2 = FsRtlLookupPerFileObjectContext(a1, MupDeviceObject, 0);
  if ( v2 )
    p_InstanceId = &v2[-1].InstanceId;
  else
    p_InstanceId = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, a1, p_InstanceId);
  }
  return p_InstanceId;
}

```

## disassembly

```asm
0x140001c10  mov     [rsp+arg_0], rbx
0x140001c15  push    rdi
0x140001c16  sub     rsp, 30h
0x140001c1a  mov     rdx, cs:MupDeviceObject; OwnerId
0x140001c21  xor     r8d, r8d; InstanceId
0x140001c24  mov     rdi, rcx
0x140001c27  call    cs:__imp_FsRtlLookupPerFileObjectContext
0x140001c2e  nop     dword ptr [rax+rax+00h]
0x140001c33  test    rax, rax
0x140001c36  jz      short loc_140001C67
0x140001c38  lea     rbx, [rax-8]
0x140001c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c43  lea     rax, WPP_GLOBAL_Control
0x140001c4a  cmp     rcx, rax
0x140001c4d  jz      short loc_140001C58
0x140001c4f  test    dword ptr [rcx+2Ch], 4000000h
0x140001c56  jnz     short loc_140001C6B
0x140001c58  mov     rax, rbx
0x140001c5b  mov     rbx, [rsp+38h+arg_0]
0x140001c60  add     rsp, 30h
0x140001c64  pop     rdi
0x140001c65  retn
0x140001c67  xor     ebx, ebx
0x140001c69  jmp     short loc_140001C3C
0x140001c6b  mov     rcx, [rcx+18h]
0x140001c6f  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x140001c76  mov     edx, 0Eh
0x140001c7b  mov     [rsp+38h+var_18], rbx
0x140001c80  mov     r9, rdi
0x140001c83  call    WPP_SF_qq
0x140001c88  jmp     short loc_140001C58
```
