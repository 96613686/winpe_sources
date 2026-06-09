# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18000a900`
- end: `0x18000a9f3`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006cd0`
- `0x180008ee0`
- `0x18000be00`
- `0x18000bf60`

## callees

- `0x18000335c`
- `0x180003c44`
- `0x18000a880`
- `0x18000a900`
- `0x18000d1e8`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18000a967`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18000a967`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a91e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a91e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a9ab`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a9ab`

## string_xrefs

- `0x18000a9ca`: `Unable to create 'C' locale.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct __crt_locale_pointers *utility::details::scoped_c_thread_locale::c_locale(void)
{
  _locale_t *v0; // rbx
  _locale_t locale; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+60h] [rbp+8h] BYREF

  if ( !__std_init_once_begin_initialize(&utility::details::g_c_localeFlag, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    v0 = (_locale_t *)operator new(8u);
    if ( v0 )
      *v0 = 0;
    else
      v0 = 0;
    locale = _create_locale(0, "C");
    *v0 = locale;
    if ( !locale )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Unable to create 'C' locale.");
      throw (std::runtime_error *)pExceptionObject;
    }
    v3 = qword_18011D018;
    qword_18011D018 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18011D018;
}

```

## disassembly

```asm
0x18000a900  mov     [rsp+arg_8], rbx
0x18000a905  push    rdi
0x18000a906  sub     rsp, 50h
0x18000a90a  xor     r9d, r9d; lpContext
0x18000a90d  lea     r8, [rsp+58h+fPending]; fPending
0x18000a912  xor     edx, edx; dwFlags
0x18000a914  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18000a91b  mov     rcx, rdi; lpInitOnce
0x18000a91e  call    cs:__imp___std_init_once_begin_initialize
0x18000a924  test    eax, eax
0x18000a926  jnz     short loc_18000A92F
0x18000a928  mov     ecx, 5
0x18000a92d  int     29h; Win8: RtlFailFast(ecx)
0x18000a92f  cmp     [rsp+58h+fPending], 0
0x18000a934  jz      short loc_18000A9B5
0x18000a936  mov     [rsp+58h+var_38], rdi
0x18000a93b  mov     [rsp+58h+var_30], 4
0x18000a943  mov     ecx, 8; Size
0x18000a948  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a94d  mov     rbx, rax
0x18000a950  test    rax, rax
0x18000a953  jz      short loc_18000A95C
0x18000a955  xor     eax, eax
0x18000a957  mov     [rbx], rax
0x18000a95a  jmp     short loc_18000A95E
0x18000a95c  xor     ebx, ebx
0x18000a95e  lea     rdx, Locale; "C"
0x18000a965  xor     ecx, ecx; Category
0x18000a967  call    cs:__imp__create_locale
0x18000a96d  mov     [rbx], rax
0x18000a970  test    rax, rax
0x18000a973  jz      short loc_18000A9CA
0x18000a975  mov     rcx, cs:qword_18011D018
0x18000a97c  mov     cs:qword_18011D018, rbx
0x18000a983  test    rcx, rcx
0x18000a986  jz      short loc_18000A995
0x18000a988  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18000a98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a994  nop
0x18000a995  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18000a99c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18000a9a3  xor     r8d, r8d; lpContext
0x18000a9a6  xor     edx, edx; dwFlags
0x18000a9a8  mov     rcx, rdi; lpInitOnce
0x18000a9ab  call    cs:__imp_InitOnceComplete
0x18000a9b1  test    eax, eax
0x18000a9b3  jz      short loc_18000A9ED
0x18000a9b5  mov     rax, cs:qword_18011D018
0x18000a9bc  mov     rax, [rax]
0x18000a9bf  mov     rbx, [rsp+58h+arg_8]
0x18000a9c4  add     rsp, 50h
0x18000a9c8  pop     rdi
0x18000a9c9  retn
0x18000a9ca  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x18000a9d1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000a9d6  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000a9db  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000a9e2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000a9e7  call    _CxxThrowException_0
0x18000a9ed  call    __std_init_once_link_alternate_names_and_abort
```
