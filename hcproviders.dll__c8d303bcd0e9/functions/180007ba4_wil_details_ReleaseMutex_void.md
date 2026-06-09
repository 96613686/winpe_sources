# wil::details::ReleaseMutex(void *)

- ea: `0x180007ba4`
- end: `0x180007bce`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004914`
- `0x180006588`

## callees

- `0x180007ba4`
- `0x1800083e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ba8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ba8`

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
0x180007ba4  sub     rsp, 28h
0x180007ba8  call    cs:__imp_ReleaseMutex
0x180007baf  nop     dword ptr [rax+rax+00h]
0x180007bb4  test    eax, eax
0x180007bb6  jnz     short loc_180007BC8
0x180007bb8  mov     rcx, [rsp+28h]; this
0x180007bbd  mov     edx, 0A15h; void *
0x180007bc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bc8  add     rsp, 28h
0x180007bcc  retn
```
