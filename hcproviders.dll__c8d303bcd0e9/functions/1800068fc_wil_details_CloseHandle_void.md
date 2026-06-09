# wil::details::CloseHandle(void *)

- ea: `0x1800068fc`
- end: `0x180006926`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006568`
- `0x180008714`

## callees

- `0x1800068fc`
- `0x1800083e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006900`

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
0x1800068fc  sub     rsp, 28h
0x180006900  call    cs:__imp_CloseHandle
0x180006907  nop     dword ptr [rax+rax+00h]
0x18000690c  test    eax, eax
0x18000690e  jnz     short loc_180006920
0x180006910  mov     rcx, [rsp+28h]; this
0x180006915  mov     edx, 0A0Bh; void *
0x18000691a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006920  add     rsp, 28h
0x180006924  retn
```
