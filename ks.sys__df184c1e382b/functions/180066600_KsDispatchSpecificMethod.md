# KsDispatchSpecificMethod

- ea: `0x180066600`
- end: `0x1800666ae`
- name: `KsDispatchSpecificMethod`
- size: `174`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PFNKSHANDLER Handler)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010a74`

## callees

- `0x180019cb0`
- `0x180066600`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180066658`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180066658`

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
0x180066600  mov     [rsp+arg_0], rbx
0x180066605  push    rdi
0x180066606  sub     rsp, 30h
0x18006660a  mov     r8, [rcx+0B8h]
0x180066611  mov     rbx, rcx
0x180066614  mov     rdi, rdx
0x180066617  test    byte ptr [rbx+88h], 4
0x18006661e  mov     ecx, [r8+8]
0x180066622  jz      short loc_18006667E
0x180066624  test    ecx, ecx
0x180066626  jz      short loc_180066676
0x180066628  test    byte ptr [r8+1], 0FBh
0x18006662d  jz      short loc_180066670
0x18006662f  mov     rcx, [rbx+8]; MemoryDescriptorList
0x180066633  test    byte ptr [rcx+0Ah], 5
0x180066637  jz      short loc_18006663F
0x180066639  mov     rax, [rcx+18h]
0x18006663d  jmp     short loc_180066664
0x18006663f  xor     r9d, r9d; RequestedAddress
0x180066642  mov     [rsp+38h+Priority], 40000010h; Priority
0x18006664a  xor     edx, edx; AccessMode
0x18006664c  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x180066654  lea     r8d, [r9+1]; CacheType
0x180066658  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18006665f  nop     dword ptr [rax+rax+00h]
0x180066664  test    rax, rax
0x180066667  jnz     short loc_180066678
0x180066669  mov     eax, 0C000009Ah
0x18006666e  jmp     short loc_1800666A2
0x180066670  mov     rax, [rbx+70h]
0x180066674  jmp     short loc_180066678
0x180066676  xor     eax, eax
0x180066678  mov     rdx, [rbx+18h]
0x18006667c  jmp     short loc_180066694
0x18006667e  add     ecx, 7
0x180066681  and     ecx, 0FFFFFFF8h
0x180066684  jz      short loc_18006668C
0x180066686  mov     rax, [rbx+18h]
0x18006668a  jmp     short loc_18006668E
0x18006668c  xor     eax, eax
0x18006668e  mov     edx, ecx
0x180066690  add     rdx, [rbx+18h]
0x180066694  mov     r8, rax
0x180066697  mov     rcx, rbx
0x18006669a  mov     rax, rdi
0x18006669d  call    _guard_dispatch_icall
0x1800666a2  mov     rbx, [rsp+38h+arg_0]
0x1800666a7  add     rsp, 30h
0x1800666ab  pop     rdi
0x1800666ac  retn
```
