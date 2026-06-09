# MupFastIoMdlWriteComplete

- ea: `0x14000f8a0`
- end: `0x14000f923`
- name: `MupFastIoMdlWriteComplete`
- size: `131`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, PMDL MdlChain)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e0`
- `0x14000f8a0`
- `0x14001e710`

## import_xrefs

- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x14000f906`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x14000f906`

## pseudocode

```c
BOOLEAN __fastcall MupFastIoMdlWriteComplete(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, PMDL MdlChain)
{
  __int64 ProviderFastIoDispatchTable; // rax
  __int64 (__fastcall *v7)(PFILE_OBJECT, PLARGE_INTEGER, PMDL, PDEVICE_OBJECT); // rax
  PDEVICE_OBJECT DeviceObject[3]; // [rsp+30h] [rbp-18h] BYREF

  DeviceObject[0] = 0;
  ProviderFastIoDispatchTable = MupiGetProviderFastIoDispatchTable(FileObject, DeviceObject);
  if ( ProviderFastIoDispatchTable
    && *(_DWORD *)ProviderFastIoDispatchTable >= 0xA0u
    && (v7 = *(__int64 (__fastcall **)(PFILE_OBJECT, PLARGE_INTEGER, PMDL, PDEVICE_OBJECT))(ProviderFastIoDispatchTable
                                                                                          + 152)) != 0 )
  {
    return v7(FileObject, FileOffset, MdlChain, DeviceObject[0]);
  }
  else
  {
    return FsRtlMdlWriteCompleteDev(FileObject, FileOffset, MdlChain, DeviceObject[0]);
  }
}

```

## disassembly

```asm
0x14000f8a0  mov     rax, rsp
0x14000f8a3  mov     [rax+8], rbx
0x14000f8a7  mov     [rax+10h], rsi
0x14000f8ab  push    rdi
0x14000f8ac  sub     rsp, 40h
0x14000f8b0  mov     rsi, rdx
0x14000f8b3  mov     qword ptr [rax-18h], 0
0x14000f8bb  lea     rdx, [rax-18h]
0x14000f8bf  mov     rdi, r8
0x14000f8c2  mov     rbx, rcx
0x14000f8c5  call    MupiGetProviderFastIoDispatchTable
0x14000f8ca  test    rax, rax
0x14000f8cd  jz      short loc_14000F8F8
0x14000f8cf  cmp     dword ptr [rax], 0A0h
0x14000f8d5  jb      short loc_14000F8F8
0x14000f8d7  mov     rax, [rax+98h]
0x14000f8de  test    rax, rax
0x14000f8e1  jz      short loc_14000F8F8
0x14000f8e3  mov     r9, [rsp+48h+DeviceObject]
0x14000f8e8  mov     r8, rdi
0x14000f8eb  mov     rdx, rsi
0x14000f8ee  mov     rcx, rbx
0x14000f8f1  call    _guard_dispatch_icall
0x14000f8f6  jmp     short loc_14000F912
0x14000f8f8  mov     r9, [rsp+48h+DeviceObject]; DeviceObject
0x14000f8fd  mov     r8, rdi; MdlChain
0x14000f900  mov     rdx, rsi; FileOffset
0x14000f903  mov     rcx, rbx; FileObject
0x14000f906  call    cs:__imp_FsRtlMdlWriteCompleteDev
0x14000f90d  nop     dword ptr [rax+rax+00h]
0x14000f912  mov     rbx, [rsp+48h+arg_0]
0x14000f917  mov     rsi, [rsp+48h+arg_8]
0x14000f91c  add     rsp, 40h
0x14000f920  pop     rdi
0x14000f921  retn
```
