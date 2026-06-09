# InvSvcHandleServiceShutdown(void *,uchar)

- ea: `0x18000c620`
- end: `0x18000c813`
- name: `?InvSvcHandleServiceShutdown@@YAXPEAXE@Z`
- size: `499`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180011720`

## callees

- `0x180003100`
- `0x18000c620`
- `0x18000c880`
- `0x1800108d4`
- `0x180011334`
- `0x1800152d0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000c77a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000c77a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c68f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c68f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c672`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c672`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c710`

## string_xrefs

- `0x18000c800`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c645`: `InvSvcHandleServiceShutdown`
- `0x18000c72f`: `Joining g_workDoneMonitorThread...`
- `0x18000c750`: `g_workDoneMonitorThread joined`
- `0x18000c798`: `g_workDoneMonitorThread is not joinable`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall InvSvcHandleServiceShutdown(void *a1)
{
  const char *v1; // r9
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  const char *v5; // rax
  const char *v6; // rax
  wil::ResultException *v7; // [rsp+30h] [rbp-28h] BYREF
  std::exception *v8; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  AslLogCallPrintf(3, "InvSvcHandleServiceShutdown", 191, "Received context: %p", a1);
  InvSvcUpdateServiceStatus(3u);
  try
  {
    if ( hEvent && !SetEvent(hEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v1);
    AcquireSRWLockExclusive(&g_tenantVectorLock);
    AslLogCallPrintf(3, "InvSvcHandleServiceShutdown", 205, "Clearing tenant vector...");
    v2 = qword_1800FEF70;
    v3 = g_tenantVector;
    if ( g_tenantVector != (void *)qword_1800FEF70 )
    {
      do
      {
        if ( *v3 )
          (**(void (__fastcall ***)(_QWORD, __int64))*v3)(*v3, 1);
        ++v3;
      }
      while ( v3 != (_QWORD *)v2 );
      qword_1800FEF70 = (__int64)g_tenantVector;
    }
    AslLogCallPrintf(3, "InvSvcHandleServiceShutdown", 207, "Tenant vector cleared");
    ReleaseSRWLockExclusive(&g_tenantVectorLock);
    if ( g_workDoneMonitorThread )
    {
      if ( *((_DWORD *)g_workDoneMonitorThread + 2) )
      {
        AslLogCallPrintf(3, "InvSvcHandleServiceShutdown", 214, "Joining g_workDoneMonitorThread...");
        std::thread::join(g_workDoneMonitorThread);
        AslLogCallPrintf(3, "InvSvcHandleServiceShutdown", 216, "g_workDoneMonitorThread joined");
        if ( g_workDoneMonitorThread )
        {
          if ( *((_DWORD *)g_workDoneMonitorThread + 2) )
          {
            _o_terminate(g_workDoneMonitorThread, v4);
            __debugbreak();
          }
          operator delete(g_workDoneMonitorThread, (const struct std::nothrow_t *)0x10);
        }
        g_workDoneMonitorThread = 0;
      }
      else
      {
        AslLogCallPrintf(1, "InvSvcHandleServiceShutdown", 222, "g_workDoneMonitorThread is not joinable");
      }
    }
  }
  catch ( wil::ResultException *v7 )
  {
    v5 = (const char *)(*(__int64 (__fastcall **)(wil::ResultException *))(*(_QWORD *)v7 + 8LL))(v7);
    AslLogCallPrintf(1, "InvSvcHandleServiceShutdown", 228, v5);
  }
  catch ( std::exception *v8 )
  {
    v6 = (const char *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v8 + 8LL))(v8);
    AslLogCallPrintf(1, "InvSvcHandleServiceShutdown", 232, v6);
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "InvSvcHandleServiceShutdown", 236, "Unknown exception");
  }
  if ( g_serviceInfo && qword_1800FEFB0 )
  {
    (*(void (**)(void))(qword_1800FEFB0 + 216))();
    g_serviceInfo = 0;
  }
  InvSvcUpdateServiceStatus(1u);
}

