# BDATuningModel::CRGSBag::CRGSBag(ushort const *,ATL::CRegObject &,unsigned __int64 &)

- ea: `0x18000dcf8`
- end: `0x18000ded4`
- name: `??0CRGSBag@BDATuningModel@@QEAA@PEBGAEAVCRegObject@ATL@@AEA_K@Z`
- size: `476`
- prototype: `__int64 __fastcall(BDATuningModel::CRGSBag *__hidden this, const unsigned __int16 *, struct ATL::CRegObject *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d5bc`
- `0x18000d728`
- `0x180042c4c`

## callees

- `0x180004640`
- `0x1800054c8`
- `0x18000dafc`
- `0x18000dc94`
- `0x18000dcf8`
- `0x18000e64c`
- `0x18000f204`
- `0x18000f368`
- `0x1800eeda0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000de8d`
- `ole32!CoTaskMemFree` at `0x18000de8d`
- `USER32!CharNextW` at `0x18000de70`
- `USER32!CharNextW` at `0x18000de70`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
BDATuningModel::CRGSBag *__fastcall BDATuningModel::CRGSBag::CRGSBag(
        BDATuningModel::CRGSBag *this,
        WCHAR *a2,
        struct ATL::CRegObject *a3,
        unsigned __int64 *a4)
{
  int v8; // eax
  _BYTE *v9; // rbx
  unsigned __int16 v10; // cx
  const WCHAR **v11; // rdi
  _WORD *v12; // rdx
  int v13; // eax
  const WCHAR *v14; // rcx
  LPVOID pv; // [rsp+20h] [rbp-2058h] BYREF
  int pExceptionObject; // [rsp+28h] [rbp-2050h] BYREF
  int v18; // [rsp+2Ch] [rbp-204Ch] BYREF
  int v19; // [rsp+30h] [rbp-2048h] BYREF
  BDATuningModel::CRGSBag *v20; // [rsp+38h] [rbp-2040h]
  unsigned __int16 v21[4096]; // [rsp+40h] [rbp-2038h] BYREF

  v20 = this;
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 32);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 10) = 0;
  std::map<WTL::CString,ATL::CComVariant>::map<WTL::CString,ATL::CComVariant>((char *)this + 88);
  *(_QWORD *)this = &ATL::CComObject<BDATuningModel::CRGSBagBase>::`vftable'{for `IObjectWithSiteImplSec<BDATuningModel::CRGSBagBase>'};
  *((_QWORD *)this + 2) = &ATL::CComObject<BDATuningModel::CRGSBagBase>::`vftable'{for `IPropertyBag2Impl<BDATuningModel::CRGSBagBase>'};
  *((_QWORD *)this + 3) = &ATL::CComObject<BDATuningModel::CRGSBagBase>::`vftable'{for `IPropertyBag'};
  _InterlockedIncrement(&dword_18021CFF8);
  *((_QWORD *)this + 14) = a3;
  *((_QWORD *)this + 13) = 0;
  *(_QWORD *)this = &BDATuningModel::CRGSBag::`vftable'{for `IObjectWithSiteImplSec<BDATuningModel::CRGSBagBase>'};
  *((_QWORD *)this + 2) = &BDATuningModel::CRGSBag::`vftable'{for `IPropertyBag2Impl<BDATuningModel::CRGSBagBase>'};
  *((_QWORD *)this + 3) = &BDATuningModel::CRGSBag::`vftable'{for `IPropertyBag'};
  pv = 0;
  v8 = ATL::CRegParser::PreProcessBuffer((BDATuningModel::CRGSBag *)((char *)this + 104), a2, &pv);
  if ( v8 < 0 || (v9 = pv) == 0 )
  {
    v19 = v8;
    throw (ComException *)&v19;
  }
  v10 = 0;
  v21[0] = 0;
  *((_QWORD *)this + 13) = pv;
  *a4 = 0;
  try
  {
    while ( 1 )
    {
      v11 = (const WCHAR **)((char *)this + 104);
      v12 = (_WORD *)*((_QWORD *)this + 13);
      if ( !v12
        || !*v12
        || v10 == 125
        || (int)ATL::CRegParser::NextToken((BDATuningModel::CRGSBag *)((char *)this + 104), v21) < 0 )
      {
        break;
      }
      if ( v21[0] != 123 )
      {
        pExceptionObject = -2147352567;
        throw (ComException *)&pExceptionObject;
      }
      v13 = BDATuningModel::CRGSBag::BuildMapFromFragment(this, v21);
      if ( v13 < 0 )
      {
        v18 = v13;
        throw (ComException *)&v18;
      }
      v10 = v21[0];
    }
    v14 = *v11;
    if ( **v11 )
    {
      v14 = CharNextW(v14);
      *v11 = v14;
    }
    *a4 = ((char *)v14 - v9) >> 1;
    if ( v9 )
    {
      CoTaskMemFree(v9);
      pv = 0;
    }
  }
  catch ( ... )
  {
    if ( pv )
      CoTaskMemFree(pv);
    throw;
  }
  return this;
}

