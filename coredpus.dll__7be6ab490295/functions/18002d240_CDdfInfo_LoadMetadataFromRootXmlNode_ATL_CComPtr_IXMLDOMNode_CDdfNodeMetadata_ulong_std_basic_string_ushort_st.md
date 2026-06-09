# CDdfInfo::LoadMetadataFromRootXmlNode(ATL::CComPtr<IXMLDOMNode>,CDdfNodeMetadata *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18002d240`
- end: `0x18002d6b3`
- name: `?LoadMetadataFromRootXmlNode@CDdfInfo@@AEAAJV?$CComPtr@UIXMLDOMNode@@@ATL@@PEAVCDdfNodeMetadata@@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012d80`
- `0x18002d240`

## callees

- `0x180004a70`
- `0x1800110bc`
- `0x1800118a0`
- `0x180011d9c`
- `0x180012b54`
- `0x180013b80`
- `0x180014330`
- `0x18002b808`
- `0x18002d240`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d300`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d3c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d524`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d593`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d5a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d625`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d634`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d646`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d300`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d3c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d524`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d593`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d5a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d625`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d634`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d646`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDdfInfo::LoadMetadataFromRootXmlNode(__int64 a1, OLECHAR *a2, __int64 a3, int a4, void *a5)
{
  unsigned int v7; // r14d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v10; // rax
  int MetadataFromRootXmlNode; // ebx
  __int64 v12; // rdx
  int v13; // eax
  BSTR v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v19; // rax
  int v20; // r12d
  OLECHAR *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rbx
  OLECHAR *v26; // rdi
  __int64 (__fastcall *v27)(OLECHAR *, _QWORD, __int64 *); // rbx
  _QWORD *v28; // rax
  unsigned __int64 v29; // r9
  int v31; // [rsp+20h] [rbp-C1h]
  OLECHAR *v32; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v33; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v34; // [rsp+40h] [rbp-A1h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-99h] BYREF
  int v36; // [rsp+50h] [rbp-91h] BYREF
  int v37; // [rsp+54h] [rbp-8Dh] BYREF
  BSTR v38; // [rsp+58h] [rbp-89h] BYREF
  __int64 v39; // [rsp+60h] [rbp-81h] BYREF
  int v40; // [rsp+68h] [rbp-79h]
  int v41[2]; // [rsp+70h] [rbp-71h]
  BSTR v42[5]; // [rsp+78h] [rbp-69h] BYREF
  _BYTE v43[32]; // [rsp+A0h] [rbp-41h] BYREF
  void *v44; // [rsp+C0h] [rbp-21h]
  _BYTE v45[32]; // [rsp+C8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v40 = a4;
  *(_QWORD *)v41 = a1;
  v42[2] = a2;
  v44 = a5;
  v7 = 0;
  v39 = 0;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  v38 = 0;
  v42[3] = 0;
  v42[4] = 0;
  v36 = 0;
  v37 = 0;
  if ( !*(_QWORD *)a2 || !a3 )
  {
    MetadataFromRootXmlNode = -2147024809;
    v12 = 713;
    goto LABEL_37;
  }
  *(_DWORD *)(a3 + 32) = a4;
  v8 = *(_QWORD *)a2;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)a2 + 296LL);
  v10 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"./NodeName");
  MetadataFromRootXmlNode = v9(v8, *v10, &v39);
  SysFreeString(bstrString);
  if ( MetadataFromRootXmlNode < 0 )
  {
    v12 = 720;
LABEL_37:
    v29 = (unsigned int)MetadataFromRootXmlNode;
    goto LABEL_38;
  }
  if ( MetadataFromRootXmlNode == 1 )
  {
    MetadataFromRootXmlNode = -2147418113;
    v12 = 724;
    goto LABEL_37;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v39 + 208LL))(v39, &v38);
  MetadataFromRootXmlNode = v13;
  if ( v13 < 0 )
  {
    v12 = 726;
LABEL_34:
    v29 = (unsigned int)v13;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)v29,
      v31);
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(v38);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v33);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v34);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v32);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v39);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)a2);
    std::wstring::_Tidy_deallocate(a5);
    return (unsigned int)MetadataFromRootXmlNode;
  }
  v14 = v38;
  v15 = -1;
  do
    ++v15;
  while ( v38[v15] );
  if ( !v15 )
    v14 = L"*";
  v16 = std::wstring::append(a5, v14);
  std::wstring::operator=(a3, v16);
  v17 = *(_QWORD *)a2;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)a2 + 288LL);
  v19 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"child::Node");
  MetadataFromRootXmlNode = v18(v17, *v19, &v34);
  SysFreeString(bstrString);
  if ( MetadataFromRootXmlNode < 0 )
  {
    v12 = 739;
    goto LABEL_37;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 64LL))(v34, &v36);
  MetadataFromRootXmlNode = v13;
  if ( v13 < 0 )
  {
    v12 = 740;
    goto LABEL_34;
  }
  v20 = a3 + 40;
  while ( (int)v7 < v36 )
  {
    v21 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR **))(*(_QWORD *)v34 + 56LL))(v34, v7, &v32);
    MetadataFromRootXmlNode = v13;
    if ( v13 < 0 )
    {
      v12 = 748;
      goto LABEL_34;
    }
    v23 = std::wstring::wstring(v45, a3);
    v24 = std::wstring::append(v23, L"/");
    v25 = (void *)std::wstring::wstring(v43, v24);
    bstrString = v32;
    if ( v32 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v32 + 8LL))(v32);
    MetadataFromRootXmlNode = CDdfInfo::LoadMetadataFromRootXmlNode(v41[0], (int)&bstrString, v20, v40 + 1, v25);
    std::wstring::_Tidy_deallocate(v45);
    if ( MetadataFromRootXmlNode < 0 )
    {
      v12 = 750;
      goto LABEL_37;
    }
    v26 = v32;
    v27 = *(__int64 (__fastcall **)(OLECHAR *, _QWORD, __int64 *))(*(_QWORD *)v32 + 288LL);
    v28 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v42, L"descendant::Node");
    MetadataFromRootXmlNode = v27(v26, *v28, &v33);
    SysFreeString(v42[0]);
    if ( MetadataFromRootXmlNode < 0 )
    {
      v12 = 753;
      goto LABEL_37;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 64LL))(v33, &v37);
    MetadataFromRootXmlNode = v13;
    if ( v13 < 0 )
    {
      v12 = 754;
      goto LABEL_34;
    }
    v20 += 40 * v37 + 40;
    ++v7;
  }
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(v38);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v33);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v34);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v32);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v39);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)a2);
  std::wstring::_Tidy_deallocate(a5);
  return 0;
}

