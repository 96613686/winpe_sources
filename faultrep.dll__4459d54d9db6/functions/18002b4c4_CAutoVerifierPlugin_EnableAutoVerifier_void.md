# CAutoVerifierPlugin::EnableAutoVerifier(void *)

- ea: `0x18002b4c4`
- end: `0x18002b9c3`
- name: `?EnableAutoVerifier@CAutoVerifierPlugin@@AEAAJPEAX@Z`
- size: `1279`
- prototype: `__int64 __fastcall(LPCWSTR *this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c3e0`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x18002b4c4`
- `0x18002b9cc`
- `0x18002c8c8`
- `0x18002ce14`
- `0x18002d57c`
- `0x180036ec4`
- `0x1800375ec`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b842`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b856`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b86a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b87e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b842`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b856`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b86a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b87e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b692`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b6e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b7cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b692`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b6e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b7cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b547`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b557`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b547`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b557`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9a3`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::EnableAutoVerifier(LPCWSTR *this, void *a2)
{
  int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  CAutoVerifierPlugin *v8; // rcx
  HKEY *phkResult; // rax
  HKEY *v10; // rax
  enum _ACCESS_MODE v11; // edx
  int v12; // eax
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  HKEY *v16; // rax
  enum _ACCESS_MODE v17; // edx
  int v18; // eax
  unsigned int i; // edi
  __int64 v20; // r12
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // eax
  CAutoVerifierPlugin *v26; // rcx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v28; // [rsp+58h] [rbp-8h] BYREF
  int v29; // [rsp+A8h] [rbp+48h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+50h] BYREF
  HKEY v31; // [rsp+B8h] [rbp+58h] BYREF

  v28 = 0;
  v31 = 0;
  hKey = 0;
  dwDisposition = 0;
  v29 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    if ( v31 )
      RegCloseKey(v31);
    return 2147942487LL;
  }
  v5 = CAutoVerifierPlugin::ValidateAutoverifier((CAutoVerifierPlugin *)this, &v29);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 54;
    goto LABEL_68;
  }
  if ( !v29 )
  {
    v5 = 1;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_69;
    v7 = 55;
    goto LABEL_68;
  }
  if ( !(unsigned int)CAutoVerifierPlugin::PromptForEnableAutoVerifier((CAutoVerifierPlugin *)this, a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    v5 = 1;
    goto LABEL_69;
  }
  v5 = CAutoVerifierPlugin::SetAutoverifierEnabledFlag(v8, 1u);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 57;
    goto LABEL_68;
  }
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options",
         0,
         0,
         0,
         0xF003Fu,
         0,
         phkResult,
         0)
    || !v28 )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 58;
