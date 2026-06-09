# wil::details::ReleaseMutex(void *)

- ea: `0x18000c26c`
- end: `0x18000c296`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa70`
- `0x18000d168`

## callees

- `0x18000c26c`
- `0x18000cfe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c270`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c270`

## string_xrefs

- `0x18000c27f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::ReleaseMutex(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ReleaseMutex(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x18000c26c  sub     rsp, 28h
0x18000c270  call    cs:__imp_ReleaseMutex
0x18000c276  test    eax, eax
0x18000c278  jnz     short loc_18000C291
0x18000c27a  mov     rcx, [rsp+28h]; this
0x18000c27f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c286  mov     edx, 0A15h; void *
0x18000c28b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c291  add     rsp, 28h
0x18000c295  retn
```
