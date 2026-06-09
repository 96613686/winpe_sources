# MupRefreshUncHardeningConfigurationTimerCallback

- ea: `0x140014ea0`
- end: `0x1400151b7`
- name: `MupRefreshUncHardeningConfigurationTimerCallback`
- size: `791`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140003758`
- `0x140014ea0`
- `0x1400151c0`
- `0x1400151fc`
- `0x140015380`
- `0x1400158a4`
- `0x140015930`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140014f18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015122`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014f18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015122`
- `ntoskrnl!ZwClose` at `0x140014fd3`
- `ntoskrnl!ZwClose` at `0x14001517f`
- `ntoskrnl!ZwClose` at `0x140014fd3`
- `ntoskrnl!ZwClose` at `0x14001517f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400150ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001516a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400150ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001516a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015133`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015133`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001515e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001515e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140014f4a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140014f4a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001502e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001502e`
- `ntoskrnl!PsInitialSystemProcess` at `0x14001503c`
- `ntoskrnl!ObDuplicateObject` at `0x14001506a`
- `ntoskrnl!ObDuplicateObject` at `0x14001506a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400150ae`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400150ae`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140014f2a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140014f2a`

## pseudocode

```c
__int64 __fastcall MupRefreshUncHardeningConfigurationTimerCallback(__int64 a1, struct _EX_RUNDOWN_REF *a2)
{
  ULONG_PTR Count; // r13
  HANDLE *v4; // rdi
  ULONG_PTR v5; // rdx
  int v6; // esi
  int v7; // eax
  unsigned int UncHardeningConfigurationToList; // eax
  char v10; // [rsp+38h] [rbp-28h]
  __int64 v11; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v12; // [rsp+48h] [rbp-18h]
  __int64 v13; // [rsp+50h] [rbp-10h] BYREF
  __int64 *v14; // [rsp+58h] [rbp-8h]
  HANDLE Handle; // [rsp+98h] [rbp+38h] BYREF

  Count = a2->Count;
  v12 = &v11;
  Handle = 0;
  v11 = (__int64)&v11;
  v14 = &v13;
  v13 = (__int64)&v13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_eb42bca7873834c81d179869f75e418e_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&a2[3], 0);
  v4 = (HANDLE *)&a2[4];
  v5 = a2[4].Count;
  if ( v5 )
  {
    v10 = 0;
    v7 = ObDuplicateObject(
           PsInitialSystemProcess,
           v5,
           PsInitialSystemProcess,
           &Handle,
           0,
           512,
           2,
           v10,
           v11,
           v12,
           v13,
           v14);
    if ( v7 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_eb42bca7873834c81d179869f75e418e_Traceguids,
        (unsigned int)v7);
    }
  }
  else if ( ExAcquireRundownProtection(a2 + 2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_eb42bca7873834c81d179869f75e418e_Traceguids);
    }
    if ( (int)MupiOpenUncHardeningRegistryKey((void **)&a2[4]) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_eb42bca7873834c81d179869f75e418e_Traceguids);
      }
      v6 = MupiRegisterUncHardeningConfigurationRegistryChangeNotification(a2);
      if ( v6 < 0 )
      {
        ZwClose(*v4);
        *v4 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_eb42bca7873834c81d179869f75e418e_Traceguids,
            (unsigned int)v6);
        }
      }
    }
    MupiArmUncHardeningConfigurationRefreshTimer(a2);
    ExReleaseRundownProtection(a2 + 2);
  }
  ExReleasePushLockSharedEx(&a2[3], 0);
  KeLeaveCriticalRegion();
  if ( Handle )
  {
    UncHardeningConfigurationToList = MupiLoadUncHardeningConfigurationToList(*v4);
    if ( (int)(UncHardeningConfigurationToList + 0x80000000) < 0 || UncHardeningConfigurationToList == -1073741444 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(Count, 0);
      MupTransferListEntries(&v13, Count + 8);
      MupTransferListEntries(Count + 8, &v11);
      ExReleasePushLockExclusiveEx(Count, 0);
      KeLeaveCriticalRegion();
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_eb42bca7873834c81d179869f75e418e_Traceguids,
        UncHardeningConfigurationToList);
    }
    if ( Handle )
      ZwClose(Handle);
  }
  MupiFreeUncHardeningConfigurationEntryList(&v13);
  return MupiFreeUncHardeningConfigurationEntryList(&v11);
}

