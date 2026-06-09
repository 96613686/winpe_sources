# CIRepairInfo::get_DescriptionEx(IDiagnosisText * *)

- ea: `0x180015de0`
- end: `0x180015f7c`
- name: `?get_DescriptionEx@CIRepairInfo@@UEAAJPEAPEAUIDiagnosisText@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CIRepairInfo *__hidden this, struct IDiagnosisText **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180012260`
- `0x180015de0`
- `0x18001ad20`
- `0x18001d808`
- `0x18001dbb4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015f3b`
- `ole32!CoTaskMemFree` at `0x180015f45`
- `ole32!CoTaskMemFree` at `0x180015f3b`
- `ole32!CoTaskMemFree` at `0x180015f45`

## pseudocode

```c
__int64 __fastcall CIRepairInfo::get_DescriptionEx(CIRepairInfo *this, struct IDiagnosisText **a2)
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

  if ( !*((_QWORD *)this + 10) )
    return 2147942421LL;
  if ( !*((_DWORD *)this + 22) )
    return 1;
  v5 = (const unsigned __int16 **)*((_QWORD *)this + 12);
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
  v9 = *((_QWORD *)this + 12);
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
  v11 = *((_QWORD *)this + 12);
  if ( !v11 )
    goto LABEL_16;
  Parameters = DiagnosisTextParserImpl::GetParameters(v10, v11 + 16, &v17, &v19);
  if ( Parameters < 0 )
    goto LABEL_17;
  v13 = *((_QWORD *)this + 12);
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
0x180015de0  mov     [rsp-28h+arg_8], rbx
0x180015de5  push    rbp
0x180015de6  push    rsi
0x180015de7  push    rdi
0x180015de8  push    r14
0x180015dea  push    r15
0x180015dec  mov     rbp, rsp
0x180015def  sub     rsp, 40h
0x180015df3  cmp     qword ptr [rcx+50h], 0
0x180015df8  mov     r15, rdx
0x180015dfb  mov     rdi, rcx
0x180015dfe  jnz     short loc_180015E0A
0x180015e00  mov     eax, 80070015h
0x180015e05  jmp     loc_180015F6B
0x180015e0a  cmp     dword ptr [rcx+58h], 0
0x180015e0e  jz      loc_180015F64
0x180015e14  mov     r8, [rcx+60h]
0x180015e18  xor     esi, esi
0x180015e1a  xor     r14d, r14d
0x180015e1d  mov     [rbp+pv], 0
0x180015e25  mov     [rbp+var_20], 0
0x180015e2d  mov     [rbp+var_18], 0
0x180015e35  mov     [rbp+var_10], rsi
0x180015e39  mov     [rbp+arg_0], esi
0x180015e3c  mov     dword ptr [rbp+arg_10], r14d
0x180015e40  test    r8, r8
0x180015e43  jz      loc_180015F32
0x180015e49  mov     r8, [r8]; unsigned __int16 *
0x180015e4c  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180015e50  mov     edx, [r8-10h]
0x180015e54  inc     edx; unsigned int
0x180015e56  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x180015e5b  mov     ebx, eax
0x180015e5d  test    eax, eax
0x180015e5f  js      loc_180015F37
0x180015e65  mov     r8, [rdi+60h]
0x180015e69  test    r8, r8
0x180015e6c  jz      loc_180015F32
0x180015e72  mov     r8, [r8+8]; unsigned __int16 *
0x180015e76  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x180015e7a  mov     edx, [r8-10h]
0x180015e7e  inc     edx; unsigned int
0x180015e80  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x180015e85  mov     ebx, eax
0x180015e87  test    eax, eax
0x180015e89  js      loc_180015F37
0x180015e8f  mov     rdx, [rdi+60h]
0x180015e93  test    rdx, rdx
0x180015e96  jz      loc_180015F32
0x180015e9c  add     rdx, 10h
0x180015ea0  lea     r9, [rbp+arg_0]
0x180015ea4  lea     r8, [rbp+var_18]
0x180015ea8  call    ?GetParameters@DiagnosisTextParserImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEAPEAUDiagnosisParameter@DiagnosisTextParser@@PEAK@Z; DiagnosisTextParserImpl::GetParameters(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,DiagnosisTextParser::DiagnosisParameter * *,ulong *)
0x180015ead  mov     ebx, eax
0x180015eaf  test    eax, eax
0x180015eb1  js      loc_180015F37
0x180015eb7  mov     rdx, [rdi+60h]
0x180015ebb  test    rdx, rdx
0x180015ebe  jz      short loc_180015EDD
0x180015ec0  add     rdx, 20h ; ' '
0x180015ec4  lea     r9, [rbp+arg_10]
0x180015ec8  lea     r8, [rbp+var_10]
0x180015ecc  call    ?GetParameters@DiagnosisTextParserImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEAPEAUDiagnosisParameter@DiagnosisTextParser@@PEAK@Z; DiagnosisTextParserImpl::GetParameters(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,DiagnosisTextParser::DiagnosisParameter * *,ulong *)
0x180015ed1  mov     rsi, [rbp+var_10]
0x180015ed5  mov     ebx, eax
0x180015ed7  mov     r14d, dword ptr [rbp+arg_10]
0x180015edb  jmp     short loc_180015EE2
0x180015edd  mov     ebx, 8007000Eh
0x180015ee2  test    ebx, ebx
0x180015ee4  js      short loc_180015F37
0x180015ee6  lea     r8, [rbp+arg_10]
0x180015eea  mov     [rbp+arg_10], 0
0x180015ef2  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosisText@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIDiagnosisText>>::CreateInstance(void *,_GUID const &,void * *)
0x180015ef7  mov     ebx, eax
0x180015ef9  test    eax, eax
0x180015efb  js      short loc_180015F37
0x180015efd  mov     rcx, [rbp+arg_10]
0x180015f01  xor     ebx, ebx
0x180015f03  mov     rax, [rbp+pv]
0x180015f07  mov     [rcx+40h], rax
0x180015f0b  mov     rax, [rbp+var_20]
0x180015f0f  mov     [rcx+48h], rax
0x180015f13  mov     rax, [rbp+var_18]
0x180015f17  mov     [rcx+50h], rax
0x180015f1b  mov     eax, [rbp+arg_0]
0x180015f1e  mov     [rcx+58h], eax
0x180015f21  mov     [rcx+60h], rsi
0x180015f25  mov     [rcx+68h], r14d
0x180015f29  mov     rax, [rbp+arg_10]
0x180015f2d  mov     [r15], rax
0x180015f30  jmp     short loc_180015F69
0x180015f32  mov     ebx, 8007000Eh
0x180015f37  mov     rcx, [rbp+pv]; pv
0x180015f3b  call    cs:__imp_CoTaskMemFree
0x180015f41  mov     rcx, [rbp+var_20]; pv
0x180015f45  call    cs:__imp_CoTaskMemFree
0x180015f4b  mov     edx, [rbp+arg_0]; unsigned int
0x180015f4e  mov     rcx, [rbp+var_18]; struct DiagnosisTextParser::DiagnosisParameter *
0x180015f52  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x180015f57  mov     edx, r14d; unsigned int
0x180015f5a  mov     rcx, rsi; struct DiagnosisTextParser::DiagnosisParameter *
0x180015f5d  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x180015f62  jmp     short loc_180015F69
0x180015f64  mov     ebx, 1
0x180015f69  mov     eax, ebx
0x180015f6b  mov     rbx, [rsp+40h+arg_8]
0x180015f70  add     rsp, 40h
0x180015f74  pop     r15
0x180015f76  pop     r14
0x180015f78  pop     rdi
0x180015f79  pop     rsi
0x180015f7a  pop     rbp
0x180015f7b  retn
```
