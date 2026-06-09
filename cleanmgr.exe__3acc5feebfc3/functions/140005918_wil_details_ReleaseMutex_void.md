# wil::details::ReleaseMutex(void *)

- ea: `0x140005918`
- end: `0x140005942`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004108`
- `0x1400066e8`

## callees

- `0x140005918`
- `0x140006574`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000591c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000591c`

## string_xrefs

- `0x14000592b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140005918  sub     rsp, 28h
0x14000591c  call    cs:__imp_ReleaseMutex
0x140005922  test    eax, eax
0x140005924  jnz     short loc_14000593D
0x140005926  mov     rcx, [rsp+28h]; this
0x14000592b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005932  mov     edx, 0A15h; void *
0x140005937  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000593d  add     rsp, 28h
0x140005941  retn
```
