# RateLimiter::New(wistd::unique_ptr<RateLimiterStrategy,wistd::default_delete<RateLimiterStrategy>>)

- ea: `0x180017614`
- end: `0x18001772e`
- name: `?New@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@V?$unique_ptr@VRateLimiterStrategy@@U?$default_delete@VRateLimiterStrategy@@@wistd@@@3@@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017328`

## callees

- `0x18000be40`
- `0x18000c24c`
- `0x180012124`
- `0x180017614`
- `0x180017928`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017696`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176a4`

## pseudocode

```c
_QWORD *__fastcall RateLimiter::New(_QWORD *a1, void (__fastcall ****a2)(_QWORD, __int64))
{
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  _QWORD *v5; // r14
  void (__fastcall ***v6)(_QWORD, __int64); // rax
  HANDLE Mutex; // rbp
  _QWORD *v9; // [rsp+20h] [rbp-38h] BYREF

  if ( !*a2 )
  {
    *a1 = 0;
    v4 = *a2;
    *a2 = 0;
    goto LABEL_3;
  }
  v5 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v6 = *a2;
    *a2 = 0;
    *v5 = v6;
    v5[1] = 0;
    v9 = v5;
    Mutex = CreateMutexExW(0, 0, 0, 0x1F0001u);
    if ( Mutex
      && (GetLastError(),
          _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
            v5 + 1,
            Mutex),
          v5[1]) )
    {
      v9 = 0;
      *a1 = v5;
    }
    else
    {
      *a1 = 0;
    }
    wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v9, 0);
    v4 = *a2;
    *a2 = 0;
LABEL_3:
    if ( v4 )
      goto LABEL_12;
    return a1;
  }
  v9 = 0;
  *a1 = 0;
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v9, 0);
  v4 = *a2;
  *a2 = 0;
  if ( v4 )
LABEL_12:
    (**v4)(v4, 1);
  return a1;
}

```

## disassembly

```asm
0x180017614  mov     [rsp+arg_10], rbx
0x180017619  push    rbp
0x18001761a  push    rsi
0x18001761b  push    rdi
0x18001761c  push    r14
0x18001761e  push    r15
0x180017620  sub     rsp, 30h
0x180017624  mov     rax, cs:__security_cookie
0x18001762b  xor     rax, rsp
0x18001762e  mov     [rsp+58h+var_30], rax
0x180017633  xor     r15d, r15d
0x180017636  mov     rdi, rdx
0x180017639  mov     rsi, rcx
0x18001763c  cmp     [rdx], r15
0x18001763f  jnz     short loc_18001765E
0x180017641  mov     [rcx], r15
0x180017644  mov     rcx, [rdx]
0x180017647  mov     [rdx], r15
0x18001764a  test    rcx, rcx
0x18001764d  jz      loc_18001770D
0x180017653  mov     rax, [rcx]
0x180017656  mov     rax, [rax]
0x180017659  jmp     loc_180017703
0x18001765e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017665  mov     ecx, 10h; unsigned __int64
0x18001766a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001766f  xor     edx, edx; lpName
0x180017671  mov     r14, rax
0x180017674  test    rax, rax
0x180017677  jz      short loc_1800176E0
0x180017679  mov     rax, [rdi]
0x18001767c  mov     r9d, 1F0001h; dwDesiredAccess
0x180017682  mov     [rdi], r15
0x180017685  xor     r8d, r8d; dwFlags
0x180017688  xor     ecx, ecx; lpMutexAttributes
0x18001768a  mov     [r14], rax
0x18001768d  mov     [r14+8], r15
0x180017691  mov     [rsp+58h+var_38], r14
0x180017696  call    cs:__imp_CreateMutexExW
0x18001769c  mov     rbp, rax
0x18001769f  test    rax, rax
0x1800176a2  jz      short loc_1800176DB
0x1800176a4  call    cs:__imp_GetLastError
0x1800176aa  mov     rdx, rbp
0x1800176ad  lea     rcx, [r14+8]
0x1800176b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800176b6  cmp     [r14+8], r15
0x1800176ba  jz      short loc_1800176DB
0x1800176bc  mov     [rsp+58h+var_38], r15
0x1800176c1  mov     [rsi], r14
0x1800176c4  xor     edx, edx
0x1800176c6  lea     rcx, [rsp+58h+var_38]
0x1800176cb  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x1800176d0  mov     rcx, [rdi]
0x1800176d3  mov     [rdi], r15
0x1800176d6  jmp     loc_18001764A
0x1800176db  mov     [rsi], r15
0x1800176de  jmp     short loc_1800176C4
0x1800176e0  lea     rcx, [rsp+58h+var_38]
0x1800176e5  mov     [rsp+58h+var_38], r15
0x1800176ea  mov     [rsi], r15
0x1800176ed  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x1800176f2  mov     rcx, [rdi]
0x1800176f5  mov     [rdi], r15
0x1800176f8  test    rcx, rcx
0x1800176fb  jz      short loc_18001770D
0x1800176fd  mov     rdx, [rcx]
0x180017700  mov     rax, [rdx]
0x180017703  mov     edx, 1
0x180017708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001770d  mov     rax, rsi
0x180017710  mov     rcx, [rsp+58h+var_30]
0x180017715  xor     rcx, rsp; StackCookie
0x180017718  call    __security_check_cookie
0x18001771d  mov     rbx, [rsp+58h+arg_10]
0x180017722  add     rsp, 30h
0x180017726  pop     r15
0x180017728  pop     r14
0x18001772a  pop     rdi
0x18001772b  pop     rsi
0x18001772c  pop     rbp
0x18001772d  retn
```
