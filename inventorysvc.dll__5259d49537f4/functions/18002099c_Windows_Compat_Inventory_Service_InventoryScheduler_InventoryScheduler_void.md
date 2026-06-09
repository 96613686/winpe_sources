# Windows::Compat::Inventory::Service::InventoryScheduler::~InventoryScheduler(void)

- ea: `0x18002099c`
- end: `0x180020c0a`
- name: `??1InventoryScheduler@Service@Inventory@Compat@Windows@@UEAA@XZ`
- size: `622`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::InventoryScheduler *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180021170`
- `0x18002e5b4`
- `0x18002f69c`
- `0x1800cf6e7`

## callees

- `0x180002bf0`
- `0x180003100`
- `0x18000fc88`
- `0x1800108d4`
- `0x180011334`
- `0x1800152d0`
- `0x18002099c`
- `0x180029a44`
- `0x1800bedd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180020a6b`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180020a6b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020a0c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020a0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aee`

## string_xrefs

- `0x180020b5c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020b76`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020b90`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020baa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020bc4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020bde`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180020bf8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800209d5`: `Windows::Compat::Inventory::Service::InventoryScheduler::~InventoryScheduler`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::InventoryScheduler::~InventoryScheduler(
        Windows::Compat::Inventory::Service::InventoryScheduler *this)
{
  unsigned int v2; // edx
  __int64 v3; // rdx
  const char *v4; // r9
  std::thread *v5; // rcx
  void *v6; // rdi
  void *v7; // rdi
  void *v8; // rcx
  const char *v9; // r9
  void *v10; // rcx
  const char *v11; // r9
  void *v12; // rcx
  const char *v13; // r9
  void *v14; // rcx
  const char *v15; // r9
  void *v16; // rcx
  const char *v17; // r9
  void *v18; // rcx
  const char *v19; // r9
  void *v20; // rcx
  HKEY v21; // rcx
  HKEY v22; // rcx
  char v23[144]; // [rsp+20h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)this = &Windows::Compat::Inventory::Service::InventoryScheduler::`vftable';
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::Service::InventoryScheduler::~InventoryScheduler",
    65,
    "Shutting down");
  TraceLoggingCorrelationVector::ToStringImpl(
    *((TraceLoggingCorrelationVector **)this + 3),
    _InterlockedExchangeAdd64((volatile signed __int64 *)(*((_QWORD *)this + 3) + 136LL), 0),
    v23);
  TelCacheProvider::SendHealthEvent(v23, v2);
  if ( !SetEvent(*((HANDLE *)this + 4)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v5 = (Windows::Compat::Inventory::Service::InventoryScheduler *)((char *)this + 80);
  if ( *((_DWORD *)this + 22) )
    std::thread::join(v5);
  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
  {
    TelemetryProvider::~TelemetryProvider(*((TelemetryProvider **)this + 13));
    operator delete(v6, (const struct std::nothrow_t *)0x40);
  }
  v7 = (void *)*((_QWORD *)this + 12);
  if ( v7 )
  {
    TelemetryProvider::~TelemetryProvider(*((TelemetryProvider **)this + 12));
    operator delete(v7, (const struct std::nothrow_t *)0x40);
  }
  if ( *((_DWORD *)this + 22) )
  {
    _o_terminate(v5, v3);
    __debugbreak();
  }
  v8 = (void *)*((_QWORD *)this + 9);
  if ( v8 && !CloseHandle(v8) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  v10 = (void *)*((_QWORD *)this + 8);
  if ( v10 && !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v11);
  v12 = (void *)*((_QWORD *)this + 7);
  if ( v12 && !CloseHandle(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v13);
  v14 = (void *)*((_QWORD *)this + 6);
  if ( v14 && !CloseHandle(v14) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v15);
  v16 = (void *)*((_QWORD *)this + 5);
  if ( v16 && !CloseHandle(v16) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v17);
  v18 = (void *)*((_QWORD *)this + 4);
  if ( v18 && !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v19);
  v20 = (void *)*((_QWORD *)this + 3);
  if ( v20 )
    operator delete(v20, (const struct std::nothrow_t *)0x90);
  v21 = (HKEY)*((_QWORD *)this + 2);
  if ( v21 )
    RegCloseKey(v21);
  v22 = (HKEY)*((_QWORD *)this + 1);
  if ( v22 )
    RegCloseKey(v22);
  *(_QWORD *)this = &Windows::Compat::Inventory::Service::InvSvcTenant::`vftable';
}

```

## disassembly

```asm
0x18002099c  mov     [rsp+arg_8], rbx
0x1800209a1  push    rdi
0x1800209a2  sub     rsp, 0C0h
0x1800209a9  mov     rax, cs:__security_cookie
0x1800209b0  xor     rax, rsp
0x1800209b3  mov     [rsp+0C8h+var_18], rax
0x1800209bb  mov     rbx, rcx
0x1800209be  lea     rax, ??_7InventoryScheduler@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::InventoryScheduler::`vftable'
0x1800209c5  mov     [rcx], rax
0x1800209c8  lea     r9, aShuttingDown; "Shutting down"
0x1800209cf  mov     r8d, 41h ; 'A'
0x1800209d5  lea     rdx, aWindowsCompatI_46; "Windows::Compat::Inventory::Service::In"...
0x1800209dc  lea     ecx, [r8-3Eh]
0x1800209e0  call    AslLogCallPrintf
0x1800209e5  mov     rcx, [rbx+18h]; this
0x1800209e9  xor     edx, edx
0x1800209eb  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800209f4  lea     r8, [rsp+0C8h+var_A8]; char *
0x1800209f9  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800209fe  lea     rcx, [rsp+0C8h+var_A8]; char *
0x180020a03  call    ?SendHealthEvent@TelCacheProvider@@SAXPEBD@Z; TelCacheProvider::SendHealthEvent(char const *)
0x180020a08  mov     rcx, [rbx+20h]; hEvent
0x180020a0c  call    cs:__imp_SetEvent
0x180020a12  test    eax, eax
0x180020a14  jz      loc_180020B6E
0x180020a1a  lea     rcx, [rbx+50h]; this
0x180020a1e  cmp     dword ptr [rcx+8], 0
0x180020a22  jz      short loc_180020A29
0x180020a24  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x180020a29  mov     rdi, [rbx+68h]
0x180020a2d  test    rdi, rdi
0x180020a30  jz      short loc_180020A47
0x180020a32  mov     rcx, rdi; this
0x180020a35  call    ??1TelemetryProvider@@QEAA@XZ; TelemetryProvider::~TelemetryProvider(void)
0x180020a3a  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180020a3f  mov     rcx, rdi; void *
0x180020a42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020a47  mov     rdi, [rbx+60h]
0x180020a4b  test    rdi, rdi
0x180020a4e  jz      short loc_180020A65
0x180020a50  mov     rcx, rdi; this
0x180020a53  call    ??1TelemetryProvider@@QEAA@XZ; TelemetryProvider::~TelemetryProvider(void)
0x180020a58  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180020a5d  mov     rcx, rdi; void *
0x180020a60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020a65  cmp     dword ptr [rbx+58h], 0
0x180020a69  jz      short loc_180020A72
0x180020a6b  call    cs:__imp__o_terminate
0x180020a71  int     3; Trap to Debugger
0x180020a72  mov     rcx, [rbx+48h]; hObject
0x180020a76  test    rcx, rcx
0x180020a79  jz      short loc_180020A89
0x180020a7b  call    cs:__imp_CloseHandle
0x180020a81  test    eax, eax
0x180020a83  jz      loc_180020B88
0x180020a89  mov     rcx, [rbx+40h]; hObject
0x180020a8d  test    rcx, rcx
0x180020a90  jz      short loc_180020AA0
0x180020a92  call    cs:__imp_CloseHandle
0x180020a98  test    eax, eax
0x180020a9a  jz      loc_180020BA2
0x180020aa0  mov     rcx, [rbx+38h]; hObject
0x180020aa4  test    rcx, rcx
0x180020aa7  jz      short loc_180020AB7
0x180020aa9  call    cs:__imp_CloseHandle
0x180020aaf  test    eax, eax
0x180020ab1  jz      loc_180020BBC
0x180020ab7  mov     rcx, [rbx+30h]; hObject
0x180020abb  test    rcx, rcx
0x180020abe  jz      short loc_180020ACE
0x180020ac0  call    cs:__imp_CloseHandle
0x180020ac6  test    eax, eax
0x180020ac8  jz      loc_180020BD6
0x180020ace  mov     rcx, [rbx+28h]; hObject
0x180020ad2  test    rcx, rcx
0x180020ad5  jz      short loc_180020AE5
0x180020ad7  call    cs:__imp_CloseHandle
0x180020add  test    eax, eax
0x180020adf  jz      loc_180020BF0
0x180020ae5  mov     rcx, [rbx+20h]; hObject
0x180020ae9  test    rcx, rcx
0x180020aec  jz      short loc_180020AF8
0x180020aee  call    cs:__imp_CloseHandle
0x180020af4  test    eax, eax
0x180020af6  jz      short loc_180020B54
0x180020af8  mov     rcx, [rbx+18h]; void *
0x180020afc  test    rcx, rcx
0x180020aff  jz      short loc_180020B0B
0x180020b01  mov     edx, 90h; struct std::nothrow_t *
0x180020b06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020b0b  mov     rcx, [rbx+10h]; hKey
0x180020b0f  test    rcx, rcx
0x180020b12  jz      short loc_180020B1A
0x180020b14  call    cs:__imp_RegCloseKey
0x180020b1a  mov     rcx, [rbx+8]; hKey
0x180020b1e  test    rcx, rcx
0x180020b21  jz      short loc_180020B29
0x180020b23  call    cs:__imp_RegCloseKey
0x180020b29  lea     rax, ??_7InvSvcTenant@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::InvSvcTenant::`vftable'
0x180020b30  mov     [rbx], rax
0x180020b33  mov     rcx, [rsp+0C8h+var_18]
0x180020b3b  xor     rcx, rsp; StackCookie
0x180020b3e  call    __security_check_cookie
0x180020b43  mov     rbx, [rsp+0C8h+arg_8]
0x180020b4b  add     rsp, 0C0h
0x180020b52  pop     rdi
0x180020b53  retn
0x180020b54  mov     rcx, [rsp+0C8h]; this
0x180020b5c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020b63  mov     edx, 0A0Bh; void *
0x180020b68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020b6e  mov     rcx, [rsp+0C8h]; this
0x180020b76  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020b7d  mov     edx, 0A01h; void *
0x180020b82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020b88  mov     rcx, [rsp+0C8h]; this
0x180020b90  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020b97  mov     edx, 0A0Bh; void *
0x180020b9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020ba2  mov     rcx, [rsp+0C8h]; this
0x180020baa  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020bb1  mov     edx, 0A0Bh; void *
0x180020bb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020bbc  mov     rcx, [rsp+0C8h]; this
0x180020bc4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020bcb  mov     edx, 0A0Bh; void *
0x180020bd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020bd6  mov     rcx, [rsp+0C8h]; this
0x180020bde  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020be5  mov     edx, 0A0Bh; void *
0x180020bea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020bf0  mov     rcx, [rsp+0C8h]; this
0x180020bf8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020bff  mov     edx, 0A0Bh; void *
0x180020c04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
