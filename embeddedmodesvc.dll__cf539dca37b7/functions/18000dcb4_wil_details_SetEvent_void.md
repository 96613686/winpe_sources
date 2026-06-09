# wil::details::SetEvent(void *)

- ea: `0x18000dcb4`
- end: `0x18000dcde`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d480`
- `0x18000d82c`
- `0x18000da64`
- `0x18000e450`
- `0x180011134`

## callees

- `0x180006af4`
- `0x18000dcb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dcb8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dcb8`

## string_xrefs

- `0x18000dcc7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x18000dcb4  sub     rsp, 28h
0x18000dcb8  call    cs:__imp_SetEvent
0x18000dcbe  test    eax, eax
0x18000dcc0  jnz     short loc_18000DCD9
0x18000dcc2  mov     rcx, [rsp+28h]; this
0x18000dcc7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dcce  mov     edx, 0A01h; void *
0x18000dcd3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dcd9  add     rsp, 28h
0x18000dcdd  retn
```
