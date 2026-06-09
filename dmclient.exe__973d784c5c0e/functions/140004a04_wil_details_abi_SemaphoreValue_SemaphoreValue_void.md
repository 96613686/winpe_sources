# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x140004a04`
- end: `0x140004a65`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ce4`
- `0x14000ae34`
- `0x140015fb4`
- `0x140017c4c`

## callees

- `0x140004a04`
- `0x14000bfd4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004a2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004a2e`

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
0x140004a04  push    rbx
0x140004a06  sub     rsp, 20h
0x140004a0a  mov     rbx, rcx
0x140004a0d  mov     rcx, [rcx+8]; hObject
0x140004a11  test    rcx, rcx
0x140004a14  jz      short loc_140004A26
0x140004a16  call    cs:__imp_CloseHandle
0x140004a1d  nop     dword ptr [rax+rax+00h]
0x140004a22  test    eax, eax
0x140004a24  jz      short loc_140004A55
0x140004a26  mov     rcx, [rbx]; hObject
0x140004a29  test    rcx, rcx
0x140004a2c  jz      short loc_140004A3E
0x140004a2e  call    cs:__imp_CloseHandle
0x140004a35  nop     dword ptr [rax+rax+00h]
0x140004a3a  test    eax, eax
0x140004a3c  jz      short loc_140004A45
0x140004a3e  add     rsp, 20h
0x140004a42  pop     rbx
0x140004a43  retn
0x140004a45  mov     rcx, [rsp+28h]; this
0x140004a4a  mov     edx, 0A0Bh; void *
0x140004a4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a55  mov     rcx, [rsp+28h]; this
0x140004a5a  mov     edx, 0A0Bh; void *
0x140004a5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
