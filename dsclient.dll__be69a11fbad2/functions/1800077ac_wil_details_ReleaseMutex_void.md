# wil::details::ReleaseMutex(void *)

- ea: `0x1800077ac`
- end: `0x1800077cf`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022b0`
- `0x1800049b8`
- `0x180008e64`

## callees

- `0x1800077ac`
- `0x180008aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077b0`

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
0x1800077ac  sub     rsp, 28h
0x1800077b0  call    cs:__imp_ReleaseMutex
0x1800077b6  test    eax, eax
0x1800077b8  jnz     short loc_1800077CA
0x1800077ba  mov     rcx, [rsp+28h]; this
0x1800077bf  mov     edx, 0A15h; void *
0x1800077c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077ca  add     rsp, 28h
0x1800077ce  retn
```
