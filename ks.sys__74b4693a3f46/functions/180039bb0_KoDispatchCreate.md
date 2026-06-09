# KoDispatchCreate

- ea: `0x180039bb0`
- end: `0x180039ce1`
- name: `KoDispatchCreate`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180039bb0`
- `0x18004fd00`
- `0x180051490`
- `0x180059470`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x180039c66`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x180039c66`
- `ntoskrnl!IofCompleteRequest` at `0x180039cc9`
- `ntoskrnl!IofCompleteRequest` at `0x180039cc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039c8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039c8f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039c0b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039c0b`

## pseudocode

```c
__int64 __fastcall KoDispatchCreate(__int64 a1, IRP *a2)
{
  NTSTATUS ObjectHeader; // ebx
  KSOBJECT_HEADER *PoolWithTag; // rax
  KSOBJECT_HEADER *v6; // rsi

  if ( a2->RequestorMode || (a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options & 0x100100) != 0x100100 )
  {
    ObjectHeader = -1073741790;
  }
  else
  {
    ObjectHeader = KsReferenceBusObject(**(KSDEVICE_HEADER **)(a1 + 64));
    if ( ObjectHeader >= 0 )
    {
      PoolWithTag = (KSOBJECT_HEADER *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x10u, 0x4946734Bu);
      v6 = PoolWithTag;
      if ( PoolWithTag )
      {
        if ( !ExPoolZeroingNativelySupported )
          *(_OWORD *)PoolWithTag = 0;
        ObjectHeader = KsAllocateObjectHeader(PoolWithTag, 1u, (PKSOBJECT_CREATE_ITEM)&ItemsList, a2, &stru_180079A00);
        if ( ObjectHeader < 0 )
        {
          ExFreePoolWithTag(v6, 0);
          KsDereferenceBusObject(**(KSDEVICE_HEADER **)(a1 + 64));
        }
        else
        {
          v6[1] = *(KSOBJECT_HEADER *)IoGetDriverObjectExtension(*(PDRIVER_OBJECT *)(a1 + 8), KoDriverInitialize);
          a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext = v6;
        }
      }
      else
      {
        KsDereferenceBusObject(**(KSDEVICE_HEADER **)(a1 + 64));
        ObjectHeader = -1073741670;
      }
    }
  }
  a2->IoStatus.Status = ObjectHeader;
  IofCompleteRequest(a2, 0);
  return (unsigned int)ObjectHeader;
}

```

## disassembly

```asm
0x180039bb0  push    rbx
0x180039bb2  push    rbp
0x180039bb3  push    rsi
0x180039bb4  push    rdi
0x180039bb5  sub     rsp, 38h
0x180039bb9  cmp     byte ptr [rdx+40h], 0
0x180039bbd  mov     rdi, rdx
0x180039bc0  mov     rbp, rcx
0x180039bc3  jnz     loc_180039CBC
0x180039bc9  mov     rax, [rdx+0B8h]
0x180039bd0  mov     r8d, [rax+10h]
0x180039bd4  mov     eax, 100100h
0x180039bd9  and     r8d, eax
0x180039bdc  cmp     r8d, eax
0x180039bdf  jnz     loc_180039CBC
0x180039be5  mov     rcx, [rcx+40h]
0x180039be9  mov     rcx, [rcx]; Header
0x180039bec  call    KsReferenceBusObject
0x180039bf1  mov     ebx, eax
0x180039bf3  test    eax, eax
0x180039bf5  js      loc_180039CC1
0x180039bfb  mov     edx, 10h; NumberOfBytes
0x180039c00  mov     ecx, 600h; PoolType
0x180039c05  mov     r8d, 4946734Bh; Tag
0x180039c0b  call    cs:__imp_ExAllocatePoolWithTag
0x180039c12  nop     dword ptr [rax+rax+00h]
0x180039c17  mov     rsi, rax
0x180039c1a  test    rax, rax
0x180039c1d  jz      loc_180039CA9
0x180039c23  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180039c2a  jnz     short loc_180039C32
0x180039c2c  xorps   xmm0, xmm0
0x180039c2f  movups  xmmword ptr [rax], xmm0
0x180039c32  lea     rax, stru_180079A00
0x180039c39  mov     r9, rdi; Irp
0x180039c3c  lea     r8, ItemsList; ItemsList
0x180039c43  mov     [rsp+58h+Table], rax; Table
0x180039c48  mov     edx, 1; ItemsCount
0x180039c4d  mov     rcx, rsi; Header
0x180039c50  call    KsAllocateObjectHeader
0x180039c55  mov     ebx, eax
0x180039c57  test    eax, eax
0x180039c59  js      short loc_180039C8A
0x180039c5b  mov     rcx, [rbp+8]; DriverObject
0x180039c5f  lea     rdx, KoDriverInitialize; ClientIdentificationAddress
0x180039c66  call    cs:__imp_IoGetDriverObjectExtension
0x180039c6d  nop     dword ptr [rax+rax+00h]
0x180039c72  mov     rcx, [rax]
0x180039c75  mov     [rsi+8], rcx
0x180039c79  mov     rax, [rdi+0B8h]
0x180039c80  mov     rcx, [rax+30h]
0x180039c84  mov     [rcx+18h], rsi
0x180039c88  jmp     short loc_180039CC1
0x180039c8a  xor     edx, edx; Tag
0x180039c8c  mov     rcx, rsi; P
0x180039c8f  call    cs:__imp_ExFreePoolWithTag
0x180039c96  nop     dword ptr [rax+rax+00h]
0x180039c9b  mov     rcx, [rbp+40h]
0x180039c9f  mov     rcx, [rcx]; Header
0x180039ca2  call    KsDereferenceBusObject
0x180039ca7  jmp     short loc_180039CC1
0x180039ca9  mov     rcx, [rbp+40h]
0x180039cad  mov     rcx, [rcx]; Header
0x180039cb0  call    KsDereferenceBusObject
0x180039cb5  mov     ebx, 0C000009Ah
0x180039cba  jmp     short loc_180039CC1
0x180039cbc  mov     ebx, 0C0000022h
0x180039cc1  xor     edx, edx; PriorityBoost
0x180039cc3  mov     [rdi+30h], ebx
0x180039cc6  mov     rcx, rdi; Irp
0x180039cc9  call    cs:__imp_IofCompleteRequest
0x180039cd0  nop     dword ptr [rax+rax+00h]
0x180039cd5  mov     eax, ebx
0x180039cd7  add     rsp, 38h
0x180039cdb  pop     rdi
0x180039cdc  pop     rsi
0x180039cdd  pop     rbp
0x180039cde  pop     rbx
0x180039cdf  retn
```
