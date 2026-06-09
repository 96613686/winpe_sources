# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x140002c44`
- end: `0x140002ca6`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b08`
- `0x140002e78`

## callees

- `0x140002c44`
- `0x1400057ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002c56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002c68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002c56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002c68`

## string_xrefs

- `0x140002c7d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140002c94`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
  }
}

```

## disassembly

```asm
0x140002c44  push    rbx
0x140002c46  sub     rsp, 20h
0x140002c4a  mov     rbx, rcx
0x140002c4d  mov     rcx, [rcx+8]; hObject
0x140002c51  test    rcx, rcx
0x140002c54  jz      short loc_140002C60
0x140002c56  call    cs:__imp_CloseHandle
0x140002c5c  test    eax, eax
0x140002c5e  jz      short loc_140002C8F
0x140002c60  mov     rcx, [rbx]; hObject
0x140002c63  test    rcx, rcx
0x140002c66  jz      short loc_140002C72
0x140002c68  call    cs:__imp_CloseHandle
0x140002c6e  test    eax, eax
0x140002c70  jz      short loc_140002C78
0x140002c72  add     rsp, 20h
0x140002c76  pop     rbx
0x140002c77  retn
0x140002c78  mov     rcx, [rsp+28h]; this
0x140002c7d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002c84  mov     edx, 0A0Bh; void *
0x140002c89  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002c8f  mov     rcx, [rsp+28h]; this
0x140002c94  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002c9b  mov     edx, 0A0Bh; void *
0x140002ca0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
