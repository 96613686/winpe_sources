# RecoverComponents(IXMLDOMDocument *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &)

- ea: `0x18001df88`
- end: `0x18001e23e`
- name: `?RecoverComponents@@YAJPEAUIXMLDOMDocument@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@2@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e244`

## callees

- `0x180009d2c`
- `0x18000bae8`
- `0x180015b60`
- `0x18001d854`
- `0x18001de8c`
- `0x18001df88`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e177`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e1b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e177`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e1b9`

## string_xrefs

- `0x18001e0b0`: `Extensions`

## pseudocode

```c
__int64 __fastcall RecoverComponents(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void **a5)
{
  int ValueFromXML; // ebx
  _QWORD **v9; // rcx
  __int64 v10; // rcx
  void **v11; // rdx
  _QWORD **v12; // rcx
  void *v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  __int64 v17; // [rsp+20h] [rbp-68h] BYREF
  __int64 v18; // [rsp+28h] [rbp-60h] BYREF
  ATL::CAtlException *v19; // [rsp+30h] [rbp-58h] BYREF
  _QWORD **v20; // [rsp+38h] [rbp-50h] BYREF
  void *v21; // [rsp+40h] [rbp-48h]
  _QWORD **v22; // [rsp+48h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-38h]
  __int64 v24; // [rsp+90h] [rbp+8h] BYREF

  try
  {
    v24 = 0;
    ValueFromXML = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 360LL))(a1, &v24);
    if ( ValueFromXML >= 0 )
    {
      v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v17 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v23 = 0;
      v22 = (_QWORD **)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,int>>>::_Buyheadnode();
      v21 = 0;
      v20 = (_QWORD **)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,int>>>::_Buyheadnode();
      ValueFromXML = GetValueFromXML(v24, L"Title", (__int64)&v18);
      if ( ValueFromXML >= 0 )
      {
        ValueFromXML = GetValueFromXML(v24, L"Description", (__int64)&v17);
        if ( ValueFromXML >= 0 )
        {
          ValueFromXML = GetNameValuePairsFromXML(L"Parameters", v24, (__int64)&v22);
          if ( ValueFromXML >= 0 )
          {
            ValueFromXML = GetNameValuePairsFromXML(L"Extensions", v24, (__int64)&v20);
            if ( ValueFromXML >= 0 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                a2,
                &v18);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                a3,
                &v17);
              if ( (_QWORD ***)a4 != &v22 )
              {
                v9 = *(_QWORD ***)a4;
                *(_QWORD *)a4 = v22;
                v22 = v9;
                v10 = *(_QWORD *)(a4 + 8);
                *(_QWORD *)(a4 + 8) = v23;
                v23 = v10;
              }
              v11 = a5;
              if ( a5 != (void **)&v20 )
              {
                v12 = (_QWORD **)*a5;
                *a5 = v20;
                v20 = v12;
                v13 = v11[1];
                v11[1] = v21;
                v21 = v13;
              }
            }
          }
        }
      }
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
        (__int64)&v20,
        v20[1]);
      v20[1] = v20;
      *v20 = v20;
      v20[2] = v20;
      v21 = 0;
      operator delete(v20);
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
        (__int64)&v22,
        v22[1]);
      v22[1] = v22;
      *v22 = v22;
      v22[2] = v22;
      v23 = 0;
      operator delete(v22);
      v14 = (_QWORD *)(v17 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
      v15 = (_QWORD *)(v18 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
    }
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  catch ( exception )
  {
    LODWORD(v24) = -2147467259;
    return (unsigned int)v24;
  }
  catch ( ATL::CAtlException *v19 )
  {
    LODWORD(v24) = *(_DWORD *)v19;
    return (unsigned int)v24;
  }
  v24 = 0;
}

