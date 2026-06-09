# wil::details::ReleaseMutex(void *)

- ea: `0x140004940`
- end: `0x140004963`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002f0c`
- `0x14000486c`

## callees

- `0x140004940`
- `0x14000530c`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x140004944`
- `KERNEL32!ReleaseMutex` at `0x140004944`

## pseudocode

```c
void __fastcall wil::details::ReleaseMutex(wil::details *this, void *a2)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ReleaseMutex(this) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v2, v3);
}

```

## disassembly

```asm
0x140004940  sub     rsp, 28h
0x140004944  call    cs:__imp_ReleaseMutex
0x14000494a  test    eax, eax
0x14000494c  jnz     short loc_14000495E
0x14000494e  mov     rcx, [rsp+28h]; this
0x140004953  mov     edx, 0A15h; void *
0x140004958  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000495e  add     rsp, 28h
0x140004962  retn
```
