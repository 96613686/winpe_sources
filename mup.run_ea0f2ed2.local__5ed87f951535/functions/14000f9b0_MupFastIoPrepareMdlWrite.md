# MupFastIoPrepareMdlWrite

- ea: `0x14000f9b0`
- end: `0x14000fa6e`
- name: `MupFastIoPrepareMdlWrite`
- size: `190`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, ULONG Length, ULONG LockKey, PMDL *, PIO_STATUS_BLOCK)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400054e0`
- `0x14000f9b0`
- `0x14001e6c0`

## import_xrefs

- `ntoskrnl!FsRtlPrepareMdlWriteDev` at `0x14000fa58`
- `ntoskrnl!FsRtlPrepareMdlWriteDev` at `0x14000fa58`

## pseudocode

```c
BOOLEAN __fastcall MupFastIoPrepareMdlWrite(
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
    && *(_DWORD *)ProviderFastIoDispatchTable >= 0x98u
    && (v11 = *(__int64 (__fastcall **)(PFILE_OBJECT, PLARGE_INTEGER, _QWORD, _QWORD, PMDL *, PIO_STATUS_BLOCK, PDEVICE_OBJECT))(ProviderFastIoDispatchTable + 144)) != 0 )
  {
    return v11(FileObject, FileOffset, Length, LockKey, MdlChain, IoStatus, DeviceObject[0]);
  }
  else
  {
    return FsRtlPrepareMdlWriteDev(FileObject, FileOffset, Length, LockKey, MdlChain, IoStatus, DeviceObject[0]);
  }
}

```

## disassembly

```asm
0x14000f9b0  push    rbx
0x14000f9b2  push    rbp
0x14000f9b3  push    rsi
0x14000f9b4  push    rdi
0x14000f9b5  sub     rsp, 58h
0x14000f9b9  mov     rbp, rdx
0x14000f9bc  mov     [rsp+78h+var_38], 0
0x14000f9c5  lea     rdx, [rsp+78h+var_38]
0x14000f9ca  mov     edi, r9d
0x14000f9cd  mov     esi, r8d
0x14000f9d0  mov     rbx, rcx
0x14000f9d3  call    MupiGetProviderFastIoDispatchTable
0x14000f9d8  test    rax, rax
0x14000f9db  jz      short loc_14000FA28
0x14000f9dd  cmp     dword ptr [rax], 98h
0x14000f9e3  jb      short loc_14000FA28
0x14000f9e5  mov     rax, [rax+90h]
0x14000f9ec  test    rax, rax
0x14000f9ef  jz      short loc_14000FA28
0x14000f9f1  mov     rcx, [rsp+78h+var_38]
0x14000f9f6  mov     r9d, edi
0x14000f9f9  mov     [rsp+78h+DeviceObject], rcx
0x14000f9fe  mov     r8d, esi
0x14000fa01  mov     rcx, [rsp+78h+arg_28]
0x14000fa09  mov     rdx, rbp
0x14000fa0c  mov     [rsp+78h+IoStatus], rcx
0x14000fa11  mov     rcx, [rsp+78h+arg_20]
0x14000fa19  mov     [rsp+78h+MdlChain], rcx
0x14000fa1e  mov     rcx, rbx
0x14000fa21  call    _guard_dispatch_icall
0x14000fa26  jmp     short loc_14000FA64
0x14000fa28  mov     rax, [rsp+78h+var_38]
0x14000fa2d  mov     r9d, edi; LockKey
0x14000fa30  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x14000fa35  mov     r8d, esi; Length
0x14000fa38  mov     rax, [rsp+78h+arg_28]
0x14000fa40  mov     rdx, rbp; FileOffset
0x14000fa43  mov     [rsp+78h+IoStatus], rax; IoStatus
0x14000fa48  mov     rcx, rbx; FileObject
0x14000fa4b  mov     rax, [rsp+78h+arg_20]
0x14000fa53  mov     [rsp+78h+MdlChain], rax; MdlChain
0x14000fa58  call    cs:__imp_FsRtlPrepareMdlWriteDev
0x14000fa5f  nop     dword ptr [rax+rax+00h]
0x14000fa64  add     rsp, 58h
0x14000fa68  pop     rdi
0x14000fa69  pop     rsi
0x14000fa6a  pop     rbp
0x14000fa6b  pop     rbx
0x14000fa6c  retn
```
