# CflApi::ClearScenarioDataWithReason

- ea: `0x18001bf60`
- end: `0x18001c4f9`
- name: `CflApi::ClearScenarioDataWithReason`
- size: `1433`
- prototype: `__int64 __fastcall(char *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020378`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x180010700`
- `0x18001332c`
- `0x18001bf60`
- `0x18001f8e4`
- `0x18001f948`
- `0x18002222c`
- `0x18002dff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c45f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c45f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c472`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c069`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c108`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c069`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c108`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c364`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c3b1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c402`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c364`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c3b1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001c402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bfb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bfb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c2a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c46a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c2a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c46a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001c11d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001c11d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c312`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c491`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c4cc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c312`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c491`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001c4cc`

## string_xrefs

- `0x18001bfe5`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c16e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c20d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c23e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c27c`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c2ba`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c33d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c38b`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c3d8`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c429`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001c15c`: `Unexpected ScenarioDataClearReason (reason: %u)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CflApi::ClearScenarioDataWithReason(char *a1, _QWORD *a2)
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
  HKEY v31; // r14
  DWORD LastError; // ebx
  LSTATUS v33; // eax
  LSTATUS v34; // eax
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
      v6 = 1947;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v5,
        phkResult);
LABEL_8:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v5;
    }
    if ( v3 == 2 )
    {
      v8 = 1952;
LABEL_38:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      v6 = 1977;
      goto LABEL_7;
    }
    goto LABEL_28;
  }
  if ( pdwType != 1 )
  {
    v5 = -2147024809;
    v6 = 1982;
    goto LABEL_7;
  }
  if ( !pcbData || (pcbData & 1) != 0 )
  {
    v5 = -2147024872;
    v6 = 1985;
    goto LABEL_7;
  }
  Buf2[0] = 0;
  v11 = CflApiNew::AllocBuffer_unsigned_short_((unsigned __int64)pcbData >> 1, Buf2);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C4,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
            (void *)0x7CD,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
          v8 = 2020;
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
            (void *)0x7F2,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
              (void *)0x7FB,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
              (void *)0x804,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
              (void *)0x80D,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)v30,
              phkResult);
            if ( v5 < 0 )
            {
LABEL_80:
              v6 = 2068;
              goto LABEL_7;
            }
            v5 = v29;
            if ( v28 <= 0 )
              v5 = v28;
          }
          if ( v5 < 0 )
            goto LABEL_80;
        }
        v31 = hKey;
        if ( hKey )
        {
          LastError = GetLastError();
          RegCloseKey(v31);
          SetLastError(LastError);
        }
        hKey = 0;
        v33 = RegDeleteKeyW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData\\ProtectedData");
        v5 = v33;
        if ( (v33 & 0xFFFFFFFD) != 0 )
        {
          if ( v33 > 0 )
            v5 = (unsigned __int16)v33 | 0x80070000;
          if ( v5 >= 0 )
            goto LABEL_8;
          v6 = 2075;
          goto LABEL_7;
        }
        if ( !v9 )
        {
          v34 = RegDeleteKeyW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ScenarioData");
          v5 = v34;
          if ( (v34 & 0xFFFFFFFD) != 0 )
          {
            if ( v34 > 0 )
              v5 = (unsigned __int16)v34 | 0x80070000;
            if ( v5 >= 0 )
              goto LABEL_8;
            v6 = 2082;
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
          (void *)0x7E9,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      (void *)0x7CF,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
0x18001bf60  mov     [rsp-28h+arg_8], rbx
0x18001bf65  mov     [rsp-28h+arg_10], rsi
0x18001bf6a  push    rbp
0x18001bf6b  push    rdi
0x18001bf6c  push    r13
0x18001bf6e  push    r14
0x18001bf70  push    r15
0x18001bf72  mov     rbp, rsp
0x18001bf75  sub     rsp, 80h
0x18001bf7c  mov     rax, cs:__security_cookie
0x18001bf83  xor     rax, rsp
0x18001bf86  mov     [rbp+var_10], rax
0x18001bf8a  mov     r15, rdx
0x18001bf8d  mov     edi, ecx
0x18001bf8f  mov     [rbp+hKey], 0
0x18001bf97  lea     rax, [rbp+hKey]
0x18001bf9b  mov     [rsp+80h+phkResult], rax; int
0x18001bfa0  mov     r9d, 3; samDesired
0x18001bfa6  xor     r8d, r8d; ulOptions
0x18001bfa9  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001bfb0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bfb7  call    cs:__imp_RegOpenKeyExW
0x18001bfbd  mov     ebx, eax
0x18001bfbf  test    eax, eax
0x18001bfc1  jz      short loc_18001C01B
0x18001bfc3  cmp     eax, 2
0x18001bfc6  jz      short loc_18001C008
0x18001bfc8  test    eax, eax
0x18001bfca  jle     short loc_18001BFD5
0x18001bfcc  movzx   ebx, ax
0x18001bfcf  or      ebx, 80070000h
0x18001bfd5  test    ebx, ebx
0x18001bfd7  jns     short loc_18001BFF2
0x18001bfd9  mov     edx, 79Bh; void *
0x18001bfde  mov     rcx, [rbp+28h]; this
0x18001bfe2  mov     r9d, ebx; char *
0x18001bfe5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001bfec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bff1  nop
0x18001bff2  mov     rcx, [rbp+hKey]; hKey
0x18001bff6  test    rcx, rcx
0x18001bff9  jz      short loc_18001C001
0x18001bffb  call    cs:__imp_RegCloseKey
0x18001c001  mov     eax, ebx
0x18001c003  jmp     loc_18001C1AC
0x18001c008  cmp     edi, 2
0x18001c00b  jnz     loc_18001C19B
0x18001c011  mov     edx, 7A0h
0x18001c016  jmp     loc_18001C1FB
0x18001c01b  xorps   xmm0, xmm0
0x18001c01e  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18001c022  mov     esi, 1
0x18001c027  cmp     edi, esi
0x18001c029  jz      loc_18001C301
0x18001c02f  mov     [rbp+pdwType], 0
0x18001c036  mov     [rbp+var_38], 0
0x18001c03d  lea     rax, [rbp+var_38]
0x18001c041  mov     [rsp+80h+pcbData], rax; pcbData
0x18001c046  mov     [rsp+80h+pvData], 0; pvData
0x18001c04f  lea     rax, [rbp+pdwType]
0x18001c053  mov     [rsp+80h+phkResult], rax; int
0x18001c058  lea     r9d, [rsi+1]; dwFlags
0x18001c05c  lea     r8, Value; "ProviderId"
0x18001c063  xor     edx, edx; lpSubKey
0x18001c065  mov     rcx, [rbp+hKey]; hkey
0x18001c069  call    cs:__imp_RegGetValueW
0x18001c06f  mov     ebx, eax
0x18001c071  test    eax, eax
0x18001c073  jz      short loc_18001C09D
0x18001c075  cmp     eax, 2
0x18001c078  jz      loc_18001C13B
0x18001c07e  test    eax, eax
0x18001c080  jle     short loc_18001C08B
0x18001c082  movzx   ebx, ax
0x18001c085  or      ebx, 80070000h
0x18001c08b  test    ebx, ebx
0x18001c08d  jns     loc_18001BFF2
0x18001c093  mov     edx, 7B9h
0x18001c098  jmp     loc_18001BFDE
0x18001c09d  cmp     [rbp+pdwType], esi
0x18001c0a0  jnz     loc_18001C2F2
0x18001c0a6  mov     eax, [rbp+var_38]
0x18001c0a9  test    eax, eax
0x18001c0ab  jz      loc_18001C2E3
0x18001c0b1  test    sil, al
0x18001c0b4  jnz     loc_18001C2E3
0x18001c0ba  mov     [rbp+Buf2], 0
0x18001c0c2  mov     ecx, eax
0x18001c0c4  shr     rcx, 1
0x18001c0c7  lea     rdx, [rbp+Buf2]
0x18001c0cb  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001c0d0  mov     ebx, eax
0x18001c0d2  test    eax, eax
0x18001c0d4  js      loc_18001C2B3
0x18001c0da  lea     rax, [rbp+var_38]
0x18001c0de  mov     [rsp+80h+pcbData], rax; pcbData
0x18001c0e3  mov     rbx, [rbp+Buf2]
0x18001c0e7  mov     [rsp+80h+pvData], rbx; char *
0x18001c0ec  mov     [rsp+80h+phkResult], 0; unsigned int
0x18001c0f5  mov     r9d, 2; dwFlags
0x18001c0fb  lea     r8, Value; "ProviderId"
0x18001c102  xor     edx, edx; lpSubKey
0x18001c104  mov     rcx, [rbp+hKey]; hkey
0x18001c108  call    cs:__imp_RegGetValueW
0x18001c10e  test    eax, eax
0x18001c110  jnz     loc_18001C275
0x18001c116  lea     rdx, [rbp+pclsid]; pclsid
0x18001c11a  mov     rcx, rbx; lpsz
0x18001c11d  call    cs:__imp_CLSIDFromString
0x18001c123  mov     r14d, eax
0x18001c126  test    eax, eax
0x18001c128  js      loc_18001C237
0x18001c12e  test    rbx, rbx
0x18001c131  jz      short loc_18001C13B
0x18001c133  mov     rcx, rbx; hMem
0x18001c136  call    CflFreeBuffer
0x18001c13b  mov     ecx, edi
0x18001c13d  sub     ecx, 1
0x18001c140  jz      loc_18001C301
0x18001c146  sub     ecx, 1
0x18001c149  jz      loc_18001C1D4
0x18001c14f  cmp     ecx, 1
0x18001c152  jz      short loc_18001C184
0x18001c154  mov     rcx, [rbp+28h]; this
0x18001c158  mov     dword ptr [rsp+80h+pvData], edi; char *
0x18001c15c  lea     rax, aUnexpectedScen; "Unexpected ScenarioDataClearReason (rea"...
0x18001c163  mov     [rsp+80h+phkResult], rax; int
0x18001c168  mov     r9d, 8000FFFFh; char *
0x18001c16e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c175  mov     edx, 7E9h; void *
0x18001c17a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c17f  jmp     loc_18001C21E
0x18001c184  mov     rax, [r15]
0x18001c187  cmp     rax, qword ptr [rbp+pclsid.Data1]
0x18001c18b  jnz     short loc_18001C19B
0x18001c18d  mov     rax, [r15+8]
0x18001c191  cmp     rax, qword ptr [rbp+pclsid.Data4]
0x18001c195  jz      loc_18001C301
0x18001c19b  mov     rcx, [rbp+hKey]; hKey
0x18001c19f  test    rcx, rcx
0x18001c1a2  jz      short loc_18001C1AA
0x18001c1a4  call    cs:__imp_RegCloseKey
0x18001c1aa  xor     eax, eax
0x18001c1ac  mov     rcx, [rbp+var_10]
0x18001c1b0  xor     rcx, rsp; StackCookie
0x18001c1b3  call    __security_check_cookie
0x18001c1b8  lea     r11, [rsp+80h+var_s0]
0x18001c1c0  mov     rbx, [r11+38h]
0x18001c1c4  mov     rsi, [r11+40h]
0x18001c1c8  mov     rsp, r11
0x18001c1cb  pop     r15
0x18001c1cd  pop     r14
0x18001c1cf  pop     r13
0x18001c1d1  pop     rdi
0x18001c1d2  pop     rbp
0x18001c1d3  retn
0x18001c1d4  xorps   xmm0, xmm0
0x18001c1d7  movups  xmmword ptr [rbp+Buf2], xmm0
0x18001c1db  mov     r8d, 10h; Size
0x18001c1e1  lea     rdx, [rbp+Buf2]; Buf2
0x18001c1e5  lea     rcx, [rbp+pclsid]; Buf1
0x18001c1e9  call    memcmp_0
0x18001c1ee  test    eax, eax
0x18001c1f0  jnz     loc_18001C304
0x18001c1f6  mov     edx, 7E4h; void *
0x18001c1fb  lea     rax, aExpectedScenar; "Expected scenario data ownership to hav"...
0x18001c202  mov     [rsp+80h+phkResult], rax; int
0x18001c207  mov     r9d, 8000FFFFh; char *
0x18001c20d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c214  mov     rcx, [rbp+28h]; this
0x18001c218  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c21d  nop
0x18001c21e  mov     rcx, [rbp+hKey]; hKey
0x18001c222  test    rcx, rcx
0x18001c225  jz      short loc_18001C22D
0x18001c227  call    cs:__imp_RegCloseKey
0x18001c22d  mov     eax, 8000FFFFh
0x18001c232  jmp     loc_18001C1AC
0x18001c237  mov     rcx, [rbp+28h]; this
0x18001c23b  mov     r9d, r14d; char *
0x18001c23e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c245  mov     edx, 7CFh; void *
0x18001c24a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c24f  nop
0x18001c250  test    rbx, rbx
0x18001c253  jz      short loc_18001C25E
0x18001c255  mov     rcx, rbx; hMem
0x18001c258  call    CflFreeBuffer
0x18001c25d  nop
0x18001c25e  mov     rcx, [rbp+hKey]; hKey
0x18001c262  test    rcx, rcx
0x18001c265  jz      short loc_18001C26D
0x18001c267  call    cs:__imp_RegCloseKey
0x18001c26d  mov     eax, r14d
0x18001c270  jmp     loc_18001C1AC
0x18001c275  mov     rcx, [rbp+28h]; this
0x18001c279  mov     r9d, eax; char *
0x18001c27c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c283  mov     edx, 7CDh; void *
0x18001c288  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c28d  mov     edi, eax
0x18001c28f  test    rbx, rbx
0x18001c292  jz      short loc_18001C29D
0x18001c294  mov     rcx, rbx; hMem
0x18001c297  call    CflFreeBuffer
0x18001c29c  nop
0x18001c29d  mov     rcx, [rbp+hKey]; hKey
0x18001c2a1  test    rcx, rcx
0x18001c2a4  jz      short loc_18001C2AC
0x18001c2a6  call    cs:__imp_RegCloseKey
0x18001c2ac  mov     eax, edi
0x18001c2ae  jmp     loc_18001C1AC
0x18001c2b3  mov     rcx, [rbp+28h]; this
0x18001c2b7  mov     r9d, ebx; char *
0x18001c2ba  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c2c1  mov     edx, 7C4h; void *
0x18001c2c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2cb  nop
0x18001c2cc  mov     rcx, [rbp+Buf2]; hMem
0x18001c2d0  test    rcx, rcx
0x18001c2d3  jz      loc_18001BFF2
0x18001c2d9  call    CflFreeBuffer
0x18001c2de  jmp     loc_18001BFF2
0x18001c2e3  mov     ebx, 80070018h
0x18001c2e8  mov     edx, 7C1h
0x18001c2ed  jmp     loc_18001BFDE
0x18001c2f2  mov     ebx, 80070057h
0x18001c2f7  mov     edx, 7BEh
0x18001c2fc  jmp     loc_18001BFDE
0x18001c301  xor     sil, sil
0x18001c304  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001c30b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c312  call    cs:__imp_RegDeleteKeyW
0x18001c318  mov     r13d, 0FFFFFFFDh
0x18001c31e  test    r13d, eax
0x18001c321  setnz   dl
0x18001c324  mov     edi, 80070000h
0x18001c329  test    eax, eax
0x18001c32b  jle     short loc_18001C332
0x18001c32d  movzx   eax, ax
0x18001c330  or      eax, edi
0x18001c332  mov     rcx, [rbp+28h]; this
0x18001c336  test    dl, dl
0x18001c338  jz      short loc_18001C34E
0x18001c33a  mov     r9d, eax; char *
0x18001c33d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c344  mov     edx, 7F2h; void *
0x18001c349  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c34e  test    sil, sil
0x18001c351  jz      loc_18001C456
0x18001c357  xor     ebx, ebx
0x18001c359  lea     rdx, aAuthbuffer; "AuthBuffer"
0x18001c360  mov     rcx, [rbp+hKey]; hKey
0x18001c364  call    cs:__imp_RegDeleteValueW
0x18001c36a  mov     r14d, eax
0x18001c36d  test    r13d, eax
0x18001c370  setnz   dl
0x18001c373  movzx   r15d, ax
0x18001c377  or      r15d, edi
0x18001c37a  mov     r9d, r15d
0x18001c37d  test    eax, eax
0x18001c37f  cmovle  r9d, eax; char *
0x18001c383  mov     rcx, [rbp+28h]; this
0x18001c387  test    dl, dl
0x18001c389  jz      short loc_18001C3A6
0x18001c38b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c392  mov     edx, 7FBh; void *
0x18001c397  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c39c  mov     ebx, r15d
0x18001c39f  test    r14d, r14d
0x18001c3a2  cmovle  ebx, r14d
0x18001c3a6  lea     rdx, aScenarioid; "ScenarioId"
0x18001c3ad  mov     rcx, [rbp+hKey]; hKey
0x18001c3b1  call    cs:__imp_RegDeleteValueW
0x18001c3b7  mov     r14d, eax
0x18001c3ba  test    r13d, eax
0x18001c3bd  setnz   dl
0x18001c3c0  movzx   r15d, ax
0x18001c3c4  or      r15d, edi
0x18001c3c7  mov     r9d, r15d
0x18001c3ca  test    eax, eax
0x18001c3cc  cmovle  r9d, eax; char *
0x18001c3d0  mov     rcx, [rbp+28h]; this
0x18001c3d4  test    dl, dl
0x18001c3d6  jz      short loc_18001C3F7
0x18001c3d8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001c3df  mov     edx, 804h; void *
0x18001c3e4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c3e9  test    ebx, ebx
0x18001c3eb  js      short loc_18001C3F7
0x18001c3ed  mov     ebx, r15d
0x18001c3f0  test    r14d, r14d
0x18001c3f3  cmovle  ebx, r14d
0x18001c3f7  lea     rdx, aScenariocontex; "ScenarioContext"
0x18001c3fe  mov     rcx, [rbp+hKey]; hKey
0x18001c402  call    cs:__imp_RegDeleteValueW
0x18001c408  mov     r14d, eax
0x18001c40b  test    r13d, eax
0x18001c40e  setnz   dl
0x18001c411  movzx   r15d, ax
  ... truncated ...
```
