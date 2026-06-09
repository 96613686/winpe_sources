# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherAllRegValues(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)

- ea: `0x180125208`
- end: `0x180125921`
- name: `?GatherAllRegValues@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z`
- size: `1817`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180125bf8`

## callees

- `0x180019080`
- `0x18001989c`
- `0x18001a054`
- `0x1800ed46c`
- `0x1800eef28`
- `0x180109140`
- `0x180125208`
- `0x18012713c`
- `0x1801271cc`
- `0x180127510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801255d9`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801255d9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801256e4`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801256e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801253c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801254ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125606`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125711`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125836`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801253c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801254ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125606`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125711`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125836`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18012543f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18012543f`
- `OLEAUT32!__imp_SysFreeString` at `0x180125516`
- `OLEAUT32!__imp_SysFreeString` at `0x180125543`
- `OLEAUT32!__imp_SysFreeString` at `0x180125516`
- `OLEAUT32!__imp_SysFreeString` at `0x180125543`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012532c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180125398`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180125496`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012559f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801256a9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012579d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012580d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012532c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180125398`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180125496`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012559f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801256a9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012579d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012580d`

## string_xrefs

- `0x180125298`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x1801254fa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180125865`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherAllRegValues(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        _QWORD *a2,
        HKEY a3)
{
  signed int DiagValue; // ebx
  __int64 v7; // rdx
  std::_Ref_count_base *v8; // rcx
  DWORD v10; // r12d
  const unsigned __int16 *v11; // r14
  LSTATUS v12; // eax
  signed int v13; // edi
  bool v14; // zf
  LSTATUS v15; // eax
  __int64 v16; // rbx
  LSTATUS v17; // eax
  __int64 v18; // rdx
  LSTATUS v19; // eax
  int v20; // eax
  LSTATUS v21; // eax
  int v22; // eax
  LSTATUS v23; // eax
  bool v24; // sf
  BYTE *v25; // rbx
  LSTATUS v26; // eax
  __int64 v27; // rdx
  std::_Ref_count_base *v28; // rcx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  int lpReservedb; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD lpData[2]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD lpcbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v37[2]; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  BSTR *p_bstrString; // [rsp+80h] [rbp-80h]
  char v41; // [rsp+88h] [rbp-78h]
  _QWORD *v42; // [rsp+90h] [rbp-70h]
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE Data[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v42 = a2;
  memset_0(ValueName, 0, 0x208u);
  cchValueName = 260;
  memset_0(Data, 0, 0x208u);
  cbData = 520;
  *(_OWORD *)v35 = 0;
  DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(*a2, 0, v35);
  if ( DiagValue < 0 )
  {
    v7 = 634;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)DiagValue,
      lpReserved);
LABEL_4:
    if ( v35[1] )
      std::_Ref_count_base::_Decref(v35[1]);
    v8 = (std::_Ref_count_base *)a2[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    return (unsigned int)DiagValue;
  }
  v10 = 0;
  v11 = (const unsigned __int16 *)((char *)v35[0] + 520);
  while ( 1 )
  {
    cchValueName = 260;
    cbData = 520;
    ValueName[0] = 0;
    *(_WORD *)Data = 0;
    Type = 0;
    v12 = RegEnumValueW(a3, v10, ValueName, &cchValueName, 0, &Type, 0, 0);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    v14 = v13 == 0;
    if ( v13 < 0 )
      goto LABEL_71;
    if ( Type == 1 )
    {
      lpData[0] = 260;
      v15 = RegEnumValueW(a3, v10, ValueName, lpData, 0, &Type, Data, &cbData);
      v13 = v15;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      if ( v13 >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 688;
            goto LABEL_3;
          }
        }
        else if ( ValueName[0] )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        ValueName,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 683;
            goto LABEL_3;
          }
        }
        goto LABEL_70;
      }
      if ( v13 != -2147024662 )
        goto LABEL_77;
      v16 = cbData >> 1;
      bstrString = SysAllocStringLen(0, (int)v16 + 1);
      p_bstrString = &bstrString;
      v41 = 1;
      lpData[0] = 260;
      v17 = RegEnumValueW(a3, v10, ValueName, lpData, 0, &Type, (LPBYTE)bstrString, &cbData);
      v13 = v17;
      if ( v17 > 0 )
        v13 = (unsigned __int16)v17 | 0x80070000;
      if ( v13 >= 0 )
      {
        bstrString[v16] = 0;
        if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11,
                        bstrString);
          if ( DiagValue < 0 )
          {
            v18 = 727;
            goto LABEL_30;
          }
        }
        else
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        ValueName,
                        bstrString);
          if ( DiagValue < 0 )
          {
            v18 = 723;
LABEL_30:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
              (const char *)(unsigned int)DiagValue,
              lpReserveda);
            SysFreeString(bstrString);
            goto LABEL_4;
          }
        }
      }
      v41 = 0;
      SysFreeString(bstrString);
      goto LABEL_70;
    }
    if ( Type == 4 )
    {
      v37[0] = 260;
      lpData[0] = 0;
      lpcbData = 4;
      v19 = RegEnumValueW(a3, v10, ValueName, v37, 0, &Type, (LPBYTE)lpData, &lpcbData);
      v13 = v19;
      if ( v19 > 0 )
        v13 = (unsigned __int16)v19 | 0x80070000;
      v14 = v13 == 0;
      if ( v13 >= 0 )
      {
        v20 = _o__itow_s(lpData[0], Data, 260, 10);
        DiagValue = v20;
        if ( v20 > 0 )
          DiagValue = (unsigned __int16)v20 | 0x80070000;
        if ( DiagValue < 0 )
        {
          v7 = 752;
          goto LABEL_3;
        }
        if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 762;
            goto LABEL_3;
          }
        }
        else
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        ValueName,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 758;
            goto LABEL_3;
          }
        }
        goto LABEL_70;
      }
      goto LABEL_71;
    }
    if ( Type != 11 )
      break;
    lpcbData = 260;
    *(_QWORD *)lpData = 0;
    v37[0] = 8;
    v21 = RegEnumValueW(a3, v10, ValueName, &lpcbData, 0, &Type, (LPBYTE)lpData, v37);
    v13 = v21;
    if ( v21 > 0 )
      v13 = (unsigned __int16)v21 | 0x80070000;
    v14 = v13 == 0;
    if ( v13 >= 0 )
    {
      v22 = _o__ui64tow_s(*(_QWORD *)lpData, Data, 260, 10);
      DiagValue = v22;
      if ( v22 > 0 )
        DiagValue = (unsigned __int16)v22 | 0x80070000;
      if ( DiagValue < 0 )
      {
        v7 = 785;
        goto LABEL_3;
      }
      if ( (unsigned int)_o__wcsicmp(v11, L"*") )
      {
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      v11,
                      (const unsigned __int16 *)Data);
        if ( DiagValue < 0 )
        {
          v7 = 795;
          goto LABEL_3;
        }
      }
      else
      {
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      ValueName,
                      (const unsigned __int16 *)Data);
        if ( DiagValue < 0 )
        {
          v7 = 791;
          goto LABEL_3;
        }
      }
      goto LABEL_70;
    }
LABEL_71:
    if ( !v14 )
      goto LABEL_77;
    ++v10;
  }
  if ( Type != 3 )
    goto LABEL_70;
  lpData[0] = 260;
  v23 = RegEnumValueW(a3, v10, ValueName, lpData, 0, 0, 0, &cbData);
  v24 = v23 < 0;
  if ( v23 > 0 )
    v24 = 1;
  if ( !v24 )
  {
    v25 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)std::nothrow);
    *(_QWORD *)v37 = v25;
    lpData[0] = 260;
    v26 = RegEnumValueW(a3, v10, ValueName, lpData, 0, 0, v25, &cbData);
    v13 = v26;
    if ( v26 > 0 )
      v13 = (unsigned __int16)v26 | 0x80070000;
    if ( v13 >= 0 )
    {
      if ( (unsigned int)_o__wcsicmp(v11, L"*") )
      {
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      v11,
                      v25,
                      cbData);
        if ( DiagValue < 0 )
        {
          v27 = 841;
          goto LABEL_67;
        }
      }
      else
      {
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      ValueName,
                      v25,
                      cbData);
        if ( DiagValue < 0 )
        {
          v27 = 837;
LABEL_67:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
            (const char *)(unsigned int)DiagValue,
            lpReservedb);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v37);
          goto LABEL_4;
        }
      }
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v37);
LABEL_70:
    v14 = v13 == 0;
    goto LABEL_71;
  }
LABEL_77:
  if ( v35[1] )
    std::_Ref_count_base::_Decref(v35[1]);
  v28 = (std::_Ref_count_base *)a2[1];
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  return 0;
}

```

