# CategoryIndex::AddNode(Microsoft::WRL::ComPtr<IXmlReader> &,std::deque<_CategoryNode *,std::allocator<_CategoryNode *>> &)

- ea: `0x180030bdc`
- end: `0x180031175`
- name: `?AddNode@CategoryIndex@@AEAAXAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@AEAV?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@@Z`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031a34`

## callees

- `0x18001b388`
- `0x180028bfc`
- `0x18002d134`
- `0x18002defc`
- `0x18002ff2c`
- `0x18002ffb4`
- `0x180030534`
- `0x180030690`
- `0x180030b74`
- `0x180030bdc`
- `0x1800312e4`
- `0x1800315f4`
- `0x180031df8`
- `0x1800322c0`
- `0x180037010`

## import_xrefs

- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x180030c80`
- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x180030cb7`
- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x180030c80`
- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x180030cb7`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x180030c8a`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x180030cc1`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x180030c8a`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x180030cc1`
- `msvcrt!_wcsicmp` at `0x180030c3b`
- `msvcrt!_wcsicmp` at `0x180030cf3`
- `msvcrt!_wcsicmp` at `0x180030d51`
- `msvcrt!_wcsicmp` at `0x180030dca`
- `msvcrt!_wcsicmp` at `0x180030e28`
- `msvcrt!_wcsicmp` at `0x180030e9f`
- `msvcrt!_wcsicmp` at `0x180030c3b`
- `msvcrt!_wcsicmp` at `0x180030cf3`
- `msvcrt!_wcsicmp` at `0x180030d51`
- `msvcrt!_wcsicmp` at `0x180030dca`
- `msvcrt!_wcsicmp` at `0x180030e28`
- `msvcrt!_wcsicmp` at `0x180030e9f`
- `msvcrt!_errno` at `0x180030f05`
- `msvcrt!_errno` at `0x180030f05`
- `msvcrt!wcstoul` at `0x180030ee4`
- `msvcrt!wcstoul` at `0x180030ee4`

## string_xrefs

- `0x180030c30`: `categoryxml`

## pseudocode

```c
__int64 __fastcall CategoryIndex::AddNode(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 *****v9; // rcx
  __int64 ***v10; // rax
  unsigned __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // r8d
  __int64 *v19; // rdx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rax
  int v28; // r8d
  __int64 v29; // rax
  int v30; // r8d
  __int64 v31; // rbx
  int v32; // [rsp+20h] [rbp-39h]
  wchar_t *v33; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *String; // [rsp+38h] [rbp-21h] BYREF
  wchar_t *EndPtr; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v36[2]; // [rsp+48h] [rbp-11h] BYREF
  __int128 v37; // [rsp+58h] [rbp-1h] BYREF
  __int128 v38; // [rsp+68h] [rbp+Fh]
  __int128 v39; // [rsp+78h] [rbp+1Fh]
  __int64 v40; // [rsp+88h] [rbp+2Fh]
  char v41; // [rsp+90h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v43; // [rsp+C8h] [rbp+6Fh] BYREF
  wchar_t *String1; // [rsp+D8h] [rbp+7Fh] BYREF

  String1 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String1, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v6,
      v32);
  if ( !*(_QWORD *)(a3 + 32) && !_wcsicmp(String1, L"categoryxml") )
  {
    v43 = a1 + 8;
    return std::deque<_CategoryNode *>::push_back(a3, &v43);
  }
  v7 = *(_QWORD *)(a3 + 32);
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)0x80070057LL,
      v32);
  v8 = *(_QWORD *)(a3 + 24);
  v9 = *(__int64 ******)a3;
  v10 = 0;
  if ( *(_QWORD *)a3 )
  {
    if ( *v9 )
    {
      v10 = **v9;
    }
    else
    {
      std::_Lockit::_Lockit((std::_Lockit *)&v43, 3);
      std::_Lockit::~_Lockit((std::_Lockit *)&v43);
      v10 = 0;
    }
  }
  v11 = v8 + v7 - 1;
  if ( !v10 )
    goto LABEL_13;
  if ( !*v10 )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v43, 3);
    std::_Lockit::~_Lockit((std::_Lockit *)&v43);
