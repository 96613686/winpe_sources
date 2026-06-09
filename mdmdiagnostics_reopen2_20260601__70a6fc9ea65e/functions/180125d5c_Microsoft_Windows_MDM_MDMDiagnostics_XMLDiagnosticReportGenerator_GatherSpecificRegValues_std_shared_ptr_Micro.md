# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherSpecificRegValues(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)

- ea: `0x180125d5c`
- end: `0x1801262b0`
- name: `?GatherSpecificRegValues@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z`
- size: `1364`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `11`
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
- `0x180125d5c`
- `0x18012713c`
- `0x1801271cc`
- `0x180127510`
- `0x1801275c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180126014`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180126014`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801260cc`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1801260cc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180125f0f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180125f0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180125f9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180126206`
- `OLEAUT32!__imp_SysFreeString` at `0x180125f9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180126206`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125e59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125ea9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125f4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125fe3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012609a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012613e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012618a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125e59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125ea9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125f4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180125fe3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012609a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012613e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18012618a`

## string_xrefs

- `0x180125dbb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x1801261ef`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x18012622c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x18012624f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

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
  unsigned __int64 i; // r15
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
  int v23; // eax
  LSTATUS v24; // eax
  bool v25; // sf
  int v26; // eax
  LSTATUS v27; // eax
  bool v28; // sf
  BYTE *v29; // rbx
  LSTATUS v30; // eax
  bool v31; // sf
  int v32; // eax
  std::_Ref_count_base *v33; // rcx
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD lpcbData[2]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v41[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v42; // [rsp+70h] [rbp-90h]
  _QWORD *v43; // [rsp+78h] [rbp-88h]
  unsigned __int16 Data[259]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v45; // [rsp+286h] [rbp+186h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v43 = a2;
  v41[0] = 0;
  ValueCount = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetValueCount(
                 (Microsoft::Windows::MDM::MDMDiagnostics::DiagKey *)*a2,
                 v41);
  DiagValue = ValueCount;
  if ( ValueCount >= 0 )
  {
    for ( i = 0; i < v41[0]; ++i )
    {
      memset_0(Data, 0, 0x208u);
      cbData = 520;
      Type = 0;
      *(_OWORD *)lpValueName = 0;
      DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(*a2, i, lpValueName);
      if ( DiagValue < 0 )
      {
        v16 = 476;
        goto LABEL_59;
      }
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
                v41[1] = (unsigned __int64)&bstrString;
                v42 = 1;
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
                      (void *)0x219,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
                      (const char *)(unsigned int)v20,
                      lpData);
                    SysFreeString(bstrString);
                    goto LABEL_60;
                  }
                }
                v42 = 0;
                SysFreeString(bstrString);
              }
            }
            else
            {
              v45 = 0;
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                            this,
                            v11 + 260,
                            Data);
              if ( DiagValue < 0 )
              {
                v16 = 509;
LABEL_59:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v16,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
                  (const char *)(unsigned int)DiagValue,
                  lpData);
LABEL_60:
                if ( lpValueName[1] )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpValueName[1]);
                goto LABEL_3;
              }
            }
            break;
          case 4u:
            *(_DWORD *)v38 = 0;
            lpcbData[0] = 4;
            v21 = RegQueryValueExW(a3, v11, 0, &Type, v38, lpcbData);
            v22 = v21 < 0;
            if ( v21 > 0 )
              v22 = 1;
            if ( !v22 )
            {
              v23 = _o__itow_s(*(unsigned int *)v38, Data, 260, 10);
              DiagValue = v23;
              if ( v23 > 0 )
                DiagValue = (unsigned __int16)v23 | 0x80070000;
              if ( DiagValue < 0 )
              {
                v16 = 558;
                goto LABEL_59;
              }
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                            this,
                            v11 + 260,
                            Data);
              if ( DiagValue < 0 )
              {
                v16 = 560;
                goto LABEL_59;
              }
            }
            break;
          case 0xBu:
            *(_QWORD *)v38 = 0;
            lpcbData[0] = 8;
            v24 = RegQueryValueExW(a3, v11, 0, &Type, v38, lpcbData);
            v25 = v24 < 0;
            if ( v24 > 0 )
              v25 = 1;
            if ( !v25 )
            {
              v26 = _o__ui64tow_s(*(_QWORD *)v38, Data, 260, 10);
              DiagValue = v26;
              if ( v26 > 0 )
                DiagValue = (unsigned __int16)v26 | 0x80070000;
              if ( DiagValue < 0 )
              {
                v16 = 580;
                goto LABEL_59;
              }
              DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                            this,
                            v11 + 260,
                            Data);
              if ( DiagValue < 0 )
              {
                v16 = 582;
                goto LABEL_59;
              }
            }
            break;
          case 3u:
            v27 = RegQueryValueExW(a3, v11, 0, 0, 0, &cbData);
            v28 = v27 < 0;
            if ( v27 > 0 )
              v28 = 1;
            if ( !v28 )
            {
              v29 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)std::nothrow);
              *(_QWORD *)lpcbData = v29;
              v30 = RegQueryValueExW(a3, v11, 0, 0, v29, &cbData);
              v31 = v30 < 0;
              if ( v30 > 0 )
                v31 = 1;
              if ( !v31 )
              {
                v32 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11 + 260,
                        v29,
                        cbData);
                DiagValue = v32;
                if ( v32 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x265,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
                    (const char *)(unsigned int)v32,
                    lpData);
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(lpcbData);
                  goto LABEL_60;
                }
              }
              std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(lpcbData);
            }
            break;
        }
      }
      if ( lpValueName[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpValueName[1]);
    }
    v33 = (std::_Ref_count_base *)a2[1];
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)ValueCount,
      lpData);
