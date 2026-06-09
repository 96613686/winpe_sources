# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180032490`
- end: `0x180032583`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018df0`
- `0x180018f50`
- `0x18003a830`
- `0x18003c2d0`

## callees

- `0x18000e46c`
- `0x18000ec30`
- `0x180032490`
- `0x1800579a8`
- `0x1800a6718`
- `0x180101010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800324f7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800324f7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800324ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800324ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003253b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003253b`

## string_xrefs

- `0x18003255a`: `Unable to create 'C' locale.`

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
    v3 = qword_180151070;
    qword_180151070 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_180151070;
}

```

## disassembly

```asm
0x180032490  mov     [rsp+arg_8], rbx
0x180032495  push    rdi
0x180032496  sub     rsp, 50h
0x18003249a  xor     r9d, r9d; lpContext
0x18003249d  lea     r8, [rsp+58h+fPending]; fPending
0x1800324a2  xor     edx, edx; dwFlags
0x1800324a4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x1800324ab  mov     rcx, rdi; lpInitOnce
0x1800324ae  call    cs:__imp___std_init_once_begin_initialize
0x1800324b4  test    eax, eax
0x1800324b6  jnz     short loc_1800324BF
0x1800324b8  mov     ecx, 5
0x1800324bd  int     29h; Win8: RtlFailFast(ecx)
0x1800324bf  cmp     [rsp+58h+fPending], 0
0x1800324c4  jz      short loc_180032545
0x1800324c6  mov     [rsp+58h+var_38], rdi
0x1800324cb  mov     [rsp+58h+var_30], 4
0x1800324d3  mov     ecx, 8; Size
0x1800324d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800324dd  mov     rbx, rax
0x1800324e0  test    rax, rax
0x1800324e3  jz      short loc_1800324EC
0x1800324e5  xor     eax, eax
0x1800324e7  mov     [rbx], rax
0x1800324ea  jmp     short loc_1800324EE
0x1800324ec  xor     ebx, ebx
0x1800324ee  lea     rdx, Locale; "C"
0x1800324f5  xor     ecx, ecx; Category
0x1800324f7  call    cs:__imp__create_locale
0x1800324fd  mov     [rbx], rax
0x180032500  test    rax, rax
0x180032503  jz      short loc_18003255A
0x180032505  mov     rcx, cs:qword_180151070
0x18003250c  mov     cs:qword_180151070, rbx
0x180032513  test    rcx, rcx
0x180032516  jz      short loc_180032525
0x180032518  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18003251f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032524  nop
0x180032525  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18003252c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180032533  xor     r8d, r8d; lpContext
0x180032536  xor     edx, edx; dwFlags
0x180032538  mov     rcx, rdi; lpInitOnce
0x18003253b  call    cs:__imp_InitOnceComplete
0x180032541  test    eax, eax
0x180032543  jz      short loc_18003257D
0x180032545  mov     rax, cs:qword_180151070
0x18003254c  mov     rax, [rax]
0x18003254f  mov     rbx, [rsp+58h+arg_8]
0x180032554  add     rsp, 50h
0x180032558  pop     rdi
0x180032559  retn
0x18003255a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180032561  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180032566  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003256b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180032572  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180032577  call    _CxxThrowException_0
0x18003257d  call    __std_init_once_link_alternate_names_and_abort
```
