# CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)

- ea: `0x180012ef0`
- end: `0x180013561`
- name: `?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z`
- size: `1649`
- prototype: `__int64 __fastcall(CSettings *this, const wchar_t *, const wchar_t *, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ff8c`

## callees

- `0x18000a004`
- `0x18000e524`
- `0x18000f740`
- `0x180011d94`
- `0x1800121e4`
- `0x180012ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180013287`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800132be`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180013287`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800132be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013180`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013180`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013156`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013156`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013545`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013545`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800130c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013103`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800130c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013103`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013378`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001342c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013378`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001342c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013479`

## string_xrefs

- `0x180012f5d`: `BrokerUp`

## pseudocode

```c
__int64 __fastcall CSettings::LoadSettings(CSettings *this, const wchar_t *a2, const wchar_t *a3, DWORD a4)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // edi
  int v8; // esi
  unsigned int i; // edi
  _WORD *v10; // r9
  HKEY *phkResult; // rax
  HKEY *v12; // rax
  HKEY v13; // rsi
  __int64 j; // rdi
  HKEY *v15; // rax
  HKEY v16; // rsi
  __int64 k; // rdi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HKEY *v21; // rax
  HKEY v22; // rsi
  __int64 m; // rdi
  HKEY *v24; // rax
  HKEY v25; // rsi
  __int64 n; // rdi
  unsigned int v27; // edi
  wchar_t *v28; // r9
  HKEY *v29; // rax
  HKEY v30; // rsi
  __int64 ii; // rdi
  HKEY *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  HKEY v35; // rsi
  __int64 jj; // rdi
  unsigned int DWORD; // eax
  unsigned int v38; // eax
  bool *pdwType; // [rsp+28h] [rbp-E0h]
  bool *pdwTypea; // [rsp+28h] [rbp-E0h]
  bool *pdwTypeb; // [rsp+28h] [rbp-E0h]
  bool pvData; // [rsp+30h] [rbp-D8h]
  bool pvDataa; // [rsp+30h] [rbp-D8h]
  bool pvDatab; // [rsp+30h] [rbp-D8h]
  HKEY v46; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-A0h]
  const wchar_t *v48; // [rsp+70h] [rbp-98h]
  __int64 v49; // [rsp+78h] [rbp-90h]
  _DWORD v50[2]; // [rsp+80h] [rbp-88h]
  __int64 v51; // [rsp+88h] [rbp-80h]
  int v52; // [rsp+90h] [rbp-78h]
  const wchar_t *v53; // [rsp+98h] [rbp-70h]
  __int64 v54; // [rsp+A0h] [rbp-68h]
  int v55; // [rsp+A8h] [rbp-60h]
  __int64 v56; // [rsp+B0h] [rbp-58h]
  int v57; // [rsp+B8h] [rbp-50h]
  const wchar_t *v58; // [rsp+C0h] [rbp-48h]
  __int64 v59; // [rsp+C8h] [rbp-40h]
  int v60; // [rsp+D0h] [rbp-38h]
  __int64 v61; // [rsp+D8h] [rbp-30h]
  int v62; // [rsp+E0h] [rbp-28h]
  const wchar_t *v63; // [rsp+E8h] [rbp-20h]
  __int64 v64; // [rsp+F0h] [rbp-18h]
  int v65; // [rsp+F8h] [rbp-10h]
  __int64 v66; // [rsp+100h] [rbp-8h]
  HKEY hKey; // [rsp+158h] [rbp+50h] BYREF
  const wchar_t *Data; // [rsp+160h] [rbp+58h] BYREF
  const wchar_t *v69; // [rsp+168h] [rbp+60h] BYREF
  DWORD pcbData; // [rsp+170h] [rbp+68h] BYREF

  pcbData = a4;
  v69 = a3;
  Data = a2;
  v52 = 9;
  hKey = 0;
  v48 = L"Consent";
  LODWORD(v47) = 0;
  v53 = L"ExcludedApplications";
  *((_DWORD *)this + 1275) = 1;
  v58 = L"DebugApplications";
  *((_DWORD *)this + 1274) = 1;
  v63 = L"BrokerUp";
  v5 = 0;
  v49 = 0;
  v6 = 0;
  v50[0] = 4;
  v51 = 1;
  v54 = 0;
  v55 = 13;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v60 = 14;
  v61 = 0;
  v62 = 0;
  v64 = 0;
  v65 = 22;
  v66 = 0;
  do
  {
    *(_WORD *)((char *)this + v6) = 0;
    ++v5;
    *(_QWORD *)((char *)this + v6 + 96) = 0;
    *(_QWORD *)((char *)this + v6 + 16) = *(_QWORD *)((char *)this + v6 + 8);
    v6 += 104;
  }
  while ( v5 != 49 );
  v7 = 0;
  while ( 1 )
  {
    v8 = CRegSetting::Initialize(
           (__int64)this + 104 * (unsigned int)dword_18004D608[10 * v7],
           *((_DWORD *)&CSettings::allHiveSettings + 10 * v7),
           *((_WORD **)&off_18004D5F8 + 5 * v7),
           (&off_18004D600)[5 * v7],
           qword_18004D610[5 * v7]);
    if ( v8 < 0 )
      break;
    if ( ++v7 >= 0xF )
    {
      for ( i = 0; i < 4; ++i )
      {
        v10 = *(_WORD **)&v50[10 * i - 2];
        if ( v10 )
        {
          v8 = CRegSetting::Initialize(
                 (__int64)this + 104 * (unsigned int)v50[10 * i],
                 *((_DWORD *)&v47 + 10 * i),
                 (&v48)[5 * i],
                 v10,
                 *(&v51 + 5 * i));
          if ( v8 < 0 )
            goto LABEL_56;
        }
      }
      LODWORD(v69) = 0;
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
             L"DefaultConsent",
             0x10u,
             0,
             &v69,
             &pcbData) == 2 )
      {
        pcbData = 4;
        if ( !RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
                L"NewUserDefaultConsent",
                0x10u,
                0,
                &v69,
                &pcbData) )
        {
          LODWORD(Data) = (_DWORD)v69;
          v46 = 0;
          if ( (unsigned int)((_DWORD)v69 - 1) <= 3 )
          {
            phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v46);
            if ( !RegCreateKeyExW(
                    HKEY_CURRENT_USER,
                    L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
                    0,
                    0,
                    0,
                    0x20106u,
                    0,
                    phkResult,
                    0) )
              RegSetValueExW(v46, L"DefaultConsent", 0, 4u, (const BYTE *)&Data, 4u);
            if ( v46 )
              RegCloseKey(v46);
          }
        }
      }
      v12 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v12) )
      {
        v13 = hKey;
        for ( j = 0; j != 49; ++j )
          CRegSetting::Load((CSettings *)((char *)this + 104 * j), v13, 256);
      }
      *((_BYTE *)this + 5108) = *((_BYTE *)this + 208) == 0;
      *((_BYTE *)this + 5109) = *((_BYTE *)this + 104) == 0;
      v15 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v15) )
      {
        v16 = hKey;
        for ( k = 0; k != 49; ++k )
          CRegSetting::Load((CSettings *)((char *)this + 104 * k), v16, 256);
      }
      if ( !*((_BYTE *)this + 208) )
        goto LABEL_28;
      v18 = *((_DWORD *)this + 53);
      if ( !v18 )
      {
        v19 = **((_DWORD **)this + 27);
        goto LABEL_29;
      }
      if ( v18 == 1 )
        v19 = wcstol(*((const wchar_t **)this + 27), 0, 10);
      else
