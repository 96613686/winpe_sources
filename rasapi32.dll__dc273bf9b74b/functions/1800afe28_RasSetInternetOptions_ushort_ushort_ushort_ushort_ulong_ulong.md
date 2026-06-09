# RasSetInternetOptions(ushort *,ushort *,ushort *,ushort *,ulong,ulong)

- ea: `0x1800afe28`
- end: `0x1800aff7e`
- name: `?RasSetInternetOptions@@YAKPEAG000KK@Z`
- size: `342`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, DWORD, DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800aff90`
- `0x1800b0370`

## callees

- `0x18004e580`
- `0x1800afe28`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afe79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afe79`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aff68`
- `WINHTTP!WinHttpCloseHandle` at `0x1800aff68`
- `WINHTTP!WinHttpOpen` at `0x1800afe6b`
- `WINHTTP!WinHttpOpen` at `0x1800afe6b`
- `WINHTTP!WinHttpWriteProxySettings` at `0x1800aff11`
- `WINHTTP!WinHttpWriteProxySettings` at `0x1800aff11`

## pseudocode

```c
__int64 __fastcall RasSetInternetOptions(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        DWORD a5,
        DWORD a6)
{
  void *v10; // rdi
  DWORD LastError; // ebx
  WINHTTP_PROXY_SETTINGS pWinHttpProxySettings; // [rsp+30h] [rbp-98h] BYREF

  memset_0(&pWinHttpProxySettings, 0, sizeof(pWinHttpProxySettings));
  v10 = WinHttpOpen(L"rasapi32", 1u, 0, 0, 0);
  if ( v10 )
  {
    pWinHttpProxySettings.dwFlags = a5;
    pWinHttpProxySettings.dwAutoDiscoveryFlags = a6;
    pWinHttpProxySettings.dwStructSize = 112;
    pWinHttpProxySettings.pwszConnectionName = a1;
    pWinHttpProxySettings.pwszProxy = a2;
    pWinHttpProxySettings.pwszProxyBypass = a3;
    pWinHttpProxySettings.pwszAutoconfigUrl = a4;
    LastError = WinHttpWriteProxySettings(v10, 1, &pWinHttpProxySettings);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, LastError);
      }
      if ( LastError == 12178 )
        LastError = 878;
    }
    WinHttpCloseHandle(v10);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800afe28  push    rbx
0x1800afe2a  push    rbp
0x1800afe2b  push    rsi
0x1800afe2c  push    rdi
0x1800afe2d  push    r14
0x1800afe2f  sub     rsp, 0A0h
0x1800afe36  mov     rbp, rdx
0x1800afe39  mov     rsi, r8
0x1800afe3c  xor     edx, edx; Val
0x1800afe3e  mov     r14, rcx
0x1800afe41  lea     rcx, [rsp+0C8h+pWinHttpProxySettings]; void *
0x1800afe46  mov     rbx, r9
0x1800afe49  lea     r8d, [rdx+70h]; Size
0x1800afe4d  call    memset_0
0x1800afe52  xor     r9d, r9d; pszProxyBypassW
0x1800afe55  mov     [rsp+0C8h+dwFlags], 0; dwFlags
0x1800afe5d  xor     r8d, r8d; pszProxyW
0x1800afe60  lea     rcx, pszAgentW; "rasapi32"
0x1800afe67  lea     edx, [r9+1]; dwAccessType
0x1800afe6b  call    cs:__imp_WinHttpOpen
0x1800afe71  mov     rdi, rax
0x1800afe74  test    rax, rax
0x1800afe77  jnz     short loc_1800AFED2
0x1800afe79  call    cs:__imp_GetLastError
0x1800afe7f  mov     ebx, eax
0x1800afe81  test    eax, eax
0x1800afe83  jz      loc_1800AFF6E
0x1800afe89  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afe90  lea     rax, WPP_GLOBAL_Control
0x1800afe97  cmp     rcx, rax
0x1800afe9a  jz      loc_1800AFF6E
0x1800afea0  test    dword ptr [rcx+1Ch], 800h
0x1800afea7  jz      loc_1800AFF6E
0x1800afead  cmp     byte ptr [rcx+19h], 2
0x1800afeb1  jb      loc_1800AFF6E
0x1800afeb7  mov     rcx, [rcx+10h]
0x1800afebb  lea     edx, [rdi+0Ah]
0x1800afebe  mov     r9d, ebx
0x1800afec1  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800afec8  call    WPP_SF_d
0x1800afecd  jmp     loc_1800AFF6E
0x1800afed2  mov     eax, [rsp+0C8h+arg_20]
0x1800afed9  lea     r8, [rsp+0C8h+pWinHttpProxySettings]; pWinHttpProxySettings
0x1800afede  mov     [rsp+0C8h+pWinHttpProxySettings.dwFlags], eax
0x1800afee2  mov     edx, 1; fForceUpdate
0x1800afee7  mov     eax, [rsp+0C8h+arg_28]
0x1800afeee  mov     rcx, rdi; hSession
0x1800afef1  mov     [rsp+0C8h+pWinHttpProxySettings.dwAutoDiscoveryFlags], eax
0x1800afef5  mov     [rsp+0C8h+pWinHttpProxySettings.dwStructSize], 70h ; 'p'
0x1800afefd  mov     [rsp+0C8h+pWinHttpProxySettings.pwszConnectionName], r14
0x1800aff02  mov     [rsp+0C8h+pWinHttpProxySettings.pwszProxy], rbp
0x1800aff07  mov     [rsp+0C8h+pWinHttpProxySettings.pwszProxyBypass], rsi
0x1800aff0c  mov     [rsp+0C8h+pWinHttpProxySettings.pwszAutoconfigUrl], rbx
0x1800aff11  call    cs:__imp_WinHttpWriteProxySettings
0x1800aff17  mov     ebx, eax
0x1800aff19  test    eax, eax
0x1800aff1b  jz      short loc_1800AFF65
0x1800aff1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aff24  lea     rax, WPP_GLOBAL_Control
0x1800aff2b  cmp     rcx, rax
0x1800aff2e  jz      short loc_1800AFF57
0x1800aff30  test    dword ptr [rcx+1Ch], 800h
0x1800aff37  jz      short loc_1800AFF57
0x1800aff39  cmp     byte ptr [rcx+19h], 2
0x1800aff3d  jb      short loc_1800AFF57
0x1800aff3f  mov     rcx, [rcx+10h]
0x1800aff43  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800aff4a  mov     edx, 0Bh
0x1800aff4f  mov     r9d, ebx
0x1800aff52  call    WPP_SF_d
0x1800aff57  cmp     ebx, 2F92h
0x1800aff5d  mov     eax, 36Eh
0x1800aff62  cmovz   ebx, eax
0x1800aff65  mov     rcx, rdi; hInternet
0x1800aff68  call    cs:__imp_WinHttpCloseHandle
0x1800aff6e  mov     eax, ebx
0x1800aff70  add     rsp, 0A0h
0x1800aff77  pop     r14
0x1800aff79  pop     rdi
0x1800aff7a  pop     rsi
0x1800aff7b  pop     rbp
0x1800aff7c  pop     rbx
0x1800aff7d  retn
```
