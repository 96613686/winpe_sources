# CflApiNew::ClearScenarioDataWithReason

- ea: `0x1800286d4`
- end: `0x180028cbe`
- name: `CflApiNew::ClearScenarioDataWithReason`
- size: `1514`
- prototype: `__int64 __fastcall(char *, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ffb0`
- `0x18002ba10`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x180010700`
- `0x18001332c`
- `0x18001f8e4`
- `0x18001f948`
- `0x18002222c`
- `0x1800286d4`
- `0x18002dff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028c37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028c37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800287dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002887c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800287dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002887c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028ad8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028b25`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028b76`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028bc7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028ad8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028b25`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028b76`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028bc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002872b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002872b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002876f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002899b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028c2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002876f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002899b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028c2f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180028891`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180028891`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180028a86`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180028c56`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180028c91`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180028a86`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180028c56`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180028c91`

## string_xrefs

- `0x1800288d0`: `Unexpected ScenarioDataClearReason (reason: %u)`
- `0x180028759`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x1800288e2`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028981`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x1800289b2`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x1800289f0`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028a2e`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028ab1`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028aff`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028b4c`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028b9d`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180028bee`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CflApiNew::ClearScenarioDataWithReason(char *a1, _QWORD *a2)
{
  int v3; // edi
  LSTATUS v4; // eax
  signed int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rdx
  char v9; // si
  LSTATUS ValueW; // eax
  int v11; // eax
  PVOID v12; // rbx
  unsigned int v13; // eax
  HRESULT v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // edi
  int v17; // eax
  bool v18; // dl
  LSTATUS v19; // eax
  int v20; // r14d
  unsigned int v21; // r15d
  unsigned __int64 v22; // r9
  LSTATUS v23; // eax
  int v24; // r14d
  unsigned int v25; // r15d
  unsigned __int64 v26; // r9
  LSTATUS v27; // eax
  int v28; // r14d
  unsigned int v29; // r15d
  unsigned __int64 v30; // r9
  LSTATUS v31; // eax
  int v32; // r14d
  unsigned int v33; // r15d
  unsigned __int64 v34; // r9
  HKEY v35; // r14
  DWORD LastError; // ebx
  LSTATUS v37; // eax
  LSTATUS v38; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  const char *pvData; // [rsp+28h] [rbp-58h]
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-38h] BYREF
  DWORD pdwType; // [rsp+4Ch] [rbp-34h] BYREF
  PVOID Buf2[2]; // [rsp+50h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v3 = (int)a1;
  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData",
         0,
         3u,
         &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_8;
      v6 = 1300;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v5,
        phkResult);
