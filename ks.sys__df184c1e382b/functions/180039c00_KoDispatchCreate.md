# KoDispatchCreate

- ea: `0x180039c00`
- end: `0x180039d31`
- name: `KoDispatchCreate`
- size: `305`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180039c00`
- `0x18004fea0`
- `0x180051630`
- `0x180059610`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x180039cb6`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x180039cb6`
- `ntoskrnl!IofCompleteRequest` at `0x180039d19`
- `ntoskrnl!IofCompleteRequest` at `0x180039d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039cdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180039cdf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039c5b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039c5b`

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
0x180039c00  push    rbx
0x180039c02  push    rbp
0x180039c03  push    rsi
0x180039c04  push    rdi
0x180039c05  sub     rsp, 38h
0x180039c09  cmp     byte ptr [rdx+40h], 0
0x180039c0d  mov     rdi, rdx
0x180039c10  mov     rbp, rcx
0x180039c13  jnz     loc_180039D0C
0x180039c19  mov     rax, [rdx+0B8h]
0x180039c20  mov     r8d, [rax+10h]
0x180039c24  mov     eax, 100100h
0x180039c29  and     r8d, eax
0x180039c2c  cmp     r8d, eax
0x180039c2f  jnz     loc_180039D0C
0x180039c35  mov     rcx, [rcx+40h]
0x180039c39  mov     rcx, [rcx]; Header
0x180039c3c  call    KsReferenceBusObject
0x180039c41  mov     ebx, eax
0x180039c43  test    eax, eax
0x180039c45  js      loc_180039D11
0x180039c4b  mov     edx, 10h; NumberOfBytes
0x180039c50  mov     ecx, 600h; PoolType
0x180039c55  mov     r8d, 4946734Bh; Tag
0x180039c5b  call    cs:__imp_ExAllocatePoolWithTag
0x180039c62  nop     dword ptr [rax+rax+00h]
0x180039c67  mov     rsi, rax
0x180039c6a  test    rax, rax
0x180039c6d  jz      loc_180039CF9
0x180039c73  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180039c7a  jnz     short loc_180039C82
0x180039c7c  xorps   xmm0, xmm0
0x180039c7f  movups  xmmword ptr [rax], xmm0
0x180039c82  lea     rax, stru_180079A00
0x180039c89  mov     r9, rdi; Irp
0x180039c8c  lea     r8, ItemsList; ItemsList
0x180039c93  mov     [rsp+58h+Table], rax; Table
0x180039c98  mov     edx, 1; ItemsCount
0x180039c9d  mov     rcx, rsi; Header
0x180039ca0  call    KsAllocateObjectHeader
0x180039ca5  mov     ebx, eax
0x180039ca7  test    eax, eax
0x180039ca9  js      short loc_180039CDA
0x180039cab  mov     rcx, [rbp+8]; DriverObject
0x180039caf  lea     rdx, KoDriverInitialize; ClientIdentificationAddress
0x180039cb6  call    cs:__imp_IoGetDriverObjectExtension
0x180039cbd  nop     dword ptr [rax+rax+00h]
0x180039cc2  mov     rcx, [rax]
0x180039cc5  mov     [rsi+8], rcx
0x180039cc9  mov     rax, [rdi+0B8h]
0x180039cd0  mov     rcx, [rax+30h]
0x180039cd4  mov     [rcx+18h], rsi
0x180039cd8  jmp     short loc_180039D11
0x180039cda  xor     edx, edx; Tag
0x180039cdc  mov     rcx, rsi; P
0x180039cdf  call    cs:__imp_ExFreePoolWithTag
0x180039ce6  nop     dword ptr [rax+rax+00h]
0x180039ceb  mov     rcx, [rbp+40h]
0x180039cef  mov     rcx, [rcx]; Header
0x180039cf2  call    KsDereferenceBusObject
0x180039cf7  jmp     short loc_180039D11
0x180039cf9  mov     rcx, [rbp+40h]
0x180039cfd  mov     rcx, [rcx]; Header
0x180039d00  call    KsDereferenceBusObject
0x180039d05  mov     ebx, 0C000009Ah
0x180039d0a  jmp     short loc_180039D11
0x180039d0c  mov     ebx, 0C0000022h
0x180039d11  xor     edx, edx; PriorityBoost
0x180039d13  mov     [rdi+30h], ebx
0x180039d16  mov     rcx, rdi; Irp
0x180039d19  call    cs:__imp_IofCompleteRequest
0x180039d20  nop     dword ptr [rax+rax+00h]
0x180039d25  mov     eax, ebx
0x180039d27  add     rsp, 38h
0x180039d2b  pop     rdi
0x180039d2c  pop     rsi
0x180039d2d  pop     rbp
0x180039d2e  pop     rbx
0x180039d2f  retn
```