LABEL_28:
        v19 = *((_DWORD *)this + 76);
LABEL_29:
      *((_DWORD *)this + 1278) = v19;
      if ( !*((_BYTE *)this + 104) )
        goto LABEL_34;
      if ( !*((_DWORD *)this + 27) )
      {
        v20 = **((_DWORD **)this + 14);
        goto LABEL_35;
      }
      if ( *((_DWORD *)this + 27) == 1 )
        v20 = wcstol(*((const wchar_t **)this + 14), 0, 10);
      else
LABEL_34:
        v20 = *((_DWORD *)this + 50);
LABEL_35:
      *((_BYTE *)this + 5110) = v20 == 1;
      *((_BYTE *)this + 5106) = *((_BYTE *)this + 208);
      *((_BYTE *)this + 5107) = *((_BYTE *)this + 104);
      v21 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v21) )
      {
        v22 = hKey;
        for ( m = 0; m != 49; ++m )
          CRegSetting::Load((CSettings *)((char *)this + 104 * m), v22, 256);
      }
      *((_BYTE *)this + 5104) = *((_BYTE *)this + 208);
      *((_BYTE *)this + 5105) = *((_BYTE *)this + 104);
      v24 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, v24) )
      {
        v25 = hKey;
        for ( n = 0; n != 49; ++n )
          CRegSetting::Load((CSettings *)((char *)this + 104 * n), v25, 256);
      }
      v27 = 0;
      while ( 1 )
      {
        v28 = (&off_18004D150)[5 * v27];
        if ( v28 )
        {
          v8 = CRegSetting::Initialize(
                 (__int64)this + 104 * (unsigned int)dword_18004D158[10 * v27],
                 *((_DWORD *)&CSettings::adminSettings + 10 * v27),
                 *((_WORD **)&off_18004D148 + 5 * v27),
                 v28,
                 qword_18004D160[5 * v27]);
          if ( v8 < 0 )
            goto LABEL_56;
        }
        if ( ++v27 >= 0x1E )
        {
          v29 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v29) )
          {
            v30 = hKey;
            for ( ii = 0; ii != 49; ++ii )
              CRegSetting::Load((CSettings *)((char *)this + 104 * ii), v30, 256);
          }
          v32 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v32) )
          {
            v35 = hKey;
            for ( jj = 0; jj != 49; ++jj )
              CRegSetting::Load((CSettings *)((char *)this + 104 * jj), v35, 256);
          }
          *((_DWORD *)this + 1275) = CSettings::ComputeConsent((__int64)this, 0, v33, v34);
          DWORD = UtilRegGetDWORD(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                    L"MSFTInternal",
                    0,
                    pdwType,
                    pvData);
          *((_DWORD *)this + 1279) = DWORD;
          if ( !DWORD )
            *((_DWORD *)this + 1279) = UtilRegGetDWORD(
                                         HKEY_LOCAL_MACHINE,
                                         L"SOFTWARE\\Microsoft\\SQMClient",
                                         L"MSFTInternal",
                                         0,
                                         pdwTypea,
                                         pvDataa);
          v38 = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                  L"IsTest",
                  0,
                  pdwTypea,
                  pvDataa);
          *((_DWORD *)this + 1280) = v38;
          if ( !v38 )
            *((_DWORD *)this + 1280) = UtilRegGetDWORD(
                                         HKEY_LOCAL_MACHINE,
                                         L"SOFTWARE\\Microsoft\\SQMClient",
                                         L"IsTest",
                                         0,
                                         pdwTypeb,
                                         pvDatab);
          v8 = 0;
          goto LABEL_56;
        }
      }
    }
  }
