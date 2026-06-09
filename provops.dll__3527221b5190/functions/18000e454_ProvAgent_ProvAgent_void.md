# ProvAgent::~ProvAgent(void)

- ea: `0x18000e454`
- end: `0x18000e4e0`
- name: `??1ProvAgent@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(ProvAgent *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f8d0`
- `0x180010b40`
- `0x180016840`
- `0x180017020`
- `0x1800349e8`
- `0x180034c8c`
- `0x1800350bc`
- `0x1800352e6`

## callees

- `0x18000864c`
- `0x18000e454`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e466`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e48b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e48b`

## string_xrefs

- `0x18000e4a0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e4b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e4ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ProvAgent::~ProvAgent(ProvAgent *this)
{
  void *v2; // rcx
  const char *v3; // r9
  void *v4; // rcx
  const char *v5; // r9
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 && !ReleaseMutex(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
  }
}

```

## disassembly

```asm
0x18000e454  push    rbx
0x18000e456  sub     rsp, 20h
0x18000e45a  mov     rbx, rcx
0x18000e45d  mov     rcx, [rcx+10h]; hMutex
0x18000e461  test    rcx, rcx
0x18000e464  jz      short loc_18000E470
0x18000e466  call    cs:__imp_ReleaseMutex
0x18000e46c  test    eax, eax
0x18000e46e  jz      short loc_18000E4B2
0x18000e470  mov     rcx, [rbx+8]; hObject
0x18000e474  test    rcx, rcx
0x18000e477  jz      short loc_18000E483
0x18000e479  call    cs:__imp_CloseHandle
0x18000e47f  test    eax, eax
0x18000e481  jz      short loc_18000E4C9
0x18000e483  mov     rcx, [rbx]; hObject
0x18000e486  test    rcx, rcx
0x18000e489  jz      short loc_18000E495
0x18000e48b  call    cs:__imp_CloseHandle
0x18000e491  test    eax, eax
0x18000e493  jz      short loc_18000E49B
0x18000e495  add     rsp, 20h
0x18000e499  pop     rbx
0x18000e49a  retn
0x18000e49b  mov     rcx, [rsp+28h]; this
0x18000e4a0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e4a7  mov     edx, 0A0Bh; void *
0x18000e4ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e4b2  mov     rcx, [rsp+28h]; this
0x18000e4b7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e4be  mov     edx, 0A15h; void *
0x18000e4c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e4c9  mov     rcx, [rsp+28h]; this
0x18000e4ce  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e4d5  mov     edx, 0A0Bh; void *
0x18000e4da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