```

## disassembly

```asm
0x18000dcf8  push    rbx
0x18000dcfa  push    rsi
0x18000dcfb  push    rdi
0x18000dcfc  push    r14
0x18000dcfe  push    r15
0x18000dd00  mov     eax, 2050h
0x18000dd05  call    _alloca_probe
0x18000dd0a  sub     rsp, rax
0x18000dd0d  mov     rax, cs:__security_cookie
0x18000dd14  xor     rax, rsp
0x18000dd17  mov     [rsp+2078h+var_38], rax
0x18000dd1f  mov     r14, r9
0x18000dd22  mov     rbx, r8
0x18000dd25  mov     rdi, rdx
0x18000dd28  mov     rsi, rcx
0x18000dd2b  mov     [rsp+2078h+var_2040], rcx
0x18000dd30  add     rcx, 20h ; ' '
0x18000dd34  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18000dd39  nop
0x18000dd3a  mov     qword ptr [rsi+8], 0
0x18000dd42  mov     qword ptr [rsi+50h], 0
0x18000dd4a  lea     rcx, [rsi+58h]
0x18000dd4e  call    ??0?$map@VCString@WTL@@VCComVariant@ATL@@U?$less@VCString@WTL@@@std@@V?$allocator@U?$pair@$$CBVCString@WTL@@VCComVariant@ATL@@@std@@@6@@std@@QEAA@XZ; std::map<WTL::CString,ATL::CComVariant>::map<WTL::CString,ATL::CComVariant>(void)
0x18000dd53  nop
0x18000dd54  lea     rax, ??_7?$CComObject@VCRGSBagBase@BDATuningModel@@@ATL@@6B?$IObjectWithSiteImplSec@VCRGSBagBase@BDATuningModel@@@@@; const ATL::CComObject<BDATuningModel::CRGSBagBase>::`vftable'{for `IObjectWithSiteImplSec<BDATuningModel::CRGSBagBase>'}
0x18000dd5b  mov     [rsi], rax
0x18000dd5e  lea     rax, ??_7?$CComObject@VCRGSBagBase@BDATuningModel@@@ATL@@6B?$IPropertyBag2Impl@VCRGSBagBase@BDATuningModel@@@@@; const ATL::CComObject<BDATuningModel::CRGSBagBase>::`vftable'{for `IPropertyBag2Impl<BDATuningModel::CRGSBagBase>'}
0x18000dd65  mov     [rsi+10h], rax
0x18000dd69  lea     rax, ??_7?$CComObject@VCRGSBagBase@BDATuningModel@@@ATL@@6BIPropertyBag@@@; const ATL::CComObject<BDATuningModel::CRGSBagBase>::`vftable'{for `IPropertyBag'}
0x18000dd70  mov     [rsi+18h], rax
0x18000dd74  lock inc cs:dword_18021CFF8
0x18000dd7b  lea     r15, [rsi+68h]
0x18000dd7f  mov     [r15+8], rbx
0x18000dd83  mov     qword ptr [r15], 0
0x18000dd8a  lea     rax, ??_7CRGSBag@BDATuningModel@@6B?$IObjectWithSiteImplSec@VCRGSBagBase@BDATuningModel@@@@@; const BDATuningModel::CRGSBag::`vftable'{for `IObjectWithSiteImplSec<BDATuningModel::CRGSBagBase>'}
0x18000dd91  mov     [rsi], rax
0x18000dd94  lea     rax, ??_7CRGSBag@BDATuningModel@@6B?$IPropertyBag2Impl@VCRGSBagBase@BDATuningModel@@@@@; const BDATuningModel::CRGSBag::`vftable'{for `IPropertyBag2Impl<BDATuningModel::CRGSBagBase>'}
0x18000dd9b  mov     [rsi+10h], rax
0x18000dd9f  lea     rax, ??_7CRGSBag@BDATuningModel@@6BIPropertyBag@@@; const BDATuningModel::CRGSBag::`vftable'{for `IPropertyBag'}
0x18000dda6  mov     [rsi+18h], rax
0x18000ddaa  mov     [rsp+2078h+pv], 0
0x18000ddb3  lea     r8, [rsp+2078h+pv]; unsigned __int16 **
0x18000ddb8  mov     rdx, rdi; unsigned __int16 *
0x18000ddbb  mov     rcx, r15; this
0x18000ddbe  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x18000ddc3  test    eax, eax
0x18000ddc5  js      loc_18000DEBE
0x18000ddcb  mov     rbx, [rsp+2078h+pv]
0x18000ddd0  test    rbx, rbx
0x18000ddd3  jz      loc_18000DEBE
0x18000ddd9  xor     ecx, ecx
0x18000dddb  mov     [rsp+2078h+var_2038], cx
0x18000dde0  mov     [r15], rbx
0x18000dde3  mov     [r14], rcx
0x18000dde6  lea     rdi, [rsi+68h]
0x18000ddea  mov     rdx, [rdi]
0x18000dded  test    rdx, rdx
0x18000ddf0  jz      short loc_18000DE66
0x18000ddf2  xor     eax, eax
0x18000ddf4  cmp     ax, [rdx]
0x18000ddf7  jz      short loc_18000DE66
0x18000ddf9  mov     eax, 7Dh ; '}'
0x18000ddfe  cmp     ax, cx
0x18000de01  jz      short loc_18000DE66
0x18000de03  lea     rdx, [rsp+2078h+var_2038]; unsigned __int16 *
0x18000de08  mov     rcx, rdi; this
0x18000de0b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000de10  test    eax, eax
0x18000de12  js      short loc_18000DE66
0x18000de14  mov     eax, 7Bh ; '{'
0x18000de19  cmp     ax, [rsp+2078h+var_2038]
0x18000de1e  jz      short loc_18000DE39
0x18000de20  mov     [rsp+2078h+pExceptionObject], 80020009h
0x18000de28  lea     rdx, _TI1?AVComException@@; pThrowInfo
0x18000de2f  lea     rcx, [rsp+2078h+pExceptionObject]; pExceptionObject
0x18000de34  call    _CxxThrowException_0
0x18000de39  lea     rdx, [rsp+2078h+var_2038]; unsigned __int16 *
0x18000de3e  mov     rcx, rsi; this
0x18000de41  call    ?BuildMapFromFragment@CRGSBag@BDATuningModel@@QEAAJPEAG@Z; BDATuningModel::CRGSBag::BuildMapFromFragment(ushort *)
0x18000de46  test    eax, eax
0x18000de48  js      short loc_18000DE51
0x18000de4a  movzx   ecx, [rsp+2078h+var_2038]
0x18000de4f  jmp     short loc_18000DDE6
0x18000de51  mov     [rsp+2078h+var_204C], eax
0x18000de55  lea     rdx, _TI1?AVComException@@; pThrowInfo
0x18000de5c  lea     rcx, [rsp+2078h+var_204C]; pExceptionObject
0x18000de61  call    _CxxThrowException_0
0x18000de66  mov     rcx, [rdi]; lpsz
0x18000de69  xor     eax, eax
0x18000de6b  cmp     ax, [rcx]
0x18000de6e  jz      short loc_18000DE7C
0x18000de70  call    cs:__imp_CharNextW
0x18000de76  mov     rcx, rax
0x18000de79  mov     [rdi], rax
0x18000de7c  sub     rcx, rbx
0x18000de7f  sar     rcx, 1
0x18000de82  mov     [r14], rcx
0x18000de85  test    rbx, rbx
0x18000de88  jz      short loc_18000DE9C
0x18000de8a  mov     rcx, rbx; pv
0x18000de8d  call    cs:__imp_CoTaskMemFree
0x18000de93  mov     [rsp+2078h+pv], 0
0x18000de9c  mov     rax, rsi
0x18000de9f  mov     rcx, [rsp+2078h+var_38]
0x18000dea7  xor     rcx, rsp; StackCookie
0x18000deaa  call    __security_check_cookie
0x18000deaf  add     rsp, 2050h
0x18000deb6  pop     r15
0x18000deb8  pop     r14
0x18000deba  pop     rdi
0x18000debb  pop     rsi
0x18000debc  pop     rbx
0x18000debd  retn
0x18000debe  mov     [rsp+2078h+var_2048], eax
0x18000dec2  lea     rdx, _TI1?AVComException@@; pThrowInfo
0x18000dec9  lea     rcx, [rsp+2078h+var_2048]; pExceptionObject
0x18000dece  call    _CxxThrowException_0
```
