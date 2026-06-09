# wil::details::ResetEvent(void *)

- ea: `0x18000dc84`
- end: `0x18000dcae`
- name: `?ResetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000da64`
- `0x18000de50`
- `0x18000e450`
- `0x1800114f0`

## callees

- `0x180006af4`
- `0x18000dc84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000dc88`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000dc88`

## string_xrefs

- `0x18000dc97`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::ResetEvent(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ResetEvent(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x18000dc84  sub     rsp, 28h
0x18000dc88  call    cs:__imp_ResetEvent
0x18000dc8e  test    eax, eax
0x18000dc90  jnz     short loc_18000DCA9
0x18000dc92  mov     rcx, [rsp+28h]; this
0x18000dc97  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dc9e  mov     edx, 0A06h; void *
0x18000dca3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dca9  add     rsp, 28h
0x18000dcad  retn
```
