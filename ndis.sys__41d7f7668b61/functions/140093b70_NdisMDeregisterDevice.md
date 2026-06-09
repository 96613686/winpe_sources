# NdisMDeregisterDevice

- ea: `0x140093b70`
- end: `0x140093c16`
- name: `NdisMDeregisterDevice`
- size: `166`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x1400400d0`
- `0x140053280`
- `0x140093b70`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140093bf5`
- `ntoskrnl!IoDeleteDevice` at `0x140093bf5`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140093be5`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140093be5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140093bc6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140093bc6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140093b94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140093b94`

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
0x140093b70  mov     [rsp+arg_0], rbx
0x140093b75  push    rdi
0x140093b76  sub     rsp, 20h
0x140093b7a  mov     rbx, [rcx+18h]
0x140093b7e  mov     rdi, rcx
0x140093b81  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140093b88  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140093b8d  lea     rcx, [rbx+188h]; SpinLock
0x140093b94  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140093b9b  nop     dword ptr [rax+rax+00h]
0x140093ba0  lea     rdx, [rdi+8]
0x140093ba4  mov     r9, [rdx]
0x140093ba7  cmp     [r9+8], rdx
0x140093bab  jnz     short loc_140093C0F
0x140093bad  mov     r8, [rdx+8]
0x140093bb1  cmp     [r8], rdx
0x140093bb4  jnz     short loc_140093C0F
0x140093bb6  mov     [r8], r9
0x140093bb9  lea     rcx, [rbx+188h]; SpinLock
0x140093bc0  mov     dl, al; NewIrql
0x140093bc2  mov     [r9+8], r8
0x140093bc6  call    cs:__imp_KeReleaseSpinLock
0x140093bcd  nop     dword ptr [rax+rax+00h]
0x140093bd2  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140093bd9  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140093bde  lea     rcx, [rdi+120h]; SymbolicLinkName
0x140093be5  call    cs:__imp_IoDeleteSymbolicLink
0x140093bec  nop     dword ptr [rax+rax+00h]
0x140093bf1  mov     rcx, [rdi+20h]; DeviceObject
0x140093bf5  call    cs:__imp_IoDeleteDevice
0x140093bfc  nop     dword ptr [rax+rax+00h]
0x140093c01  mov     rbx, [rsp+28h+arg_0]
0x140093c06  xor     eax, eax
0x140093c08  add     rsp, 20h
0x140093c0c  pop     rdi
0x140093c0d  retn
0x140093c0f  mov     ecx, 3
0x140093c14  int     29h; Win8: RtlFailFast(ecx)
```
