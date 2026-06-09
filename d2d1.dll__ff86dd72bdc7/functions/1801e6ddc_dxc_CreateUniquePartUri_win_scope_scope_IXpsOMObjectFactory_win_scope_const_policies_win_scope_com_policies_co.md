# dxc::CreateUniquePartUri(win_scope::scope<IXpsOMObjectFactory *,win_scope::const_policies<win_scope::com_policies>> const &,wchar_t const *,wchar_t const *)

- ea: `0x1801e6ddc`
- end: `0x1801e6f36`
- name: `?CreateUniquePartUri@dxc@@YA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV?$scope@PEAUIXpsOMObjectFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEB_W1@Z`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1801e6ff8`
- `0x1801ef6e0`

## callees

- `0x1801e6ddc`
- `0x1801edd7c`
- `0x180214888`
- `0x18025b100`
- `0x18025bb98`
- `0x180299298`
- `0x18029a1a8`
- `0x18029b95c`
- `0x18029b988`
- `0x18029b9a4`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801e6e38`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801e6e38`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801e6e6c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801e6e6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall dxc::CreateUniquePartUri(_QWORD *a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r8
  HRESULT v8; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD *); // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  _BYTE v28[32]; // [rsp+30h] [rbp-D0h] BYREF
  GUID pguid; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[254]; // [rsp+62h] [rbp-9Eh] BYREF

  std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(v28);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(v28, v7);
  pguid = 0;
  v8 = CoCreateGuid(&pguid);
  if ( v8 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v8, v9, v10, v11);
  memset_0(&sz, 0, 0x100u);
  v12 = StringFromGUID2(&pguid, &sz, 128);
  if ( v12 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v12, v13, v14, v15);
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)&v31[2 * v16 - 2] );
  std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(v28, v31, v16 - 2);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(v28, L".");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(v28, a4);
  *a1 = 0;
  v17 = *a2;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v17 + 304LL);
  win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
    a1,
    0);
  *a1 = 0;
  v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28, v19, v20, v21);
  v23 = v18(v17, v22, a1);
  if ( v23 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v23, v24, v25, v26);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(v28);
  return a1;
}

```

## disassembly

```asm
0x1801e6ddc  push    rbp
0x1801e6dde  push    rbx
0x1801e6ddf  push    rsi
0x1801e6de0  push    rdi
0x1801e6de1  push    r14
0x1801e6de3  lea     rbp, [rsp-70h]
0x1801e6de8  sub     rsp, 170h
0x1801e6def  mov     rax, cs:__security_cookie
0x1801e6df6  xor     rax, rsp
0x1801e6df9  mov     [rbp+90h+var_30], rax
0x1801e6dfd  mov     rbx, r9
0x1801e6e00  mov     rdi, rdx
0x1801e6e03  mov     rsi, rcx
0x1801e6e06  mov     [rsp+190h+var_168], rcx
0x1801e6e0b  xor     r14d, r14d
0x1801e6e0e  mov     [rsp+190h+var_170], r14d
0x1801e6e13  lea     rcx, [rsp+190h+var_160]
0x1801e6e18  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(void)
0x1801e6e1d  nop
0x1801e6e1e  mov     rdx, r8
0x1801e6e21  lea     rcx, [rsp+190h+var_160]
0x1801e6e26  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAAAEAV12@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(wchar_t const * const)
0x1801e6e2b  xorps   xmm0, xmm0
0x1801e6e2e  movups  xmmword ptr [rsp+190h+pguid.Data1], xmm0
0x1801e6e33  lea     rcx, [rsp+190h+pguid]; pguid
0x1801e6e38  call    cs:__imp_CoCreateGuid
0x1801e6e3e  test    eax, eax
0x1801e6e40  jns     short loc_1801E6E4A
0x1801e6e42  mov     ecx, eax; this
0x1801e6e44  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e6e4a  xor     edx, edx; Val
0x1801e6e4c  mov     r8d, 100h; Size
0x1801e6e52  lea     rcx, [rsp+190h+sz]; void *
0x1801e6e57  call    memset_0
0x1801e6e5c  mov     r8d, 80h; cchMax
0x1801e6e62  lea     rdx, [rsp+190h+sz]; lpsz
0x1801e6e67  lea     rcx, [rsp+190h+pguid]; rguid
0x1801e6e6c  call    cs:__imp_StringFromGUID2
0x1801e6e72  test    eax, eax
0x1801e6e74  jns     short loc_1801E6E7E
0x1801e6e76  mov     ecx, eax; this
0x1801e6e78  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e6e7e  lea     rax, [rsp+190h+sz]
0x1801e6e83  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801e6e87  inc     r8
0x1801e6e8a  cmp     [rax+r8*2], r14w
0x1801e6e8f  jnz     short loc_1801E6E87
0x1801e6e91  add     r8, 0FFFFFFFFFFFFFFFEh
0x1801e6e95  lea     rdx, [rsp+190h+var_12E]
0x1801e6e9a  lea     rcx, [rsp+190h+var_160]
0x1801e6e9f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(wchar_t const * const,unsigned __int64)
0x1801e6ea4  lea     rdx, asc_18056CB04; "."
0x1801e6eab  lea     rcx, [rsp+190h+var_160]
0x1801e6eb0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAAAEAV12@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(wchar_t const * const)
0x1801e6eb5  mov     rdx, rbx
0x1801e6eb8  lea     rcx, [rsp+190h+var_160]
0x1801e6ebd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAAAEAV12@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::append(wchar_t const * const)
0x1801e6ec2  mov     [rsi], r14
0x1801e6ec5  mov     [rsp+190h+var_170], 1
0x1801e6ecd  mov     rdi, [rdi]
0x1801e6ed0  mov     rax, [rdi]
0x1801e6ed3  mov     rbx, [rax+130h]
0x1801e6eda  xor     edx, edx
0x1801e6edc  mov     rcx, rsi
0x1801e6edf  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801e6ee4  mov     [rsi], r14
0x1801e6ee7  lea     rcx, [rsp+190h+var_160]
0x1801e6eec  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1801e6ef1  mov     rdx, rax
0x1801e6ef4  mov     r8, rsi
0x1801e6ef7  mov     rcx, rdi
0x1801e6efa  mov     rax, rbx
0x1801e6efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6f02  test    eax, eax
0x1801e6f04  jns     short loc_1801E6F0E
0x1801e6f06  mov     ecx, eax; this
0x1801e6f08  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e6f0e  lea     rcx, [rsp+190h+var_160]
0x1801e6f13  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(void)
0x1801e6f18  mov     rax, rsi
0x1801e6f1b  mov     rcx, [rbp+90h+var_30]
0x1801e6f1f  xor     rcx, rsp; StackCookie
0x1801e6f22  call    __security_check_cookie
0x1801e6f27  add     rsp, 170h
0x1801e6f2e  pop     r14
0x1801e6f30  pop     rdi
0x1801e6f31  pop     rsi
0x1801e6f32  pop     rbx
0x1801e6f33  pop     rbp
0x1801e6f34  retn
```
