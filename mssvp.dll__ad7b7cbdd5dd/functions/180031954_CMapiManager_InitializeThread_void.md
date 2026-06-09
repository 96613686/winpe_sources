# CMapiManager::InitializeThread(void)

- ea: `0x180031954`
- end: `0x1800319ea`
- name: `?InitializeThread@CMapiManager@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800320e8`

## callees

- `0x18000a56c`
- `0x180024504`
- `0x18002d33c`
- `0x18002d37c`
- `0x180031954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003196a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003196a`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x180031992`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x1800319c1`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x180031992`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitialize` at `0x1800319c1`

## string_xrefs

- `0x18003199e`: `     CMapiManager::IntializeThread() MapiInitialize() FAILED!, trying again`
- `0x1800319c9`: `   CMapiManager::IntializeThread() MapiInitialize() Completed!`
- `0x180031981`: `   CMapiManager::IntializeThread() MapiInitialize() Calling...`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiManager::InitializeThread(CMapiManager *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = (__int64)this;
  v5 = &CMapiManager::s_csMapiIdleThread;
  EnterCriticalSection(&CMapiManager::s_csMapiIdleThread);
  v4 = 0x900000000LL;
  CLogger::Info(L"   CMapiManager::IntializeThread() MapiInitialize() Calling...");
  v1 = MAPIInitialize(&v4);
  v2 = v1;
  if ( v1 < 0 )
  {
    CLogger::Error(v1, L"     CMapiManager::IntializeThread() MapiInitialize() FAILED!, trying again");
    if ( v2 == -2147221242 )
    {
      HIDWORD(v4) = 1;
      v2 = MAPIInitialize(&v4);
    }
  }
  CLogger::Info(v2, L"   CMapiManager::IntializeThread() MapiInitialize() Completed!");
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
  return v2;
}

```

## disassembly

```asm
0x180031954  mov     [rsp+arg_0], rcx
0x180031959  push    rbx
0x18003195a  sub     rsp, 20h
0x18003195e  lea     rcx, ?s_csMapiIdleThread@CMapiManager@@0VCriticalSection@@A; lpCriticalSection
0x180031965  mov     [rsp+28h+arg_8], rcx
0x18003196a  call    cs:__imp_EnterCriticalSection
0x180031970  nop
0x180031971  mov     dword ptr [rsp+28h+arg_0], 0
0x180031979  mov     dword ptr [rsp+28h+arg_0+4], 9
0x180031981  lea     rcx, aCmapimanagerIn; "   CMapiManager::IntializeThread() Mapi"...
0x180031988  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18003198d  lea     rcx, [rsp+28h+arg_0]
0x180031992  call    cs:__imp_MAPIInitialize
0x180031998  mov     ebx, eax
0x18003199a  test    eax, eax
0x18003199c  jns     short loc_1800319C9
0x18003199e  lea     rdx, aCmapimanagerIn_3; "     CMapiManager::IntializeThread() Ma"...
0x1800319a5  mov     ecx, eax; int
0x1800319a7  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800319ac  cmp     ebx, 80040106h
0x1800319b2  jnz     short loc_1800319C9
0x1800319b4  mov     dword ptr [rsp+28h+arg_0+4], 1
0x1800319bc  lea     rcx, [rsp+28h+arg_0]
0x1800319c1  call    cs:__imp_MAPIInitialize
0x1800319c7  mov     ebx, eax
0x1800319c9  lea     rdx, aCmapimanagerIn_0; "   CMapiManager::IntializeThread() Mapi"...
0x1800319d0  mov     ecx, ebx; int
0x1800319d2  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800319d7  nop
0x1800319d8  lea     rcx, [rsp+28h+arg_8]
0x1800319dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800319e2  mov     eax, ebx
0x1800319e4  add     rsp, 20h
0x1800319e8  pop     rbx
0x1800319e9  retn
```
