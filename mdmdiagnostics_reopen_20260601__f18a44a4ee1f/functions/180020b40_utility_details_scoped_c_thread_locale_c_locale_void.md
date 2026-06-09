# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180020b40`
- end: `0x180020c33`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800c3960`
- `0x1800c3ac0`
- `0x1800c4bd0`
- `0x1800c6670`

## callees

- `0x1800190a4`
- `0x18001a084`
- `0x1800206e0`
- `0x180020b40`
- `0x1800a9eb8`
- `0x180193010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180020ba7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180020ba7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020beb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020beb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020b5e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020b5e`

## string_xrefs

- `0x180020c0a`: `Unable to create 'C' locale.`

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
    v3 = qword_180241038;
    qword_180241038 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_180241038;
}

```

## disassembly

```asm
0x180020b40  mov     [rsp+arg_8], rbx
0x180020b45  push    rdi
0x180020b46  sub     rsp, 50h
0x180020b4a  xor     r9d, r9d; lpContext
0x180020b4d  lea     r8, [rsp+58h+fPending]; fPending
0x180020b52  xor     edx, edx; dwFlags
0x180020b54  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x180020b5b  mov     rcx, rdi; lpInitOnce
0x180020b5e  call    cs:__imp___std_init_once_begin_initialize
0x180020b64  test    eax, eax
0x180020b66  jnz     short loc_180020B6F
0x180020b68  mov     ecx, 5
0x180020b6d  int     29h; Win8: RtlFailFast(ecx)
0x180020b6f  cmp     [rsp+58h+fPending], 0
0x180020b74  jz      short loc_180020BF5
0x180020b76  mov     [rsp+58h+var_38], rdi
0x180020b7b  mov     [rsp+58h+var_30], 4
0x180020b83  mov     ecx, 8; Size
0x180020b88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020b8d  mov     rbx, rax
0x180020b90  test    rax, rax
0x180020b93  jz      short loc_180020B9C
0x180020b95  xor     eax, eax
0x180020b97  mov     [rbx], rax
0x180020b9a  jmp     short loc_180020B9E
0x180020b9c  xor     ebx, ebx
0x180020b9e  lea     rdx, Locale; "C"
0x180020ba5  xor     ecx, ecx; Category
0x180020ba7  call    cs:__imp__create_locale
0x180020bad  mov     [rbx], rax
0x180020bb0  test    rax, rax
0x180020bb3  jz      short loc_180020C0A
0x180020bb5  mov     rcx, cs:qword_180241038
0x180020bbc  mov     cs:qword_180241038, rbx
0x180020bc3  test    rcx, rcx
0x180020bc6  jz      short loc_180020BD5
0x180020bc8  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180020bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd4  nop
0x180020bd5  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x180020bdc  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180020be3  xor     r8d, r8d; lpContext
0x180020be6  xor     edx, edx; dwFlags
0x180020be8  mov     rcx, rdi; lpInitOnce
0x180020beb  call    cs:__imp_InitOnceComplete
0x180020bf1  test    eax, eax
0x180020bf3  jz      short loc_180020C2D
0x180020bf5  mov     rax, cs:qword_180241038
0x180020bfc  mov     rax, [rax]
0x180020bff  mov     rbx, [rsp+58h+arg_8]
0x180020c04  add     rsp, 50h
0x180020c08  pop     rdi
0x180020c09  retn
0x180020c0a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180020c11  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180020c16  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180020c1b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180020c22  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180020c27  call    _CxxThrowException_0
0x180020c2d  call    __std_init_once_link_alternate_names_and_abort
```
