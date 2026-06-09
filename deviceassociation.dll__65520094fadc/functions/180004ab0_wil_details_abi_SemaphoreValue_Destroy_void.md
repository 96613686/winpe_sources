# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x180004ab0`
- end: `0x180004b4c`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800071bc`
- `0x1800072d0`

## callees

- `0x180004ab0`
- `0x18000844c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ae1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ae1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b02`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::Destroy(wil::details_abi::SemaphoreValue *this)
{
  void *v1; // rdi
  DWORD LastError; // esi
  __int64 v4; // r8
  const char *v5; // r9
  void *v6; // rdi
  DWORD v7; // esi
  __int64 v8; // r8
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    v7 = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(v7);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180004ab0  mov     [rsp+arg_0], rbx
0x180004ab5  mov     [rsp+arg_8], rsi
0x180004aba  push    rdi
0x180004abb  sub     rsp, 20h
0x180004abf  mov     rdi, [rcx]
0x180004ac2  mov     rbx, rcx
0x180004ac5  test    rdi, rdi
0x180004ac8  jz      short loc_180004AE7
0x180004aca  call    cs:__imp_GetLastError
0x180004ad0  mov     rcx, rdi; hObject
0x180004ad3  mov     esi, eax
0x180004ad5  call    cs:__imp_CloseHandle
0x180004adb  test    eax, eax
0x180004add  jz      short loc_180004B3C
0x180004adf  mov     ecx, esi; dwErrCode
0x180004ae1  call    cs:__imp_SetLastError
0x180004ae7  mov     qword ptr [rbx], 0
0x180004aee  mov     rdi, [rbx+8]
0x180004af2  test    rdi, rdi
0x180004af5  jz      short loc_180004B14
0x180004af7  call    cs:__imp_GetLastError
0x180004afd  mov     rcx, rdi; hObject
0x180004b00  mov     esi, eax
0x180004b02  call    cs:__imp_CloseHandle
0x180004b08  test    eax, eax
0x180004b0a  jz      short loc_180004B2C
0x180004b0c  mov     ecx, esi; dwErrCode
0x180004b0e  call    cs:__imp_SetLastError
0x180004b14  mov     rsi, [rsp+28h+arg_8]
0x180004b19  mov     qword ptr [rbx+8], 0
0x180004b21  mov     rbx, [rsp+28h+arg_0]
0x180004b26  add     rsp, 20h
0x180004b2a  pop     rdi
0x180004b2b  retn
0x180004b2c  mov     rcx, [rsp+28h]; this
0x180004b31  mov     edx, 0A0Bh; void *
0x180004b36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b3c  mov     rcx, [rsp+28h]; this
0x180004b41  mov     edx, 0A0Bh; void *
0x180004b46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
