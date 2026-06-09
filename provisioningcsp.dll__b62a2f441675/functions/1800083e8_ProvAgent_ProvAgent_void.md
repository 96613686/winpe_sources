# ProvAgent::~ProvAgent(void)

- ea: `0x1800083e8`
- end: `0x180008472`
- name: `??1ProvAgent@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(ProvAgent *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008ab0`
- `0x180023680`
- `0x18003610f`
- `0x180036b6d`

## callees

- `0x180007834`
- `0x1800083e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800083fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800083fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000842b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000842b`

## pseudocode

```c
void __fastcall ProvAgent::~ProvAgent(ProvAgent *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  void *v5; // rcx
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 && !ReleaseMutex(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v3, v4);
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 && !CloseHandle(v5) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
  }
}

```

## disassembly

```asm
0x1800083e8  push    rbx
0x1800083ea  sub     rsp, 20h
0x1800083ee  mov     rbx, rcx
0x1800083f1  mov     rcx, [rcx+10h]; hMutex
0x1800083f5  test    rcx, rcx
0x1800083f8  jz      short loc_18000840A
0x1800083fa  call    cs:__imp_ReleaseMutex
0x180008401  nop     dword ptr [rax+rax+00h]
0x180008406  test    eax, eax
0x180008408  jz      short loc_180008452
0x18000840a  mov     rcx, [rbx+8]; hObject
0x18000840e  test    rcx, rcx
0x180008411  jz      short loc_180008423
0x180008413  call    cs:__imp_CloseHandle
0x18000841a  nop     dword ptr [rax+rax+00h]
0x18000841f  test    eax, eax
0x180008421  jz      short loc_180008462
0x180008423  mov     rcx, [rbx]; hObject
0x180008426  test    rcx, rcx
0x180008429  jz      short loc_18000843B
0x18000842b  call    cs:__imp_CloseHandle
0x180008432  nop     dword ptr [rax+rax+00h]
0x180008437  test    eax, eax
0x180008439  jz      short loc_180008442
0x18000843b  add     rsp, 20h
0x18000843f  pop     rbx
0x180008440  retn
0x180008442  mov     rcx, [rsp+28h]; this
0x180008447  mov     edx, 0A0Bh; void *
0x18000844c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008452  mov     rcx, [rsp+28h]; this
0x180008457  mov     edx, 0A15h; void *
0x18000845c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008462  mov     rcx, [rsp+28h]; this
0x180008467  mov     edx, 0A0Bh; void *
0x18000846c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
