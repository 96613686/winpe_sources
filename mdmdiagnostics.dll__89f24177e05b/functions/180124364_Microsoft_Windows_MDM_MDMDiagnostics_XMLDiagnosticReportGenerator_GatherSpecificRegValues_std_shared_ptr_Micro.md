# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherSpecificRegValues(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)

- ea: `0x180124364`
- end: `0x18012491f`
- name: `?GatherSpecificRegValues@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this, _QWORD *, HKEY)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180124208`

## callees

- `0x180019000`
- `0x18001981c`
- `0x180019fc4`
- `0x1800ece5c`
- `0x1800ed730`
- `0x1800ee898`
- `0x180107e60`
- `0x1801236f4`
- `0x180124364`
- `0x180125748`
- `0x1801257d8`
- `0x180125b18`
- `0x180125bc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180124618`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180124618`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801246c5`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801246c5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180124500`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180124500`
- `OLEAUT32!__imp_SysFreeString` at `0x180124595`
- `OLEAUT32!__imp_SysFreeString` at `0x1801245ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180124595`
- `OLEAUT32!__imp_SysFreeString` at `0x1801245ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124455`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012449d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801245ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124696`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801247bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124809`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124455`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012449d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801245ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124696`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801247bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180124809`

## string_xrefs

- `0x1801243c1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x18012457e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180124848`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x1801248f9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherSpecificRegValues(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        _QWORD *a2,
        HKEY a3)
{
  int ValueCount; // eax
  signed int DiagValue; // ebx
  std::_Ref_count_base *v8; // rcx
  __int64 v10; // r12
  LPCWSTR v11; // rsi
  LSTATUS v12; // eax
  bool v13; // zf
  int v14; // eax
  bool v15; // sf
  __int64 v16; // rdx
  __int64 v17; // rbx
  LSTATUS v18; // eax
  bool v19; // sf
  int v20; // eax
  LSTATUS v21; // eax
  bool v22; // sf
  bool v23; // sf
  LSTATUS v24; // eax
  bool v25; // sf
  bool v26; // sf
  unsigned int v27; // r8d
  LSTATUS v28; // eax
  bool v29; // sf
  BYTE *v30; // rbx
  LSTATUS v31; // eax
  bool v32; // sf
  int v33; // eax
  std::_Ref_count_base *v34; // rcx
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  LPCWSTR lpValueName[2]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v39[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v43; // [rsp+70h] [rbp-90h]
  _QWORD *v44; // [rsp+78h] [rbp-88h]
  unsigned __int16 v45[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Data[259]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v47; // [rsp+2D6h] [rbp+1D6h]
  unsigned __int16 v48[256]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v44 = a2;
  v42[0] = 0;
  ValueCount = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetValueCount(
                 (Microsoft::Windows::MDM::MDMDiagnostics::DiagKey *)*a2,
                 v42);
  DiagValue = ValueCount;
  if ( ValueCount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)ValueCount,
      lpData);
LABEL_3:
    v8 = (std::_Ref_count_base *)a2[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    return (unsigned int)DiagValue;
  }
  v10 = 0;
  if ( v42[0] )
  {
    while ( 1 )
    {
      memset_0(Data, 0, 0x208u);
      cbData = 520;
      Type = 0;
      *(_OWORD *)lpValueName = 0;
      DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(*a2, v10, lpValueName);
      if ( DiagValue < 0 )
        break;
      v11 = lpValueName[0];
      v12 = RegQueryValueExW(a3, lpValueName[0], 0, &Type, 0, 0);
      v13 = v12 == 0;
      if ( v12 > 0 )
        v13 = 0;
      if ( v13 )
      {
        switch ( Type )
        {
          case 1u:
            v14 = RegQueryValueExW(a3, v11, 0, &Type, (LPBYTE)Data, &cbData);
            v15 = v14 < 0;
            if ( v14 > 0 )
            {
              v14 = (unsigned __int16)v14 | 0x80070000;
              v15 = v14 < 0;
            }
            if ( v15 )
            {
              if ( v14 == -2147024662 )
              {
                v17 = cbData >> 1;
                cbData = 2 * (v17 + 1);
                bstrString = SysAllocStringLen(0, (int)v17 + 1);
                v42[1] = (unsigned __int64)&bstrString;
                v43 = 1;
                v18 = RegQueryValueExW(a3, v11, 0, &Type, (LPBYTE)bstrString, &cbData);
                v19 = v18 < 0;
                if ( v18 > 0 )
                  v19 = 1;
                if ( !v19 )
                {
                  bstrString[v17] = 0;
                  v20 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                          this,
                          v11 + 260,
                          bstrString);
                  DiagValue = v20;
                  if ( v20 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x21A,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
                      (const char *)(unsigned int)v20,
                      lpData);
                    SysFreeString(bstrString);
                    goto LABEL_69;
                  }
                }
                v43 = 0;
                SysFreeString(bstrString);
              }
            }
            else
            {
              v47 = 0;
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                            this,
                            v11 + 260,
                            Data);
              if ( DiagValue < 0 )
              {
                v16 = 510;
                goto LABEL_68;
              }
            }
            break;
          case 4u:
            *(_DWORD *)v39 = 0;
            lpcbData[0] = 4;
            v21 = RegQueryValueExW(a3, v11, 0, &Type, v39, lpcbData);
            v22 = v21 < 0;
            if ( v21 > 0 )
              v22 = 1;
            if ( !v22 )
            {
              DiagValue = _o__itow_s(*(unsigned int *)v39, Data, 260, 10);
              v23 = DiagValue < 0;
              if ( DiagValue > 0 )
              {
                DiagValue = (unsigned __int16)DiagValue | 0x80070000;
                v23 = DiagValue < 0;
              }
              if ( v23 )
              {
                v16 = 559;
                goto LABEL_68;
              }
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                            this,
                            v11 + 260,
                            Data);
              if ( DiagValue < 0 )
              {
                v16 = 561;
                goto LABEL_68;
              }
            }
            break;
          case 0xBu:
            *(_QWORD *)v39 = 0;
            lpcbData[0] = 8;
            v24 = RegQueryValueExW(a3, v11, 0, &Type, v39, lpcbData);
            v25 = v24 < 0;
            if ( v24 > 0 )
              v25 = 1;
            if ( !v25 )
            {
              DiagValue = _o__ui64tow_s(*(_QWORD *)v39, Data, 260, 10);
              v26 = DiagValue < 0;
              if ( DiagValue > 0 )
              {
                DiagValue = (unsigned __int16)DiagValue | 0x80070000;
                v26 = DiagValue < 0;
              }
              if ( v26 )
              {
                v16 = 581;
                goto LABEL_68;
              }
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                            this,
                            v11 + 260,
                            Data);
              if ( DiagValue < 0 )
              {
                v16 = 583;
                goto LABEL_68;
              }
              memset_0(v45, 0, sizeof(v45));
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::FormatQwordTimestamp(
                            *(unsigned __int64 *)v39,
                            v45,
                            v27);
              if ( DiagValue < 0 )
              {
                v16 = 586;
                goto LABEL_68;
              }
              if ( v45[0] )
              {
                memset_0(v48, 0, sizeof(v48));
                DiagValue = StringCchPrintfW(v48, 0x100u, L"%sFriendly", v11 + 260);
                if ( DiagValue < 0 )
                {
                  v16 = 590;
                  goto LABEL_68;
                }
                DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                              this,
                              v48,
                              v45);
                if ( DiagValue < 0 )
                {
                  v16 = 591;
                  goto LABEL_68;
                }
              }
            }
            break;
          case 3u:
            v28 = RegQueryValueExW(a3, v11, 0, 0, 0, &cbData);
            v29 = v28 < 0;
            if ( v28 > 0 )
              v29 = 1;
            if ( !v29 )
            {
              v30 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)std::nothrow);
              *(_QWORD *)lpcbData = v30;
              v31 = RegQueryValueExW(a3, v11, 0, 0, v30, &cbData);
              v32 = v31 < 0;
              if ( v31 > 0 )
                v32 = 1;
              if ( !v32 )
              {
                v33 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11 + 260,
                        v30,
                        cbData);
                DiagValue = v33;
                if ( v33 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x26F,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
                    (const char *)(unsigned int)v33,
                    lpData);
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(lpcbData);
                  goto LABEL_69;
                }
              }
              std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(lpcbData);
            }
            break;
        }
      }
      if ( lpValueName[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpValueName[1]);
      if ( ++v10 >= v42[0] )
        goto LABEL_59;
    }
    v16 = 477;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)DiagValue,
      lpData);
LABEL_69:
    if ( lpValueName[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpValueName[1]);
    goto LABEL_3;
  }
LABEL_59:
  v34 = (std::_Ref_count_base *)a2[1];
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  return 0;
}

```

