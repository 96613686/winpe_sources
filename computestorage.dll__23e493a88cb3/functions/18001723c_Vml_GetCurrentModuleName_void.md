# Vml::GetCurrentModuleName(void)

- ea: `0x18001723c`
- end: `0x18001735c`
- name: `?GetCurrentModuleName@Vml@@YAPEBGXZ`
- size: `288`
- prototype: `const unsigned __int16 *__fastcall(Vml *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800196a8`

## callees

- `0x180002690`
- `0x1800136f8`
- `0x18001723c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800172b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800172b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180017274`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180017274`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017302`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017302`

## string_xrefs

- `0x18001734a`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x180017338`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
const unsigned __int16 *__fastcall Vml::GetCurrentModuleName(Vml *this)
{
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&Vml::Details::g_ModulePathInitOnce, 0, &fPending, 0) )
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
0x18001723c  mov     [rsp+arg_0], rbx
0x180017241  mov     [rsp+arg_8], rsi
0x180017246  push    rdi
0x180017247  sub     rsp, 40h
0x18001724b  mov     rax, cs:__security_cookie
0x180017252  xor     rax, rsp
0x180017255  mov     [rsp+48h+var_10], rax
0x18001725a  xor     ebx, ebx
0x18001725c  mov     [rsp+48h+fPending], ebx
0x180017260  xor     r9d, r9d; lpContext
0x180017263  lea     r8, [rsp+48h+fPending]; fPending
0x180017268  xor     edx, edx; dwFlags
0x18001726a  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x180017271  mov     rcx, rsi; lpInitOnce
0x180017274  call    cs:__imp___std_init_once_begin_initialize
0x18001727b  nop     dword ptr [rax+rax+00h]
0x180017280  mov     rcx, [rsp+48h]; this
0x180017285  test    eax, eax
0x180017287  jz      loc_18001734A
0x18001728d  cmp     [rsp+48h+fPending], ebx
0x180017291  jz      short loc_18001730E
0x180017293  mov     [rsp+48h+var_28], rsi
0x180017298  mov     [rsp+48h+var_20], 4
0x1800172a0  mov     r8d, 104h; nSize
0x1800172a6  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x1800172ad  mov     rdx, rdi; lpFilename
0x1800172b0  lea     rcx, __ImageBase; hModule
0x1800172b7  call    cs:__imp_GetModuleFileNameW
0x1800172be  nop     dword ptr [rax+rax+00h]
0x1800172c3  test    eax, eax
0x1800172c5  jz      short loc_180017333
0x1800172c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800172cb  inc     rax
0x1800172ce  cmp     [rdi+rax*2], bx
0x1800172d2  jnz     short loc_1800172CB
0x1800172d4  test    rax, rax
0x1800172d7  jz      short loc_1800172EF
0x1800172d9  cmp     word ptr [rdi+rax*2-2], 2Fh ; '/'
0x1800172df  jz      short loc_1800172EF
0x1800172e1  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800172e7  jz      short loc_1800172EF
0x1800172e9  sub     rax, 1
0x1800172ed  jnz     short loc_1800172D9
0x1800172ef  lea     rax, [rdi+rax*2]
0x1800172f3  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ModuleName
0x1800172fa  xor     r8d, r8d; lpContext
0x1800172fd  xor     edx, edx; dwFlags
0x1800172ff  mov     rcx, rsi; lpInitOnce
0x180017302  call    cs:__imp_InitOnceComplete
0x180017309  nop     dword ptr [rax+rax+00h]
0x18001730e  mov     rax, cs:?g_ModuleName@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ModuleName
0x180017315  mov     rcx, [rsp+48h+var_10]
0x18001731a  xor     rcx, rsp; StackCookie
0x18001731d  call    __security_check_cookie
0x180017322  mov     rbx, [rsp+48h+arg_0]
0x180017327  mov     rsi, [rsp+48h+arg_8]
0x18001732c  add     rsp, 40h
0x180017330  pop     rdi
0x180017331  retn
0x180017333  mov     rcx, [rsp+48h]; this
0x180017338  lea     r8, aOnecoreVmCommo_4; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x18001733f  mov     edx, 30h ; '0'; void *
0x180017344  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001734a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017351  mov     edx, 3BCh; void *
0x180017356  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
