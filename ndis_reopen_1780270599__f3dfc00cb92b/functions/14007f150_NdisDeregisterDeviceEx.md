# NdisDeregisterDeviceEx

- ea: `0x14007f150`
- end: `0x14007f359`
- name: `NdisDeregisterDeviceEx`
- size: `521`
- prototype: `void __stdcall(NDIS_HANDLE NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x1400110b0`
- `0x1400400d0`
- `0x14007f150`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x14007f1e1`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14007f1e1`
- `ntoskrnl!IoDeleteDevice` at `0x14007f306`
- `ntoskrnl!IoDeleteDevice` at `0x14007f306`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007f2f6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007f2f6`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007f2dc`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007f2dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007f2c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007f2c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f1f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f234`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f26e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f299`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f1f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f234`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f26e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007f299`

## pseudocode

```c
void __stdcall NdisDeregisterDeviceEx(NDIS_HANDLE NdisDeviceHandle)
{
  char *v2; // rcx
  char v3; // al
  KSPIN_LOCK *v4; // rdi
  KIRQL v5; // al
  _QWORD *v6; // r9
  NDIS_HANDLE *v7; // rdx
  __int64 v8; // rdi
  NDIS_HANDLE *v9; // r9
  NDIS_HANDLE *v10; // r8
  KSPIN_LOCK *v11; // rcx
  __int64 v12; // r9
  char *v13; // rdx
  char **v14; // r8

  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      1,
      115,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)NdisDeviceHandle);
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  v2 = (char *)*((_QWORD *)NdisDeviceHandle + 3);
  v3 = *v2;
  if ( *v2 == 2 )
  {
    v4 = (KSPIN_LOCK *)(v2 + 392);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2 + 49);
    v12 = *((_QWORD *)NdisDeviceHandle + 1);
    v13 = (char *)NdisDeviceHandle + 8;
    if ( *(NDIS_HANDLE *)(v12 + 8) != (char *)NdisDeviceHandle + 8 )
      goto LABEL_14;
    goto LABEL_16;
  }
  if ( v3 == 4 )
  {
    v4 = (KSPIN_LOCK *)(v2 + 40);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2 + 5);
    v12 = *((_QWORD *)NdisDeviceHandle + 1);
    v13 = (char *)NdisDeviceHandle + 8;
    if ( *(NDIS_HANDLE *)(v12 + 8) != (char *)NdisDeviceHandle + 8 )
      goto LABEL_14;
LABEL_16:
    v14 = (char **)*((_QWORD *)v13 + 1);
    if ( *v14 == v13 )
    {
      *v14 = (char *)v12;
      *(_QWORD *)(v12 + 8) = v14;
      goto LABEL_18;
    }
LABEL_14:
    __fastfail(3u);
  }
  if ( v3 != 17 )
  {
    if ( v3 != -86 )
      goto LABEL_20;
    v4 = (KSPIN_LOCK *)((char *)IoGetDriverObjectExtension(**((PDRIVER_OBJECT **)v2 + 1), (PVOID)0x4E4D4944) + 392);
    v5 = KeAcquireSpinLockRaiseToDpc(v4);
    v6 = (_QWORD *)*((_QWORD *)NdisDeviceHandle + 1);
    if ( (NDIS_HANDLE)v6[1] == (char *)NdisDeviceHandle + 8 )
    {
      v7 = (NDIS_HANDLE *)*((_QWORD *)NdisDeviceHandle + 2);
      if ( *v7 == (char *)NdisDeviceHandle + 8 )
      {
        *v7 = v6;
        v6[1] = v7;
LABEL_18:
        v11 = v4;
        goto LABEL_19;
      }
    }
    goto LABEL_14;
  }
  v8 = *((_QWORD *)v2 + 470);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 392));
  v9 = (NDIS_HANDLE *)*((_QWORD *)NdisDeviceHandle + 1);
  if ( v9[1] != (char *)NdisDeviceHandle + 8 )
    goto LABEL_14;
  v10 = (NDIS_HANDLE *)*((_QWORD *)NdisDeviceHandle + 2);
  if ( *v10 != (char *)NdisDeviceHandle + 8 )
    goto LABEL_14;
  *v10 = v9;
  v11 = (KSPIN_LOCK *)(v8 + 392);
  v9[1] = v10;
LABEL_19:
  KeReleaseSpinLock(v11, v5);
LABEL_20:
  MmUnlockPagableImageSection(ImageSectionHandle);
  _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
  IoDeleteSymbolicLink((PUNICODE_STRING)NdisDeviceHandle + 18);
  IoDeleteDevice(*((PDEVICE_OBJECT *)NdisDeviceHandle + 4));
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      1,
      116,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)NdisDeviceHandle);
}

```

## disassembly

