# RecoverComponents(IXMLDOMDocument *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &)

- ea: `0x18002be68`
- end: `0x18002c0b7`
- name: `?RecoverComponents@@YAJPEAUIXMLDOMDocument@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@2@Z`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c314`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x180008c84`
- `0x180009e58`
- `0x18002b908`
- `0x18002b9a0`
- `0x18002bac4`
- `0x18002bd7c`
- `0x18002be68`
- `0x18002f010`

## string_xrefs

- `0x18002bf48`: `Extensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RecoverComponents(__int64 a1, char **a2, char **a3, __int64 *a4, __int64 *a5)
{
  int ValueFromXML; // ebx
  volatile signed __int32 *v9; // rcx
  int *v10; // rdi
  volatile signed __int32 *v11; // r15
  volatile signed __int32 *v12; // rcx
  int *v13; // rdi
  volatile signed __int32 *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  _BYTE *v21; // [rsp+20h] [rbp-78h] BYREF
  _BYTE *v22; // [rsp+28h] [rbp-70h] BYREF
  ATL::CAtlException *v23; // [rsp+30h] [rbp-68h] BYREF
  __int64 v24; // [rsp+38h] [rbp-60h] BYREF
  __int64 v25; // [rsp+40h] [rbp-58h]
  __int64 v26; // [rsp+48h] [rbp-50h] BYREF
  __int64 v27; // [rsp+50h] [rbp-48h]
  __int64 v28; // [rsp+A0h] [rbp+8h] BYREF

  try
  {
    v28 = 0;
    ValueFromXML = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 360LL))(a1, &v28);
    if ( ValueFromXML >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v22);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v21);
      std::multimap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::multimap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v26);
      std::multimap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::multimap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v24);
      ValueFromXML = GetValueFromXML(v28, L"Title", (__int64)&v22);
      if ( ValueFromXML >= 0 )
      {
        ValueFromXML = GetValueFromXML(v28, L"Description", (__int64)&v21);
        if ( ValueFromXML >= 0 )
        {
          ValueFromXML = GetNameValuePairsFromXML(L"Parameters", v28, (__int64)&v26);
          if ( ValueFromXML >= 0 )
          {
            ValueFromXML = GetNameValuePairsFromXML(L"Extensions", v28, (__int64)&v24);
            if ( ValueFromXML >= 0 )
            {
              v9 = (volatile signed __int32 *)(v22 - 24);
              v10 = (int *)(*a2 - 24);
              if ( v22 - 24 != (_BYTE *)v10 )
              {
                if ( v10[4] >= 0 && *(_QWORD *)v9 == *(_QWORD *)v10 )
                {
                  v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v9);
                  ATL::CStringData::Release((ATL::CStringData *)v10);
                  *a2 = (char *)(v11 + 6);
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v22, *((_DWORD *)v22 - 4));
                }
              }
              v12 = (volatile signed __int32 *)(v21 - 24);
              v13 = (int *)(*a3 - 24);
              if ( v21 - 24 != (_BYTE *)v13 )
              {
                if ( v13[4] >= 0 && *(_QWORD *)v12 == *(_QWORD *)v13 )
                {
                  v14 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12);
                  ATL::CStringData::Release((ATL::CStringData *)v13);
                  *a3 = (char *)(v14 + 6);
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v21, *((_DWORD *)v21 - 4));
                }
              }
              if ( a4 != &v26 )
              {
                v15 = *a4;
                *a4 = v26;
                v26 = v15;
                v16 = a4[1];
                a4[1] = v27;
                v27 = v16;
              }
              v17 = a5;
              if ( a5 != &v24 )
              {
                v18 = *a5;
                *a5 = v24;
                v24 = v18;
                v19 = v17[1];
                v17[1] = v25;
                v25 = v19;
              }
            }
          }
        }
      }
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>(&v24);
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>(&v26);
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
    }
    ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v28);
  }
  catch ( exception )
  {
    LODWORD(v28) = -2147467259;
    return (unsigned int)v28;
  }
  catch ( ATL::CAtlException *v23 )
  {
    LODWORD(v28) = *(_DWORD *)v23;
    return (unsigned int)v28;
  }
  return (unsigned int)ValueFromXML;
}

```

