# AOMDHandler::AOMDHandler(void)

- ea: `0x180007074`
- end: `0x180007178`
- name: `??0AOMDHandler@@QEAA@XZ`
- size: `260`
- prototype: `AOMDHandler *__fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001b860`

## callees

- `0x180007074`
- `0x18001459c`
- `0x180016384`
- `0x1800188bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007125`
- `KERNEL32!GetLastError` at `0x180007125`
- `KERNEL32!CreateEventExW` at `0x180007111`
- `KERNEL32!CreateEventExW` at `0x180007111`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
AOMDHandler *__fastcall AOMDHandler::AOMDHandler(AOMDHandler *this)
{
  void *v2; // rdx
  HANDLE Event; // rdi
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

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
  *((_DWORD *)this + 19) = 720;
  *((_DWORD *)this + 20) = 336;
  *((_DWORD *)this + 21) = 3;
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
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &g_exitEvent,
    Event);
  if ( !g_exitEvent )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v6, v7, v8);
  return this;
}

```

## disassembly

```asm
0x180007074  mov     [rsp+arg_8], rbx
0x180007079  mov     [rsp+arg_10], rsi
0x18000707e  mov     [rsp+arg_0], rcx
0x180007083  push    rdi
0x180007084  sub     rsp, 20h
0x180007088  mov     rbx, rcx
0x18000708b  xor     esi, esi
0x18000708d  mov     [rcx+8], rsi
0x180007091  mov     [rcx+10h], esi
0x180007094  or      qword ptr [rcx+18h], 0FFFFFFFFFFFFFFFFh
0x180007099  lea     ecx, [rsi+1]
0x18000709c  mov     [rbx+20h], ecx
0x18000709f  mov     [rbx+24h], esi
0x1800070a2  mov     [rbx+28h], rsi
0x1800070a6  mov     [rbx+30h], rsi
0x1800070aa  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800070b1  lea     rax, ??_7AOMDHandler@@6B@; const AOMDHandler::`vftable'
0x1800070b8  mov     [rbx], rax
0x1800070bb  mov     [rbx+38h], esi
0x1800070be  mov     dword ptr [rbx+3Ch], 2
0x1800070c5  mov     [rbx+40h], ecx
0x1800070c8  mov     [rbx+44h], ecx
0x1800070cb  mov     eax, 2D0h
0x1800070d0  mov     [rbx+48h], eax
0x1800070d3  mov     [rbx+4Ch], eax
0x1800070d6  mov     dword ptr [rbx+50h], 150h
0x1800070dd  mov     dword ptr [rbx+54h], 3
0x1800070e4  mov     [rbx+58h], rsi
0x1800070e8  mov     [rbx+60h], rsi
0x1800070ec  mov     [rbx+68h], rsi
0x1800070f0  mov     [rbx+70h], esi
0x1800070f3  mov     [rbx+78h], rsi
0x1800070f7  mov     [rbx+80h], esi
0x1800070fd  mov     [rbx+88h], rsi
0x180007104  mov     r9d, 1F0003h; dwDesiredAccess
0x18000710a  xor     r8d, r8d; dwFlags
0x18000710d  xor     edx, edx; lpName
0x18000710f  xor     ecx, ecx; lpEventAttributes
0x180007111  call    cs:__imp_CreateEventExW
0x180007118  nop     dword ptr [rax+rax+00h]
0x18000711d  mov     rdi, rax
0x180007120  test    rax, rax
0x180007123  jz      short loc_18000716D
0x180007125  call    cs:__imp_GetLastError
0x18000712c  nop     dword ptr [rax+rax+00h]
0x180007131  mov     rdx, rdi
0x180007134  lea     rcx, ?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18000713b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007140  cmp     cs:?g_exitEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi
0x180007147  setz    al
0x18000714a  mov     rcx, [rsp+28h]; this
0x18000714f  test    al, al
0x180007151  jnz     short loc_180007167
0x180007153  mov     rax, rbx
0x180007156  mov     rbx, [rsp+28h+arg_8]
0x18000715b  mov     rsi, [rsp+28h+arg_10]
0x180007160  add     rsp, 20h
0x180007164  pop     rdi
0x180007165  retn
0x180007167  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000716d  mov     rcx, [rsp+28h]; this
0x180007172  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
