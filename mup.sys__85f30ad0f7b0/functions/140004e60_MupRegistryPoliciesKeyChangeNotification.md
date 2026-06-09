# MupRegistryPoliciesKeyChangeNotification

- ea: `0x140004e60`
- end: `0x14000503c`
- name: `MupRegistryPoliciesKeyChangeNotification`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140004e60`
- `0x140016858`
- `0x140016c40`
- `0x140016dc4`
- `0x140016f2c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140004ec1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004ec1`
- `ntoskrnl!ZwClose` at `0x140004f46`
- `ntoskrnl!ZwClose` at `0x140004fb8`
- `ntoskrnl!ZwClose` at `0x140004f46`
- `ntoskrnl!ZwClose` at `0x140004fb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005012`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005012`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004ed3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004ed3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140005006`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140005006`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140004e7c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140004e7c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005022`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005022`
- `ntoskrnl!ZwQueryKey` at `0x140004efa`
- `ntoskrnl!ZwQueryKey` at `0x140004efa`

## pseudocode

```c
void __fastcall MupRegistryPoliciesKeyChangeNotification(struct _EX_RUNDOWN_REF *a1)
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_4108bb1397623747c94676978a28aeb5_Traceguids);
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
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4108bb1397623747c94676978a28aeb5_Traceguids);
      }
      if ( *v2 )
      {
        ZwClose(*v2);
        *v2 = 0;
      }
      v4 = MupiOpenPoliciesKeyFromRegistry((void **)&a1[3]);
      if ( v4 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_4108bb1397623747c94676978a28aeb5_Traceguids,
          (unsigned int)v4);
      }
    }
    if ( *v2 )
    {
      LOBYTE(MupEnableMailslotsByPolicy) = MupiReadEnableMailslotsFromPoliciesRegistry(*v2, 1);
      v5 = MupiRegisterPoliciesKeyRegistryChangeNotification(a1);
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
            WPP_4108bb1397623747c94676978a28aeb5_Traceguids,
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
0x140004e60  push    rbx
0x140004e62  push    rbp
0x140004e63  push    rsi
0x140004e64  push    rdi
0x140004e65  push    r12
0x140004e67  push    r14
0x140004e69  sub     rsp, 38h
0x140004e6d  mov     rdi, rcx
0x140004e70  mov     [rsp+68h+arg_0], 0
0x140004e78  add     rcx, 8; RunRef
0x140004e7c  call    cs:__imp_ExAcquireRundownProtection
0x140004e83  nop     dword ptr [rax+rax+00h]
0x140004e88  test    al, al
0x140004e8a  jz      loc_14000502E
0x140004e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e97  lea     r12, WPP_GLOBAL_Control
0x140004e9e  cmp     rcx, r12
0x140004ea1  jz      short loc_140004EC1
0x140004ea3  test    dword ptr [rcx+2Ch], 4000000h
0x140004eaa  jz      short loc_140004EC1
0x140004eac  mov     rcx, [rcx+18h]
0x140004eb0  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004eb7  mov     edx, 13h
0x140004ebc  call    WPP_SF_
0x140004ec1  call    cs:__imp_KeEnterCriticalRegion
0x140004ec8  nop     dword ptr [rax+rax+00h]
0x140004ecd  xor     edx, edx
0x140004ecf  lea     rcx, [rdi+10h]
0x140004ed3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140004eda  nop     dword ptr [rax+rax+00h]
0x140004edf  xor     r9d, r9d; Length
0x140004ee2  lea     rax, [rsp+68h+arg_0]
0x140004ee7  lea     rbx, [rdi+18h]
0x140004eeb  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140004ef0  mov     rcx, [rbx]; KeyHandle
0x140004ef3  xor     r8d, r8d; KeyInformation
0x140004ef6  lea     edx, [r9+4]; KeyInformationClass
0x140004efa  call    cs:__imp_ZwQueryKey
0x140004f01  nop     dword ptr [rax+rax+00h]
0x140004f06  cmp     eax, 0C000017Ch
0x140004f0b  jz      short loc_140004F14
0x140004f0d  cmp     eax, 0C0000425h
0x140004f12  jnz     short loc_140004F92
0x140004f14  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f1b  cmp     rcx, r12
0x140004f1e  jz      short loc_140004F3E
0x140004f20  test    dword ptr [rcx+2Ch], 2000000h
0x140004f27  jz      short loc_140004F3E
0x140004f29  mov     rcx, [rcx+18h]
0x140004f2d  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004f34  mov     edx, 14h
0x140004f39  call    WPP_SF_
0x140004f3e  mov     rcx, [rbx]; Handle
0x140004f41  test    rcx, rcx
0x140004f44  jz      short loc_140004F59
0x140004f46  call    cs:__imp_ZwClose
0x140004f4d  nop     dword ptr [rax+rax+00h]
0x140004f52  mov     qword ptr [rbx], 0
0x140004f59  mov     rcx, rbx
0x140004f5c  call    MupiOpenPoliciesKeyFromRegistry
0x140004f61  test    eax, eax
0x140004f63  jns     short loc_140004F92
0x140004f65  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f6c  cmp     rcx, r12
0x140004f6f  jz      short loc_140004F92
0x140004f71  test    dword ptr [rcx+2Ch], 1000000h
0x140004f78  jz      short loc_140004F92
0x140004f7a  mov     rcx, [rcx+18h]
0x140004f7e  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004f85  mov     edx, 15h
0x140004f8a  mov     r9d, eax
0x140004f8d  call    WPP_SF_d
0x140004f92  mov     rcx, [rbx]; KeyHandle
0x140004f95  test    rcx, rcx
0x140004f98  jz      short loc_140004FF8
0x140004f9a  mov     dl, 1
0x140004f9c  call    MupiReadEnableMailslotsFromPoliciesRegistry
0x140004fa1  mov     rcx, rdi
0x140004fa4  mov     byte ptr cs:MupEnableMailslotsByPolicy, al
0x140004faa  call    MupiRegisterPoliciesKeyRegistryChangeNotification
0x140004faf  mov     esi, eax
0x140004fb1  test    eax, eax
0x140004fb3  jns     short loc_140004FF8
0x140004fb5  mov     rcx, [rbx]; Handle
0x140004fb8  call    cs:__imp_ZwClose
0x140004fbf  nop     dword ptr [rax+rax+00h]
0x140004fc4  mov     qword ptr [rbx], 0
0x140004fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004fd2  cmp     rcx, r12
0x140004fd5  jz      short loc_140004FF8
0x140004fd7  test    dword ptr [rcx+2Ch], 1000000h
0x140004fde  jz      short loc_140004FF8
0x140004fe0  mov     rcx, [rcx+18h]
0x140004fe4  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004feb  mov     edx, 16h
0x140004ff0  mov     r9d, esi
0x140004ff3  call    WPP_SF_d
0x140004ff8  mov     rcx, rdi
0x140004ffb  call    MupiArmParametersKeyRefreshTimer
0x140005000  xor     edx, edx
0x140005002  lea     rcx, [rdi+10h]
0x140005006  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000500d  nop     dword ptr [rax+rax+00h]
0x140005012  call    cs:__imp_KeLeaveCriticalRegion
0x140005019  nop     dword ptr [rax+rax+00h]
0x14000501e  lea     rcx, [rdi+8]; RunRef
0x140005022  call    cs:__imp_ExReleaseRundownProtection
0x140005029  nop     dword ptr [rax+rax+00h]
0x14000502e  add     rsp, 38h
0x140005032  pop     r14
0x140005034  pop     r12
0x140005036  pop     rdi
0x140005037  pop     rsi
0x140005038  pop     rbp
0x140005039  pop     rbx
0x14000503a  retn
```