LABEL_13:
    v12 = 0;
    goto LABEL_14;
  }
  v19 = **v10;
  if ( !v19 )
    goto LABEL_13;
  v12 = *v19;
LABEL_14:
  v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 8 * ((v11 >> 1) & (*(_QWORD *)(v12 + 16) - 1LL))) + 8 * (v11 & 1));
  if ( _wcsicmp(String1, L"category") )
  {
    if ( _wcsicmp(String1, L"error") )
    {
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v37 = 0u;
      *(_QWORD *)&v37 = std::_Tree_alloc<0,std::_Tree_base_types<unsigned int>>::_Buyheadnode();
      v38 = 0;
      *(_QWORD *)&v38 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_CategoryNode>>>::_Buyheadnode();
      v39 = 0;
      *(_QWORD *)&v39 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,unsigned long>>>::_Buyheadnode();
      v29 = std::_Tree_buy<std::pair<std::wstring const,_CategoryNode>>::_Buynode<unsigned short const * &,_CategoryNode>(
              v13 + 16,
              &String1,
              &v37);
      std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::_Insert_nohint<std::pair<std::wstring const,_CategoryNode> &,std::_Tree_node<std::pair<std::wstring const,_CategoryNode>,void *> *>(
        v13 + 16,
        (unsigned int)v36,
        v30,
        v29 + 32,
        v29);
      _CategoryNode::~_CategoryNode((_CategoryNode *)&v37);
      v31 = v36[0] + 64LL;
      *(_BYTE *)(v31 + 48) = CategoryIndex::HasUserNamedNodes(a2);
      v43 = v31;
      return std::deque<_CategoryNode *>::push_back(a3, &v43);
    }
    v33 = 0;
    String = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v20,
        v32);
    v21 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &v33, 0);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v21,
        v32);
    if ( _wcsicmp(v33, L"code") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v32);
    v22 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &String, 0);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v22,
        v32);
    v36[0] = 0;
    v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v23,
        v32);
    v24 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &v33, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v24,
        v32);
    if ( _wcsicmp(v33, L"messageID") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v32);
    v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, v36, 0);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v25,
        v32);
    EndPtr = 0;
    v26 = wcstoul(String, &EndPtr, 16);
    if ( String == EndPtr || *EndPtr || *_errno() == 34 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v32);
    LODWORD(v43) = v26;
    v27 = std::_Tree_buy<std::pair<long const,std::wstring>>::_Buynode<long,unsigned short const * &>(
            v13 + 32,
            &v43,
            v36);
    return std::_Tree<std::_Tmap_traits<long,std::wstring,std::less<long>,std::allocator<std::pair<long const,std::wstring>>,0>>::_Insert_nohint<std::pair<long const,std::wstring> &,std::_Tree_node<std::pair<long const,std::wstring>,void *> *>(
             (int)v13 + 32,
             (unsigned int)&v41,
             v28,
             (int)v27 + 32,
             v27);
  }
  else
  {
    String = 0;
    v33 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v14,
        v32);
    v15 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String, 0);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v15,
        v32);
    if ( _wcsicmp(String, L"name") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v32);
    v16 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &v33, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v16,
        v32);
    LODWORD(v43) = CategoryIndex::GetCategoryByName(v33);
    return std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int,std::_Nil>(
             v13,
             (unsigned int)v36,
             v17,
             (unsigned int)&v43,
             byte_18004AED0);
  }
}