LABEL_8:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v5;
    }
    if ( v3 == 2 )
    {
      v8 = 1305;
LABEL_38:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Expected scenario data ownership to have been set",
        pvData);
      goto LABEL_39;
    }
    goto LABEL_33;
  }
  pclsid = 0;
  v9 = 1;
  if ( v3 == 1 )
    goto LABEL_56;
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hKey, 0, L"ProviderId", 2u, &pdwType, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        v5 = (unsigned __int16)ValueW | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_8;
      v6 = 1330;
      goto LABEL_7;
    }
    goto LABEL_28;
  }
  if ( pdwType != 1 )
  {
    v5 = -2147024809;
    v6 = 1335;
    goto LABEL_7;
  }
  if ( !pcbData || (pcbData & 1) != 0 )
  {
    v5 = -2147024872;
    v6 = 1338;
    goto LABEL_7;
  }
  Buf2[0] = 0;
  v11 = CflApiNew::AllocBuffer_unsigned_short_((unsigned __int64)pcbData >> 1, Buf2);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53D,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v11,
      phkResult);
    if ( Buf2[0] )
      CflFreeBuffer(Buf2[0]);
    goto LABEL_8;
  }
  v12 = Buf2[0];
  v13 = RegGetValueW(hKey, 0, L"ProviderId", 2u, 0, Buf2[0], &pcbData);
  if ( v13 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x546,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
            (const char *)v13,
            phkResult);
    if ( v12 )
      CflFreeBuffer(v12);
    if ( hKey )
      RegCloseKey(hKey);
    return v16;
  }
  else
  {
    v14 = CLSIDFromString((LPCOLESTR)v12, &pclsid);
    v15 = v14;
    if ( v14 >= 0 )
    {
      if ( v12 )
        CflFreeBuffer(v12);
LABEL_28:
      if ( v3 == 2 )
      {
        *(_OWORD *)Buf2 = 0;
        if ( !memcmp_0(&pclsid, Buf2, 0x10u) )
        {
          v8 = 1373;
          goto LABEL_38;
        }
LABEL_57:
        v17 = RegDeleteKeyW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData");
        v18 = (v17 & 0xFFFFFFFD) != 0;
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        if ( v18 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x56B,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
            (const char *)(unsigned int)v17,
            phkResult);
        if ( v9 )
        {
          v5 = 0;
          v19 = RegDeleteValueW(hKey, L"AuthBuffer");
          v20 = v19;
          v21 = (unsigned __int16)v19 | 0x80070000;
          v22 = v21;
          if ( v19 <= 0 )
            v22 = (unsigned int)v19;
          if ( (v19 & 0xFFFFFFFD) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x574,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v22,
              phkResult);
            v5 = v21;
            if ( v20 <= 0 )
              v5 = v20;
          }
          v23 = RegDeleteValueW(hKey, L"ScenarioId");
          v24 = v23;
          v25 = (unsigned __int16)v23 | 0x80070000;
          v26 = v25;
          if ( v23 <= 0 )
            v26 = (unsigned int)v23;
          if ( (v23 & 0xFFFFFFFD) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x57D,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v26,
              phkResult);
            if ( v5 >= 0 )
            {
              v5 = v25;
              if ( v24 <= 0 )
                v5 = v24;
            }
          }
          v27 = RegDeleteValueW(hKey, L"ScenarioContext");
          v28 = v27;
          v29 = (unsigned __int16)v27 | 0x80070000;
          v30 = v29;
          if ( v27 <= 0 )
            v30 = (unsigned int)v27;
          if ( (v27 & 0xFFFFFFFD) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x586,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v30,
              phkResult);
            if ( v5 >= 0 )
            {
              v5 = v29;
              if ( v28 <= 0 )
                v5 = v28;
            }
          }
          v31 = RegDeleteValueW(hKey, L"LastSessionId");
          v32 = v31;
          v33 = (unsigned __int16)v31 | 0x80070000;
          v34 = v33;
          if ( v31 <= 0 )
            v34 = (unsigned int)v31;
          if ( (v31 & 0xFFFFFFFD) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x58F,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
              (const char *)v34,
              phkResult);
            if ( v5 < 0 )
            {
LABEL_86:
              v6 = 1431;
              goto LABEL_7;
            }
            v5 = v33;
            if ( v32 <= 0 )
              v5 = v32;
          }
          if ( v5 < 0 )
            goto LABEL_86;
        }
        v35 = hKey;
        if ( hKey )
        {
          LastError = GetLastError();
          RegCloseKey(v35);
          SetLastError(LastError);
        }
        hKey = 0;
        v37 = RegDeleteKeyW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData\\ProtectedData");
        v5 = v37;
        if ( (v37 & 0xFFFFFFFD) != 0 )
        {
          if ( v37 > 0 )
            v5 = (unsigned __int16)v37 | 0x80070000;
          if ( v5 >= 0 )
            goto LABEL_8;
          v6 = 1438;
          goto LABEL_7;
        }
        if ( !v9 )
        {
          v38 = RegDeleteKeyW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData");
          v5 = v38;
          if ( (v38 & 0xFFFFFFFD) != 0 )
          {
            if ( v38 > 0 )
              v5 = (unsigned __int16)v38 | 0x80070000;
            if ( v5 >= 0 )
              goto LABEL_8;
            v6 = 1445;
            goto LABEL_7;
          }
        }