```

## disassembly

```asm
0x18000c620  mov     [rsp+arg_0], rbx
0x18000c625  mov     [rsp+arg_8], rsi
0x18000c62a  push    rdi
0x18000c62b  push    r14
0x18000c62d  push    r15
0x18000c62f  sub     rsp, 40h
0x18000c633  mov     [rsp+58h+var_38], rcx
0x18000c638  lea     r9, aReceivedContex; "Received context: %p"
0x18000c63f  mov     r8d, 0BFh
0x18000c645  lea     rsi, aInvsvchandlese; "InvSvcHandleServiceShutdown"
0x18000c64c  mov     rdx, rsi
0x18000c64f  mov     r14d, 3
0x18000c655  mov     ecx, r14d
0x18000c658  call    AslLogCallPrintf
0x18000c65d  mov     ecx, r14d; unsigned int
0x18000c660  call    ?InvSvcUpdateServiceStatus@@YAXK@Z; InvSvcUpdateServiceStatus(ulong)
0x18000c665  nop
0x18000c666  mov     rcx, cs:hEvent; hEvent
0x18000c66d  test    rcx, rcx
0x18000c670  jz      short loc_18000C685
0x18000c672  call    cs:__imp_SetEvent
0x18000c678  mov     rcx, [rsp+58h]; this
0x18000c67d  test    eax, eax
0x18000c67f  jz      loc_18000C800
0x18000c685  lea     r15, ?g_tenantVectorLock@@3Vsrwlock@wil@@A; wil::srwlock g_tenantVectorLock
0x18000c68c  mov     rcx, r15; SRWLock
0x18000c68f  call    cs:__imp_AcquireSRWLockExclusive
0x18000c695  mov     [rsp+58h+arg_10], r15
0x18000c69a  lea     r9, aClearingTenant; "Clearing tenant vector..."
0x18000c6a1  mov     r8d, 0CDh
0x18000c6a7  mov     rdx, rsi
0x18000c6aa  mov     ecx, r14d
0x18000c6ad  call    AslLogCallPrintf
0x18000c6b2  mov     rdi, cs:qword_1800FEF70
0x18000c6b9  mov     rbx, cs:?g_tenantVector@@3V?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@A; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>> g_tenantVector
0x18000c6c0  cmp     rbx, rdi
0x18000c6c3  jz      short loc_18000C6F4
0x18000c6c5  mov     rcx, [rbx]
0x18000c6c8  test    rcx, rcx
0x18000c6cb  jz      short loc_18000C6DD
0x18000c6cd  mov     rax, [rcx]
0x18000c6d0  mov     edx, 1
0x18000c6d5  mov     rax, [rax]
0x18000c6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6dd  add     rbx, 8
0x18000c6e1  cmp     rbx, rdi
0x18000c6e4  jnz     short loc_18000C6C5
0x18000c6e6  mov     rax, cs:?g_tenantVector@@3V?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@A; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>> g_tenantVector
0x18000c6ed  mov     cs:qword_1800FEF70, rax
0x18000c6f4  lea     r9, aTenantVectorCl; "Tenant vector cleared"
0x18000c6fb  mov     r8d, 0CFh
0x18000c701  mov     rdx, rsi
0x18000c704  mov     ecx, r14d
0x18000c707  call    AslLogCallPrintf
0x18000c70c  nop
0x18000c70d  mov     rcx, r15; SRWLock
0x18000c710  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c716  mov     rax, cs:?g_workDoneMonitorThread@@3PEAVthread@std@@EA; std::thread * g_workDoneMonitorThread
0x18000c71d  test    rax, rax
0x18000c720  jz      loc_18000C7B0
0x18000c726  mov     rdx, rsi
0x18000c729  cmp     dword ptr [rax+8], 0
0x18000c72d  jz      short loc_18000C798
0x18000c72f  lea     r9, aJoiningGWorkdo; "Joining g_workDoneMonitorThread..."
0x18000c736  mov     r8d, 0D6h
0x18000c73c  mov     ecx, r14d
0x18000c73f  call    AslLogCallPrintf
0x18000c744  mov     rcx, cs:?g_workDoneMonitorThread@@3PEAVthread@std@@EA; this
0x18000c74b  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x18000c750  lea     r9, aGWorkdonemonit_0; "g_workDoneMonitorThread joined"
0x18000c757  mov     r8d, 0D8h
0x18000c75d  mov     rdx, rsi
0x18000c760  mov     ecx, r14d
0x18000c763  call    AslLogCallPrintf
0x18000c768  mov     rcx, cs:?g_workDoneMonitorThread@@3PEAVthread@std@@EA; void *
0x18000c76f  test    rcx, rcx
0x18000c772  jz      short loc_18000C78B
0x18000c774  cmp     dword ptr [rcx+8], 0
0x18000c778  jz      short loc_18000C781
0x18000c77a  call    cs:__imp__o_terminate
0x18000c780  int     3; Trap to Debugger
0x18000c781  mov     edx, 10h; struct std::nothrow_t *
0x18000c786  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c78b  mov     cs:?g_workDoneMonitorThread@@3PEAVthread@std@@EA, 0; std::thread * g_workDoneMonitorThread
0x18000c796  jmp     short loc_18000C7B0
0x18000c798  lea     r9, aGWorkdonemonit; "g_workDoneMonitorThread is not joinable"
0x18000c79f  mov     r8d, 0DEh
0x18000c7a5  mov     ecx, 1
0x18000c7aa  call    AslLogCallPrintf
0x18000c7af  nop
0x18000c7b0  mov     rcx, cs:?g_serviceInfo@@3U_unnamed_type_g_serviceInfo_@@A; _unnamed_type_g_serviceInfo_ g_serviceInfo
0x18000c7b7  test    rcx, rcx
0x18000c7ba  jz      short loc_18000C7DF
0x18000c7bc  mov     rax, cs:qword_1800FEFB0
0x18000c7c3  test    rax, rax
0x18000c7c6  jz      short loc_18000C7DF
0x18000c7c8  mov     rax, [rax+0D8h]
0x18000c7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d4  mov     cs:?g_serviceInfo@@3U_unnamed_type_g_serviceInfo_@@A, 0; _unnamed_type_g_serviceInfo_ g_serviceInfo
0x18000c7df  mov     ecx, 1; unsigned int
0x18000c7e4  mov     rbx, [rsp+58h+arg_0]
0x18000c7e9  mov     rsi, [rsp+58h+arg_8]
0x18000c7ee  add     rsp, 40h
0x18000c7f2  pop     r15
0x18000c7f4  pop     r14
0x18000c7f6  pop     rdi
0x18000c7f7  jmp     ?InvSvcUpdateServiceStatus@@YAXK@Z; InvSvcUpdateServiceStatus(ulong)
0x18000c7fc  jmp     short loc_18000C7B0
0x18000c7fe  jmp     short loc_18000C7B0
0x18000c800  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c807  mov     edx, 0A01h; void *
0x18000c80c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
