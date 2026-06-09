# MupRefreshUncHardeningConfigurationTimerCallback

- ea: `0x140014ef0`
- end: `0x140015207`
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
- `0x140014ef0`
- `0x140015210`
- `0x14001524c`
- `0x1400153d0`
- `0x1400158f4`
- `0x140015980`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140014f68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015172`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014f68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015172`
- `ntoskrnl!ZwClose` at `0x140015023`
- `ntoskrnl!ZwClose` at `0x1400151cf`
- `ntoskrnl!ZwClose` at `0x140015023`
- `ntoskrnl!ZwClose` at `0x1400151cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001510a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400151ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001510a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400151ba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015183`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015183`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400151ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400151ae`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140014f9a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140014f9a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001507e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001507e`
- `ntoskrnl!PsInitialSystemProcess` at `0x14001508c`
- `ntoskrnl!ObDuplicateObject` at `0x1400150ba`
- `ntoskrnl!ObDuplicateObject` at `0x1400150ba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400150fe`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400150fe`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140014f7a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140014f7a`

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
0x140014ef0  mov     [rsp-28h+arg_0], rbx
0x140014ef5  mov     [rsp-28h+arg_10], rsi
0x140014efa  push    rbp
0x140014efb  push    rdi
0x140014efc  push    r13
0x140014efe  push    r14
0x140014f00  push    r15
0x140014f02  mov     rbp, rsp
0x140014f05  sub     rsp, 60h
0x140014f09  mov     r13, [rdx]
0x140014f0c  lea     rax, [rbp+var_20]
0x140014f10  mov     [rbp+var_18], rax
0x140014f14  mov     rbx, rdx
0x140014f17  lea     rax, [rbp+var_20]
0x140014f1b  mov     [rbp+Handle], 0
0x140014f23  mov     [rbp+var_20], rax
0x140014f27  lea     rax, [rbp+var_10]
0x140014f2b  mov     [rbp+var_8], rax
0x140014f2f  lea     rax, [rbp+var_10]
0x140014f33  mov     [rbp+var_10], rax
0x140014f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f3e  lea     rsi, WPP_GLOBAL_Control
0x140014f45  cmp     rcx, rsi
0x140014f48  jz      short loc_140014F68
0x140014f4a  test    dword ptr [rcx+2Ch], 4000000h
0x140014f51  jz      short loc_140014F68
0x140014f53  mov     rcx, [rcx+18h]
0x140014f57  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014f5e  mov     edx, 0Eh
0x140014f63  call    WPP_SF_
0x140014f68  call    cs:__imp_KeEnterCriticalRegion
0x140014f6f  nop     dword ptr [rax+rax+00h]
0x140014f74  xor     edx, edx
0x140014f76  lea     rcx, [rbx+18h]
0x140014f7a  call    cs:__imp_ExAcquirePushLockSharedEx
0x140014f81  nop     dword ptr [rax+rax+00h]
0x140014f86  lea     rdi, [rbx+20h]
0x140014f8a  mov     rdx, [rdi]
0x140014f8d  test    rdx, rdx
0x140014f90  jnz     loc_14001508C
0x140014f96  lea     rcx, [rbx+10h]; RunRef
0x140014f9a  call    cs:__imp_ExAcquireRundownProtection
0x140014fa1  nop     dword ptr [rax+rax+00h]
0x140014fa6  test    al, al
0x140014fa8  jz      loc_1400150F8
0x140014fae  mov     rcx, cs:WPP_GLOBAL_Control
0x140014fb5  cmp     rcx, rsi
0x140014fb8  jz      short loc_140014FD8
0x140014fba  test    dword ptr [rcx+2Ch], 4000000h
0x140014fc1  jz      short loc_140014FD8
0x140014fc3  mov     rcx, [rcx+18h]
0x140014fc7  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014fce  mov     edx, 0Fh
0x140014fd3  call    WPP_SF_
0x140014fd8  mov     rcx, rdi
0x140014fdb  call    MupiOpenUncHardeningRegistryKey
0x140014fe0  test    eax, eax
0x140014fe2  js      loc_140015072
0x140014fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x140014fef  cmp     rcx, rsi
0x140014ff2  jz      short loc_140015012
0x140014ff4  test    dword ptr [rcx+2Ch], 4000000h
0x140014ffb  jz      short loc_140015012
0x140014ffd  mov     rcx, [rcx+18h]
0x140015001  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015008  mov     edx, 10h
0x14001500d  call    WPP_SF_
0x140015012  mov     rcx, rbx
0x140015015  call    MupiRegisterUncHardeningConfigurationRegistryChangeNotification
0x14001501a  mov     esi, eax
0x14001501c  test    eax, eax
0x14001501e  jns     short loc_14001506B
0x140015020  mov     rcx, [rdi]; Handle
0x140015023  call    cs:__imp_ZwClose
0x14001502a  nop     dword ptr [rax+rax+00h]
0x14001502f  mov     qword ptr [rdi], 0
0x140015036  mov     r10, cs:WPP_GLOBAL_Control
0x14001503d  lea     rax, WPP_GLOBAL_Control
0x140015044  cmp     r10, rax
0x140015047  jz      short loc_14001506B
0x140015049  test    dword ptr [r10+2Ch], 1000000h
0x140015051  jz      short loc_14001506B
0x140015053  mov     rcx, [r10+18h]
0x140015057  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x14001505e  mov     edx, 11h
0x140015063  mov     r9d, esi
0x140015066  call    WPP_SF_d
0x14001506b  lea     rsi, WPP_GLOBAL_Control
0x140015072  mov     rcx, rbx
0x140015075  call    MupiArmUncHardeningConfigurationRefreshTimer
0x14001507a  lea     rcx, [rbx+10h]; RunRef
0x14001507e  call    cs:__imp_ExReleaseRundownProtection
0x140015085  nop     dword ptr [rax+rax+00h]
0x14001508a  jmp     short loc_1400150F8
0x14001508c  mov     rax, cs:__imp_PsInitialSystemProcess
0x140015093  lea     r9, [rbp+Handle]
0x140015097  mov     [rsp+60h+var_28], 0
0x14001509c  mov     [rsp+60h+var_30], 2
0x1400150a4  mov     [rsp+60h+var_38], 200h
0x1400150ac  mov     rcx, [rax]
0x1400150af  mov     r8, rcx
0x1400150b2  mov     [rsp+60h+var_40], 0
0x1400150ba  call    cs:__imp_ObDuplicateObject
0x1400150c1  nop     dword ptr [rax+rax+00h]
0x1400150c6  test    eax, eax
0x1400150c8  jns     short loc_1400150F8
0x1400150ca  mov     r10, cs:WPP_GLOBAL_Control
0x1400150d1  cmp     r10, rsi
0x1400150d4  jz      short loc_1400150F8
0x1400150d6  test    dword ptr [r10+2Ch], 1000000h
0x1400150de  jz      short loc_1400150F8
0x1400150e0  mov     rcx, [r10+18h]
0x1400150e4  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x1400150eb  mov     edx, 12h
0x1400150f0  mov     r9d, eax
0x1400150f3  call    WPP_SF_d
0x1400150f8  xor     edx, edx
0x1400150fa  lea     rcx, [rbx+18h]
0x1400150fe  call    cs:__imp_ExReleasePushLockSharedEx
0x140015105  nop     dword ptr [rax+rax+00h]
0x14001510a  call    cs:__imp_KeLeaveCriticalRegion
0x140015111  nop     dword ptr [rax+rax+00h]
0x140015116  cmp     [rbp+Handle], 0
0x14001511b  jz      loc_1400151DB
0x140015121  mov     rcx, [rdi]; KeyHandle
0x140015124  lea     rdx, [rbp+var_20]
0x140015128  call    MupiLoadUncHardeningConfigurationToList
0x14001512d  mov     r9d, eax
0x140015130  mov     eax, 80000000h
0x140015135  lea     ecx, [r9+rax]
0x140015139  test    eax, ecx
0x14001513b  jnz     short loc_140015172
0x14001513d  cmp     r9d, 0C000017Ch
0x140015144  jz      short loc_140015172
0x140015146  mov     rcx, cs:WPP_GLOBAL_Control
0x14001514d  cmp     rcx, rsi
0x140015150  jz      short loc_1400151C6
0x140015152  test    dword ptr [rcx+2Ch], 1000000h
0x140015159  jz      short loc_1400151C6
0x14001515b  mov     rcx, [rcx+18h]
0x14001515f  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140015166  mov     edx, 13h
0x14001516b  call    WPP_SF_d
0x140015170  jmp     short loc_1400151C6
0x140015172  call    cs:__imp_KeEnterCriticalRegion
0x140015179  nop     dword ptr [rax+rax+00h]
0x14001517e  xor     edx, edx
0x140015180  mov     rcx, r13
0x140015183  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001518a  nop     dword ptr [rax+rax+00h]
0x14001518f  lea     rdx, [r13+8]
0x140015193  lea     rcx, [rbp+var_10]
0x140015197  call    MupTransferListEntries
0x14001519c  lea     rdx, [rbp+var_20]
0x1400151a0  lea     rcx, [r13+8]
0x1400151a4  call    MupTransferListEntries
0x1400151a9  xor     edx, edx
0x1400151ab  mov     rcx, r13
0x1400151ae  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400151b5  nop     dword ptr [rax+rax+00h]
0x1400151ba  call    cs:__imp_KeLeaveCriticalRegion
0x1400151c1  nop     dword ptr [rax+rax+00h]
0x1400151c6  mov     rcx, [rbp+Handle]; Handle
0x1400151ca  test    rcx, rcx
0x1400151cd  jz      short loc_1400151DB
0x1400151cf  call    cs:__imp_ZwClose
0x1400151d6  nop     dword ptr [rax+rax+00h]
0x1400151db  lea     rcx, [rbp+var_10]
0x1400151df  call    MupiFreeUncHardeningConfigurationEntryList
0x1400151e4  lea     rcx, [rbp+var_20]
0x1400151e8  call    MupiFreeUncHardeningConfigurationEntryList
0x1400151ed  lea     r11, [rsp+60h+var_s0]
0x1400151f2  mov     rbx, [r11+30h]
0x1400151f6  mov     rsi, [r11+40h]
0x1400151fa  mov     rsp, r11
0x1400151fd  pop     r15
0x1400151ff  pop     r14
0x140015201  pop     r13
0x140015203  pop     rdi
0x140015204  pop     rbp
0x140015205  retn
```
