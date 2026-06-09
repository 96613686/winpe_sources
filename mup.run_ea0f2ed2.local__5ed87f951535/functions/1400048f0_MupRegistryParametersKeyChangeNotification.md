# MupRegistryParametersKeyChangeNotification

- ea: `0x1400048f0`
- end: `0x140004acc`
- name: `MupRegistryParametersKeyChangeNotification`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x1400048f0`
- `0x140016808`
- `0x140016844`
- `0x1400169e4`
- `0x140016b44`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140004951`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004951`
- `ntoskrnl!ZwClose` at `0x1400049d6`
- `ntoskrnl!ZwClose` at `0x140004a48`
- `ntoskrnl!ZwClose` at `0x1400049d6`
- `ntoskrnl!ZwClose` at `0x140004a48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004aa2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004aa2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004963`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004963`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004a96`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004a96`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000490c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000490c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140004ab2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140004ab2`
- `ntoskrnl!ZwQueryKey` at `0x14000498a`
- `ntoskrnl!ZwQueryKey` at `0x14000498a`

## pseudocode

```c
void __fastcall MupRegistryParametersKeyChangeNotification(struct _EX_RUNDOWN_REF *a1)
{
  HANDLE *v2; // rbx
  NTSTATUS v3; // eax
  int v4; // eax
  int v5; // esi
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  ResultLength = 0;
  if ( ExAcquireRundownProtection(a1 + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids);
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&a1[2], 0);
    v2 = (HANDLE *)&a1[3];
    v3 = ZwQueryKey(a1[3].Ptr, KeyCachedInformation, 0, 0, &ResultLength);
    if ( v3 == -1073741444 || v3 == -1073740763 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids);
      }
      if ( *v2 )
      {
        ZwClose(*v2);
        *v2 = 0;
      }
      v4 = MupiOpenParametersKeyFromRegistry((void **)&a1[3]);
      if ( v4 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_511a9a8026a53b8720c76e64765e5363_Traceguids,
          (unsigned int)v4);
      }
    }
    if ( *v2 )
    {
      MupEnableMailslots = MupiReadEnableMailslotsFromRegistry(*v2, 1);
      v5 = MupiRegisterParametersKeyRegistryChangeNotification(a1);
      if ( v5 < 0 )
      {
        ZwClose(*v2);
        *v2 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_511a9a8026a53b8720c76e64765e5363_Traceguids,
            (unsigned int)v5);
        }
      }
    }
    MupiArmParametersKeyRefreshTimer(a1);
    ExReleasePushLockExclusiveEx(&a1[2], 0);
    KeLeaveCriticalRegion();
    ExReleaseRundownProtection(a1 + 1);
  }
}

