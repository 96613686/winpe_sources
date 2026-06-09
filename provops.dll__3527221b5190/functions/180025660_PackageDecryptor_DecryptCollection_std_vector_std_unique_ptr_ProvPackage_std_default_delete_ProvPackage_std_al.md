# PackageDecryptor::DecryptCollection(std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>> *,ushort const * const *,unsigned __int64,std::vector<bool,std::allocator<bool>> *)

- ea: `0x180025660`
- end: `0x180025af6`
- name: `?DecryptCollection@PackageDecryptor@@QEAAXPEAV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@PEBQEBG_KPEAV?$vector@_NV?$allocator@_N@std@@@3@@Z`
- size: `1174`
- prototype: `__int64 __fastcall(__int64, __int64 **, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f8d0`

## callees

- `0x180001678`
- `0x1800023dc`
- `0x180002f44`
- `0x18001b388`
- `0x18001f548`
- `0x180020fe0`
- `0x1800221dc`
- `0x180024440`
- `0x180024eac`
- `0x180024f80`
- `0x180025660`
- `0x180026068`
- `0x18002e030`
- `0x18002f9a0`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002595a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002597e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002599c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002595a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002597e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002599c`
- `provpackageapidll!CreatePackageSecurity` at `0x1800256cc`
- `provpackageapidll!CreatePackageSecurity` at `0x1800256cc`

## pseudocode

```c
__int64 __fastcall PackageDecryptor::DecryptCollection(__int64 a1, __int64 **a2, __int64 a3, __int64 a4, __int64 *a5)
{
  int v7; // eax
  __int64 v8; // rbx
  __int64 *v9; // rdi
  __int64 v10; // rcx
  __int64 *v11; // r15
  __int64 *v12; // rbx
  __int64 *v13; // rdi
  __int64 *v14; // rsi
  __int64 v15; // r12
  __int64 v16; // rcx
  __int64 i; // rbx
  __int64 v18; // rdi
  void *v19; // rsi
  __int64 v20; // rsi
  int v21; // r15d
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  void **v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  void **v34; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  char v38; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  _QWORD *v41; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v42[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v43; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v46; // [rsp+D8h] [rbp-28h]
  void *v47[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v49; // [rsp+F8h] [rbp-8h]
  void *v50[4]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  IPasswordEnumerator::CreateInstance(&v33, a3, a4);
  v32 = 0;
  v36 = &v32;
  v37 = 0;
  v38 = 1;
  v7 = CreatePackageSecurity(&v37);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagedecryptor.cpp",
      (const char *)(unsigned int)v7,
      v31);
  if ( v38 )
  {
    v8 = v37;
    v9 = v36;
    v10 = *v36;
    if ( v37 != *v36 )
    {
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
      *v9 = v8;
    }
  }
  v39 = 0;
  v40 = 0;
  v11 = a2[1];
  v12 = *a2;
  v43 = &v32;
  v44 = &v33;
  v45 = a1;
  v46 = (unsigned __int64)&v39;
  if ( v12 != v11 )
  {
    while ( 1 )
    {
      v13 = v12 + 1;
      if ( (unsigned __int8)lambda_9958db7f662a3826030c55bd79ac5a74_::operator()(&v43, v12) )
        break;
      ++v12;
      if ( v13 == v11 )
        goto LABEL_20;
    }
    v43 = &v32;
    v44 = &v33;
    v45 = a1;
    v46 = (unsigned __int64)&v39;
    while ( v13 != v11 )
    {
      if ( !(unsigned __int8)lambda_9958db7f662a3826030c55bd79ac5a74_::operator()(&v43, v13) )
      {
        v14 = v12++;
        if ( v14 != v13 )
        {
          v15 = *v13;
          *v13 = 0;
          v16 = *v14;
          if ( v15 != *v14 )
          {
            if ( v16 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 64LL))(v16, 1);
            *v14 = v15;
          }
        }
      }
      ++v13;
    }
  }
LABEL_20:
  std::vector<std::unique_ptr<ProvPackage>>::erase(a2, &v34, v12, a2[1]);
  std::vector<bool>::resize(a5, a2[1] - *a2);
  v18 = *((_QWORD *)&v39 + 1);
  for ( i = v39; i != v18; i += 72 )
  {
    v19 = operator new(0xA8u);
    v42[2] = v19;
    if ( v19 )
    {
      v34 = v47;
      v49 = 7;
      v48 = 0;
      LOWORD(v47[0]) = 0;
      std::wstring::assign(v47);
      v46 = 7;
      v45 = 0;
      LOWORD(v43) = 0;
      std::wstring::assign(&v43);
      v20 = ProvPackage::ProvPackage(v19, &v43, v47);
    }
    else
    {
      v20 = 0;
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v20 + 72LL))(v20) )
    {
      v21 = g_hProvTraceProvider;
      if ( *(_DWORD *)g_hProvTraceProvider > 4u )
      {
        v22 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v20 + 24LL))(v20, v50);
        if ( v22[3] >= 8u )
          v22 = (_QWORD *)*v22;
        v41 = v22;
        v23 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void **))v20)(v20, v47);
        if ( v23[3] >= 8u )
          v23 = (_QWORD *)*v23;
        v35 = v23;
        v24 = (void **)(*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v20 + 16LL))(v20, &v43);
        if ( (unsigned __int64)v24[3] >= 8 )
          v24 = (void **)*v24;
        v34 = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v21,
          (unsigned int)&word_180041156,
          v25,
          v26,
          (__int64)&v34,
          (__int64)&v35,
          (__int64)&v41);
        if ( v46 >= 8 )
          operator delete(v43);
        v46 = 7;
        v45 = 0;
        LOWORD(v43) = 0;
        if ( v49 >= 8 )
          operator delete(v47[0]);
        v49 = 7;
        v48 = 0;
        LOWORD(v47[0]) = 0;
        if ( v50[3] >= (void *)8 )
          operator delete(v50[0]);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 80LL))(v20);
    }
    else if ( *(_DWORD *)g_hProvTraceProvider > 2u )
    {
      tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, qword_180041128, 0, 0);
    }
    v27 = *a5;
    v28 = a5[3];
    if ( v28 )
    {
      v29 = a5[3] & 0x1F;
      if ( v28 >= 0 )
        v27 += 4 * ((unsigned __int64)v28 >> 5);
      else
        v27 -= 4 * ((unsigned __int64)~v28 >> 5) + 4;
    }
    else
    {
      v29 = 0;
    }
    v42[0] = v27;
    v42[1] = v29;
    std::vector<bool>::_Insert_n((_DWORD)a5, (unsigned int)&v36, (unsigned int)v42, 1, i);
    if ( a2[1] == a2[2] )
      std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a2);
    *a2[1]++ = v20;
  }
  result = std::vector<std::tuple<std::wstring,std::wstring,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>::~vector<std::tuple<std::wstring,std::wstring,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>(&v39);
  if ( v32 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 32LL))(v32);
  if ( v33 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 40LL))(v33, 1);
  return result;
}

