# dmstd::DeleteDynamicManagementRegistryTree(ushort const *,ushort const *,ushort const *)

- ea: `0x1800eb2a0`
- end: `0x1800eb699`
- name: `?DeleteDynamicManagementRegistryTree@dmstd@@YAJPEBG00@Z`
- size: `1017`
- prototype: `int(dmstd *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ed290`
- `0x1800ed7e0`
- `0x1800f25f0`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x18000f0c8`
- `0x180019fd8`
- `0x18002031c`
- `0x180020380`
- `0x1800232e4`
- `0x18002390c`
- `0x180025ac0`
- `0x18002d994`
- `0x18002dcc8`
- `0x1800657b8`
- `0x1800878cc`
- `0x1800eb0c0`
- `0x1800eb2a0`
- `0x1800ebc2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800eb53c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800eb53c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb4ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb5ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb4ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eb5ab`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800eb60f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800eb60f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall dmstd::DeleteDynamicManagementRegistryTree(
        dmstd *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  const WCHAR *v15; // rax
  LSTATUS v16; // eax
  signed int v17; // ebx
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  const WCHAR *v22; // rax
  LSTATUS v23; // eax
  unsigned int v24; // ebx
  int phkResult; // [rsp+20h] [rbp-138h]
  HKEY hKey; // [rsp+30h] [rbp-128h] BYREF
  _QWORD v27[3]; // [rsp+38h] [rbp-120h] BYREF
  _BYTE v28[32]; // [rsp+50h] [rbp-108h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-E8h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v31[32]; // [rsp+B0h] [rbp-A8h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-68h] BYREF
  _BYTE v34[32]; // [rsp+110h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  if ( !this )
  {
    v7 = 124;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\helpers.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v7 = 125;
    goto LABEL_3;
  }
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v27);
  v9 = std::wstring::wstring(v33, lpSubKey);
  v10 = std::operator+<unsigned short>(v32, v9, L"\\");
  v11 = std::operator+<unsigned short>(v31, v10, this);
  std::operator+<unsigned short>(v29, v11, L"\\");
  std::wstring::~wstring(v31);
  std::wstring::~wstring(v32);
  std::wstring::~wstring(v33);
  std::wstring::wstring(v28, this);
  std::vector<std::wstring>::push_back(v27, v28);
  std::wstring::~wstring(v28);
  if ( a2 )
  {
    v12 = std::wstring::wstring(v30, L"User");
    v13 = std::operator+<unsigned short>(v34, v12, L"\\");
    v14 = std::operator+<unsigned short>(v28, v13, a2);
    std::wstring::append(v29, v14);
    std::wstring::~wstring(v28);
    std::wstring::~wstring(v34);
    std::wstring::~wstring(v30);
    std::wstring::wstring(v28, L"User");
    std::vector<std::wstring>::push_back(v27, v28);
    std::wstring::~wstring(v28);
    std::wstring::wstring(v28, a2);
  }
  else
  {
    std::wstring::append(v29, L"Device");
    std::wstring::wstring(v28, L"Device");
  }
  std::vector<std::wstring>::push_back(v27, v28);
  std::wstring::~wstring(v28);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x10009u, &hKey);
  v17 = v16;
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  if ( v17 < 0 )
    goto LABEL_18;
  v18 = RegDeleteTreeW(hKey, a3);
  v17 = v18;
  if ( v18 > 0 )
    v17 = (unsigned __int16)v18 | 0x80070000;
  if ( v17 < 0 )
    goto LABEL_18;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v17 = v19;
  if ( v19 > 0 )
    v17 = (unsigned __int16)v19 | 0x80070000;
  if ( v17 >= 0 )
  {
    do
    {
      v21 = lambda_0efc253941f2ee789cd73d41de8d0770_::operator()(v20, v30, v27);
      v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
      v23 = RegDeleteKeyW(hKey, v22);
      v24 = v23;
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0x80070000;
      std::wstring::~wstring(v30);
      std::vector<std::wstring>::pop_back(v27);
    }
    while ( v27[0] != v27[1] && (!v24 || v24 == -2147024894) );
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v29);
    std::vector<std::wstring>::_Tidy(v27);
    return 0;
  }
  else
  {
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v29);
    std::vector<std::wstring>::_Tidy(v27);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x1800eb2a0  push    rbx
0x1800eb2a2  push    rsi
0x1800eb2a3  push    rdi
0x1800eb2a4  sub     rsp, 140h
0x1800eb2ab  mov     rax, cs:__security_cookie
0x1800eb2b2  xor     rax, rsp
0x1800eb2b5  mov     [rsp+158h+var_28], rax
0x1800eb2bd  mov     rsi, r8
0x1800eb2c0  mov     rbx, rdx
0x1800eb2c3  mov     rdi, rcx
0x1800eb2c6  test    rcx, rcx
0x1800eb2c9  jnz     short loc_1800EB2F1
0x1800eb2cb  lea     edx, [rcx+7Ch]; void *
0x1800eb2ce  mov     ebx, 80070057h
0x1800eb2d3  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800eb2da  mov     r9d, ebx; char *
0x1800eb2dd  mov     rcx, [rsp+158h]; this
0x1800eb2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb2ea  mov     eax, ebx
0x1800eb2ec  jmp     loc_1800EB67D
0x1800eb2f1  test    rsi, rsi
0x1800eb2f4  jnz     short loc_1800EB2FB
0x1800eb2f6  lea     edx, [rsi+7Dh]
0x1800eb2f9  jmp     short loc_1800EB2CE
0x1800eb2fb  lea     rcx, [rsp+158h+var_120]
0x1800eb300  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x1800eb305  nop
0x1800eb306  mov     rdx, cs:lpSubKey
0x1800eb30d  lea     rcx, [rsp+158h+var_68]
0x1800eb315  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eb31a  nop
0x1800eb31b  lea     r8, StringValue; "\\"
0x1800eb322  mov     rdx, rax
0x1800eb325  lea     rcx, [rsp+158h+var_88]
0x1800eb32d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800eb332  nop
0x1800eb333  mov     r8, rdi
0x1800eb336  mov     rdx, rax
0x1800eb339  lea     rcx, [rsp+158h+var_A8]
0x1800eb341  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800eb346  nop
0x1800eb347  lea     r8, StringValue; "\\"
0x1800eb34e  mov     rdx, rax
0x1800eb351  lea     rcx, [rsp+158h+var_E8]
0x1800eb356  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800eb35b  nop
0x1800eb35c  lea     rcx, [rsp+158h+var_A8]
0x1800eb364  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb369  nop
0x1800eb36a  lea     rcx, [rsp+158h+var_88]
0x1800eb372  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb377  nop
0x1800eb378  lea     rcx, [rsp+158h+var_68]
0x1800eb380  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb385  mov     rdx, rdi
0x1800eb388  lea     rcx, [rsp+158h+var_108]
0x1800eb38d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eb392  nop
0x1800eb393  lea     rdx, [rsp+158h+var_108]
0x1800eb398  lea     rcx, [rsp+158h+var_120]
0x1800eb39d  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800eb3a2  nop
0x1800eb3a3  lea     rcx, [rsp+158h+var_108]
0x1800eb3a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb3ad  test    rbx, rbx
0x1800eb3b0  jz      loc_1800EB474
0x1800eb3b6  lea     rdx, aUser_0; "User"
0x1800eb3bd  lea     rcx, [rsp+158h+var_C8]
0x1800eb3c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eb3ca  nop
0x1800eb3cb  lea     r8, StringValue; "\\"
0x1800eb3d2  mov     rdx, rax
0x1800eb3d5  lea     rcx, [rsp+158h+var_48]
0x1800eb3dd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800eb3e2  nop
0x1800eb3e3  mov     r8, rbx
0x1800eb3e6  mov     rdx, rax
0x1800eb3e9  lea     rcx, [rsp+158h+var_108]
0x1800eb3ee  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800eb3f3  nop
0x1800eb3f4  mov     rdx, rax
0x1800eb3f7  lea     rcx, [rsp+158h+var_E8]
0x1800eb3fc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800eb401  nop
0x1800eb402  lea     rcx, [rsp+158h+var_108]
0x1800eb407  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb40c  nop
0x1800eb40d  lea     rcx, [rsp+158h+var_48]
0x1800eb415  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb41a  nop
0x1800eb41b  lea     rcx, [rsp+158h+var_C8]
0x1800eb423  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb428  lea     rdx, aUser_0; "User"
0x1800eb42f  lea     rcx, [rsp+158h+var_108]
0x1800eb434  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eb439  nop
0x1800eb43a  lea     rdx, [rsp+158h+var_108]
0x1800eb43f  lea     rcx, [rsp+158h+var_120]
0x1800eb444  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800eb449  nop
0x1800eb44a  lea     rcx, [rsp+158h+var_108]
0x1800eb44f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb454  mov     rdx, rbx
0x1800eb457  lea     rcx, [rsp+158h+var_108]
0x1800eb45c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eb461  nop
0x1800eb462  lea     rdx, [rsp+158h+var_108]
0x1800eb467  lea     rcx, [rsp+158h+var_120]
0x1800eb46c  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800eb471  nop
0x1800eb472  jmp     short loc_1800EB4A7
0x1800eb474  lea     rdx, aDevice; "Device"
0x1800eb47b  lea     rcx, [rsp+158h+var_E8]
0x1800eb480  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800eb485  lea     rdx, aDevice; "Device"
0x1800eb48c  lea     rcx, [rsp+158h+var_108]
0x1800eb491  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eb496  nop
0x1800eb497  lea     rdx, [rsp+158h+var_108]
0x1800eb49c  lea     rcx, [rsp+158h+var_120]
0x1800eb4a1  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800eb4a6  nop
0x1800eb4a7  lea     rcx, [rsp+158h+var_108]
0x1800eb4ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb4b1  mov     [rsp+158h+hKey], 0
0x1800eb4ba  xor     edx, edx
0x1800eb4bc  lea     rcx, [rsp+158h+hKey]
0x1800eb4c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800eb4c6  lea     rcx, [rsp+158h+var_E8]
0x1800eb4cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800eb4d0  mov     rdx, rax; lpSubKey
0x1800eb4d3  lea     rax, [rsp+158h+hKey]
0x1800eb4d8  mov     qword ptr [rsp+158h+phkResult], rax; phkResult
0x1800eb4dd  mov     r9d, 10009h; samDesired
0x1800eb4e3  xor     r8d, r8d; ulOptions
0x1800eb4e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800eb4ed  call    cs:__imp_RegOpenKeyExW
0x1800eb4f4  nop     dword ptr [rax+rax+00h]
0x1800eb4f9  mov     ebx, eax
0x1800eb4fb  mov     edi, 80070000h
0x1800eb500  test    eax, eax
0x1800eb502  jle     short loc_1800EB509
0x1800eb504  movzx   ebx, ax
0x1800eb507  or      ebx, edi
0x1800eb509  test    ebx, ebx
0x1800eb50b  jns     short loc_1800EB534
0x1800eb50d  lea     rcx, [rsp+158h+hKey]
0x1800eb512  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800eb517  nop
0x1800eb518  lea     rcx, [rsp+158h+var_E8]
0x1800eb51d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb522  nop
0x1800eb523  lea     rcx, [rsp+158h+var_120]
0x1800eb528  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800eb52d  mov     eax, ebx
0x1800eb52f  jmp     loc_1800EB67D
0x1800eb534  mov     rdx, rsi; lpSubKey
0x1800eb537  mov     rcx, [rsp+158h+hKey]; hKey
0x1800eb53c  call    cs:__imp_RegDeleteTreeW
0x1800eb543  nop     dword ptr [rax+rax+00h]
0x1800eb548  mov     ebx, eax
0x1800eb54a  test    eax, eax
0x1800eb54c  jle     short loc_1800EB553
0x1800eb54e  movzx   ebx, ax
0x1800eb551  or      ebx, edi
0x1800eb553  test    ebx, ebx
0x1800eb555  jns     short loc_1800EB57E
0x1800eb557  lea     rcx, [rsp+158h+hKey]
0x1800eb55c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800eb561  nop
0x1800eb562  lea     rcx, [rsp+158h+var_E8]
0x1800eb567  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb56c  nop
0x1800eb56d  lea     rcx, [rsp+158h+var_120]
0x1800eb572  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800eb577  mov     eax, ebx
0x1800eb579  jmp     loc_1800EB67D
0x1800eb57e  xor     edx, edx
0x1800eb580  lea     rcx, [rsp+158h+hKey]
0x1800eb585  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800eb58a  lea     rax, [rsp+158h+hKey]
0x1800eb58f  mov     qword ptr [rsp+158h+phkResult], rax; phkResult
0x1800eb594  mov     r9d, 20019h; samDesired
0x1800eb59a  xor     r8d, r8d; ulOptions
0x1800eb59d  mov     rdx, cs:lpSubKey; lpSubKey
0x1800eb5a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800eb5ab  call    cs:__imp_RegOpenKeyExW
0x1800eb5b2  nop     dword ptr [rax+rax+00h]
0x1800eb5b7  mov     ebx, eax
0x1800eb5b9  test    eax, eax
0x1800eb5bb  jle     short loc_1800EB5C2
0x1800eb5bd  movzx   ebx, ax
0x1800eb5c0  or      ebx, edi
0x1800eb5c2  test    ebx, ebx
0x1800eb5c4  jns     short loc_1800EB5ED
0x1800eb5c6  lea     rcx, [rsp+158h+hKey]
0x1800eb5cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800eb5d0  nop
0x1800eb5d1  lea     rcx, [rsp+158h+var_E8]
0x1800eb5d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb5db  nop
0x1800eb5dc  lea     rcx, [rsp+158h+var_120]
0x1800eb5e1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800eb5e6  mov     eax, ebx
0x1800eb5e8  jmp     loc_1800EB67D
0x1800eb5ed  lea     r8, [rsp+158h+var_120]
0x1800eb5f2  lea     rdx, [rsp+158h+var_C8]
0x1800eb5fa  call    _lambda_0efc253941f2ee789cd73d41de8d0770___operator__
0x1800eb5ff  mov     rcx, rax
0x1800eb602  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800eb607  mov     rdx, rax; lpSubKey
0x1800eb60a  mov     rcx, [rsp+158h+hKey]; hKey
0x1800eb60f  call    cs:__imp_RegDeleteKeyW
0x1800eb616  nop     dword ptr [rax+rax+00h]
0x1800eb61b  mov     ebx, eax
0x1800eb61d  test    eax, eax
0x1800eb61f  jle     short loc_1800EB626
0x1800eb621  movzx   ebx, ax
0x1800eb624  or      ebx, edi
0x1800eb626  lea     rcx, [rsp+158h+var_C8]
0x1800eb62e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb633  lea     rcx, [rsp+158h+var_120]
0x1800eb638  call    ?pop_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::pop_back(void)
0x1800eb63d  mov     rax, [rsp+158h+var_118]
0x1800eb642  cmp     [rsp+158h+var_120], rax
0x1800eb647  jz      short loc_1800EB655
0x1800eb649  test    ebx, ebx
0x1800eb64b  jz      short loc_1800EB5ED
0x1800eb64d  cmp     ebx, 80070002h
0x1800eb653  jz      short loc_1800EB5ED
0x1800eb655  lea     rcx, [rsp+158h+hKey]
0x1800eb65a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800eb65f  nop
0x1800eb660  lea     rcx, [rsp+158h+var_E8]
0x1800eb665  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb66a  nop
0x1800eb66b  lea     rcx, [rsp+158h+var_120]
0x1800eb670  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800eb675  xor     eax, eax
0x1800eb677  jmp     short loc_1800EB67D
0x1800eb679  mov     eax, dword ptr [rsp+158h+hKey]
0x1800eb67d  mov     rcx, [rsp+158h+var_28]
0x1800eb685  xor     rcx, rsp; StackCookie
0x1800eb688  call    __security_check_cookie
0x1800eb68d  add     rsp, 140h
0x1800eb694  pop     rdi
0x1800eb695  pop     rsi
0x1800eb696  pop     rbx
0x1800eb697  retn
```