LABEL_33:
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
      if ( v3 != 3 )
      {
        LODWORD(pvData) = v3;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x562,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unexpected ScenarioDataClearReason (reason: %u)",
          pvData);
LABEL_39:
        if ( hKey )
          RegCloseKey(hKey);
        return 2147549183LL;
      }
      if ( *a2 != *(_QWORD *)&pclsid.Data1 || a2[1] != *(_QWORD *)pclsid.Data4 )
        goto LABEL_33;
LABEL_56:
      v9 = 0;
      goto LABEL_57;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x548,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v14,
      phkResult);
    if ( v12 )
      CflFreeBuffer(v12);
    if ( hKey )
      RegCloseKey(hKey);
    return v15;
  }
}

```

## disassembly

```asm
0x1800286d4  mov     [rsp-28h+arg_8], rbx
0x1800286d9  mov     [rsp-28h+arg_10], rsi
0x1800286de  push    rbp
0x1800286df  push    rdi
0x1800286e0  push    r13
0x1800286e2  push    r14
0x1800286e4  push    r15
0x1800286e6  mov     rbp, rsp
0x1800286e9  sub     rsp, 80h
0x1800286f0  mov     rax, cs:__security_cookie
0x1800286f7  xor     rax, rsp
0x1800286fa  mov     [rbp+var_10], rax
0x1800286fe  mov     r15, rdx
0x180028701  mov     edi, ecx
0x180028703  mov     [rbp+hKey], 0
0x18002870b  lea     rax, [rbp+hKey]
0x18002870f  mov     [rsp+80h+phkResult], rax; int
0x180028714  mov     r9d, 3; samDesired
0x18002871a  xor     r8d, r8d; ulOptions
0x18002871d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180028724  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002872b  call    cs:__imp_RegOpenKeyExW
0x180028731  mov     ebx, eax
0x180028733  test    eax, eax
0x180028735  jz      short loc_18002878F
0x180028737  cmp     eax, 2
0x18002873a  jz      short loc_18002877C
0x18002873c  test    eax, eax
0x18002873e  jle     short loc_180028749
0x180028740  movzx   ebx, ax
0x180028743  or      ebx, 80070000h
0x180028749  test    ebx, ebx
0x18002874b  jns     short loc_180028766
0x18002874d  mov     edx, 514h; void *
0x180028752  mov     rcx, [rbp+28h]; this
0x180028756  mov     r9d, ebx; char *
0x180028759  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180028760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028765  nop
0x180028766  mov     rcx, [rbp+hKey]; hKey
0x18002876a  test    rcx, rcx
0x18002876d  jz      short loc_180028775
0x18002876f  call    cs:__imp_RegCloseKey
0x180028775  mov     eax, ebx
0x180028777  jmp     loc_180028920
0x18002877c  cmp     edi, 2
0x18002877f  jnz     loc_18002890F
0x180028785  mov     edx, 519h
0x18002878a  jmp     loc_18002896F
0x18002878f  xorps   xmm0, xmm0
0x180028792  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180028796  mov     esi, 1
0x18002879b  cmp     edi, esi
0x18002879d  jz      loc_180028A75
0x1800287a3  mov     [rbp+pdwType], 0
0x1800287aa  mov     [rbp+var_38], 0
0x1800287b1  lea     rax, [rbp+var_38]
0x1800287b5  mov     [rsp+80h+pcbData], rax; pcbData
0x1800287ba  mov     [rsp+80h+pvData], 0; pvData
0x1800287c3  lea     rax, [rbp+pdwType]
0x1800287c7  mov     [rsp+80h+phkResult], rax; int
0x1800287cc  lea     r9d, [rsi+1]; dwFlags
0x1800287d0  lea     r8, Value; "ProviderId"
0x1800287d7  xor     edx, edx; lpSubKey
0x1800287d9  mov     rcx, [rbp+hKey]; hkey
0x1800287dd  call    cs:__imp_RegGetValueW
0x1800287e3  mov     ebx, eax
0x1800287e5  test    eax, eax
0x1800287e7  jz      short loc_180028811
0x1800287e9  cmp     eax, 2
0x1800287ec  jz      loc_1800288AF
0x1800287f2  test    eax, eax
0x1800287f4  jle     short loc_1800287FF
0x1800287f6  movzx   ebx, ax
0x1800287f9  or      ebx, 80070000h
0x1800287ff  test    ebx, ebx
0x180028801  jns     loc_180028766
0x180028807  mov     edx, 532h
0x18002880c  jmp     loc_180028752
0x180028811  cmp     [rbp+pdwType], esi
0x180028814  jnz     loc_180028A66
0x18002881a  mov     eax, [rbp+var_38]
0x18002881d  test    eax, eax
0x18002881f  jz      loc_180028A57
0x180028825  test    sil, al
0x180028828  jnz     loc_180028A57
0x18002882e  mov     [rbp+Buf2], 0
0x180028836  mov     ecx, eax
0x180028838  shr     rcx, 1
0x18002883b  lea     rdx, [rbp+Buf2]
0x18002883f  call    CflApiNew__AllocBuffer_unsigned_short_
0x180028844  mov     ebx, eax
0x180028846  test    eax, eax
0x180028848  js      loc_180028A27
0x18002884e  lea     rax, [rbp+var_38]
0x180028852  mov     [rsp+80h+pcbData], rax; pcbData
0x180028857  mov     rbx, [rbp+Buf2]
0x18002885b  mov     [rsp+80h+pvData], rbx; char *
0x180028860  mov     [rsp+80h+phkResult], 0; unsigned int
0x180028869  mov     r9d, 2; dwFlags
0x18002886f  lea     r8, Value; "ProviderId"
0x180028876  xor     edx, edx; lpSubKey
0x180028878  mov     rcx, [rbp+hKey]; hkey
0x18002887c  call    cs:__imp_RegGetValueW
0x180028882  test    eax, eax
0x180028884  jnz     loc_1800289E9
0x18002888a  lea     rdx, [rbp+pclsid]; pclsid
0x18002888e  mov     rcx, rbx; lpsz
0x180028891  call    cs:__imp_CLSIDFromString
0x180028897  mov     r14d, eax
0x18002889a  test    eax, eax
0x18002889c  js      loc_1800289AB
0x1800288a2  test    rbx, rbx
0x1800288a5  jz      short loc_1800288AF
0x1800288a7  mov     rcx, rbx; hMem
0x1800288aa  call    CflFreeBuffer
0x1800288af  mov     ecx, edi
0x1800288b1  sub     ecx, 1
0x1800288b4  jz      loc_180028A75
0x1800288ba  sub     ecx, 1
0x1800288bd  jz      loc_180028948
0x1800288c3  cmp     ecx, 1
0x1800288c6  jz      short loc_1800288F8
0x1800288c8  mov     rcx, [rbp+28h]; this
0x1800288cc  mov     dword ptr [rsp+80h+pvData], edi; char *
0x1800288d0  lea     rax, aUnexpectedScen; "Unexpected ScenarioDataClearReason (rea"...
0x1800288d7  mov     [rsp+80h+phkResult], rax; int
0x1800288dc  mov     r9d, 8000FFFFh; char *
0x1800288e2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800288e9  mov     edx, 562h; void *
0x1800288ee  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800288f3  jmp     loc_180028992
0x1800288f8  mov     rax, [r15]
0x1800288fb  cmp     rax, qword ptr [rbp+pclsid.Data1]
0x1800288ff  jnz     short loc_18002890F
0x180028901  mov     rax, [r15+8]
0x180028905  cmp     rax, qword ptr [rbp+pclsid.Data4]
0x180028909  jz      loc_180028A75
0x18002890f  mov     rcx, [rbp+hKey]; hKey
0x180028913  test    rcx, rcx
0x180028916  jz      short loc_18002891E
0x180028918  call    cs:__imp_RegCloseKey
0x18002891e  xor     eax, eax
0x180028920  mov     rcx, [rbp+var_10]
0x180028924  xor     rcx, rsp; StackCookie
0x180028927  call    __security_check_cookie
0x18002892c  lea     r11, [rsp+80h+var_s0]
0x180028934  mov     rbx, [r11+38h]
0x180028938  mov     rsi, [r11+40h]
0x18002893c  mov     rsp, r11
0x18002893f  pop     r15
0x180028941  pop     r14
0x180028943  pop     r13
0x180028945  pop     rdi
0x180028946  pop     rbp
0x180028947  retn
0x180028948  xorps   xmm0, xmm0
0x18002894b  movups  xmmword ptr [rbp+Buf2], xmm0
0x18002894f  mov     r8d, 10h; Size
0x180028955  lea     rdx, [rbp+Buf2]; Buf2
0x180028959  lea     rcx, [rbp+pclsid]; Buf1
0x18002895d  call    memcmp_0
0x180028962  test    eax, eax
0x180028964  jnz     loc_180028A78
0x18002896a  mov     edx, 55Dh; void *
0x18002896f  lea     rax, aExpectedScenar; "Expected scenario data ownership to hav"...
0x180028976  mov     [rsp+80h+phkResult], rax; int
0x18002897b  mov     r9d, 8000FFFFh; char *
0x180028981  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180028988  mov     rcx, [rbp+28h]; this
0x18002898c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028991  nop
0x180028992  mov     rcx, [rbp+hKey]; hKey
0x180028996  test    rcx, rcx
0x180028999  jz      short loc_1800289A1
0x18002899b  call    cs:__imp_RegCloseKey
0x1800289a1  mov     eax, 8000FFFFh
0x1800289a6  jmp     loc_180028920
0x1800289ab  mov     rcx, [rbp+28h]; this
0x1800289af  mov     r9d, r14d; char *
0x1800289b2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800289b9  mov     edx, 548h; void *
0x1800289be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800289c3  nop
0x1800289c4  test    rbx, rbx
0x1800289c7  jz      short loc_1800289D2
0x1800289c9  mov     rcx, rbx; hMem
0x1800289cc  call    CflFreeBuffer
0x1800289d1  nop
0x1800289d2  mov     rcx, [rbp+hKey]; hKey
0x1800289d6  test    rcx, rcx
0x1800289d9  jz      short loc_1800289E1
0x1800289db  call    cs:__imp_RegCloseKey
0x1800289e1  mov     eax, r14d
0x1800289e4  jmp     loc_180028920
0x1800289e9  mov     rcx, [rbp+28h]; this
0x1800289ed  mov     r9d, eax; char *
0x1800289f0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800289f7  mov     edx, 546h; void *
0x1800289fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028a01  mov     edi, eax
0x180028a03  test    rbx, rbx
0x180028a06  jz      short loc_180028A11
0x180028a08  mov     rcx, rbx; hMem
0x180028a0b  call    CflFreeBuffer
0x180028a10  nop
0x180028a11  mov     rcx, [rbp+hKey]; hKey
0x180028a15  test    rcx, rcx
0x180028a18  jz      short loc_180028A20
0x180028a1a  call    cs:__imp_RegCloseKey
0x180028a20  mov     eax, edi
0x180028a22  jmp     loc_180028920
0x180028a27  mov     rcx, [rbp+28h]; this
0x180028a2b  mov     r9d, ebx; char *
0x180028a2e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180028a35  mov     edx, 53Dh; void *
0x180028a3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a3f  nop
0x180028a40  mov     rcx, [rbp+Buf2]; hMem
0x180028a44  test    rcx, rcx
0x180028a47  jz      loc_180028766
0x180028a4d  call    CflFreeBuffer
0x180028a52  jmp     loc_180028766
0x180028a57  mov     ebx, 80070018h
0x180028a5c  mov     edx, 53Ah
0x180028a61  jmp     loc_180028752
0x180028a66  mov     ebx, 80070057h
0x180028a6b  mov     edx, 537h
0x180028a70  jmp     loc_180028752
0x180028a75  xor     sil, sil
0x180028a78  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180028a7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028a86  call    cs:__imp_RegDeleteKeyW
0x180028a8c  mov     r13d, 0FFFFFFFDh
0x180028a92  test    r13d, eax
0x180028a95  setnz   dl
0x180028a98  mov     edi, 80070000h
0x180028a9d  test    eax, eax
0x180028a9f  jle     short loc_180028AA6
0x180028aa1  movzx   eax, ax
0x180028aa4  or      eax, edi
0x180028aa6  mov     rcx, [rbp+28h]; this
0x180028aaa  test    dl, dl
0x180028aac  jz      short loc_180028AC2
0x180028aae  mov     r9d, eax; char *
0x180028ab1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180028ab8  mov     edx, 56Bh; void *
0x180028abd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028ac2  test    sil, sil
0x180028ac5  jz      loc_180028C1B
0x180028acb  xor     ebx, ebx
0x180028acd  lea     rdx, aAuthbuffer; "AuthBuffer"
0x180028ad4  mov     rcx, [rbp+hKey]; hKey
0x180028ad8  call    cs:__imp_RegDeleteValueW
0x180028ade  mov     r14d, eax
0x180028ae1  test    r13d, eax
0x180028ae4  setnz   dl
0x180028ae7  movzx   r15d, ax
0x180028aeb  or      r15d, edi
0x180028aee  mov     r9d, r15d
0x180028af1  test    eax, eax
0x180028af3  cmovle  r9d, eax; char *
0x180028af7  mov     rcx, [rbp+28h]; this
0x180028afb  test    dl, dl
0x180028afd  jz      short loc_180028B1A
0x180028aff  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180028b06  mov     edx, 574h; void *
0x180028b0b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028b10  mov     ebx, r15d
0x180028b13  test    r14d, r14d
0x180028b16  cmovle  ebx, r14d
0x180028b1a  lea     rdx, aScenarioid; "ScenarioId"
0x180028b21  mov     rcx, [rbp+hKey]; hKey
0x180028b25  call    cs:__imp_RegDeleteValueW
0x180028b2b  mov     r14d, eax
0x180028b2e  test    r13d, eax
0x180028b31  setnz   dl
0x180028b34  movzx   r15d, ax
0x180028b38  or      r15d, edi
0x180028b3b  mov     r9d, r15d
0x180028b3e  test    eax, eax
0x180028b40  cmovle  r9d, eax; char *
0x180028b44  mov     rcx, [rbp+28h]; this
0x180028b48  test    dl, dl
0x180028b4a  jz      short loc_180028B6B
0x180028b4c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180028b53  mov     edx, 57Dh; void *
0x180028b58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028b5d  test    ebx, ebx
0x180028b5f  js      short loc_180028B6B
0x180028b61  mov     ebx, r15d
0x180028b64  test    r14d, r14d
0x180028b67  cmovle  ebx, r14d
0x180028b6b  lea     rdx, aScenariocontex; "ScenarioContext"
0x180028b72  mov     rcx, [rbp+hKey]; hKey
0x180028b76  call    cs:__imp_RegDeleteValueW
0x180028b7c  mov     r14d, eax
0x180028b7f  test    r13d, eax
0x180028b82  setnz   dl
0x180028b85  movzx   r15d, ax
  ... truncated ...
```
