# MupAttemptToLoadRegistryConfigurationRunOnce

- ea: `0x140014bc0`
- end: `0x140014cb9`
- name: `MupAttemptToLoadRegistryConfigurationRunOnce`
- size: `249`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140014bc0`
- `0x14001524c`
- `0x1400153d0`
- `0x1400158f4`
- `0x140015980`
- `0x14001f080`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140014c64`
- `ntoskrnl!ZwClose` at `0x140014c64`

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
0x140014bc0  push    rbx
0x140014bc2  push    rbp
0x140014bc3  push    rsi
0x140014bc4  push    rdi
0x140014bc5  push    r14
0x140014bc7  sub     rsp, 20h
0x140014bcb  mov     rbp, [rdx]
0x140014bce  lea     rsi, [rdx+20h]
0x140014bd2  mov     rcx, rsi
0x140014bd5  mov     r14, rdx
0x140014bd8  call    MupiOpenUncHardeningRegistryKey
0x140014bdd  mov     ebx, eax
0x140014bdf  test    eax, eax
0x140014be1  js      short loc_140014C53
0x140014be3  lea     rdi, [rbp+8]
0x140014be7  mov     rcx, rdi
0x140014bea  mov     [rdi+8], rdi
0x140014bee  mov     [rdi], rdi
0x140014bf1  call    MupiLoadUncHardeningDefaultsToList
0x140014bf6  mov     ebx, eax
0x140014bf8  test    eax, eax
0x140014bfa  js      short loc_140014C53
0x140014bfc  mov     rcx, [rsi]; KeyHandle
0x140014bff  mov     rdx, rdi
0x140014c02  call    MupiLoadUncHardeningConfigurationToList
0x140014c07  mov     ebx, eax
0x140014c09  test    eax, eax
0x140014c0b  js      short loc_140014C53
0x140014c0d  mov     rcx, r14
0x140014c10  call    MupiRegisterUncHardeningConfigurationRegistryChangeNotification
0x140014c15  mov     ebx, eax
0x140014c17  test    eax, eax
0x140014c19  js      short loc_140014C53
0x140014c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c22  lea     rax, WPP_GLOBAL_Control
0x140014c29  cmp     rcx, rax
0x140014c2c  jz      short loc_140014C4C
0x140014c2e  test    dword ptr [rcx+2Ch], 2000000h
0x140014c35  jz      short loc_140014C4C
0x140014c37  mov     rcx, [rcx+18h]
0x140014c3b  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014c42  mov     edx, 15h
0x140014c47  call    WPP_SF_
0x140014c4c  mov     eax, 1
0x140014c51  jmp     short loc_140014CAD
0x140014c53  lea     rcx, [rbp+8]
0x140014c57  call    MupiFreeUncHardeningConfigurationEntryList
0x140014c5c  mov     rcx, [rsi]; Handle
0x140014c5f  test    rcx, rcx
0x140014c62  jz      short loc_140014C77
0x140014c64  call    cs:__imp_ZwClose
0x140014c6b  nop     dword ptr [rax+rax+00h]
0x140014c70  mov     qword ptr [rsi], 0
0x140014c77  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c7e  lea     rax, WPP_GLOBAL_Control
0x140014c85  cmp     rcx, rax
0x140014c88  jz      short loc_140014CAB
0x140014c8a  test    dword ptr [rcx+2Ch], 1000000h
0x140014c91  jz      short loc_140014CAB
0x140014c93  mov     rcx, [rcx+18h]
0x140014c97  lea     r8, WPP_eb42bca7873834c81d179869f75e418e_Traceguids
0x140014c9e  mov     edx, 16h
0x140014ca3  mov     r9d, ebx
0x140014ca6  call    WPP_SF_d
0x140014cab  xor     eax, eax
0x140014cad  add     rsp, 20h
0x140014cb1  pop     r14
0x140014cb3  pop     rdi
0x140014cb4  pop     rsi
0x140014cb5  pop     rbp
0x140014cb6  pop     rbx
0x140014cb7  retn
```
