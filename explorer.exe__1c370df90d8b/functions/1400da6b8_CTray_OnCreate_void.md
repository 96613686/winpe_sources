# CTray::_OnCreate(void)

- ea: `0x1400da6b8`
- end: `0x1400da816`
- name: `?_OnCreate@CTray@@IEAA_JXZ`
- size: `350`
- prototype: `__int64 __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14001d860`

## callees

- `0x140015168`
- `0x140023a40`
- `0x140084610`
- `0x1400b53fc`
- `0x1400da6b8`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1400da78b`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1400da78b`
- `ntdll!RtlInitUnicodeString` at `0x1400da779`
- `ntdll!RtlInitUnicodeString` at `0x1400da779`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400da747`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400da75d`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400da747`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400da75d`
- `USER32!__imp_SetWindowMessageCapability` at `0x1400da7a3`
- `USER32!__imp_SetWindowMessageCapability` at `0x1400da7a3`
- `SndVolSSO!__imp_?AudioHIDInitialize@@YAHPEAUHWND__@@@Z` at `0x1400da720`
- `SndVolSSO!__imp_?AudioHIDInitialize@@YAHPEAUHWND__@@@Z` at `0x1400da720`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RegisterWindowMessageW` at `0x1400da7b0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RegisterWindowMessageW` at `0x1400da7b0`

## pseudocode

```c
__int64 __fastcall CTray::_OnCreate(CTray *this)
{
  HWND v1; // rax
  __int64 v3; // rdi
  UINT v4; // eax
  bool v5; // zf
  HDSA v6; // rax
  _BYTE pvParam[20]; // [rsp+20h] [rbp-29h] BYREF
  _BYTE v9[48]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v10[48]; // [rsp+68h] [rbp+1Fh] BYREF

  v1 = (HWND)*((_QWORD *)this + 1);
  *((_QWORD *)this + 124) = v1;
  *((_DWORD *)this + 122) = 0;
  v_hwndTray = v1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl) )
    CTray::UpdateTrayAndDesktopCloaking(this);
  CTray::_RecordMonitorInfo(this);
  *((_DWORD *)this + 58) = AudioHIDInitialize(*((HWND *)this + 1));
  *(_DWORD *)pvParam = 20;
  *(_OWORD *)&pvParam[4] = 0;
  SystemParametersInfoW(0x2Bu, 0x14u, pvParam, 0);
  *(_DWORD *)&pvParam[16] |= 8u;
  SystemParametersInfoW(0x2Cu, 0x14u, pvParam, 0);
  v3 = *((_QWORD *)this + 1);
  *(_OWORD *)pvParam = 0;
  RtlInitUnicodeString((PUNICODE_STRING)pvParam, L"isolatedWin32-sysTrayIcon");
  if ( (int)RtlDeriveCapabilitySidsFromName(pvParam, v10, v9) >= 0 )
    SetWindowMessageCapability(v3, 74, v9);
  v4 = RegisterWindowMessageW(L"Logoff User");
  v5 = *((_QWORD *)this + 33) == 0;
  *((_DWORD *)this + 114) = v4;
  if ( !v5 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 48LL))(*((_QWORD *)this + 133));
  v6 = DSA_Create(24, 0);
  *((_QWORD *)this + 33) = v6;
  if ( v6 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 48LL))(*((_QWORD *)this + 133));
  else
    return -1;
}