## disassembly

```asm
0x180124364  push    rbp
0x180124366  push    rbx
0x180124367  push    rsi
0x180124368  push    rdi
0x180124369  push    r12
0x18012436b  push    r14
0x18012436d  push    r15
0x18012436f  lea     rbp, [rsp-3F0h]
0x180124377  sub     rsp, 4F0h
0x18012437e  mov     rax, cs:__security_cookie
0x180124385  xor     rax, rsp
0x180124388  mov     [rbp+420h+var_40], rax
0x18012438f  mov     r15, r8
0x180124392  mov     rdi, rdx
0x180124395  mov     r14, rcx
0x180124398  mov     [rsp+520h+var_4A8], rdx
0x18012439d  xor     esi, esi
0x18012439f  mov     [rsp+520h+var_4C0], rsi
0x1801243a4  lea     rdx, [rsp+520h+var_4C0]; unsigned __int64 *
0x1801243a9  mov     rcx, [rdi]; this
0x1801243ac  call    ?GetValueCount@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJPEA_K@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetValueCount(unsigned __int64 *)
0x1801243b1  mov     ebx, eax
0x1801243b3  test    eax, eax
0x1801243b5  jns     short loc_1801243E8
0x1801243b7  mov     rcx, [rbp+428h]; this
0x1801243be  mov     r9d, eax; char *
0x1801243c1  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801243c8  mov     edx, 1D2h; void *
0x1801243cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801243d2  nop
0x1801243d3  mov     rcx, [rdi+8]; this
0x1801243d7  test    rcx, rcx
0x1801243da  jz      short loc_1801243E1
0x1801243dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801243e1  mov     eax, ebx
0x1801243e3  jmp     loc_1801248A6
0x1801243e8  mov     r12, rsi
0x1801243eb  cmp     [rsp+520h+var_4C0], rsi
0x1801243f0  jbe     loc_180124896
0x1801243f6  xor     edx, edx; Val
0x1801243f8  mov     r8d, 208h; Size
0x1801243fe  lea     rcx, [rbp+420h+Data]; void *
0x180124402  call    memset_0
0x180124407  mov     [rsp+520h+cbData], 208h
0x18012440f  mov     [rsp+520h+Type], esi
0x180124413  xorps   xmm0, xmm0
0x180124416  movdqu  xmmword ptr [rsp+520h+lpValueName], xmm0
0x18012441c  lea     r8, [rsp+520h+lpValueName]
0x180124421  mov     rdx, r12
0x180124424  mov     rcx, [rdi]
0x180124427  call    ?GetDiagValue@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJ_KPEAV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(unsigned __int64,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue> *)
0x18012442c  mov     ebx, eax
0x18012442e  test    eax, eax
0x180124430  js      loc_1801248EA
0x180124436  mov     rsi, [rsp+520h+lpValueName]
0x18012443b  xor     ebx, ebx
0x18012443d  mov     [rsp+520h+lpcbData], rbx; lpcbData
0x180124442  mov     [rsp+520h+lpData], rbx; lpData
0x180124447  lea     r9, [rsp+520h+Type]; lpType
0x18012444c  xor     r8d, r8d; lpReserved
0x18012444f  mov     rdx, rsi; lpValueName
0x180124452  mov     rcx, r15; hKey
0x180124455  call    cs:__imp_RegQueryValueExW
0x18012445b  test    eax, eax
0x18012445d  jle     short loc_180124469
0x18012445f  movzx   eax, ax
0x180124462  or      eax, 80070000h
0x180124467  test    eax, eax
0x180124469  jnz     loc_180124877
0x18012446f  mov     eax, [rsp+520h+Type]
0x180124473  cmp     eax, 1
0x180124476  jnz     loc_1801245B7
0x18012447c  lea     rax, [rsp+520h+cbData]
0x180124481  mov     [rsp+520h+lpcbData], rax; lpcbData
0x180124486  lea     rax, [rbp+420h+Data]
0x18012448a  mov     [rsp+520h+lpData], rax; lpData
0x18012448f  lea     r9, [rsp+520h+Type]; lpType
0x180124494  xor     r8d, r8d; lpReserved
0x180124497  mov     rdx, rsi; lpValueName
0x18012449a  mov     rcx, r15; hKey
0x18012449d  call    cs:__imp_RegQueryValueExW
0x1801244a3  test    eax, eax
0x1801244a5  jle     short loc_1801244B1
0x1801244a7  movzx   eax, ax
0x1801244aa  or      eax, 80070000h
0x1801244af  test    eax, eax
0x1801244b1  js      short loc_1801244E3
0x1801244b3  mov     [rbp+420h+var_24A], bx
0x1801244ba  lea     rdx, [rsi+208h]; unsigned __int16 *
0x1801244c1  lea     r8, [rbp+420h+Data]; unsigned __int16 *
0x1801244c5  mov     rcx, r14; this
0x1801244c8  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x1801244cd  mov     ebx, eax
0x1801244cf  xor     esi, esi
0x1801244d1  test    eax, eax
0x1801244d3  jns     loc_180124879
0x1801244d9  mov     edx, 1FEh
0x1801244de  jmp     loc_1801248EF
0x1801244e3  cmp     eax, 800700EAh
0x1801244e8  jnz     loc_180124877
0x1801244ee  mov     ebx, [rsp+520h+cbData]
0x1801244f2  shr     ebx, 1
0x1801244f4  lea     edx, [rbx+1]; ui
0x1801244f7  lea     eax, [rdx+rdx]
0x1801244fa  mov     [rsp+520h+cbData], eax
0x1801244fe  xor     ecx, ecx; strIn
0x180124500  call    cs:__imp_SysAllocStringLen
0x180124506  mov     [rsp+520h+bstrString], rax
0x18012450b  lea     rcx, [rsp+520h+bstrString]
0x180124510  mov     [rsp+520h+var_4B8], rcx
0x180124515  mov     [rsp+520h+var_4B0], 1
0x18012451a  lea     rcx, [rsp+520h+cbData]
0x18012451f  mov     [rsp+520h+lpcbData], rcx; lpcbData
0x180124524  mov     [rsp+520h+lpData], rax; int
0x180124529  lea     r9, [rsp+520h+Type]; lpType
0x18012452e  xor     r8d, r8d; lpReserved
0x180124531  mov     rdx, rsi; lpValueName
0x180124534  mov     rcx, r15; hKey
0x180124537  call    cs:__imp_RegQueryValueExW
0x18012453d  xor     ecx, ecx
0x18012453f  test    eax, eax
0x180124541  jle     short loc_18012454D
0x180124543  movzx   eax, ax
0x180124546  or      eax, 80070000h
0x18012454b  test    eax, eax
0x18012454d  js      short loc_1801245A0
0x18012454f  mov     rax, [rsp+520h+bstrString]
0x180124554  mov     [rax+rbx*2], cx
0x180124558  lea     rdx, [rsi+208h]; unsigned __int16 *
0x18012455f  mov     r8, [rsp+520h+bstrString]; unsigned __int16 *
0x180124564  mov     rcx, r14; this
0x180124567  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x18012456c  mov     ebx, eax
0x18012456e  xor     esi, esi
0x180124570  test    eax, eax
0x180124572  jns     short loc_1801245A2
0x180124574  mov     rcx, [rbp+428h]; this
0x18012457b  mov     r9d, eax; char *
0x18012457e  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180124585  mov     edx, 21Ah; void *
0x18012458a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012458f  nop
0x180124590  mov     rcx, [rsp+520h+bstrString]; bstrString
0x180124595  call    cs:__imp_SysFreeString
0x18012459b  jmp     loc_180124906
0x1801245a0  xor     esi, esi
0x1801245a2  mov     [rsp+520h+var_4B0], sil
0x1801245a7  mov     rcx, [rsp+520h+bstrString]; bstrString
0x1801245ac  call    cs:__imp_SysFreeString
0x1801245b2  jmp     loc_180124879
0x1801245b7  cmp     eax, 4
0x1801245ba  jnz     loc_18012465E
0x1801245c0  mov     dword ptr [rsp+520h+var_4D8], ebx
0x1801245c4  mov     [rsp+520h+var_4D0], eax
0x1801245c8  lea     rax, [rsp+520h+var_4D0]
0x1801245cd  mov     [rsp+520h+lpcbData], rax; lpcbData
0x1801245d2  lea     rax, [rsp+520h+var_4D8]
0x1801245d7  mov     [rsp+520h+lpData], rax; lpData
0x1801245dc  lea     r9, [rsp+520h+Type]; lpType
0x1801245e1  xor     r8d, r8d; lpReserved
0x1801245e4  mov     rdx, rsi; lpValueName
0x1801245e7  mov     rcx, r15; hKey
0x1801245ea  call    cs:__imp_RegQueryValueExW
0x1801245f0  test    eax, eax
0x1801245f2  jle     short loc_1801245FE
0x1801245f4  movzx   eax, ax
0x1801245f7  or      eax, 80070000h
0x1801245fc  test    eax, eax
0x1801245fe  js      loc_180124877
0x180124604  mov     r9d, 0Ah
0x18012460a  mov     r8d, 104h
0x180124610  lea     rdx, [rbp+420h+Data]
0x180124614  mov     ecx, dword ptr [rsp+520h+var_4D8]
0x180124618  call    cs:__imp__o__itow_s
0x18012461e  mov     ebx, eax
0x180124620  test    eax, eax
0x180124622  jle     short loc_18012462F
0x180124624  movzx   ebx, bx
0x180124627  or      ebx, 80070000h
0x18012462d  test    ebx, ebx
0x18012462f  js      loc_1801248C7
0x180124635  lea     rdx, [rsi+208h]; unsigned __int16 *
0x18012463c  lea     r8, [rbp+420h+Data]; unsigned __int16 *
0x180124640  mov     rcx, r14; this
0x180124643  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180124648  mov     ebx, eax
0x18012464a  xor     esi, esi
0x18012464c  test    eax, eax
0x18012464e  jns     loc_180124879
0x180124654  mov     edx, 231h
0x180124659  jmp     loc_1801248EF
0x18012465e  cmp     eax, 0Bh
0x180124661  jnz     loc_180124798
0x180124667  mov     qword ptr [rsp+520h+var_4D8], rbx
0x18012466c  mov     [rsp+520h+var_4D0], 8
0x180124674  lea     rax, [rsp+520h+var_4D0]
0x180124679  mov     [rsp+520h+lpcbData], rax; lpcbData
0x18012467e  lea     rax, [rsp+520h+var_4D8]
0x180124683  mov     [rsp+520h+lpData], rax; lpData
0x180124688  lea     r9, [rsp+520h+Type]; lpType
0x18012468d  xor     r8d, r8d; lpReserved
0x180124690  mov     rdx, rsi; lpValueName
0x180124693  mov     rcx, r15; hKey
0x180124696  call    cs:__imp_RegQueryValueExW
0x18012469c  test    eax, eax
0x18012469e  jle     short loc_1801246AA
0x1801246a0  movzx   eax, ax
0x1801246a3  or      eax, 80070000h
0x1801246a8  test    eax, eax
0x1801246aa  js      loc_180124877
0x1801246b0  mov     r9d, 0Ah
0x1801246b6  mov     r8d, 104h
0x1801246bc  lea     rdx, [rbp+420h+Data]
0x1801246c0  mov     rcx, qword ptr [rsp+520h+var_4D8]
0x1801246c5  call    cs:__imp__o__ui64tow_s
0x1801246cb  mov     ebx, eax
0x1801246cd  test    eax, eax
0x1801246cf  jle     short loc_1801246DC
0x1801246d1  movzx   ebx, bx
0x1801246d4  or      ebx, 80070000h
0x1801246da  test    ebx, ebx
0x1801246dc  js      loc_1801248E3
0x1801246e2  lea     r8, [rbp+420h+Data]; unsigned __int16 *
0x1801246e6  lea     rdx, [rsi+208h]; unsigned __int16 *
0x1801246ed  mov     rcx, r14; this
0x1801246f0  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x1801246f5  mov     ebx, eax
0x1801246f7  test    eax, eax
0x1801246f9  js      loc_1801248DC
0x1801246ff  xor     edx, edx; Val
0x180124701  lea     r8d, [rdx+50h]; Size
0x180124705  lea     rcx, [rbp+420h+var_4A0]; void *
0x180124709  call    memset_0
0x18012470e  lea     rdx, [rbp+420h+var_4A0]; unsigned __int16 *
0x180124712  mov     rcx, qword ptr [rsp+520h+var_4D8]; unsigned __int64
0x180124717  call    ?FormatQwordTimestamp@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@CAJ_KPEAGK@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::FormatQwordTimestamp(unsigned __int64,ushort *,ulong)
0x18012471c  mov     ebx, eax
0x18012471e  xor     eax, eax
0x180124720  test    ebx, ebx
0x180124722  js      loc_1801248D5
0x180124728  cmp     [rbp+420h+var_4A0], ax
0x18012472c  jz      loc_180124877
0x180124732  xor     edx, edx; Val
0x180124734  mov     r8d, 200h; Size
0x18012473a  lea     rcx, [rbp+420h+var_240]; void *
0x180124741  call    memset_0
0x180124746  lea     r9, [rsi+208h]
0x18012474d  lea     r8, aSfriendly; "%sFriendly"
0x180124754  mov     edx, 100h; unsigned __int64
0x180124759  lea     rcx, [rbp+420h+var_240]; unsigned __int16 *
0x180124760  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180124765  mov     ebx, eax
0x180124767  xor     esi, esi
0x180124769  test    eax, eax
0x18012476b  js      loc_1801248CE
0x180124771  lea     r8, [rbp+420h+var_4A0]; unsigned __int16 *
0x180124775  lea     rdx, [rbp+420h+var_240]; unsigned __int16 *
0x18012477c  mov     rcx, r14; this
0x18012477f  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180124784  mov     ebx, eax
0x180124786  test    eax, eax
0x180124788  jns     loc_180124879
0x18012478e  mov     edx, 24Fh
0x180124793  jmp     loc_1801248EF
0x180124798  cmp     eax, 3
0x18012479b  jnz     loc_180124877
0x1801247a1  lea     rax, [rsp+520h+cbData]
0x1801247a6  mov     [rsp+520h+lpcbData], rax; lpcbData
0x1801247ab  mov     [rsp+520h+lpData], rbx; lpData
0x1801247b0  xor     r9d, r9d; lpType
0x1801247b3  xor     r8d, r8d; lpReserved
0x1801247b6  mov     rdx, rsi; lpValueName
0x1801247b9  mov     rcx, r15; hKey
0x1801247bc  call    cs:__imp_RegQueryValueExW
0x1801247c2  test    eax, eax
0x1801247c4  jle     short loc_1801247D0
0x1801247c6  movzx   eax, ax
0x1801247c9  or      eax, 80070000h
0x1801247ce  test    eax, eax
0x1801247d0  js      loc_180124877
0x1801247d6  mov     ecx, [rsp+520h+cbData]; unsigned __int64
0x1801247da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801247e1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801247e6  mov     rbx, rax
0x1801247e9  mov     qword ptr [rsp+520h+var_4D0], rax
0x1801247ee  lea     rax, [rsp+520h+cbData]
0x1801247f3  mov     [rsp+520h+lpcbData], rax; lpcbData
0x1801247f8  mov     [rsp+520h+lpData], rbx; int
0x1801247fd  xor     r9d, r9d; lpType
0x180124800  xor     r8d, r8d; lpReserved
0x180124803  mov     rdx, rsi; lpValueName
0x180124806  mov     rcx, r15; hKey
0x180124809  call    cs:__imp_RegQueryValueExW
0x18012480f  test    eax, eax
0x180124811  jle     short loc_18012481D
0x180124813  movzx   eax, ax
0x180124816  or      eax, 80070000h
0x18012481b  test    eax, eax
0x18012481d  js      short loc_180124869
0x18012481f  lea     rdx, [rsi+208h]; unsigned __int16 *
  ... truncated ...
```
