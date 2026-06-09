# WERReport::SetResult(tagNDFStoppedStatusEnum,long,tagRepairInfo *,ProblemInstance *)

- ea: `0x180027020`
- end: `0x180027624`
- name: `?SetResult@WERReport@@UEAAJW4tagNDFStoppedStatusEnum@@JPEAUtagRepairInfo@@PEAVProblemInstance@@@Z`
- size: `1540`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update`

## callees

- `0x1800020d6`
- `0x1800035a8`
- `0x1800040b4`
- `0x180006fa0`
- `0x18001006c`
- `0x1800218e8`
- `0x180027020`
- `0x18002a224`
- `0x18002a454`
- `0x18002a584`
- `0x18002a81c`
- `0x18002a9ac`
- `0x18002ad14`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x180027539`
- `KERNEL32!FileTimeToSystemTime` at `0x180027539`
- `wer!WerReportSetParameter` at `0x1800270c3`
- `wer!WerReportSetParameter` at `0x18002710c`
- `wer!WerReportSetParameter` at `0x1800271e4`
- `wer!WerReportSetParameter` at `0x180027242`
- `wer!WerReportSetParameter` at `0x180027312`
- `wer!WerReportSetParameter` at `0x18002749c`
- `wer!WerReportSetParameter` at `0x180027596`
- `wer!WerReportSetParameter` at `0x1800275cf`
- `wer!WerReportSetParameter` at `0x1800275f2`
- `wer!WerReportSetParameter` at `0x1800270c3`
- `wer!WerReportSetParameter` at `0x18002710c`
- `wer!WerReportSetParameter` at `0x1800271e4`
- `wer!WerReportSetParameter` at `0x180027242`
- `wer!WerReportSetParameter` at `0x180027312`
- `wer!WerReportSetParameter` at `0x18002749c`
- `wer!WerReportSetParameter` at `0x180027596`
- `wer!WerReportSetParameter` at `0x1800275cf`
- `wer!WerReportSetParameter` at `0x1800275f2`

## string_xrefs

