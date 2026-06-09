# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x14000c490`
- end: `0x14000c583`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140008ef0`
- `0x14000a820`
- `0x14000bc80`
- `0x14000bde0`

## callees

- `0x140002f84`
- `0x140003b64`
- `0x14000c490`
- `0x14000cea8`
- `0x14001ec04`
- `0x14003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x14000c4f7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x14000c4f7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000c53b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000c53b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000c4ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000c4ae`

## string_xrefs

- `0x14000c55a`: `Unable to create 'C' locale.`

## pseudocode

```c
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
    v3 = qword_140075038;
    qword_140075038 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_140075038;
}

```

## disassembly

```asm
0x14000c490  mov     [rsp+arg_8], rbx
0x14000c495  push    rdi
0x14000c496  sub     rsp, 50h
0x14000c49a  xor     r9d, r9d; lpContext
0x14000c49d  lea     r8, [rsp+58h+fPending]; fPending
0x14000c4a2  xor     edx, edx; dwFlags
0x14000c4a4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x14000c4ab  mov     rcx, rdi; lpInitOnce
0x14000c4ae  call    cs:__imp___std_init_once_begin_initialize
0x14000c4b4  test    eax, eax
0x14000c4b6  jnz     short loc_14000C4BF
0x14000c4b8  mov     ecx, 5
0x14000c4bd  int     29h; Win8: RtlFailFast(ecx)
0x14000c4bf  cmp     [rsp+58h+fPending], 0
0x14000c4c4  jz      short loc_14000C545
0x14000c4c6  mov     [rsp+58h+var_38], rdi
0x14000c4cb  mov     [rsp+58h+var_30], 4
0x14000c4d3  mov     ecx, 8; Size
0x14000c4d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c4dd  mov     rbx, rax
0x14000c4e0  test    rax, rax
0x14000c4e3  jz      short loc_14000C4EC
0x14000c4e5  xor     eax, eax
0x14000c4e7  mov     [rbx], rax
0x14000c4ea  jmp     short loc_14000C4EE
0x14000c4ec  xor     ebx, ebx
0x14000c4ee  lea     rdx, Locale; "C"
0x14000c4f5  xor     ecx, ecx; Category
0x14000c4f7  call    cs:__imp__create_locale
0x14000c4fd  mov     [rbx], rax
0x14000c500  test    rax, rax
0x14000c503  jz      short loc_14000C55A
0x14000c505  mov     rcx, cs:qword_140075038
0x14000c50c  mov     cs:qword_140075038, rbx
0x14000c513  test    rcx, rcx
0x14000c516  jz      short loc_14000C525
0x14000c518  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x14000c51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c524  nop
0x14000c525  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x14000c52c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x14000c533  xor     r8d, r8d; lpContext
0x14000c536  xor     edx, edx; dwFlags
0x14000c538  mov     rcx, rdi; lpInitOnce
0x14000c53b  call    cs:__imp_InitOnceComplete
0x14000c541  test    eax, eax
0x14000c543  jz      short loc_14000C57D
0x14000c545  mov     rax, cs:qword_140075038
0x14000c54c  mov     rax, [rax]
0x14000c54f  mov     rbx, [rsp+58h+arg_8]
0x14000c554  add     rsp, 50h
0x14000c558  pop     rdi
0x14000c559  retn
0x14000c55a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x14000c561  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14000c566  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14000c56b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14000c572  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14000c577  call    _CxxThrowException_0
0x14000c57d  call    __std_init_once_link_alternate_names_and_abort
```
