# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1800098a0`
- end: `0x180009901`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac68`
- `0x18000b120`

## callees

- `0x1800098a0`
- `0x18000bd6c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098ca`

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
0x1800098a0  push    rbx
0x1800098a2  sub     rsp, 20h
0x1800098a6  mov     rbx, rcx
0x1800098a9  mov     rcx, [rcx+8]; hObject
0x1800098ad  test    rcx, rcx
0x1800098b0  jz      short loc_1800098C2
0x1800098b2  call    cs:__imp_CloseHandle
0x1800098b9  nop     dword ptr [rax+rax+00h]
0x1800098be  test    eax, eax
0x1800098c0  jz      short loc_1800098F1
0x1800098c2  mov     rcx, [rbx]; hObject
0x1800098c5  test    rcx, rcx
0x1800098c8  jz      short loc_1800098DA
0x1800098ca  call    cs:__imp_CloseHandle
0x1800098d1  nop     dword ptr [rax+rax+00h]
0x1800098d6  test    eax, eax
0x1800098d8  jz      short loc_1800098E1
0x1800098da  add     rsp, 20h
0x1800098de  pop     rbx
0x1800098df  retn
0x1800098e1  mov     rcx, [rsp+28h]; this
0x1800098e6  mov     edx, 0A0Bh; void *
0x1800098eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098f1  mov     rcx, [rsp+28h]; this
0x1800098f6  mov     edx, 0A0Bh; void *
0x1800098fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