```

## disassembly

```asm
0x1400da6b8  mov     [rsp-8+arg_8], rbx
0x1400da6bd  mov     [rsp-8+arg_10], rdi
0x1400da6c2  push    rbp
0x1400da6c3  lea     rbp, [rsp-57h]
0x1400da6c8  sub     rsp, 0A0h
0x1400da6cf  mov     rax, cs:__security_cookie
0x1400da6d6  xor     rax, rsp
0x1400da6d9  mov     [rbp+57h+var_8], rax
0x1400da6dd  mov     rax, [rcx+8]
0x1400da6e1  mov     rbx, rcx
0x1400da6e4  mov     [rcx+3E0h], rax
0x1400da6eb  mov     dword ptr [rcx+1E8h], 0
0x1400da6f5  mov     cs:v_hwndTray, rax
0x1400da6fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x1400da703  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x1400da708  test    al, al
0x1400da70a  jz      short loc_1400DA714
0x1400da70c  mov     rcx, rbx; this
0x1400da70f  call    ?UpdateTrayAndDesktopCloaking@CTray@@QEAAXXZ; CTray::UpdateTrayAndDesktopCloaking(void)
0x1400da714  mov     rcx, rbx; this
0x1400da717  call    ?_RecordMonitorInfo@CTray@@AEAAXXZ; CTray::_RecordMonitorInfo(void)
0x1400da71c  mov     rcx, [rbx+8]
0x1400da720  call    cs:__imp_?AudioHIDInitialize@@YAHPEAUHWND__@@@Z; AudioHIDInitialize(HWND__ *)
0x1400da726  mov     edi, 14h
0x1400da72b  lea     r8, [rbp+57h+pvParam]; pvParam
0x1400da72f  xorps   xmm0, xmm0
0x1400da732  mov     [rbx+0E8h], eax
0x1400da738  xor     r9d, r9d; fWinIni
0x1400da73b  mov     dword ptr [rbp+57h+pvParam], edi
0x1400da73e  mov     edx, edi; uiParam
0x1400da740  lea     ecx, [rdi+17h]; uiAction
0x1400da743  movups  [rbp+57h+pvParam+4], xmm0
0x1400da747  call    cs:__imp_SystemParametersInfoW
0x1400da74d  or      [rbp+57h+var_70], 8
0x1400da751  lea     r8, [rbp+57h+pvParam]; pvParam
0x1400da755  xor     r9d, r9d; fWinIni
0x1400da758  lea     ecx, [rdi+18h]; uiAction
0x1400da75b  mov     edx, edi; uiParam
0x1400da75d  call    cs:__imp_SystemParametersInfoW
0x1400da763  mov     rdi, [rbx+8]
0x1400da767  lea     rdx, aIsolatedwin32S; "isolatedWin32-sysTrayIcon"
0x1400da76e  xorps   xmm0, xmm0
0x1400da771  lea     rcx, [rbp+57h+pvParam]; DestinationString
0x1400da775  movups  [rbp+57h+pvParam], xmm0
0x1400da779  call    cs:__imp_RtlInitUnicodeString
0x1400da77f  lea     r8, [rbp+57h+var_68]
0x1400da783  lea     rdx, [rbp+57h+var_38]
0x1400da787  lea     rcx, [rbp+57h+pvParam]
0x1400da78b  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1400da791  test    eax, eax
0x1400da793  js      short loc_1400DA7A9
0x1400da795  xor     r9d, r9d
0x1400da798  lea     r8, [rbp+57h+var_68]
0x1400da79c  mov     rcx, rdi
0x1400da79f  lea     edx, [r9+4Ah]
0x1400da7a3  call    cs:__imp_SetWindowMessageCapability
0x1400da7a9  lea     rcx, aLogoffUser; "Logoff User"
0x1400da7b0  call    cs:__imp_RegisterWindowMessageW
0x1400da7b6  cmp     qword ptr [rbx+108h], 0
0x1400da7be  mov     [rbx+1C8h], eax
0x1400da7c4  jnz     short loc_1400DA7E2
0x1400da7c6  xor     edx, edx; cItemGrow
0x1400da7c8  lea     ecx, [rdx+18h]; cbItem
0x1400da7cb  call    DSA_Create
0x1400da7d0  mov     [rbx+108h], rax
0x1400da7d7  test    rax, rax
0x1400da7da  jnz     short loc_1400DA7E2
0x1400da7dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400da7e0  jmp     short loc_1400DA7F5
0x1400da7e2  mov     rcx, [rbx+428h]
0x1400da7e9  mov     rax, [rcx]
0x1400da7ec  mov     rax, [rax+30h]
0x1400da7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400da7f5  mov     rcx, [rbp+57h+var_8]
0x1400da7f9  xor     rcx, rsp; StackCookie
0x1400da7fc  call    __security_check_cookie
0x1400da801  lea     r11, [rsp+0A0h+var_s0]
0x1400da809  mov     rbx, [r11+18h]
0x1400da80d  mov     rdi, [r11+20h]
0x1400da811  mov     rsp, r11
0x1400da814  pop     rbp
0x1400da815  retn
```
