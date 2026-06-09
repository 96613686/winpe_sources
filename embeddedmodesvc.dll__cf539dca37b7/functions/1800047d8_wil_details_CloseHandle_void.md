# wil::details::CloseHandle(void *)

- ea: `0x1800047d8`
- end: `0x180004802`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044e0`
- `0x180006c14`

## callees

- `0x1800047d8`
- `0x180006af4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047dc`

## string_xrefs

- `0x1800047eb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::CloseHandle(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !CloseHandle(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x1800047d8  sub     rsp, 28h
0x1800047dc  call    cs:__imp_CloseHandle
0x1800047e2  test    eax, eax
0x1800047e4  jnz     short loc_1800047FD
0x1800047e6  mov     rcx, [rsp+28h]; this
0x1800047eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800047f2  mov     edx, 0A0Bh; void *
0x1800047f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047fd  add     rsp, 28h
0x180004801  retn
```