LABEL_3:
    v8 = (std::_Ref_count_base *)a2[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    return (unsigned int)DiagValue;
  }
}

```

## disassembly

```asm
0x180125d5c  push    rbp
0x180125d5e  push    rbx
0x180125d5f  push    rsi
0x180125d60  push    rdi
0x180125d61  push    r12
0x180125d63  push    r14
0x180125d65  push    r15
0x180125d67  lea     rbp, [rsp-1A0h]
0x180125d6f  sub     rsp, 2A0h
0x180125d76  mov     rax, cs:__security_cookie
0x180125d7d  xor     rax, rsp
0x180125d80  mov     [rbp+1D0h+var_40], rax
0x180125d87  mov     r14, r8
0x180125d8a  mov     rdi, rdx
0x180125d8d  mov     r12, rcx
0x180125d90  mov     [rsp+2D0h+var_258], rdx
0x180125d95  mov     [rsp+2D0h+var_270], 0
0x180125d9e  lea     rdx, [rsp+2D0h+var_270]; unsigned __int64 *
0x180125da3  mov     rcx, [rdi]; this
0x180125da6  call    ?GetValueCount@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJPEA_K@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetValueCount(unsigned __int64 *)
0x180125dab  mov     ebx, eax
0x180125dad  test    eax, eax
0x180125daf  jns     short loc_180125DE2
0x180125db1  mov     rcx, [rbp+1D8h]; this
0x180125db8  mov     r9d, eax; char *
0x180125dbb  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125dc2  mov     edx, 1D1h; void *
0x180125dc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125dcc  nop
0x180125dcd  mov     rcx, [rdi+8]; this
0x180125dd1  test    rcx, rcx
0x180125dd4  jz      short loc_180125DDB
0x180125dd6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125ddb  mov     eax, ebx
0x180125ddd  jmp     loc_18012628E
0x180125de2  xor     r15d, r15d
0x180125de5  cmp     r15, [rsp+2D0h+var_270]
0x180125dea  jnb     loc_18012627E
0x180125df0  xor     edx, edx; Val
0x180125df2  mov     r8d, 208h; Size
0x180125df8  lea     rcx, [rbp+1D0h+Data]; void *
0x180125dfc  call    memset_0
0x180125e01  mov     [rsp+2D0h+cbData], 208h
0x180125e09  mov     [rsp+2D0h+Type], 0
0x180125e11  xorps   xmm0, xmm0
0x180125e14  movdqu  xmmword ptr [rsp+2D0h+lpValueName], xmm0
0x180125e1a  lea     r8, [rsp+2D0h+lpValueName]
0x180125e1f  mov     rdx, r15
0x180125e22  mov     rcx, [rdi]
0x180125e25  call    ?GetDiagValue@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJ_KPEAV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(unsigned __int64,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue> *)
0x180125e2a  mov     ebx, eax
0x180125e2c  test    eax, eax
0x180125e2e  js      loc_18012624A
0x180125e34  mov     rsi, [rsp+2D0h+lpValueName]
0x180125e39  mov     [rsp+2D0h+lpcbData], 0; lpcbData
0x180125e42  mov     [rsp+2D0h+lpData], 0; lpData
0x180125e4b  lea     r9, [rsp+2D0h+Type]; lpType
0x180125e50  xor     r8d, r8d; lpReserved
0x180125e53  mov     rdx, rsi; lpValueName
0x180125e56  mov     rcx, r14; hKey
0x180125e59  call    cs:__imp_RegQueryValueExW
0x180125e60  nop     dword ptr [rax+rax+00h]
0x180125e65  mov     ebx, 80070000h
0x180125e6a  test    eax, eax
0x180125e6c  jle     short loc_180125E75
0x180125e6e  movzx   eax, ax
0x180125e71  or      eax, ebx
0x180125e73  test    eax, eax
0x180125e75  jnz     loc_1801261CE
0x180125e7b  mov     eax, [rsp+2D0h+Type]
0x180125e7f  cmp     eax, 1
0x180125e82  jnz     loc_180125FAC
0x180125e88  lea     rax, [rsp+2D0h+cbData]
0x180125e8d  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180125e92  lea     rax, [rbp+1D0h+Data]
0x180125e96  mov     [rsp+2D0h+lpData], rax; lpData
0x180125e9b  lea     r9, [rsp+2D0h+Type]; lpType
0x180125ea0  xor     r8d, r8d; lpReserved
0x180125ea3  mov     rdx, rsi; lpValueName
0x180125ea6  mov     rcx, r14; hKey
0x180125ea9  call    cs:__imp_RegQueryValueExW
0x180125eb0  nop     dword ptr [rax+rax+00h]
0x180125eb5  test    eax, eax
0x180125eb7  jle     short loc_180125EC0
0x180125eb9  movzx   eax, ax
0x180125ebc  or      eax, ebx
0x180125ebe  test    eax, eax
0x180125ec0  js      short loc_180125EF2
0x180125ec2  xor     eax, eax
0x180125ec4  mov     [rbp+1D0h+var_4A], ax
0x180125ecb  lea     rdx, [rsi+208h]; unsigned __int16 *
0x180125ed2  lea     r8, [rbp+1D0h+Data]; unsigned __int16 *
0x180125ed6  mov     rcx, r12; this
0x180125ed9  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180125ede  mov     ebx, eax
0x180125ee0  test    eax, eax
0x180125ee2  jns     loc_1801261CE
0x180125ee8  mov     edx, 1FDh
0x180125eed  jmp     loc_18012624F
0x180125ef2  cmp     eax, 800700EAh
0x180125ef7  jnz     loc_1801261CE
0x180125efd  mov     ebx, [rsp+2D0h+cbData]
0x180125f01  shr     ebx, 1
0x180125f03  lea     edx, [rbx+1]; ui
0x180125f06  lea     eax, [rdx+rdx]
0x180125f09  mov     [rsp+2D0h+cbData], eax
0x180125f0d  xor     ecx, ecx; strIn
0x180125f0f  call    cs:__imp_SysAllocStringLen
0x180125f16  nop     dword ptr [rax+rax+00h]
0x180125f1b  mov     [rsp+2D0h+bstrString], rax
0x180125f20  lea     rcx, [rsp+2D0h+bstrString]
0x180125f25  mov     [rsp+2D0h+var_268], rcx
0x180125f2a  mov     [rsp+2D0h+var_260], 1
0x180125f2f  lea     rcx, [rsp+2D0h+cbData]
0x180125f34  mov     [rsp+2D0h+lpcbData], rcx; lpcbData
0x180125f39  mov     [rsp+2D0h+lpData], rax; int
0x180125f3e  lea     r9, [rsp+2D0h+Type]; lpType
0x180125f43  xor     r8d, r8d; lpReserved
0x180125f46  mov     rdx, rsi; lpValueName
0x180125f49  mov     rcx, r14; hKey
0x180125f4c  call    cs:__imp_RegQueryValueExW
0x180125f53  nop     dword ptr [rax+rax+00h]
0x180125f58  test    eax, eax
0x180125f5a  jle     short loc_180125F66
0x180125f5c  movzx   eax, ax
0x180125f5f  or      eax, 80070000h
0x180125f64  test    eax, eax
0x180125f66  js      short loc_180125F91
0x180125f68  xor     ecx, ecx
0x180125f6a  mov     rax, [rsp+2D0h+bstrString]
0x180125f6f  mov     [rax+rbx*2], cx
0x180125f73  lea     rdx, [rsi+208h]; unsigned __int16 *
0x180125f7a  mov     r8, [rsp+2D0h+bstrString]; unsigned __int16 *
0x180125f7f  mov     rcx, r12; this
0x180125f82  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180125f87  mov     ebx, eax
0x180125f89  test    eax, eax
0x180125f8b  js      loc_1801261E5
0x180125f91  mov     [rsp+2D0h+var_260], 0
0x180125f96  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x180125f9b  call    cs:__imp_SysFreeString
0x180125fa2  nop     dword ptr [rax+rax+00h]
0x180125fa7  jmp     loc_1801261CE
0x180125fac  cmp     eax, 4
0x180125faf  jnz     loc_18012605E
0x180125fb5  mov     dword ptr [rsp+2D0h+var_290], 0
0x180125fbd  mov     [rsp+2D0h+var_298], eax
0x180125fc1  lea     rax, [rsp+2D0h+var_298]
0x180125fc6  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180125fcb  lea     rax, [rsp+2D0h+var_290]
0x180125fd0  mov     [rsp+2D0h+lpData], rax; lpData
0x180125fd5  lea     r9, [rsp+2D0h+Type]; lpType
0x180125fda  xor     r8d, r8d; lpReserved
0x180125fdd  mov     rdx, rsi; lpValueName
0x180125fe0  mov     rcx, r14; hKey
0x180125fe3  call    cs:__imp_RegQueryValueExW
0x180125fea  nop     dword ptr [rax+rax+00h]
0x180125fef  test    eax, eax
0x180125ff1  jle     short loc_180125FFA
0x180125ff3  movzx   eax, ax
0x180125ff6  or      eax, ebx
0x180125ff8  test    eax, eax
0x180125ffa  js      loc_1801261CE
0x180126000  mov     r9d, 0Ah
0x180126006  mov     r8d, 104h
0x18012600c  lea     rdx, [rbp+1D0h+Data]
0x180126010  mov     ecx, dword ptr [rsp+2D0h+var_290]
0x180126014  call    cs:__imp__o__itow_s
0x18012601b  nop     dword ptr [rax+rax+00h]
0x180126020  mov     ebx, eax
0x180126022  test    eax, eax
0x180126024  jle     short loc_18012602F
0x180126026  movzx   ebx, ax
0x180126029  or      ebx, 80070000h
0x18012602f  test    ebx, ebx
0x180126031  js      loc_180126214
0x180126037  lea     rdx, [rsi+208h]; unsigned __int16 *
0x18012603e  lea     r8, [rbp+1D0h+Data]; unsigned __int16 *
0x180126042  mov     rcx, r12; this
0x180126045  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x18012604a  mov     ebx, eax
0x18012604c  test    eax, eax
0x18012604e  jns     loc_1801261CE
0x180126054  mov     edx, 230h
0x180126059  jmp     loc_18012624F
0x18012605e  cmp     eax, 0Bh
0x180126061  jnz     loc_180126116
0x180126067  mov     qword ptr [rsp+2D0h+var_290], 0
0x180126070  mov     [rsp+2D0h+var_298], 8
0x180126078  lea     rax, [rsp+2D0h+var_298]
0x18012607d  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180126082  lea     rax, [rsp+2D0h+var_290]
0x180126087  mov     [rsp+2D0h+lpData], rax; lpData
0x18012608c  lea     r9, [rsp+2D0h+Type]; lpType
0x180126091  xor     r8d, r8d; lpReserved
0x180126094  mov     rdx, rsi; lpValueName
0x180126097  mov     rcx, r14; hKey
0x18012609a  call    cs:__imp_RegQueryValueExW
0x1801260a1  nop     dword ptr [rax+rax+00h]
0x1801260a6  test    eax, eax
0x1801260a8  jle     short loc_1801260B1
0x1801260aa  movzx   eax, ax
0x1801260ad  or      eax, ebx
0x1801260af  test    eax, eax
0x1801260b1  js      loc_1801261CE
0x1801260b7  mov     r9d, 0Ah
0x1801260bd  mov     r8d, 104h
0x1801260c3  lea     rdx, [rbp+1D0h+Data]
0x1801260c7  mov     rcx, qword ptr [rsp+2D0h+var_290]
0x1801260cc  call    cs:__imp__o__ui64tow_s
0x1801260d3  nop     dword ptr [rax+rax+00h]
0x1801260d8  mov     ebx, eax
0x1801260da  test    eax, eax
0x1801260dc  jle     short loc_1801260E7
0x1801260de  movzx   ebx, ax
0x1801260e1  or      ebx, 80070000h
0x1801260e7  test    ebx, ebx
0x1801260e9  js      loc_18012621B
0x1801260ef  lea     rdx, [rsi+208h]; unsigned __int16 *
0x1801260f6  lea     r8, [rbp+1D0h+Data]; unsigned __int16 *
0x1801260fa  mov     rcx, r12; this
0x1801260fd  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180126102  mov     ebx, eax
0x180126104  test    eax, eax
0x180126106  jns     loc_1801261CE
0x18012610c  mov     edx, 246h
0x180126111  jmp     loc_18012624F
0x180126116  cmp     eax, 3
0x180126119  jnz     loc_1801261CE
0x18012611f  lea     rax, [rsp+2D0h+cbData]
0x180126124  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180126129  mov     [rsp+2D0h+lpData], 0; lpData
0x180126132  xor     r9d, r9d; lpType
0x180126135  xor     r8d, r8d; lpReserved
0x180126138  mov     rdx, rsi; lpValueName
0x18012613b  mov     rcx, r14; hKey
0x18012613e  call    cs:__imp_RegQueryValueExW
0x180126145  nop     dword ptr [rax+rax+00h]
0x18012614a  test    eax, eax
0x18012614c  jle     short loc_180126155
0x18012614e  movzx   eax, ax
0x180126151  or      eax, ebx
0x180126153  test    eax, eax
0x180126155  js      short loc_1801261CE
0x180126157  mov     ecx, [rsp+2D0h+cbData]; unsigned __int64
0x18012615b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180126162  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180126167  mov     rbx, rax
0x18012616a  mov     qword ptr [rsp+2D0h+var_298], rax
0x18012616f  lea     rax, [rsp+2D0h+cbData]
0x180126174  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180126179  mov     [rsp+2D0h+lpData], rbx; int
0x18012617e  xor     r9d, r9d; lpType
0x180126181  xor     r8d, r8d; lpReserved
0x180126184  mov     rdx, rsi; lpValueName
0x180126187  mov     rcx, r14; hKey
0x18012618a  call    cs:__imp_RegQueryValueExW
0x180126191  nop     dword ptr [rax+rax+00h]
0x180126196  test    eax, eax
0x180126198  jle     short loc_1801261A4
0x18012619a  movzx   eax, ax
0x18012619d  or      eax, 80070000h
0x1801261a2  test    eax, eax
0x1801261a4  js      short loc_1801261C3
0x1801261a6  lea     rdx, [rsi+208h]; unsigned __int16 *
0x1801261ad  mov     r9d, [rsp+2D0h+cbData]; unsigned int
0x1801261b2  mov     r8, rbx; unsigned __int8 *
0x1801261b5  mov     rcx, r12; this
0x1801261b8  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBGPEAEK@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,uchar *,ulong)
0x1801261bd  mov     ebx, eax
0x1801261bf  test    eax, eax
0x1801261c1  js      short loc_180126222
0x1801261c3  lea     rcx, [rsp+2D0h+var_298]
0x1801261c8  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801261cd  nop
0x1801261ce  mov     rcx, [rsp+2D0h+lpValueName+8]; this
0x1801261d3  test    rcx, rcx
0x1801261d6  jz      short loc_1801261DD
0x1801261d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801261dd  inc     r15
0x1801261e0  jmp     loc_180125DE5
0x1801261e5  mov     rcx, [rbp+1D8h]; this
0x1801261ec  mov     r9d, ebx; char *
0x1801261ef  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801261f6  mov     edx, 219h; void *
0x1801261fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126200  nop
0x180126201  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x180126206  call    cs:__imp_SysFreeString
0x18012620d  nop     dword ptr [rax+rax+00h]
0x180126212  jmp     short loc_180126266
0x180126214  mov     edx, 22Eh
0x180126219  jmp     short loc_18012624F
0x18012621b  mov     edx, 244h
0x180126220  jmp     short loc_18012624F
0x180126222  mov     rcx, [rbp+1D8h]; this
0x180126229  mov     r9d, ebx; char *
0x18012622c  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180126233  mov     edx, 265h; void *
0x180126238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