```asm
0x14007f150  mov     [rsp+arg_8], rbx
0x14007f155  mov     [rsp+arg_10], rbp
0x14007f15a  push    rsi
0x14007f15b  sub     rsp, 30h
0x14007f15f  mov     rbx, rcx
0x14007f162  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f169  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14007f170  lea     rbp, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007f177  jz      short loc_14007F1A1
0x14007f179  mov     qword ptr [rsp+38h+var_10], rcx; char
0x14007f17e  mov     r9d, 73h ; 's'; int
0x14007f184  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f18b  mov     r8d, 1; int
0x14007f191  mov     dl, 4; int
0x14007f193  mov     [rsp+38h+var_18], rbp; struct _GUID *
0x14007f198  mov     rcx, [rcx+40h]; int
0x14007f19c  call    WPP_RECORDER_SF_q
0x14007f1a1  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14007f1a8  mov     [rsp+38h+arg_0], rdi
0x14007f1ad  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14007f1b2  mov     rcx, [rbx+18h]
0x14007f1b6  movzx   eax, byte ptr [rcx]
0x14007f1b9  cmp     al, 2
0x14007f1bb  jz      loc_14007F28F
0x14007f1c1  cmp     al, 4
0x14007f1c3  jz      loc_14007F267
0x14007f1c9  cmp     al, 11h
0x14007f1cb  jz      short loc_14007F226
0x14007f1cd  cmp     al, 0AAh
0x14007f1cf  jnz     loc_14007F2D5
0x14007f1d5  mov     rcx, [rcx+8]
0x14007f1d9  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x14007f1de  mov     rcx, [rcx]; DriverObject
0x14007f1e1  call    cs:__imp_IoGetDriverObjectExtension
0x14007f1e8  nop     dword ptr [rax+rax+00h]
0x14007f1ed  lea     rdi, [rax+188h]
0x14007f1f4  mov     rcx, rdi; SpinLock
0x14007f1f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007f1fe  nop     dword ptr [rax+rax+00h]
0x14007f203  mov     r9, [rbx+8]
0x14007f207  lea     r8, [rbx+8]
0x14007f20b  cmp     [r9+8], r8
0x14007f20f  jnz     short loc_14007F288
0x14007f211  mov     rdx, [r8+8]
0x14007f215  cmp     [rdx], r8
0x14007f218  jnz     short loc_14007F288
0x14007f21a  mov     [rdx], r9
0x14007f21d  mov     [r9+8], rdx
0x14007f221  jmp     loc_14007F2C3
0x14007f226  mov     rdi, [rcx+0EB0h]
0x14007f22d  lea     rcx, [rdi+188h]; SpinLock
0x14007f234  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007f23b  nop     dword ptr [rax+rax+00h]
0x14007f240  mov     r9, [rbx+8]
0x14007f244  lea     rdx, [rbx+8]
0x14007f248  cmp     [r9+8], rdx
0x14007f24c  jnz     short loc_14007F288
0x14007f24e  mov     r8, [rdx+8]
0x14007f252  cmp     [r8], rdx
0x14007f255  jnz     short loc_14007F288
0x14007f257  mov     [r8], r9
0x14007f25a  lea     rcx, [rdi+188h]
0x14007f261  mov     [r9+8], r8
0x14007f265  jmp     short loc_14007F2C6
0x14007f267  lea     rdi, [rcx+28h]
0x14007f26b  mov     rcx, rdi; SpinLock
0x14007f26e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007f275  nop     dword ptr [rax+rax+00h]
0x14007f27a  mov     r9, [rbx+8]
0x14007f27e  lea     rdx, [rbx+8]
0x14007f282  cmp     [r9+8], rdx
0x14007f286  jz      short loc_14007F2B3
0x14007f288  mov     ecx, 3
0x14007f28d  int     29h; Win8: RtlFailFast(ecx)
0x14007f28f  lea     rdi, [rcx+188h]
0x14007f296  mov     rcx, rdi; SpinLock
0x14007f299  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007f2a0  nop     dword ptr [rax+rax+00h]
0x14007f2a5  mov     r9, [rbx+8]
0x14007f2a9  lea     rdx, [rbx+8]
0x14007f2ad  cmp     [r9+8], rdx
0x14007f2b1  jnz     short loc_14007F288
0x14007f2b3  mov     r8, [rdx+8]
0x14007f2b7  cmp     [r8], rdx
0x14007f2ba  jnz     short loc_14007F288
0x14007f2bc  mov     [r8], r9
0x14007f2bf  mov     [r9+8], r8
0x14007f2c3  mov     rcx, rdi; SpinLock
0x14007f2c6  movzx   edx, al; NewIrql
0x14007f2c9  call    cs:__imp_KeReleaseSpinLock
0x14007f2d0  nop     dword ptr [rax+rax+00h]
0x14007f2d5  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x14007f2dc  call    cs:__imp_MmUnlockPagableImageSection
0x14007f2e3  nop     dword ptr [rax+rax+00h]
0x14007f2e8  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x14007f2ef  lea     rcx, [rbx+120h]; SymbolicLinkName
0x14007f2f6  call    cs:__imp_IoDeleteSymbolicLink
0x14007f2fd  nop     dword ptr [rax+rax+00h]
0x14007f302  mov     rcx, [rbx+20h]; DeviceObject
0x14007f306  call    cs:__imp_IoDeleteDevice
0x14007f30d  nop     dword ptr [rax+rax+00h]
0x14007f312  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14007f319  jz      short loc_14007F343
0x14007f31b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f322  mov     r9d, 74h ; 't'; int
0x14007f328  mov     qword ptr [rsp+38h+var_10], rbx; char
0x14007f32d  mov     r8d, 1; int
0x14007f333  mov     dl, 4; int
0x14007f335  mov     [rsp+38h+var_18], rbp; struct _GUID *
0x14007f33a  mov     rcx, [rcx+40h]; int
0x14007f33e  call    WPP_RECORDER_SF_q
0x14007f343  mov     rdi, [rsp+38h+arg_0]
0x14007f348  mov     rbx, [rsp+38h+arg_8]
0x14007f34d  mov     rbp, [rsp+38h+arg_10]
0x14007f352  add     rsp, 30h
0x14007f356  pop     rsi
0x14007f357  retn
```