```

## disassembly

```asm
0x180030bdc  mov     [rsp-8+arg_0], rbx
0x180030be1  mov     [rsp-8+arg_10], rsi
0x180030be6  push    rbp
0x180030be7  push    rdi
0x180030be8  push    r14
0x180030bea  lea     rbp, [rsp-47h]
0x180030bef  sub     rsp, 0A0h
0x180030bf6  mov     rsi, r8
0x180030bf9  mov     rdi, rdx
0x180030bfc  mov     rbx, rcx
0x180030bff  mov     [rbp+57h+String1], 0
0x180030c07  mov     rcx, [rdx]
0x180030c0a  mov     rax, [rcx]
0x180030c0d  xor     r8d, r8d
0x180030c10  lea     rdx, [rbp+57h+String1]
0x180030c14  mov     rax, [rax+70h]
0x180030c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c1d  mov     rcx, [rbp+5Fh]; this
0x180030c21  test    eax, eax
0x180030c23  js      loc_180031013
0x180030c29  cmp     qword ptr [rsi+20h], 0
0x180030c2e  jnz     short loc_180030C52
0x180030c30  lea     rdx, aCategoryxml; "categoryxml"
0x180030c37  mov     rcx, [rbp+57h+String1]; String1
0x180030c3b  call    cs:__imp__wcsicmp
0x180030c41  test    eax, eax
0x180030c43  jnz     short loc_180030C52
0x180030c45  lea     rax, [rbx+8]
0x180030c49  mov     [rbp+57h+arg_8], rax
0x180030c4d  jmp     loc_180030FD3
0x180030c52  mov     rbx, [rsi+20h]
0x180030c56  mov     rcx, [rbp+5Fh]; this
0x180030c5a  test    rbx, rbx
0x180030c5d  jz      loc_180031028
0x180030c63  mov     r14, [rsi+18h]
0x180030c67  mov     rcx, [rsi]
0x180030c6a  xor     eax, eax
0x180030c6c  test    rcx, rcx
0x180030c6f  jz      short loc_180030C97
0x180030c71  mov     rax, [rcx]
0x180030c74  test    rax, rax
0x180030c77  jnz     short loc_180030C94
0x180030c79  lea     edx, [rax+3]
0x180030c7c  lea     rcx, [rbp+57h+arg_8]
0x180030c80  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180030c86  lea     rcx, [rbp+57h+arg_8]
0x180030c8a  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180030c90  xor     eax, eax
0x180030c92  jmp     short loc_180030C97
0x180030c94  mov     rax, [rax]
0x180030c97  dec     rbx
0x180030c9a  add     rbx, r14
0x180030c9d  test    rax, rax
0x180030ca0  jz      short loc_180030CC7
0x180030ca2  mov     rdx, [rax]
0x180030ca5  test    rdx, rdx
0x180030ca8  jnz     loc_180030DAB
0x180030cae  mov     edx, 3
0x180030cb3  lea     rcx, [rbp+57h+arg_8]
0x180030cb7  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180030cbd  lea     rcx, [rbp+57h+arg_8]
0x180030cc1  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180030cc7  xor     edx, edx
0x180030cc9  mov     rcx, [rdx+10h]
0x180030ccd  dec     rcx
0x180030cd0  mov     rax, rbx
0x180030cd3  shr     rax, 1
0x180030cd6  and     rcx, rax
0x180030cd9  mov     rax, [rdx+8]
0x180030cdd  and     ebx, 1
0x180030ce0  mov     rax, [rax+rcx*8]
0x180030ce4  mov     rbx, [rax+rbx*8]
0x180030ce8  lea     rdx, aCategory; "category"
0x180030cef  mov     rcx, [rbp+57h+String1]; String1
0x180030cf3  call    cs:__imp__wcsicmp
0x180030cf9  test    eax, eax
0x180030cfb  jnz     loc_180030DBF
0x180030d01  mov     [rbp+57h+String], 0
0x180030d09  mov     [rbp+57h+var_80], 0
0x180030d11  mov     rcx, [rdi]
0x180030d14  mov     rax, [rcx]
0x180030d17  mov     rax, [rax+48h]
0x180030d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d20  test    eax, eax
0x180030d22  js      loc_180031040
0x180030d28  mov     rcx, [rdi]
0x180030d2b  mov     rax, [rcx]
0x180030d2e  xor     r8d, r8d
0x180030d31  lea     rdx, [rbp+57h+String]
0x180030d35  mov     rax, [rax+70h]
0x180030d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d3e  test    eax, eax
0x180030d40  js      loc_180031059
0x180030d46  lea     rdx, aName; "name"
0x180030d4d  mov     rcx, [rbp+57h+String]; String1
0x180030d51  call    cs:__imp__wcsicmp
0x180030d57  test    eax, eax
0x180030d59  jnz     loc_180031072
0x180030d5f  mov     rcx, [rdi]
0x180030d62  mov     rax, [rcx]
0x180030d65  xor     r8d, r8d
0x180030d68  lea     rdx, [rbp+57h+var_80]
0x180030d6c  mov     rax, [rax+80h]
0x180030d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d78  test    eax, eax
0x180030d7a  js      loc_18003108E
0x180030d80  mov     rcx, [rbp+57h+var_80]; String1
0x180030d84  call    ?GetCategoryByName@CategoryIndex@@SAIPEBG@Z; CategoryIndex::GetCategoryByName(ushort const *)
0x180030d89  mov     dword ptr [rbp+57h+arg_8], eax
0x180030d8c  mov     al, cs:byte_18004AED0
0x180030d92  mov     byte ptr [rsp+0B0h+var_90], al
0x180030d96  lea     r9, [rbp+57h+arg_8]
0x180030d9a  lea     rdx, [rbp+57h+var_68]
0x180030d9e  mov     rcx, rbx
0x180030da1  call    ??$_Insert_nohint@IU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_N$$QEAIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint,std::_Nil>(bool,uint &&,std::_Nil)
0x180030da6  jmp     loc_180030FDF
0x180030dab  mov     rdx, [rdx]
0x180030dae  test    rdx, rdx
0x180030db1  jz      loc_180030CC7
0x180030db7  mov     rdx, [rdx]
0x180030dba  jmp     loc_180030CC9
0x180030dbf  lea     rdx, aError; "error"
0x180030dc6  mov     rcx, [rbp+57h+String1]; String1
0x180030dca  call    cs:__imp__wcsicmp
0x180030dd0  test    eax, eax
0x180030dd2  jnz     loc_180030F43
0x180030dd8  mov     [rbp+57h+var_80], 0
0x180030de0  mov     [rbp+57h+String], 0
0x180030de8  mov     rcx, [rdi]
0x180030deb  mov     rax, [rcx]
0x180030dee  mov     rax, [rax+48h]
0x180030df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030df7  test    eax, eax
0x180030df9  js      loc_1800310A7
0x180030dff  mov     rcx, [rdi]
0x180030e02  mov     rax, [rcx]
0x180030e05  xor     r8d, r8d
0x180030e08  lea     rdx, [rbp+57h+var_80]
0x180030e0c  mov     rax, [rax+70h]
0x180030e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e15  test    eax, eax
0x180030e17  js      loc_1800310C0
0x180030e1d  lea     rdx, aCode; "code"
0x180030e24  mov     rcx, [rbp+57h+var_80]; String1
0x180030e28  call    cs:__imp__wcsicmp
0x180030e2e  test    eax, eax
0x180030e30  jnz     loc_1800310D9
0x180030e36  mov     rcx, [rdi]
0x180030e39  mov     rax, [rcx]
0x180030e3c  xor     r8d, r8d
0x180030e3f  lea     rdx, [rbp+57h+String]
0x180030e43  mov     rax, [rax+80h]
0x180030e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e4f  test    eax, eax
0x180030e51  js      loc_1800310F5
0x180030e57  mov     [rbp+57h+var_68], 0
0x180030e5f  mov     rcx, [rdi]
0x180030e62  mov     rax, [rcx]
0x180030e65  mov     rax, [rax+48h]
0x180030e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e6e  test    eax, eax
0x180030e70  js      loc_18003110E
0x180030e76  mov     rcx, [rdi]
0x180030e79  mov     rax, [rcx]
0x180030e7c  xor     r8d, r8d
0x180030e7f  lea     rdx, [rbp+57h+var_80]
0x180030e83  mov     rax, [rax+70h]
0x180030e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e8c  test    eax, eax
0x180030e8e  js      loc_180031127
0x180030e94  lea     rdx, aMessageid; "messageID"
0x180030e9b  mov     rcx, [rbp+57h+var_80]; String1
0x180030e9f  call    cs:__imp__wcsicmp
0x180030ea5  test    eax, eax
0x180030ea7  jnz     loc_180031140
0x180030ead  mov     rcx, [rdi]
0x180030eb0  mov     rax, [rcx]
0x180030eb3  xor     r8d, r8d
0x180030eb6  lea     rdx, [rbp+57h+var_68]
0x180030eba  mov     rax, [rax+80h]
0x180030ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ec6  test    eax, eax
0x180030ec8  js      loc_18003115C
0x180030ece  mov     [rbp+57h+EndPtr], 0
0x180030ed6  mov     r8d, 10h; Radix
0x180030edc  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x180030ee0  mov     rcx, [rbp+57h+String]; String
0x180030ee4  call    cs:__imp_wcstoul
0x180030eea  mov     edi, eax
0x180030eec  mov     rdx, [rbp+57h+EndPtr]
0x180030ef0  cmp     [rbp+57h+String], rdx
0x180030ef4  jz      loc_180030FF7
0x180030efa  xor     ecx, ecx
0x180030efc  cmp     cx, [rdx]
0x180030eff  jnz     loc_180030FF7
0x180030f05  call    cs:__imp__errno
0x180030f0b  cmp     dword ptr [rax], 22h ; '"'
0x180030f0e  jz      loc_180030FF7
0x180030f14  mov     dword ptr [rbp+57h+arg_8], edi
0x180030f17  lea     r8, [rbp+57h+var_68]
0x180030f1b  lea     rdx, [rbp+57h+arg_8]
0x180030f1f  lea     rcx, [rbx+20h]
0x180030f23  call    ??$_Buynode@JAEAPEBG@?$_Tree_buy@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@$$QEAJAEAPEBG@Z; std::_Tree_buy<std::pair<long const,std::wstring>>::_Buynode<long,ushort const * &>(long &&,ushort const * &)
0x180030f28  lea     r9, [rax+20h]
0x180030f2c  mov     qword ptr [rsp+0B0h+var_90], rax
0x180030f31  lea     rdx, [rbp+57h+var_20]
0x180030f35  lea     rcx, [rbx+20h]
0x180030f39  call    ??$_Insert_nohint@AEAU?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@J@2@V?$allocator@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<long,std::wstring,std::less<long>,std::allocator<std::pair<long const,std::wstring>>,0>>::_Insert_nohint<std::pair<long const,std::wstring> &,std::_Tree_node<std::pair<long const,std::wstring>,void *> *>(bool,std::pair<long const,std::wstring> &,std::_Tree_node<std::pair<long const,std::wstring>,void *> *)
0x180030f3e  jmp     loc_180030FDF
0x180030f43  xorps   xmm0, xmm0
0x180030f46  xor     eax, eax
0x180030f48  movups  [rbp+57h+var_58], xmm0
0x180030f4c  movups  [rbp+57h+var_48], xmm0
0x180030f50  movups  [rbp+57h+var_38], xmm0
0x180030f54  mov     [rbp+57h+var_28], rax
0x180030f58  mov     qword ptr [rbp+57h+var_58], rax
0x180030f5c  mov     qword ptr [rbp+57h+var_58+8], rax
0x180030f60  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@IV?$allocator@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@IPEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<uint>>::_Buyheadnode(void)
0x180030f65  mov     qword ptr [rbp+57h+var_58], rax
0x180030f69  xorps   xmm0, xmm0
0x180030f6c  movdqu  [rbp+57h+var_48], xmm0
0x180030f71  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_CategoryNode>>>::_Buyheadnode(void)
0x180030f76  mov     qword ptr [rbp+57h+var_48], rax
0x180030f7a  xorps   xmm0, xmm0
0x180030f7d  movdqu  [rbp+57h+var_38], xmm0
0x180030f82  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,ulong>>>::_Buyheadnode(void)
0x180030f87  mov     qword ptr [rbp+57h+var_38], rax
0x180030f8b  lea     r8, [rbp+57h+var_58]
0x180030f8f  lea     rdx, [rbp+57h+String1]
0x180030f93  lea     rcx, [rbx+10h]
0x180030f97  call    ??$_Buynode@AEAPEBGU_CategoryNode@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@1@AEAPEBG$$QEAU_CategoryNode@@@Z; std::_Tree_buy<std::pair<std::wstring const,_CategoryNode>>::_Buynode<ushort const * &,_CategoryNode>(ushort const * &,_CategoryNode &&)
0x180030f9c  lea     r9, [rax+20h]
0x180030fa0  mov     qword ptr [rsp+0B0h+var_90], rax
0x180030fa5  lea     rdx, [rbp+57h+var_68]
0x180030fa9  lea     rcx, [rbx+10h]
0x180030fad  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::_Insert_nohint<std::pair<std::wstring const,_CategoryNode> &,std::_Tree_node<std::pair<std::wstring const,_CategoryNode>,void *> *>(bool,std::pair<std::wstring const,_CategoryNode> &,std::_Tree_node<std::pair<std::wstring const,_CategoryNode>,void *> *)
0x180030fb2  nop
0x180030fb3  lea     rcx, [rbp+57h+var_58]; this
0x180030fb7  call    ??1_CategoryNode@@QEAA@XZ; _CategoryNode::~_CategoryNode(void)
0x180030fbc  mov     rbx, [rbp+57h+var_68]
0x180030fc0  add     rbx, 40h ; '@'
0x180030fc4  mov     rcx, rdi
0x180030fc7  call    ?HasUserNamedNodes@CategoryIndex@@CA_NAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z; CategoryIndex::HasUserNamedNodes(Microsoft::WRL::ComPtr<IXmlReader> &)
0x180030fcc  mov     [rbx+30h], al
0x180030fcf  mov     [rbp+57h+arg_8], rbx
0x180030fd3  lea     rdx, [rbp+57h+arg_8]
0x180030fd7  mov     rcx, rsi
0x180030fda  call    ?push_back@?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@QEAAX$$QEAPEAU_CategoryNode@@@Z; std::deque<_CategoryNode *>::push_back(_CategoryNode * &&)
0x180030fdf  lea     r11, [rsp+0B0h+var_10]
0x180030fe7  mov     rbx, [r11+20h]
0x180030feb  mov     rsi, [r11+30h]
0x180030fef  mov     rsp, r11
0x180030ff2  pop     r14
0x180030ff4  pop     rdi
0x180030ff5  pop     rbp
0x180030ff6  retn
0x180030ff7  mov     rcx, [rbp+5Fh]; this
0x180030ffb  mov     r9d, 8007000Dh; char *
0x180031001  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031008  mov     edx, 9Bh; void *
0x18003100d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031013  mov     r9d, eax; char *
0x180031016  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003101d  mov     edx, 6Fh ; 'o'; void *
0x180031022  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031028  mov     r9d, 80070057h; char *
0x18003102e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031035  mov     edx, 78h ; 'x'; void *
0x18003103a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031040  mov     rcx, [rbp+5Fh]; this
0x180031044  mov     r9d, eax; char *
0x180031047  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003104e  mov     edx, 81h; void *
0x180031053  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031059  mov     rcx, [rbp+5Fh]; this
0x18003105d  mov     r9d, eax; char *
0x180031060  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031067  mov     edx, 82h; void *
0x18003106c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031072  mov     rcx, [rbp+5Fh]; this
0x180031076  mov     r9d, 8007000Dh; char *
0x18003107c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x180031083  mov     edx, 83h; void *
0x180031088  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003108e  mov     rcx, [rbp+5Fh]; this
0x180031092  mov     r9d, eax; char *
0x180031095  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003109c  mov     edx, 84h; void *
0x1800310a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800310a7  mov     rcx, [rbp+5Fh]; this
0x1800310ab  mov     r9d, eax; char *
0x1800310ae  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800310b5  mov     edx, 8Eh; void *
0x1800310ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800310c0  mov     rcx, [rbp+5Fh]; this
0x1800310c4  mov     r9d, eax; char *
0x1800310c7  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800310ce  mov     edx, 8Fh; void *
0x1800310d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800310d9  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
