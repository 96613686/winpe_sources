# Vml::GetCurrentModuleName(void)

- ea: `0x18000c1f0`
- end: `0x18000c2fd`
- name: `?GetCurrentModuleName@Vml@@YAPEBGXZ`
- size: `269`
- prototype: `const unsigned __int16 *__fastcall(Vml *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b0fc`
- `0x18000b9ac`

## callees

- `0x1800067c0`
- `0x18000c1f0`
- `0x18001017c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c265`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c265`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c228`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c228`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c2aa`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c2aa`

## string_xrefs

- `0x18000c2eb`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x18000c2d9`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const unsigned __int16 *__fastcall Vml::GetCurrentModuleName(Vml *this)
{
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&Vml::Details::g_ModulePathInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      v1);
  if ( fPending )
  {
    if ( !GetModuleFileNameW(&_ImageBase, &Vml::Details::g_ModulePath, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModuleUtils.h",
        v2);
    v3 = -1;
    do
      ++v3;
    while ( *(&Vml::Details::g_ModulePath + v3) );
    for ( ; v3; --v3 )
    {
      if ( *(&Vml::Details::g_ModulePath + v3 - 1) == 47 )
        break;
      if ( *(&Vml::Details::g_ModulePath + v3 - 1) == 92 )
        break;
    }
    Vml::Details::g_ModuleName = &Vml::Details::g_ModulePath + v3;
    InitOnceComplete(&Vml::Details::g_ModulePathInitOnce, 0, 0);
  }
  return Vml::Details::g_ModuleName;
}

```

## disassembly

```asm
0x18000c1f0  mov     [rsp+arg_0], rbx
0x18000c1f5  mov     [rsp+arg_8], rsi
0x18000c1fa  push    rdi
0x18000c1fb  sub     rsp, 40h
0x18000c1ff  mov     rax, cs:__security_cookie
0x18000c206  xor     rax, rsp
0x18000c209  mov     [rsp+48h+var_10], rax
0x18000c20e  xor     ebx, ebx
0x18000c210  mov     [rsp+48h+fPending], ebx
0x18000c214  xor     r9d, r9d; lpContext
0x18000c217  lea     r8, [rsp+48h+fPending]; fPending
0x18000c21c  xor     edx, edx; dwFlags
0x18000c21e  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x18000c225  mov     rcx, rsi; lpInitOnce
0x18000c228  call    cs:__imp_InitOnceBeginInitialize
0x18000c22e  mov     rcx, [rsp+48h]; this
0x18000c233  test    eax, eax
0x18000c235  jz      loc_18000C2EB
0x18000c23b  cmp     [rsp+48h+fPending], ebx
0x18000c23f  jz      short loc_18000C2B0
0x18000c241  mov     [rsp+48h+var_28], rsi
0x18000c246  mov     [rsp+48h+var_20], 4
0x18000c24e  mov     r8d, 104h; nSize
0x18000c254  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x18000c25b  mov     rdx, rdi; lpFilename
0x18000c25e  lea     rcx, __ImageBase; hModule
0x18000c265  call    cs:__imp_GetModuleFileNameW
0x18000c26b  test    eax, eax
0x18000c26d  jz      short loc_18000C2D4
0x18000c26f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c273  inc     rax
0x18000c276  cmp     [rdi+rax*2], bx
0x18000c27a  jnz     short loc_18000C273
0x18000c27c  test    rax, rax
0x18000c27f  jz      short loc_18000C297
0x18000c281  cmp     word ptr [rdi+rax*2-2], 2Fh ; '/'
0x18000c287  jz      short loc_18000C297
0x18000c289  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18000c28f  jz      short loc_18000C297
0x18000c291  sub     rax, 1
0x18000c295  jnz     short loc_18000C281
0x18000c297  lea     rax, [rdi+rax*2]
0x18000c29b  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ModuleName
0x18000c2a2  xor     r8d, r8d; lpContext
0x18000c2a5  xor     edx, edx; dwFlags
0x18000c2a7  mov     rcx, rsi; lpInitOnce
0x18000c2aa  call    cs:__imp_InitOnceComplete
0x18000c2b0  mov     rax, cs:?g_ModuleName@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ModuleName
0x18000c2b7  mov     rcx, [rsp+48h+var_10]
0x18000c2bc  xor     rcx, rsp; StackCookie
0x18000c2bf  call    __security_check_cookie
0x18000c2c4  mov     rbx, [rsp+48h+arg_0]
0x18000c2c9  mov     rsi, [rsp+48h+arg_8]
0x18000c2ce  add     rsp, 40h
0x18000c2d2  pop     rdi
0x18000c2d3  retn
0x18000c2d4  mov     rcx, [rsp+48h]; this
0x18000c2d9  lea     r8, aOnecoreVmCommo_29; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x18000c2e0  mov     edx, 30h ; '0'; void *
0x18000c2e5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000c2eb  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c2f2  mov     edx, 3BCh; void *
0x18000c2f7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
