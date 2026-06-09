# NameFromNetwork

- ea: `0x180042350`
- end: `0x180042598`
- name: `NameFromNetwork`
- size: `584`
- prototype: `__int64 __fastcall(__int64, __int64 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008fc40`

## callees

- `0x180015608`
- `0x180042350`
- `0x1800425a0`
- `0x180043488`
- `0x180043e80`
- `0x18004c5bc`
- `0x180090780`
- `0x1800a88a0`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004256a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004256a`

## string_xrefs

- `0x180042537`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x18004254c`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x180042581`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NameFromNetwork(__int64 a1, __int64 **a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  LPVOID v6; // rax
  void (*v7)(void); // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, LPVOID *, LPVOID *); // r14
  void *v13; // rdi
  int v14; // eax
  int v15; // [rsp+20h] [rbp-50h]
  _QWORD v16[2]; // [rsp+30h] [rbp-40h] BYREF
  LPVOID i; // [rsp+40h] [rbp-30h] BYREF
  int v18; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v20; // [rsp+58h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v16[0] = a1;
  v20 = 0;
  v3 = *a2;
  v4 = **a2;
  v20 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v4 + 128))(v3, 3, &v20);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)(unsigned int)v5,
      v15);
  v6 = 0;
  for ( i = 0; ; v6 = i )
  {
    if ( v6 )
    {
      MidlAllocString(a1, &i);
      if ( i )
        CoTaskMemFree(i);
      if ( v20 )
      {
        v7 = *(void (**)(void))(*v20 + 16);
LABEL_8:
        v7();
        return a1;
      }
      return a1;
    }
    v19 = 0;
    v18 = 0;
    v9 = *v20;
    v19 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, int *))(v9 + 24))(v20, 1, &v19, &v18);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)(unsigned int)v10,
        v15);
    if ( !v18 || v10 == 1 )
      break;
    pv = 0;
    v11 = v19;
    v12 = *(__int64 (__fastcall **)(__int64, LPVOID *, LPVOID *))(*(_QWORD *)v19 + 72LL);
    pv = 0;
    v13 = i;
    if ( i )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v16);
      CoTaskMemFree(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
    }
    i = 0;
    v14 = v12(v11, &i, &pv);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)(unsigned int)v14,
        v15);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  MidlAllocEmptyString(a1);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( i )
    CoTaskMemFree(i);
  if ( v20 )
  {
    v7 = *(void (**)(void))(*v20 + 16);
    goto LABEL_8;
  }
  return a1;
}

```

## disassembly

