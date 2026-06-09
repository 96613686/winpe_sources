# FwNotifyQueryFriendlyNameForImage(ushort const *,ushort * *)

- ea: `0x18007884c`
- end: `0x180078a7a`
- name: `?FwNotifyQueryFriendlyNameForImage@@YAJPEBGPEAPEAG@Z`
- size: `558`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006edbc`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18006e148`
- `0x18006f520`
- `0x18007884c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800789f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800789f5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180078a3f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180078a3f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007888a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007888a`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x180078908`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x18007896a`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x180078908`
- `ext-ms-win-shell-shlwapi-l1-1-0!AssocQueryStringW` at `0x18007896a`
- `fwbase!FwStringCopy` at `0x180078a03`
- `fwbase!FwStringCopy` at `0x180078a03`
- `fwbase!FwReportReturnError` at `0x180078a18`
- `fwbase!FwReportReturnError` at `0x180078a52`
- `fwbase!FwReportReturnError` at `0x180078a18`
- `fwbase!FwReportReturnError` at `0x180078a52`
- `fwbase!FwAlloc` at `0x180078920`
- `fwbase!FwAlloc` at `0x180078920`
- `fwbase!FwFree` at `0x1800789b4`
- `fwbase!FwFree` at `0x1800789b4`
- `fwbase!FwReportErrorAsWinError` at `0x180078942`
- `fwbase!FwReportErrorAsWinError` at `0x180078942`

## pseudocode

```c
__int64 __fastcall FwNotifyQueryFriendlyNameForImage(LPCWSTR pszPath, unsigned __int16 **a2)
{
  HRESULT v4; // edi
  __int64 v5; // r8
  HRESULT v6; // ebx
  HRESULT v7; // eax
  WCHAR *pszOut; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  LPWSTR FileNameW; // rax
  int v13; // eax
  __int64 v14; // rdx
  DWORD pcchOut; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  v17 = 0;
  pcchOut = 0;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    v6 = v4;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        23,
        WPP_3ec461e273913f4b05610a2e2629c131_Traceguids,
        (unsigned int)v4);
    return (unsigned int)FwReportReturnError("FwNotifyQueryFriendlyNameForImage", (unsigned int)v6, v5);
  }
  v7 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, pszPath, 0, 0, &pcchOut);
  if ( v7 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        25,
        (unsigned int)WPP_3ec461e273913f4b05610a2e2629c131_Traceguids,
        (_DWORD)pszPath,
        v7);
  }
  else
  {
    pszOut = (WCHAR *)FwAlloc(2LL * pcchOut);
    v17 = pszOut;
    if ( !pszOut )
    {
      v6 = FwReportErrorAsWinError("FwNotifyQueryFriendlyNameForImage", "FwAlloc", 8);
      goto LABEL_23;
    }
    v6 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, pszPath, 0, pszOut, &pcchOut);
    if ( v6 >= 0 )
      goto LABEL_20;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        24,
        (unsigned int)WPP_3ec461e273913f4b05610a2e2629c131_Traceguids,
        (_DWORD)pszPath,
        v6);
    FwFree(v17);
  }
  FileNameW = PathFindFileNameW(pszPath);
  v13 = FwStringCopy(FileNameW, &v17);
  v6 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
LABEL_19:
    FwReportReturnError("FwNotifyQueryFriendlyNameForImage", v14, v5);
    goto LABEL_23;
  }
LABEL_20:
  if ( !v17 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v5, v11);
    v6 = -2147467261;
    v14 = 2147500035LL;
    goto LABEL_19;
  }
  *a2 = v17;