## disassembly

```asm
0x180125208  mov     [rsp-8+arg_18], rbx
0x18012520d  push    rbp
0x18012520e  push    rsi
0x18012520f  push    rdi
0x180125210  push    r12
0x180125212  push    r13
0x180125214  push    r14
0x180125216  push    r15
0x180125218  lea     rbp, [rsp-3D0h]
0x180125220  sub     rsp, 4D0h
0x180125227  mov     rax, cs:__security_cookie
0x18012522e  xor     rax, rsp
0x180125231  mov     [rbp+400h+var_40], rax
0x180125238  mov     r13, r8
0x18012523b  mov     rsi, rdx
0x18012523e  mov     r15, rcx
0x180125241  mov     [rbp+400h+var_470], rdx
0x180125245  mov     ebx, 208h
0x18012524a  mov     r8d, ebx; Size
0x18012524d  xor     edx, edx; Val
0x18012524f  lea     rcx, [rbp+400h+ValueName]; void *
0x180125253  call    memset_0
0x180125258  mov     [rsp+500h+cchValueName], 104h
0x180125260  mov     r8d, ebx; Size
0x180125263  xor     edx, edx; Val
0x180125265  lea     rcx, [rbp+400h+Data]; void *
0x18012526c  call    memset_0
0x180125271  mov     [rsp+500h+cbData], ebx
0x180125275  xorps   xmm0, xmm0
0x180125278  movdqu  xmmword ptr [rsp+500h+var_4B0], xmm0
0x18012527e  lea     r8, [rsp+500h+var_4B0]
0x180125283  xor     edx, edx
0x180125285  mov     rcx, [rsi]
0x180125288  call    ?GetDiagValue@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJ_KPEAV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(unsigned __int64,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue> *)
0x18012528d  mov     ebx, eax
0x18012528f  test    eax, eax
0x180125291  jns     short loc_1801252D4
0x180125293  mov     edx, 27Ah; void *
0x180125298  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012529f  mov     r9d, ebx; char *
0x1801252a2  mov     rcx, [rbp+408h]; this
0x1801252a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801252ae  nop
0x1801252af  mov     rcx, [rsp+500h+var_4B0+8]; this
0x1801252b4  test    rcx, rcx
0x1801252b7  jz      short loc_1801252BF
0x1801252b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801252be  nop
0x1801252bf  mov     rcx, [rsi+8]; this
0x1801252c3  test    rcx, rcx
0x1801252c6  jz      short loc_1801252CD
0x1801252c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801252cd  mov     eax, ebx
0x1801252cf  jmp     loc_1801258F6
0x1801252d4  xor     ebx, ebx
0x1801252d6  mov     r12d, ebx
0x1801252d9  mov     r14, [rsp+500h+var_4B0]
0x1801252de  add     r14, 208h
0x1801252e5  mov     [rsp+500h+cchValueName], 104h
0x1801252ed  mov     [rsp+500h+cbData], 208h
0x1801252f5  mov     [rbp+400h+ValueName], bx
0x1801252f9  mov     word ptr [rbp+400h+Data], bx
0x180125300  mov     [rsp+500h+Type], ebx
0x180125304  mov     [rsp+500h+lpcbData], rbx; lpcbData
0x180125309  mov     [rsp+500h+lpData], rbx; lpData
0x18012530e  lea     rax, [rsp+500h+Type]
0x180125313  mov     [rsp+500h+lpType], rax; lpType
0x180125318  mov     [rsp+500h+lpReserved], rbx; lpReserved
0x18012531d  lea     r9, [rsp+500h+cchValueName]; lpcchValueName
0x180125322  lea     r8, [rbp+400h+ValueName]; lpValueName
0x180125326  mov     edx, r12d; dwIndex
0x180125329  mov     rcx, r13; hKey
0x18012532c  call    cs:__imp_RegEnumValueW
0x180125333  nop     dword ptr [rax+rax+00h]
0x180125338  mov     edi, eax
0x18012533a  test    eax, eax
0x18012533c  jle     short loc_180125347
0x18012533e  movzx   edi, ax
0x180125341  or      edi, 80070000h
0x180125347  test    edi, edi
0x180125349  js      loc_1801258A7
0x18012534f  mov     eax, [rsp+500h+Type]
0x180125353  cmp     eax, 1
0x180125356  jnz     loc_180125554
0x18012535c  mov     [rsp+500h+var_4B8], 104h
0x180125364  lea     rax, [rsp+500h+cbData]
0x180125369  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18012536e  lea     rax, [rbp+400h+Data]
0x180125375  mov     [rsp+500h+lpData], rax; lpData
0x18012537a  lea     rax, [rsp+500h+Type]
0x18012537f  mov     [rsp+500h+lpType], rax; lpType
0x180125384  mov     [rsp+500h+lpReserved], rbx; lpReserved
0x180125389  lea     r9, [rsp+500h+var_4B8]; lpcchValueName
0x18012538e  lea     r8, [rbp+400h+ValueName]; lpValueName
0x180125392  mov     edx, r12d; dwIndex
0x180125395  mov     rcx, r13; hKey
0x180125398  call    cs:__imp_RegEnumValueW
0x18012539f  nop     dword ptr [rax+rax+00h]
0x1801253a4  mov     edi, eax
0x1801253a6  test    eax, eax
0x1801253a8  jle     short loc_1801253B3
0x1801253aa  movzx   edi, ax
0x1801253ad  or      edi, 80070000h
0x1801253b3  test    edi, edi
0x1801253b5  js      short loc_180125428
0x1801253b7  lea     rdx, Delimiter; "*"
0x1801253be  mov     rcx, r14
0x1801253c1  call    cs:__imp__o__wcsicmp
0x1801253c8  nop     dword ptr [rax+rax+00h]
0x1801253cd  test    eax, eax
0x1801253cf  jnz     short loc_180125402
0x1801253d1  cmp     [rbp+400h+ValueName], bx
0x1801253d5  jz      loc_1801258A5
0x1801253db  lea     r8, [rbp+400h+Data]; unsigned __int16 *
0x1801253e2  lea     rdx, [rbp+400h+ValueName]; unsigned __int16 *
0x1801253e6  mov     rcx, r15; this
0x1801253e9  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x1801253ee  mov     ebx, eax
0x1801253f0  test    eax, eax
0x1801253f2  jns     loc_1801258A3
0x1801253f8  mov     edx, 2ABh
0x1801253fd  jmp     loc_180125298
0x180125402  lea     r8, [rbp+400h+Data]; unsigned __int16 *
0x180125409  mov     rdx, r14; unsigned __int16 *
0x18012540c  mov     rcx, r15; this
0x18012540f  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180125414  mov     ebx, eax
0x180125416  test    eax, eax
0x180125418  jns     loc_1801258A3
0x18012541e  mov     edx, 2B0h
0x180125423  jmp     loc_180125298
0x180125428  cmp     edi, 800700EAh
0x18012542e  jnz     loc_1801258D6
0x180125434  mov     ebx, [rsp+500h+cbData]
0x180125438  shr     ebx, 1
0x18012543a  lea     edx, [rbx+1]; ui
0x18012543d  xor     ecx, ecx; strIn
0x18012543f  call    cs:__imp_SysAllocStringLen
0x180125446  nop     dword ptr [rax+rax+00h]
0x18012544b  mov     [rsp+500h+bstrString], rax
0x180125450  lea     rcx, [rsp+500h+bstrString]
0x180125455  mov     [rbp+400h+var_480], rcx
0x180125459  mov     [rbp+400h+var_478], 1
0x18012545d  mov     [rsp+500h+var_4B8], 104h
0x180125465  lea     rcx, [rsp+500h+cbData]
0x18012546a  mov     [rsp+500h+lpcbData], rcx; lpcbData
0x18012546f  mov     [rsp+500h+lpData], rax; lpData
0x180125474  lea     rax, [rsp+500h+Type]
0x180125479  mov     [rsp+500h+lpType], rax; lpType
0x18012547e  mov     [rsp+500h+lpReserved], 0; int
0x180125487  lea     r9, [rsp+500h+var_4B8]; lpcchValueName
0x18012548c  lea     r8, [rbp+400h+ValueName]; lpValueName
0x180125490  mov     edx, r12d; dwIndex
0x180125493  mov     rcx, r13; hKey
0x180125496  call    cs:__imp_RegEnumValueW
0x18012549d  nop     dword ptr [rax+rax+00h]
0x1801254a2  mov     edi, eax
0x1801254a4  test    eax, eax
0x1801254a6  jle     short loc_1801254B1
0x1801254a8  movzx   edi, ax
0x1801254ab  or      edi, 80070000h
0x1801254b1  test    edi, edi
0x1801254b3  js      loc_180125539
0x1801254b9  xor     ecx, ecx
0x1801254bb  mov     rax, [rsp+500h+bstrString]
0x1801254c0  mov     [rax+rbx*2], cx
0x1801254c4  lea     rdx, Delimiter; "*"
0x1801254cb  mov     rcx, r14
0x1801254ce  call    cs:__imp__o__wcsicmp
0x1801254d5  nop     dword ptr [rax+rax+00h]
0x1801254da  mov     r8, [rsp+500h+bstrString]; unsigned __int16 *
0x1801254df  mov     rcx, r15; this
0x1801254e2  test    eax, eax
0x1801254e4  jnz     short loc_180125527
0x1801254e6  lea     rdx, [rbp+400h+ValueName]; unsigned __int16 *
0x1801254ea  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x1801254ef  mov     ebx, eax
0x1801254f1  test    eax, eax
0x1801254f3  jns     short loc_180125539
0x1801254f5  mov     edx, 2D3h; void *
0x1801254fa  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125501  mov     r9d, ebx; char *
0x180125504  mov     rcx, [rbp+408h]; this
0x18012550b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125510  nop
0x180125511  mov     rcx, [rsp+500h+bstrString]; bstrString
0x180125516  call    cs:__imp_SysFreeString
0x18012551d  nop     dword ptr [rax+rax+00h]
0x180125522  jmp     loc_1801252AF
0x180125527  mov     rdx, r14; unsigned __int16 *
0x18012552a  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x18012552f  mov     ebx, eax
0x180125531  test    eax, eax
0x180125533  js      loc_1801258B1
0x180125539  xor     ebx, ebx
0x18012553b  mov     [rbp+400h+var_478], bl
0x18012553e  mov     rcx, [rsp+500h+bstrString]; bstrString
0x180125543  call    cs:__imp_SysFreeString
0x18012554a  nop     dword ptr [rax+rax+00h]
0x18012554f  jmp     loc_1801258A5
0x180125554  cmp     eax, 4
0x180125557  jnz     loc_180125659
0x18012555d  mov     [rsp+500h+var_498], 104h
0x180125565  mov     [rsp+500h+var_4B8], ebx
0x180125569  mov     [rsp+500h+var_4A0], eax
0x18012556d  lea     rax, [rsp+500h+var_4A0]
0x180125572  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180125577  lea     rax, [rsp+500h+var_4B8]
0x18012557c  mov     [rsp+500h+lpData], rax; lpData
0x180125581  lea     rax, [rsp+500h+Type]
0x180125586  mov     [rsp+500h+lpType], rax; lpType
0x18012558b  mov     [rsp+500h+lpReserved], rbx; lpReserved
0x180125590  lea     r9, [rsp+500h+var_498]; lpcchValueName
0x180125595  lea     r8, [rbp+400h+ValueName]; lpValueName
0x180125599  mov     edx, r12d; dwIndex
0x18012559c  mov     rcx, r13; hKey
0x18012559f  call    cs:__imp_RegEnumValueW
0x1801255a6  nop     dword ptr [rax+rax+00h]
0x1801255ab  mov     edi, eax
0x1801255ad  test    eax, eax
0x1801255af  jle     short loc_1801255BA
0x1801255b1  movzx   edi, ax
0x1801255b4  or      edi, 80070000h
0x1801255ba  test    edi, edi
0x1801255bc  js      loc_1801258A7
0x1801255c2  mov     r9d, 0Ah
0x1801255c8  mov     r8d, 104h
0x1801255ce  lea     rdx, [rbp+400h+Data]
0x1801255d5  mov     ecx, [rsp+500h+var_4B8]
0x1801255d9  call    cs:__imp__o__itow_s
0x1801255e0  nop     dword ptr [rax+rax+00h]
0x1801255e5  mov     ebx, eax
0x1801255e7  test    eax, eax
0x1801255e9  jle     short loc_1801255F4
0x1801255eb  movzx   ebx, ax
0x1801255ee  or      ebx, 80070000h
0x1801255f4  test    ebx, ebx
0x1801255f6  js      loc_1801258BB
0x1801255fc  lea     rdx, Delimiter; "*"
0x180125603  mov     rcx, r14
0x180125606  call    cs:__imp__o__wcsicmp
0x18012560d  nop     dword ptr [rax+rax+00h]
0x180125612  lea     r8, [rbp+400h+Data]; unsigned __int16 *
0x180125619  mov     rcx, r15; this
0x18012561c  test    eax, eax
0x18012561e  jnz     short loc_18012563D
0x180125620  lea     rdx, [rbp+400h+ValueName]; unsigned __int16 *
0x180125624  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180125629  mov     ebx, eax
0x18012562b  test    eax, eax
0x18012562d  jns     loc_1801258A3
0x180125633  mov     edx, 2F6h
0x180125638  jmp     loc_180125298
0x18012563d  mov     rdx, r14; unsigned __int16 *
0x180125640  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180125645  mov     ebx, eax
0x180125647  test    eax, eax
0x180125649  jns     loc_1801258A3
0x18012564f  mov     edx, 2FAh
0x180125654  jmp     loc_180125298
0x180125659  cmp     eax, 0Bh
0x18012565c  jnz     loc_180125764
0x180125662  mov     [rsp+500h+var_4A0], 104h
0x18012566a  mov     qword ptr [rsp+500h+var_4B8], rbx
0x18012566f  mov     [rsp+500h+var_498], 8
0x180125677  lea     rax, [rsp+500h+var_498]
0x18012567c  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180125681  lea     rax, [rsp+500h+var_4B8]
0x180125686  mov     [rsp+500h+lpData], rax; lpData
0x18012568b  lea     rax, [rsp+500h+Type]
0x180125690  mov     [rsp+500h+lpType], rax; lpType
0x180125695  mov     [rsp+500h+lpReserved], rbx; lpReserved
0x18012569a  lea     r9, [rsp+500h+var_4A0]; lpcchValueName
0x18012569f  lea     r8, [rbp+400h+ValueName]; lpValueName
0x1801256a3  mov     edx, r12d; dwIndex
0x1801256a6  mov     rcx, r13; hKey
0x1801256a9  call    cs:__imp_RegEnumValueW
0x1801256b0  nop     dword ptr [rax+rax+00h]
0x1801256b5  mov     edi, eax
0x1801256b7  test    eax, eax
0x1801256b9  jle     short loc_1801256C4
0x1801256bb  movzx   edi, ax
0x1801256be  or      edi, 80070000h
0x1801256c4  test    edi, edi
0x1801256c6  js      loc_1801258A7
0x1801256cc  mov     r9d, 0Ah
0x1801256d2  mov     r8d, 104h
0x1801256d8  lea     rdx, [rbp+400h+Data]
0x1801256df  mov     rcx, qword ptr [rsp+500h+var_4B8]
0x1801256e4  call    cs:__imp__o__ui64tow_s
0x1801256eb  nop     dword ptr [rax+rax+00h]
0x1801256f0  mov     ebx, eax
0x1801256f2  test    eax, eax
0x1801256f4  jle     short loc_1801256FF
0x1801256f6  movzx   ebx, ax
0x1801256f9  or      ebx, 80070000h
0x1801256ff  test    ebx, ebx
0x180125701  js      loc_1801258C5
0x180125707  lea     rdx, Delimiter; "*"
0x18012570e  mov     rcx, r14
  ... truncated ...
```
