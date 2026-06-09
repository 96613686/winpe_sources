# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180002d50`
- end: `0x180002db1`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004210`
- `0x1800046c4`

## callees

- `0x180002d50`
- `0x1800055e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d7a`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  __int64 v3; // r8
  const char *v4; // r9
  __int64 v5; // r8
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  }
}

```

## disassembly

```asm
0x180002d50  push    rbx
0x180002d52  sub     rsp, 20h
0x180002d56  mov     rbx, rcx
0x180002d59  mov     rcx, [rcx+8]; hObject
0x180002d5d  test    rcx, rcx
0x180002d60  jz      short loc_180002D72
0x180002d62  call    cs:__imp_CloseHandle
0x180002d69  nop     dword ptr [rax+rax+00h]
0x180002d6e  test    eax, eax
0x180002d70  jz      short loc_180002DA1
0x180002d72  mov     rcx, [rbx]; hObject
0x180002d75  test    rcx, rcx
0x180002d78  jz      short loc_180002D8A
0x180002d7a  call    cs:__imp_CloseHandle
0x180002d81  nop     dword ptr [rax+rax+00h]
0x180002d86  test    eax, eax
0x180002d88  jz      short loc_180002D91
0x180002d8a  add     rsp, 20h
0x180002d8e  pop     rbx
0x180002d8f  retn
0x180002d91  mov     rcx, [rsp+28h]; this
0x180002d96  mov     edx, 0A0Bh; void *
0x180002d9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180002da1  mov     rcx, [rsp+28h]; this
0x180002da6  mov     edx, 0A0Bh; void *
0x180002dab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
