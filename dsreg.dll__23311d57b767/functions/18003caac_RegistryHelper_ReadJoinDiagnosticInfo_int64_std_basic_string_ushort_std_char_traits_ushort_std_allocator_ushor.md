# RegistryHelper::ReadJoinDiagnosticInfo(__int64 &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,long &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003caac`
- end: `0x18003d116`
- name: `?ReadJoinDiagnosticInfo@RegistryHelper@@SAJAEA_JAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAJ1111AEAK1@Z`
- size: `1642`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18002a7e8`

## callees

- `0x1800065d0`
- `0x180006750`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180012c7c`
- `0x18001378c`
- `0x18002b9b4`
- `0x1800319ac`
- `0x18003caac`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cb7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cb7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d0e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d0e4`

## string_xrefs

- `0x18003cd6c`: `RegReadStringValue`
- `0x18003cf27`: `RegReadStringValue`
- `0x18003cba8`: `RegistryHelper::ReadJoinDiagnosticInfo`
- `0x18003cbf2`: `RegistryHelper::ReadJoinDiagnosticInfo`
- `0x18003cc1a`: `RegistryHelper::ReadJoinDiagnosticInfo`
- `0x18003cc7e`: `RegistryHelper::ReadJoinDiagnosticInfo`
- `0x18003cf7b`: `RegistryHelper::ReadJoinDiagnosticInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryHelper::ReadJoinDiagnosticInfo(
        _QWORD *a1,
        char **a2,
        char **a3,
        unsigned int *a4,
        char **a5,
        char **a6,
        char **a7,
        char **a8,
        unsigned int *a9,
        char **a10)
{
  signed int v14; // edi
  unsigned __int16 *v15; // rsi
  const WCHAR *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  LPCWSTR *v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  __int64 v25; // rdx
  LPCWSTR *v26; // rbx
  __int64 v27; // rax
  LPCWSTR *v28; // r8
  const unsigned __int16 *v29; // r9
  int DwordValue; // eax
  const wchar_t *v31; // r8
  const unsigned __int16 *v32; // r9
  int v33; // eax
  const unsigned __int16 *v34; // r9
  int v35; // eax
  const unsigned __int16 *v36; // r9
  int StringValue; // eax
  const unsigned __int16 *v38; // r9
  int v39; // eax
  const unsigned __int16 *v40; // r9
  int v41; // eax
  const unsigned __int16 *v42; // r9
  int v43; // eax
  const unsigned __int16 *v44; // r9
  int v45; // eax
  const unsigned __int16 *v46; // r9
  int v47; // eax
  const unsigned __int16 *v48; // r9
  int v49; // eax
  const wchar_t *v50; // r8
  const unsigned __int16 *v51; // r9
  int v52; // eax
  __int64 v53; // rbx
  __int64 v54; // r8
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // r8
  HKEY hKey; // [rsp+30h] [rbp-A1h] BYREF
  unsigned int v62; // [rsp+38h] [rbp-99h] BYREF
  unsigned __int16 *v63; // [rsp+40h] [rbp-91h] BYREF
  unsigned int v64[2]; // [rsp+48h] [rbp-89h] BYREF
  void *lpMem; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int16 *v66; // [rsp+58h] [rbp-79h] BYREF
  unsigned __int16 *v67; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int16 *v68; // [rsp+68h] [rbp-69h] BYREF
  unsigned __int16 *v69; // [rsp+70h] [rbp-61h] BYREF
  unsigned __int16 *v70; // [rsp+78h] [rbp-59h] BYREF
  char **v71; // [rsp+80h] [rbp-51h]
  char **v72; // [rsp+88h] [rbp-49h]
  char **v73; // [rsp+90h] [rbp-41h]
  char **v74; // [rsp+98h] [rbp-39h]
  char **v75; // [rsp+A0h] [rbp-31h]
  LPCWSTR lpSubKey[3]; // [rsp+A8h] [rbp-29h] BYREF
  unsigned __int64 v77; // [rsp+C0h] [rbp-11h]

  v71 = a5;
  v72 = a6;
  v74 = a7;
  v73 = a8;
  v75 = a10;
  v14 = 0;
  hKey = 0;
  *(_QWORD *)v64 = 0;
  v62 = 0;
  lpMem = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v70 = 0;
  v69 = 0;
  v15 = 0;
  v63 = 0;
  std::wstring::wstring((__int64)lpSubKey, (__int64)L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin\\Diagnostics");
  v16 = (const WCHAR *)lpSubKey;
  if ( v77 > 7 )
    v16 = lpSubKey[0];
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0x20019u, &hKey) != 2 )
  {
    v29 = (const unsigned __int16 *)lpSubKey;
    if ( v77 > 7 )
      v29 = lpSubKey[0];
    DwordValue = RegReadDwordValue(hKey, 0, L"lowTime", v29, v64, 0);
    v14 = DwordValue;
    if ( DwordValue > 0 )
      v14 = (unsigned __int16)DwordValue | 0x80070000;
    if ( v14 < 0 )
      goto LABEL_20;
    v32 = (const unsigned __int16 *)lpSubKey;
    if ( v77 > 7 )
      v32 = lpSubKey[0];
    v33 = RegReadDwordValue(hKey, 0, L"highTime", v32, &v64[1], 0);
    v14 = v33;
    if ( v33 > 0 )
      v14 = (unsigned __int16)v33 | 0x80070000;
    if ( v14 < 0 )
      goto LABEL_20;
    v34 = (const unsigned __int16 *)lpSubKey;
    if ( v77 > 7 )
      v34 = lpSubKey[0];
    v35 = RegReadDwordValue(hKey, 0, L"hr", v34, &v62, 0);
    v14 = v35;
    if ( v35 > 0 )
      v14 = (unsigned __int16)v35 | 0x80070000;
    if ( v14 < 0 )
    {
LABEL_20:
      v31 = L"RegSaveDwordValue";
    }
    else
    {
      v36 = (const unsigned __int16 *)lpSubKey;
      if ( v77 > 7 )
        v36 = lpSubKey[0];
      StringValue = RegReadStringValue(hKey, 0, L"phase", v36, 2u, (unsigned __int16 **)&lpMem);
      v14 = StringValue;
      if ( StringValue > 0 )
        v14 = (unsigned __int16)StringValue | 0x80070000;
      if ( v14 >= 0 )
      {
        v38 = (const unsigned __int16 *)lpSubKey;
        if ( v77 > 7 )
          v38 = lpSubKey[0];
        v39 = RegReadStringValue(hKey, 0, L"registrationType", v38, 2u, &v66);
        v14 = v39;
        if ( v39 > 0 )
          v14 = (unsigned __int16)v39 | 0x80070000;
        if ( v14 >= 0 )
        {
          v40 = (const unsigned __int16 *)lpSubKey;
          if ( v77 > 7 )
            v40 = lpSubKey[0];
          v41 = RegReadStringValue(hKey, 0, L"serverErrorCode", v40, 2u, &v67);
          v14 = v41;
          if ( v41 > 0 )
            v14 = (unsigned __int16)v41 | 0x80070000;
          if ( v14 >= 0 )
          {
            v42 = (const unsigned __int16 *)lpSubKey;
            if ( v77 > 7 )
              v42 = lpSubKey[0];
            v43 = RegReadStringValue(hKey, 0, L"serverErrorSubCode", v42, 2u, &v68);
            v14 = v43;
            if ( v43 > 0 )
              v14 = (unsigned __int16)v43 | 0x80070000;
            if ( v14 >= 0 )
            {
              v44 = (const unsigned __int16 *)lpSubKey;
              if ( v77 > 7 )
                v44 = lpSubKey[0];
              v45 = RegReadStringValue(hKey, 0, L"serverMessage", v44, 2u, &v69);
              v14 = v45;
              if ( v45 > 0 )
                v14 = (unsigned __int16)v45 | 0x80070000;
              if ( v14 >= 0 )
              {
                v46 = (const unsigned __int16 *)lpSubKey;
                if ( v77 > 7 )
                  v46 = lpSubKey[0];
                v47 = RegReadStringValue(hKey, 0, L"serverOperation", v46, 2u, &v70);
                v14 = v47;
                if ( v47 > 0 )
                  v14 = (unsigned __int16)v47 | 0x80070000;
                if ( v14 >= 0 )
                {
                  v48 = (const unsigned __int16 *)lpSubKey;
                  if ( v77 > 7 )
                    v48 = lpSubKey[0];
                  v49 = RegReadStringValue(hKey, 0, L"requestId", v48, 2u, &v63);
                  v14 = v49;
                  if ( v49 > 0 )
                    v14 = (unsigned __int16)v49 | 0x80070000;
                  if ( v14 >= 0 )
                  {
                    v51 = (const unsigned __int16 *)lpSubKey;
                    if ( v77 > 7 )
                      v51 = lpSubKey[0];
                    v52 = RegReadDwordValue(hKey, 0, L"httpStatus", v51, a9, 0);
                    v14 = v52;
                    if ( v52 > 0 )
                      v14 = (unsigned __int16)v52 | 0x80070000;
                    if ( v14 >= 0 )
                      goto LABEL_76;
                    v50 = L"RegSaveDwordValue";
                  }
                  else
                  {
                    v50 = L"RegReadStringValue";
                  }
                  Logger::TraceError(
                    L"%s: %s failed with error code: 0x%08x.",
                    L"RegistryHelper::ReadJoinDiagnosticInfo",
                    v50,
                    (unsigned int)v14);
LABEL_76:
                  v15 = v63;
                  goto LABEL_77;
                }
              }
            }
          }
        }
      }
      v31 = L"RegReadStringValue";
    }
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistryHelper::ReadJoinDiagnosticInfo",
      v31,
      (unsigned int)v14);
    goto LABEL_77;
  }
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v18, v17) )
  {
    v19 = lpSubKey;
    if ( v77 > 7 )
      v19 = (LPCWSTR *)lpSubKey[0];
    wprintf(
      L"%s: The key was not found, so returning the default values. Key: %s\n",
      L"RegistryHelper::ReadJoinDiagnosticInfo",
      v19);
    CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v21, v20);
    if ( *(_BYTE *)(*CurrentRef + 12LL) )
    {
      v24 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v23);
      if ( *(_QWORD *)(*v24 + 184LL) )
      {
        v26 = lpSubKey;
        if ( v77 > 7 )
          v26 = (LPCWSTR *)lpSubKey[0];
        v27 = CmdOptions::GetCurrentRef(*v24, v25);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v27 + 184LL),
          L"%s: The key was not found, so returning the default values. Key: %s\n",
          L"RegistryHelper::ReadJoinDiagnosticInfo",
          v26);
      }
    }
  }
  v28 = lpSubKey;
  if ( v77 > 7 )
    v28 = (LPCWSTR *)lpSubKey[0];
  Logger::TraceVerbose(
    (wchar_t *)L"%s: The key was not found, so returning the default values. Key: %s\n",
    L"RegistryHelper::ReadJoinDiagnosticInfo",
    v28);