```

## disassembly

```asm
0x180025660  mov     [rsp-8+arg_0], rbx
0x180025665  push    rbp
0x180025666  push    rsi
0x180025667  push    rdi
0x180025668  push    r12
0x18002566a  push    r13
0x18002566c  push    r14
0x18002566e  push    r15
0x180025670  lea     rbp, [rsp-30h]
0x180025675  sub     rsp, 130h
0x18002567c  mov     rax, cs:__security_cookie
0x180025683  xor     rax, rsp
0x180025686  mov     [rbp+60h+var_40], rax
0x18002568a  mov     rax, r8
0x18002568d  mov     r14, rdx
0x180025690  mov     rsi, rcx
0x180025693  mov     r13, [rbp+60h+arg_20]
0x18002569a  xor     r12d, r12d
0x18002569d  mov     r8, r9
0x1800256a0  mov     rdx, rax
0x1800256a3  lea     rcx, [rsp+160h+var_118]
0x1800256a8  call    ?CreateInstance@IPasswordEnumerator@@SA?AV?$unique_ptr@VIPasswordEnumerator@@U?$default_delete@VIPasswordEnumerator@@@std@@@std@@PEBQEBG_K@Z; IPasswordEnumerator::CreateInstance(ushort const * const *,unsigned __int64)
0x1800256ad  nop
0x1800256ae  mov     [rsp+160h+var_120], r12
0x1800256b3  lea     rax, [rsp+160h+var_120]
0x1800256b8  mov     [rsp+160h+var_100], rax
0x1800256bd  mov     [rsp+160h+var_F8], r12
0x1800256c2  mov     [rsp+160h+var_F0], 1
0x1800256c7  lea     rcx, [rsp+160h+var_F8]
0x1800256cc  call    cs:__imp_CreatePackageSecurity
0x1800256d2  mov     rcx, [rbp+68h]; this
0x1800256d6  test    eax, eax
0x1800256d8  js      loc_180025AE1
0x1800256de  cmp     [rsp+160h+var_F0], r12b
0x1800256e3  jz      short loc_18002570B
0x1800256e5  mov     rbx, [rsp+160h+var_F8]
0x1800256ea  mov     rdi, [rsp+160h+var_100]
0x1800256ef  mov     rcx, [rdi]
0x1800256f2  cmp     rbx, rcx
0x1800256f5  jz      short loc_18002570B
0x1800256f7  test    rcx, rcx
0x1800256fa  jz      short loc_180025708
0x1800256fc  mov     rax, [rcx]
0x1800256ff  mov     rax, [rax+20h]
0x180025703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025708  mov     [rdi], rbx
0x18002570b  xorps   xmm0, xmm0
0x18002570e  movdqu  [rsp+160h+var_E8], xmm0
0x180025714  mov     [rbp+60h+var_D8], r12
0x180025718  mov     r15, [r14+8]
0x18002571c  mov     rbx, [r14]
0x18002571f  lea     rax, [rsp+160h+var_120]
0x180025724  mov     [rbp+60h+var_A0], rax
0x180025728  lea     rax, [rsp+160h+var_118]
0x18002572d  mov     [rbp+60h+var_98], rax
0x180025731  mov     [rbp+60h+var_90], rsi
0x180025735  lea     rax, [rsp+160h+var_E8]
0x18002573a  mov     [rbp+60h+var_88], rax
0x18002573e  cmp     rbx, r15
0x180025741  jz      loc_1800257D9
0x180025747  lea     rdi, [rbx+8]
0x18002574b  mov     rdx, rbx
0x18002574e  lea     rcx, [rbp+60h+var_A0]
0x180025752  call    _lambda_9958db7f662a3826030c55bd79ac5a74___operator__
0x180025757  test    al, al
0x180025759  jnz     short loc_180025765
0x18002575b  mov     rbx, rdi
0x18002575e  cmp     rdi, r15
0x180025761  jnz     short loc_180025747
0x180025763  jmp     short loc_1800257D9
0x180025765  lea     rax, [rsp+160h+var_120]
0x18002576a  mov     [rbp+60h+var_A0], rax
0x18002576e  lea     rax, [rsp+160h+var_118]
0x180025773  mov     [rbp+60h+var_98], rax
0x180025777  mov     [rbp+60h+var_90], rsi
0x18002577b  lea     rax, [rsp+160h+var_E8]
0x180025780  mov     [rbp+60h+var_88], rax
0x180025784  jmp     short loc_1800257D4
0x180025786  mov     rdx, rdi
0x180025789  lea     rcx, [rbp+60h+var_A0]
0x18002578d  call    _lambda_9958db7f662a3826030c55bd79ac5a74___operator__
0x180025792  test    al, al
0x180025794  jnz     short loc_1800257D0
0x180025796  mov     rsi, rbx
0x180025799  add     rbx, 8
0x18002579d  cmp     rsi, rdi
0x1800257a0  jz      short loc_1800257D0
0x1800257a2  mov     r12, [rdi]
0x1800257a5  mov     qword ptr [rdi], 0
0x1800257ac  mov     rcx, [rsi]
0x1800257af  cmp     r12, rcx
0x1800257b2  jz      short loc_1800257CD
0x1800257b4  test    rcx, rcx
0x1800257b7  jz      short loc_1800257CA
0x1800257b9  mov     rax, [rcx]
0x1800257bc  mov     edx, 1
0x1800257c1  mov     rax, [rax+40h]
0x1800257c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257ca  mov     [rsi], r12
0x1800257cd  xor     r12d, r12d
0x1800257d0  add     rdi, 8
0x1800257d4  cmp     rdi, r15
0x1800257d7  jnz     short loc_180025786
0x1800257d9  mov     r9, [r14+8]
0x1800257dd  mov     r8, rbx
0x1800257e0  lea     rdx, [rsp+160h+var_110]
0x1800257e5  mov     rcx, r14
0x1800257e8  call    ?erase@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackage>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<ProvPackage>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<ProvPackage>>>>)
0x1800257ed  mov     rdx, [r14+8]
0x1800257f1  sub     rdx, [r14]
0x1800257f4  sar     rdx, 3
0x1800257f8  mov     rcx, r13
0x1800257fb  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x180025800  mov     rbx, qword ptr [rsp+160h+var_E8]
0x180025805  mov     rdi, qword ptr [rbp+60h+var_E8+8]
0x180025809  mov     r15d, 7
0x18002580f  cmp     rbx, rdi
0x180025812  jz      loc_180025A7D
0x180025818  mov     ecx, 0A8h; Size
0x18002581d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025822  mov     rsi, rax
0x180025825  mov     [rbp+60h+var_B0], rax
0x180025829  test    rax, rax
0x18002582c  jz      short loc_180025890
0x18002582e  lea     rax, [rbp+60h+var_80]
0x180025832  mov     [rsp+160h+var_110], rax
0x180025837  mov     [rbp+60h+var_68], r15
0x18002583b  mov     [rbp+60h+var_70], r12
0x18002583f  mov     word ptr [rbp+60h+var_80], r12w
0x180025844  lea     rdx, [rbx+8]
0x180025848  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002584c  xor     r8d, r8d
0x18002584f  lea     rcx, [rbp+60h+var_80]; void *
0x180025853  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180025858  nop
0x180025859  mov     [rbp+60h+var_88], r15
0x18002585d  mov     [rbp+60h+var_90], r12
0x180025861  mov     word ptr [rbp+60h+var_A0], r12w
0x180025866  lea     rdx, [rbx+28h]
0x18002586a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002586e  xor     r8d, r8d
0x180025871  lea     rcx, [rbp+60h+var_A0]; void *
0x180025875  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002587a  nop
0x18002587b  lea     r8, [rbp+60h+var_80]
0x18002587f  lea     rdx, [rbp+60h+var_A0]
0x180025883  mov     rcx, rsi
0x180025886  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x18002588b  mov     rsi, rax
0x18002588e  jmp     short loc_180025893
0x180025890  mov     rsi, r12
0x180025893  mov     rax, [rsi]
0x180025896  mov     rcx, rsi
0x180025899  mov     rax, [rax+48h]
0x18002589d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a2  test    al, al
0x1800258a4  jz      loc_1800259BB
0x1800258aa  mov     r15, cs:g_hProvTraceProvider
0x1800258b1  mov     eax, [r15]
0x1800258b4  cmp     eax, 4
0x1800258b7  jbe     loc_1800259A4
0x1800258bd  mov     rax, [rsi]
0x1800258c0  lea     rdx, [rbp+60h+var_60]
0x1800258c4  mov     rcx, rsi
0x1800258c7  mov     rax, [rax+18h]
0x1800258cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258d0  nop
0x1800258d1  cmp     qword ptr [rax+18h], 8
0x1800258d6  jb      short loc_1800258DB
0x1800258d8  mov     rax, [rax]
0x1800258db  mov     [rbp+60h+var_D0], rax
0x1800258df  mov     rax, [rsi]
0x1800258e2  lea     rdx, [rbp+60h+var_80]
0x1800258e6  mov     rcx, rsi
0x1800258e9  mov     rax, [rax]
0x1800258ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258f1  nop
0x1800258f2  cmp     qword ptr [rax+18h], 8
0x1800258f7  jb      short loc_1800258FC
0x1800258f9  mov     rax, [rax]
0x1800258fc  mov     [rsp+160h+var_108], rax
0x180025901  mov     rax, [rsi]
0x180025904  lea     rdx, [rbp+60h+var_A0]
0x180025908  mov     rcx, rsi
0x18002590b  mov     rax, [rax+10h]
0x18002590f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025914  cmp     qword ptr [rax+18h], 8
0x180025919  jb      short loc_18002591E
0x18002591b  mov     rax, [rax]
0x18002591e  mov     [rsp+160h+var_110], rax
0x180025923  lea     rax, [rbp+60h+var_D0]
0x180025927  mov     [rsp+160h+var_130], rax
0x18002592c  lea     rax, [rsp+160h+var_108]
0x180025931  mov     [rsp+160h+var_138], rax
0x180025936  lea     rax, [rsp+160h+var_110]
0x18002593b  mov     [rsp+160h+var_140], rax
0x180025940  lea     rdx, word_180041156
0x180025947  mov     rcx, r15
0x18002594a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002594f  cmp     [rbp+60h+var_88], 8
0x180025954  jb      short loc_180025960
0x180025956  mov     rcx, [rbp+60h+var_A0]
0x18002595a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025960  mov     r15d, 7
0x180025966  mov     [rbp+60h+var_88], r15
0x18002596a  mov     [rbp+60h+var_90], r12
0x18002596e  mov     word ptr [rbp+60h+var_A0], r12w
0x180025973  cmp     [rbp+60h+var_68], 8
0x180025978  jb      short loc_180025984
0x18002597a  mov     rcx, [rbp+60h+var_80]
0x18002597e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025984  mov     [rbp+60h+var_68], r15
0x180025988  mov     [rbp+60h+var_70], r12
0x18002598c  mov     word ptr [rbp+60h+var_80], r12w
0x180025991  cmp     [rbp+60h+var_48], 8
0x180025996  jb      short loc_1800259AA
0x180025998  mov     rcx, [rbp+60h+var_60]
0x18002599c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800259a2  jmp     short loc_1800259AA
0x1800259a4  mov     r15d, 7
0x1800259aa  mov     rax, [rsi]
0x1800259ad  mov     rcx, rsi
0x1800259b0  mov     rax, [rax+50h]
0x1800259b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259b9  jmp     short loc_1800259EC
0x1800259bb  mov     rcx, cs:g_hProvTraceProvider
0x1800259c2  mov     eax, [rcx]
0x1800259c4  cmp     eax, 2
0x1800259c7  jbe     short loc_1800259EC
0x1800259c9  lea     rax, [rbp+60h+var_60]
0x1800259cd  mov     [rsp+160h+var_138], rax
0x1800259d2  mov     dword ptr [rsp+160h+var_140], 2
0x1800259da  xor     r9d, r9d
0x1800259dd  xor     r8d, r8d
0x1800259e0  lea     rdx, qword_180041128
0x1800259e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800259ec  mov     rdx, [r13+0]
0x1800259f0  mov     rcx, [r13+18h]
0x1800259f4  test    rcx, rcx
0x1800259f7  jz      short loc_180025A2F
0x1800259f9  jns     short loc_180025A1E
0x1800259fb  mov     rax, rcx
0x1800259fe  neg     rax
0x180025a01  jz      short loc_180025A1E
0x180025a03  mov     r8, rcx
0x180025a06  and     r8d, 1Fh
0x180025a0a  not     rcx
0x180025a0d  shr     rcx, 5
0x180025a11  lea     rax, ds:4[rcx*4]
0x180025a19  sub     rdx, rax
0x180025a1c  jmp     short loc_180025A32
0x180025a1e  mov     r8, rcx
0x180025a21  and     r8d, 1Fh
0x180025a25  shr     rcx, 5
0x180025a29  lea     rdx, [rdx+rcx*4]
0x180025a2d  jmp     short loc_180025A32
0x180025a2f  mov     r8, r12
0x180025a32  mov     [rbp+60h+var_C0], rdx
0x180025a36  mov     [rbp+60h+var_B8], r8
0x180025a3a  mov     [rsp+160h+var_140], rbx
0x180025a3f  mov     r9d, 1
0x180025a45  lea     r8, [rbp+60h+var_C0]
0x180025a49  lea     rdx, [rsp+160h+var_100]
0x180025a4e  mov     rcx, r13
0x180025a51  call    ?_Insert_n@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@V?$_Vb_const_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@_KAEB_N@Z; std::vector<bool>::_Insert_n(std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<uint>>>,unsigned __int64,bool const &)
0x180025a56  mov     rax, [r14+10h]
0x180025a5a  cmp     [r14+8], rax
0x180025a5e  jnz     short loc_180025A68
0x180025a60  mov     rcx, r14
0x180025a63  call    ?_Reserve@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ProvPackage>>::_Reserve(unsigned __int64)
0x180025a68  mov     rax, [r14+8]
0x180025a6c  mov     [rax], rsi
0x180025a6f  add     qword ptr [r14+8], 8
0x180025a74  add     rbx, 48h ; 'H'
0x180025a78  jmp     loc_18002580F
0x180025a7d  lea     rcx, [rsp+160h+var_E8]
0x180025a82  call    ??1?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@_NU_Nil@2@U32@U32@U32@U32@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@_NU_Nil@2@U32@U32@U32@U32@@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<std::wstring,std::wstring,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>::~vector<std::tuple<std::wstring,std::wstring,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>(void)
0x180025a87  nop
0x180025a88  mov     rcx, [rsp+160h+var_120]
0x180025a8d  test    rcx, rcx
0x180025a90  jz      short loc_180025A9F
0x180025a92  mov     rax, [rcx]
0x180025a95  mov     rax, [rax+20h]
0x180025a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a9e  nop
0x180025a9f  mov     rcx, [rsp+160h+var_118]
0x180025aa4  test    rcx, rcx
0x180025aa7  jz      short loc_180025ABA
0x180025aa9  mov     rax, [rcx]
0x180025aac  mov     edx, 1
0x180025ab1  mov     rax, [rax+28h]
0x180025ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025aba  mov     rcx, [rbp+60h+var_40]
0x180025abe  xor     rcx, rsp; StackCookie
0x180025ac1  call    __security_check_cookie
0x180025ac6  mov     rbx, [rsp+160h+arg_0]
0x180025ace  add     rsp, 130h
0x180025ad5  pop     r15
0x180025ad7  pop     r14
0x180025ad9  pop     r13
  ... truncated ...
```