```

## disassembly

```asm
0x18001df88  mov     r11, rsp
0x18001df8b  push    rbx
0x18001df8c  push    rsi
0x18001df8d  push    rdi
0x18001df8e  push    r14
0x18001df90  sub     rsp, 68h
0x18001df94  mov     rdi, r9
0x18001df97  mov     r14, r8
0x18001df9a  mov     rsi, rdx
0x18001df9d  mov     qword ptr [r11+8], 0
0x18001dfa5  mov     rax, [rcx]
0x18001dfa8  lea     rdx, [r11+8]
0x18001dfac  mov     rax, [rax+168h]
0x18001dfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb8  mov     ebx, eax
0x18001dfba  test    eax, eax
0x18001dfbc  js      loc_18001E20F
0x18001dfc2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001dfc9  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001dfd0  mov     rax, [rax+18h]
0x18001dfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfd9  add     rax, 18h
0x18001dfdd  mov     [rsp+88h+var_60], rax
0x18001dfe2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001dfe9  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001dff0  mov     rax, [rax+18h]
0x18001dff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dff9  add     rax, 18h
0x18001dffd  mov     [rsp+88h+var_68], rax
0x18001e002  mov     [rsp+88h+var_40], 0
0x18001e00b  mov     [rsp+88h+var_38], 0
0x18001e014  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@H@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@H@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,int>>>::_Buyheadnode(void)
0x18001e019  mov     [rsp+88h+var_40], rax
0x18001e01e  mov     [rsp+88h+var_50], 0
0x18001e027  mov     [rsp+88h+var_48], 0
0x18001e030  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@H@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@H@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,int>>>::_Buyheadnode(void)
0x18001e035  mov     [rsp+88h+var_50], rax
0x18001e03a  lea     r8, [rsp+88h+var_60]
0x18001e03f  lea     rdx, aTitle; "Title"
0x18001e046  mov     rcx, [rsp+88h+arg_0]
0x18001e04e  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001e053  mov     ebx, eax
0x18001e055  test    eax, eax
0x18001e057  js      loc_18001E13C
0x18001e05d  lea     r8, [rsp+88h+var_68]
0x18001e062  lea     rdx, aDescription; "Description"
0x18001e069  mov     rcx, [rsp+88h+arg_0]
0x18001e071  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001e076  mov     ebx, eax
0x18001e078  test    eax, eax
0x18001e07a  js      loc_18001E13C
0x18001e080  lea     r8, [rsp+88h+var_40]
0x18001e085  mov     rdx, [rsp+88h+arg_0]
0x18001e08d  lea     rcx, aParameters; "Parameters"
0x18001e094  call    ?GetNameValuePairsFromXML@@YAJPEBGPEAUIXMLDOMElement@@AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@Z; GetNameValuePairsFromXML(ushort const *,IXMLDOMElement *,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x18001e099  mov     ebx, eax
0x18001e09b  test    eax, eax
0x18001e09d  js      loc_18001E13C
0x18001e0a3  lea     r8, [rsp+88h+var_50]
0x18001e0a8  mov     rdx, [rsp+88h+arg_0]
0x18001e0b0  lea     rcx, aExtensions; "Extensions"
0x18001e0b7  call    ?GetNameValuePairsFromXML@@YAJPEBGPEAUIXMLDOMElement@@AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@Z; GetNameValuePairsFromXML(ushort const *,IXMLDOMElement *,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x18001e0bc  mov     ebx, eax
0x18001e0be  test    eax, eax
0x18001e0c0  js      short loc_18001E13C
0x18001e0c2  lea     rdx, [rsp+88h+var_60]
0x18001e0c7  mov     rcx, rsi
0x18001e0ca  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001e0cf  lea     rdx, [rsp+88h+var_68]
0x18001e0d4  mov     rcx, r14
0x18001e0d7  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001e0dc  lea     rax, [rsp+88h+var_40]
0x18001e0e1  cmp     rdi, rax
0x18001e0e4  jz      short loc_18001E108
0x18001e0e6  mov     rcx, [rdi]
0x18001e0e9  mov     rax, [rsp+88h+var_40]
0x18001e0ee  mov     [rdi], rax
0x18001e0f1  mov     [rsp+88h+var_40], rcx
0x18001e0f6  mov     rcx, [rdi+8]
0x18001e0fa  mov     rax, [rsp+88h+var_38]
0x18001e0ff  mov     [rdi+8], rax
0x18001e103  mov     [rsp+88h+var_38], rcx
0x18001e108  lea     rax, [rsp+88h+var_50]
0x18001e10d  mov     rdx, [rsp+88h+arg_20]
0x18001e115  cmp     rdx, rax
0x18001e118  jz      short loc_18001E13C
0x18001e11a  mov     rcx, [rdx]
0x18001e11d  mov     rax, [rsp+88h+var_50]
0x18001e122  mov     [rdx], rax
0x18001e125  mov     [rsp+88h+var_50], rcx
0x18001e12a  mov     rcx, [rdx+8]
0x18001e12e  mov     rax, [rsp+88h+var_48]
0x18001e133  mov     [rdx+8], rax
0x18001e137  mov     [rsp+88h+var_48], rcx
0x18001e13c  mov     rdx, [rsp+88h+var_50]
0x18001e141  mov     rdx, [rdx+8]
0x18001e145  lea     rcx, [rsp+88h+var_50]
0x18001e14a  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18001e14f  mov     rax, [rsp+88h+var_50]
0x18001e154  mov     [rax+8], rax
0x18001e158  mov     rax, [rsp+88h+var_50]
0x18001e15d  mov     [rax], rax
0x18001e160  mov     rax, [rsp+88h+var_50]
0x18001e165  mov     [rax+10h], rax
0x18001e169  mov     [rsp+88h+var_48], 0
0x18001e172  mov     rcx, [rsp+88h+var_50]
0x18001e177  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e17d  nop
0x18001e17e  mov     rdx, [rsp+88h+var_40]
0x18001e183  mov     rdx, [rdx+8]
0x18001e187  lea     rcx, [rsp+88h+var_40]
0x18001e18c  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18001e191  mov     rax, [rsp+88h+var_40]
0x18001e196  mov     [rax+8], rax
0x18001e19a  mov     rax, [rsp+88h+var_40]
0x18001e19f  mov     [rax], rax
0x18001e1a2  mov     rax, [rsp+88h+var_40]
0x18001e1a7  mov     [rax+10h], rax
0x18001e1ab  mov     [rsp+88h+var_38], 0
0x18001e1b4  mov     rcx, [rsp+88h+var_40]
0x18001e1b9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e1bf  nop
0x18001e1c0  mov     rdx, [rsp+88h+var_68]
0x18001e1c5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001e1c9  or      edi, 0FFFFFFFFh
0x18001e1cc  mov     eax, edi
0x18001e1ce  lock xadd [rdx+10h], eax
0x18001e1d3  add     eax, edi
0x18001e1d5  test    eax, eax
0x18001e1d7  jg      short loc_18001E1E9
0x18001e1d9  mov     rcx, [rdx]
0x18001e1dc  mov     rax, [rcx]
0x18001e1df  mov     rax, [rax+8]
0x18001e1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e8  nop
0x18001e1e9  mov     rdx, [rsp+88h+var_60]
0x18001e1ee  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001e1f2  mov     eax, edi
0x18001e1f4  lock xadd [rdx+10h], eax
0x18001e1f9  add     eax, edi
0x18001e1fb  test    eax, eax
0x18001e1fd  jg      short loc_18001E20F
0x18001e1ff  mov     rcx, [rdx]
0x18001e202  mov     rax, [rcx]
0x18001e205  mov     rax, [rax+8]
0x18001e209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e20e  nop
0x18001e20f  mov     rcx, [rsp+88h+arg_0]
0x18001e217  test    rcx, rcx
0x18001e21a  jz      short loc_18001E229
0x18001e21c  mov     rax, [rcx]
0x18001e21f  mov     rax, [rax+10h]
0x18001e223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e228  nop
0x18001e229  jmp     short loc_18001E232
0x18001e22b  mov     ebx, dword ptr [rsp+88h+arg_0]
0x18001e232  mov     eax, ebx
0x18001e234  add     rsp, 68h
0x18001e238  pop     r14
0x18001e23a  pop     rdi
0x18001e23b  pop     rsi
0x18001e23c  pop     rbx
0x18001e23d  retn
```
