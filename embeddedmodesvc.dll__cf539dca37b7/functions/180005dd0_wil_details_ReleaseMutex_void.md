# wil::details::ReleaseMutex(void *)

- ea: `0x180005dd0`
- end: `0x180005dfa`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044fc`
- `0x180005cfc`

## callees

- `0x180005dd0`
- `0x180006af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005dd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005dd4`

## string_xrefs

- `0x180005de3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180005dd0  sub     rsp, 28h
0x180005dd4  call    cs:__imp_ReleaseMutex
0x180005dda  test    eax, eax
0x180005ddc  jnz     short loc_180005DF5
0x180005dde  mov     rcx, [rsp+28h]; this
0x180005de3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005dea  mov     edx, 0A15h; void *
0x180005def  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005df5  add     rsp, 28h
0x180005df9  retn
```
