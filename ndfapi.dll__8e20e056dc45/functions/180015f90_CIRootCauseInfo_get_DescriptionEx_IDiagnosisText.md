# CIRootCauseInfo::get_DescriptionEx(IDiagnosisText * *)

- ea: `0x180015f90`
- end: `0x18001612c`
- name: `?get_DescriptionEx@CIRootCauseInfo@@UEAAJPEAPEAUIDiagnosisText@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CIRootCauseInfo *__hidden this, struct IDiagnosisText **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012260`
- `0x180015f90`
- `0x18001ad20`
- `0x18001d808`
- `0x18001dbb4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800160eb`
- `ole32!CoTaskMemFree` at `0x1800160f5`
- `ole32!CoTaskMemFree` at `0x1800160eb`
- `ole32!CoTaskMemFree` at `0x1800160f5`

## pseudocode

```c
__int64 __fastcall CIRootCauseInfo::get_DescriptionEx(CIRootCauseInfo *this, struct IDiagnosisText **a2)
{
  const unsigned __int16 **v5; // r8
  LPVOID *v6; // rsi
  unsigned int v7; // r14d
  int Parameters; // ebx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rcx
  unsigned __int16 *v16; // [rsp+20h] [rbp-20h] BYREF
  struct DiagnosisTextParser::DiagnosisParameter *v17; // [rsp+28h] [rbp-18h] BYREF
  LPVOID *v18; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+70h] [rbp+30h] BYREF
  __int64 v20; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF

  if ( !*((_QWORD *)this + 9) )
    return 2147942421LL;
  if ( !*((_DWORD *)this + 20) )
    return 1;
  v5 = (const unsigned __int16 **)*((_QWORD *)this + 11);
  v6 = 0;
  v7 = 0;
  pv = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  LODWORD(v20) = 0;
  if ( !v5 )
    goto LABEL_16;
  Parameters = UtilStringCopyWithAlloc((unsigned __int16 **)&pv, *((_DWORD *)*v5 - 4) + 1, *v5);
  if ( Parameters < 0 )
    goto LABEL_17;
  v9 = *((_QWORD *)this + 11);
  if ( !v9 )
  {
LABEL_16:
    Parameters = -2147024882;
    goto LABEL_17;
  }
  Parameters = UtilStringCopyWithAlloc(
                 &v16,
                 *(_DWORD *)(*(_QWORD *)(v9 + 8) - 16LL) + 1,
                 *(const unsigned __int16 **)(v9 + 8));
  if ( Parameters < 0 )
  {
LABEL_17:
    CoTaskMemFree(pv);
    CoTaskMemFree(v16);
    FreeDiagnosisParameters((LPVOID *)v17, v19);
    FreeDiagnosisParameters(v6, v7);
    return (unsigned int)Parameters;
  }
  v11 = *((_QWORD *)this + 11);
  if ( !v11 )
    goto LABEL_16;
  Parameters = DiagnosisTextParserImpl::GetParameters(v10, v11 + 16, &v17, &v19);
  if ( Parameters < 0 )
    goto LABEL_17;
  v13 = *((_QWORD *)this + 11);
  if ( v13 )
  {
    v14 = DiagnosisTextParserImpl::GetParameters(v12, v13 + 32, &v18, &v20);
    v6 = v18;
    Parameters = v14;
    v7 = v20;
  }
  else
  {
    Parameters = -2147024882;
  }
  if ( Parameters < 0 )
    goto LABEL_17;
  v20 = 0;
  Parameters = ATL::CComCreator<ATL::CComObject<CIDiagnosisText>>::CreateInstance(v12, v13, &v20);
  if ( Parameters < 0 )
    goto LABEL_17;
  v15 = v20;
  Parameters = 0;
  *(_QWORD *)(v20 + 64) = pv;
  *(_QWORD *)(v15 + 72) = v16;
  *(_QWORD *)(v15 + 80) = v17;
  *(_DWORD *)(v15 + 88) = v19;
  *(_QWORD *)(v15 + 96) = v6;
  *(_DWORD *)(v15 + 104) = v7;
  *a2 = (struct IDiagnosisText *)v20;
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x180015f90  mov     [rsp-28h+arg_8], rbx
0x180015f95  push    rbp
0x180015f96  push    rsi
0x180015f97  push    rdi
0x180015f98  push    r14
0x180015f9a  push    r15
0x180015f9c  mov     rbp, rsp
0x180015f9f  sub     rsp, 40h
0x180015fa3  cmp     qword ptr [rcx+48h], 0
0x180015fa8  mov     r15, rdx
0x180015fab  mov     rdi, rcx
0x180015fae  jnz     short loc_180015FBA
0x180015fb0  mov     eax, 80070015h
0x180015fb5  jmp     loc_18001611B
0x180015fba  cmp     dword ptr [rcx+50h], 0
0x180015fbe  jz      loc_180016114
0x180015fc4  mov     r8, [rcx+58h]
0x180015fc8  xor     esi, esi
0x180015fca  xor     r14d, r14d
0x180015fcd  mov     [rbp+pv], 0
0x180015fd5  mov     [rbp+var_20], 0
0x180015fdd  mov     [rbp+var_18], 0
0x180015fe5  mov     [rbp+var_10], rsi
0x180015fe9  mov     [rbp+arg_0], esi
0x180015fec  mov     dword ptr [rbp+arg_10], r14d
0x180015ff0  test    r8, r8
0x180015ff3  jz      loc_1800160E2
0x180015ff9  mov     r8, [r8]; unsigned __int16 *
0x180015ffc  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180016000  mov     edx, [r8-10h]
0x180016004  inc     edx; unsigned int
0x180016006  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x18001600b  mov     ebx, eax
0x18001600d  test    eax, eax
0x18001600f  js      loc_1800160E7
0x180016015  mov     r8, [rdi+58h]
0x180016019  test    r8, r8
0x18001601c  jz      loc_1800160E2
0x180016022  mov     r8, [r8+8]; unsigned __int16 *
0x180016026  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x18001602a  mov     edx, [r8-10h]
0x18001602e  inc     edx; unsigned int
0x180016030  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x180016035  mov     ebx, eax
0x180016037  test    eax, eax
0x180016039  js      loc_1800160E7
0x18001603f  mov     rdx, [rdi+58h]
0x180016043  test    rdx, rdx
0x180016046  jz      loc_1800160E2
0x18001604c  add     rdx, 10h
0x180016050  lea     r9, [rbp+arg_0]
0x180016054  lea     r8, [rbp+var_18]
0x180016058  call    ?GetParameters@DiagnosisTextParserImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEAPEAUDiagnosisParameter@DiagnosisTextParser@@PEAK@Z; DiagnosisTextParserImpl::GetParameters(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,DiagnosisTextParser::DiagnosisParameter * *,ulong *)
0x18001605d  mov     ebx, eax
0x18001605f  test    eax, eax
0x180016061  js      loc_1800160E7
0x180016067  mov     rdx, [rdi+58h]
0x18001606b  test    rdx, rdx
0x18001606e  jz      short loc_18001608D
0x180016070  add     rdx, 20h ; ' '
0x180016074  lea     r9, [rbp+arg_10]
0x180016078  lea     r8, [rbp+var_10]
0x18001607c  call    ?GetParameters@DiagnosisTextParserImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEAPEAUDiagnosisParameter@DiagnosisTextParser@@PEAK@Z; DiagnosisTextParserImpl::GetParameters(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,DiagnosisTextParser::DiagnosisParameter * *,ulong *)
0x180016081  mov     rsi, [rbp+var_10]
0x180016085  mov     ebx, eax
0x180016087  mov     r14d, dword ptr [rbp+arg_10]
0x18001608b  jmp     short loc_180016092
0x18001608d  mov     ebx, 8007000Eh
0x180016092  test    ebx, ebx
0x180016094  js      short loc_1800160E7
0x180016096  lea     r8, [rbp+arg_10]
0x18001609a  mov     [rbp+arg_10], 0
0x1800160a2  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosisText@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIDiagnosisText>>::CreateInstance(void *,_GUID const &,void * *)
0x1800160a7  mov     ebx, eax
0x1800160a9  test    eax, eax
0x1800160ab  js      short loc_1800160E7
0x1800160ad  mov     rcx, [rbp+arg_10]
0x1800160b1  xor     ebx, ebx
0x1800160b3  mov     rax, [rbp+pv]
0x1800160b7  mov     [rcx+40h], rax
0x1800160bb  mov     rax, [rbp+var_20]
0x1800160bf  mov     [rcx+48h], rax
0x1800160c3  mov     rax, [rbp+var_18]
0x1800160c7  mov     [rcx+50h], rax
0x1800160cb  mov     eax, [rbp+arg_0]
0x1800160ce  mov     [rcx+58h], eax
0x1800160d1  mov     [rcx+60h], rsi
0x1800160d5  mov     [rcx+68h], r14d
0x1800160d9  mov     rax, [rbp+arg_10]
0x1800160dd  mov     [r15], rax
0x1800160e0  jmp     short loc_180016119
0x1800160e2  mov     ebx, 8007000Eh
0x1800160e7  mov     rcx, [rbp+pv]; pv
0x1800160eb  call    cs:__imp_CoTaskMemFree
0x1800160f1  mov     rcx, [rbp+var_20]; pv
0x1800160f5  call    cs:__imp_CoTaskMemFree
0x1800160fb  mov     edx, [rbp+arg_0]; unsigned int
0x1800160fe  mov     rcx, [rbp+var_18]; struct DiagnosisTextParser::DiagnosisParameter *
0x180016102  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x180016107  mov     edx, r14d; unsigned int
0x18001610a  mov     rcx, rsi; struct DiagnosisTextParser::DiagnosisParameter *
0x18001610d  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x180016112  jmp     short loc_180016119
0x180016114  mov     ebx, 1
0x180016119  mov     eax, ebx
0x18001611b  mov     rbx, [rsp+40h+arg_8]
0x180016120  add     rsp, 40h
0x180016124  pop     r15
0x180016126  pop     r14
0x180016128  pop     rdi
0x180016129  pop     rsi
0x18001612a  pop     rbp
0x18001612b  retn
```
