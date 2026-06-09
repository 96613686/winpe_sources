# Windows::Compat::Inventory::Service::TraceController::~TraceController(void)

- ea: `0x18002fe14`
- end: `0x18002fede`
- name: `??1TraceController@Service@Inventory@Compat@Windows@@UEAA@XZ`
- size: `202`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::TraceController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ff40`

## callees

- `0x18000774c`
- `0x1800108d4`
- `0x180011334`
- `0x18002fe14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002fe4e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002fe4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fe35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fe35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe71`

## string_xrefs

- `0x18002fe9e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002feb5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002fecc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::TraceController::~TraceController(HANDLE *this, __int64 a2)
{
  const char *v3; // r9
  HANDLE v4; // rcx
  const char *v5; // r9
  HANDLE v6; // rcx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *this = &Windows::Compat::Inventory::Service::TraceController::`vftable';
  if ( *((_DWORD *)this + 14) )
  {
    if ( !SetEvent(this[5]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v3);
    std::thread::join((std::thread *)(this + 6));
  }
  if ( *((_DWORD *)this + 14) )
  {
    _o_terminate(this, a2);
    __debugbreak();
  }
  v4 = this[5];
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  v6 = this[4];
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v7);
  std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::~vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(this + 1);
  *this = &Windows::Compat::Inventory::Service::InvSvcTenant::`vftable';
}

```

## disassembly

```asm
0x18002fe14  mov     [rsp+arg_0], rbx
0x18002fe19  push    rdi
0x18002fe1a  sub     rsp, 20h
0x18002fe1e  mov     rbx, rcx
0x18002fe21  lea     rax, ??_7TraceController@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::TraceController::`vftable'
0x18002fe28  mov     [rcx], rax
0x18002fe2b  cmp     dword ptr [rcx+38h], 0
0x18002fe2f  jz      short loc_18002FE48
0x18002fe31  mov     rcx, [rcx+28h]; hEvent
0x18002fe35  call    cs:__imp_SetEvent
0x18002fe3b  test    eax, eax
0x18002fe3d  jz      short loc_18002FEB0
0x18002fe3f  lea     rcx, [rbx+30h]; this
0x18002fe43  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x18002fe48  cmp     dword ptr [rbx+38h], 0
0x18002fe4c  jz      short loc_18002FE55
0x18002fe4e  call    cs:__imp__o_terminate
0x18002fe54  int     3; Trap to Debugger
0x18002fe55  mov     rcx, [rbx+28h]; hObject
0x18002fe59  test    rcx, rcx
0x18002fe5c  jz      short loc_18002FE68
0x18002fe5e  call    cs:__imp_CloseHandle
0x18002fe64  test    eax, eax
0x18002fe66  jz      short loc_18002FEC7
0x18002fe68  mov     rcx, [rbx+20h]; hObject
0x18002fe6c  test    rcx, rcx
0x18002fe6f  jz      short loc_18002FE7B
0x18002fe71  call    cs:__imp_CloseHandle
0x18002fe77  test    eax, eax
0x18002fe79  jz      short loc_18002FE99
0x18002fe7b  lea     rcx, [rbx+8]
0x18002fe7f  call    ??1?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>::~vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>>(void)
0x18002fe84  lea     rax, ??_7InvSvcTenant@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::InvSvcTenant::`vftable'
0x18002fe8b  mov     [rbx], rax
0x18002fe8e  mov     rbx, [rsp+28h+arg_0]
0x18002fe93  add     rsp, 20h
0x18002fe97  pop     rdi
0x18002fe98  retn
0x18002fe99  mov     rcx, [rsp+28h]; this
0x18002fe9e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002fea5  mov     edx, 0A0Bh; void *
0x18002feaa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002feb0  mov     rcx, [rsp+28h]; this
0x18002feb5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002febc  mov     edx, 0A01h; void *
0x18002fec1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002fec7  mov     rcx, [rsp+28h]; this
0x18002fecc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002fed3  mov     edx, 0A0Bh; void *
0x18002fed8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
