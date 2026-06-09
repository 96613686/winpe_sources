# wil::details::CloseHandle(void *)

- ea: `0x14000310c`
- end: `0x14000312f`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ef0`
- `0x1400053e0`

## callees

- `0x14000310c`
- `0x14000530c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140003110`
- `KERNEL32!CloseHandle` at `0x140003110`

## pseudocode

```c
void __fastcall wil::details::CloseHandle(wil::details *this, void *a2)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !CloseHandle(this) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v2, v3);
}

```

## disassembly

```asm
0x14000310c  sub     rsp, 28h
0x140003110  call    cs:__imp_CloseHandle
0x140003116  test    eax, eax
0x140003118  jnz     short loc_14000312A
0x14000311a  mov     rcx, [rsp+28h]; this
0x14000311f  mov     edx, 0A0Bh; void *
0x140003124  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000312a  add     rsp, 28h
0x14000312e  retn
```
