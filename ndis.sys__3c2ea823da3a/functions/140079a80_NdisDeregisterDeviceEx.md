# NdisDeregisterDeviceEx

- ea: `0x140079a80`
- end: `0x140079c89`
- name: `NdisDeregisterDeviceEx`
- size: `521`
- prototype: `void __stdcall(NDIS_HANDLE NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x14001cf50`
- `0x14003d920`
- `0x140079a80`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140079b11`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140079b11`
- `ntoskrnl!IoDeleteDevice` at `0x140079c36`
- `ntoskrnl!IoDeleteDevice` at `0x140079c36`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140079c26`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140079c26`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140079c0c`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140079c0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079bf9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079bf9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079b27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079b64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079b9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079bc9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079b27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079b64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079b9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079bc9`

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
0x140079a80  mov     [rsp+arg_8], rbx
0x140079a85  mov     [rsp+arg_10], rbp
0x140079a8a  push    rsi
0x140079a8b  sub     rsp, 30h
0x140079a8f  mov     rbx, rcx
0x140079a92  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079a99  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140079aa0  lea     rbp, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140079aa7  jz      short loc_140079AD1
0x140079aa9  mov     qword ptr [rsp+38h+var_10], rcx; char
0x140079aae  mov     r9d, 73h ; 's'; int
0x140079ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x140079abb  mov     r8d, 1; int
0x140079ac1  mov     dl, 4; int
0x140079ac3  mov     [rsp+38h+var_18], rbp; struct _GUID *
0x140079ac8  mov     rcx, [rcx+40h]; int
0x140079acc  call    WPP_RECORDER_SF_q
0x140079ad1  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140079ad8  mov     [rsp+38h+arg_0], rdi
0x140079add  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140079ae2  mov     rcx, [rbx+18h]
0x140079ae6  movzx   eax, byte ptr [rcx]
0x140079ae9  cmp     al, 2
0x140079aeb  jz      loc_140079BBF
0x140079af1  cmp     al, 4
0x140079af3  jz      loc_140079B97
0x140079af9  cmp     al, 11h
0x140079afb  jz      short loc_140079B56
0x140079afd  cmp     al, 0AAh
0x140079aff  jnz     loc_140079C05
0x140079b05  mov     rcx, [rcx+8]
0x140079b09  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x140079b0e  mov     rcx, [rcx]; DriverObject
0x140079b11  call    cs:__imp_IoGetDriverObjectExtension
0x140079b18  nop     dword ptr [rax+rax+00h]
0x140079b1d  lea     rdi, [rax+188h]
0x140079b24  mov     rcx, rdi; SpinLock
0x140079b27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140079b2e  nop     dword ptr [rax+rax+00h]
0x140079b33  mov     r9, [rbx+8]
0x140079b37  lea     r8, [rbx+8]
0x140079b3b  cmp     [r9+8], r8
0x140079b3f  jnz     short loc_140079BB8
0x140079b41  mov     rdx, [r8+8]
0x140079b45  cmp     [rdx], r8
0x140079b48  jnz     short loc_140079BB8
0x140079b4a  mov     [rdx], r9
0x140079b4d  mov     [r9+8], rdx
0x140079b51  jmp     loc_140079BF3
0x140079b56  mov     rdi, [rcx+0EB0h]
0x140079b5d  lea     rcx, [rdi+188h]; SpinLock
0x140079b64  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140079b6b  nop     dword ptr [rax+rax+00h]
0x140079b70  mov     r9, [rbx+8]
0x140079b74  lea     rdx, [rbx+8]
0x140079b78  cmp     [r9+8], rdx
0x140079b7c  jnz     short loc_140079BB8
0x140079b7e  mov     r8, [rdx+8]
0x140079b82  cmp     [r8], rdx
0x140079b85  jnz     short loc_140079BB8
0x140079b87  mov     [r8], r9
0x140079b8a  lea     rcx, [rdi+188h]
0x140079b91  mov     [r9+8], r8
0x140079b95  jmp     short loc_140079BF6
0x140079b97  lea     rdi, [rcx+28h]
0x140079b9b  mov     rcx, rdi; SpinLock
0x140079b9e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140079ba5  nop     dword ptr [rax+rax+00h]
0x140079baa  mov     r9, [rbx+8]
0x140079bae  lea     rdx, [rbx+8]
0x140079bb2  cmp     [r9+8], rdx
0x140079bb6  jz      short loc_140079BE3
0x140079bb8  mov     ecx, 3
0x140079bbd  int     29h; Win8: RtlFailFast(ecx)
0x140079bbf  lea     rdi, [rcx+188h]
0x140079bc6  mov     rcx, rdi; SpinLock
0x140079bc9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140079bd0  nop     dword ptr [rax+rax+00h]
0x140079bd5  mov     r9, [rbx+8]
0x140079bd9  lea     rdx, [rbx+8]
0x140079bdd  cmp     [r9+8], rdx
0x140079be1  jnz     short loc_140079BB8
0x140079be3  mov     r8, [rdx+8]
0x140079be7  cmp     [r8], rdx
0x140079bea  jnz     short loc_140079BB8
0x140079bec  mov     [r8], r9
0x140079bef  mov     [r9+8], r8
0x140079bf3  mov     rcx, rdi; SpinLock
0x140079bf6  movzx   edx, al; NewIrql
0x140079bf9  call    cs:__imp_KeReleaseSpinLock
0x140079c00  nop     dword ptr [rax+rax+00h]
0x140079c05  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x140079c0c  call    cs:__imp_MmUnlockPagableImageSection
0x140079c13  nop     dword ptr [rax+rax+00h]
0x140079c18  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x140079c1f  lea     rcx, [rbx+120h]; SymbolicLinkName
0x140079c26  call    cs:__imp_IoDeleteSymbolicLink
0x140079c2d  nop     dword ptr [rax+rax+00h]
0x140079c32  mov     rcx, [rbx+20h]; DeviceObject
0x140079c36  call    cs:__imp_IoDeleteDevice
0x140079c3d  nop     dword ptr [rax+rax+00h]
0x140079c42  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140079c49  jz      short loc_140079C73
0x140079c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c52  mov     r9d, 74h ; 't'; int
0x140079c58  mov     qword ptr [rsp+38h+var_10], rbx; char
0x140079c5d  mov     r8d, 1; int
0x140079c63  mov     dl, 4; int
0x140079c65  mov     [rsp+38h+var_18], rbp; struct _GUID *
0x140079c6a  mov     rcx, [rcx+40h]; int
0x140079c6e  call    WPP_RECORDER_SF_q
0x140079c73  mov     rdi, [rsp+38h+arg_0]
0x140079c78  mov     rbx, [rsp+38h+arg_8]
0x140079c7d  mov     rbp, [rsp+38h+arg_10]
0x140079c82  add     rsp, 30h
0x140079c86  pop     rsi
0x140079c87  retn
```
