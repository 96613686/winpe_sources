# CRestoreSession::Initialize(IFhConfigMgrPriv *,IFhCatalog *)

- ea: `0x1800244e0`
- end: `0x180024851`
- name: `?Initialize@CRestoreSession@@UEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z`
- size: `881`
- prototype: `__int64 __fastcall(OLECHAR *this, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002c24`
- `0x1800031b0`
- `0x1800042e8`
- `0x180004308`
- `0x1800062d0`
- `0x180006914`
- `0x180007818`
- `0x1800091a4`
- `0x18000935c`
- `0x180009674`
- `0x1800097b0`
- `0x18000ac60`
- `0x18000bbb8`
- `0x18001284c`
- `0x180024410`
- `0x1800244e0`
- `0x180024b10`
- `0x180034010`

## import_xrefs

- `msvcrt!free` at `0x180024602`
- `msvcrt!free` at `0x180024602`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247a8`

## pseudocode

```c
__int64 __fastcall CRestoreSession::Initialize(OLECHAR *this, struct IUnknown *a2, struct IUnknown *a3)
{
  OLECHAR *v3; // r13
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 result; // rax
  int i; // r15d
  _QWORD *v9; // rsi
  unsigned int v10; // r14d
  _QWORD *v11; // r12
  int j; // eax
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  char v19; // bl
  unsigned __int64 v20; // rbx
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // [rsp+30h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-70h] BYREF
  int v25; // [rsp+40h] [rbp-68h]
  const unsigned __int16 *v26; // [rsp+48h] [rbp-60h] BYREF
  int v27; // [rsp+50h] [rbp-58h]
  _QWORD *v28; // [rsp+58h] [rbp-50h]
  int v29; // [rsp+60h] [rbp-48h] BYREF
  __int64 v30; // [rsp+68h] [rbp-40h] BYREF
  _QWORD *v31; // [rsp+70h] [rbp-38h]
  _QWORD *v32; // [rsp+78h] [rbp-30h]
  unsigned int v34; // [rsp+C8h] [rbp+20h]

  v3 = this;
  v4 = CSessionBaseRO::Initialize(this + 32, a2, a3);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 11;
    goto LABEL_5;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v3 + 8) + 168LL))(
         *((_QWORD *)v3 + 8),
         *((_QWORD *)v3 + 9));
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 12;
LABEL_5:
    WPP_SF_d(v5[2], v6, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, (unsigned int)v4);
    goto LABEL_6;
  }
  i = 0;
LABEL_12:
  v25 = i;
  if ( i >= 2 )
    goto LABEL_6;
  v23 = 0;
  if ( !i )
  {
    v9 = v3 + 124;
    goto LABEL_18;
  }
  if ( i != 1 )
  {
    v9 = 0;
LABEL_18:
    v10 = 1;
    goto LABEL_19;
  }
  v10 = 3;
  v9 = v3 + 140;
LABEL_19:
  v34 = v10;
  v28 = v9;
  v31 = v9;
  v11 = v9 + 1;
  if ( *v9 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      *v9,
      *v11);
    free((void *)*v9);
    *v9 = 0;
  }
  v32 = v9 + 1;
  *v11 = 0;
  v9[2] = 0;
  for ( j = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)v3 + 8) + 184LL))(
              *((_QWORD *)v3 + 8),
              v10,
              &v23); ; j = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23) )
  {
    if ( j < 0 )
    {
      v4 = 0;
      if ( j != -2147023728 )
        v4 = j;
      if ( v4 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 15;
          goto LABEL_27;
        }
        goto LABEL_28;
      }
      v4 = CRestoreSession::SortStringList(v13, v9);
      if ( v4 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 16;
LABEL_27:
          WPP_SF_dd(v14[2], v15, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v10, v4);
        }
LABEL_28:
        ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v23);
        goto LABEL_6;
      }
      ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v23);
      ++i;
      goto LABEL_12;
    }
    bstrString = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 32LL))(v23, &bstrString);
    if ( v4 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 13;
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
    v16 = ocslen(bstrString);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v17, v16);
      v18 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
              &v26,
              &v30);
      v19 = ATL::operator!=(v18);
      ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
      if ( v19 )
        ATL::CSimpleStringT<unsigned short,0>::Append(&v26, L"\\", 1);
      v20 = v9[1];
      if ( v20 >= v9[2]
        && !ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GrowBuffer(
              (__int64)v9,
              v20 + 1) )
      {
        ATL::AtlThrowImpl(-2147024882);
      }
      v21 = *v31 + 8 * v20;
      v22 = v26;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        v21,
        v26);
      *v11 = v9[1] + 1LL;
      ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v29) )
      {
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        v27 = v29;
        if ( v29 >= 0 )
        {
          v3 = this;
          i = v25;
          v10 = v34;
          v9 = v28;
          v11 = v32;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002477F);
          goto LABEL_36;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v34, v29);
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002476C);
        ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v23);
        v4 = v27;
LABEL_6:
        result = (unsigned int)v4;
      }
    }
LABEL_36:
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
  }
}

