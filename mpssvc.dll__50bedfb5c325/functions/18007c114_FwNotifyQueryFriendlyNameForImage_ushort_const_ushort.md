# FwNotifyQueryFriendlyNameForImage(ushort const *,ushort * *)

- ea: `0x18007c114`
- end: `0x18007c385`
- name: `?FwNotifyQueryFriendlyNameForImage@@YAJPEBGPEAPEAG@Z`
- size: `625`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180072230`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180071544`
- `0x1800729c0`
- `0x18007c114`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18007c2e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18007c2e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007c33d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007c33d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007c152`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007c152`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x18007c1d6`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x18007c24a`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x18007c1d6`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x18007c24a`
- `fwbase!FwReportErrorAsWinError` at `0x18007c21c`
- `fwbase!FwReportErrorAsWinError` at `0x18007c21c`
- `fwbase!FwStringCopy` at `0x18007c2f5`
- `fwbase!FwStringCopy` at `0x18007c2f5`
- `fwbase!FwReportReturnError` at `0x18007c310`
- `fwbase!FwReportReturnError` at `0x18007c356`
- `fwbase!FwReportReturnError` at `0x18007c310`
- `fwbase!FwReportReturnError` at `0x18007c356`
- `fwbase!FwAlloc` at `0x18007c1f4`
- `fwbase!FwAlloc` at `0x18007c1f4`
- `fwbase!FwFree` at `0x18007c29a`
- `fwbase!FwFree` at `0x18007c29a`

## pseudocode

