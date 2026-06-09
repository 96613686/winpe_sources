# MupiUncHardeningRegistryWatcherKeyChangeNotification

- ea: `0x140015430`
- end: `0x1400155fd`
- name: `MupiUncHardeningRegistryWatcherKeyChangeNotification`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140015210`
- `0x14001524c`
- `0x1400153d0`
- `0x140015430`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140015491`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015491`
- `ntoskrnl!ZwClose` at `0x140015516`
- `ntoskrnl!ZwClose` at `0x140015579`
- `ntoskrnl!ZwClose` at `0x140015516`
- `ntoskrnl!ZwClose` at `0x140015579`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155d3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400154a3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400154a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400155c7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400155c7`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001544c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001544c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400155e3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400155e3`
- `ntoskrnl!ZwQueryKey` at `0x1400154ca`
- `ntoskrnl!ZwQueryKey` at `0x1400154ca`

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
0x140015430  push    rbx
0x140015432  push    rbp
0x140015433  push    rsi
0x140015434  push    rdi
0x140015435  push    r12
0x140015437  push    r14
0x140015439  sub     rsp, 38h
0x14001543d  mov     rdi, rcx
0x140015440  mov     [rsp+68h+arg_0], 0
0x140015448  add     rcx, 10h; RunRef
0x14001544c  call    cs:__imp_ExAcquireRundownProtection
0x140015453  nop     dword ptr [rax+rax+00h]
0x140015458  test    al, al
0x14001545a  jz      loc_1400155EF
0x140015460  mov     rcx, cs:WPP_GLOBAL_Control
0x140015467  lea     r12, WPP_GLOBAL_Control
0x14001546e  cmp     rcx, r12
0x140015471  jz      short loc_140015491
0x140015473  test    dword ptr [rcx+2Ch], 4000000h
0x14001547a  jz      short loc_140015491
0x14001547c  mov     rcx, [rcx+18h]
0x140015480  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015487  mov     edx, 0Ah
0x14001548c  call    WPP_SF_
0x140015491  call    cs:__imp_KeEnterCriticalRegion
0x140015498  nop     dword ptr [rax+rax+00h]
0x14001549d  xor     edx, edx
0x14001549f  lea     rcx, [rdi+18h]
0x1400154a3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400154aa  nop     dword ptr [rax+rax+00h]
0x1400154af  xor     r9d, r9d; Length
0x1400154b2  lea     rax, [rsp+68h+arg_0]
0x1400154b7  lea     rbx, [rdi+20h]
0x1400154bb  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1400154c0  mov     rcx, [rbx]; KeyHandle
0x1400154c3  xor     r8d, r8d; KeyInformation
0x1400154c6  lea     edx, [r9+4]; KeyInformationClass
0x1400154ca  call    cs:__imp_ZwQueryKey
0x1400154d1  nop     dword ptr [rax+rax+00h]
0x1400154d6  cmp     eax, 0C000017Ch
0x1400154db  jz      short loc_1400154E4
0x1400154dd  cmp     eax, 0C0000425h
0x1400154e2  jnz     short loc_140015562
0x1400154e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154eb  cmp     rcx, r12
0x1400154ee  jz      short loc_14001550E
0x1400154f0  test    dword ptr [rcx+2Ch], 2000000h
0x1400154f7  jz      short loc_14001550E
0x1400154f9  mov     rcx, [rcx+18h]
0x1400154fd  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015504  mov     edx, 0Bh
0x140015509  call    WPP_SF_
0x14001550e  mov     rcx, [rbx]; Handle
0x140015511  test    rcx, rcx
0x140015514  jz      short loc_140015529
0x140015516  call    cs:__imp_ZwClose
0x14001551d  nop     dword ptr [rax+rax+00h]
0x140015522  mov     qword ptr [rbx], 0
0x140015529  mov     rcx, rbx
0x14001552c  call    MupiOpenUncHardeningRegistryKey
0x140015531  test    eax, eax
0x140015533  jns     short loc_140015562
0x140015535  mov     rcx, cs:WPP_GLOBAL_Control
0x14001553c  cmp     rcx, r12
0x14001553f  jz      short loc_140015562
0x140015541  test    dword ptr [rcx+2Ch], 1000000h
0x140015548  jz      short loc_140015562
0x14001554a  mov     rcx, [rcx+18h]
0x14001554e  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015555  mov     edx, 0Ch
0x14001555a  mov     r9d, eax
0x14001555d  call    WPP_SF_d
0x140015562  cmp     qword ptr [rbx], 0
0x140015566  jz      short loc_1400155B9
0x140015568  mov     rcx, rdi
0x14001556b  call    MupiRegisterUncHardeningConfigurationRegistryChangeNotification
0x140015570  mov     esi, eax
0x140015572  test    eax, eax
0x140015574  jns     short loc_1400155B9
0x140015576  mov     rcx, [rbx]; Handle
0x140015579  call    cs:__imp_ZwClose
0x140015580  nop     dword ptr [rax+rax+00h]
0x140015585  mov     qword ptr [rbx], 0
0x14001558c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015593  cmp     rcx, r12
0x140015596  jz      short loc_1400155B9
0x140015598  test    dword ptr [rcx+2Ch], 1000000h
0x14001559f  jz      short loc_1400155B9
0x1400155a1  mov     rcx, [rcx+18h]
0x1400155a5  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x1400155ac  mov     edx, 0Dh
0x1400155b1  mov     r9d, esi
0x1400155b4  call    WPP_SF_d
0x1400155b9  mov     rcx, rdi
0x1400155bc  call    MupiArmUncHardeningConfigurationRefreshTimer
0x1400155c1  xor     edx, edx
0x1400155c3  lea     rcx, [rdi+18h]
0x1400155c7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400155ce  nop     dword ptr [rax+rax+00h]
0x1400155d3  call    cs:__imp_KeLeaveCriticalRegion
0x1400155da  nop     dword ptr [rax+rax+00h]
0x1400155df  lea     rcx, [rdi+10h]; RunRef
0x1400155e3  call    cs:__imp_ExReleaseRundownProtection
0x1400155ea  nop     dword ptr [rax+rax+00h]
0x1400155ef  add     rsp, 38h
0x1400155f3  pop     r14
0x1400155f5  pop     r12
0x1400155f7  pop     rdi
0x1400155f8  pop     rsi
0x1400155f9  pop     rbp
0x1400155fa  pop     rbx
0x1400155fb  retn
```
