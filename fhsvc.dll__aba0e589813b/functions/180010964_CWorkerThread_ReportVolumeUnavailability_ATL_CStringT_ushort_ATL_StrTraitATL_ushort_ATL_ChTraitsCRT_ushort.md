# CWorkerThread::ReportVolumeUnavailability(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x180010964`
- end: `0x1800109cc`
- name: `?ReportVolumeUnavailability@CWorkerThread@@QEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ac48`

## callees

- `0x18000ac14`
- `0x18000be54`
- `0x180010964`
- `0x180013010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800109a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109a7`

## pseudocode

```c
__int64 __fastcall CWorkerThread::ReportVolumeUnavailability(__int64 a1, const unsigned __int16 **a2)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, __int64); // rsi
  __int64 v4; // rdx
  const unsigned __int16 **v5; // rbx
  unsigned int v7; // [rsp+20h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 **v9; // [rsp+48h] [rbp+10h]

  v9 = a2;
  try
  {
    v5 = a2;
    v2 = *(_QWORD *)(a1 + 16);
    v3 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 56LL);
    v4 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *a2);
    v3(v2, v4);
    SysFreeString(bstrString);
  }
  catch ( ATL::CAtlException v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v7);
    v5 = v9;
  }
  v5 = a2;
}

```

## disassembly

```asm
0x180010964  mov     r11, rsp
0x180010967  mov     [r11+18h], rbx
0x18001096b  mov     [r11+20h], rsi
0x18001096f  mov     [r11+10h], rdx
0x180010973  push    rdi
0x180010974  sub     rsp, 30h
0x180010978  mov     rbx, rdx
0x18001097b  mov     rdi, [rcx+10h]
0x18001097f  mov     rax, [rdi]
0x180010982  mov     rsi, [rax+38h]
0x180010986  mov     rdx, [rdx]; unsigned __int16 *
0x180010989  lea     rcx, [r11+8]; this
0x18001098d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180010992  nop
0x180010993  mov     rdx, [rax]
0x180010996  mov     rcx, rdi
0x180010999  mov     rax, rsi
0x18001099c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a1  nop
0x1800109a2  mov     rcx, [rsp+38h+bstrString]; bstrString
0x1800109a7  call    cs:__imp_SysFreeString
0x1800109ad  nop
0x1800109ae  jmp     short loc_1800109B5
0x1800109b0  mov     rbx, [rsp+38h+arg_8]
0x1800109b5  mov     rcx, rbx
0x1800109b8  mov     rbx, [rsp+38h+arg_10]
0x1800109bd  mov     rsi, [rsp+38h+arg_18]
0x1800109c2  add     rsp, 30h
0x1800109c6  pop     rdi
0x1800109c7  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
