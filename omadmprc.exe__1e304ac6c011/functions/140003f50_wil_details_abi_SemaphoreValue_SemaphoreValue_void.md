# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x140003f50`
- end: `0x140003fb1`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400042a4`
- `0x140004680`
- `0x140007dc4`
- `0x140007f30`

## callees

- `0x140003f50`
- `0x140009e20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f7a`

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
0x140003f50  push    rbx
0x140003f52  sub     rsp, 20h
0x140003f56  mov     rbx, rcx
0x140003f59  mov     rcx, [rcx+8]; hObject
0x140003f5d  test    rcx, rcx
0x140003f60  jz      short loc_140003F72
0x140003f62  call    cs:__imp_CloseHandle
0x140003f69  nop     dword ptr [rax+rax+00h]
0x140003f6e  test    eax, eax
0x140003f70  jz      short loc_140003FA1
0x140003f72  mov     rcx, [rbx]; hObject
0x140003f75  test    rcx, rcx
0x140003f78  jz      short loc_140003F8A
0x140003f7a  call    cs:__imp_CloseHandle
0x140003f81  nop     dword ptr [rax+rax+00h]
0x140003f86  test    eax, eax
0x140003f88  jz      short loc_140003F91
0x140003f8a  add     rsp, 20h
0x140003f8e  pop     rbx
0x140003f8f  retn
0x140003f91  mov     rcx, [rsp+28h]; this
0x140003f96  mov     edx, 0A0Bh; void *
0x140003f9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003fa1  mov     rcx, [rsp+28h]; this
0x140003fa6  mov     edx, 0A0Bh; void *
0x140003fab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
