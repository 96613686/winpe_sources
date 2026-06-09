# CAutoVerifierPlugin::ValidateAutoverifier(int *)

- ea: `0x18002d57c`
- end: `0x18002d74d`
- name: `?ValidateAutoverifier@CAutoVerifierPlugin@@AEAAJPEAH@Z`
- size: `465`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b4c4`

## callees

- `0x180009ed8`
- `0x18000a004`
- `0x18002b11c`
- `0x18002b218`
- `0x18002d57c`
- `0x180036e08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d67b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d67b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d5d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d73a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d5d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d73a`

## string_xrefs

- `0x18002d64c`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::ValidateAutoverifier(CAutoVerifierPlugin *this, int *a2)
{
  HKEY v4; // rcx
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HKEY *phkResult; // rax
  const wchar_t *v10; // r8
  CAutoVerifierPlugin *v11; // rcx
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
      v4 = hKey;
    }
    if ( v4 )
      RegCloseKey(v4);
    return 2147942487LL;
  }
  v6 = CAutoVerifierPlugin::CheckSettingsAndVersion(this, a2);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v8 = 31;
    goto LABEL_12;
  }
  if ( !*a2 )
    goto LABEL_28;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins",
         0,
         0,
         0,
         5u,
         0,
         phkResult,
         &dwDisposition) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    v6 = -2147467259;
    goto LABEL_29;
  }
  v6 = CheckPluginLastPromptedTime(hKey, 0, v10, 2u, a2);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v8 = 33;
    goto LABEL_12;
  }
  if ( !*a2 || (v6 = CAutoVerifierPlugin::CheckForMonitoredApplications(v11, a2), v6 >= 0) )
  {
LABEL_28:
    v6 = 0;
    goto LABEL_29;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_29;
  v8 = 34;
LABEL_12:
  WPP_SF_(v7[2], v8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002d57c  mov     [rsp+arg_0], rbx
0x18002d581  push    rdi
0x18002d582  sub     rsp, 50h
0x18002d586  mov     rax, rcx
0x18002d589  mov     rdi, rdx
0x18002d58c  xor     ecx, ecx
0x18002d58e  mov     [rsp+58h+hKey], rcx
0x18002d593  mov     [rsp+58h+dwDisposition], ecx
0x18002d597  test    rdx, rdx
0x18002d59a  jnz     short loc_18002D5E3
0x18002d59c  mov     r9, cs:WPP_GLOBAL_Control
0x18002d5a3  lea     rax, WPP_GLOBAL_Control
0x18002d5aa  cmp     r9, rax
0x18002d5ad  jz      short loc_18002D5CE
0x18002d5af  test    byte ptr [r9+1Ch], 1
0x18002d5b4  jz      short loc_18002D5CE
0x18002d5b6  mov     rcx, [r9+10h]
0x18002d5ba  lea     edx, [rdi+1Eh]
0x18002d5bd  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002d5c4  call    WPP_SF_
0x18002d5c9  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d5ce  test    rcx, rcx
0x18002d5d1  jz      short loc_18002D5D9
0x18002d5d3  call    cs:__imp_RegCloseKey
0x18002d5d9  mov     eax, 80070057h
0x18002d5de  jmp     loc_18002D742
0x18002d5e3  mov     rcx, rax; this
0x18002d5e6  call    ?CheckSettingsAndVersion@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::CheckSettingsAndVersion(int *)
0x18002d5eb  mov     ebx, eax
0x18002d5ed  test    eax, eax
0x18002d5ef  jns     short loc_18002D62C
0x18002d5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5f8  lea     rax, WPP_GLOBAL_Control
0x18002d5ff  cmp     rcx, rax
0x18002d602  jz      loc_18002D730
0x18002d608  test    byte ptr [rcx+1Ch], 1
0x18002d60c  jz      loc_18002D730
0x18002d612  mov     edx, 1Fh
0x18002d617  mov     rcx, [rcx+10h]
0x18002d61b  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002d622  call    WPP_SF_
0x18002d627  jmp     loc_18002D730
0x18002d62c  cmp     dword ptr [rdi], 0
0x18002d62f  jz      loc_18002D72E
0x18002d635  lea     rcx, [rsp+58h+hKey]
0x18002d63a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002d63f  lea     rcx, [rsp+58h+dwDisposition]
0x18002d644  xor     r9d, r9d; lpClass
0x18002d647  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18002d64c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x18002d653  mov     [rsp+58h+phkResult], rax; phkResult
0x18002d658  xor     r8d, r8d; Reserved
0x18002d65b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002d664  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002d66b  mov     [rsp+58h+samDesired], 5; samDesired
0x18002d673  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002d67b  call    cs:__imp_RegCreateKeyExW
0x18002d681  test    eax, eax
0x18002d683  jz      short loc_18002D6BA
0x18002d685  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d68c  lea     rax, WPP_GLOBAL_Control
0x18002d693  cmp     rcx, rax
0x18002d696  jz      short loc_18002D6B3
0x18002d698  test    byte ptr [rcx+1Ch], 1
0x18002d69c  jz      short loc_18002D6B3
0x18002d69e  mov     rcx, [rcx+10h]
0x18002d6a2  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002d6a9  mov     edx, 20h ; ' '
0x18002d6ae  call    WPP_SF_
0x18002d6b3  mov     ebx, 80004005h
0x18002d6b8  jmp     short loc_18002D730
0x18002d6ba  mov     rcx, [rsp+58h+hKey]; HKEY
0x18002d6bf  xor     edx, edx; wchar_t *
0x18002d6c1  mov     qword ptr [rsp+58h+dwOptions], rdi; int *
0x18002d6c6  lea     r9d, [rdx+2]; unsigned int
0x18002d6ca  call    ?CheckPluginLastPromptedTime@@YAJPEAUHKEY__@@PEB_W1KPEAH@Z; CheckPluginLastPromptedTime(HKEY__ *,wchar_t const *,wchar_t const *,ulong,int *)
0x18002d6cf  mov     ebx, eax
0x18002d6d1  test    eax, eax
0x18002d6d3  jns     short loc_18002D6F8
0x18002d6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6dc  lea     rax, WPP_GLOBAL_Control
0x18002d6e3  cmp     rcx, rax
0x18002d6e6  jz      short loc_18002D730
0x18002d6e8  test    byte ptr [rcx+1Ch], 1
0x18002d6ec  jz      short loc_18002D730
0x18002d6ee  mov     edx, 21h ; '!'
0x18002d6f3  jmp     loc_18002D617
0x18002d6f8  cmp     dword ptr [rdi], 0
0x18002d6fb  jz      short loc_18002D72E
0x18002d6fd  mov     rdx, rdi; int *
0x18002d700  call    ?CheckForMonitoredApplications@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::CheckForMonitoredApplications(int *)
0x18002d705  mov     ebx, eax
0x18002d707  test    eax, eax
0x18002d709  jns     short loc_18002D72E
0x18002d70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d712  lea     rax, WPP_GLOBAL_Control
0x18002d719  cmp     rcx, rax
0x18002d71c  jz      short loc_18002D730
0x18002d71e  test    byte ptr [rcx+1Ch], 1
0x18002d722  jz      short loc_18002D730
0x18002d724  mov     edx, 22h ; '"'
0x18002d729  jmp     loc_18002D617
0x18002d72e  xor     ebx, ebx
0x18002d730  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d735  test    rcx, rcx
0x18002d738  jz      short loc_18002D740
0x18002d73a  call    cs:__imp_RegCloseKey
0x18002d740  mov     eax, ebx
0x18002d742  mov     rbx, [rsp+58h+arg_0]
0x18002d747  add     rsp, 50h
0x18002d74b  pop     rdi
0x18002d74c  retn
```
