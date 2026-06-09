# MupiUncHardeningRegistryWatcherKeyChangeNotification

- ea: `0x1400153e0`
- end: `0x1400155ad`
- name: `MupiUncHardeningRegistryWatcherKeyChangeNotification`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x1400151c0`
- `0x1400151fc`
- `0x140015380`
- `0x1400153e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140015441`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015441`
- `ntoskrnl!ZwClose` at `0x1400154c6`
- `ntoskrnl!ZwClose` at `0x140015529`
- `ntoskrnl!ZwClose` at `0x1400154c6`
- `ntoskrnl!ZwClose` at `0x140015529`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015583`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015583`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015453`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015453`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015577`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015577`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400153fc`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400153fc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140015593`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140015593`
- `ntoskrnl!ZwQueryKey` at `0x14001547a`
- `ntoskrnl!ZwQueryKey` at `0x14001547a`

## pseudocode

```c
void __fastcall MupiUncHardeningRegistryWatcherKeyChangeNotification(struct _EX_RUNDOWN_REF *a1)
{
  HANDLE *v2; // rbx
  NTSTATUS v3; // eax
  int v4; // eax
  int v5; // esi
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  ResultLength = 0;
  if ( ExAcquireRundownProtection(a1 + 2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_eb42bca7873834c81d179869f75e418e_Traceguids);
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&a1[3], 0);
    v2 = (HANDLE *)&a1[4];
    v3 = ZwQueryKey(a1[4].Ptr, KeyCachedInformation, 0, 0, &ResultLength);
    if ( v3 == -1073741444 || v3 == -1073740763 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_eb42bca7873834c81d179869f75e418e_Traceguids);
      }
      if ( *v2 )
      {
        ZwClose(*v2);
        *v2 = 0;
      }
      v4 = MupiOpenUncHardeningRegistryKey((void **)&a1[4]);
      if ( v4 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_eb42bca7873834c81d179869f75e418e_Traceguids,
          (unsigned int)v4);
      }
    }
    if ( *v2 )
    {
      v5 = MupiRegisterUncHardeningConfigurationRegistryChangeNotification(a1);
      if ( v5 < 0 )
      {
        ZwClose(*v2);
        *v2 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_eb42bca7873834c81d179869f75e418e_Traceguids,
            (unsigned int)v5);
        }
      }
    }
    MupiArmUncHardeningConfigurationRefreshTimer(a1);
    ExReleasePushLockExclusiveEx(&a1[3], 0);
    KeLeaveCriticalRegion();
    ExReleaseRundownProtection(a1 + 2);
  }
}

