# wil::details::SetEvent(void *)

- ea: `0x18001d674`
- end: `0x18001d69e`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b1f0`
- `0x180036610`
- `0x180036780`

## callees

- `0x18000cfe8`
- `0x18001d674`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d678`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d678`

## string_xrefs

- `0x18001d687`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x18001d674  sub     rsp, 28h
0x18001d678  call    cs:__imp_SetEvent
0x18001d67e  test    eax, eax
0x18001d680  jnz     short loc_18001D699
0x18001d682  mov     rcx, [rsp+28h]; this
0x18001d687  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d68e  mov     edx, 0A01h; void *
0x18001d693  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d699  add     rsp, 28h
0x18001d69d  retn
```
