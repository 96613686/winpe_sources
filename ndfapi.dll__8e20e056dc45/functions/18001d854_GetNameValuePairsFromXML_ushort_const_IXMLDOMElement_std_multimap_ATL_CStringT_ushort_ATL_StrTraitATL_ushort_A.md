# GetNameValuePairsFromXML(ushort const *,IXMLDOMElement *,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &)

- ea: `0x18001d854`
- end: `0x18001dbad`
- name: `?GetNameValuePairsFromXML@@YAJPEBGPEAUIXMLDOMElement@@AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(const OLECHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001df88`

## callees

- `0x18000bdc4`
- `0x180010b18`
- `0x180010e0c`
- `0x18001d854`
- `0x18001de8c`
- `0x180021010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d87b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d87b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d8ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d8ac`

## pseudocode

```c
__int64 __fastcall GetNameValuePairsFromXML(const OLECHAR *a1, __int64 a2, __int64 a3)
{
  OLECHAR *v5; // rbx
  int ValueFromXML; // r14d
  __int64 v7; // rbx
  __int64 v8; // rdi
  int v9; // eax
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rax
  int v13; // r8d
  volatile signed __int32 *v14; // rdx
  volatile signed __int32 *v15; // rdx
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h]
  volatile signed __int32 *v21; // [rsp+50h] [rbp-20h] BYREF
  volatile signed __int32 *v22; // [rsp+58h] [rbp-18h]
  char v23; // [rsp+60h] [rbp-10h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+48h] BYREF

  v19 = 0;
  v5 = SysAllocString(a1);
  if ( v5 )
  {
    ValueFromXML = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)a2 + 296LL))(a2, v5, &v19);
    SysFreeString(v5);
    if ( ValueFromXML )
    {
      if ( ValueFromXML == 1 )
        ValueFromXML = 0;
    }
    else
    {
      v18 = 0;
      ValueFromXML = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 96LL))(v19, &v18);
      if ( ValueFromXML >= 0 )
      {
        while ( 2 )
        {
          v7 = 0;
          v20 = 0;
          v8 = v18;
          while ( 1 )
          {
            v17 = 0;
            LODWORD(v24) = 1;
            v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 72LL))(v8, &v17);
            ValueFromXML = v9;
            if ( v9 >= 0 )
            {
              if ( v9 == 1 || !v17 )
              {
                if ( v17 )
                  (*(void (**)(void))(*(_QWORD *)v17 + 16LL))();
                goto LABEL_35;
              }
              ValueFromXML = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 80LL))(v17, &v24);
              if ( ValueFromXML >= 0 && (_DWORD)v24 == 1 )
                break;
            }
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            if ( ValueFromXML < 0 )
              goto LABEL_16;
          }
          v7 = v17;
          v20 = v17;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_16:
          if ( ValueFromXML == 1 )
          {
LABEL_35:
            ValueFromXML = 0;
            if ( v7 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            break;
          }
          if ( ValueFromXML >= 0 )
          {
            v17 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
            v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
            v24 = v10;
            ValueFromXML = GetValueFromXML(v7, L"Name", &v17);
            v11 = v17;
            if ( ValueFromXML >= 0 )
            {
              ValueFromXML = GetValueFromXML(v7, L"Value", &v24);
              if ( ValueFromXML < 0 )
              {
                v10 = v24;
              }
              else
              {
                v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData((volatile signed __int32 *)(v11 - 24)) + 6;
                v10 = v24;
                v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData((volatile signed __int32 *)(v24 - 24)) + 6;
                v12 = std::_Tree_buy<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::_Buynode<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
                        a3,
                        &v21);
                std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Insert_nohint<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>> &,std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *> *>(
                  a3,
                  (unsigned int)&v23,
                  v13,
                  v12 + 32,
                  v12);
                v14 = v22 - 6;
                if ( _InterlockedDecrement(v22 - 2) <= 0 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
                v15 = v21 - 6;
                if ( _InterlockedDecrement(v21 - 2) <= 0 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
              }
            }
            if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
            if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24));
          }
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          if ( ValueFromXML >= 0 )
            continue;
          break;
        }
      }
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  else
  {
    ValueFromXML = -2147024882;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)ValueFromXML;
}

```

## disassembly

