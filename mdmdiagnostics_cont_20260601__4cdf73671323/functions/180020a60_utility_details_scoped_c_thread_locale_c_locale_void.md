# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180020a60`
- end: `0x180020b53`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800c37c0`
- `0x1800c3920`
- `0x1800c4a30`
- `0x1800c64d0`

## callees

- `0x180019024`
- `0x180019ff4`
- `0x180020600`
- `0x180020a60`
- `0x1800a9d18`
- `0x180191010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180020ac7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180020ac7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020b0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020b0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020a7e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020a7e`

## string_xrefs

- `0x180020b2a`: `Unable to create 'C' locale.`

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
    v3 = qword_18023F038;
    qword_18023F038 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18023F038;
}

```

## disassembly

```asm
0x180020a60  mov     [rsp+arg_8], rbx
0x180020a65  push    rdi
0x180020a66  sub     rsp, 50h
0x180020a6a  xor     r9d, r9d; lpContext
0x180020a6d  lea     r8, [rsp+58h+fPending]; fPending
0x180020a72  xor     edx, edx; dwFlags
0x180020a74  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x180020a7b  mov     rcx, rdi; lpInitOnce
0x180020a7e  call    cs:__imp___std_init_once_begin_initialize
0x180020a84  test    eax, eax
0x180020a86  jnz     short loc_180020A8F
0x180020a88  mov     ecx, 5
0x180020a8d  int     29h; Win8: RtlFailFast(ecx)
0x180020a8f  cmp     [rsp+58h+fPending], 0
0x180020a94  jz      short loc_180020B15
0x180020a96  mov     [rsp+58h+var_38], rdi
0x180020a9b  mov     [rsp+58h+var_30], 4
0x180020aa3  mov     ecx, 8; Size
0x180020aa8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020aad  mov     rbx, rax
0x180020ab0  test    rax, rax
0x180020ab3  jz      short loc_180020ABC
0x180020ab5  xor     eax, eax
0x180020ab7  mov     [rbx], rax
0x180020aba  jmp     short loc_180020ABE
0x180020abc  xor     ebx, ebx
0x180020abe  lea     rdx, Locale; "C"
0x180020ac5  xor     ecx, ecx; Category
0x180020ac7  call    cs:__imp__create_locale
0x180020acd  mov     [rbx], rax
0x180020ad0  test    rax, rax
0x180020ad3  jz      short loc_180020B2A
0x180020ad5  mov     rcx, cs:qword_18023F038
0x180020adc  mov     cs:qword_18023F038, rbx
0x180020ae3  test    rcx, rcx
0x180020ae6  jz      short loc_180020AF5
0x180020ae8  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180020aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020af4  nop
0x180020af5  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x180020afc  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180020b03  xor     r8d, r8d; lpContext
0x180020b06  xor     edx, edx; dwFlags
0x180020b08  mov     rcx, rdi; lpInitOnce
0x180020b0b  call    cs:__imp_InitOnceComplete
0x180020b11  test    eax, eax
0x180020b13  jz      short loc_180020B4D
0x180020b15  mov     rax, cs:qword_18023F038
0x180020b1c  mov     rax, [rax]
0x180020b1f  mov     rbx, [rsp+58h+arg_8]
0x180020b24  add     rsp, 50h
0x180020b28  pop     rdi
0x180020b29  retn
0x180020b2a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180020b31  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180020b36  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180020b3b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180020b42  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180020b47  call    _CxxThrowException_0
0x180020b4d  call    __std_init_once_link_alternate_names_and_abort
```