```

## disassembly

```asm
0x140014ea0  mov     [rsp-28h+arg_0], rbx
0x140014ea5  mov     [rsp-28h+arg_10], rsi
0x140014eaa  push    rbp
0x140014eab  push    rdi
0x140014eac  push    r13
0x140014eae  push    r14
0x140014eb0  push    r15
0x140014eb2  mov     rbp, rsp
0x140014eb5  sub     rsp, 60h
0x140014eb9  mov     r13, [rdx]
0x140014ebc  lea     rax, [rbp+var_20]
0x140014ec0  mov     [rbp+var_18], rax
0x140014ec4  mov     rbx, rdx
0x140014ec7  lea     rax, [rbp+var_20]
0x140014ecb  mov     [rbp+Handle], 0
0x140014ed3  mov     [rbp+var_20], rax
0x140014ed7  lea     rax, [rbp+var_10]
0x140014edb  mov     [rbp+var_8], rax
0x140014edf  lea     rax, [rbp+var_10]
0x140014ee3  mov     [rbp+var_10], rax
0x140014ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eee  lea     rsi, WPP_GLOBAL_Control
0x140014ef5  cmp     rcx, rsi
0x140014ef8  jz      short loc_140014F18
0x140014efa  test    dword ptr [rcx+2Ch], 4000000h
0x140014f01  jz      short loc_140014F18
0x140014f03  mov     rcx, [rcx+18h]
0x140014f07  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014f0e  mov     edx, 0Eh
0x140014f13  call    WPP_SF_
0x140014f18  call    cs:__imp_KeEnterCriticalRegion
0x140014f1f  nop     dword ptr [rax+rax+00h]
0x140014f24  xor     edx, edx
0x140014f26  lea     rcx, [rbx+18h]
0x140014f2a  call    cs:__imp_ExAcquirePushLockSharedEx
0x140014f31  nop     dword ptr [rax+rax+00h]
0x140014f36  lea     rdi, [rbx+20h]
0x140014f3a  mov     rdx, [rdi]
0x140014f3d  test    rdx, rdx
0x140014f40  jnz     loc_14001503C
0x140014f46  lea     rcx, [rbx+10h]; RunRef
0x140014f4a  call    cs:__imp_ExAcquireRundownProtection
0x140014f51  nop     dword ptr [rax+rax+00h]
0x140014f56  test    al, al
0x140014f58  jz      loc_1400150A8
0x140014f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f65  cmp     rcx, rsi
0x140014f68  jz      short loc_140014F88
0x140014f6a  test    dword ptr [rcx+2Ch], 4000000h
0x140014f71  jz      short loc_140014F88
0x140014f73  mov     rcx, [rcx+18h]
0x140014f77  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014f7e  mov     edx, 0Fh
0x140014f83  call    WPP_SF_
0x140014f88  mov     rcx, rdi
0x140014f8b  call    MupiOpenUncHardeningRegistryKey
0x140014f90  test    eax, eax
0x140014f92  js      loc_140015022
0x140014f98  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f9f  cmp     rcx, rsi
0x140014fa2  jz      short loc_140014FC2
0x140014fa4  test    dword ptr [rcx+2Ch], 4000000h
0x140014fab  jz      short loc_140014FC2
0x140014fad  mov     rcx, [rcx+18h]
0x140014fb1  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014fb8  mov     edx, 10h
0x140014fbd  call    WPP_SF_
0x140014fc2  mov     rcx, rbx
0x140014fc5  call    MupiRegisterUncHardeningConfigurationRegistryChangeNotification
0x140014fca  mov     esi, eax
0x140014fcc  test    eax, eax
0x140014fce  jns     short loc_14001501B
0x140014fd0  mov     rcx, [rdi]; Handle
0x140014fd3  call    cs:__imp_ZwClose
0x140014fda  nop     dword ptr [rax+rax+00h]
0x140014fdf  mov     qword ptr [rdi], 0
0x140014fe6  mov     r10, cs:WPP_GLOBAL_Control
0x140014fed  lea     rax, WPP_GLOBAL_Control
0x140014ff4  cmp     r10, rax
0x140014ff7  jz      short loc_14001501B
0x140014ff9  test    dword ptr [r10+2Ch], 1000000h
0x140015001  jz      short loc_14001501B
0x140015003  mov     rcx, [r10+18h]
0x140015007  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x14001500e  mov     edx, 11h
0x140015013  mov     r9d, esi
0x140015016  call    WPP_SF_d
0x14001501b  lea     rsi, WPP_GLOBAL_Control
0x140015022  mov     rcx, rbx
0x140015025  call    MupiArmUncHardeningConfigurationRefreshTimer
0x14001502a  lea     rcx, [rbx+10h]; RunRef
0x14001502e  call    cs:__imp_ExReleaseRundownProtection
0x140015035  nop     dword ptr [rax+rax+00h]
0x14001503a  jmp     short loc_1400150A8
0x14001503c  mov     rax, cs:__imp_PsInitialSystemProcess
0x140015043  lea     r9, [rbp+Handle]
0x140015047  mov     [rsp+60h+var_28], 0
0x14001504c  mov     [rsp+60h+var_30], 2
0x140015054  mov     [rsp+60h+var_38], 200h
0x14001505c  mov     rcx, [rax]
0x14001505f  mov     r8, rcx
0x140015062  mov     [rsp+60h+var_40], 0
0x14001506a  call    cs:__imp_ObDuplicateObject
0x140015071  nop     dword ptr [rax+rax+00h]
0x140015076  test    eax, eax
0x140015078  jns     short loc_1400150A8
0x14001507a  mov     r10, cs:WPP_GLOBAL_Control
0x140015081  cmp     r10, rsi
0x140015084  jz      short loc_1400150A8
0x140015086  test    dword ptr [r10+2Ch], 1000000h
0x14001508e  jz      short loc_1400150A8
0x140015090  mov     rcx, [r10+18h]
0x140015094  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x14001509b  mov     edx, 12h
0x1400150a0  mov     r9d, eax
0x1400150a3  call    WPP_SF_d
0x1400150a8  xor     edx, edx
0x1400150aa  lea     rcx, [rbx+18h]
0x1400150ae  call    cs:__imp_ExReleasePushLockSharedEx
0x1400150b5  nop     dword ptr [rax+rax+00h]
0x1400150ba  call    cs:__imp_KeLeaveCriticalRegion
0x1400150c1  nop     dword ptr [rax+rax+00h]
0x1400150c6  cmp     [rbp+Handle], 0
0x1400150cb  jz      loc_14001518B
0x1400150d1  mov     rcx, [rdi]; KeyHandle
0x1400150d4  lea     rdx, [rbp+var_20]
0x1400150d8  call    MupiLoadUncHardeningConfigurationToList
0x1400150dd  mov     r9d, eax
0x1400150e0  mov     eax, 80000000h
0x1400150e5  lea     ecx, [r9+rax]
0x1400150e9  test    eax, ecx
0x1400150eb  jnz     short loc_140015122
0x1400150ed  cmp     r9d, 0C000017Ch
0x1400150f4  jz      short loc_140015122
0x1400150f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150fd  cmp     rcx, rsi
0x140015100  jz      short loc_140015176
0x140015102  test    dword ptr [rcx+2Ch], 1000000h
0x140015109  jz      short loc_140015176
0x14001510b  mov     rcx, [rcx+18h]
0x14001510f  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015116  mov     edx, 13h
0x14001511b  call    WPP_SF_d
0x140015120  jmp     short loc_140015176
0x140015122  call    cs:__imp_KeEnterCriticalRegion
0x140015129  nop     dword ptr [rax+rax+00h]
0x14001512e  xor     edx, edx
0x140015130  mov     rcx, r13
0x140015133  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001513a  nop     dword ptr [rax+rax+00h]
0x14001513f  lea     rdx, [r13+8]
0x140015143  lea     rcx, [rbp+var_10]
0x140015147  call    MupTransferListEntries
0x14001514c  lea     rdx, [rbp+var_20]
0x140015150  lea     rcx, [r13+8]
0x140015154  call    MupTransferListEntries
0x140015159  xor     edx, edx
0x14001515b  mov     rcx, r13
0x14001515e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015165  nop     dword ptr [rax+rax+00h]
0x14001516a  call    cs:__imp_KeLeaveCriticalRegion
0x140015171  nop     dword ptr [rax+rax+00h]
0x140015176  mov     rcx, [rbp+Handle]; Handle
0x14001517a  test    rcx, rcx
0x14001517d  jz      short loc_14001518B
0x14001517f  call    cs:__imp_ZwClose
0x140015186  nop     dword ptr [rax+rax+00h]
0x14001518b  lea     rcx, [rbp+var_10]
0x14001518f  call    MupiFreeUncHardeningConfigurationEntryList
0x140015194  lea     rcx, [rbp+var_20]
0x140015198  call    MupiFreeUncHardeningConfigurationEntryList
0x14001519d  lea     r11, [rsp+60h+var_s0]
0x1400151a2  mov     rbx, [r11+30h]
0x1400151a6  mov     rsi, [r11+40h]
0x1400151aa  mov     rsp, r11
0x1400151ad  pop     r15
0x1400151af  pop     r14
0x1400151b1  pop     r13
0x1400151b3  pop     rdi
0x1400151b4  pop     rbp
0x1400151b5  retn
```
