# EndpointDlp::Common::GetLocalMachineStringRegistryValue(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180063438`
- end: `0x1800635e6`
- name: `?GetLocalMachineStringRegistryValue@Common@EndpointDlp@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `430`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800630ac`
- `0x1800b73d0`
- `0x18016de0c`
- `0x180180938`
- `0x1801f8780`

## callees

- `0x180062c38`
- `0x180063438`
- `0x180063ce0`
- `0x18010cb40`
- `0x18023a310`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800634ef`
- `ADVAPI32!RegQueryValueExW` at `0x180063593`
- `ADVAPI32!RegQueryValueExW` at `0x1800634ef`
- `ADVAPI32!RegQueryValueExW` at `0x180063593`
- `ADVAPI32!RegCloseKey` at `0x1800635c0`
- `ADVAPI32!RegCloseKey` at `0x1800635c0`
- `ADVAPI32!RegOpenKeyExW` at `0x18006348d`
- `ADVAPI32!RegOpenKeyExW` at `0x18006348d`

## string_xrefs

- `0x1800634a6`: `src\epp\Dlp\EndpointDlp\Common\src\registry.cpp`
- `0x180063508`: `src\epp\Dlp\EndpointDlp\Common\src\registry.cpp`
- `0x1800635a5`: `src\epp\Dlp\EndpointDlp\Common\src\registry.cpp`
- `0x180063497`: `Failed to open registry key `
- `0x1800634f9`: `Failed to query registry value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall EndpointDlp::Common::GetLocalMachineStringRegistryValue(
        const WCHAR *lpSubKey,
        const WCHAR *lpValueName,
        __int64 a3)
{
  unsigned int v5; // eax
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  LPBYTE v8; // rdx
  __int64 v9; // r14
  unsigned __int64 v10; // rcx
  BYTE *v11; // rax
  size_t v12; // rbx
  unsigned int v13; // eax
  LSTATUS result; // eax
  const char *lpcbData; // [rsp+28h] [rbp-28h]
  const char *lpcbDataa; // [rsp+28h] [rbp-28h]
  const char *lpcbDatab; // [rsp+28h] [rbp-28h]
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  hKey = 0;
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    lpSubKey = *(const WCHAR **)lpSubKey;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x1B,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\registry.cpp",
    (const char *)v5,
    (unsigned int)"Failed to open registry key ",
    lpcbData);
  cbData = 0;
  Type = 0;
  v6 = lpValueName;
  if ( *((_QWORD *)lpValueName + 3) > 7u )
    v6 = *(const WCHAR **)lpValueName;
  v7 = RegQueryValueExW(hKey, v6, 0, &Type, 0, &cbData);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x20,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\registry.cpp",
    (const char *)v7,
    (unsigned int)"Failed to query registry value",
    lpcbDataa);
  v8 = *(LPBYTE *)a3;
  v9 = *(_QWORD *)(a3 + 8);
  v10 = v9 - *(_QWORD *)a3;
  if ( cbData >= v10 )
  {
    if ( cbData <= v10 )
      goto LABEL_12;
    if ( (unsigned __int64)cbData > *(_QWORD *)(a3 + 16) - (_QWORD)v8 )
    {
      _mm_lfence();
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, cbData);
      goto LABEL_12;
    }
    v12 = cbData - v10;
    memset(*(void **)(a3 + 8), 0, v12);
    v11 = (BYTE *)(v12 + v9);
  }
  else
  {
    v11 = &v8[cbData];
  }
  *(_QWORD *)(a3 + 8) = v11;
