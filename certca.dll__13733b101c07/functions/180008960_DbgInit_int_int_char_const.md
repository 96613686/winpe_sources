# DbgInit(int,int,char const *)

- ea: `0x180008960`
- end: `0x180009186`
- name: `?DbgInit@@YAXHHPEBD@Z`
- size: `2086`
- prototype: `void __fastcall(int, int, const char *)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005010`
- `0x180007da0`
- `0x1800084d0`
- `0x180008590`
- `0x180008610`
- `0x180008900`

## callees

- `0x180006990`
- `0x180008400`
- `0x180008610`
- `0x180008960`
- `0x18000a3b0`
- `0x18000a414`
- `0x18001e964`
- `0x180038262`
- `0x1800382c0`

## import_xrefs

- `msvcrt!getenv` at `0x180008a18`
- `msvcrt!getenv` at `0x180008f05`
- `msvcrt!getenv` at `0x180008a18`
- `msvcrt!getenv` at `0x180008f05`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800089f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800089f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008b2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009015`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008b2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008cd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800090fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008cd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800090fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009106`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009067`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009067`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008ac7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008eb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008ac7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008eb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008c86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008c86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008c22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008c22`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008dea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008e65`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008dea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008e65`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180008db2`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180008e2d`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180008db2`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180008e2d`

## string_xrefs

- `0x180008ab6`: `SYSTEM\CurrentControlSet\Services\CertSvc\Configuration`

## pseudocode

```c
void __fastcall DbgInit(int a1, int a2, const char *a3)
{
  unsigned int v5; // ebx
  char *v6; // rax
  const CHAR *v7; // r14
  const WCHAR *v8; // r15
  unsigned int v9; // r13d
  WCHAR *v10; // r12
  __int64 v11; // r14
  const WCHAR *v12; // r9
  __int64 v13; // rax
  WCHAR *v14; // rcx
  __int64 v15; // r8
  WCHAR v16; // dx
  LSTATUS v17; // eax
  signed int v18; // r14d
  HKEY v19; // rax
  BYTE *v20; // r13
  unsigned int v21; // r14d
  LSTATUS v22; // eax
  int v23; // r15d
  int v24; // eax
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *v26; // r8
  bool v27; // zf
  int v28; // r15d
  unsigned int v29; // ecx
  UINT ACP; // eax
  __int64 v31; // r15
  int v32; // esi
  const CHAR *v33; // r14
  UINT v34; // eax
  __int64 v35; // r15
  int v36; // esi
  char *v37; // rax
  DWORD LastError; // eax
  WCHAR *v39; // rcx
  DWORD v40; // eax
  int CertRegDWValue; // eax
  DWORD v42; // eax
  WCHAR *v43; // rcx
  unsigned int v44; // [rsp+40h] [rbp-198h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-194h] BYREF
  LSTATUS v46; // [rsp+48h] [rbp-190h]
  DWORD cbData; // [rsp+4Ch] [rbp-18Ch] BYREF
  unsigned int v48; // [rsp+50h] [rbp-188h] BYREF
  DWORD Type; // [rsp+54h] [rbp-184h] BYREF
  DWORD v50; // [rsp+58h] [rbp-180h]
  int v51; // [rsp+5Ch] [rbp-17Ch] BYREF
  int pvData; // [rsp+60h] [rbp-178h] BYREF
  int v53; // [rsp+64h] [rbp-174h]
  int v54; // [rsp+68h] [rbp-170h]
  int v55; // [rsp+70h] [rbp-168h]
  int v56; // [rsp+78h] [rbp-160h]
  HLOCAL hMem; // [rsp+80h] [rbp-158h]
  HKEY phkResult; // [rsp+88h] [rbp-150h] BYREF
  const WCHAR *v59; // [rsp+90h] [rbp-148h]
  __int64 v60; // [rsp+98h] [rbp-140h]
  const WCHAR *v61; // [rsp+A0h] [rbp-138h]
  HKEY v62; // [rsp+A8h] [rbp-130h]
  WCHAR *v63; // [rsp+B0h] [rbp-128h]
  char *v64; // [rsp+B8h] [rbp-120h]
  const WCHAR *v65; // [rsp+C0h] [rbp-118h]
  __int64 v66; // [rsp+C8h] [rbp-110h]
  __int64 v67; // [rsp+D0h] [rbp-108h]
  const WCHAR *v68; // [rsp+D8h] [rbp-100h]
  WCHAR *v69; // [rsp+E0h] [rbp-F8h]
  const CHAR *v70; // [rsp+E8h] [rbp-F0h]
  WCHAR WideCharStr[23]; // [rsp+F0h] [rbp-E8h] BYREF
  WCHAR v72; // [rsp+11Eh] [rbp-BAh] BYREF
  WCHAR Value[63]; // [rsp+120h] [rbp-B8h] BYREF
  WCHAR v74; // [rsp+19Eh] [rbp-3Ah] BYREF

  if ( _InterlockedIncrement(&dword_1800C4EF0) != 1 || !a2 && !dword_1800C4440 )
    goto LABEL_93;
  try
  {
    if ( dword_1800C4440 )
    {
      InitializeCriticalSection(&g_DBGCriticalSection);
      g_fDBGCSInit = 1;
      v5 = 0;
      dword_1800C4440 = 0;
    }
    else
    {
      v5 = 0;
    }
    v6 = getenv("CERTSRV_DEBUG");
    v7 = v6;
    if ( v6 )
    {
      v64 = v6;
      ACP = GetACP();
      WideCharStr[0] = 0;
      v31 = -1;
      v32 = MultiByteToWideChar(ACP, 0, v7, -1, WideCharStr, 24);
      v53 = v32;
      if ( !v32 )
      {
        LastError = GetLastError();
        v39 = WideCharStr;
        v63 = WideCharStr;
        while ( *v7 )
        {
          if ( v39 >= &v72 )
          {
            *v39 = 0;
            goto LABEL_44;
          }
          *v39++ = *v7;
          v63 = v39;
          v64 = (char *)++v7;
        }
        *v39 = 0;
        if ( LastError != 122 )
        {
          do
            ++v31;
          while ( WideCharStr[v31] );
          v32 = v31;
          v53 = v31;
        }
      }
LABEL_44:
      if ( v32 )
        v5 = myatolx(WideCharStr);
      goto LABEL_39;
    }
    pvData = 0;
    v51 = 0;
    v44 = 0;
    v48 = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Cryptography\\AutoEnrollment",
           L"Debug",
           0x10u,
           0,
           &pvData,
           &pcbData) )
    {
      pvData = 0;
    }
    pcbData = 4;
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration";
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration",
           L"Debug",
           0x10u,
           0,
           &v51,
           &pcbData) )
    {
      v51 = 0;
    }
    v9 = 0;
    v44 = 0;
    hMem = 0;
    v50 = 0;
    v46 = 0;
    phkResult = 0;
    v10 = 0;
    v68 = 0;
    v61 = 0;
    v62 = 0;
    v11 = 56;
    if ( is_mul_ok(0x38u, 2u) )
    {
      v12 = (const WCHAR *)LocalAlloc(0x40u, 0x70u);
      v61 = v12;
      if ( v12 )
      {
        v13 = 2147483646;
        v67 = 2147483646;
        v65 = L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration";
        v66 = 56;
        v14 = (WCHAR *)v12;
        v59 = v12;
        v15 = 0;
        v60 = 0;
        while ( v11 )
        {
          if ( !v13 )
            goto LABEL_20;
          v16 = *v8;
          if ( !*v8 )
            goto LABEL_20;
          v65 = ++v8;
          *v14++ = v16;
          v59 = v14;
          v66 = --v11;
          v67 = --v13;
          v60 = ++v15;
        }
        v59 = --v14;
        v60 = v15 - 1;
LABEL_20:
        *v14 = 0;
        v10 = (WCHAR *)v12;
        v68 = v12;
        v61 = 0;
        v46 = 0;
        v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20019u, &phkResult);
        v18 = v17;
        v46 = v17;
        if ( v17 )
        {
          CSPrintErrorLineFileData2(0, 0x1FA01B5u, v17, 2);
        }
        else
        {
          v19 = phkResult;
          v62 = phkResult;
          Type = 0;
          cbData = 0;
          v20 = 0;
          v21 = 0;
          v54 = 0;
          hMem = 0;
          v50 = 0;
          while ( 1 )
          {
            v22 = RegQueryValueExW(v19, L"Active", 0, &Type, v20, &cbData);
            v23 = v22;
            if ( v22 )
            {
              CSPrintErrorLineFileData2(L"Active", 0x1B101B5u, v22, 2);
              goto LABEL_24;
            }
            if ( v20 )
            {
              memset_0(&v20[cbData], 0, v21);
              v50 = Type;
              hMem = v20;
              v23 = 0;
              goto LABEL_24;
            }
            if ( Type == 7 || Type == 1 )
            {
              v21 = 4;
              v54 = 4;
              v40 = cbData;
              if ( (cbData & 1) != 0 )
                v21 = 5;
              v54 = v21;
            }
            else
            {
              v40 = cbData;
            }
            v20 = (BYTE *)LocalAlloc(0, v21 + v40);
            if ( !v20 )
              break;
            v19 = v62;
          }
          v23 = -2147024882;
          CSPrintErrorLineFile(0x1CF01B5u, -2147024882);
LABEL_24:
          v24 = myHError(v23);
          v18 = v24;
          v46 = v24;
          if ( v24 )
            CSPrintErrorLineFileData2(L"Active", 0x20701B5u, v24, -2147024894);
          v9 = v44;
        }
LABEL_27:
        LocalFree(v10);
        if ( phkResult )
          RegCloseKey(phkResult);
        v55 = v18;
        if ( v18 == 1 )
        {
          CSPrintErrorLineFileData2(L"S_FALSE == hr", 0x65F01CAu, 1, 0);
        }
        else
        {
          v27 = v18 == 0;
          if ( !v18 )
            goto LABEL_35;
          if ( v18 < 0 )
            goto LABEL_34;
          v18 = (unsigned __int16)v18 | 0x80070000;
          v55 = v18;
          if ( !(_WORD)v18 )
          {
            v18 = -2147418113;
            v55 = -2147418113;
            goto LABEL_79;
          }
        }
        v27 = v18 == 0;
LABEL_34:
        if ( v27 )
        {
LABEL_35:
          if ( v50 == 1 )
          {
            CertRegDWValue = myGetCertRegDWValue((const unsigned __int16 *)hMem, v25, v26, L"Debug", &v44);
            v9 = v44;
            if ( CertRegDWValue )
              v9 = 0;
            v44 = v9;
            LocalFree(hMem);
          }
          else
          {
            LocalFree(hMem);
            hMem = 0;
            CSPrintErrorLineFile(0x37F01B5u, -2147024809);
          }
          goto LABEL_37;
        }
LABEL_79:
        CSPrintErrorLineFileData2(L"Active", 0x22C01B5u, v18, 0);
        CSPrintErrorLineFileData2(0, 0x37701B5u, v18, -2147024894);
LABEL_37:
        v48 = 0;
        if ( a3 )
        {
          v33 = a3 + 1;
          if ( *a3 != 43 )
            v33 = a3;
          v70 = v33;
          v34 = GetACP();
          v56 = 0;
          Value[0] = 0;
          v35 = -1;
          v36 = MultiByteToWideChar(v34, 0, v33, -1, Value, 64);
          v56 = v36;
          if ( !v36 )
          {
            v42 = GetLastError();
            v43 = Value;
            v69 = Value;
            while ( *v33 )
            {
              if ( v43 >= &v74 )
              {
                *v43 = 0;
                goto LABEL_52;
              }
              *v43++ = *v33;
              v69 = v43;
              v70 = ++v33;
            }
            *v43 = 0;
            if ( v42 != 122 )
            {
              do
                ++v35;
              while ( Value[v35] );
              v36 = v35;
              v56 = v35;
            }
LABEL_52:
            if ( !v36 )
              goto LABEL_53;
          }
          pcbData = 4;
          if ( RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Cryptography\\AutoEnrollment",
                 Value,
                 0x10u,
                 0,
                 &v48,
                 &pcbData) )
          {
            v48 = 0;
          }
          else
          {
LABEL_53:
            v5 = v48;
          }
        }
        v5 |= pvData | v51 | v9;