```asm
0x18001d854  mov     [rsp-28h+arg_0], rbx
0x18001d859  mov     [rsp-28h+arg_8], rsi
0x18001d85e  push    rbp
0x18001d85f  push    rdi
0x18001d860  push    r13
0x18001d862  push    r14
0x18001d864  push    r15
0x18001d866  mov     rbp, rsp
0x18001d869  sub     rsp, 70h
0x18001d86d  mov     r15, r8
0x18001d870  mov     rdi, rdx
0x18001d873  mov     [rbp+var_30], 0
0x18001d87b  call    cs:__imp_SysAllocString
0x18001d881  mov     rbx, rax
0x18001d884  test    rax, rax
0x18001d887  jz      loc_18001DB75
0x18001d88d  mov     rcx, [rdi]
0x18001d890  mov     rax, [rcx+128h]
0x18001d897  lea     r8, [rbp+var_30]
0x18001d89b  mov     rdx, rbx
0x18001d89e  mov     rcx, rdi
0x18001d8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8a6  mov     r14d, eax
0x18001d8a9  mov     rcx, rbx; bstrString
0x18001d8ac  call    cs:__imp_SysFreeString
0x18001d8b2  test    r14d, r14d
0x18001d8b5  jnz     loc_18001DB6A
0x18001d8bb  mov     [rbp+var_38], 0
0x18001d8c3  mov     rcx, [rbp+var_30]
0x18001d8c7  mov     rax, [rcx]
0x18001d8ca  lea     rdx, [rbp+var_38]
0x18001d8ce  mov     rax, [rax+60h]
0x18001d8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d7  mov     r14d, eax
0x18001d8da  test    eax, eax
0x18001d8dc  js      loc_18001DB52
0x18001d8e2  or      r13d, 0FFFFFFFFh
0x18001d8e6  xor     ebx, ebx
0x18001d8e8  mov     [rbp+var_28], rbx
0x18001d8ec  mov     rdi, [rbp+var_38]
0x18001d8f0  mov     [rbp+var_40], 0
0x18001d8f8  mov     dword ptr [rbp+arg_18], 1
0x18001d8ff  mov     rax, [rdi]
0x18001d902  lea     rdx, [rbp+var_40]
0x18001d906  mov     rcx, rdi
0x18001d909  mov     rax, [rax+48h]
0x18001d90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d912  mov     r14d, eax
0x18001d915  test    eax, eax
0x18001d917  js      short loc_18001D94C
0x18001d919  mov     rcx, [rbp+var_40]
0x18001d91d  cmp     eax, 1
0x18001d920  jz      loc_18001DB28
0x18001d926  test    rcx, rcx
0x18001d929  jz      loc_18001DB28
0x18001d92f  mov     rax, [rcx]
0x18001d932  lea     rdx, [rbp+arg_18]
0x18001d936  mov     rax, [rax+50h]
0x18001d93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d93f  mov     r14d, eax
0x18001d942  test    eax, eax
0x18001d944  js      short loc_18001D94C
0x18001d946  cmp     dword ptr [rbp+arg_18], 1
0x18001d94a  jz      short loc_18001D969
0x18001d94c  mov     rcx, [rbp+var_40]
0x18001d950  test    rcx, rcx
0x18001d953  jz      short loc_18001D962
0x18001d955  mov     rax, [rcx]
0x18001d958  mov     rax, [rax+10h]
0x18001d95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d961  nop
0x18001d962  test    r14d, r14d
0x18001d965  jns     short loc_18001D8F0
0x18001d967  jmp     short loc_18001D997
0x18001d969  mov     rbx, [rbp+var_40]
0x18001d96d  mov     [rbp+var_28], rbx
0x18001d971  mov     rax, [rbx]
0x18001d974  mov     rcx, rbx
0x18001d977  mov     rax, [rax+8]
0x18001d97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d980  nop
0x18001d981  mov     rcx, [rbp+var_40]
0x18001d985  test    rcx, rcx
0x18001d988  jz      short loc_18001D997
0x18001d98a  mov     rax, [rcx]
0x18001d98d  mov     rax, [rax+10h]
0x18001d991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d996  nop
0x18001d997  cmp     r14d, 1
0x18001d99b  jz      loc_18001DB3A
0x18001d9a1  test    r14d, r14d
0x18001d9a4  js      loc_18001DB08
0x18001d9aa  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d9b1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d9b8  mov     rax, [rax+18h]
0x18001d9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9c1  add     rax, 18h
0x18001d9c5  mov     [rbp+var_40], rax
0x18001d9c9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d9d0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d9d7  mov     rax, [rax+18h]
0x18001d9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9e0  lea     rdi, [rax+18h]
0x18001d9e4  mov     [rbp+arg_18], rdi
0x18001d9e8  lea     r8, [rbp+var_40]
0x18001d9ec  lea     rdx, aName; "Name"
0x18001d9f3  mov     rcx, rbx
0x18001d9f6  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001d9fb  mov     r14d, eax
0x18001d9fe  mov     rsi, [rbp+var_40]
0x18001da02  test    eax, eax
0x18001da04  js      loc_18001DAC2
0x18001da0a  lea     r8, [rbp+arg_18]
0x18001da0e  lea     rdx, aValue; "Value"
0x18001da15  mov     rcx, rbx
0x18001da18  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001da1d  mov     r14d, eax
0x18001da20  test    eax, eax
0x18001da22  js      loc_18001DABE
0x18001da28  lea     rcx, [rsi-18h]
0x18001da2c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001da31  add     rax, 18h
0x18001da35  mov     [rbp+var_20], rax
0x18001da39  mov     rdi, [rbp+arg_18]
0x18001da3d  lea     rcx, [rdi-18h]
0x18001da41  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001da46  add     rax, 18h
0x18001da4a  mov     [rbp+var_18], rax
0x18001da4e  lea     rdx, [rbp+var_20]
0x18001da52  mov     rcx, r15
0x18001da55  call    ??$_Buynode@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@?$_Tree_buy@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@1@@Z; std::_Tree_buy<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::_Buynode<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &&)
0x18001da5a  lea     r9, [rax+20h]
0x18001da5e  mov     [rsp+70h+var_50], rax
0x18001da63  lea     rdx, [rbp+var_10]
0x18001da67  mov     rcx, r15
0x18001da6a  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Insert_nohint<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>(bool,std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18001da6f  nop
0x18001da70  mov     rdx, [rbp+var_18]
0x18001da74  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001da78  mov     eax, r13d
0x18001da7b  lock xadd [rdx+10h], eax
0x18001da80  add     eax, r13d
0x18001da83  test    eax, eax
0x18001da85  jg      short loc_18001DA96
0x18001da87  mov     rcx, [rdx]
0x18001da8a  mov     rax, [rcx]
0x18001da8d  mov     rax, [rax+8]
0x18001da91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da96  mov     rdx, [rbp+var_20]
0x18001da9a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001da9e  mov     eax, r13d
0x18001daa1  lock xadd [rdx+10h], eax
0x18001daa6  add     eax, r13d
0x18001daa9  test    eax, eax
0x18001daab  jg      short loc_18001DAC2
0x18001daad  mov     rcx, [rdx]
0x18001dab0  mov     rax, [rcx]
0x18001dab3  mov     rax, [rax+8]
0x18001dab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dabc  jmp     short loc_18001DAC2
0x18001dabe  mov     rdi, [rbp+arg_18]
0x18001dac2  lea     rdx, [rdi-18h]
0x18001dac6  mov     eax, r13d
0x18001dac9  lock xadd [rdx+10h], eax
0x18001dace  add     eax, r13d
0x18001dad1  test    eax, eax
0x18001dad3  jg      short loc_18001DAE5
0x18001dad5  mov     rcx, [rdx]
0x18001dad8  mov     rax, [rcx]
0x18001dadb  mov     rax, [rax+8]
0x18001dadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae4  nop
0x18001dae5  lea     rdx, [rsi-18h]
0x18001dae9  mov     eax, r13d
0x18001daec  lock xadd [rdx+10h], eax
0x18001daf1  add     eax, r13d
0x18001daf4  test    eax, eax
0x18001daf6  jg      short loc_18001DB08
0x18001daf8  mov     rcx, [rdx]
0x18001dafb  mov     rax, [rcx]
0x18001dafe  mov     rax, [rax+8]
0x18001db02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db07  nop
0x18001db08  test    rbx, rbx
0x18001db0b  jz      short loc_18001DB1D
0x18001db0d  mov     rax, [rbx]
0x18001db10  mov     rcx, rbx
0x18001db13  mov     rax, [rax+10h]
0x18001db17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db1c  nop
0x18001db1d  test    r14d, r14d
0x18001db20  jns     loc_18001D8E6
0x18001db26  jmp     short loc_18001DB52
0x18001db28  test    rcx, rcx
0x18001db2b  jz      short loc_18001DB3A
0x18001db2d  mov     rax, [rcx]
0x18001db30  mov     rax, [rax+10h]
0x18001db34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db39  nop
0x18001db3a  xor     r14d, r14d
0x18001db3d  test    rbx, rbx
0x18001db40  jz      short loc_18001DB52
0x18001db42  mov     rax, [rbx]
0x18001db45  mov     rcx, rbx
0x18001db48  mov     rax, [rax+10h]
0x18001db4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db51  nop
0x18001db52  mov     rcx, [rbp+var_38]
0x18001db56  test    rcx, rcx
0x18001db59  jz      short loc_18001DB68
0x18001db5b  mov     rax, [rcx]
0x18001db5e  mov     rax, [rax+10h]
0x18001db62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db67  nop
0x18001db68  jmp     short loc_18001DB7B
0x18001db6a  cmp     r14d, 1
0x18001db6e  jnz     short loc_18001DB7B
0x18001db70  xor     r14d, r14d
0x18001db73  jmp     short loc_18001DB7B
0x18001db75  mov     r14d, 8007000Eh
0x18001db7b  mov     rcx, [rbp+var_30]
0x18001db7f  test    rcx, rcx
0x18001db82  jz      short loc_18001DB91
0x18001db84  mov     rax, [rcx]
0x18001db87  mov     rax, [rax+10h]
0x18001db8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db90  nop
0x18001db91  mov     eax, r14d
0x18001db94  lea     r11, [rsp+70h+var_s0]
0x18001db99  mov     rbx, [r11+30h]
0x18001db9d  mov     rsi, [r11+38h]
0x18001dba1  mov     rsp, r11
0x18001dba4  pop     r15
0x18001dba6  pop     r14
0x18001dba8  pop     r13
0x18001dbaa  pop     rdi
0x18001dbab  pop     rbp
0x18001dbac  retn
```
