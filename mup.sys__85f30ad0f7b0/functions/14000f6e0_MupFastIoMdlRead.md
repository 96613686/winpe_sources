# MupFastIoMdlRead

- ea: `0x14000f6e0`
- end: `0x14000f79e`
- name: `MupFastIoMdlRead`
- size: `190`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, ULONG Length, ULONG LockKey, PMDL *, PIO_STATUS_BLOCK)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400054e0`
- `0x14000f6e0`
- `0x14001e710`

## import_xrefs

- `ntoskrnl!FsRtlMdlReadDev` at `0x14000f788`
- `ntoskrnl!FsRtlMdlReadDev` at `0x14000f788`

## pseudocode

```c
BOOLEAN __fastcall MupFastIoMdlRead(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        ULONG Length,
        ULONG LockKey,
        PMDL *MdlChain,
        PIO_STATUS_BLOCK IoStatus)
{
  __int64 ProviderFastIoDispatchTable; // rax
  __int64 (__fastcall *v11)(PFILE_OBJECT, PLARGE_INTEGER, _QWORD, _QWORD, PMDL *, PIO_STATUS_BLOCK, PDEVICE_OBJECT); // rax
  PDEVICE_OBJECT DeviceObject[7]; // [rsp+40h] [rbp-38h] BYREF

  DeviceObject[0] = 0;
  ProviderFastIoDispatchTable = MupiGetProviderFastIoDispatchTable(FileObject, DeviceObject);
  if ( ProviderFastIoDispatchTable
    && *(_DWORD *)ProviderFastIoDispatchTable >= 0x88u
    && (v11 = *(__int64 (__fastcall **)(PFILE_OBJECT, PLARGE_INTEGER, _QWORD, _QWORD, PMDL *, PIO_STATUS_BLOCK, PDEVICE_OBJECT))(ProviderFastIoDispatchTable + 128)) != 0 )
  {
    return v11(FileObject, FileOffset, Length, LockKey, MdlChain, IoStatus, DeviceObject[0]);
  }
  else
  {
    return FsRtlMdlReadDev(FileObject, FileOffset, Length, LockKey, MdlChain, IoStatus, DeviceObject[0]);
  }
}

```

## disassembly

```asm
0x14000f6e0  push    rbx
0x14000f6e2  push    rbp
0x14000f6e3  push    rsi
0x14000f6e4  push    rdi
0x14000f6e5  sub     rsp, 58h
0x14000f6e9  mov     rbp, rdx
0x14000f6ec  mov     [rsp+78h+var_38], 0
0x14000f6f5  lea     rdx, [rsp+78h+var_38]
0x14000f6fa  mov     edi, r9d
0x14000f6fd  mov     esi, r8d
0x14000f700  mov     rbx, rcx
0x14000f703  call    MupiGetProviderFastIoDispatchTable
0x14000f708  test    rax, rax
0x14000f70b  jz      short loc_14000F758
0x14000f70d  cmp     dword ptr [rax], 88h
0x14000f713  jb      short loc_14000F758
0x14000f715  mov     rax, [rax+80h]
0x14000f71c  test    rax, rax
0x14000f71f  jz      short loc_14000F758
0x14000f721  mov     rcx, [rsp+78h+var_38]
0x14000f726  mov     r9d, edi
0x14000f729  mov     [rsp+78h+DeviceObject], rcx
0x14000f72e  mov     r8d, esi
0x14000f731  mov     rcx, [rsp+78h+arg_28]
0x14000f739  mov     rdx, rbp
0x14000f73c  mov     [rsp+78h+IoStatus], rcx
0x14000f741  mov     rcx, [rsp+78h+arg_20]
0x14000f749  mov     [rsp+78h+MdlChain], rcx
0x14000f74e  mov     rcx, rbx
0x14000f751  call    _guard_dispatch_icall
0x14000f756  jmp     short loc_14000F794
0x14000f758  mov     rax, [rsp+78h+var_38]
0x14000f75d  mov     r9d, edi; LockKey
0x14000f760  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x14000f765  mov     r8d, esi; Length
0x14000f768  mov     rax, [rsp+78h+arg_28]
0x14000f770  mov     rdx, rbp; FileOffset
0x14000f773  mov     [rsp+78h+IoStatus], rax; IoStatus
0x14000f778  mov     rcx, rbx; FileObject
0x14000f77b  mov     rax, [rsp+78h+arg_20]
0x14000f783  mov     [rsp+78h+MdlChain], rax; MdlChain
0x14000f788  call    cs:__imp_FsRtlMdlReadDev
0x14000f78f  nop     dword ptr [rax+rax+00h]
0x14000f794  add     rsp, 58h
0x14000f798  pop     rdi
0x14000f799  pop     rsi
0x14000f79a  pop     rbp
0x14000f79b  pop     rbx
0x14000f79c  retn
```