```asm
0x180042350  mov     [rsp-18h+arg_10], rbx
0x180042355  mov     [rsp-18h+arg_18], rsi
0x18004235a  push    rbp
0x18004235b  push    rdi
0x18004235c  push    r14
0x18004235e  mov     rbp, rsp
0x180042361  sub     rsp, 70h
0x180042365  mov     rax, cs:__security_cookie
0x18004236c  xor     rax, rsp
0x18004236f  mov     [rbp+var_8], rax
0x180042373  mov     rbx, rcx
0x180042376  mov     [rbp+var_40], rcx
0x18004237a  mov     [rbp+var_18], 0
0x180042382  mov     rcx, [rdx]
0x180042385  mov     rax, [rcx]
0x180042388  mov     [rbp+var_18], 0
0x180042390  lea     r8, [rbp+var_18]
0x180042394  mov     edx, 3
0x180042399  mov     rax, [rax+80h]
0x1800423a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423a5  mov     rcx, [rbp+18h]; this
0x1800423a9  test    eax, eax
0x1800423ab  js      loc_180042534
0x1800423b1  xor     eax, eax
0x1800423b3  mov     [rbp+var_30], rax
0x1800423b7  test    rax, rax
0x1800423ba  jz      short loc_180042410
0x1800423bc  lea     rdx, [rbp+var_30]
0x1800423c0  mov     rcx, rbx
0x1800423c3  call    ?MidlAllocString@@YA?AV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MidlAllocString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &)
0x1800423c8  nop
0x1800423c9  mov     rcx, [rbp+var_30]; pv
0x1800423cd  test    rcx, rcx
0x1800423d0  jnz     loc_1800424E1
0x1800423d6  mov     rcx, [rbp+var_18]
0x1800423da  test    rcx, rcx
0x1800423dd  jz      short loc_1800423EC
0x1800423df  mov     rdx, [rcx]
0x1800423e2  mov     rax, [rdx+10h]
0x1800423e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423eb  nop
0x1800423ec  mov     rax, rbx
0x1800423ef  mov     rcx, [rbp+var_8]
0x1800423f3  xor     rcx, rsp; StackCookie
0x1800423f6  call    __security_check_cookie
0x1800423fb  lea     r11, [rsp+70h+var_s0]
0x180042400  mov     rbx, [r11+30h]
0x180042404  mov     rsi, [r11+38h]
0x180042408  mov     rsp, r11
0x18004240b  pop     r14
0x18004240d  pop     rdi
0x18004240e  pop     rbp
0x18004240f  retn
0x180042410  mov     [rbp+var_20], 0
0x180042418  mov     [rbp+var_28], 0
0x18004241f  mov     rcx, [rbp+var_18]
0x180042423  mov     rax, [rcx]
0x180042426  mov     [rbp+var_20], 0
0x18004242e  lea     r9, [rbp+var_28]
0x180042432  lea     r8, [rbp+var_20]
0x180042436  mov     edx, 1
0x18004243b  mov     rax, [rax+18h]
0x18004243f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042444  mov     rcx, [rbp+18h]; this
0x180042448  test    eax, eax
0x18004244a  js      loc_180042549
0x180042450  cmp     [rbp+var_28], 0
0x180042454  jz      loc_1800424EC
0x18004245a  cmp     eax, 1
0x18004245d  jz      loc_1800424EC
0x180042463  mov     [rbp+pv], 0
0x18004246b  mov     rsi, [rbp+var_20]
0x18004246f  mov     rax, [rsi]
0x180042472  mov     r14, [rax+48h]
0x180042476  mov     [rbp+pv], 0
0x18004247e  mov     rdi, [rbp+var_30]
0x180042482  test    rdi, rdi
0x180042485  jnz     loc_18004255E
0x18004248b  mov     [rbp+var_30], 0
0x180042493  lea     r8, [rbp+pv]
0x180042497  lea     rdx, [rbp+var_30]
0x18004249b  mov     rcx, rsi
0x18004249e  mov     rax, r14
0x1800424a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424a6  mov     rcx, [rbp+18h]; this
0x1800424aa  test    eax, eax
0x1800424ac  js      loc_18004257E
0x1800424b2  mov     rcx, [rbp+pv]; pv
0x1800424b6  test    rcx, rcx
0x1800424b9  jz      short loc_1800424C2
0x1800424bb  call    cs:__imp_CoTaskMemFree
0x1800424c1  nop
0x1800424c2  mov     rcx, [rbp+var_20]
0x1800424c6  test    rcx, rcx
0x1800424c9  jz      short loc_1800424D8
0x1800424cb  mov     rax, [rcx]
0x1800424ce  mov     rax, [rax+10h]
0x1800424d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424d7  nop
0x1800424d8  mov     rax, [rbp+var_30]
0x1800424dc  jmp     loc_1800423B7
0x1800424e1  call    cs:__imp_CoTaskMemFree
0x1800424e7  jmp     loc_1800423D6
0x1800424ec  mov     rcx, rbx
0x1800424ef  call    ?MidlAllocEmptyString@@YA?AV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@XZ; MidlAllocEmptyString(void)
0x1800424f4  nop
0x1800424f5  mov     rcx, [rbp+var_20]
0x1800424f9  test    rcx, rcx
0x1800424fc  jz      short loc_18004250B
0x1800424fe  mov     rax, [rcx]
0x180042501  mov     rax, [rax+10h]
0x180042505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004250a  nop
0x18004250b  mov     rcx, [rbp+var_30]; pv
0x18004250f  test    rcx, rcx
0x180042512  jz      short loc_18004251B
0x180042514  call    cs:__imp_CoTaskMemFree
0x18004251a  nop
0x18004251b  mov     rcx, [rbp+var_18]
0x18004251f  test    rcx, rcx
0x180042522  jz      loc_1800423EC
0x180042528  mov     rax, [rcx]
0x18004252b  mov     rax, [rax+10h]
0x18004252f  jmp     loc_1800423E6
0x180042534  mov     r9d, eax; char *
0x180042537  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x18004253e  mov     edx, 0BCh; void *
0x180042543  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042549  mov     r9d, eax; char *
0x18004254c  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180042553  mov     edx, 0C4h; void *
0x180042558  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004255e  lea     rcx, [rbp+var_40]; this
0x180042562  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180042567  mov     rcx, rdi; pv
0x18004256a  call    cs:__imp_CoTaskMemFree
0x180042570  lea     rcx, [rbp+var_40]; this
0x180042574  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180042579  jmp     loc_18004248B
0x18004257e  mov     r9d, eax; char *
0x180042581  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180042588  mov     edx, 0CCh; void *
0x18004258d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042592  jmp     loc_1800424B2
```