```

## disassembly

```asm
0x1800244e0  mov     [rsp+arg_8], rbx
0x1800244e5  mov     [rsp+arg_0], rcx
0x1800244ea  push    rsi
0x1800244eb  push    r12
0x1800244ed  push    r13
0x1800244ef  push    r14
0x1800244f1  push    r15
0x1800244f3  sub     rsp, 80h
0x1800244fa  mov     r13, rcx
0x1800244fd  add     rcx, 40h ; '@'; this
0x180024501  call    ?Initialize@CSessionBaseRO@@IEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z; CSessionBaseRO::Initialize(IFhConfigMgrPriv *,IFhCatalog *)
0x180024506  mov     ebx, eax
0x180024508  test    eax, eax
0x18002450a  jns     short loc_180024558
0x18002450c  lea     rax, WPP_GLOBAL_Control
0x180024513  mov     rcx, cs:WPP_GLOBAL_Control
0x18002451a  cmp     rcx, rax
0x18002451d  jz      short loc_18002453D
0x18002451f  test    byte ptr [rcx+1Ch], 1
0x180024523  jz      short loc_18002453D
0x180024525  mov     edx, 0Bh
0x18002452a  mov     r9d, ebx
0x18002452d  lea     r8, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x180024534  mov     rcx, [rcx+10h]
0x180024538  call    WPP_SF_d
0x18002453d  mov     eax, ebx
0x18002453f  mov     rbx, [rsp+0A8h+arg_8]
0x180024547  add     rsp, 80h
0x18002454e  pop     r15
0x180024550  pop     r14
0x180024552  pop     r13
0x180024554  pop     r12
0x180024556  pop     rsi
0x180024557  retn
0x180024558  mov     rcx, [r13+40h]
0x18002455c  mov     rax, [rcx]
0x18002455f  mov     rdx, [r13+48h]
0x180024563  mov     rax, [rax+0A8h]
0x18002456a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002456f  mov     ebx, eax
0x180024571  test    eax, eax
0x180024573  jns     short loc_180024595
0x180024575  lea     rax, WPP_GLOBAL_Control
0x18002457c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024583  cmp     rcx, rax
0x180024586  jz      short loc_18002453D
0x180024588  test    byte ptr [rcx+1Ch], 1
0x18002458c  jz      short loc_18002453D
0x18002458e  mov     edx, 0Ch
0x180024593  jmp     short loc_18002452A
0x180024595  xor     r15d, r15d
0x180024598  mov     [rsp+0A8h+var_68], r15d
0x18002459d  cmp     r15d, 2
0x1800245a1  jge     short loc_18002453D
0x1800245a3  mov     [rsp+0A8h+var_78], 0
0x1800245ac  test    r15d, r15d
0x1800245af  jz      short loc_1800245CA
0x1800245b1  cmp     r15d, 1
0x1800245b5  jz      short loc_1800245BB
0x1800245b7  xor     esi, esi
0x1800245b9  jmp     short loc_1800245D1
0x1800245bb  mov     r14d, 3
0x1800245c1  lea     rsi, [r13+118h]
0x1800245c8  jmp     short loc_1800245D7
0x1800245ca  lea     rsi, [r13+0F8h]
0x1800245d1  mov     r14d, 1
0x1800245d7  mov     [rsp+0A8h+arg_18], r14d
0x1800245df  mov     [rsp+0A8h+var_50], rsi
0x1800245e4  mov     [rsp+0A8h+var_38], rsi
0x1800245e9  lea     r12, [rsi+8]
0x1800245ed  cmp     qword ptr [rsi], 0
0x1800245f1  jz      short loc_18002460F
0x1800245f3  mov     rdx, [r12]
0x1800245f7  mov     rcx, [rsi]
0x1800245fa  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x1800245ff  mov     rcx, [rsi]; Block
0x180024602  call    cs:__imp_free
0x180024608  mov     qword ptr [rsi], 0
0x18002460f  mov     [rsp+0A8h+var_30], r12
0x180024614  mov     qword ptr [r12], 0
0x18002461c  mov     qword ptr [rsi+10h], 0
0x180024624  mov     rcx, [r13+40h]
0x180024628  mov     rax, [rcx]
0x18002462b  lea     r8, [rsp+0A8h+var_78]
0x180024630  mov     edx, r14d
0x180024633  mov     rax, [rax+0B8h]
0x18002463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002463f  test    eax, eax
0x180024641  js      loc_1800247CD
0x180024647  mov     [rsp+0A8h+bstrString], 0
0x180024650  mov     rcx, [rsp+0A8h+var_78]
0x180024655  mov     rax, [rcx]
0x180024658  lea     rdx, [rsp+0A8h+bstrString]
0x18002465d  mov     rax, [rax+20h]
0x180024661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024666  mov     ebx, eax
0x180024668  test    eax, eax
0x18002466a  jns     short loc_1800246B1
0x18002466c  lea     rax, WPP_GLOBAL_Control
0x180024673  mov     rcx, cs:WPP_GLOBAL_Control
0x18002467a  cmp     rcx, rax
0x18002467d  jz      short loc_1800246A2
0x18002467f  test    byte ptr [rcx+1Ch], 1
0x180024683  jz      short loc_1800246A2
0x180024685  mov     edx, 0Dh
0x18002468a  mov     [rsp+0A8h+var_88], ebx
0x18002468e  mov     r9d, r14d
0x180024691  lea     r8, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x180024698  mov     rcx, [rcx+10h]
0x18002469c  call    WPP_SF_dd
0x1800246a1  nop
0x1800246a2  lea     rcx, [rsp+0A8h+var_78]
0x1800246a7  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x1800246ac  jmp     loc_18002453D
0x1800246b1  lea     rcx, [rsp+0A8h+var_60]
0x1800246b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800246bb  nop
0x1800246bc  mov     rcx, [rsp+0A8h+bstrString]; unsigned __int16 *
0x1800246c1  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x1800246c6  mov     r8d, eax
0x1800246c9  mov     rdx, rcx
0x1800246cc  lea     rcx, [rsp+0A8h+var_60]
0x1800246d1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800246d6  lea     rdx, [rsp+0A8h+var_40]
0x1800246db  lea     rcx, [rsp+0A8h+var_60]
0x1800246e0  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x1800246e5  mov     rcx, rax
0x1800246e8  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800246ed  mov     bl, al
0x1800246ef  mov     rcx, [rsp+0A8h+var_40]
0x1800246f4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800246f8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800246fd  test    bl, bl
0x1800246ff  jz      short loc_180024718
0x180024701  mov     r8d, 1
0x180024707  lea     rdx, asc_180037180; "\\"
0x18002470e  lea     rcx, [rsp+0A8h+var_60]
0x180024713  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180024718  mov     rbx, [rsi+8]
0x18002471c  cmp     rbx, [rsi+10h]
0x180024720  jb      short loc_18002473C
0x180024722  lea     rdx, [rbx+1]
0x180024726  mov     rcx, rsi
0x180024729  call    ?GrowBuffer@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GrowBuffer(unsigned __int64)
0x18002472e  test    al, al
0x180024730  jnz     short loc_18002473C
0x180024732  mov     ecx, 8007000Eh; int
0x180024737  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002473c  mov     rax, [rsp+0A8h+var_38]
0x180024741  mov     rax, [rax]
0x180024744  lea     rcx, [rax+rbx*8]
0x180024748  mov     rbx, [rsp+0A8h+var_60]
0x18002474d  mov     rdx, rbx
0x180024750  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180024755  mov     rax, [rsi+8]
0x180024759  inc     rax
0x18002475c  mov     [r12], rax
0x180024760  lea     rcx, [rbx-18h]; this
0x180024764  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024769  nop
0x18002476a  jmp     short loc_18002479E
0x18002476c  lea     rcx, [rsp+0A8h+var_78]
0x180024771  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x180024776  mov     ebx, [rsp+0A8h+var_58]
0x18002477a  jmp     loc_18002453D
0x18002477f  mov     r13, [rsp+0A8h+arg_0]
0x180024787  mov     r15d, [rsp+0A8h+var_68]
0x18002478c  mov     r14d, [rsp+0A8h+arg_18]
0x180024794  mov     rsi, [rsp+0A8h+var_50]
0x180024799  mov     r12, [rsp+0A8h+var_30]
0x18002479e  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x1800247a3  test    rcx, rcx
0x1800247a6  jz      short loc_1800247B7
0x1800247a8  call    cs:__imp_SysFreeString
0x1800247ae  mov     [rsp+0A8h+bstrString], 0
0x1800247b7  mov     rcx, [rsp+0A8h+var_78]
0x1800247bc  mov     rax, [rcx]
0x1800247bf  mov     rax, [rax+18h]
0x1800247c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c8  jmp     loc_18002463F
0x1800247cd  xor     ebx, ebx
0x1800247cf  cmp     eax, 80070490h
0x1800247d4  cmovnz  ebx, eax
0x1800247d7  test    ebx, ebx
0x1800247d9  jns     short loc_180024806
0x1800247db  lea     rax, WPP_GLOBAL_Control
0x1800247e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247e9  cmp     rcx, rax
0x1800247ec  jz      loc_1800246A2
0x1800247f2  test    byte ptr [rcx+1Ch], 1
0x1800247f6  jz      loc_1800246A2
0x1800247fc  mov     edx, 0Fh
0x180024801  jmp     loc_18002468A
0x180024806  mov     rdx, rsi
0x180024809  call    ?SortStringList@CRestoreSession@@AEAAJAEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CRestoreSession::SortStringList(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18002480e  mov     ebx, eax
0x180024810  test    eax, eax
0x180024812  jns     short loc_18002483F
0x180024814  lea     rax, WPP_GLOBAL_Control
0x18002481b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024822  cmp     rcx, rax
0x180024825  jz      loc_1800246A2
0x18002482b  test    byte ptr [rcx+1Ch], 1
0x18002482f  jz      loc_1800246A2
0x180024835  mov     edx, 10h
0x18002483a  jmp     loc_18002468A
0x18002483f  lea     rcx, [rsp+0A8h+var_78]
0x180024844  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x180024849  inc     r15d
0x18002484c  jmp     loc_180024598
```