LABEL_68:
    WPP_SF_(v6[2], v7, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    goto LABEL_69;
  }
  v10 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v31);
  if ( RegCreateKeyExW(v28, this[93], 0, 0, 1u, 0x60002u, 0, v10, &dwDisposition) || !v31 )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 59;
    goto LABEL_68;
  }
  v12 = WerPluginAdjustAppContainerAccessToKey(v31, v11, 0x80010000);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v12);
  }
  v13 = WerPluginWriteSettings((struct _AUTOVERIFIER_IPT_SETTINGS *)(this + 120), 0x15u, v31, 0);
  v5 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v15 = 61;
    goto LABEL_37;
  }
  v16 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(v31, L"Autoverifier", 0, 0, 1u, 0x60002u, 0, v16, &dwDisposition) || !hKey )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 62;
    goto LABEL_68;
  }
  v18 = WerPluginAdjustAppContainerAccessToKey(hKey, v17, 0x80000002);
  if ( v18 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v18);
  }
  for ( i = 0; i < 0x15; ++i )
  {
    v20 = 71LL * (int)i;
    if ( (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierFlags")
      && (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierCount")
      && (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierTimeDuration")
      && (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierBucketID") )
    {
      v25 = 0;
    }
    else
    {
      if ( HIDWORD(this[v20 + 190]) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v22, v21, v23, v24);
      v25 = 1;
    }
    HIDWORD(this[v20 + 190]) = v25;
  }
  v13 = WerPluginWriteSettings((struct _AUTOVERIFIER_IPT_SETTINGS *)(this + 120), 0x15u, hKey, 0);
  v5 = v13;
  if ( v13 >= 0 )
  {
    CAutoVerifierPlugin::EnableHKCULookupForIFEO(v26, 1);
    *((_DWORD *)this + 238) = 1;
    v5 = 0;
    goto LABEL_69;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_69;
  v15 = 64;
LABEL_37:
  WPP_SF_d(v14[2], v15, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids, (unsigned int)v13);
LABEL_69:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v31 )
    RegCloseKey(v31);
  if ( v28 )
    RegCloseKey(v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002b4c4  mov     [rsp-38h+arg_0], rbx
0x18002b4c9  push    rbp
0x18002b4ca  push    rsi
0x18002b4cb  push    rdi
0x18002b4cc  push    r12
0x18002b4ce  push    r13
0x18002b4d0  push    r14
0x18002b4d2  push    r15
0x18002b4d4  mov     rbp, rsp
0x18002b4d7  sub     rsp, 60h
0x18002b4db  mov     rbx, rdx
0x18002b4de  mov     r14, rcx
0x18002b4e1  xor     r15d, r15d
0x18002b4e4  mov     [rbp+var_8], r15
0x18002b4e8  mov     [rbp+arg_18], r15
0x18002b4ec  mov     ecx, r15d
0x18002b4ef  mov     [rbp+hKey], rcx
0x18002b4f3  mov     [rbp+dwDisposition], r15d
0x18002b4f7  mov     [rbp+arg_8], r15d
0x18002b4fb  test    rdx, rdx
0x18002b4fe  jnz     short loc_18002B567
0x18002b500  lea     rsi, WPP_GLOBAL_Control
0x18002b507  mov     rax, cs:WPP_GLOBAL_Control
0x18002b50e  cmp     rax, rsi
0x18002b511  jz      short loc_18002B532
0x18002b513  lea     ebx, [rdx+1]
0x18002b516  test    [rax+1Ch], bl
0x18002b519  jz      short loc_18002B532
0x18002b51b  lea     edx, [rbx+34h]
0x18002b51e  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b525  mov     rcx, [rax+10h]
0x18002b529  call    WPP_SF_
0x18002b52e  mov     rcx, [rbp+hKey]; hKey
0x18002b532  test    rcx, rcx
0x18002b535  jz      short loc_18002B53E
0x18002b537  call    cs:__imp_RegCloseKey
0x18002b53d  nop
0x18002b53e  mov     rcx, [rbp+arg_18]; hKey
0x18002b542  test    rcx, rcx
0x18002b545  jz      short loc_18002B54E
0x18002b547  call    cs:__imp_RegCloseKey
0x18002b54d  nop
0x18002b54e  mov     rcx, [rbp+var_8]; hKey
0x18002b552  test    rcx, rcx
0x18002b555  jz      short loc_18002B55D
0x18002b557  call    cs:__imp_RegCloseKey
0x18002b55d  mov     eax, 80070057h
0x18002b562  jmp     loc_18002B9AB
0x18002b567  lea     rdx, [rbp+arg_8]; int *
0x18002b56b  mov     rcx, r14; this
0x18002b56e  call    ?ValidateAutoverifier@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::ValidateAutoverifier(int *)
0x18002b573  mov     edi, eax
0x18002b575  test    eax, eax
0x18002b577  jns     short loc_18002B5A6
0x18002b579  lea     rsi, WPP_GLOBAL_Control
0x18002b580  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b587  cmp     rcx, rsi
0x18002b58a  jz      loc_18002B97A
0x18002b590  mov     ebx, 1
0x18002b595  test    [rcx+1Ch], bl
0x18002b598  jz      loc_18002B97A
0x18002b59e  lea     edx, [rbx+35h]
0x18002b5a1  jmp     loc_18002B969
0x18002b5a6  cmp     [rbp+arg_8], r15d
0x18002b5aa  jnz     short loc_18002B5DA
0x18002b5ac  mov     edi, 1
0x18002b5b1  lea     rsi, WPP_GLOBAL_Control
0x18002b5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5bf  cmp     rcx, rsi
0x18002b5c2  jz      loc_18002B97A
0x18002b5c8  test    byte ptr [rcx+1Ch], 4
0x18002b5cc  jz      loc_18002B97A
0x18002b5d2  lea     edx, [rdi+36h]
0x18002b5d5  jmp     loc_18002B969
0x18002b5da  mov     rdx, rbx; void *
0x18002b5dd  mov     rcx, r14; this
0x18002b5e0  call    ?PromptForEnableAutoVerifier@CAutoVerifierPlugin@@AEAAHPEAX@Z; CAutoVerifierPlugin::PromptForEnableAutoVerifier(void *)
0x18002b5e5  test    eax, eax
0x18002b5e7  jnz     short loc_18002B61F
0x18002b5e9  lea     rsi, WPP_GLOBAL_Control
0x18002b5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5f7  cmp     rcx, rsi
0x18002b5fa  jz      short loc_18002B615
0x18002b5fc  test    byte ptr [rcx+1Ch], 4
0x18002b600  jz      short loc_18002B615
0x18002b602  lea     edx, [rax+38h]
0x18002b605  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b60c  mov     rcx, [rcx+10h]
0x18002b610  call    WPP_SF_
0x18002b615  mov     edi, 1
0x18002b61a  jmp     loc_18002B97A
0x18002b61f  mov     ebx, 1
0x18002b624  mov     edx, ebx; unsigned int
0x18002b626  call    ?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z; CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)
0x18002b62b  mov     edi, eax
0x18002b62d  test    eax, eax
0x18002b62f  jns     short loc_18002B659
0x18002b631  lea     rsi, WPP_GLOBAL_Control
0x18002b638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b63f  cmp     rcx, rsi
0x18002b642  jz      loc_18002B97A
0x18002b648  test    [rcx+1Ch], bl
0x18002b64b  jz      loc_18002B97A
0x18002b651  lea     edx, [rbx+38h]
0x18002b654  jmp     loc_18002B969
0x18002b659  lea     rcx, [rbp+var_8]
0x18002b65d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002b662  mov     [rsp+60h+lpdwDisposition], r15; lpdwDisposition
0x18002b667  mov     [rsp+60h+phkResult], rax; phkResult
0x18002b66c  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002b671  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18002b679  mov     [rsp+60h+dwOptions], r15d; dwOptions
0x18002b67e  xor     r9d, r9d; lpClass
0x18002b681  xor     r8d, r8d; Reserved
0x18002b684  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002b68b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002b692  call    cs:__imp_RegCreateKeyExW
0x18002b698  test    eax, eax
0x18002b69a  jnz     loc_18002B947
0x18002b6a0  cmp     [rbp+var_8], r15
0x18002b6a4  jz      loc_18002B947
0x18002b6aa  lea     rcx, [rbp+arg_18]
0x18002b6ae  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002b6b3  lea     rcx, [rbp+dwDisposition]
0x18002b6b7  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x18002b6bc  mov     [rsp+60h+phkResult], rax; phkResult
0x18002b6c1  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002b6c6  mov     r12d, 60002h
0x18002b6cc  mov     [rsp+60h+samDesired], r12d; samDesired
0x18002b6d1  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x18002b6d5  xor     r9d, r9d; lpClass
0x18002b6d8  xor     r8d, r8d; Reserved
0x18002b6db  mov     rdx, [r14+2E8h]; lpSubKey
0x18002b6e2  mov     rcx, [rbp+var_8]; hKey
0x18002b6e6  call    cs:__imp_RegCreateKeyExW
0x18002b6ec  test    eax, eax
0x18002b6ee  jnz     loc_18002B923
0x18002b6f4  mov     rcx, [rbp+arg_18]; hKey
0x18002b6f8  test    rcx, rcx
0x18002b6fb  jz      loc_18002B923
0x18002b701  mov     r8d, 80010000h; unsigned int
0x18002b707  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x18002b70c  lea     rsi, WPP_GLOBAL_Control
0x18002b713  test    eax, eax
0x18002b715  jns     short loc_18002B741
0x18002b717  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b71e  cmp     rcx, rsi
0x18002b721  jz      short loc_18002B741
0x18002b723  test    byte ptr [rcx+1Ch], 2
0x18002b727  jz      short loc_18002B741
0x18002b729  mov     edx, 3Ch ; '<'
0x18002b72e  mov     r9d, eax
0x18002b731  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b738  mov     rcx, [rcx+10h]
0x18002b73c  call    WPP_SF_d
0x18002b741  lea     r13, [r14+3C0h]
0x18002b748  xor     r9d, r9d; wchar_t *
0x18002b74b  mov     r8, [rbp+arg_18]; HKEY
0x18002b74f  lea     edx, [r9+15h]; unsigned int
0x18002b753  mov     rcx, r13; struct _AUTOVERIFIER_IPT_SETTINGS *
0x18002b756  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x18002b75b  mov     edi, eax
0x18002b75d  test    eax, eax
0x18002b75f  jns     short loc_18002B797
0x18002b761  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b768  cmp     rcx, rsi
0x18002b76b  jz      loc_18002B97A
0x18002b771  test    [rcx+1Ch], bl
0x18002b774  jz      loc_18002B97A
0x18002b77a  mov     edx, 3Dh ; '='
0x18002b77f  mov     r9d, eax
0x18002b782  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b789  mov     rcx, [rcx+10h]
0x18002b78d  call    WPP_SF_d
0x18002b792  jmp     loc_18002B97A
0x18002b797  lea     rcx, [rbp+hKey]
0x18002b79b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002b7a0  lea     rcx, [rbp+dwDisposition]
0x18002b7a4  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x18002b7a9  mov     [rsp+60h+phkResult], rax; phkResult
0x18002b7ae  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002b7b3  mov     [rsp+60h+samDesired], r12d; samDesired
0x18002b7b8  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x18002b7bc  xor     r9d, r9d; lpClass
0x18002b7bf  xor     r8d, r8d; Reserved
0x18002b7c2  lea     rdx, aAutoverifier; "Autoverifier"
0x18002b7c9  mov     rcx, [rbp+arg_18]; hKey
0x18002b7cd  call    cs:__imp_RegCreateKeyExW
0x18002b7d3  test    eax, eax
0x18002b7d5  jnz     loc_18002B906
0x18002b7db  mov     rcx, [rbp+hKey]; hKey
0x18002b7df  test    rcx, rcx
0x18002b7e2  jz      loc_18002B906
0x18002b7e8  mov     r8d, 80000002h; unsigned int
0x18002b7ee  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x18002b7f3  test    eax, eax
0x18002b7f5  jns     short loc_18002B821
0x18002b7f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7fe  cmp     rcx, rsi
0x18002b801  jz      short loc_18002B821
0x18002b803  test    byte ptr [rcx+1Ch], 2
0x18002b807  jz      short loc_18002B821
0x18002b809  mov     edx, 3Fh ; '?'
0x18002b80e  mov     r9d, eax
0x18002b811  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b818  mov     rcx, [rcx+10h]
0x18002b81c  call    WPP_SF_d
0x18002b821  mov     edi, r15d
0x18002b824  movsxd  rax, edi
0x18002b827  imul    r12, rax, 238h
0x18002b82e  lea     r15, [r14+3C4h]
0x18002b835  add     r15, r12
0x18002b838  lea     rdx, aAutoverifierfl; "AutoVerifierFlags"
0x18002b83f  mov     rcx, r15
0x18002b842  call    cs:__imp__o__wcsicmp
0x18002b848  test    eax, eax
0x18002b84a  jz      short loc_18002B890
0x18002b84c  lea     rdx, aAutoverifierco; "AutoVerifierCount"
0x18002b853  mov     rcx, r15
0x18002b856  call    cs:__imp__o__wcsicmp
0x18002b85c  test    eax, eax
0x18002b85e  jz      short loc_18002B890
0x18002b860  lea     rdx, aAutoverifierti; "AutoVerifierTimeDuration"
0x18002b867  mov     rcx, r15
0x18002b86a  call    cs:__imp__o__wcsicmp
0x18002b870  test    eax, eax
0x18002b872  jz      short loc_18002B890
0x18002b874  lea     rdx, aAutoverifierbu; "AutoVerifierBucketID"
0x18002b87b  mov     rcx, r15
0x18002b87e  call    cs:__imp__o__wcsicmp
0x18002b884  xor     r15d, r15d
0x18002b887  test    eax, eax
0x18002b889  jz      short loc_18002B893
0x18002b88b  mov     eax, r15d
0x18002b88e  jmp     short loc_18002B8A4
0x18002b890  xor     r15d, r15d
0x18002b893  cmp     [r12+r14+5F4h], r15d
0x18002b89b  jz      short loc_18002B8A2
0x18002b89d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b8a2  mov     eax, ebx
0x18002b8a4  mov     [r12+r14+5F4h], eax
0x18002b8ac  add     edi, ebx
0x18002b8ae  cmp     edi, 15h
0x18002b8b1  jb      loc_18002B824
0x18002b8b7  xor     r9d, r9d; wchar_t *
0x18002b8ba  mov     r8, [rbp+hKey]; HKEY
0x18002b8be  lea     edx, [r9+15h]; unsigned int
0x18002b8c2  mov     rcx, r13; struct _AUTOVERIFIER_IPT_SETTINGS *
0x18002b8c5  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x18002b8ca  mov     edi, eax
0x18002b8cc  test    eax, eax
0x18002b8ce  jns     short loc_18002B8F3
0x18002b8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8d7  cmp     rcx, rsi
0x18002b8da  jz      loc_18002B97A
0x18002b8e0  test    [rcx+1Ch], bl
0x18002b8e3  jz      loc_18002B97A
0x18002b8e9  mov     edx, 40h ; '@'
0x18002b8ee  jmp     loc_18002B77F
0x18002b8f3  mov     edx, ebx; int
0x18002b8f5  call    ?EnableHKCULookupForIFEO@CAutoVerifierPlugin@@AEAAJH@Z; CAutoVerifierPlugin::EnableHKCULookupForIFEO(int)
0x18002b8fa  mov     [r14+3B8h], ebx
0x18002b901  mov     edi, r15d
0x18002b904  jmp     short loc_18002B97A
0x18002b906  mov     edi, 80004005h
0x18002b90b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b912  cmp     rcx, rsi
0x18002b915  jz      short loc_18002B97A
0x18002b917  test    [rcx+1Ch], bl
0x18002b91a  jz      short loc_18002B97A
0x18002b91c  mov     edx, 3Eh ; '>'
0x18002b921  jmp     short loc_18002B969
0x18002b923  mov     edi, 80004005h
0x18002b928  lea     rsi, WPP_GLOBAL_Control
0x18002b92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b936  cmp     rcx, rsi
0x18002b939  jz      short loc_18002B97A
0x18002b93b  test    [rcx+1Ch], bl
0x18002b93e  jz      short loc_18002B97A
0x18002b940  mov     edx, 3Bh ; ';'
0x18002b945  jmp     short loc_18002B969
0x18002b947  mov     edi, 80004005h
0x18002b94c  lea     rsi, WPP_GLOBAL_Control
0x18002b953  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b95a  cmp     rcx, rsi
0x18002b95d  jz      short loc_18002B97A
0x18002b95f  test    [rcx+1Ch], bl
0x18002b962  jz      short loc_18002B97A
0x18002b964  mov     edx, 3Ah ; ':'
0x18002b969  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b970  mov     rcx, [rcx+10h]
0x18002b974  call    WPP_SF_
0x18002b979  nop
0x18002b97a  mov     rcx, [rbp+hKey]; hKey
0x18002b97e  test    rcx, rcx
0x18002b981  jz      short loc_18002B98A
0x18002b983  call    cs:__imp_RegCloseKey
0x18002b989  nop
0x18002b98a  mov     rcx, [rbp+arg_18]; hKey
0x18002b98e  test    rcx, rcx
  ... truncated ...
```
