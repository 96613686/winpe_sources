# CategoryIndex::AddNode(Microsoft::WRL::ComPtr<IXmlReader> &,std::deque<_CategoryNode *,std::allocator<_CategoryNode *>> &)

- ea: `0x18003e488`
- end: `0x18003ea21`
- name: `?AddNode@CategoryIndex@@AEAAXAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@AEAV?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@@Z`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003f334`

## callees

- `0x18000ebd8`
- `0x180020af4`
- `0x180020b74`
- `0x180021cf4`
- `0x18003d87c`
- `0x18003d904`
- `0x18003de84`
- `0x18003dfe0`
- `0x18003e420`
- `0x18003e488`
- `0x18003ebe8`
- `0x18003eef4`
- `0x18003f6a4`
- `0x18003fa34`
- `0x180047010`

## import_xrefs

- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x18003e52c`
- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x18003e563`
- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x18003e52c`
- `msvcp110_win!??0_Lockit@std@@QEAA@H@Z` at `0x18003e563`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x18003e536`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x18003e56d`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x18003e536`
- `msvcp110_win!??1_Lockit@std@@QEAA@XZ` at `0x18003e56d`
- `msvcrt!wcstoul` at `0x18003e790`
- `msvcrt!wcstoul` at `0x18003e790`
- `msvcrt!_errno` at `0x18003e7b1`
- `msvcrt!_errno` at `0x18003e7b1`
- `msvcrt!_wcsicmp` at `0x18003e4e7`
- `msvcrt!_wcsicmp` at `0x18003e59f`
- `msvcrt!_wcsicmp` at `0x18003e5fd`
- `msvcrt!_wcsicmp` at `0x18003e676`
- `msvcrt!_wcsicmp` at `0x18003e6d4`
- `msvcrt!_wcsicmp` at `0x18003e74b`
- `msvcrt!_wcsicmp` at `0x18003e4e7`
- `msvcrt!_wcsicmp` at `0x18003e59f`
- `msvcrt!_wcsicmp` at `0x18003e5fd`
- `msvcrt!_wcsicmp` at `0x18003e676`
- `msvcrt!_wcsicmp` at `0x18003e6d4`
- `msvcrt!_wcsicmp` at `0x18003e74b`

## string_xrefs

- `0x18003e4dc`: `categoryxml`

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
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // edi
  __int64 v28; // rax
  int v29; // r8d
  __int64 v30; // rax
  int v31; // r8d
  __int64 v32; // rbx
  int v33; // [rsp+20h] [rbp-39h]
  wchar_t *v34; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *String; // [rsp+38h] [rbp-21h] BYREF
  wchar_t *EndPtr; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v37[2]; // [rsp+48h] [rbp-11h] BYREF
  __int128 v38; // [rsp+58h] [rbp-1h] BYREF
  __int128 v39; // [rsp+68h] [rbp+Fh]
  __int128 v40; // [rsp+78h] [rbp+1Fh]
  __int64 v41; // [rsp+88h] [rbp+2Fh]
  char v42; // [rsp+90h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v44; // [rsp+C8h] [rbp+6Fh] BYREF
  wchar_t *String1; // [rsp+D8h] [rbp+7Fh] BYREF

  String1 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String1, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v6,
      v33);
  if ( !*(_QWORD *)(a3 + 32) && !_wcsicmp(String1, L"categoryxml") )
  {
    v44 = a1 + 8;
    return std::deque<_CategoryNode *>::push_back(a3, &v44);
  }
  v7 = *(_QWORD *)(a3 + 32);
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)0x80070057LL,
      v33);
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
      std::_Lockit::_Lockit((std::_Lockit *)&v44, 3);
      std::_Lockit::~_Lockit((std::_Lockit *)&v44);
      v10 = 0;
    }
  }
  v11 = v8 + v7 - 1;
  if ( !v10 )
    goto LABEL_13;
  if ( !*v10 )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v44, 3);
    std::_Lockit::~_Lockit((std::_Lockit *)&v44);
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
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v38 = 0u;
      *(_QWORD *)&v38 = std::_Tree_alloc<0,std::_Tree_base_types<unsigned int>>::_Buyheadnode(v20);
      v39 = 0;
      *(_QWORD *)&v39 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_CategoryNode>>>::_Buyheadnode();
      v40 = 0;
      *(_QWORD *)&v40 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode();
      v30 = std::_Tree_buy<std::pair<std::wstring const,_CategoryNode>>::_Buynode<unsigned short const * &,_CategoryNode>(
              v13 + 16,
              &String1,
              &v38);
      std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::_Insert_nohint<std::pair<std::wstring const,_CategoryNode> &,std::_Tree_node<std::pair<std::wstring const,_CategoryNode>,void *> *>(
        v13 + 16,
        (unsigned int)v37,
        v31,
        v30 + 32,
        v30);
      _CategoryNode::~_CategoryNode((_CategoryNode *)&v38);
      v32 = v37[0] + 64LL;
      *(_BYTE *)(v32 + 48) = CategoryIndex::HasUserNamedNodes(a2);
      v44 = v32;
      return std::deque<_CategoryNode *>::push_back(a3, &v44);
    }
    v34 = 0;
    String = 0;
    v21 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v21,
        v33);
    v22 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &v34, 0);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v22,
        v33);
    if ( _wcsicmp(v34, L"code") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v33);
    v23 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &String, 0);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v23,
        v33);
    v37[0] = 0;
    v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v24,
        v33);
    v25 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &v34, 0);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v25,
        v33);
    if ( _wcsicmp(v34, L"messageID") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v33);
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, v37, 0);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v26,
        v33);
    EndPtr = 0;
    v27 = wcstoul(String, &EndPtr, 16);
    if ( String == EndPtr || *EndPtr || *_errno() == 34 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v33);
    LODWORD(v44) = v27;
    v28 = std::_Tree_buy<std::pair<long const,std::wstring>>::_Buynode<long,unsigned short const * &>(
            v13 + 32,
            &v44,
            v37);
    return std::_Tree<std::_Tmap_traits<long,std::wstring,std::less<long>,std::allocator<std::pair<long const,std::wstring>>,0>>::_Insert_nohint<std::pair<long const,std::wstring> &,std::_Tree_node<std::pair<long const,std::wstring>,void *> *>(
             (int)v13 + 32,
             (unsigned int)&v42,
             v29,
             (int)v28 + 32,
             v28);
  }
  else
  {
    String = 0;
    v34 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v14,
        v33);
    v15 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &String, 0);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v15,
        v33);
    if ( _wcsicmp(String, L"name") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)0x8007000DLL,
        v33);
    v16 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &v34, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
        (const char *)(unsigned int)v16,
        v33);
    LODWORD(v44) = CategoryIndex::GetCategoryByName(v34);
    return std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int,std::_Nil>(
             v13,
             (unsigned int)v37,
             v17,
             (unsigned int)&v44,
             byte_18005ADE8);
  }
}

```