LABEL_56:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012ef0  mov     rax, rsp
0x180012ef3  mov     [rax+20h], r9d
0x180012ef7  mov     [rax+18h], r8
0x180012efb  mov     [rax+10h], rdx
0x180012eff  push    rbp
0x180012f00  push    rbx
0x180012f01  push    rsi
0x180012f02  push    rdi
0x180012f03  push    r12
0x180012f05  push    r13
0x180012f07  push    r14
0x180012f09  push    r15
0x180012f0b  lea     rbp, [rax-48h]
0x180012f0f  sub     rsp, 108h
0x180012f16  xor     r14d, r14d
0x180012f19  mov     [rbp+40h+var_B8], 9
0x180012f20  lea     rax, aConsent; "Consent"
0x180012f27  mov     [rbp+40h+hKey], r14
0x180012f2b  mov     [rsp+140h+var_D8], rax
0x180012f30  mov     rbx, rcx
0x180012f33  lea     rax, aExcludedapplic; "ExcludedApplications"
0x180012f3a  mov     dword ptr [rsp+140h+var_E0], r14d
0x180012f3f  lea     r15d, [r14+1]
0x180012f43  mov     [rbp+40h+var_B0], rax
0x180012f47  lea     rax, aDebugapplicati; "DebugApplications"
0x180012f4e  mov     [rcx+13ECh], r15d
0x180012f55  mov     [rbp+40h+var_88], rax
0x180012f59  lea     r12d, [r14+4]
0x180012f5d  lea     rax, aBrokerup; "BrokerUp"
0x180012f64  mov     [rcx+13E8h], r15d
0x180012f6b  mov     [rbp+40h+var_60], rax
0x180012f6f  mov     edx, r14d
0x180012f72  mov     [rsp+140h+var_D0], r14
0x180012f77  mov     ecx, r14d
0x180012f7a  mov     [rsp+140h+var_C8], r12d
0x180012f7f  mov     [rbp+40h+var_C0], r15
0x180012f83  mov     [rbp+40h+var_A8], r14
0x180012f87  mov     [rbp+40h+var_A0], 0Dh
0x180012f8e  mov     [rbp+40h+var_98], r14
0x180012f92  mov     [rbp+40h+var_90], r14d
0x180012f96  mov     [rbp+40h+var_80], r14
0x180012f9a  mov     [rbp+40h+var_78], 0Eh
0x180012fa1  mov     [rbp+40h+var_70], r14
0x180012fa5  mov     [rbp+40h+var_68], r14d
0x180012fa9  mov     [rbp+40h+var_58], r14
0x180012fad  mov     [rbp+40h+var_50], 16h
0x180012fb4  mov     [rbp+40h+var_48], r14
0x180012fb8  mov     [rbx+rcx], r14w
0x180012fbd  add     rdx, r15
0x180012fc0  mov     [rbx+rcx+60h], r14
0x180012fc5  mov     rax, [rbx+rcx+8]
0x180012fca  mov     [rbx+rcx+10h], rax
0x180012fcf  lea     rcx, [rcx+68h]
0x180012fd3  cmp     rdx, 31h ; '1'
0x180012fd7  jnz     short loc_180012FB8
0x180012fd9  mov     edi, r14d
0x180012fdc  lea     r10, __ImageBase
0x180012fe3  mov     eax, edi
0x180012fe5  lea     rdx, [rax+rax*4]
0x180012fe9  mov     eax, ds:rva dword_18004D608[r10+rdx*8]
0x180012ff1  mov     r9, ds:rva off_18004D600[r10+rdx*8]; "DontSendAdditionalData" ...
0x180012ff9  mov     r8, ds:rva off_18004D5F8[r10+rdx*8]
0x180013001  imul    rcx, rax, 68h ; 'h'
0x180013005  mov     rax, ds:rva qword_18004D610[r10+rdx*8]
0x18001300d  mov     edx, ds:rva ?allHiveSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::allHiveSettings ...
0x180013015  add     rcx, rbx
0x180013018  mov     [rsp+140h+pdwType], rax
0x18001301d  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x180013022  mov     esi, eax
0x180013024  test    eax, eax
0x180013026  js      loc_18001353C
0x18001302c  add     edi, r15d
0x18001302f  lea     r10, __ImageBase
0x180013036  cmp     edi, 0Fh
0x180013039  jb      short loc_180012FE3
0x18001303b  mov     edi, r14d
0x18001303e  mov     eax, edi
0x180013040  lea     rdx, [rax+rax*4]
0x180013044  mov     r9, [rsp+rdx*8+140h+var_D0]
0x180013049  test    r9, r9
0x18001304c  jz      short loc_18001307B
0x18001304e  mov     eax, [rsp+rdx*8+140h+var_C8]
0x180013052  mov     r8, [rsp+rdx*8+140h+var_D8]
0x180013057  imul    rcx, rax, 68h ; 'h'
0x18001305b  mov     rax, [rbp+rdx*8+40h+var_C0]
0x180013060  mov     edx, dword ptr [rsp+rdx*8+140h+var_E0]
0x180013064  add     rcx, rbx
0x180013067  mov     [rsp+140h+pdwType], rax
0x18001306c  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x180013071  mov     esi, eax
0x180013073  test    eax, eax
0x180013075  js      loc_18001353C
0x18001307b  add     edi, r15d
0x18001307e  cmp     edi, r12d
0x180013081  jb      short loc_18001303E
0x180013083  lea     rax, [rbp+40h+arg_18]
0x180013087  mov     dword ptr [rbp+40h+arg_10], r14d
0x18001308b  mov     [rsp+140h+pcbData], rax; pcbData
0x180013090  lea     rdi, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x180013097  lea     rax, [rbp+40h+arg_10]
0x18001309b  mov     [rbp+40h+arg_18], r12d
0x18001309f  mov     [rsp+140h+pvData], rax; pvData
0x1800130a4  lea     r8, Value; "DefaultConsent"
0x1800130ab  mov     esi, 10h
0x1800130b0  mov     [rsp+140h+pdwType], r14; pdwType
0x1800130b5  mov     r9d, esi; dwFlags
0x1800130b8  mov     rdx, rdi; lpSubKey
0x1800130bb  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800130c2  call    cs:__imp_RegGetValueW
0x1800130c8  mov     r13, 0FFFFFFFF80000002h
0x1800130cf  cmp     eax, 2
0x1800130d2  jnz     loc_180013196
0x1800130d8  lea     rax, [rbp+40h+arg_18]
0x1800130dc  mov     [rbp+40h+arg_18], r12d
0x1800130e0  mov     [rsp+140h+pcbData], rax; pcbData
0x1800130e5  lea     r8, aNewuserdefault; "NewUserDefaultConsent"
0x1800130ec  lea     rax, [rbp+40h+arg_10]
0x1800130f0  mov     r9d, esi; dwFlags
0x1800130f3  mov     [rsp+140h+pvData], rax; pvData
0x1800130f8  mov     rdx, rdi; lpSubKey
0x1800130fb  mov     rcx, r13; hkey
0x1800130fe  mov     [rsp+140h+pdwType], r14; pdwType
0x180013103  call    cs:__imp_RegGetValueW
0x180013109  test    eax, eax
0x18001310b  jnz     loc_180013196
0x180013111  mov     eax, dword ptr [rbp+40h+arg_10]
0x180013114  mov     dword ptr [rbp+40h+Data], eax
0x180013117  dec     eax
0x180013119  mov     [rsp+140h+var_F0], r14
0x18001311e  cmp     eax, 3
0x180013121  ja      short loc_180013196
0x180013123  lea     rcx, [rsp+140h+var_F0]
0x180013128  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001312d  mov     [rsp+40h], r14; lpdwDisposition
0x180013132  lea     rcx, [r13-1]; hKey
0x180013136  mov     [rsp+140h+phkResult], rax; phkResult
0x18001313b  xor     r9d, r9d; lpClass
0x18001313e  mov     [rsp+140h+pcbData], r14; lpSecurityAttributes
0x180013143  xor     r8d, r8d; Reserved
0x180013146  mov     dword ptr [rsp+140h+pvData], 20106h; samDesired
0x18001314e  mov     rdx, rdi; lpSubKey
0x180013151  mov     dword ptr [rsp+140h+pdwType], r14d; dwOptions
0x180013156  call    cs:__imp_RegCreateKeyExW
0x18001315c  test    eax, eax
0x18001315e  jnz     short loc_180013186
0x180013160  mov     rcx, [rsp+140h+var_F0]; hKey
0x180013165  lea     rax, [rbp+40h+Data]
0x180013169  mov     dword ptr [rsp+140h+pvData], r12d; bool
0x18001316e  lea     rdx, Value; "DefaultConsent"
0x180013175  mov     r9d, r12d; dwType
0x180013178  mov     [rsp+140h+pdwType], rax; lpData
0x18001317d  xor     r8d, r8d; Reserved
0x180013180  call    cs:__imp_RegSetValueExW
0x180013186  mov     rcx, [rsp+140h+var_F0]; hKey
0x18001318b  test    rcx, rcx
0x18001318e  jz      short loc_180013196
0x180013190  call    cs:__imp_RegCloseKey
0x180013196  lea     rcx, [rbp+40h+hKey]
0x18001319a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001319f  mov     r9d, 20119h; samDesired
0x1800131a5  mov     [rsp+140h+pdwType], rax; phkResult
0x1800131aa  xor     r8d, r8d; ulOptions
0x1800131ad  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800131b4  mov     rcx, r13; hKey
0x1800131b7  call    cs:__imp_RegOpenKeyExW
0x1800131bd  mov     r12d, 100h
0x1800131c3  test    eax, eax
0x1800131c5  jnz     short loc_1800131E9
0x1800131c7  mov     rsi, [rbp+40h+hKey]
0x1800131cb  mov     rdi, r14
0x1800131ce  imul    rcx, rdi, 68h ; 'h'
0x1800131d2  mov     r8d, r12d; unsigned int
0x1800131d5  mov     rdx, rsi; HKEY
0x1800131d8  add     rcx, rbx; this
0x1800131db  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1800131e0  add     rdi, r15
0x1800131e3  cmp     rdi, 31h ; '1'
0x1800131e7  jnz     short loc_1800131CE
0x1800131e9  cmp     [rbx+0D0h], r14b
0x1800131f0  lea     rcx, [rbp+40h+hKey]
0x1800131f4  setz    al
0x1800131f7  mov     [rbx+13F4h], al
0x1800131fd  cmp     [rbx+68h], r14b
0x180013201  setz    al
0x180013204  mov     [rbx+13F5h], al
0x18001320a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001320f  mov     r9d, 20119h; samDesired
0x180013215  mov     [rsp+140h+pdwType], rax; phkResult
0x18001321a  xor     r8d, r8d; ulOptions
0x18001321d  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x180013224  mov     rcx, r13; hKey
0x180013227  call    cs:__imp_RegOpenKeyExW
0x18001322d  test    eax, eax
0x18001322f  jnz     short loc_180013253
0x180013231  mov     rsi, [rbp+40h+hKey]
0x180013235  mov     rdi, r14
0x180013238  imul    rcx, rdi, 68h ; 'h'
0x18001323c  mov     r8d, r12d; unsigned int
0x18001323f  mov     rdx, rsi; HKEY
0x180013242  add     rcx, rbx; this
0x180013245  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18001324a  add     rdi, r15
0x18001324d  cmp     rdi, 31h ; '1'
0x180013251  jnz     short loc_180013238
0x180013253  mov     edi, 0Ah
0x180013258  cmp     [rbx+0D0h], r14b
0x18001325f  jz      short loc_18001328F
0x180013261  mov     eax, [rbx+0D4h]
0x180013267  test    eax, eax
0x180013269  jnz     short loc_180013276
0x18001326b  mov     rax, [rbx+0D8h]
0x180013272  mov     eax, [rax]
0x180013274  jmp     short loc_180013295
0x180013276  cmp     eax, r15d
0x180013279  jnz     short loc_18001328F
0x18001327b  mov     rcx, [rbx+0D8h]; String
0x180013282  mov     r8d, edi; Radix
0x180013285  xor     edx, edx; EndPtr
0x180013287  call    cs:__imp_wcstol
0x18001328d  jmp     short loc_180013295
0x18001328f  mov     eax, [rbx+130h]
0x180013295  mov     [rbx+13F8h], eax
0x18001329b  cmp     [rbx+68h], r14b
0x18001329f  jz      short loc_1800132C6
0x1800132a1  cmp     [rbx+6Ch], r14d
0x1800132a5  jnz     short loc_1800132AF
0x1800132a7  mov     rax, [rbx+70h]
0x1800132ab  mov     eax, [rax]
0x1800132ad  jmp     short loc_1800132CC
0x1800132af  cmp     [rbx+6Ch], r15d
0x1800132b3  jnz     short loc_1800132C6
0x1800132b5  mov     rcx, [rbx+70h]; String
0x1800132b9  mov     r8d, edi; Radix
0x1800132bc  xor     edx, edx; EndPtr
0x1800132be  call    cs:__imp_wcstol
0x1800132c4  jmp     short loc_1800132CC
0x1800132c6  mov     eax, [rbx+0C8h]
0x1800132cc  cmp     eax, r15d
0x1800132cf  lea     rcx, [rbp+40h+hKey]
0x1800132d3  setz    al
0x1800132d6  mov     [rbx+13F6h], al
0x1800132dc  mov     al, [rbx+0D0h]
0x1800132e2  mov     [rbx+13F2h], al
0x1800132e8  mov     al, [rbx+68h]
0x1800132eb  mov     [rbx+13F3h], al
0x1800132f1  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800132f6  mov     r9d, 20119h; samDesired
0x1800132fc  mov     [rsp+140h+pdwType], rax; phkResult
0x180013301  xor     r8d, r8d; ulOptions
0x180013304  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18001330b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180013312  call    cs:__imp_RegOpenKeyExW
0x180013318  test    eax, eax
0x18001331a  jnz     short loc_18001333E
0x18001331c  mov     rsi, [rbp+40h+hKey]
0x180013320  mov     rdi, r14
0x180013323  imul    rcx, rdi, 68h ; 'h'
0x180013327  mov     r8d, r12d; unsigned int
0x18001332a  mov     rdx, rsi; HKEY
0x18001332d  add     rcx, rbx; this
0x180013330  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x180013335  add     rdi, r15
0x180013338  cmp     rdi, 31h ; '1'
0x18001333c  jnz     short loc_180013323
0x18001333e  mov     al, [rbx+0D0h]
0x180013344  lea     rcx, [rbp+40h+hKey]
0x180013348  mov     [rbx+13F0h], al
0x18001334e  mov     al, [rbx+68h]
0x180013351  mov     [rbx+13F1h], al
0x180013357  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001335c  mov     r9d, 20119h; samDesired
0x180013362  mov     [rsp+140h+pdwType], rax; phkResult
0x180013367  xor     r8d, r8d; ulOptions
0x18001336a  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Windows E"...
0x180013371  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180013378  call    cs:__imp_RegOpenKeyExW
0x18001337e  test    eax, eax
0x180013380  jnz     short loc_1800133A4
0x180013382  mov     rsi, [rbp+40h+hKey]
0x180013386  mov     rdi, r14
0x180013389  imul    rcx, rdi, 68h ; 'h'
0x18001338d  mov     r8d, r12d; unsigned int
0x180013390  mov     rdx, rsi; HKEY
0x180013393  add     rcx, rbx; this
0x180013396  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18001339b  add     rdi, r15
0x18001339e  cmp     rdi, 31h ; '1'
0x1800133a2  jnz     short loc_180013389
0x1800133a4  mov     edi, r14d
0x1800133a7  lea     r10, __ImageBase
0x1800133ae  mov     eax, edi
0x1800133b0  lea     rdx, [rax+rax*4]
0x1800133b4  mov     r9, ds:rva off_18004D150[r10+rdx*8]; "DisableArchive" ...
0x1800133bc  test    r9, r9
0x1800133bf  jz      short loc_180013403
0x1800133c1  mov     eax, ds:rva dword_18004D158[r10+rdx*8]
0x1800133c9  mov     r8, ds:rva off_18004D148[r10+rdx*8]
0x1800133d1  imul    rcx, rax, 68h ; 'h'
0x1800133d5  mov     rax, ds:rva qword_18004D160[r10+rdx*8]
0x1800133dd  mov     edx, ds:rva ?adminSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::adminSettings ...
  ... truncated ...
```