```

## disassembly

```asm
0x1400048f0  push    rbx
0x1400048f2  push    rbp
0x1400048f3  push    rsi
0x1400048f4  push    rdi
0x1400048f5  push    r12
0x1400048f7  push    r14
0x1400048f9  sub     rsp, 38h
0x1400048fd  mov     rdi, rcx
0x140004900  mov     [rsp+68h+arg_0], 0
0x140004908  add     rcx, 8; RunRef
0x14000490c  call    cs:__imp_ExAcquireRundownProtection
0x140004913  nop     dword ptr [rax+rax+00h]
0x140004918  test    al, al
0x14000491a  jz      loc_140004ABE
0x140004920  mov     rcx, cs:WPP_GLOBAL_Control
0x140004927  lea     r12, WPP_GLOBAL_Control
0x14000492e  cmp     rcx, r12
0x140004931  jz      short loc_140004951
0x140004933  test    dword ptr [rcx+2Ch], 4000000h
0x14000493a  jz      short loc_140004951
0x14000493c  mov     rcx, [rcx+18h]
0x140004940  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140004947  mov     edx, 13h
0x14000494c  call    WPP_SF_
0x140004951  call    cs:__imp_KeEnterCriticalRegion
0x140004958  nop     dword ptr [rax+rax+00h]
0x14000495d  xor     edx, edx
0x14000495f  lea     rcx, [rdi+10h]
0x140004963  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000496a  nop     dword ptr [rax+rax+00h]
0x14000496f  xor     r9d, r9d; Length
0x140004972  lea     rax, [rsp+68h+arg_0]
0x140004977  lea     rbx, [rdi+18h]
0x14000497b  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140004980  mov     rcx, [rbx]; KeyHandle
0x140004983  xor     r8d, r8d; KeyInformation
0x140004986  lea     edx, [r9+4]; KeyInformationClass
0x14000498a  call    cs:__imp_ZwQueryKey
0x140004991  nop     dword ptr [rax+rax+00h]
0x140004996  cmp     eax, 0C000017Ch
0x14000499b  jz      short loc_1400049A4
0x14000499d  cmp     eax, 0C0000425h
0x1400049a2  jnz     short loc_140004A22
0x1400049a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049ab  cmp     rcx, r12
0x1400049ae  jz      short loc_1400049CE
0x1400049b0  test    dword ptr [rcx+2Ch], 2000000h
0x1400049b7  jz      short loc_1400049CE
0x1400049b9  mov     rcx, [rcx+18h]
0x1400049bd  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x1400049c4  mov     edx, 14h
0x1400049c9  call    WPP_SF_
0x1400049ce  mov     rcx, [rbx]; Handle
0x1400049d1  test    rcx, rcx
0x1400049d4  jz      short loc_1400049E9
0x1400049d6  call    cs:__imp_ZwClose
0x1400049dd  nop     dword ptr [rax+rax+00h]
0x1400049e2  mov     qword ptr [rbx], 0
0x1400049e9  mov     rcx, rbx
0x1400049ec  call    MupiOpenParametersKeyFromRegistry
0x1400049f1  test    eax, eax
0x1400049f3  jns     short loc_140004A22
0x1400049f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049fc  cmp     rcx, r12
0x1400049ff  jz      short loc_140004A22
0x140004a01  test    dword ptr [rcx+2Ch], 1000000h
0x140004a08  jz      short loc_140004A22
0x140004a0a  mov     rcx, [rcx+18h]
0x140004a0e  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140004a15  mov     edx, 15h
0x140004a1a  mov     r9d, eax
0x140004a1d  call    WPP_SF_d
0x140004a22  mov     rcx, [rbx]; KeyHandle
0x140004a25  test    rcx, rcx
0x140004a28  jz      short loc_140004A88
0x140004a2a  mov     dl, 1
0x140004a2c  call    MupiReadEnableMailslotsFromRegistry
0x140004a31  mov     rcx, rdi
0x140004a34  mov     cs:MupEnableMailslots, al
0x140004a3a  call    MupiRegisterParametersKeyRegistryChangeNotification
0x140004a3f  mov     esi, eax
0x140004a41  test    eax, eax
0x140004a43  jns     short loc_140004A88
0x140004a45  mov     rcx, [rbx]; Handle
0x140004a48  call    cs:__imp_ZwClose
0x140004a4f  nop     dword ptr [rax+rax+00h]
0x140004a54  mov     qword ptr [rbx], 0
0x140004a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a62  cmp     rcx, r12
0x140004a65  jz      short loc_140004A88
0x140004a67  test    dword ptr [rcx+2Ch], 1000000h
0x140004a6e  jz      short loc_140004A88
0x140004a70  mov     rcx, [rcx+18h]
0x140004a74  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140004a7b  mov     edx, 16h
0x140004a80  mov     r9d, esi
0x140004a83  call    WPP_SF_d
0x140004a88  mov     rcx, rdi
0x140004a8b  call    MupiArmParametersKeyRefreshTimer
0x140004a90  xor     edx, edx
0x140004a92  lea     rcx, [rdi+10h]
0x140004a96  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140004a9d  nop     dword ptr [rax+rax+00h]
0x140004aa2  call    cs:__imp_KeLeaveCriticalRegion
0x140004aa9  nop     dword ptr [rax+rax+00h]
0x140004aae  lea     rcx, [rdi+8]; RunRef
0x140004ab2  call    cs:__imp_ExReleaseRundownProtection
0x140004ab9  nop     dword ptr [rax+rax+00h]
0x140004abe  add     rsp, 38h
0x140004ac2  pop     r14
0x140004ac4  pop     r12
0x140004ac6  pop     rdi
0x140004ac7  pop     rsi
0x140004ac8  pop     rbp
0x140004ac9  pop     rbx
0x140004aca  retn
```