## disassembly

```asm
0x18003e488  mov     [rsp-8+arg_0], rbx
0x18003e48d  mov     [rsp-8+arg_10], rsi
0x18003e492  push    rbp
0x18003e493  push    rdi
0x18003e494  push    r14
0x18003e496  lea     rbp, [rsp-47h]
0x18003e49b  sub     rsp, 0A0h
0x18003e4a2  mov     rsi, r8
0x18003e4a5  mov     rdi, rdx
0x18003e4a8  mov     rbx, rcx
0x18003e4ab  mov     [rbp+57h+String1], 0
0x18003e4b3  mov     rcx, [rdx]
0x18003e4b6  mov     rax, [rcx]
0x18003e4b9  xor     r8d, r8d
0x18003e4bc  lea     rdx, [rbp+57h+String1]
0x18003e4c0  mov     rax, [rax+70h]
0x18003e4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4c9  mov     rcx, [rbp+5Fh]; this
0x18003e4cd  test    eax, eax
0x18003e4cf  js      loc_18003E8BF
0x18003e4d5  cmp     qword ptr [rsi+20h], 0
0x18003e4da  jnz     short loc_18003E4FE
0x18003e4dc  lea     rdx, aCategoryxml; "categoryxml"
0x18003e4e3  mov     rcx, [rbp+57h+String1]; String1
0x18003e4e7  call    cs:__imp__wcsicmp
0x18003e4ed  test    eax, eax
0x18003e4ef  jnz     short loc_18003E4FE
0x18003e4f1  lea     rax, [rbx+8]
0x18003e4f5  mov     [rbp+57h+arg_8], rax
0x18003e4f9  jmp     loc_18003E87F
0x18003e4fe  mov     rbx, [rsi+20h]
0x18003e502  mov     rcx, [rbp+5Fh]; this
0x18003e506  test    rbx, rbx
0x18003e509  jz      loc_18003E8D4
0x18003e50f  mov     r14, [rsi+18h]
0x18003e513  mov     rcx, [rsi]
0x18003e516  xor     eax, eax
0x18003e518  test    rcx, rcx
0x18003e51b  jz      short loc_18003E543
0x18003e51d  mov     rax, [rcx]
0x18003e520  test    rax, rax
0x18003e523  jnz     short loc_18003E540
0x18003e525  lea     edx, [rax+3]
0x18003e528  lea     rcx, [rbp+57h+arg_8]
0x18003e52c  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x18003e532  lea     rcx, [rbp+57h+arg_8]
0x18003e536  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x18003e53c  xor     eax, eax
0x18003e53e  jmp     short loc_18003E543
0x18003e540  mov     rax, [rax]
0x18003e543  dec     rbx
0x18003e546  add     rbx, r14
0x18003e549  test    rax, rax
0x18003e54c  jz      short loc_18003E573
0x18003e54e  mov     rdx, [rax]
0x18003e551  test    rdx, rdx
0x18003e554  jnz     loc_18003E657
0x18003e55a  mov     edx, 3
0x18003e55f  lea     rcx, [rbp+57h+arg_8]
0x18003e563  call    cs:__imp_??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x18003e569  lea     rcx, [rbp+57h+arg_8]
0x18003e56d  call    cs:__imp_??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x18003e573  xor     edx, edx
0x18003e575  mov     rcx, [rdx+10h]
0x18003e579  dec     rcx
0x18003e57c  mov     rax, rbx
0x18003e57f  shr     rax, 1
0x18003e582  and     rcx, rax
0x18003e585  mov     rax, [rdx+8]
0x18003e589  and     ebx, 1
0x18003e58c  mov     rax, [rax+rcx*8]
0x18003e590  mov     rbx, [rax+rbx*8]
0x18003e594  lea     rdx, aCategory; "category"
0x18003e59b  mov     rcx, [rbp+57h+String1]; String1
0x18003e59f  call    cs:__imp__wcsicmp
0x18003e5a5  test    eax, eax
0x18003e5a7  jnz     loc_18003E66B
0x18003e5ad  mov     [rbp+57h+String], 0
0x18003e5b5  mov     [rbp+57h+var_80], 0
0x18003e5bd  mov     rcx, [rdi]
0x18003e5c0  mov     rax, [rcx]
0x18003e5c3  mov     rax, [rax+48h]
0x18003e5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5cc  test    eax, eax
0x18003e5ce  js      loc_18003E8EC
0x18003e5d4  mov     rcx, [rdi]
0x18003e5d7  mov     rax, [rcx]
0x18003e5da  xor     r8d, r8d
0x18003e5dd  lea     rdx, [rbp+57h+String]
0x18003e5e1  mov     rax, [rax+70h]
0x18003e5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5ea  test    eax, eax
0x18003e5ec  js      loc_18003E905
0x18003e5f2  lea     rdx, aName; "name"
0x18003e5f9  mov     rcx, [rbp+57h+String]; String1
0x18003e5fd  call    cs:__imp__wcsicmp
0x18003e603  test    eax, eax
0x18003e605  jnz     loc_18003E91E
0x18003e60b  mov     rcx, [rdi]
0x18003e60e  mov     rax, [rcx]
0x18003e611  xor     r8d, r8d
0x18003e614  lea     rdx, [rbp+57h+var_80]
0x18003e618  mov     rax, [rax+80h]
0x18003e61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e624  test    eax, eax
0x18003e626  js      loc_18003E93A
0x18003e62c  mov     rcx, [rbp+57h+var_80]; String1
0x18003e630  call    ?GetCategoryByName@CategoryIndex@@SAIPEBG@Z; CategoryIndex::GetCategoryByName(ushort const *)
0x18003e635  mov     dword ptr [rbp+57h+arg_8], eax
0x18003e638  mov     al, cs:byte_18005ADE8
0x18003e63e  mov     byte ptr [rsp+0B0h+var_90], al
0x18003e642  lea     r9, [rbp+57h+arg_8]
0x18003e646  lea     rdx, [rbp+57h+var_68]
0x18003e64a  mov     rcx, rbx
0x18003e64d  call    ??$_Insert_nohint@IU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_N$$QEAIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint,std::_Nil>(bool,uint &&,std::_Nil)
0x18003e652  jmp     loc_18003E88B
0x18003e657  mov     rdx, [rdx]
0x18003e65a  test    rdx, rdx
0x18003e65d  jz      loc_18003E573
0x18003e663  mov     rdx, [rdx]
0x18003e666  jmp     loc_18003E575
0x18003e66b  lea     rdx, aError; "error"
0x18003e672  mov     rcx, [rbp+57h+String1]; String1
0x18003e676  call    cs:__imp__wcsicmp
0x18003e67c  test    eax, eax
0x18003e67e  jnz     loc_18003E7EF
0x18003e684  mov     [rbp+57h+var_80], 0
0x18003e68c  mov     [rbp+57h+String], 0
0x18003e694  mov     rcx, [rdi]
0x18003e697  mov     rax, [rcx]
0x18003e69a  mov     rax, [rax+48h]
0x18003e69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6a3  test    eax, eax
0x18003e6a5  js      loc_18003E953
0x18003e6ab  mov     rcx, [rdi]
0x18003e6ae  mov     rax, [rcx]
0x18003e6b1  xor     r8d, r8d
0x18003e6b4  lea     rdx, [rbp+57h+var_80]
0x18003e6b8  mov     rax, [rax+70h]
0x18003e6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6c1  test    eax, eax
0x18003e6c3  js      loc_18003E96C
0x18003e6c9  lea     rdx, aCode; "code"
0x18003e6d0  mov     rcx, [rbp+57h+var_80]; String1
0x18003e6d4  call    cs:__imp__wcsicmp
0x18003e6da  test    eax, eax
0x18003e6dc  jnz     loc_18003E985
0x18003e6e2  mov     rcx, [rdi]
0x18003e6e5  mov     rax, [rcx]
0x18003e6e8  xor     r8d, r8d
0x18003e6eb  lea     rdx, [rbp+57h+String]
0x18003e6ef  mov     rax, [rax+80h]
0x18003e6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6fb  test    eax, eax
0x18003e6fd  js      loc_18003E9A1
0x18003e703  mov     [rbp+57h+var_68], 0
0x18003e70b  mov     rcx, [rdi]
0x18003e70e  mov     rax, [rcx]
0x18003e711  mov     rax, [rax+48h]
0x18003e715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e71a  test    eax, eax
0x18003e71c  js      loc_18003E9BA
0x18003e722  mov     rcx, [rdi]
0x18003e725  mov     rax, [rcx]
0x18003e728  xor     r8d, r8d
0x18003e72b  lea     rdx, [rbp+57h+var_80]
0x18003e72f  mov     rax, [rax+70h]
0x18003e733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e738  test    eax, eax
0x18003e73a  js      loc_18003E9D3
0x18003e740  lea     rdx, aMessageid; "messageID"
0x18003e747  mov     rcx, [rbp+57h+var_80]; String1
0x18003e74b  call    cs:__imp__wcsicmp
0x18003e751  test    eax, eax
0x18003e753  jnz     loc_18003E9EC
0x18003e759  mov     rcx, [rdi]
0x18003e75c  mov     rax, [rcx]
0x18003e75f  xor     r8d, r8d
0x18003e762  lea     rdx, [rbp+57h+var_68]
0x18003e766  mov     rax, [rax+80h]
0x18003e76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e772  test    eax, eax
0x18003e774  js      loc_18003EA08
0x18003e77a  mov     [rbp+57h+EndPtr], 0
0x18003e782  mov     r8d, 10h; Radix
0x18003e788  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x18003e78c  mov     rcx, [rbp+57h+String]; String
0x18003e790  call    cs:__imp_wcstoul
0x18003e796  mov     edi, eax
0x18003e798  mov     rdx, [rbp+57h+EndPtr]
0x18003e79c  cmp     [rbp+57h+String], rdx
0x18003e7a0  jz      loc_18003E8A3
0x18003e7a6  xor     ecx, ecx
0x18003e7a8  cmp     cx, [rdx]
0x18003e7ab  jnz     loc_18003E8A3
0x18003e7b1  call    cs:__imp__errno
0x18003e7b7  cmp     dword ptr [rax], 22h ; '"'
0x18003e7ba  jz      loc_18003E8A3
0x18003e7c0  mov     dword ptr [rbp+57h+arg_8], edi
0x18003e7c3  lea     r8, [rbp+57h+var_68]
0x18003e7c7  lea     rdx, [rbp+57h+arg_8]
0x18003e7cb  lea     rcx, [rbx+20h]
0x18003e7cf  call    ??$_Buynode@JAEAPEBG@?$_Tree_buy@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@$$QEAJAEAPEBG@Z; std::_Tree_buy<std::pair<long const,std::wstring>>::_Buynode<long,ushort const * &>(long &&,ushort const * &)
0x18003e7d4  lea     r9, [rax+20h]
0x18003e7d8  mov     qword ptr [rsp+0B0h+var_90], rax
0x18003e7dd  lea     rdx, [rbp+57h+var_20]
0x18003e7e1  lea     rcx, [rbx+20h]
0x18003e7e5  call    ??$_Insert_nohint@AEAU?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@J@2@V?$allocator@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<long,std::wstring,std::less<long>,std::allocator<std::pair<long const,std::wstring>>,0>>::_Insert_nohint<std::pair<long const,std::wstring> &,std::_Tree_node<std::pair<long const,std::wstring>,void *> *>(bool,std::pair<long const,std::wstring> &,std::_Tree_node<std::pair<long const,std::wstring>,void *> *)
0x18003e7ea  jmp     loc_18003E88B
0x18003e7ef  xorps   xmm0, xmm0
0x18003e7f2  xor     eax, eax
0x18003e7f4  movups  [rbp+57h+var_58], xmm0
0x18003e7f8  movups  [rbp+57h+var_48], xmm0
0x18003e7fc  movups  [rbp+57h+var_38], xmm0
0x18003e800  mov     [rbp+57h+var_28], rax
0x18003e804  mov     qword ptr [rbp+57h+var_58], rax
0x18003e808  mov     qword ptr [rbp+57h+var_58+8], rax
0x18003e80c  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@IV?$allocator@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@IPEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<uint>>::_Buyheadnode(void)
0x18003e811  mov     qword ptr [rbp+57h+var_58], rax
0x18003e815  xorps   xmm0, xmm0
0x18003e818  movdqu  [rbp+57h+var_48], xmm0
0x18003e81d  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,_CategoryNode>>>::_Buyheadnode(void)
0x18003e822  mov     qword ptr [rbp+57h+var_48], rax
0x18003e826  xorps   xmm0, xmm0
0x18003e829  movdqu  [rbp+57h+var_38], xmm0
0x18003e82e  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode(void)
0x18003e833  mov     qword ptr [rbp+57h+var_38], rax
0x18003e837  lea     r8, [rbp+57h+var_58]
0x18003e83b  lea     rdx, [rbp+57h+String1]
0x18003e83f  lea     rcx, [rbx+10h]
0x18003e843  call    ??$_Buynode@AEAPEBGU_CategoryNode@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@1@AEAPEBG$$QEAU_CategoryNode@@@Z; std::_Tree_buy<std::pair<std::wstring const,_CategoryNode>>::_Buynode<ushort const * &,_CategoryNode>(ushort const * &,_CategoryNode &&)
0x18003e848  lea     r9, [rax+20h]
0x18003e84c  mov     qword ptr [rsp+0B0h+var_90], rax
0x18003e851  lea     rdx, [rbp+57h+var_68]
0x18003e855  lea     rcx, [rbx+10h]
0x18003e859  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::_Insert_nohint<std::pair<std::wstring const,_CategoryNode> &,std::_Tree_node<std::pair<std::wstring const,_CategoryNode>,void *> *>(bool,std::pair<std::wstring const,_CategoryNode> &,std::_Tree_node<std::pair<std::wstring const,_CategoryNode>,void *> *)
0x18003e85e  nop
0x18003e85f  lea     rcx, [rbp+57h+var_58]; this
0x18003e863  call    ??1_CategoryNode@@QEAA@XZ; _CategoryNode::~_CategoryNode(void)
0x18003e868  mov     rbx, [rbp+57h+var_68]
0x18003e86c  add     rbx, 40h ; '@'
0x18003e870  mov     rcx, rdi
0x18003e873  call    ?HasUserNamedNodes@CategoryIndex@@CA_NAEAV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z; CategoryIndex::HasUserNamedNodes(Microsoft::WRL::ComPtr<IXmlReader> &)
0x18003e878  mov     [rbx+30h], al
0x18003e87b  mov     [rbp+57h+arg_8], rbx
0x18003e87f  lea     rdx, [rbp+57h+arg_8]
0x18003e883  mov     rcx, rsi
0x18003e886  call    ?push_back@?$deque@PEAU_CategoryNode@@V?$allocator@PEAU_CategoryNode@@@std@@@std@@QEAAX$$QEAPEAU_CategoryNode@@@Z; std::deque<_CategoryNode *>::push_back(_CategoryNode * &&)
0x18003e88b  lea     r11, [rsp+0B0h+var_10]
0x18003e893  mov     rbx, [r11+20h]
0x18003e897  mov     rsi, [r11+30h]
0x18003e89b  mov     rsp, r11
0x18003e89e  pop     r14
0x18003e8a0  pop     rdi
0x18003e8a1  pop     rbp
0x18003e8a2  retn
0x18003e8a3  mov     rcx, [rbp+5Fh]; this
0x18003e8a7  mov     r9d, 8007000Dh; char *
0x18003e8ad  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e8b4  mov     edx, 9Bh; void *
0x18003e8b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e8bf  mov     r9d, eax; char *
0x18003e8c2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e8c9  mov     edx, 6Fh ; 'o'; void *
0x18003e8ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e8d4  mov     r9d, 80070057h; char *
0x18003e8da  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e8e1  mov     edx, 78h ; 'x'; void *
0x18003e8e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e8ec  mov     rcx, [rbp+5Fh]; this
0x18003e8f0  mov     r9d, eax; char *
0x18003e8f3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e8fa  mov     edx, 81h; void *
0x18003e8ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e905  mov     rcx, [rbp+5Fh]; this
0x18003e909  mov     r9d, eax; char *
0x18003e90c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e913  mov     edx, 82h; void *
0x18003e918  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e91e  mov     rcx, [rbp+5Fh]; this
0x18003e922  mov     r9d, 8007000Dh; char *
0x18003e928  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e92f  mov     edx, 83h; void *
0x18003e934  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e93a  mov     rcx, [rbp+5Fh]; this
0x18003e93e  mov     r9d, eax; char *
0x18003e941  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e948  mov     edx, 84h; void *
0x18003e94d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e953  mov     rcx, [rbp+5Fh]; this
0x18003e957  mov     r9d, eax; char *
0x18003e95a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e961  mov     edx, 8Eh; void *
0x18003e966  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e96c  mov     rcx, [rbp+5Fh]; this
0x18003e970  mov     r9d, eax; char *
0x18003e973  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18003e97a  mov     edx, 8Fh; void *
0x18003e97f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e985  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
