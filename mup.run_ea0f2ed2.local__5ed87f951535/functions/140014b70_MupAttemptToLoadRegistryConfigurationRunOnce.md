# MupAttemptToLoadRegistryConfigurationRunOnce

- ea: `0x140014b70`
- end: `0x140014c69`
- name: `MupAttemptToLoadRegistryConfigurationRunOnce`
- size: `249`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140014b70`
- `0x1400151fc`
- `0x140015380`
- `0x1400158a4`
- `0x140015930`
- `0x14001f030`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140014c14`
- `ntoskrnl!ZwClose` at `0x140014c14`

## pseudocode

```c
__int64 __fastcall MupAttemptToLoadRegistryConfigurationRunOnce(PRTL_RUN_ONCE a1, void **a2, PVOID *a3)
{
  _QWORD *v3; // rbp
  HANDLE *v4; // rsi
  int UncHardeningDefaultsToList; // ebx

  v3 = *a2;
  v4 = a2 + 4;
  UncHardeningDefaultsToList = MupiOpenUncHardeningRegistryKey(a2 + 4);
  if ( UncHardeningDefaultsToList < 0
    || (v3[2] = v3 + 1,
        v3[1] = v3 + 1,
        UncHardeningDefaultsToList = MupiLoadUncHardeningDefaultsToList(v3 + 1),
        UncHardeningDefaultsToList < 0)
    || (UncHardeningDefaultsToList = MupiLoadUncHardeningConfigurationToList(*v4, (__int64)(v3 + 1)),
        UncHardeningDefaultsToList < 0)
    || (UncHardeningDefaultsToList = MupiRegisterUncHardeningConfigurationRegistryChangeNotification(a2),
        UncHardeningDefaultsToList < 0) )
  {
    MupiFreeUncHardeningConfigurationEntryList(v3 + 1);
    if ( *v4 )
    {
      ZwClose(*v4);
      *v4 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_eb42bca7873834c81d179869f75e418e_Traceguids,
        (unsigned int)UncHardeningDefaultsToList);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_eb42bca7873834c81d179869f75e418e_Traceguids);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x140014b70  push    rbx
0x140014b72  push    rbp
0x140014b73  push    rsi
0x140014b74  push    rdi
0x140014b75  push    r14
0x140014b77  sub     rsp, 20h
0x140014b7b  mov     rbp, [rdx]
0x140014b7e  lea     rsi, [rdx+20h]
0x140014b82  mov     rcx, rsi
0x140014b85  mov     r14, rdx
0x140014b88  call    MupiOpenUncHardeningRegistryKey
0x140014b8d  mov     ebx, eax
0x140014b8f  test    eax, eax
0x140014b91  js      short loc_140014C03
0x140014b93  lea     rdi, [rbp+8]
0x140014b97  mov     rcx, rdi
0x140014b9a  mov     [rdi+8], rdi
0x140014b9e  mov     [rdi], rdi
0x140014ba1  call    MupiLoadUncHardeningDefaultsToList
0x140014ba6  mov     ebx, eax
0x140014ba8  test    eax, eax
0x140014baa  js      short loc_140014C03
0x140014bac  mov     rcx, [rsi]; KeyHandle
0x140014baf  mov     rdx, rdi
0x140014bb2  call    MupiLoadUncHardeningConfigurationToList
0x140014bb7  mov     ebx, eax
0x140014bb9  test    eax, eax
0x140014bbb  js      short loc_140014C03
0x140014bbd  mov     rcx, r14
0x140014bc0  call    MupiRegisterUncHardeningConfigurationRegistryChangeNotification
0x140014bc5  mov     ebx, eax
0x140014bc7  test    eax, eax
0x140014bc9  js      short loc_140014C03
0x140014bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140014bd2  lea     rax, WPP_GLOBAL_Control
0x140014bd9  cmp     rcx, rax
0x140014bdc  jz      short loc_140014BFC
0x140014bde  test    dword ptr [rcx+2Ch], 2000000h
0x140014be5  jz      short loc_140014BFC
0x140014be7  mov     rcx, [rcx+18h]
0x140014beb  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014bf2  mov     edx, 15h
0x140014bf7  call    WPP_SF_
0x140014bfc  mov     eax, 1
0x140014c01  jmp     short loc_140014C5D
0x140014c03  lea     rcx, [rbp+8]
0x140014c07  call    MupiFreeUncHardeningConfigurationEntryList
0x140014c0c  mov     rcx, [rsi]; Handle
0x140014c0f  test    rcx, rcx
0x140014c12  jz      short loc_140014C27
0x140014c14  call    cs:__imp_ZwClose
0x140014c1b  nop     dword ptr [rax+rax+00h]
0x140014c20  mov     qword ptr [rsi], 0
0x140014c27  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c2e  lea     rax, WPP_GLOBAL_Control
0x140014c35  cmp     rcx, rax
0x140014c38  jz      short loc_140014C5B
0x140014c3a  test    dword ptr [rcx+2Ch], 1000000h
0x140014c41  jz      short loc_140014C5B
0x140014c43  mov     rcx, [rcx+18h]
0x140014c47  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014c4e  mov     edx, 16h
0x140014c53  mov     r9d, ebx
0x140014c56  call    WPP_SF_d
0x140014c5b  xor     eax, eax
0x140014c5d  add     rsp, 20h
0x140014c61  pop     r14
0x140014c63  pop     rdi
0x140014c64  pop     rsi
0x140014c65  pop     rbp
0x140014c66  pop     rbx
0x140014c67  retn
```
