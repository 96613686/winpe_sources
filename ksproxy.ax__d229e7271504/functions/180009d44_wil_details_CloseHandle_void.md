# wil::details::CloseHandle(void *)

- ea: `0x180009d44`
- end: `0x180009d75`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007318`
- `0x180008464`
- `0x18001b934`

## callees

- `0x180009d44`
- `0x180025724`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009d48`
- `KERNEL32!CloseHandle` at `0x180009d48`

## string_xrefs

- `0x180009d63`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180009d44  sub     rsp, 28h
0x180009d48  call    cs:__imp_CloseHandle
0x180009d4f  nop     dword ptr [rax+rax+00h]
0x180009d54  test    eax, eax
0x180009d56  jz      short loc_180009D5E
0x180009d58  add     rsp, 28h
0x180009d5c  retn
0x180009d5e  mov     rcx, [rsp+28h]; this
0x180009d63  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009d6a  mov     edx, 0A0Bh; void *
0x180009d6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