LABEL_77:
  *a1 = *(_QWORD *)v64 / 0x989680uLL - 0x2B6109100LL;
  *a4 = v62;
  v53 = -1;
  if ( lpMem )
  {
    v54 = -1;
    do
      ++v54;
    while ( *((_WORD *)lpMem + v54) );
    std::wstring::_Assign<unsigned short>(a3, lpMem, (char *)v54);
    SafeFree(lpMem);
  }
  if ( v66 )
  {
    v55 = -1;
    do
      ++v55;
    while ( v66[v55] );
    std::wstring::_Assign<unsigned short>(a2, v66, (char *)v55);
    SafeFree(v66);
  }
  if ( v67 )
  {
    v56 = -1;
    do
      ++v56;
    while ( v67[v56] );
    std::wstring::_Assign<unsigned short>(v71, v67, (char *)v56);
    SafeFree(v67);
  }
  if ( v68 )
  {
    v57 = -1;
    do
      ++v57;
    while ( v68[v57] );
    std::wstring::_Assign<unsigned short>(v72, v68, (char *)v57);
    SafeFree(v68);
  }
  if ( v69 )
  {
    v58 = -1;
    do
      ++v58;
    while ( v69[v58] );
    std::wstring::_Assign<unsigned short>(v73, v69, (char *)v58);
    SafeFree(v69);
  }
  if ( v70 )
  {
    v59 = -1;
    do
      ++v59;
    while ( v70[v59] );
    std::wstring::_Assign<unsigned short>(v74, v70, (char *)v59);
    SafeFree(v70);
  }
  if ( v15 )
  {
    do
      ++v53;
    while ( v15[v53] );
    std::wstring::_Assign<unsigned short>(v75, v15, (char *)v53);
    SafeFree(v15);
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate((__int64)lpSubKey);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003caac  push    rbp
0x18003caae  push    rbx
0x18003caaf  push    rsi
0x18003cab0  push    rdi
0x18003cab1  push    r12
0x18003cab3  push    r13
0x18003cab5  push    r14
0x18003cab7  push    r15
0x18003cab9  lea     rbp, [rsp-7]
0x18003cabe  sub     rsp, 0D8h
0x18003cac5  mov     rax, cs:__security_cookie
0x18003cacc  xor     rax, rsp
0x18003cacf  mov     [rbp+3Fh+var_48], rax
0x18003cad3  mov     r15, r9
0x18003cad6  mov     r12, r8
0x18003cad9  mov     r13, rdx
0x18003cadc  mov     r14, rcx
0x18003cadf  mov     rax, [rbp+3Fh+arg_20]
0x18003cae3  mov     [rbp+3Fh+var_90], rax
0x18003cae7  mov     rax, [rbp+3Fh+arg_28]
0x18003caeb  mov     [rbp+3Fh+var_88], rax
0x18003caef  mov     rax, [rbp+3Fh+arg_30]
0x18003caf3  mov     [rbp+3Fh+var_78], rax
0x18003caf7  mov     rax, [rbp+3Fh+arg_38]
0x18003cafe  mov     [rbp+3Fh+var_80], rax
0x18003cb02  mov     rbx, [rbp+3Fh+arg_40]
0x18003cb09  mov     rax, [rbp+3Fh+arg_48]
0x18003cb10  mov     [rbp+3Fh+var_70], rax
0x18003cb14  xor     edi, edi
0x18003cb16  mov     [rsp+110h+hKey], rdi
0x18003cb1b  mov     qword ptr [rsp+110h+var_C8], rdi
0x18003cb20  mov     [rsp+110h+var_D8], edi
0x18003cb24  mov     [rsp+110h+lpMem], rdi
0x18003cb29  mov     [rbp+3Fh+var_B8], rdi
0x18003cb2d  mov     [rbp+3Fh+var_B0], rdi
0x18003cb31  mov     [rbp+3Fh+var_A8], rdi
0x18003cb35  mov     [rbp+3Fh+var_98], rdi
0x18003cb39  mov     [rbp+3Fh+var_A0], rdi
0x18003cb3d  mov     esi, edi
0x18003cb3f  mov     [rsp+110h+var_D0], rdi
0x18003cb44  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x18003cb4b  lea     rcx, [rbp+3Fh+lpSubKey]
0x18003cb4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cb54  nop
0x18003cb55  lea     rdx, [rbp+3Fh+lpSubKey]
0x18003cb59  cmp     [rbp+3Fh+var_50], 7
0x18003cb5e  cmova   rdx, [rbp+3Fh+lpSubKey]; lpSubKey
0x18003cb63  lea     rax, [rsp+110h+hKey]
0x18003cb68  mov     [rsp+110h+phkResult], rax; phkResult
0x18003cb6d  mov     r9d, 20019h; samDesired
0x18003cb73  xor     r8d, r8d; ulOptions
0x18003cb76  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003cb7d  call    cs:__imp_RegOpenKeyExW
0x18003cb83  cmp     eax, 2
0x18003cb86  jnz     loc_18003CC32
0x18003cb8c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003cb91  mov     rcx, [rax]
0x18003cb94  xor     ebx, ebx
0x18003cb96  cmp     [rcx], bl
0x18003cb98  jz      short loc_18003CC0C
0x18003cb9a  lea     r8, [rbp+3Fh+lpSubKey]
0x18003cb9e  cmp     [rbp+3Fh+var_50], 7
0x18003cba3  cmova   r8, [rbp+3Fh+lpSubKey]
0x18003cba8  lea     rdx, aRegistryhelper_2; "RegistryHelper::ReadJoinDiagnosticInfo"
0x18003cbaf  lea     rcx, aSTheKeyWasNotF; "%s: The key was not found, so returning"...
0x18003cbb6  call    wprintf
0x18003cbbb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003cbc0  mov     rcx, [rax]
0x18003cbc3  cmp     [rcx+0Ch], bl
0x18003cbc6  jz      short loc_18003CC0C
0x18003cbc8  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003cbcd  mov     rcx, [rax]
0x18003cbd0  cmp     [rcx+0B8h], rbx
0x18003cbd7  jz      short loc_18003CC0C
0x18003cbd9  lea     rbx, [rbp+3Fh+lpSubKey]
0x18003cbdd  cmp     [rbp+3Fh+var_50], 7
0x18003cbe2  cmova   rbx, [rbp+3Fh+lpSubKey]
0x18003cbe7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003cbec  mov     rcx, [rax]
0x18003cbef  mov     r9, rbx
0x18003cbf2  lea     r8, aRegistryhelper_2; "RegistryHelper::ReadJoinDiagnosticInfo"
0x18003cbf9  lea     rdx, aSTheKeyWasNotF; "%s: The key was not found, so returning"...
0x18003cc00  mov     rcx, [rcx+0B8h]; Stream
0x18003cc07  call    fwprintf_s
0x18003cc0c  lea     r8, [rbp+3Fh+lpSubKey]
0x18003cc10  cmp     [rbp+3Fh+var_50], 7
0x18003cc15  cmova   r8, [rbp+3Fh+lpSubKey]
0x18003cc1a  lea     rdx, aRegistryhelper_2; "RegistryHelper::ReadJoinDiagnosticInfo"
0x18003cc21  lea     rcx, aSTheKeyWasNotF; "%s: The key was not found, so returning"...
0x18003cc28  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003cc2d  jmp     loc_18003CF93
0x18003cc32  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cc36  cmp     [rbp+3Fh+var_50], 7
0x18003cc3b  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cc40  mov     dword ptr [rsp+110h+var_E8], edi; unsigned int
0x18003cc44  lea     rax, [rsp+110h+var_C8]
0x18003cc49  mov     [rsp+110h+phkResult], rax; unsigned int *
0x18003cc4e  lea     r8, aLowtime; "lowTime"
0x18003cc55  xor     edx, edx; unsigned __int16 *
0x18003cc57  mov     rcx, [rsp+110h+hKey]; HKEY
0x18003cc5c  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18003cc61  mov     edi, eax
0x18003cc63  test    eax, eax
0x18003cc65  jle     short loc_18003CC70
0x18003cc67  movzx   edi, ax
0x18003cc6a  or      edi, 80070000h
0x18003cc70  test    edi, edi
0x18003cc72  jns     short loc_18003CC96
0x18003cc74  lea     r8, aRegsavedwordva; "RegSaveDwordValue"
0x18003cc7b  mov     r9d, edi
0x18003cc7e  lea     rdx, aRegistryhelper_2; "RegistryHelper::ReadJoinDiagnosticInfo"
0x18003cc85  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003cc8c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003cc91  jmp     loc_18003CF93
0x18003cc96  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cc9a  cmp     [rbp+3Fh+var_50], 7
0x18003cc9f  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cca4  mov     dword ptr [rsp+110h+var_E8], 0; unsigned int
0x18003ccac  lea     rax, [rsp+110h+var_C8+4]
0x18003ccb1  mov     [rsp+110h+phkResult], rax; unsigned int *
0x18003ccb6  lea     r8, aHightime; "highTime"
0x18003ccbd  xor     edx, edx; unsigned __int16 *
0x18003ccbf  mov     rcx, [rsp+110h+hKey]; HKEY
0x18003ccc4  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18003ccc9  mov     edi, eax
0x18003cccb  test    eax, eax
0x18003cccd  jle     short loc_18003CCD8
0x18003cccf  movzx   edi, ax
0x18003ccd2  or      edi, 80070000h
0x18003ccd8  test    edi, edi
0x18003ccda  js      short loc_18003CC74
0x18003ccdc  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cce0  cmp     [rbp+3Fh+var_50], 7
0x18003cce5  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003ccea  mov     dword ptr [rsp+110h+var_E8], 0; unsigned int
0x18003ccf2  lea     rax, [rsp+110h+var_D8]
0x18003ccf7  mov     [rsp+110h+phkResult], rax; unsigned int *
0x18003ccfc  lea     r8, aHr; "hr"
0x18003cd03  xor     edx, edx; unsigned __int16 *
0x18003cd05  mov     rcx, [rsp+110h+hKey]; HKEY
0x18003cd0a  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18003cd0f  mov     edi, eax
0x18003cd11  test    eax, eax
0x18003cd13  jle     short loc_18003CD1E
0x18003cd15  movzx   edi, ax
0x18003cd18  or      edi, 80070000h
0x18003cd1e  test    edi, edi
0x18003cd20  js      loc_18003CC74
0x18003cd26  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cd2a  cmp     [rbp+3Fh+var_50], 7
0x18003cd2f  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cd34  lea     rax, [rsp+110h+lpMem]
0x18003cd39  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003cd3e  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003cd46  lea     r8, aPhase; "phase"
0x18003cd4d  xor     edx, edx; lpSubKey
0x18003cd4f  mov     rcx, [rsp+110h+hKey]; hkey
0x18003cd54  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003cd59  mov     edi, eax
0x18003cd5b  test    eax, eax
0x18003cd5d  jle     short loc_18003CD68
0x18003cd5f  movzx   edi, ax
0x18003cd62  or      edi, 80070000h
0x18003cd68  test    edi, edi
0x18003cd6a  jns     short loc_18003CD78
0x18003cd6c  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18003cd73  jmp     loc_18003CC7B
0x18003cd78  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cd7c  cmp     [rbp+3Fh+var_50], 7
0x18003cd81  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cd86  lea     rax, [rbp+3Fh+var_B8]
0x18003cd8a  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003cd8f  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003cd97  lea     r8, aRegistrationty; "registrationType"
0x18003cd9e  xor     edx, edx; lpSubKey
0x18003cda0  mov     rcx, [rsp+110h+hKey]; hkey
0x18003cda5  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003cdaa  mov     edi, eax
0x18003cdac  test    eax, eax
0x18003cdae  jle     short loc_18003CDB9
0x18003cdb0  movzx   edi, ax
0x18003cdb3  or      edi, 80070000h
0x18003cdb9  test    edi, edi
0x18003cdbb  js      short loc_18003CD6C
0x18003cdbd  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cdc1  cmp     [rbp+3Fh+var_50], 7
0x18003cdc6  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cdcb  lea     rax, [rbp+3Fh+var_B0]
0x18003cdcf  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003cdd4  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003cddc  lea     r8, aServererrorcod; "serverErrorCode"
0x18003cde3  xor     edx, edx; lpSubKey
0x18003cde5  mov     rcx, [rsp+110h+hKey]; hkey
0x18003cdea  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003cdef  mov     edi, eax
0x18003cdf1  test    eax, eax
0x18003cdf3  jle     short loc_18003CDFE
0x18003cdf5  movzx   edi, ax
0x18003cdf8  or      edi, 80070000h
0x18003cdfe  test    edi, edi
0x18003ce00  js      loc_18003CD6C
0x18003ce06  lea     r9, [rbp+3Fh+lpSubKey]
0x18003ce0a  cmp     [rbp+3Fh+var_50], 7
0x18003ce0f  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003ce14  lea     rax, [rbp+3Fh+var_A8]
0x18003ce18  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003ce1d  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003ce25  lea     r8, aServererrorsub; "serverErrorSubCode"
0x18003ce2c  xor     edx, edx; lpSubKey
0x18003ce2e  mov     rcx, [rsp+110h+hKey]; hkey
0x18003ce33  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003ce38  mov     edi, eax
0x18003ce3a  test    eax, eax
0x18003ce3c  jle     short loc_18003CE47
0x18003ce3e  movzx   edi, ax
0x18003ce41  or      edi, 80070000h
0x18003ce47  test    edi, edi
0x18003ce49  js      loc_18003CD6C
0x18003ce4f  lea     r9, [rbp+3Fh+lpSubKey]
0x18003ce53  cmp     [rbp+3Fh+var_50], 7
0x18003ce58  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003ce5d  lea     rax, [rbp+3Fh+var_A0]
0x18003ce61  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003ce66  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003ce6e  lea     r8, aServermessage; "serverMessage"
0x18003ce75  xor     edx, edx; lpSubKey
0x18003ce77  mov     rcx, [rsp+110h+hKey]; hkey
0x18003ce7c  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003ce81  mov     edi, eax
0x18003ce83  test    eax, eax
0x18003ce85  jle     short loc_18003CE90
0x18003ce87  movzx   edi, ax
0x18003ce8a  or      edi, 80070000h
0x18003ce90  test    edi, edi
0x18003ce92  js      loc_18003CD6C
0x18003ce98  lea     r9, [rbp+3Fh+lpSubKey]
0x18003ce9c  cmp     [rbp+3Fh+var_50], 7
0x18003cea1  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cea6  lea     rax, [rbp+3Fh+var_98]
0x18003ceaa  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003ceaf  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003ceb7  lea     r8, aServeroperatio; "serverOperation"
0x18003cebe  xor     edx, edx; lpSubKey
0x18003cec0  mov     rcx, [rsp+110h+hKey]; hkey
0x18003cec5  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003ceca  mov     edi, eax
0x18003cecc  test    eax, eax
0x18003cece  jle     short loc_18003CED9
0x18003ced0  movzx   edi, ax
0x18003ced3  or      edi, 80070000h
0x18003ced9  test    edi, edi
0x18003cedb  js      loc_18003CD6C
0x18003cee1  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cee5  cmp     [rbp+3Fh+var_50], 7
0x18003ceea  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003ceef  lea     rax, [rsp+110h+var_D0]
0x18003cef4  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18003cef9  mov     dword ptr [rsp+110h+phkResult], 2; dwFlags
0x18003cf01  lea     r8, aRequestid; "requestId"
0x18003cf08  xor     edx, edx; lpSubKey
0x18003cf0a  mov     rcx, [rsp+110h+hKey]; hkey
0x18003cf0f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18003cf14  mov     edi, eax
0x18003cf16  test    eax, eax
0x18003cf18  jle     short loc_18003CF23
0x18003cf1a  movzx   edi, ax
0x18003cf1d  or      edi, 80070000h
0x18003cf23  test    edi, edi
0x18003cf25  jns     short loc_18003CF30
0x18003cf27  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18003cf2e  jmp     short loc_18003CF78
0x18003cf30  lea     r9, [rbp+3Fh+lpSubKey]
0x18003cf34  cmp     [rbp+3Fh+var_50], 7
0x18003cf39  cmova   r9, [rbp+3Fh+lpSubKey]; unsigned __int16 *
0x18003cf3e  mov     dword ptr [rsp+110h+var_E8], 0; unsigned int
0x18003cf46  mov     [rsp+110h+phkResult], rbx; unsigned int *
0x18003cf4b  lea     r8, aHttpstatus; "httpStatus"
0x18003cf52  xor     edx, edx; unsigned __int16 *
0x18003cf54  mov     rcx, [rsp+110h+hKey]; HKEY
0x18003cf59  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18003cf5e  mov     edi, eax
0x18003cf60  test    eax, eax
0x18003cf62  jle     short loc_18003CF6D
0x18003cf64  movzx   edi, ax
0x18003cf67  or      edi, 80070000h
0x18003cf6d  test    edi, edi
0x18003cf6f  jns     short loc_18003CF8E
0x18003cf71  lea     r8, aRegsavedwordva; "RegSaveDwordValue"
0x18003cf78  mov     r9d, edi
0x18003cf7b  lea     rdx, aRegistryhelper_2; "RegistryHelper::ReadJoinDiagnosticInfo"
0x18003cf82  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003cf89  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003cf8e  mov     rsi, [rsp+110h+var_D0]
0x18003cf93  mov     rax, 0D6BF94D5E57A42BDh
0x18003cf9d  mul     qword ptr [rsp+110h+var_C8]
0x18003cfa2  shr     rdx, 17h
0x18003cfa6  mov     rax, 2B6109100h
0x18003cfb0  sub     rdx, rax
0x18003cfb3  mov     [r14], rdx
0x18003cfb6  mov     eax, [rsp+110h+var_D8]
  ... truncated ...
```