LABEL_39:
        g_dwPrintMask = v5;
        if ( a1 && !g_pfDebugLog )
        {
          v37 = getenv("CERTSRV_LOGFILE");
          DbgOpenLogFile(v37);
        }
        goto LABEL_93;
      }
      v28 = -2147024882;
      v29 = 7012789;
    }
    else
    {
      v28 = -2147024362;
      v29 = 6488501;
    }
    CSPrintErrorLineFile(v29, v28);
    v46 = v28;
    v18 = v28;
    CSPrintErrorLineFile(0x1F201B5u, v28);
    goto LABEL_27;
  }
  catch ( ... )
  {
  }
LABEL_93:
  _InterlockedDecrement(&dword_1800C4EF0);
}

```

## disassembly

```asm
0x180008960  mov     [rsp+arg_0], rbx
0x180008965  mov     [rsp+arg_8], rsi
0x18000896a  push    rdi
0x18000896b  push    r12
0x18000896d  push    r13
0x18000896f  push    r14
0x180008971  push    r15
0x180008973  sub     rsp, 1B0h
0x18000897a  mov     rax, cs:__security_cookie
0x180008981  xor     rax, rsp
0x180008984  mov     [rsp+1D8h+var_38], rax
0x18000898c  mov     rsi, r8
0x18000898f  mov     edi, ecx
0x180008991  mov     eax, 1
0x180008996  lock xadd cs:dword_1800C4EF0, eax
0x18000899e  inc     eax
0x1800089a0  cmp     eax, 1
0x1800089a3  jnz     short loc_1800089B1
0x1800089a5  test    edx, edx
0x1800089a7  jnz     short loc_1800089E5
0x1800089a9  cmp     cs:dword_1800C4440, edx
0x1800089af  jnz     short loc_1800089E5
0x1800089b1  lock dec cs:dword_1800C4EF0
0x1800089b8  mov     rcx, [rsp+1D8h+var_38]
0x1800089c0  xor     rcx, rsp; StackCookie
0x1800089c3  call    __security_check_cookie
0x1800089c8  lea     r11, [rsp+1D8h+var_28]
0x1800089d0  mov     rbx, [r11+30h]
0x1800089d4  mov     rsi, [r11+38h]
0x1800089d8  mov     rsp, r11
0x1800089db  pop     r15
0x1800089dd  pop     r14
0x1800089df  pop     r13
0x1800089e1  pop     r12
0x1800089e3  pop     rdi
0x1800089e4  retn
0x1800089e5  cmp     cs:dword_1800C4440, 0
0x1800089ec  jz      loc_180008F18
0x1800089f2  lea     rcx, ?g_DBGCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800089f9  call    cs:__imp_InitializeCriticalSection
0x1800089ff  mov     cs:?g_fDBGCSInit@@3HA, 1; int g_fDBGCSInit
0x180008a09  xor     ebx, ebx
0x180008a0b  mov     cs:dword_1800C4440, ebx
0x180008a11  lea     rcx, VarName; "CERTSRV_DEBUG"
0x180008a18  call    cs:__imp_getenv
0x180008a1e  mov     r14, rax
0x180008a21  test    rax, rax
0x180008a24  jnz     loc_180008DAA
0x180008a2a  mov     [rsp+1D8h+var_178], ebx
0x180008a2e  mov     [rsp+1D8h+var_17C], ebx
0x180008a32  mov     [rsp+1D8h+var_198], ebx
0x180008a36  mov     [rsp+1D8h+var_188], ebx
0x180008a3a  mov     [rsp+1D8h+var_194], ebx
0x180008a3e  mov     [rsp+1D8h+var_194], 4
0x180008a46  lea     rax, [rsp+1D8h+var_194]
0x180008a4b  mov     [rsp+1D8h+pcbData], rax; pcbData
0x180008a50  lea     rax, [rsp+1D8h+var_178]
0x180008a55  mov     [rsp+1D8h+pvData], rax; pvData
0x180008a5a  mov     [rsp+1D8h+pdwType], rbx; pdwType
0x180008a5f  mov     r9d, 10h; dwFlags
0x180008a65  lea     r8, Value; "Debug"
0x180008a6c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\Auto"...
0x180008a73  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008a7a  call    cs:__imp_RegGetValueW
0x180008a80  test    eax, eax
0x180008a82  jz      short loc_180008A88
0x180008a84  mov     [rsp+1D8h+var_178], ebx
0x180008a88  mov     [rsp+1D8h+var_194], 4
0x180008a90  lea     rax, [rsp+1D8h+var_194]
0x180008a95  mov     [rsp+1D8h+pcbData], rax; pcbData
0x180008a9a  lea     rax, [rsp+1D8h+var_17C]
0x180008a9f  mov     [rsp+1D8h+pvData], rax; pvData
0x180008aa4  mov     [rsp+1D8h+pdwType], rbx; pdwType
0x180008aa9  mov     r9d, 10h; dwFlags
0x180008aaf  lea     r8, Value; "Debug"
0x180008ab6  lea     r15, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ce"...
0x180008abd  mov     rdx, r15; lpSubKey
0x180008ac0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008ac7  call    cs:__imp_RegGetValueW
0x180008acd  test    eax, eax
0x180008acf  jz      short loc_180008AD5
0x180008ad1  mov     [rsp+1D8h+var_17C], ebx
0x180008ad5  mov     r13d, ebx
0x180008ad8  mov     [rsp+1D8h+var_198], ebx
0x180008adc  mov     [rsp+1D8h+hMem], rbx
0x180008ae4  mov     [rsp+1D8h+var_180], ebx
0x180008ae8  mov     [rsp+1D8h+var_190], ebx
0x180008aec  mov     [rsp+1D8h+phkResult], rbx
0x180008af4  mov     r12, rbx
0x180008af7  mov     [rsp+1D8h+var_100], rbx
0x180008aff  mov     [rsp+1D8h+var_138], rbx
0x180008b07  mov     [rsp+1D8h+var_130], rbx
0x180008b0f  mov     eax, 2
0x180008b14  mov     r14d, 38h ; '8'
0x180008b1a  mul     r14
0x180008b1d  test    rdx, rdx
0x180008b20  jnz     loc_180008D7D
0x180008b26  mov     rdx, rax; uBytes
0x180008b29  mov     ecx, 40h ; '@'; uFlags
0x180008b2e  call    cs:__imp_LocalAlloc
0x180008b34  mov     r9, rax
0x180008b37  mov     [rsp+1D8h+var_138], rax
0x180008b3f  test    rax, rax
0x180008b42  jz      loc_180008F9A
0x180008b48  mov     eax, 7FFFFFFEh
0x180008b4d  mov     [rsp+1D8h+var_108], rax
0x180008b55  mov     [rsp+1D8h+var_118], r15
0x180008b5d  mov     [rsp+1D8h+var_110], r14
0x180008b65  mov     rcx, r9
0x180008b68  mov     [rsp+1D8h+var_148], rcx
0x180008b70  mov     r8, rbx
0x180008b73  mov     [rsp+1D8h+var_140], rbx
0x180008b7b  nop     dword ptr [rax+rax+00h]
0x180008b80  test    r14, r14
0x180008b83  jz      short loc_180008BD1
0x180008b85  test    rax, rax
0x180008b88  jz      short loc_180008BE8
0x180008b8a  movzx   edx, word ptr [r15]
0x180008b8e  test    dx, dx
0x180008b91  jz      short loc_180008BE8
0x180008b93  add     r15, 2
0x180008b97  mov     [rsp+1D8h+var_118], r15
0x180008b9f  mov     [rcx], dx
0x180008ba2  add     rcx, 2
0x180008ba6  mov     [rsp+1D8h+var_148], rcx
0x180008bae  dec     r14
0x180008bb1  mov     [rsp+1D8h+var_110], r14
0x180008bb9  dec     rax
0x180008bbc  mov     [rsp+1D8h+var_108], rax
0x180008bc4  inc     r8
0x180008bc7  mov     [rsp+1D8h+var_140], r8
0x180008bcf  jmp     short loc_180008B80
0x180008bd1  sub     rcx, 2
0x180008bd5  mov     [rsp+1D8h+var_148], rcx
0x180008bdd  dec     r8
0x180008be0  mov     [rsp+1D8h+var_140], r8
0x180008be8  mov     [rcx], bx
0x180008beb  mov     r12, r9
0x180008bee  mov     [rsp+1D8h+var_100], r9
0x180008bf6  mov     [rsp+1D8h+var_138], rbx
0x180008bfe  mov     [rsp+1D8h+var_190], ebx
0x180008c02  lea     rax, [rsp+1D8h+phkResult]
0x180008c0a  mov     [rsp+1D8h+pdwType], rax; phkResult
0x180008c0f  mov     r9d, 20019h; samDesired
0x180008c15  xor     r8d, r8d; ulOptions
0x180008c18  mov     rdx, r12; lpSubKey
0x180008c1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008c22  call    cs:__imp_RegOpenKeyExW
0x180008c28  mov     r14d, eax
0x180008c2b  mov     [rsp+1D8h+var_190], eax
0x180008c2f  test    eax, eax
0x180008c31  jnz     loc_180008EC9
0x180008c37  mov     rax, [rsp+1D8h+phkResult]
0x180008c3f  mov     [rsp+1D8h+var_130], rax
0x180008c47  mov     [rsp+1D8h+Type], ebx
0x180008c4b  mov     [rsp+1D8h+cbData], ebx
0x180008c4f  mov     r13, rbx
0x180008c52  mov     r14d, ebx
0x180008c55  mov     [rsp+1D8h+var_170], ebx
0x180008c59  mov     [rsp+1D8h+hMem], rbx
0x180008c61  mov     [rsp+1D8h+var_180], ebx
0x180008c65  lea     rcx, [rsp+1D8h+cbData]
0x180008c6a  mov     [rsp+1D8h+pvData], rcx; lpcbData
0x180008c6f  mov     [rsp+1D8h+pdwType], r13; lpData
0x180008c74  lea     r9, [rsp+1D8h+Type]; lpType
0x180008c79  xor     r8d, r8d; lpReserved
0x180008c7c  lea     rdx, aActive; "Active"
0x180008c83  mov     rcx, rax; hKey
0x180008c86  call    cs:__imp_RegQueryValueExW
0x180008c8c  mov     r15d, eax
0x180008c8f  test    eax, eax
0x180008c91  jz      loc_180008FAA
0x180008c97  mov     r9d, 2; int
0x180008c9d  mov     r8d, eax; int
0x180008ca0  mov     edx, 1B101B5h; unsigned int
0x180008ca5  lea     rcx, aActive; "Active"
0x180008cac  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180008cb1  mov     ecx, r15d; int
0x180008cb4  call    ?myHError@@YAJJ@Z; myHError(long)
0x180008cb9  mov     r14d, eax
0x180008cbc  mov     [rsp+1D8h+var_190], eax
0x180008cc0  test    eax, eax
0x180008cc2  jnz     loc_18000903B
0x180008cc8  mov     r13d, [rsp+1D8h+var_198]
0x180008ccd  mov     rcx, r12; hMem
0x180008cd0  call    cs:__imp_LocalFree
0x180008cd6  mov     rcx, [rsp+1D8h+phkResult]; hKey
0x180008cde  test    rcx, rcx
0x180008ce1  jnz     loc_180009067
0x180008ce7  mov     [rsp+1D8h+var_168], r14d
0x180008cec  cmp     r14d, 1
0x180008cf0  jz      loc_180009072
0x180008cf6  test    r14d, r14d
0x180008cf9  jz      short loc_180008D22
0x180008cfb  js      short loc_180008D1C
0x180008cfd  jle     short loc_180008D0A
0x180008cff  movzx   r14d, r14w
0x180008d03  or      r14d, 80070000h
0x180008d0a  mov     [rsp+1D8h+var_168], r14d
0x180008d0f  test    r14w, r14w
0x180008d13  jz      loc_180009091
0x180008d19  test    r14d, r14d
0x180008d1c  jnz     loc_18000909C
0x180008d22  mov     rcx, [rsp+1D8h+hMem]; unsigned __int16 *
0x180008d2a  cmp     [rsp+1D8h+var_180], 1
0x180008d2f  jz      loc_1800090CD
0x180008d35  call    cs:__imp_LocalFree
0x180008d3b  mov     [rsp+1D8h+hMem], rbx
0x180008d43  mov     edx, 80070057h; int
0x180008d48  mov     ecx, 37F01B5h; unsigned int
0x180008d4d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180008d52  mov     [rsp+1D8h+var_188], ebx
0x180008d56  test    rsi, rsi
0x180008d59  jnz     loc_180008E1A
0x180008d5f  or      ebx, r13d
0x180008d62  or      ebx, [rsp+1D8h+var_17C]
0x180008d66  or      ebx, [rsp+1D8h+var_178]
0x180008d6a  mov     cs:?g_dwPrintMask@@3KA, ebx; ulong g_dwPrintMask
0x180008d70  test    edi, edi
0x180008d72  jnz     loc_180008EF0
0x180008d78  jmp     loc_1800089B1
0x180008d7d  mov     r15d, 80070216h
0x180008d83  mov     ecx, 6301B5h; unsigned int
0x180008d88  mov     edx, r15d; int
0x180008d8b  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180008d90  mov     [rsp+1D8h+var_190], r15d
0x180008d95  mov     r14d, r15d
0x180008d98  mov     edx, r15d; int
0x180008d9b  mov     ecx, 1F201B5h; unsigned int
0x180008da0  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180008da5  jmp     loc_180008CCD
0x180008daa  mov     [rsp+1D8h+var_120], r14
0x180008db2  call    cs:__imp_GetACP
0x180008db8  mov     [rsp+1D8h+var_174], ebx
0x180008dbc  mov     [rsp+1D8h+WideCharStr], bx
0x180008dc4  mov     dword ptr [rsp+1D8h+pvData], 18h; cchWideChar
0x180008dcc  lea     rcx, [rsp+1D8h+WideCharStr]
0x180008dd4  mov     [rsp+1D8h+pdwType], rcx; lpWideCharStr
0x180008dd9  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180008de0  mov     r9d, r15d; cbMultiByte
0x180008de3  mov     r8, r14; lpMultiByteStr
0x180008de6  xor     edx, edx; dwFlags
0x180008de8  mov     ecx, eax; CodePage
0x180008dea  call    cs:__imp_MultiByteToWideChar
0x180008df0  mov     esi, eax
0x180008df2  mov     [rsp+1D8h+var_174], eax
0x180008df6  test    eax, eax
0x180008df8  jz      loc_180008F1F
0x180008dfe  test    esi, esi
0x180008e00  jz      loc_180008D6A
0x180008e06  lea     rcx, [rsp+1D8h+WideCharStr]; unsigned __int16 *
0x180008e0e  call    ?myatolx@@YAKPEBG@Z; myatolx(ushort const *)
0x180008e13  mov     ebx, eax
0x180008e15  jmp     loc_180008D6A
0x180008e1a  lea     r14, [rsi+1]
0x180008e1e  cmp     byte ptr [rsi], 2Bh ; '+'
0x180008e21  cmovnz  r14, rsi
0x180008e25  mov     [rsp+1D8h+var_F0], r14
0x180008e2d  call    cs:__imp_GetACP
0x180008e33  mov     [rsp+1D8h+var_160], ebx
0x180008e37  mov     [rsp+1D8h+Value], bx
0x180008e3f  mov     dword ptr [rsp+1D8h+pvData], 40h ; '@'; cchWideChar
0x180008e47  lea     rcx, [rsp+1D8h+Value]
0x180008e4f  mov     [rsp+1D8h+pdwType], rcx; lpWideCharStr
0x180008e54  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180008e5b  mov     r9d, r15d; cbMultiByte
0x180008e5e  mov     r8, r14; lpMultiByteStr
0x180008e61  xor     edx, edx; dwFlags
0x180008e63  mov     ecx, eax; CodePage
0x180008e65  call    cs:__imp_MultiByteToWideChar
0x180008e6b  mov     esi, eax
0x180008e6d  mov     [rsp+1D8h+var_160], eax
0x180008e71  test    eax, eax
0x180008e73  jz      loc_180009106
0x180008e79  mov     [rsp+1D8h+var_194], 4
0x180008e81  lea     rax, [rsp+1D8h+var_194]
0x180008e86  mov     [rsp+1D8h+pcbData], rax; pcbData
0x180008e8b  lea     rax, [rsp+1D8h+var_188]
0x180008e90  mov     [rsp+1D8h+pvData], rax; pvData
0x180008e95  mov     [rsp+1D8h+pdwType], rbx; pdwType
0x180008e9a  mov     r9d, 10h; dwFlags
0x180008ea0  lea     r8, [rsp+1D8h+Value]; lpValue
0x180008ea8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\Auto"...
0x180008eaf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008eb6  call    cs:__imp_RegGetValueW
0x180008ebc  test    eax, eax
0x180008ebe  jz      short loc_180008EE7
0x180008ec0  mov     [rsp+1D8h+var_188], ebx
0x180008ec4  jmp     loc_180008D5F
0x180008ec9  mov     r9d, 2; int
0x180008ecf  mov     r8d, eax; int
0x180008ed2  mov     edx, 1FA01B5h; unsigned int
0x180008ed7  xor     ecx, ecx; unsigned __int16 *
0x180008ed9  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180008ede  jmp     loc_180008CCD
0x180008ee3  test    esi, esi
0x180008ee5  jnz     short loc_180008E79
0x180008ee7  mov     ebx, [rsp+1D8h+var_188]
0x180008eeb  jmp     loc_180008D5F
0x180008ef0  cmp     cs:?g_pfDebugLog@@3PEAU_iobuf@@EA, 0; _iobuf * g_pfDebugLog
  ... truncated ...
```