- `0x1800271d4`: `Repair`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WERReport::SetResult(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        struct ProblemInstance *a5)
{
  int NetDevice; // ebx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // r9
  struct _SP_DRVINFO_DETAIL_DATA_W *v13; // rdi
  unsigned int v14; // edx
  unsigned __int16 *InfFileName; // r8
  __int64 v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  struct _SP_DRVINFO_DETAIL_DATA_W *v30; // [rsp+70h] [rbp-90h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h]
  _BYTE v33[1560]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v34; // [rsp+6A8h] [rbp+5A8h]
  struct _SYSTEMTIME SystemTime; // [rsp+6B0h] [rbp+5B0h] BYREF
  struct _GUID v36; // [rsp+6C0h] [rbp+5C0h] BYREF
  _QWORD v37[2]; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int128 v38; // [rsp+6E0h] [rbp+5E0h]
  __int128 v39; // [rsp+6F0h] [rbp+5F0h]
  __int64 v40; // [rsp+700h] [rbp+600h]
  char v41; // [rsp+708h] [rbp+608h]
  _BYTE Src[1568]; // [rsp+710h] [rbp+610h] BYREF
  unsigned __int16 v43[32]; // [rsp+D30h] [rbp+C30h] BYREF
  WCHAR pwzValue[264]; // [rsp+D70h] [rbp+C70h] BYREF

  if ( !*(_QWORD *)(a1 + 8) || !a5 )
    return 2147942406LL;
  memset_0(pwzValue, 0, 0x208u);
  NetDevice = StringCchPrintfW(pwzValue, 0x104u, L"%i", a2);
  if ( NetDevice >= 0 )
  {
    NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 2u, L"SessionStatus", pwzValue);
    if ( NetDevice >= 0 )
    {
      NetDevice = StringCchPrintfW(pwzValue, 0x104u, L"%X", a3);
      if ( NetDevice >= 0 )
      {
        NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 3u, L"HRESULT", pwzValue);
        if ( NetDevice >= 0 )
        {
          v10 = a4
              ? StringCchPrintfW(
                  pwzValue,
                  0x104u,
                  L"{%08lX-%04X-%04x-%02X%02X-%02X%02X%02X%02X%02X%02X}",
                  *a4,
                  *((unsigned __int16 *)a4 + 2),
                  *((unsigned __int16 *)a4 + 3),
                  *((unsigned __int8 *)a4 + 8),
                  *((unsigned __int8 *)a4 + 9),
                  *((unsigned __int8 *)a4 + 10),
                  *((unsigned __int8 *)a4 + 11),
                  *((unsigned __int8 *)a4 + 12),
                  *((unsigned __int8 *)a4 + 13),
                  *((unsigned __int8 *)a4 + 14),
                  *((unsigned __int8 *)a4 + 15))
              : StringCchPrintfW(pwzValue, 0x104u, L"{00000000-0000-0000-0000-000000000000}");
          NetDevice = v10;
          if ( v10 >= 0 )
          {
            NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 4u, L"Repair", pwzValue);
            if ( NetDevice >= 0 )
            {
              v11 = *((_QWORD *)a5 + 3);
              if ( !*(_DWORD *)(v11 - 16) )
                v11 = *((_QWORD *)a5 + 1);
              v12 = *((_QWORD *)a5 + 2);
              if ( !*(_DWORD *)(v12 - 16) )
                v12 = *(_QWORD *)a5;
              StringCchPrintfW(pwzValue, 0x104u, L"%s [%s]", v12, v11);
              NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 5u, L"RootCauseHC", pwzValue);
              if ( NetDevice >= 0 )
              {
                LODWORD(v29) = *((unsigned __int8 *)a5 + 271);
                LODWORD(v28) = *((unsigned __int8 *)a5 + 270);
                LODWORD(v27) = *((unsigned __int8 *)a5 + 269);
                LODWORD(v26) = *((unsigned __int8 *)a5 + 268);
                LODWORD(v25) = *((unsigned __int8 *)a5 + 267);
                LODWORD(v24) = *((unsigned __int8 *)a5 + 266);
                LODWORD(v23) = *((unsigned __int8 *)a5 + 265);
                LODWORD(v21) = *((unsigned __int8 *)a5 + 264);
                LODWORD(v19) = *((unsigned __int16 *)a5 + 131);
                LODWORD(v17) = *((unsigned __int16 *)a5 + 130);
                NetDevice = StringCchPrintfW(
                              pwzValue,
                              0x104u,
                              L"{%08lX-%04X-%04x-%02X%02X-%02X%02X%02X%02X%02X%02X}",
                              *((unsigned int *)a5 + 64),
                              v17,
                              v19,
                              v21,
                              v23,
                              v24,
                              v25,
                              v26,
                              v27,
                              v28,
                              v29);
                if ( NetDevice >= 0 )
                {
                  NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 6u, L"RootCause", pwzValue);
                  if ( NetDevice >= 0 )
                  {
                    v36 = 0;
                    if ( GetAdapterGUID(a5, &v36) )
                    {
                      v37[1] = 0;
                      v40 = -1;
                      v41 = 0;
                      v38 = 0;
                      v39 = 0;
                      memset_0(Src, 0, sizeof(Src));
                      v37[0] = &CSetupAPINetDevice::`vftable';
                      NetDevice = GetNetDevice(&v36, (struct CSetupAPINetDevice *)v37);
                      if ( NetDevice >= 0 )
                      {
                        v30 = 0;
                        v31 = 0;
                        v32 = 0;
                        NetDevice = CSetupAPIDevice::InitializeDriverInfo((CSetupAPIDevice *)v37);
                        if ( NetDevice >= 0 )
                        {
                          memcpy_0(v33, Src, 0x620u);
                          NetDevice = CSetupAPIDevice::GetDriverFiles((__int64)v37, (__int64 *)&v31);
                          if ( NetDevice >= 0 )
                          {
                            NetDevice = CSetupAPIDevice::GetDriverDetails((CSetupAPIDevice *)v37, &v30);
                            if ( NetDevice >= 0 )
                            {
                              v13 = v30;
                              memset_0(pwzValue, 0, 0x208u);
                              InfFileName = (unsigned __int16 *)v31;
                              if ( *((_QWORD *)&v31 + 1) == (_QWORD)v31 )
                                InfFileName = v13->InfFileName;
                              NetDevice = GetFileName(pwzValue, v14, InfFileName);
                              if ( NetDevice >= 0 )
                              {
                                NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 7u, L"DriverFileName", pwzValue);
                                if ( NetDevice >= 0 )
                                {
                                  memset_0(v43, 0, sizeof(v43));
                                  if ( v34 )
                                  {
                                    LODWORD(v22) = (unsigned __int16)v34;
                                    LODWORD(v20) = WORD1(v34);
                                    LODWORD(v18) = WORD2(v34);
                                    StringCchPrintfW(v43, 0x20u, L"%d.%d.%d.%d", HIWORD(v34), v18, v20, v22);
                                  }
                                  else
                                  {
                                    StringCchCopyW(v43, 0x20u, L"0");
                                  }
                                  SystemTime = 0;
                                  FileTimeToSystemTime(&v13->InfDate, &SystemTime);
                                  LODWORD(v22) = SystemTime.wYear;
                                  LODWORD(v20) = SystemTime.wMonth;
                                  LODWORD(v18) = SystemTime.wDay;
                                  StringCchPrintfW(pwzValue, 0x104u, L"%s %02u/%02u/%u", v43, v18, v20, v22);
                                  NetDevice = WerReportSetParameter(
                                                *(HREPORT *)(a1 + 8),
                                                8u,
                                                L"DriverVersion",
                                                pwzValue);
                                }
                              }
                              TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v30);
                            }
                          }
                        }
                        std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)&v31);
                      }
                      v37[0] = &CSetupAPINetDevice::`vftable';
                      CSetupAPIDevice::~CSetupAPIDevice((CSetupAPIDevice *)v37);
                    }
                    else
                    {
                      NetDevice = WerReportSetParameter(*(HREPORT *)(a1 + 8), 7u, L"DriverFileName", L"N/A");
                      if ( NetDevice >= 0 )
                        return (unsigned int)WerReportSetParameter(*(HREPORT *)(a1 + 8), 8u, L"DriverVersion", L"N/A");
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)NetDevice;
}

```

## disassembly

```asm
0x180027020  push    rbp
0x180027022  push    rbx
0x180027023  push    rsi
0x180027024  push    rdi
0x180027025  push    r12
0x180027027  push    r14
0x180027029  push    r15
0x18002702b  lea     rbp, [rsp-0E90h]
0x180027033  sub     rsp, 0F90h
0x18002703a  mov     rax, cs:__security_cookie
0x180027041  xor     rax, rsp
0x180027044  mov     [rbp+0EC0h+var_40], rax
0x18002704b  mov     r12, r9
0x18002704e  mov     edi, r8d
0x180027051  mov     ebx, edx
0x180027053  mov     r15, rcx
0x180027056  mov     r14, [rbp+0EC0h+arg_20]
0x18002705d  cmp     qword ptr [rcx+8], 0
0x180027062  jz      loc_1800275FE
0x180027068  test    r14, r14
0x18002706b  jz      loc_1800275FE
0x180027071  xor     edx, edx; Val
0x180027073  mov     r8d, 208h; Size
0x180027079  lea     rcx, [rbp+0EC0h+pwzValue]; void *
0x180027080  call    memset_0
0x180027085  mov     r9d, ebx
0x180027088  lea     r8, aI_0; "%i"
0x18002708f  mov     esi, 104h
0x180027094  mov     edx, esi; unsigned __int64
0x180027096  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x18002709d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800270a2  mov     ebx, eax
0x1800270a4  test    eax, eax
0x1800270a6  js      loc_1800275FA
0x1800270ac  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x1800270b3  lea     r8, aSessionstatus; "SessionStatus"
0x1800270ba  mov     edx, 2; dwparamID
0x1800270bf  mov     rcx, [r15+8]; hReportHandle
0x1800270c3  call    cs:__imp_WerReportSetParameter
0x1800270c9  mov     ebx, eax
0x1800270cb  test    eax, eax
0x1800270cd  js      loc_1800275FA
0x1800270d3  mov     r9d, edi
0x1800270d6  lea     r8, asc_18003893C; "%X"
0x1800270dd  mov     edx, esi; unsigned __int64
0x1800270df  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x1800270e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800270eb  mov     ebx, eax
0x1800270ed  test    eax, eax
0x1800270ef  js      loc_1800275FA
0x1800270f5  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x1800270fc  lea     r8, aHresult; "HRESULT"
0x180027103  mov     edx, 3; dwparamID
0x180027108  mov     rcx, [r15+8]; hReportHandle
0x18002710c  call    cs:__imp_WerReportSetParameter
0x180027112  mov     ebx, eax
0x180027114  test    eax, eax
0x180027116  js      loc_1800275FA
0x18002711c  test    r12, r12
0x18002711f  jz      loc_1800271AD
0x180027125  movzx   eax, byte ptr [r12+0Fh]
0x18002712b  movzx   ecx, byte ptr [r12+0Eh]
0x180027131  movzx   edx, byte ptr [r12+0Dh]
0x180027137  movzx   r8d, byte ptr [r12+0Ch]
0x18002713d  movzx   r9d, byte ptr [r12+0Bh]
0x180027143  movzx   r10d, byte ptr [r12+0Ah]
0x180027149  movzx   r11d, byte ptr [r12+9]
0x18002714f  movzx   ebx, byte ptr [r12+8]
0x180027155  movzx   edi, word ptr [r12+6]
0x18002715b  movzx   esi, word ptr [r12+4]
0x180027161  mov     dword ptr [rsp+0FC0h+var_F58], eax
0x180027165  mov     dword ptr [rsp+0FC0h+var_F60], ecx
0x180027169  mov     dword ptr [rsp+0FC0h+var_F68], edx
0x18002716d  mov     dword ptr [rsp+0FC0h+var_F70], r8d
0x180027172  mov     dword ptr [rsp+0FC0h+var_F78], r9d
0x180027177  mov     dword ptr [rsp+0FC0h+var_F80], r10d
0x18002717c  mov     dword ptr [rsp+0FC0h+var_F88], r11d
0x180027181  mov     dword ptr [rsp+0FC0h+var_F90], ebx
0x180027185  mov     dword ptr [rsp+0FC0h+var_F98], edi
0x180027189  mov     dword ptr [rsp+0FC0h+var_FA0], esi
0x18002718d  mov     r9d, [r12]
0x180027191  lea     r8, a08lx04x04x02x0; "{%08lX-%04X-%04x-%02X%02X-%02X%02X%02X%"...
0x180027198  mov     esi, 104h
0x18002719d  mov     edx, esi; unsigned __int64
0x18002719f  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x1800271a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800271ab  jmp     short loc_1800271C3
0x1800271ad  lea     r8, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800271b4  mov     rdx, rsi; unsigned __int64
0x1800271b7  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x1800271be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800271c3  mov     ebx, eax
0x1800271c5  test    eax, eax
0x1800271c7  js      loc_1800275FA
0x1800271cd  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x1800271d4  lea     r8, aRepair; "Repair"
0x1800271db  mov     edx, 4; dwparamID
0x1800271e0  mov     rcx, [r15+8]; hReportHandle
0x1800271e4  call    cs:__imp_WerReportSetParameter
0x1800271ea  mov     ebx, eax
0x1800271ec  test    eax, eax
0x1800271ee  js      loc_1800275FA
0x1800271f4  mov     rax, [r14+18h]
0x1800271f8  cmp     dword ptr [rax-10h], 0
0x1800271fc  jnz     short loc_180027202
0x1800271fe  mov     rax, [r14+8]
0x180027202  mov     r9, [r14+10h]
0x180027206  cmp     dword ptr [r9-10h], 0
0x18002720b  jnz     short loc_180027210
0x18002720d  mov     r9, [r14]
0x180027210  mov     [rsp+0FC0h+var_FA0], rax
0x180027215  lea     r8, aSS; "%s [%s]"
0x18002721c  mov     rdx, rsi; unsigned __int64
0x18002721f  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x180027226  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002722b  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x180027232  lea     r8, aRootcausehc; "RootCauseHC"
0x180027239  mov     edx, 5; dwparamID
0x18002723e  mov     rcx, [r15+8]; hReportHandle
0x180027242  call    cs:__imp_WerReportSetParameter
0x180027248  mov     ebx, eax
0x18002724a  test    eax, eax
0x18002724c  js      loc_1800275FA
0x180027252  movzx   eax, byte ptr [r14+10Fh]
0x18002725a  movzx   ecx, byte ptr [r14+10Eh]
0x180027262  movzx   edx, byte ptr [r14+10Dh]
0x18002726a  movzx   r8d, byte ptr [r14+10Ch]
0x180027272  movzx   r9d, byte ptr [r14+10Bh]
0x18002727a  movzx   r10d, byte ptr [r14+10Ah]
0x180027282  movzx   r11d, byte ptr [r14+109h]
0x18002728a  movzx   ebx, byte ptr [r14+108h]
0x180027292  movzx   edi, word ptr [r14+106h]
0x18002729a  movzx   esi, word ptr [r14+104h]
0x1800272a2  mov     dword ptr [rsp+0FC0h+var_F58], eax
0x1800272a6  mov     dword ptr [rsp+0FC0h+var_F60], ecx
0x1800272aa  mov     dword ptr [rsp+0FC0h+var_F68], edx
0x1800272ae  mov     dword ptr [rsp+0FC0h+var_F70], r8d
0x1800272b3  mov     dword ptr [rsp+0FC0h+var_F78], r9d
0x1800272b8  mov     dword ptr [rsp+0FC0h+var_F80], r10d
0x1800272bd  mov     dword ptr [rsp+0FC0h+var_F88], r11d
0x1800272c2  mov     dword ptr [rsp+0FC0h+var_F90], ebx
0x1800272c6  mov     dword ptr [rsp+0FC0h+var_F98], edi
0x1800272ca  mov     dword ptr [rsp+0FC0h+var_FA0], esi
0x1800272ce  mov     r9d, [r14+100h]
0x1800272d5  lea     r8, a08lx04x04x02x0; "{%08lX-%04X-%04x-%02X%02X-%02X%02X%02X%"...
0x1800272dc  mov     r12d, 104h
0x1800272e2  mov     edx, r12d; unsigned __int64
0x1800272e5  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x1800272ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800272f1  mov     ebx, eax
0x1800272f3  test    eax, eax
0x1800272f5  js      loc_1800275FA
0x1800272fb  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x180027302  lea     r8, aRootcause; "RootCause"
0x180027309  mov     edx, 6; dwparamID
0x18002730e  mov     rcx, [r15+8]; hReportHandle
0x180027312  call    cs:__imp_WerReportSetParameter
0x180027318  mov     ebx, eax
0x18002731a  test    eax, eax
0x18002731c  js      loc_1800275FA
0x180027322  xorps   xmm0, xmm0
0x180027325  movups  xmmword ptr [rbp+0EC0h+var_900.Data1], xmm0
0x18002732c  lea     rdx, [rbp+0EC0h+var_900]; struct _GUID *
0x180027333  mov     rcx, r14; struct ProblemInstance *
0x180027336  call    ?GetAdapterGUID@@YAHPEAVProblemInstance@@PEAU_GUID@@@Z; GetAdapterGUID(ProblemInstance *,_GUID *)
0x18002733b  test    eax, eax
0x18002733d  jz      loc_1800275B8
0x180027343  mov     [rbp+0EC0h+var_8E8], 0
0x18002734e  mov     [rbp+0EC0h+var_8C0], 0FFFFFFFFFFFFFFFFh
0x180027359  mov     [rbp+0EC0h+var_8B8], 0
0x180027360  xorps   xmm0, xmm0
0x180027363  movups  [rbp+0EC0h+var_8E0], xmm0
0x18002736a  movups  [rbp+0EC0h+var_8D0], xmm0
0x180027371  mov     edi, 620h
0x180027376  mov     r8d, edi; Size
0x180027379  xor     edx, edx; Val
0x18002737b  lea     rcx, [rbp+0EC0h+Src]; void *
0x180027382  call    memset_0
0x180027387  lea     rsi, ??_7CSetupAPINetDevice@@6B@; const CSetupAPINetDevice::`vftable'
0x18002738e  mov     [rbp+0EC0h+var_8F0], rsi
0x180027395  lea     rdx, [rbp+0EC0h+var_8F0]; struct CSetupAPINetDevice *
0x18002739c  lea     rcx, [rbp+0EC0h+var_900]; struct _GUID *
0x1800273a3  call    ?GetNetDevice@@YAJAEBU_GUID@@AEAVCSetupAPINetDevice@@@Z; GetNetDevice(_GUID const &,CSetupAPINetDevice &)
0x1800273a8  mov     ebx, eax
0x1800273aa  test    eax, eax
0x1800273ac  jns     short loc_1800273C6
0x1800273ae  mov     [rbp+0EC0h+var_8F0], rsi
0x1800273b5  lea     rcx, [rbp+0EC0h+var_8F0]; this
0x1800273bc  call    ??1CSetupAPIDevice@@UEAA@XZ; CSetupAPIDevice::~CSetupAPIDevice(void)
0x1800273c1  jmp     loc_1800275FA
0x1800273c6  mov     [rsp+0FC0h+var_F50], 0
0x1800273cf  xorps   xmm0, xmm0
0x1800273d2  movdqu  [rsp+0FC0h+var_F48], xmm0
0x1800273d8  mov     [rbp+0EC0h+var_F38], 0
0x1800273e0  lea     rcx, [rbp+0EC0h+var_8F0]; this
0x1800273e7  call    ?InitializeDriverInfo@CSetupAPIDevice@@AEAAJXZ; CSetupAPIDevice::InitializeDriverInfo(void)
0x1800273ec  mov     ebx, eax
0x1800273ee  test    eax, eax
0x1800273f0  js      loc_1800275A9
0x1800273f6  lea     rcx, [rbp+0EC0h+var_F30]; void *
0x1800273fa  lea     rdx, [rbp+0EC0h+Src]; Src
0x180027401  mov     r8, rdi; Size
0x180027404  call    memcpy_0
0x180027409  lea     rdx, [rsp+0FC0h+var_F48]
0x18002740e  lea     rcx, [rbp+0EC0h+var_8F0]
0x180027415  call    ?GetDriverFiles@CSetupAPIDevice@@QEAAJPEAV?$vector@USetupAPIDriverFileInfo@@V?$allocator@USetupAPIDriverFileInfo@@@std@@@std@@@Z; CSetupAPIDevice::GetDriverFiles(std::vector<SetupAPIDriverFileInfo> *)
0x18002741a  mov     ebx, eax
0x18002741c  test    eax, eax
0x18002741e  js      loc_1800275A9
0x180027424  lea     rdx, [rsp+0FC0h+var_F50]; struct _SP_DRVINFO_DETAIL_DATA_W **
0x180027429  lea     rcx, [rbp+0EC0h+var_8F0]; this
0x180027430  call    ?GetDriverDetails@CSetupAPIDevice@@QEAAJPEAPEAU_SP_DRVINFO_DETAIL_DATA_W@@@Z; CSetupAPIDevice::GetDriverDetails(_SP_DRVINFO_DETAIL_DATA_W * *)
0x180027435  mov     ebx, eax
0x180027437  test    eax, eax
0x180027439  js      loc_1800275A9
0x18002743f  mov     rdi, [rsp+0FC0h+var_F50]
0x180027444  mov     [rsp+0FC0h+var_F50], rdi
0x180027449  xor     edx, edx; Val
0x18002744b  mov     r8d, 208h; Size
0x180027451  lea     rcx, [rbp+0EC0h+pwzValue]; void *
0x180027458  call    memset_0
0x18002745d  mov     r8, qword ptr [rsp+0FC0h+var_F48]
0x180027462  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x180027469  cmp     qword ptr [rbp+0EC0h+var_F48+8], r8
0x18002746d  jnz     short loc_180027476
0x18002746f  lea     r8, [rdi+220h]; unsigned __int16 *
0x180027476  call    ?GetFileName@@YAJPEAGK0@Z; GetFileName(ushort *,ulong,ushort *)
0x18002747b  mov     ebx, eax
0x18002747d  test    eax, eax
0x18002747f  js      loc_18002759E
0x180027485  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x18002748c  lea     r8, aDriverfilename; "DriverFileName"
0x180027493  mov     edx, 7; dwparamID
0x180027498  mov     rcx, [r15+8]; hReportHandle
0x18002749c  call    cs:__imp_WerReportSetParameter
0x1800274a2  mov     ebx, eax
0x1800274a4  test    eax, eax
0x1800274a6  js      loc_18002759E
0x1800274ac  xor     edx, edx; Val
0x1800274ae  lea     r8d, [rdx+40h]; Size
0x1800274b2  lea     rcx, [rbp+0EC0h+var_290]; void *
0x1800274b9  call    memset_0
0x1800274be  mov     r9, [rbp+0EC0h+var_918]
0x1800274c5  test    r9, r9
0x1800274c8  jnz     short loc_1800274E3
0x1800274ca  lea     r8, a0; "0"
0x1800274d1  lea     edx, [r9+20h]; unsigned __int64
0x1800274d5  lea     rcx, [rbp+0EC0h+var_290]; unsigned __int16 *
0x1800274dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800274e1  jmp     short loc_180027524
0x1800274e3  movzx   r8d, r9w
0x1800274e7  mov     rax, r9
0x1800274ea  shr     rax, 10h
0x1800274ee  movzx   edx, ax
0x1800274f1  mov     rax, r9
0x1800274f4  shr     rax, 20h
0x1800274f8  movzx   ecx, ax
0x1800274fb  shr     r9, 30h
0x1800274ff  mov     dword ptr [rsp+0FC0h+var_F90], r8d
0x180027504  mov     dword ptr [rsp+0FC0h+var_F98], edx
0x180027508  mov     dword ptr [rsp+0FC0h+var_FA0], ecx
0x18002750c  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180027513  mov     edx, 20h ; ' '; unsigned __int64
0x180027518  lea     rcx, [rbp+0EC0h+var_290]; unsigned __int16 *
0x18002751f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027524  xorps   xmm0, xmm0
0x180027527  movups  xmmword ptr [rbp+0EC0h+SystemTime.wYear], xmm0
0x18002752e  lea     rcx, [rdi+4]; lpFileTime
0x180027532  lea     rdx, [rbp+0EC0h+SystemTime]; lpSystemTime
0x180027539  call    cs:__imp_FileTimeToSystemTime
0x18002753f  movzx   eax, [rbp+0EC0h+SystemTime.wYear]
0x180027546  movzx   ecx, [rbp+0EC0h+SystemTime.wMonth]
0x18002754d  movzx   r8d, [rbp+0EC0h+SystemTime.wDay]
0x180027555  mov     dword ptr [rsp+0FC0h+var_F90], eax
0x180027559  mov     dword ptr [rsp+0FC0h+var_F98], ecx
0x18002755d  mov     dword ptr [rsp+0FC0h+var_FA0], r8d
0x180027562  lea     r9, [rbp+0EC0h+var_290]
0x180027569  lea     r8, aS02u02uU; "%s %02u/%02u/%u"
0x180027570  mov     rdx, r12; unsigned __int64
0x180027573  lea     rcx, [rbp+0EC0h+pwzValue]; unsigned __int16 *
0x18002757a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002757f  lea     r9, [rbp+0EC0h+pwzValue]; pwzValue
0x180027586  lea     r8, aDriverversion; "DriverVersion"
0x18002758d  mov     edx, 8; dwparamID
0x180027592  mov     rcx, [r15+8]; hReportHandle
0x180027596  call    cs:__imp_WerReportSetParameter
0x18002759c  mov     ebx, eax
0x18002759e  lea     rcx, [rsp+0FC0h+var_F50]
0x1800275a3  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x1800275a8  nop
0x1800275a9  lea     rcx, [rsp+0FC0h+var_F48]
0x1800275ae  call    ??1?$vector@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>(void)
0x1800275b3  jmp     loc_1800273AE
0x1800275b8  lea     r9, pwzValue; "N/A"
0x1800275bf  lea     r8, aDriverfilename; "DriverFileName"
0x1800275c6  mov     edx, 7; dwparamID
0x1800275cb  mov     rcx, [r15+8]; hReportHandle
0x1800275cf  call    cs:__imp_WerReportSetParameter
0x1800275d5  mov     ebx, eax
0x1800275d7  test    eax, eax
  ... truncated ...
```
