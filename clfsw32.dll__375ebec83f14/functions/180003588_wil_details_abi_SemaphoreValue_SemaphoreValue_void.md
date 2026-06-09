# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180003588`
- end: `0x1800035e9`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037f4`
- `0x180003ba0`
- `0x180006924`
- `0x180006a90`

## callees

- `0x180003588`
- `0x180007e10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000359a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000359a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035b2`

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
0x180003588  push    rbx
0x18000358a  sub     rsp, 20h
0x18000358e  mov     rbx, rcx
0x180003591  mov     rcx, [rcx+8]; hObject
0x180003595  test    rcx, rcx
0x180003598  jz      short loc_1800035AA
0x18000359a  call    cs:__imp_CloseHandle
0x1800035a1  nop     dword ptr [rax+rax+00h]
0x1800035a6  test    eax, eax
0x1800035a8  jz      short loc_1800035D9
0x1800035aa  mov     rcx, [rbx]; hObject
0x1800035ad  test    rcx, rcx
0x1800035b0  jz      short loc_1800035C2
0x1800035b2  call    cs:__imp_CloseHandle
0x1800035b9  nop     dword ptr [rax+rax+00h]
0x1800035be  test    eax, eax
0x1800035c0  jz      short loc_1800035C9
0x1800035c2  add     rsp, 20h
0x1800035c6  pop     rbx
0x1800035c7  retn
0x1800035c9  mov     rcx, [rsp+28h]; this
0x1800035ce  mov     edx, 0A0Bh; void *
0x1800035d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800035d9  mov     rcx, [rsp+28h]; this
0x1800035de  mov     edx, 0A0Bh; void *
0x1800035e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