LABEL_23:
  if ( v4 >= 0 )
    CoUninitialize();
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwNotifyQueryFriendlyNameForImage", (unsigned int)v6, v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007884c  mov     [rsp+arg_10], rbx
0x180078851  push    rsi
0x180078852  push    rdi
0x180078853  push    r14
0x180078855  sub     rsp, 50h
0x180078859  mov     rax, cs:__security_cookie
0x180078860  xor     rax, rsp
0x180078863  mov     [rsp+68h+var_28], rax
0x180078868  mov     r14, rdx
0x18007886b  mov     qword ptr [rdx], 0
0x180078872  mov     rsi, rcx
0x180078875  mov     [rsp+68h+var_30], 0
0x18007887e  xor     edx, edx; dwCoInit
0x180078880  mov     [rsp+68h+var_38], 0
0x180078888  xor     ecx, ecx; pvReserved
0x18007888a  call    cs:__imp_CoInitializeEx
0x180078890  mov     edi, eax
0x180078892  mov     eax, 80000000h
0x180078897  lea     ecx, [rdi+rax]
0x18007889a  test    eax, ecx
0x18007889c  jnz     short loc_1800788E6
0x18007889e  cmp     edi, 80010106h
0x1800788a4  jz      short loc_1800788E6
0x1800788a6  mov     ebx, edi
0x1800788a8  mov     rax, cs:WPP_GLOBAL_Control
0x1800788af  lea     rcx, WPP_GLOBAL_Control
0x1800788b6  cmp     rax, rcx
0x1800788b9  jz      loc_180078A49
0x1800788bf  test    byte ptr [rax+1Ch], 1
0x1800788c3  jz      loc_180078A49
0x1800788c9  mov     rcx, [rax+10h]
0x1800788cd  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x1800788d4  mov     edx, 17h
0x1800788d9  mov     r9d, edi
0x1800788dc  call    WPP_SF_d
0x1800788e1  jmp     loc_180078A49
0x1800788e6  xor     r9d, r9d; pszExtra
0x1800788e9  lea     rax, [rsp+68h+var_38]
0x1800788ee  mov     [rsp+68h+pcchOut], rax; pcchOut
0x1800788f3  mov     r8, rsi; pszAssoc
0x1800788f6  mov     [rsp+68h+pszOut], 0; pszOut
0x1800788ff  lea     ebx, [r9+4]
0x180078903  mov     edx, ebx; str
0x180078905  lea     ecx, [rbx-2]; flags
0x180078908  call    cs:__imp_AssocQueryStringW
0x18007890e  mov     r8d, eax
0x180078911  test    eax, eax
0x180078913  js      loc_1800789BC
0x180078919  mov     ecx, [rsp+68h+var_38]
0x18007891d  add     rcx, rcx
0x180078920  call    cs:__imp_FwAlloc
0x180078926  mov     [rsp+68h+var_30], rax
0x18007892b  test    rax, rax
0x18007892e  jnz     short loc_18007894F
0x180078930  lea     r8d, [rbx+4]
0x180078934  lea     rdx, aFwalloc_0; "FwAlloc"
0x18007893b  lea     rcx, aFwnotifyqueryf; "FwNotifyQueryFriendlyNameForImage"
0x180078942  call    cs:__imp_FwReportErrorAsWinError
0x180078948  mov     ebx, eax
0x18007894a  jmp     loc_180078A3B
0x18007894f  xor     r9d, r9d; pszExtra
0x180078952  lea     r8, [rsp+68h+var_38]
0x180078957  mov     [rsp+68h+pcchOut], r8; pcchOut
0x18007895c  mov     edx, ebx; str
0x18007895e  mov     r8, rsi; pszAssoc
0x180078961  mov     [rsp+68h+pszOut], rax; pszOut
0x180078966  lea     ecx, [r9+2]; flags
0x18007896a  call    cs:__imp_AssocQueryStringW
0x180078970  mov     ebx, eax
0x180078972  test    eax, eax
0x180078974  jns     loc_180078A20
0x18007897a  mov     rax, cs:WPP_GLOBAL_Control
0x180078981  lea     rcx, WPP_GLOBAL_Control
0x180078988  cmp     rax, rcx
0x18007898b  jz      short loc_1800789AF
0x18007898d  test    byte ptr [rax+1Ch], 1
0x180078991  jz      short loc_1800789AF
0x180078993  mov     rcx, [rax+10h]
0x180078997  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x18007899e  mov     edx, 18h
0x1800789a3  mov     dword ptr [rsp+68h+pszOut], ebx
0x1800789a7  mov     r9, rsi
0x1800789aa  call    WPP_SF_Sd
0x1800789af  mov     rcx, [rsp+68h+var_30]
0x1800789b4  call    cs:__imp_FwFree
0x1800789ba  jmp     short loc_1800789F2
0x1800789bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800789c3  lea     rcx, WPP_GLOBAL_Control
0x1800789ca  cmp     rax, rcx
0x1800789cd  jz      short loc_1800789F2
0x1800789cf  test    byte ptr [rax+1Ch], 1
0x1800789d3  jz      short loc_1800789F2
0x1800789d5  mov     rcx, [rax+10h]
0x1800789d9  mov     edx, 19h
0x1800789de  mov     dword ptr [rsp+68h+pszOut], r8d
0x1800789e3  mov     r9, rsi
0x1800789e6  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x1800789ed  call    WPP_SF_Sd
0x1800789f2  mov     rcx, rsi; pszPath
0x1800789f5  call    cs:__imp_PathFindFileNameW
0x1800789fb  mov     rcx, rax
0x1800789fe  lea     rdx, [rsp+68h+var_30]
0x180078a03  call    cs:__imp_FwStringCopy
0x180078a09  mov     ebx, eax
0x180078a0b  test    eax, eax
0x180078a0d  jns     short loc_180078A20
0x180078a0f  mov     edx, eax
0x180078a11  lea     rcx, aFwnotifyqueryf; "FwNotifyQueryFriendlyNameForImage"
0x180078a18  call    cs:__imp_FwReportReturnError
0x180078a1e  jmp     short loc_180078A3B
0x180078a20  mov     rax, [rsp+68h+var_30]
0x180078a25  test    rax, rax
0x180078a28  jnz     short loc_180078A38
0x180078a2a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180078a2f  mov     ebx, 80004003h
0x180078a34  mov     edx, ebx
0x180078a36  jmp     short loc_180078A11
0x180078a38  mov     [r14], rax
0x180078a3b  test    edi, edi
0x180078a3d  js      short loc_180078A45
0x180078a3f  call    cs:__imp_CoUninitialize
0x180078a45  test    ebx, ebx
0x180078a47  jns     short loc_180078A5A
0x180078a49  mov     edx, ebx
0x180078a4b  lea     rcx, aFwnotifyqueryf; "FwNotifyQueryFriendlyNameForImage"
0x180078a52  call    cs:__imp_FwReportReturnError
0x180078a58  mov     ebx, eax
0x180078a5a  mov     eax, ebx
0x180078a5c  mov     rcx, [rsp+68h+var_28]
0x180078a61  xor     rcx, rsp; StackCookie
0x180078a64  call    __security_check_cookie
0x180078a69  mov     rbx, [rsp+68h+arg_10]
0x180078a71  add     rsp, 50h
0x180078a75  pop     r14
0x180078a77  pop     rdi
0x180078a78  pop     rsi
0x180078a79  retn
```