```

## disassembly

```asm
0x1400153e0  push    rbx
0x1400153e2  push    rbp
0x1400153e3  push    rsi
0x1400153e4  push    rdi
0x1400153e5  push    r12
0x1400153e7  push    r14
0x1400153e9  sub     rsp, 38h
0x1400153ed  mov     rdi, rcx
0x1400153f0  mov     [rsp+68h+arg_0], 0
0x1400153f8  add     rcx, 10h; RunRef
0x1400153fc  call    cs:__imp_ExAcquireRundownProtection
0x140015403  nop     dword ptr [rax+rax+00h]
0x140015408  test    al, al
0x14001540a  jz      loc_14001559F
0x140015410  mov     rcx, cs:WPP_GLOBAL_Control
0x140015417  lea     r12, WPP_GLOBAL_Control
0x14001541e  cmp     rcx, r12
0x140015421  jz      short loc_140015441
0x140015423  test    dword ptr [rcx+2Ch], 4000000h
0x14001542a  jz      short loc_140015441
0x14001542c  mov     rcx, [rcx+18h]
0x140015430  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015437  mov     edx, 0Ah
0x14001543c  call    WPP_SF_
0x140015441  call    cs:__imp_KeEnterCriticalRegion
0x140015448  nop     dword ptr [rax+rax+00h]
0x14001544d  xor     edx, edx
0x14001544f  lea     rcx, [rdi+18h]
0x140015453  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001545a  nop     dword ptr [rax+rax+00h]
0x14001545f  xor     r9d, r9d; Length
0x140015462  lea     rax, [rsp+68h+arg_0]
0x140015467  lea     rbx, [rdi+20h]
0x14001546b  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140015470  mov     rcx, [rbx]; KeyHandle
0x140015473  xor     r8d, r8d; KeyInformation
0x140015476  lea     edx, [r9+4]; KeyInformationClass
0x14001547a  call    cs:__imp_ZwQueryKey
0x140015481  nop     dword ptr [rax+rax+00h]
0x140015486  cmp     eax, 0C000017Ch
0x14001548b  jz      short loc_140015494
0x14001548d  cmp     eax, 0C0000425h
0x140015492  jnz     short loc_140015512
0x140015494  mov     rcx, cs:WPP_GLOBAL_Control
0x14001549b  cmp     rcx, r12
0x14001549e  jz      short loc_1400154BE
0x1400154a0  test    dword ptr [rcx+2Ch], 2000000h
0x1400154a7  jz      short loc_1400154BE
0x1400154a9  mov     rcx, [rcx+18h]
0x1400154ad  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x1400154b4  mov     edx, 0Bh
0x1400154b9  call    WPP_SF_
0x1400154be  mov     rcx, [rbx]; Handle
0x1400154c1  test    rcx, rcx
0x1400154c4  jz      short loc_1400154D9
0x1400154c6  call    cs:__imp_ZwClose
0x1400154cd  nop     dword ptr [rax+rax+00h]
0x1400154d2  mov     qword ptr [rbx], 0
0x1400154d9  mov     rcx, rbx
0x1400154dc  call    MupiOpenUncHardeningRegistryKey
0x1400154e1  test    eax, eax
0x1400154e3  jns     short loc_140015512
0x1400154e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154ec  cmp     rcx, r12
0x1400154ef  jz      short loc_140015512
0x1400154f1  test    dword ptr [rcx+2Ch], 1000000h
0x1400154f8  jz      short loc_140015512
0x1400154fa  mov     rcx, [rcx+18h]
0x1400154fe  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015505  mov     edx, 0Ch
0x14001550a  mov     r9d, eax
0x14001550d  call    WPP_SF_d
0x140015512  cmp     qword ptr [rbx], 0
0x140015516  jz      short loc_140015569
0x140015518  mov     rcx, rdi
0x14001551b  call    MupiRegisterUncHardeningConfigurationRegistryChangeNotification
0x140015520  mov     esi, eax
0x140015522  test    eax, eax
0x140015524  jns     short loc_140015569
0x140015526  mov     rcx, [rbx]; Handle
0x140015529  call    cs:__imp_ZwClose
0x140015530  nop     dword ptr [rax+rax+00h]
0x140015535  mov     qword ptr [rbx], 0
0x14001553c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015543  cmp     rcx, r12
0x140015546  jz      short loc_140015569
0x140015548  test    dword ptr [rcx+2Ch], 1000000h
0x14001554f  jz      short loc_140015569
0x140015551  mov     rcx, [rcx+18h]
0x140015555  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x14001555c  mov     edx, 0Dh
0x140015561  mov     r9d, esi
0x140015564  call    WPP_SF_d
0x140015569  mov     rcx, rdi
0x14001556c  call    MupiArmUncHardeningConfigurationRefreshTimer
0x140015571  xor     edx, edx
0x140015573  lea     rcx, [rdi+18h]
0x140015577  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001557e  nop     dword ptr [rax+rax+00h]
0x140015583  call    cs:__imp_KeLeaveCriticalRegion
0x14001558a  nop     dword ptr [rax+rax+00h]
0x14001558f  lea     rcx, [rdi+10h]; RunRef
0x140015593  call    cs:__imp_ExReleaseRundownProtection
0x14001559a  nop     dword ptr [rax+rax+00h]
0x14001559f  add     rsp, 38h
0x1400155a3  pop     r14
0x1400155a5  pop     r12
0x1400155a7  pop     rdi
0x1400155a8  pop     rsi
0x1400155a9  pop     rbp
0x1400155aa  pop     rbx
0x1400155ab  retn
```
