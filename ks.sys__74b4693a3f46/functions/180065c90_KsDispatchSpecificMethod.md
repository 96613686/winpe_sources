# KsDispatchSpecificMethod

- ea: `0x180065c90`
- end: `0x180065d3e`
- name: `KsDispatchSpecificMethod`
- size: `174`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PFNKSHANDLER Handler)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010a04`

## callees

- `0x180019c60`
- `0x180065c90`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180065ce8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180065ce8`

## pseudocode

```c
NTSTATUS __stdcall KsDispatchSpecificMethod(PIRP Irp, PFNKSHANDLER Handler)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  bool v5; // zf
  ULONG Length; // ecx
  PMDL MdlAddress; // rcx
  void *MasterIrp; // rax
  struct _IRP *v10; // rdx
  unsigned int v11; // ecx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = (*(_BYTE *)(&Irp->Tail.CompletionKey + 2) & 4) == 0;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( v5 )
  {
    v11 = (Length + 7) & 0xFFFFFFF8;
    if ( v11 )
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
    else
      MasterIrp = 0;
    v10 = (struct _IRP *)((char *)Irp->AssociatedIrp.MasterIrp + v11);
  }
  else
  {
    if ( Length )
    {
      if ( (CurrentStackLocation->MinorFunction & 0xFB) != 0 )
      {
        MdlAddress = Irp->MdlAddress;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MasterIrp = MdlAddress->MappedSystemVa;
        else
          MasterIrp = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        if ( !MasterIrp )
          return -1073741670;
      }
      else
      {
        MasterIrp = Irp->UserBuffer;
      }
    }
    else
    {
      MasterIrp = 0;
    }
    v10 = Irp->AssociatedIrp.MasterIrp;
  }
  return ((__int64 (__fastcall *)(PIRP, struct _IRP *, void *))Handler)(Irp, v10, MasterIrp);
}

```

## disassembly

```asm
0x180065c90  mov     [rsp+arg_0], rbx
0x180065c95  push    rdi
0x180065c96  sub     rsp, 30h
0x180065c9a  mov     r8, [rcx+0B8h]
0x180065ca1  mov     rbx, rcx
0x180065ca4  mov     rdi, rdx
0x180065ca7  test    byte ptr [rbx+88h], 4
0x180065cae  mov     ecx, [r8+8]
0x180065cb2  jz      short loc_180065D0E
0x180065cb4  test    ecx, ecx
0x180065cb6  jz      short loc_180065D06
0x180065cb8  test    byte ptr [r8+1], 0FBh
0x180065cbd  jz      short loc_180065D00
0x180065cbf  mov     rcx, [rbx+8]; MemoryDescriptorList
0x180065cc3  test    byte ptr [rcx+0Ah], 5
0x180065cc7  jz      short loc_180065CCF
0x180065cc9  mov     rax, [rcx+18h]
0x180065ccd  jmp     short loc_180065CF4
0x180065ccf  xor     r9d, r9d; RequestedAddress
0x180065cd2  mov     [rsp+38h+Priority], 40000010h; Priority
0x180065cda  xor     edx, edx; AccessMode
0x180065cdc  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x180065ce4  lea     r8d, [r9+1]; CacheType
0x180065ce8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180065cef  nop     dword ptr [rax+rax+00h]
0x180065cf4  test    rax, rax
0x180065cf7  jnz     short loc_180065D08
0x180065cf9  mov     eax, 0C000009Ah
0x180065cfe  jmp     short loc_180065D32
0x180065d00  mov     rax, [rbx+70h]
0x180065d04  jmp     short loc_180065D08
0x180065d06  xor     eax, eax
0x180065d08  mov     rdx, [rbx+18h]
0x180065d0c  jmp     short loc_180065D24
0x180065d0e  add     ecx, 7
0x180065d11  and     ecx, 0FFFFFFF8h
0x180065d14  jz      short loc_180065D1C
0x180065d16  mov     rax, [rbx+18h]
0x180065d1a  jmp     short loc_180065D1E
0x180065d1c  xor     eax, eax
0x180065d1e  mov     edx, ecx
0x180065d20  add     rdx, [rbx+18h]
0x180065d24  mov     r8, rax
0x180065d27  mov     rcx, rbx
0x180065d2a  mov     rax, rdi
0x180065d2d  call    _guard_dispatch_icall
0x180065d32  mov     rbx, [rsp+38h+arg_0]
0x180065d37  add     rsp, 30h
0x180065d3b  pop     rdi
0x180065d3c  retn
```
