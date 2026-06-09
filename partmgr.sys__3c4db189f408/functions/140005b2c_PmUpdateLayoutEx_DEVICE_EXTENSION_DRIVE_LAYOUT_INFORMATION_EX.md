# PmUpdateLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140005b2c`
- end: `0x140005c49`
- name: `?PmUpdateLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x140007bcc`

## callees

- `0x140005b2c`
- `0x140005c50`
- `0x140005d78`
- `0x140008104`
- `0x14000a014`
- `0x14000ae88`
- `0x14000ce84`
- `0x14000d794`
- `0x14001ccb4`
- `0x140021300`
- `0x14002184c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140005b63`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c31`
- `ntoskrnl!KeReleaseMutex` at `0x140005bbc`
- `ntoskrnl!KeReleaseMutex` at `0x140005be9`
- `ntoskrnl!KeReleaseMutex` at `0x140005bbc`
- `ntoskrnl!KeReleaseMutex` at `0x140005be9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c0e`

## string_xrefs

- `0x140005c1a`: `PmUpdateLayoutEx`

## pseudocode

```c
__int64 __fastcall PmUpdateLayoutEx(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  char *DeviceExtension; // rbx
  struct _KMUTANT *v5; // rbx
  int v6; // esi
  int updated; // eax
  KIRQL v8; // bl

  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  PmSetLegacyRemovableFlag(a1, a2);
  v5 = (struct _KMUTANT *)(DeviceExtension + 104);
  KeWaitForSingleObject(v5, Executive, 0, 0, 0);
  PmRemoveIds(a1);
  if ( (ScReadNoFence((unsigned int *)a1 + 129) & 0x1000) != 0 )
  {
    updated = PmUpdatePartitionsLegacyRemovable(a1, a2);
  }
  else
  {
    if ( PmLayoutHasIds(a2) )
    {
      v6 = PmUpdateAttributes(a1, a2);
      if ( v6 < 0 || (v6 = PmValidateIds(a1, a2), v6 < 0) )
      {
        KeReleaseMutex(v5, 0);
        return (unsigned int)v6;
      }
    }
    updated = PmUpdatePartitions(a1, a2);
  }
  v6 = updated;
  KeReleaseMutex(v5, 0);
  if ( v6 >= 0 )
  {
    v6 = PmAssociatePartitions(a1, a2);
    if ( v6 >= 0 )
    {
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      PmQueueNotificationWorkItem(a1, "PmUpdateLayoutEx");
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v8);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005b2c  push    rbx
0x140005b2e  push    rbp
0x140005b2f  push    rsi
0x140005b30  push    rdi
0x140005b31  sub     rsp, 38h
0x140005b35  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140005b3c  mov     rdi, rdx
0x140005b3f  mov     rbp, rcx
0x140005b42  mov     rbx, [rax+40h]
0x140005b46  call    ?PmSetLegacyRemovableFlag@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmSetLegacyRemovableFlag(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005b4b  add     rbx, 68h ; 'h'
0x140005b4f  mov     [rsp+58h+Timeout], 0; Timeout
0x140005b58  mov     rcx, rbx; Object
0x140005b5b  xor     r9d, r9d; Alertable
0x140005b5e  xor     r8d, r8d; WaitMode
0x140005b61  xor     edx, edx; WaitReason
0x140005b63  call    cs:__imp_KeWaitForSingleObject
0x140005b6a  nop     dword ptr [rax+rax+00h]
0x140005b6f  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005b72  call    ?PmRemoveIds@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmRemoveIds(_DEVICE_EXTENSION *)
0x140005b77  lea     rcx, [rbp+204h]; unsigned int *
0x140005b7e  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140005b83  bt      eax, 0Ch
0x140005b87  jb      short loc_140005BD7
0x140005b89  mov     rcx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005b8c  call    ?PmLayoutHasIds@@YAEPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmLayoutHasIds(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005b91  test    al, al
0x140005b93  jz      short loc_140005BCA
0x140005b95  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005b98  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005b9b  call    ?PmUpdateAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmUpdateAttributes(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005ba0  mov     esi, eax
0x140005ba2  test    eax, eax
0x140005ba4  js      short loc_140005BB7
0x140005ba6  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005ba9  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005bac  call    ?PmValidateIds@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmValidateIds(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005bb1  mov     esi, eax
0x140005bb3  test    eax, eax
0x140005bb5  jns     short loc_140005BCA
0x140005bb7  xor     edx, edx; Wait
0x140005bb9  mov     rcx, rbx; Mutex
0x140005bbc  call    cs:__imp_KeReleaseMutex
0x140005bc3  nop     dword ptr [rax+rax+00h]
0x140005bc8  jmp     short loc_140005C3D
0x140005bca  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005bcd  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005bd0  call    ?PmUpdatePartitions@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmUpdatePartitions(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005bd5  jmp     short loc_140005BE2
0x140005bd7  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005bda  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005bdd  call    ?PmUpdatePartitionsLegacyRemovable@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmUpdatePartitionsLegacyRemovable(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005be2  xor     edx, edx; Wait
0x140005be4  mov     rcx, rbx; Mutex
0x140005be7  mov     esi, eax
0x140005be9  call    cs:__imp_KeReleaseMutex
0x140005bf0  nop     dword ptr [rax+rax+00h]
0x140005bf5  test    esi, esi
0x140005bf7  js      short loc_140005C3D
0x140005bf9  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005bfc  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005bff  call    ?PmAssociatePartitions@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmAssociatePartitions(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005c04  mov     esi, eax
0x140005c06  test    eax, eax
0x140005c08  js      short loc_140005C3D
0x140005c0a  lea     rcx, [rbp+70h]; SpinLock
0x140005c0e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c15  nop     dword ptr [rax+rax+00h]
0x140005c1a  lea     rdx, aPmupdatelayout; "PmUpdateLayoutEx"
0x140005c21  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140005c24  mov     bl, al
0x140005c26  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x140005c2b  mov     dl, bl; NewIrql
0x140005c2d  lea     rcx, [rbp+70h]; SpinLock
0x140005c31  call    cs:__imp_KeReleaseSpinLock
0x140005c38  nop     dword ptr [rax+rax+00h]
0x140005c3d  mov     eax, esi
0x140005c3f  add     rsp, 38h
0x140005c43  pop     rdi
0x140005c44  pop     rsi
0x140005c45  pop     rbp
0x140005c46  pop     rbx
0x140005c47  retn
```
