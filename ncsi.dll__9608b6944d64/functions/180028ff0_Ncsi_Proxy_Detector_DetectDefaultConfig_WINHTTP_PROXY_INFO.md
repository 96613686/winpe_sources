# Ncsi::Proxy::Detector::DetectDefaultConfig(_WINHTTP_PROXY_INFO &)

- ea: `0x180028ff0`
- end: `0x1800290c6`
- name: `?DetectDefaultConfig@Detector@Proxy@Ncsi@@CAKAEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `214`
- prototype: `unsigned int __fastcall(WINHTTP_PROXY_INFO *pProxyInfo)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028f04`

## callees

- `0x180010200`
- `0x180011a58`
- `0x180028ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002904a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002904a`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180029040`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180029040`

## pseudocode

```c
__int64 __fastcall Ncsi::Proxy::Detector::DetectDefaultConfig(WINHTTP_PROXY_INFO *pProxyInfo)
{
  DWORD LastError; // eax

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids);
  }
  *(_OWORD *)&pProxyInfo->dwAccessType = 0;
  pProxyInfo->lpszProxyBypass = 0;
  if ( !WinHttpGetDefaultProxyConfiguration(pProxyInfo) )
  {
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids, LastError);
    }
    return 1168;
  }
  if ( pProxyInfo->dwAccessType != 3 )
    return 1168;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 45, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180028ff0  mov     [rsp+arg_0], rbx
0x180028ff5  push    rsi
0x180028ff6  sub     rsp, 20h
0x180028ffa  mov     rbx, rcx
0x180028ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180029004  lea     rsi, WPP_GLOBAL_Control
0x18002900b  cmp     rcx, rsi
0x18002900e  jz      short loc_180029031
0x180029010  test    byte ptr [rcx+1Ch], 10h
0x180029014  jz      short loc_180029031
0x180029016  cmp     byte ptr [rcx+19h], 5
0x18002901a  jb      short loc_180029031
0x18002901c  mov     rcx, [rcx+10h]
0x180029020  lea     r8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids
0x180029027  mov     edx, 2Bh ; '+'
0x18002902c  call    WPP_SF_
0x180029031  xorps   xmm0, xmm0
0x180029034  xor     eax, eax
0x180029036  movups  xmmword ptr [rbx], xmm0
0x180029039  mov     rcx, rbx; pProxyInfo
0x18002903c  mov     [rbx+10h], rax
0x180029040  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x180029046  test    eax, eax
0x180029048  jnz     short loc_180029090
0x18002904a  call    cs:__imp_GetLastError
0x180029050  mov     rcx, cs:WPP_GLOBAL_Control
0x180029057  cmp     rcx, rsi
0x18002905a  jz      short loc_180029080
0x18002905c  test    byte ptr [rcx+1Ch], 10h
0x180029060  jz      short loc_180029080
0x180029062  cmp     byte ptr [rcx+19h], 2
0x180029066  jb      short loc_180029080
0x180029068  mov     rcx, [rcx+10h]
0x18002906c  lea     r8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids
0x180029073  mov     edx, 2Ch ; ','
0x180029078  mov     r9d, eax
0x18002907b  call    WPP_SF_d
0x180029080  mov     eax, 490h
0x180029085  mov     rbx, [rsp+28h+arg_0]
0x18002908a  add     rsp, 20h
0x18002908e  pop     rsi
0x18002908f  retn
0x180029090  cmp     dword ptr [rbx], 3
0x180029093  jnz     short loc_180029080
0x180029095  mov     rcx, cs:WPP_GLOBAL_Control
0x18002909c  cmp     rcx, rsi
0x18002909f  jz      short loc_1800290C2
0x1800290a1  test    byte ptr [rcx+1Ch], 10h
0x1800290a5  jz      short loc_1800290C2
0x1800290a7  cmp     byte ptr [rcx+19h], 5
0x1800290ab  jb      short loc_1800290C2
0x1800290ad  mov     rcx, [rcx+10h]
0x1800290b1  lea     r8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids
0x1800290b8  mov     edx, 2Dh ; '-'
0x1800290bd  call    WPP_SF_
0x1800290c2  xor     eax, eax
0x1800290c4  jmp     short loc_180029085
```