## disassembly

```asm
0x18002be68  mov     r11, rsp
0x18002be6b  push    rbx
0x18002be6c  push    rsi
0x18002be6d  push    rdi
0x18002be6e  push    r12
0x18002be70  push    r14
0x18002be72  push    r15
0x18002be74  sub     rsp, 68h
0x18002be78  mov     rsi, r9
0x18002be7b  mov     r12, r8
0x18002be7e  mov     r14, rdx
0x18002be81  mov     qword ptr [r11+8], 0
0x18002be89  mov     rax, [rcx]
0x18002be8c  lea     rdx, [r11+8]
0x18002be90  mov     rax, [rax+168h]
0x18002be97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be9c  mov     ebx, eax
0x18002be9e  test    eax, eax
0x18002bea0  js      loc_18002C08E
0x18002bea6  lea     rcx, [rsp+98h+var_70]
0x18002beab  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002beb0  nop
0x18002beb1  lea     rcx, [rsp+98h+var_78]
0x18002beb6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002bebb  nop
0x18002bebc  lea     rcx, [rsp+98h+var_50]
0x18002bec1  call    ??0?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAA@XZ; std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x18002bec6  nop
0x18002bec7  lea     rcx, [rsp+98h+var_60]
0x18002becc  call    ??0?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAA@XZ; std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x18002bed1  nop
0x18002bed2  lea     r8, [rsp+98h+var_70]
0x18002bed7  lea     rdx, aTitle; "Title"
0x18002bede  mov     rcx, [rsp+98h+arg_0]
0x18002bee6  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002beeb  mov     ebx, eax
0x18002beed  test    eax, eax
0x18002beef  js      loc_18002C05A
0x18002bef5  lea     r8, [rsp+98h+var_78]
0x18002befa  lea     rdx, aDescription; "Description"
0x18002bf01  mov     rcx, [rsp+98h+arg_0]
0x18002bf09  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002bf0e  mov     ebx, eax
0x18002bf10  test    eax, eax
0x18002bf12  js      loc_18002C05A
0x18002bf18  lea     r8, [rsp+98h+var_50]
0x18002bf1d  mov     rdx, [rsp+98h+arg_0]
0x18002bf25  lea     rcx, aParameters; "Parameters"
0x18002bf2c  call    ?GetNameValuePairsFromXML@@YAJPEBGPEAUIXMLDOMElement@@AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@Z; GetNameValuePairsFromXML(ushort const *,IXMLDOMElement *,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x18002bf31  mov     ebx, eax
0x18002bf33  test    eax, eax
0x18002bf35  js      loc_18002C05A
0x18002bf3b  lea     r8, [rsp+98h+var_60]
0x18002bf40  mov     rdx, [rsp+98h+arg_0]
0x18002bf48  lea     rcx, aExtensions; "Extensions"
0x18002bf4f  call    ?GetNameValuePairsFromXML@@YAJPEBGPEAUIXMLDOMElement@@AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@Z; GetNameValuePairsFromXML(ushort const *,IXMLDOMElement *,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x18002bf54  mov     ebx, eax
0x18002bf56  test    eax, eax
0x18002bf58  js      loc_18002C05A
0x18002bf5e  mov     rcx, [rsp+98h+var_70]
0x18002bf63  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18002bf67  mov     rdi, [r14]
0x18002bf6a  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18002bf6e  cmp     rcx, rdi
0x18002bf71  jz      short loc_18002BFAB
0x18002bf73  cmp     dword ptr [rdi+10h], 0
0x18002bf77  jl      short loc_18002BF9A
0x18002bf79  mov     rax, [rdi]
0x18002bf7c  cmp     [rcx], rax
0x18002bf7f  jnz     short loc_18002BF9A
0x18002bf81  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002bf86  mov     r15, rax
0x18002bf89  mov     rcx, rdi; this
0x18002bf8c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bf91  lea     rax, [r15+18h]
0x18002bf95  mov     [r14], rax
0x18002bf98  jmp     short loc_18002BFAB
0x18002bf9a  mov     rdx, [rsp+98h+var_70]
0x18002bf9f  mov     r8d, [rdx-10h]
0x18002bfa3  mov     rcx, r14
0x18002bfa6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002bfab  mov     rcx, [rsp+98h+var_78]
0x18002bfb0  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18002bfb4  mov     rdi, [r12]
0x18002bfb8  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18002bfbc  cmp     rcx, rdi
0x18002bfbf  jz      short loc_18002BFFA
0x18002bfc1  cmp     dword ptr [rdi+10h], 0
0x18002bfc5  jl      short loc_18002BFE9
0x18002bfc7  mov     rax, [rdi]
0x18002bfca  cmp     [rcx], rax
0x18002bfcd  jnz     short loc_18002BFE9
0x18002bfcf  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002bfd4  mov     r14, rax
0x18002bfd7  mov     rcx, rdi; this
0x18002bfda  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bfdf  lea     rax, [r14+18h]
0x18002bfe3  mov     [r12], rax
0x18002bfe7  jmp     short loc_18002BFFA
0x18002bfe9  mov     rdx, [rsp+98h+var_78]
0x18002bfee  mov     r8d, [rdx-10h]
0x18002bff2  mov     rcx, r12
0x18002bff5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002bffa  lea     rax, [rsp+98h+var_50]
0x18002bfff  cmp     rsi, rax
0x18002c002  jz      short loc_18002C026
0x18002c004  mov     rcx, [rsi]
0x18002c007  mov     rax, [rsp+98h+var_50]
0x18002c00c  mov     [rsi], rax
0x18002c00f  mov     [rsp+98h+var_50], rcx
0x18002c014  mov     rcx, [rsi+8]
0x18002c018  mov     rax, [rsp+98h+var_48]
0x18002c01d  mov     [rsi+8], rax
0x18002c021  mov     [rsp+98h+var_48], rcx
0x18002c026  lea     rax, [rsp+98h+var_60]
0x18002c02b  mov     rdx, [rsp+98h+arg_20]
0x18002c033  cmp     rdx, rax
0x18002c036  jz      short loc_18002C05A
0x18002c038  mov     rcx, [rdx]
0x18002c03b  mov     rax, [rsp+98h+var_60]
0x18002c040  mov     [rdx], rax
0x18002c043  mov     [rsp+98h+var_60], rcx
0x18002c048  mov     rcx, [rdx+8]
0x18002c04c  mov     rax, [rsp+98h+var_58]
0x18002c051  mov     [rdx+8], rax
0x18002c055  mov     [rsp+98h+var_58], rcx
0x18002c05a  lea     rcx, [rsp+98h+var_60]
0x18002c05f  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>(void)
0x18002c064  nop
0x18002c065  lea     rcx, [rsp+98h+var_50]
0x18002c06a  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>(void)
0x18002c06f  nop
0x18002c070  mov     rcx, [rsp+98h+var_78]
0x18002c075  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c079  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c07e  nop
0x18002c07f  mov     rcx, [rsp+98h+var_70]
0x18002c084  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c088  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c08d  nop
0x18002c08e  lea     rcx, [rsp+98h+arg_0]
0x18002c096  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002c09b  nop
0x18002c09c  jmp     short loc_18002C0A7
0x18002c09e  jmp     short $+2
0x18002c0a0  mov     ebx, dword ptr [rsp+98h+arg_0]
0x18002c0a7  mov     eax, ebx
0x18002c0a9  add     rsp, 68h
0x18002c0ad  pop     r15
0x18002c0af  pop     r14
0x18002c0b1  pop     r12
0x18002c0b3  pop     rdi
0x18002c0b4  pop     rsi
0x18002c0b5  pop     rbx
0x18002c0b6  retn
```
