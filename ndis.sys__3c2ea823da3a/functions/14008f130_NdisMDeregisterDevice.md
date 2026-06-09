# NdisMDeregisterDevice

- ea: `0x14008f130`
- end: `0x14008f1d6`
- name: `NdisMDeregisterDevice`
- size: `166`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x14003d920`
- `0x14004e050`
- `0x14008f130`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14008f1b5`
- `ntoskrnl!IoDeleteDevice` at `0x14008f1b5`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14008f1a5`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14008f1a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008f186`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008f186`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008f154`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008f154`

## pseudocode

```c
NDIS_STATUS __stdcall NdisMDeregisterDevice(NDIS_HANDLE NdisDeviceHandle)
{
  __int64 v1; // rbx
  KIRQL v3; // al
  NDIS_HANDLE *v4; // r9
  NDIS_HANDLE *v5; // r8

  v1 = *((_QWORD *)NdisDeviceHandle + 3);
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 392));
  v4 = (NDIS_HANDLE *)*((_QWORD *)NdisDeviceHandle + 1);
  if ( v4[1] != (char *)NdisDeviceHandle + 8
    || (v5 = (NDIS_HANDLE *)*((_QWORD *)NdisDeviceHandle + 2), *v5 != (char *)NdisDeviceHandle + 8) )
  {
    __fastfail(3u);
  }
  *v5 = v4;
  v4[1] = v5;
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 392), v3);
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  IoDeleteSymbolicLink((PUNICODE_STRING)NdisDeviceHandle + 18);
  IoDeleteDevice(*((PDEVICE_OBJECT *)NdisDeviceHandle + 4));
  return 0;
}

```

## disassembly

```asm
0x14008f130  mov     [rsp+arg_0], rbx
0x14008f135  push    rdi
0x14008f136  sub     rsp, 20h
0x14008f13a  mov     rbx, [rcx+18h]
0x14008f13e  mov     rdi, rcx
0x14008f141  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14008f148  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14008f14d  lea     rcx, [rbx+188h]; SpinLock
0x14008f154  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008f15b  nop     dword ptr [rax+rax+00h]
0x14008f160  lea     rdx, [rdi+8]
0x14008f164  mov     r9, [rdx]
0x14008f167  cmp     [r9+8], rdx
0x14008f16b  jnz     short loc_14008F1CF
0x14008f16d  mov     r8, [rdx+8]
0x14008f171  cmp     [r8], rdx
0x14008f174  jnz     short loc_14008F1CF
0x14008f176  mov     [r8], r9
0x14008f179  lea     rcx, [rbx+188h]; SpinLock
0x14008f180  mov     dl, al; NewIrql
0x14008f182  mov     [r9+8], r8
0x14008f186  call    cs:__imp_KeReleaseSpinLock
0x14008f18d  nop     dword ptr [rax+rax+00h]
0x14008f192  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14008f199  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14008f19e  lea     rcx, [rdi+120h]; SymbolicLinkName
0x14008f1a5  call    cs:__imp_IoDeleteSymbolicLink
0x14008f1ac  nop     dword ptr [rax+rax+00h]
0x14008f1b1  mov     rcx, [rdi+20h]; DeviceObject
0x14008f1b5  call    cs:__imp_IoDeleteDevice
0x14008f1bc  nop     dword ptr [rax+rax+00h]
0x14008f1c1  mov     rbx, [rsp+28h+arg_0]
0x14008f1c6  xor     eax, eax
0x14008f1c8  add     rsp, 20h
0x14008f1cc  pop     rdi
0x14008f1cd  retn
0x14008f1cf  mov     ecx, 3
0x14008f1d4  int     29h; Win8: RtlFailFast(ecx)
```
