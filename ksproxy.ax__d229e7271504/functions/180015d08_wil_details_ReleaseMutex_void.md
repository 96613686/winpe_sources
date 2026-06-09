# wil::details::ReleaseMutex(void *)

- ea: `0x180015d08`
- end: `0x180015d39`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006e3c`
- `0x180008464`
- `0x18001cea8`

## callees

- `0x180015d08`
- `0x180025724`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180015d0c`
- `KERNEL32!ReleaseMutex` at `0x180015d0c`

## string_xrefs

- `0x180015d27`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180015d08  sub     rsp, 28h
0x180015d0c  call    cs:__imp_ReleaseMutex
0x180015d13  nop     dword ptr [rax+rax+00h]
0x180015d18  test    eax, eax
0x180015d1a  jz      short loc_180015D22
0x180015d1c  add     rsp, 28h
0x180015d20  retn
0x180015d22  mov     rcx, [rsp+28h]; this
0x180015d27  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015d2e  mov     edx, 0A15h; void *
0x180015d33  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
