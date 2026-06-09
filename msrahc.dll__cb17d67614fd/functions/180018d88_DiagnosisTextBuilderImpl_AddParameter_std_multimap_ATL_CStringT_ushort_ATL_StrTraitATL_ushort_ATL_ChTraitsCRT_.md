# DiagnosisTextBuilderImpl::AddParameter(std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &,ushort const *,ushort const *)

- ea: `0x180018d88`
- end: `0x180018e50`
- name: `?AddParameter@DiagnosisTextBuilderImpl@@AEAAJAEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@PEBG1@Z`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000da10`

## callees

- `0x180018780`
- `0x180018a2c`
- `0x180018b84`
- `0x180018cec`
- `0x180018d88`
- `0x1800194c0`
- `0x180019754`

## string_xrefs

- `0x180018dbc`: `LinkButtonText`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::AddParameter(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // ebx
  __int64 v8; // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-38h] BYREF
  ATL::CAtlException *v11; // [rsp+28h] [rbp-30h] BYREF
  _BYTE v12[40]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = a3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v14);
  try
  {
    v7 = InitializeString(&v13, L"LinkButtonText", *a1);
    if ( v7 >= 0 )
    {
      v7 = InitializeString(&v14, a4, *a1);
      if ( v7 >= 0 )
      {
        v8 = std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
               v12,
               &v13,
               &v14);
        std::multimap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::insert<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
          a2,
          v10,
          v8);
        std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(v12);
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
  }
  catch ( exception )
  {
    LODWORD(v14) = -2147467259;
    return (unsigned int)v14;
  }
  catch ( ATL::CAtlException *v11 )
  {
    LODWORD(v14) = *(_DWORD *)v11;
    return (unsigned int)v14;
  }
  v7 = InitializeString(&v13, L"LinkButtonText", *a1);
}

```

## disassembly

```asm
0x180018d88  mov     [rsp+arg_8], rbx
0x180018d8d  mov     [rsp+arg_10], r8
0x180018d92  push    rsi
0x180018d93  push    rdi
0x180018d94  push    r14
0x180018d96  sub     rsp, 40h
0x180018d9a  mov     rsi, r9
0x180018d9d  mov     r14, rdx
0x180018da0  mov     rdi, rcx
0x180018da3  lea     rcx, [rsp+58h+arg_0]
0x180018da8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018dad  nop
0x180018dae  lea     rcx, [rsp+58h+arg_10]
0x180018db3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018db8  nop
0x180018db9  mov     r8, [rdi]
0x180018dbc  lea     rdx, aLinkbuttontext; "LinkButtonText"
0x180018dc3  lea     rcx, [rsp+58h+arg_0]
0x180018dc8  call    ?InitializeString@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAUHINSTANCE__@@@Z; InitializeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,HINSTANCE__ *)
0x180018dcd  mov     ebx, eax
0x180018dcf  test    eax, eax
0x180018dd1  js      short loc_180018E1A
0x180018dd3  mov     r8, [rdi]
0x180018dd6  mov     rdx, rsi
0x180018dd9  lea     rcx, [rsp+58h+arg_10]
0x180018dde  call    ?InitializeString@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAUHINSTANCE__@@@Z; InitializeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,HINSTANCE__ *)
0x180018de3  mov     ebx, eax
0x180018de5  test    eax, eax
0x180018de7  js      short loc_180018E1A
0x180018de9  lea     r8, [rsp+58h+arg_10]
0x180018dee  lea     rdx, [rsp+58h+arg_0]
0x180018df3  lea     rcx, [rsp+58h+var_28]
0x180018df8  call    ??$?0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV01@@?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@QEAA@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAPEAX@Z; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,void * *)
0x180018dfd  nop
0x180018dfe  mov     r8, rax
0x180018e01  lea     rdx, [rsp+58h+var_38]
0x180018e06  mov     rcx, r14
0x180018e09  call    ??$insert@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@1@@Z; std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::insert<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &&)
0x180018e0e  nop
0x180018e0f  lea     rcx, [rsp+58h+var_28]
0x180018e14  call    ??1?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x180018e19  nop
0x180018e1a  mov     rcx, [rsp+58h+arg_10]
0x180018e1f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018e23  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018e28  nop
0x180018e29  mov     rcx, [rsp+58h+arg_0]
0x180018e2e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018e32  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018e37  nop
0x180018e38  jmp     short loc_180018E40
0x180018e3a  jmp     short $+2
0x180018e3c  mov     ebx, dword ptr [rsp+58h+arg_10]
0x180018e40  mov     eax, ebx
0x180018e42  mov     rbx, [rsp+58h+arg_8]
0x180018e47  add     rsp, 40h
0x180018e4b  pop     r14
0x180018e4d  pop     rdi
0x180018e4e  pop     rsi
0x180018e4f  retn
```