```c
__int64 __fastcall FwNotifyQueryFriendlyNameForImage(LPCWSTR pszPath, unsigned __int16 **a2)
{
  HRESULT v4; // edi
  HRESULT v5; // ebx
  HRESULT v6; // eax
  WCHAR *pszOut; // rax
  __int64 v8; // rcx
  LPWSTR FileNameW; // rax
  int v10; // eax
  __int64 v11; // rdx
  DWORD pcchOut; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  v14 = 0;
  pcchOut = 0;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    v5 = v4;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        23,
        WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids,
        (unsigned int)v4);
    return (unsigned int)FwReportReturnError("FwNotifyQueryFriendlyNameForImage", (unsigned int)v5);
  }
  v6 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, pszPath, 0, 0, &pcchOut);
  if ( v6 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        25,
        (unsigned int)WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids,
        (_DWORD)pszPath,
        v6);
  }
  else
  {
    pszOut = (WCHAR *)FwAlloc(2LL * pcchOut);
    v14 = pszOut;
    if ( !pszOut )
    {
      v5 = FwReportErrorAsWinError("FwNotifyQueryFriendlyNameForImage", "FwAlloc", 8);
      goto LABEL_23;
    }
    v5 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, pszPath, 0, pszOut, &pcchOut);
    if ( v5 >= 0 )
      goto LABEL_20;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        24,
        (unsigned int)WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids,
        (_DWORD)pszPath,
        v5);
    FwFree(v14);
  }
  FileNameW = PathFindFileNameW(pszPath);
  v10 = FwStringCopy(FileNameW, &v14);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
LABEL_19:
    FwReportReturnError("FwNotifyQueryFriendlyNameForImage", v11);
    goto LABEL_23;
  }
LABEL_20:
  if ( !v14 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    v5 = -2147467261;
    v11 = 2147500035LL;
    goto LABEL_19;
  }
  *a2 = v14;
LABEL_23:
  if ( v4 >= 0 )
    CoUninitialize();
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwNotifyQueryFriendlyNameForImage", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007c114  mov     [rsp+arg_10], rbx
0x18007c119  push    rsi
0x18007c11a  push    rdi
0x18007c11b  push    r14
0x18007c11d  sub     rsp, 50h
0x18007c121  mov     rax, cs:__security_cookie
0x18007c128  xor     rax, rsp
0x18007c12b  mov     [rsp+68h+var_28], rax
0x18007c130  mov     r14, rdx
0x18007c133  mov     qword ptr [rdx], 0
0x18007c13a  mov     rsi, rcx
0x18007c13d  mov     [rsp+68h+var_30], 0
0x18007c146  xor     edx, edx; dwCoInit
0x18007c148  mov     [rsp+68h+var_38], 0
0x18007c150  xor     ecx, ecx; pvReserved
0x18007c152  call    cs:__imp_CoInitializeEx
0x18007c159  nop     dword ptr [rax+rax+00h]
0x18007c15e  mov     edi, eax
0x18007c160  mov     eax, 80000000h
0x18007c165  lea     ecx, [rdi+rax]
0x18007c168  test    eax, ecx
0x18007c16a  jnz     short loc_18007C1B4
0x18007c16c  cmp     edi, 80010106h
0x18007c172  jz      short loc_18007C1B4
0x18007c174  mov     ebx, edi
0x18007c176  mov     rax, cs:WPP_GLOBAL_Control
0x18007c17d  lea     rcx, WPP_GLOBAL_Control
0x18007c184  cmp     rax, rcx
0x18007c187  jz      loc_18007C34D
0x18007c18d  test    byte ptr [rax+1Ch], 1
0x18007c191  jz      loc_18007C34D
0x18007c197  mov     rcx, [rax+10h]
0x18007c19b  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x18007c1a2  mov     edx, 17h
0x18007c1a7  mov     r9d, edi
0x18007c1aa  call    WPP_SF_d
0x18007c1af  jmp     loc_18007C34D
0x18007c1b4  xor     r9d, r9d; pszExtra
0x18007c1b7  lea     rax, [rsp+68h+var_38]
0x18007c1bc  mov     [rsp+68h+pcchOut], rax; pcchOut
0x18007c1c1  mov     r8, rsi; pszAssoc
0x18007c1c4  mov     [rsp+68h+pszOut], 0; pszOut
0x18007c1cd  lea     ebx, [r9+4]
0x18007c1d1  mov     edx, ebx; str
0x18007c1d3  lea     ecx, [rbx-2]; flags
0x18007c1d6  call    cs:__imp_AssocQueryStringW
0x18007c1dd  nop     dword ptr [rax+rax+00h]
0x18007c1e2  mov     r8d, eax
0x18007c1e5  test    eax, eax
0x18007c1e7  js      loc_18007C2A8
0x18007c1ed  mov     ecx, [rsp+68h+var_38]
0x18007c1f1  add     rcx, rcx
0x18007c1f4  call    cs:__imp_FwAlloc
0x18007c1fb  nop     dword ptr [rax+rax+00h]
0x18007c200  mov     [rsp+68h+var_30], rax
0x18007c205  test    rax, rax
0x18007c208  jnz     short loc_18007C22F
0x18007c20a  lea     r8d, [rbx+4]
0x18007c20e  lea     rdx, aFwalloc_0; "FwAlloc"
0x18007c215  lea     rcx, aFwnotifyqueryf; "FwNotifyQueryFriendlyNameForImage"
0x18007c21c  call    cs:__imp_FwReportErrorAsWinError
0x18007c223  nop     dword ptr [rax+rax+00h]
0x18007c228  mov     ebx, eax
0x18007c22a  jmp     loc_18007C339
0x18007c22f  xor     r9d, r9d; pszExtra
0x18007c232  lea     r8, [rsp+68h+var_38]
0x18007c237  mov     [rsp+68h+pcchOut], r8; pcchOut
0x18007c23c  mov     edx, ebx; str
0x18007c23e  mov     r8, rsi; pszAssoc
0x18007c241  mov     [rsp+68h+pszOut], rax; pszOut
0x18007c246  lea     ecx, [r9+2]; flags
0x18007c24a  call    cs:__imp_AssocQueryStringW
0x18007c251  nop     dword ptr [rax+rax+00h]
0x18007c256  mov     ebx, eax
0x18007c258  test    eax, eax
0x18007c25a  jns     loc_18007C31E
0x18007c260  mov     rax, cs:WPP_GLOBAL_Control
0x18007c267  lea     rcx, WPP_GLOBAL_Control
0x18007c26e  cmp     rax, rcx
0x18007c271  jz      short loc_18007C295
0x18007c273  test    byte ptr [rax+1Ch], 1
0x18007c277  jz      short loc_18007C295
0x18007c279  mov     rcx, [rax+10h]
0x18007c27d  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x18007c284  mov     edx, 18h
0x18007c289  mov     dword ptr [rsp+68h+pszOut], ebx
0x18007c28d  mov     r9, rsi
0x18007c290  call    WPP_SF_Sd
0x18007c295  mov     rcx, [rsp+68h+var_30]
0x18007c29a  call    cs:__imp_FwFree
0x18007c2a1  nop     dword ptr [rax+rax+00h]
0x18007c2a6  jmp     short loc_18007C2DE
0x18007c2a8  mov     rax, cs:WPP_GLOBAL_Control
0x18007c2af  lea     rcx, WPP_GLOBAL_Control
0x18007c2b6  cmp     rax, rcx
0x18007c2b9  jz      short loc_18007C2DE
0x18007c2bb  test    byte ptr [rax+1Ch], 1
0x18007c2bf  jz      short loc_18007C2DE
0x18007c2c1  mov     rcx, [rax+10h]
0x18007c2c5  mov     edx, 19h
0x18007c2ca  mov     dword ptr [rsp+68h+pszOut], r8d
0x18007c2cf  mov     r9, rsi
0x18007c2d2  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x18007c2d9  call    WPP_SF_Sd
0x18007c2de  mov     rcx, rsi; pszPath
0x18007c2e1  call    cs:__imp_PathFindFileNameW
0x18007c2e8  nop     dword ptr [rax+rax+00h]
0x18007c2ed  mov     rcx, rax
0x18007c2f0  lea     rdx, [rsp+68h+var_30]
0x18007c2f5  call    cs:__imp_FwStringCopy
0x18007c2fc  nop     dword ptr [rax+rax+00h]
0x18007c301  mov     ebx, eax
0x18007c303  test    eax, eax
0x18007c305  jns     short loc_18007C31E
0x18007c307  mov     edx, eax
0x18007c309  lea     rcx, aFwnotifyqueryf; "FwNotifyQueryFriendlyNameForImage"
0x18007c310  call    cs:__imp_FwReportReturnError
0x18007c317  nop     dword ptr [rax+rax+00h]
0x18007c31c  jmp     short loc_18007C339
0x18007c31e  mov     rax, [rsp+68h+var_30]
0x18007c323  test    rax, rax
0x18007c326  jnz     short loc_18007C336
0x18007c328  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "name != NULL")
0x18007c32d  mov     ebx, 80004003h
0x18007c332  mov     edx, ebx
0x18007c334  jmp     short loc_18007C309
0x18007c336  mov     [r14], rax
0x18007c339  test    edi, edi
0x18007c33b  js      short loc_18007C349
0x18007c33d  call    cs:__imp_CoUninitialize
0x18007c344  nop     dword ptr [rax+rax+00h]
0x18007c349  test    ebx, ebx
0x18007c34b  jns     short loc_18007C364
0x18007c34d  mov     edx, ebx
0x18007c34f  lea     rcx, aFwnotifyqueryf; "FwNotifyQueryFriendlyNameForImage"
0x18007c356  call    cs:__imp_FwReportReturnError
0x18007c35d  nop     dword ptr [rax+rax+00h]
0x18007c362  mov     ebx, eax
0x18007c364  mov     eax, ebx
0x18007c366  mov     rcx, [rsp+68h+var_28]
0x18007c36b  xor     rcx, rsp; StackCookie
0x18007c36e  call    __security_check_cookie
0x18007c373  mov     rbx, [rsp+68h+arg_10]
0x18007c37b  add     rsp, 50h
0x18007c37f  pop     r14
0x18007c381  pop     rdi
0x18007c382  pop     rsi
0x18007c383  retn
```