LABEL_12:
  if ( *((_QWORD *)lpValueName + 3) > 7u )
    lpValueName = *(const WCHAR **)lpValueName;
  v13 = RegQueryValueExW(hKey, lpValueName, 0, &Type, *(LPBYTE *)a3, &cbData);
  result = wil::details::in1diag3::Throw_IfWin32ErrorMsg(
             retaddr,
             (void *)0x24,
             (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\registry.cpp",
             (const char *)v13,
             (unsigned int)"Failed to query registry value",
             lpcbDatab);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180063438  mov     [rsp-28h+arg_18], rbx
0x18006343d  push    rbp
0x18006343e  push    rsi
0x18006343f  push    rdi
0x180063440  push    r13
0x180063442  push    r14
0x180063444  mov     rbp, rsp
0x180063447  sub     rsp, 50h
0x18006344b  mov     rax, cs:__security_cookie
0x180063452  xor     rax, rsp
0x180063455  mov     [rbp+var_10], rax
0x180063459  mov     rsi, r8
0x18006345c  mov     rdi, rdx
0x18006345f  mov     [rbp+hKey], 0
0x180063467  cmp     qword ptr [rcx+18h], 7
0x18006346c  jbe     short loc_180063471
0x18006346e  mov     rcx, [rcx]
0x180063471  lea     rax, [rbp+hKey]
0x180063475  mov     [rsp+50h+phkResult], rax; phkResult
0x18006347a  mov     r9d, 20119h; samDesired
0x180063480  xor     r8d, r8d; ulOptions
0x180063483  mov     rdx, rcx; lpSubKey
0x180063486  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006348d  call    cs:__imp_RegOpenKeyExW
0x180063493  mov     rcx, [rbp+28h]; this
0x180063497  lea     rdx, aFailedToOpenRe; "Failed to open registry key "
0x18006349e  mov     [rsp+50h+phkResult], rdx; unsigned int
0x1800634a3  mov     r9d, eax; char *
0x1800634a6  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x1800634ad  mov     edx, 1Bh; void *
0x1800634b2  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800634b7  mov     [rbp+cbData], 0
0x1800634be  mov     [rbp+Type], 0
0x1800634c5  mov     rdx, rdi
0x1800634c8  cmp     qword ptr [rdi+18h], 7
0x1800634cd  jbe     short loc_1800634D2
0x1800634cf  mov     rdx, [rdi]; lpValueName
0x1800634d2  lea     rax, [rbp+cbData]
0x1800634d6  mov     [rsp+50h+lpcbData], rax; char *
0x1800634db  mov     [rsp+50h+phkResult], 0; lpData
0x1800634e4  lea     r9, [rbp+Type]; lpType
0x1800634e8  xor     r8d, r8d; lpReserved
0x1800634eb  mov     rcx, [rbp+hKey]; hKey
0x1800634ef  call    cs:__imp_RegQueryValueExW
0x1800634f5  mov     rcx, [rbp+28h]; this
0x1800634f9  lea     r13, aFailedToQueryR; "Failed to query registry value"
0x180063500  mov     [rsp+50h+phkResult], r13; unsigned int
0x180063505  mov     r9d, eax; char *
0x180063508  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x18006350f  mov     edx, 20h ; ' '; void *
0x180063514  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180063519  mov     ebx, [rbp+cbData]
0x18006351c  mov     rdx, [rsi]
0x18006351f  mov     r14, [rsi+8]
0x180063523  mov     rcx, r14
0x180063526  sub     rcx, rdx
0x180063529  cmp     rbx, rcx
0x18006352c  jnb     short loc_180063534
0x18006352e  lea     rax, [rdx+rbx]
0x180063532  jmp     short loc_180063566
0x180063534  jbe     short loc_18006356A
0x180063536  mov     rax, [rsi+10h]
0x18006353a  sub     rax, rdx
0x18006353d  cmp     rbx, rax
0x180063540  jbe     short loc_180063552
0x180063542  lfence
0x180063545  mov     rdx, rbx
0x180063548  mov     rcx, rsi
0x18006354b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180063550  jmp     short loc_18006356A
0x180063552  sub     rbx, rcx
0x180063555  mov     r8, rbx; Size
0x180063558  xor     edx, edx; Val
0x18006355a  mov     rcx, r14; void *
0x18006355d  call    memset
0x180063562  lea     rax, [rbx+r14]
0x180063566  mov     [rsi+8], rax
0x18006356a  mov     rax, [rsi]
0x18006356d  cmp     qword ptr [rdi+18h], 7
0x180063572  jbe     short loc_180063577
0x180063574  mov     rdi, [rdi]
0x180063577  lea     rcx, [rbp+cbData]
0x18006357b  mov     [rsp+50h+lpcbData], rcx; char *
0x180063580  mov     [rsp+50h+phkResult], rax; lpData
0x180063585  lea     r9, [rbp+Type]; lpType
0x180063589  xor     r8d, r8d; lpReserved
0x18006358c  mov     rdx, rdi; lpValueName
0x18006358f  mov     rcx, [rbp+hKey]; hKey
0x180063593  call    cs:__imp_RegQueryValueExW
0x180063599  mov     rcx, [rbp+28h]; this
0x18006359d  mov     [rsp+50h+phkResult], r13; unsigned int
0x1800635a2  mov     r9d, eax; char *
0x1800635a5  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x1800635ac  mov     edx, 24h ; '$'; void *
0x1800635b1  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800635b6  nop
0x1800635b7  mov     rcx, [rbp+hKey]; hKey
0x1800635bb  test    rcx, rcx
0x1800635be  jz      short loc_1800635C6
0x1800635c0  call    cs:__imp_RegCloseKey
0x1800635c6  mov     rcx, [rbp+var_10]
0x1800635ca  xor     rcx, rsp; StackCookie
0x1800635cd  call    __security_check_cookie
0x1800635d2  mov     rbx, [rsp+50h+arg_18]
0x1800635da  add     rsp, 50h
0x1800635de  pop     r14
0x1800635e0  pop     r13
0x1800635e2  pop     rdi
0x1800635e3  pop     rsi
0x1800635e4  pop     rbp
0x1800635e5  retn
```
