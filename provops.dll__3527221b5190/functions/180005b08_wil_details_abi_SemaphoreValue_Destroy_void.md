# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x180005b08`
- end: `0x180005bb2`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800070e4`
- `0x180015d6c`

## callees

- `0x180005b08`
- `0x18000864c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b5a`

## string_xrefs

- `0x180005b89`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005ba0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::Destroy(wil::details_abi::SemaphoreValue *this)
{
  void *v1; // rdi
  DWORD LastError; // esi
  const char *v4; // r9
  void *v5; // rdi
  DWORD v6; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v6 = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(v6);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180005b08  mov     [rsp+arg_0], rbx
0x180005b0d  mov     [rsp+arg_8], rsi
0x180005b12  push    rdi
0x180005b13  sub     rsp, 20h
0x180005b17  mov     rdi, [rcx]
0x180005b1a  mov     rbx, rcx
0x180005b1d  test    rdi, rdi
0x180005b20  jz      short loc_180005B3F
0x180005b22  call    cs:__imp_GetLastError
0x180005b28  mov     rcx, rdi; hObject
0x180005b2b  mov     esi, eax
0x180005b2d  call    cs:__imp_CloseHandle
0x180005b33  test    eax, eax
0x180005b35  jz      short loc_180005B9B
0x180005b37  mov     ecx, esi; dwErrCode
0x180005b39  call    cs:__imp_SetLastError
0x180005b3f  mov     qword ptr [rbx], 0
0x180005b46  mov     rdi, [rbx+8]
0x180005b4a  test    rdi, rdi
0x180005b4d  jz      short loc_180005B6C
0x180005b4f  call    cs:__imp_GetLastError
0x180005b55  mov     rcx, rdi; hObject
0x180005b58  mov     esi, eax
0x180005b5a  call    cs:__imp_CloseHandle
0x180005b60  test    eax, eax
0x180005b62  jz      short loc_180005B84
0x180005b64  mov     ecx, esi; dwErrCode
0x180005b66  call    cs:__imp_SetLastError
0x180005b6c  mov     rsi, [rsp+28h+arg_8]
0x180005b71  mov     qword ptr [rbx+8], 0
0x180005b79  mov     rbx, [rsp+28h+arg_0]
0x180005b7e  add     rsp, 20h
0x180005b82  pop     rdi
0x180005b83  retn
0x180005b84  mov     rcx, [rsp+28h]; this
0x180005b89  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005b90  mov     edx, 0A0Bh; void *
0x180005b95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005b9b  mov     rcx, [rsp+28h]; this
0x180005ba0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005ba7  mov     edx, 0A0Bh; void *
0x180005bac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
