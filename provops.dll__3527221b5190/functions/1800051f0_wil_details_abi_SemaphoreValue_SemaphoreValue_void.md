# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1800051f0`
- end: `0x180005252`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f90`
- `0x180005480`
- `0x18000f4c8`
- `0x180015d6c`

## callees

- `0x1800051f0`
- `0x18000864c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005214`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005214`

## string_xrefs

- `0x180005229`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005240`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800051f0  push    rbx
0x1800051f2  sub     rsp, 20h
0x1800051f6  mov     rbx, rcx
0x1800051f9  mov     rcx, [rcx+8]; hObject
0x1800051fd  test    rcx, rcx
0x180005200  jz      short loc_18000520C
0x180005202  call    cs:__imp_CloseHandle
0x180005208  test    eax, eax
0x18000520a  jz      short loc_18000523B
0x18000520c  mov     rcx, [rbx]; hObject
0x18000520f  test    rcx, rcx
0x180005212  jz      short loc_18000521E
0x180005214  call    cs:__imp_CloseHandle
0x18000521a  test    eax, eax
0x18000521c  jz      short loc_180005224
0x18000521e  add     rsp, 20h
0x180005222  pop     rbx
0x180005223  retn
0x180005224  mov     rcx, [rsp+28h]; this
0x180005229  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005230  mov     edx, 0A0Bh; void *
0x180005235  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000523b  mov     rcx, [rsp+28h]; this
0x180005240  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005247  mov     edx, 0A0Bh; void *
0x18000524c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
