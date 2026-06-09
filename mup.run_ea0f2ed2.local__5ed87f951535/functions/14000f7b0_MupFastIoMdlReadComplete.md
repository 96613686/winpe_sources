# MupFastIoMdlReadComplete

- ea: `0x14000f7b0`
- end: `0x14000f821`
- name: `MupFastIoMdlReadComplete`
- size: `113`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PMDL MdlChain)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e0`
- `0x14000f7b0`
- `0x14001e6c0`

## import_xrefs

- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x14000f809`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x14000f809`

## pseudocode

```c
BOOLEAN __fastcall MupFastIoMdlReadComplete(PFILE_OBJECT FileObject, PMDL MdlChain)
{
  __int64 ProviderFastIoDispatchTable; // rax
  __int64 (__fastcall *v5)(PFILE_OBJECT, PMDL, PDEVICE_OBJECT); // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp+20h] BYREF

  DeviceObject = 0;
  ProviderFastIoDispatchTable = MupiGetProviderFastIoDispatchTable(FileObject, &DeviceObject);
  if ( ProviderFastIoDispatchTable
    && *(_DWORD *)ProviderFastIoDispatchTable >= 0x90u
    && (v5 = *(__int64 (__fastcall **)(PFILE_OBJECT, PMDL, PDEVICE_OBJECT))(ProviderFastIoDispatchTable + 136)) != 0 )
  {
    return v5(FileObject, MdlChain, DeviceObject);
  }
  else
  {
    return FsRtlMdlReadCompleteDev(FileObject, MdlChain, DeviceObject);
  }
}

```

## disassembly

```asm
0x14000f7b0  mov     [rsp+arg_0], rbx
0x14000f7b5  push    rdi
0x14000f7b6  sub     rsp, 20h
0x14000f7ba  mov     rdi, rdx
0x14000f7bd  mov     [rsp+28h+DeviceObject], 0
0x14000f7c6  lea     rdx, [rsp+28h+DeviceObject]
0x14000f7cb  mov     rbx, rcx
0x14000f7ce  call    MupiGetProviderFastIoDispatchTable
0x14000f7d3  test    rax, rax
0x14000f7d6  jz      short loc_14000F7FE
0x14000f7d8  cmp     dword ptr [rax], 90h
0x14000f7de  jb      short loc_14000F7FE
0x14000f7e0  mov     rax, [rax+88h]
0x14000f7e7  test    rax, rax
0x14000f7ea  jz      short loc_14000F7FE
0x14000f7ec  mov     r8, [rsp+28h+DeviceObject]
0x14000f7f1  mov     rdx, rdi
0x14000f7f4  mov     rcx, rbx
0x14000f7f7  call    _guard_dispatch_icall
0x14000f7fc  jmp     short loc_14000F815
0x14000f7fe  mov     r8, [rsp+28h+DeviceObject]; DeviceObject
0x14000f803  mov     rdx, rdi; MdlChain
0x14000f806  mov     rcx, rbx; FileObject
0x14000f809  call    cs:__imp_FsRtlMdlReadCompleteDev
0x14000f810  nop     dword ptr [rax+rax+00h]
0x14000f815  mov     rbx, [rsp+28h+arg_0]
0x14000f81a  add     rsp, 20h
0x14000f81e  pop     rdi
0x14000f81f  retn
```