```

## disassembly

```asm
0x18002d240  push    rbp
0x18002d242  push    rbx
0x18002d243  push    rsi
0x18002d244  push    rdi
0x18002d245  push    r12
0x18002d247  push    r13
0x18002d249  push    r14
0x18002d24b  push    r15
0x18002d24d  lea     rbp, [rsp-17h]
0x18002d252  sub     rsp, 0F8h
0x18002d259  mov     rax, cs:__security_cookie
0x18002d260  xor     rax, rsp
0x18002d263  mov     [rbp+4Fh+var_48], rax
0x18002d267  mov     eax, r9d
0x18002d26a  mov     [rbp+4Fh+var_C8], eax
0x18002d26d  mov     r13, r8
0x18002d270  mov     rsi, rdx
0x18002d273  mov     qword ptr [rbp+4Fh+var_C0], rcx
0x18002d277  mov     [rbp+4Fh+var_A8], rdx
0x18002d27b  mov     r15, [rbp+4Fh+arg_20]
0x18002d27f  mov     [rbp+4Fh+var_70], r15
0x18002d283  xor     r14d, r14d
0x18002d286  mov     [rsp+130h+var_D0], r14
0x18002d28b  mov     [rsp+130h+var_100], r14
0x18002d290  mov     [rsp+130h+var_F0], r14
0x18002d295  mov     [rsp+130h+var_F8], r14
0x18002d29a  mov     [rsp+130h+var_D8], r14
0x18002d29f  mov     [rbp+4Fh+var_A0], r14
0x18002d2a3  mov     [rbp+4Fh+var_98], r14
0x18002d2a7  mov     [rsp+130h+var_E0], r14d
0x18002d2ac  mov     [rsp+130h+var_DC], r14d
0x18002d2b1  cmp     [rdx], r14
0x18002d2b4  jz      loc_18002D605
0x18002d2ba  test    r8, r8
0x18002d2bd  jz      loc_18002D605
0x18002d2c3  mov     [r8+20h], eax
0x18002d2c7  mov     rdi, [rdx]
0x18002d2ca  mov     rax, [rdi]
0x18002d2cd  mov     rbx, [rax+128h]
0x18002d2d4  lea     rdx, aNodename; "./NodeName"
0x18002d2db  lea     rcx, [rsp+130h+bstrString]; this
0x18002d2e0  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002d2e5  nop
0x18002d2e6  lea     r8, [rsp+130h+var_D0]
0x18002d2eb  mov     rdx, [rax]
0x18002d2ee  mov     rcx, rdi
0x18002d2f1  mov     rax, rbx
0x18002d2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2f9  mov     ebx, eax
0x18002d2fb  mov     rcx, [rsp+130h+bstrString]; bstrString
0x18002d300  call    cs:__imp_SysFreeString
0x18002d307  nop     dword ptr [rax+rax+00h]
0x18002d30c  test    ebx, ebx
0x18002d30e  jns     short loc_18002D31A
0x18002d310  mov     edx, 2D0h
0x18002d315  jmp     loc_18002D60F
0x18002d31a  cmp     ebx, 1
0x18002d31d  jnz     short loc_18002D32E
0x18002d31f  mov     ebx, 8000FFFFh
0x18002d324  mov     edx, 2D4h
0x18002d329  jmp     loc_18002D60F
0x18002d32e  mov     rcx, [rsp+130h+var_D0]
0x18002d333  mov     rax, [rcx]
0x18002d336  lea     rdx, [rsp+130h+var_D8]
0x18002d33b  mov     rax, [rax+0D0h]
0x18002d342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d347  mov     ebx, eax
0x18002d349  test    eax, eax
0x18002d34b  jns     short loc_18002D357
0x18002d34d  mov     edx, 2D6h
0x18002d352  jmp     loc_18002D589
0x18002d357  mov     rdx, [rsp+130h+var_D8]
0x18002d35c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d360  inc     rax
0x18002d363  cmp     [rdx+rax*2], r14w
0x18002d368  jnz     short loc_18002D360
0x18002d36a  mov     rcx, r15
0x18002d36d  test    rax, rax
0x18002d370  jnz     short loc_18002D379
0x18002d372  lea     rdx, asc_180034C20; "*"
0x18002d379  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002d37e  mov     rdx, rax
0x18002d381  mov     rcx, r13
0x18002d384  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d389  mov     rdi, [rsi]
0x18002d38c  mov     rax, [rdi]
0x18002d38f  mov     rbx, [rax+120h]
0x18002d396  lea     rdx, aChildNode; "child::Node"
0x18002d39d  lea     rcx, [rsp+130h+bstrString]; this
0x18002d3a2  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002d3a7  nop
0x18002d3a8  lea     r8, [rsp+130h+var_F0]
0x18002d3ad  mov     rdx, [rax]
0x18002d3b0  mov     rcx, rdi
0x18002d3b3  mov     rax, rbx
0x18002d3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3bb  mov     ebx, eax
0x18002d3bd  mov     rcx, [rsp+130h+bstrString]; bstrString
0x18002d3c2  call    cs:__imp_SysFreeString
0x18002d3c9  nop     dword ptr [rax+rax+00h]
0x18002d3ce  test    ebx, ebx
0x18002d3d0  jns     short loc_18002D3DC
0x18002d3d2  mov     edx, 2E3h
0x18002d3d7  jmp     loc_18002D60F
0x18002d3dc  mov     rcx, [rsp+130h+var_F0]
0x18002d3e1  mov     rax, [rcx]
0x18002d3e4  lea     rdx, [rsp+130h+var_E0]
0x18002d3e9  mov     rax, [rax+40h]
0x18002d3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3f2  mov     ebx, eax
0x18002d3f4  test    eax, eax
0x18002d3f6  jns     short loc_18002D402
0x18002d3f8  mov     edx, 2E4h
0x18002d3fd  jmp     loc_18002D589
0x18002d402  lea     r12, [r13+28h]
0x18002d406  cmp     r14d, [rsp+130h+var_E0]
0x18002d40b  jge     loc_18002D591
0x18002d411  mov     rcx, [rsp+130h+var_100]
0x18002d416  test    rcx, rcx
0x18002d419  jz      short loc_18002D431
0x18002d41b  mov     [rsp+130h+var_100], 0
0x18002d424  mov     rax, [rcx]
0x18002d427  mov     rax, [rax+10h]
0x18002d42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d430  nop
0x18002d431  mov     rcx, [rsp+130h+var_F8]
0x18002d436  test    rcx, rcx
0x18002d439  jz      short loc_18002D451
0x18002d43b  mov     [rsp+130h+var_F8], 0
0x18002d444  mov     rax, [rcx]
0x18002d447  mov     rax, [rax+10h]
0x18002d44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d450  nop
0x18002d451  mov     rcx, [rsp+130h+var_F0]
0x18002d456  mov     rax, [rcx]
0x18002d459  lea     r8, [rsp+130h+var_100]
0x18002d45e  mov     edx, r14d
0x18002d461  mov     rax, [rax+38h]
0x18002d465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d46a  mov     ebx, eax
0x18002d46c  test    eax, eax
0x18002d46e  js      loc_18002D584
0x18002d474  mov     rdx, r13
0x18002d477  lea     rcx, [rbp+4Fh+var_68]
0x18002d47b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002d480  nop
0x18002d481  lea     rdx, asc_180032DA8; "/"
0x18002d488  mov     rcx, rax
0x18002d48b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002d490  mov     rdx, rax
0x18002d493  lea     rcx, [rbp+4Fh+var_90]
0x18002d497  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002d49c  mov     rbx, rax
0x18002d49f  mov     rcx, [rsp+130h+var_100]
0x18002d4a4  mov     [rsp+130h+bstrString], rcx
0x18002d4a9  test    rcx, rcx
0x18002d4ac  jz      short loc_18002D4BB
0x18002d4ae  mov     rdx, [rcx]
0x18002d4b1  mov     rax, [rdx+8]
0x18002d4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4ba  nop
0x18002d4bb  mov     r9d, [rbp+4Fh+var_C8]
0x18002d4bf  inc     r9d; int
0x18002d4c2  mov     qword ptr [rsp+130h+var_110], rbx; int
0x18002d4c7  mov     r8, r12; int
0x18002d4ca  lea     rdx, [rsp+130h+bstrString]; int
0x18002d4cf  mov     rcx, qword ptr [rbp+4Fh+var_C0]; int
0x18002d4d3  call    ?LoadMetadataFromRootXmlNode@CDdfInfo@@AEAAJV?$CComPtr@UIXMLDOMNode@@@ATL@@PEAVCDdfNodeMetadata@@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CDdfInfo::LoadMetadataFromRootXmlNode(ATL::CComPtr<IXMLDOMNode>,CDdfNodeMetadata *,ulong,std::wstring)
0x18002d4d8  mov     ebx, eax
0x18002d4da  lea     rcx, [rbp+4Fh+var_68]; void *
0x18002d4de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d4e3  test    ebx, ebx
0x18002d4e5  js      loc_18002D57A
0x18002d4eb  mov     rdi, [rsp+130h+var_100]
0x18002d4f0  mov     rax, [rdi]
0x18002d4f3  mov     rbx, [rax+120h]
0x18002d4fa  lea     rdx, aDescendantNode; "descendant::Node"
0x18002d501  lea     rcx, [rbp+4Fh+var_B8]; this
0x18002d505  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002d50a  nop
0x18002d50b  lea     r8, [rsp+130h+var_F8]
0x18002d510  mov     rdx, [rax]
0x18002d513  mov     rcx, rdi
0x18002d516  mov     rax, rbx
0x18002d519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d51e  mov     ebx, eax
0x18002d520  mov     rcx, [rbp+4Fh+var_B8]; bstrString
0x18002d524  call    cs:__imp_SysFreeString
0x18002d52b  nop     dword ptr [rax+rax+00h]
0x18002d530  test    ebx, ebx
0x18002d532  js      short loc_18002D570
0x18002d534  mov     rcx, [rsp+130h+var_F8]
0x18002d539  mov     rax, [rcx]
0x18002d53c  lea     rdx, [rsp+130h+var_DC]
0x18002d541  mov     rax, [rax+40h]
0x18002d545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d54a  mov     ebx, eax
0x18002d54c  test    eax, eax
0x18002d54e  js      short loc_18002D569
0x18002d550  movsxd  rax, [rsp+130h+var_DC]
0x18002d555  lea     rcx, [rax+rax*4]
0x18002d559  lea     r12, [r12+rcx*8]
0x18002d55d  add     r12, 28h ; '('
0x18002d561  inc     r14d
0x18002d564  jmp     loc_18002D406
0x18002d569  mov     edx, 2F2h
0x18002d56e  jmp     short loc_18002D589
0x18002d570  mov     edx, 2F1h
0x18002d575  jmp     loc_18002D60F
0x18002d57a  mov     edx, 2EEh
0x18002d57f  jmp     loc_18002D60F
0x18002d584  mov     edx, 2ECh
0x18002d589  mov     r9d, eax
0x18002d58c  jmp     loc_18002D612
0x18002d591  xor     ecx, ecx; bstrString
0x18002d593  call    cs:__imp_SysFreeString
0x18002d59a  nop     dword ptr [rax+rax+00h]
0x18002d59f  nop
0x18002d5a0  xor     ecx, ecx; bstrString
0x18002d5a2  call    cs:__imp_SysFreeString
0x18002d5a9  nop     dword ptr [rax+rax+00h]
0x18002d5ae  nop
0x18002d5af  mov     rcx, [rsp+130h+var_D8]; bstrString
0x18002d5b4  call    cs:__imp_SysFreeString
0x18002d5bb  nop     dword ptr [rax+rax+00h]
0x18002d5c0  nop
0x18002d5c1  lea     rcx, [rsp+130h+var_F8]
0x18002d5c6  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d5cb  nop
0x18002d5cc  lea     rcx, [rsp+130h+var_F0]
0x18002d5d1  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d5d6  nop
0x18002d5d7  lea     rcx, [rsp+130h+var_100]
0x18002d5dc  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d5e1  nop
0x18002d5e2  lea     rcx, [rsp+130h+var_D0]
0x18002d5e7  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d5ec  nop
0x18002d5ed  mov     rcx, rsi
0x18002d5f0  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d5f5  nop
0x18002d5f6  mov     rcx, r15; void *
0x18002d5f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d5fe  xor     eax, eax
0x18002d600  jmp     loc_18002D692
0x18002d605  mov     ebx, 80070057h
0x18002d60a  mov     edx, 2C9h; void *
0x18002d60f  mov     r9d, ebx; char *
0x18002d612  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002d619  mov     rcx, [rbp+57h]; this
0x18002d61d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d622  nop
0x18002d623  xor     ecx, ecx; bstrString
0x18002d625  call    cs:__imp_SysFreeString
0x18002d62c  nop     dword ptr [rax+rax+00h]
0x18002d631  nop
0x18002d632  xor     ecx, ecx; bstrString
0x18002d634  call    cs:__imp_SysFreeString
0x18002d63b  nop     dword ptr [rax+rax+00h]
0x18002d640  nop
0x18002d641  mov     rcx, [rsp+130h+var_D8]; bstrString
0x18002d646  call    cs:__imp_SysFreeString
0x18002d64d  nop     dword ptr [rax+rax+00h]
0x18002d652  nop
0x18002d653  lea     rcx, [rsp+130h+var_F8]
0x18002d658  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d65d  nop
0x18002d65e  lea     rcx, [rsp+130h+var_F0]
0x18002d663  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d668  nop
0x18002d669  lea     rcx, [rsp+130h+var_100]
0x18002d66e  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d673  nop
0x18002d674  lea     rcx, [rsp+130h+var_D0]
0x18002d679  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d67e  nop
0x18002d67f  mov     rcx, rsi
0x18002d682  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d687  nop
0x18002d688  mov     rcx, r15; void *
0x18002d68b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d690  mov     eax, ebx
0x18002d692  mov     rcx, [rbp+4Fh+var_48]
0x18002d696  xor     rcx, rsp; StackCookie
0x18002d699  call    __security_check_cookie
0x18002d69e  add     rsp, 0F8h
0x18002d6a5  pop     r15
0x18002d6a7  pop     r14
0x18002d6a9  pop     r13
0x18002d6ab  pop     r12
0x18002d6ad  pop     rdi
0x18002d6ae  pop     rsi
0x18002d6af  pop     rbx
0x18002d6b0  pop     rbp
0x18002d6b1  retn
```
