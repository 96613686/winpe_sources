# CSettingsMonitor::_UpdateMeteredCostState(void)

- ea: `0x1800991e0`
- end: `0x1800993cc`
- name: `?_UpdateMeteredCostState@CSettingsMonitor@@AEAA_NXZ`
- size: `492`
- prototype: `bool __fastcall(CSettingsMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009865c`
- `0x18009a090`

## callees

- `0x180008fb8`
- `0x1800991e0`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800993a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800993a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180099310`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180099310`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009922b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009922b`

## string_xrefs

- `0x18009938d`: `CSettingsMonitor::_UpdateMeteredCostState`
- `0x180099236`: `Failed to CoCreate NLM`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CSettingsMonitor::_UpdateMeteredCostState(RTL_SRWLOCK *this)
{
  bool v2; // bl
  unsigned int v3; // eax
  int v4; // edi
  int v5; // eax
  LPVOID v6; // rcx
  int v7; // esi
  int Ptr; // ecx
  const char *v10; // [rsp+28h] [rbp-40h]
  int v11; // [rsp+30h] [rbp-38h] BYREF
  LPVOID v12; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = 0;
  v12 = 0;
  v3 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, &v12);
  v4 = 0;
  if ( wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0x10F,
         (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\DeviceStateNotificationManager.cpp",
         (const char *)v3,
         (int)"Failed to CoCreate NLM",
         v10) >= 0 )
  {
    v11 = 0;
    v5 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, &v11, 0);
    if ( v5 < 0 )
    {
      if ( v5 != -2147023674 )
        LogResult(
          3u,
          "CDeviceStateNotificationManager::IsCurrentNetworkMetered",
          0x11Bu,
          v5,
          "INetworkCostManager->GetCost failed");
    }
    else
    {
      v4 = v11;
      v2 = v11 && (v11 & 1) == 0;
    }
  }
  LogMessage(5u, "CDeviceStateNotificationManager::IsCurrentNetworkMetered", 0x11Eu, "fMetered = %u", v2);
  v6 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  AcquireSRWLockExclusive(this + 21);
  LOBYTE(v7) = 0;
  HIDWORD(this[27].Ptr) = v4;
  Ptr = (int)this[27].Ptr;
  if ( Ptr )
  {
    if ( Ptr == 1 )
    {
      v7 = !v2;
      Ptr = 2 * v7;
      LODWORD(this[27].Ptr) = 2 * v7;
    }
    else if ( Ptr == 2 )
    {
      Ptr = 2;
      if ( v2 )
      {
        LODWORD(this[27].Ptr) = 0;
        LOBYTE(v7) = 1;
        Ptr = 0;
      }
    }
  }
  else
  {
    Ptr = 0;
    if ( !v2 )
    {
      LODWORD(this[27].Ptr) = 1;
      Ptr = 1;
    }
  }
  LogMessage(
    5u,
    "CSettingsMonitor::_UpdateMeteredCostState",
    0x1F8u,
    "costState = %d, fCostChange = %u",
    Ptr,
    (unsigned __int8)v7);
  ReleaseSRWLockExclusive(this + 21);
  return v7;
}

```

## disassembly

