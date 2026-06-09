# AOMDHandler::AOMDHandler(void)

- ea: `0x180006fd8`
- end: `0x1800070f0`
- name: `??0AOMDHandler@@QEAA@XZ`
- size: `280`
- prototype: `AOMDHandler *__fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001a890`

## callees

- `0x180006fd8`
- `0x18001399c`
- `0x180015604`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800070a6`
- `KERNEL32!CloseHandle` at `0x1800070a6`
- `KERNEL32!GetLastError` at `0x180007089`
- `KERNEL32!GetLastError` at `0x18000709b`
- `KERNEL32!GetLastError` at `0x180007089`
- `KERNEL32!GetLastError` at `0x18000709b`
- `KERNEL32!CreateEventExW` at `0x18000707b`
- `KERNEL32!CreateEventExW` at `0x18000707b`
- `KERNEL32!SetLastError` at `0x1800070b7`
- `KERNEL32!SetLastError` at `0x1800070b7`

## pseudocode

```c
AOMDHandler *__fastcall AOMDHandler::AOMDHandler(AOMDHandler *this)
{
  void *v2; // rdx
  HANDLE Event; // rsi
  unsigned int v4; // r8d
  const char *v5; // r9
  HANDLE v6; // rdi
  DWORD LastError; // ebp
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = -1;
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
  *(_QWORD *)this = &AOMDHandler::`vftable';
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 2;
  *((_DWORD *)this + 16) = 1;
  *((_DWORD *)this + 17) = 1;
  *((_DWORD *)this + 18) = 720;
  *((_DWORD *)this + 19) = 336;
  *((_DWORD *)this + 20) = 336;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 17) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  v6 = g_exitEvent;
  if ( g_exitEvent )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(LastError);
  }
  g_exitEvent = Event;
  return this;
}

```

## disassembly

```asm
0x180006fd8  mov     [rsp+arg_8], rbx
0x180006fdd  mov     [rsp+arg_10], rbp
0x180006fe2  mov     [rsp+arg_0], rcx
0x180006fe7  push    rsi
0x180006fe8  push    rdi
0x180006fe9  push    r14
0x180006feb  sub     rsp, 20h
0x180006fef  mov     rbx, rcx
0x180006ff2  xor     r14d, r14d
0x180006ff5  mov     [rcx+8], r14
0x180006ff9  mov     [rcx+10h], r14d
0x180006ffd  mov     qword ptr [rcx+18h], 0FFFFFFFFFFFFFFFFh
0x180007005  lea     ecx, [r14+1]
0x180007009  mov     [rbx+20h], ecx
0x18000700c  mov     [rbx+24h], r14d
0x180007010  mov     [rbx+28h], r14
0x180007014  mov     [rbx+30h], r14
0x180007018  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000701f  lea     rax, ??_7AOMDHandler@@6B@; const AOMDHandler::`vftable'
0x180007026  mov     [rbx], rax
0x180007029  mov     [rbx+38h], r14d
0x18000702d  mov     dword ptr [rbx+3Ch], 2
0x180007034  mov     [rbx+40h], ecx
0x180007037  mov     [rbx+44h], ecx
0x18000703a  mov     dword ptr [rbx+48h], 2D0h
0x180007041  mov     eax, 150h
0x180007046  mov     [rbx+4Ch], eax
0x180007049  mov     [rbx+50h], eax
0x18000704c  mov     [rbx+58h], r14
0x180007050  mov     [rbx+60h], r14
0x180007054  mov     [rbx+68h], r14
0x180007058  mov     [rbx+70h], r14d
0x18000705c  mov     [rbx+78h], r14
0x180007060  mov     [rbx+80h], r14d
0x180007067  mov     [rbx+88h], r14
0x18000706e  mov     r9d, 1F0003h; dwDesiredAccess
0x180007074  xor     r8d, r8d; dwFlags
0x180007077  xor     edx, edx; lpName
0x180007079  xor     ecx, ecx; lpEventAttributes
0x18000707b  call    cs:__imp_CreateEventExW
0x180007081  mov     rsi, rax
0x180007084  test    rax, rax
0x180007087  jz      short loc_1800070E5
0x180007089  call    cs:__imp_GetLastError
0x18000708f  mov     rdi, cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x180007096  test    rdi, rdi
0x180007099  jz      short loc_1800070BD
0x18000709b  call    cs:__imp_GetLastError
0x1800070a1  mov     ebp, eax
0x1800070a3  mov     rcx, rdi; hObject
0x1800070a6  call    cs:__imp_CloseHandle
0x1800070ac  mov     rcx, [rsp+38h]; this
0x1800070b1  test    eax, eax
0x1800070b3  jz      short loc_1800070DA
0x1800070b5  mov     ecx, ebp; dwErrCode
0x1800070b7  call    cs:__imp_SetLastError
0x1800070bd  mov     cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi
0x1800070c4  mov     rax, rbx
0x1800070c7  mov     rbx, [rsp+38h+arg_8]
0x1800070cc  mov     rbp, [rsp+38h+arg_10]
0x1800070d1  add     rsp, 20h
0x1800070d5  pop     r14
0x1800070d7  pop     rdi
0x1800070d8  pop     rsi
0x1800070d9  retn
0x1800070da  mov     edx, 0A0Bh; void *
0x1800070df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800070e5  mov     rcx, [rsp+38h]; this
0x1800070ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
