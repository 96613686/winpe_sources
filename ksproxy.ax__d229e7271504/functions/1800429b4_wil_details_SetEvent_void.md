# wil::details::SetEvent(void *)

- ea: `0x1800429b4`
- end: `0x1800429e5`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076b4`
- `0x18001ca10`
- `0x18004369c`

## callees

- `0x180025724`
- `0x1800429b4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800429b8`
- `KERNEL32!SetEvent` at `0x1800429b8`

## string_xrefs

- `0x1800429cd`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall wil::details::SetEvent(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetEvent(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x1800429b4  sub     rsp, 28h
0x1800429b8  call    cs:__imp_SetEvent
0x1800429bf  nop     dword ptr [rax+rax+00h]
0x1800429c4  test    eax, eax
0x1800429c6  jnz     short loc_1800429DF
0x1800429c8  mov     rcx, [rsp+28h]; this
0x1800429cd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800429d4  mov     edx, 0A01h; void *
0x1800429d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800429df  add     rsp, 28h
0x1800429e3  retn
```