```asm
0x1800991e0  mov     r11, rsp
0x1800991e3  mov     [r11+10h], rbx
0x1800991e7  mov     [r11+18h], rbp
0x1800991eb  push    rsi
0x1800991ec  push    rdi
0x1800991ed  push    r14
0x1800991ef  sub     rsp, 50h
0x1800991f3  mov     rax, cs:__security_cookie
0x1800991fa  xor     rax, rsp
0x1800991fd  mov     [rsp+68h+var_28], rax
0x180099202  mov     rbp, rcx
0x180099205  xor     bl, bl
0x180099207  mov     qword ptr [r11-30h], 0
0x18009920f  lea     rax, [r11-30h]
0x180099213  mov     [r11-48h], rax
0x180099217  lea     r9, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b; riid
0x18009921e  xor     edx, edx; pUnkOuter
0x180099220  lea     r8d, [rdx+1]; dwClsContext
0x180099224  lea     rcx, CLSID_NetworkListManager; rclsid
0x18009922b  call    cs:__imp_CoCreateInstance
0x180099231  mov     rcx, [rsp+68h]; this
0x180099236  lea     rdx, aFailedToCocrea; "Failed to CoCreate NLM"
0x18009923d  mov     [rsp+68h+var_48], rdx; int
0x180099242  mov     r9d, eax; char *
0x180099245  lea     r8, aCW1SSrcDeliver_80; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009924c  mov     edx, 10Fh; void *
0x180099251  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180099256  xor     edi, edi
0x180099258  test    eax, eax
0x18009925a  js      short loc_1800992C0
0x18009925c  mov     [rsp+68h+var_38], edi
0x180099260  mov     rcx, [rsp+68h+var_30]
0x180099265  mov     rax, [rcx]
0x180099268  xor     r8d, r8d
0x18009926b  lea     rdx, [rsp+68h+var_38]
0x180099270  mov     rax, [rax+18h]
0x180099274  call    _guard_dispatch_icall
0x180099279  test    eax, eax
0x18009927b  js      short loc_180099293
0x18009927d  mov     edi, [rsp+68h+var_38]
0x180099281  test    edi, edi
0x180099283  jz      short loc_18009928F
0x180099285  test    dil, 1
0x180099289  jnz     short loc_18009928F
0x18009928b  mov     bl, 1
0x18009928d  jmp     short loc_1800992C0
0x18009928f  xor     bl, bl
0x180099291  jmp     short loc_1800992C0
0x180099293  cmp     eax, 800704C6h
0x180099298  jz      short loc_1800992C0
0x18009929a  lea     rcx, aInetworkcostma; "INetworkCostManager->GetCost failed"
0x1800992a1  mov     [rsp+68h+var_48], rcx; char *
0x1800992a6  mov     r9d, eax; int
0x1800992a9  mov     r8d, 11Bh; unsigned int
0x1800992af  lea     rdx, aCdevicestateno_14; "CDeviceStateNotificationManager::IsCurr"...
0x1800992b6  mov     ecx, 3; unsigned __int8
0x1800992bb  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800992c0  movzx   eax, bl
0x1800992c3  mov     dword ptr [rsp+68h+var_48], eax
0x1800992c7  lea     r9, aFmeteredU; "fMetered = %u"
0x1800992ce  mov     r8d, 11Eh; unsigned int
0x1800992d4  lea     rdx, aCdevicestateno_14; "CDeviceStateNotificationManager::IsCurr"...
0x1800992db  mov     ecx, 5; unsigned __int8
0x1800992e0  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800992e5  nop
0x1800992e6  mov     rcx, [rsp+68h+var_30]
0x1800992eb  test    rcx, rcx
0x1800992ee  jz      short loc_180099306
0x1800992f0  mov     [rsp+68h+var_30], 0
0x1800992f9  mov     rax, [rcx]
0x1800992fc  mov     rax, [rax+10h]
0x180099300  call    _guard_dispatch_icall
0x180099305  nop
0x180099306  lea     r14, [rbp+0A8h]
0x18009930d  mov     rcx, r14; SRWLock
0x180099310  call    cs:__imp_AcquireSRWLockExclusive
0x180099316  xor     sil, sil
0x180099319  mov     [rbp+0DCh], edi
0x18009931f  mov     ecx, [rbp+0D8h]
0x180099325  mov     edx, ecx
0x180099327  test    ecx, ecx
0x180099329  jz      short loc_18009935F
0x18009932b  sub     edx, 1
0x18009932e  jz      short loc_18009934D
0x180099330  cmp     edx, 1
0x180099333  jnz     short loc_180099374
0x180099335  lea     ecx, [rdx+1]
0x180099338  test    bl, bl
0x18009933a  jz      short loc_180099374
0x18009933c  mov     dword ptr [rbp+0D8h], 0
0x180099346  mov     sil, dl
0x180099349  xor     ecx, ecx
0x18009934b  jmp     short loc_180099374
0x18009934d  xor     bl, 1
0x180099350  movzx   esi, bl
0x180099353  mov     ecx, esi
0x180099355  add     ecx, ecx
0x180099357  mov     [rbp+0D8h], ecx
0x18009935d  jmp     short loc_180099374
0x18009935f  xor     ecx, ecx
0x180099361  test    bl, bl
0x180099363  jnz     short loc_180099374
0x180099365  mov     dword ptr [rbp+0D8h], 1
0x18009936f  mov     ecx, 1
0x180099374  movzx   edx, sil
0x180099378  mov     dword ptr [rsp+68h+var_40], edx
0x18009937c  mov     dword ptr [rsp+68h+var_48], ecx
0x180099380  lea     r9, aCoststateDFcos; "costState = %d, fCostChange = %u"
0x180099387  mov     r8d, 1F8h; unsigned int
0x18009938d  lea     rdx, aCsettingsmonit_7; "CSettingsMonitor::_UpdateMeteredCostSta"...
0x180099394  mov     ecx, 5; unsigned __int8
0x180099399  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18009939e  mov     rcx, r14; SRWLock
0x1800993a1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800993a7  mov     al, sil
0x1800993aa  mov     rcx, [rsp+68h+var_28]
0x1800993af  xor     rcx, rsp; StackCookie
0x1800993b2  call    __security_check_cookie
0x1800993b7  lea     r11, [rsp+68h+var_18]
0x1800993bc  mov     rbx, [r11+28h]
0x1800993c0  mov     rbp, [r11+30h]
0x1800993c4  mov     rsp, r11
0x1800993c7  pop     r14
0x1800993c9  pop     rdi
0x1800993ca  pop     rsi
0x1800993cb  retn
```
