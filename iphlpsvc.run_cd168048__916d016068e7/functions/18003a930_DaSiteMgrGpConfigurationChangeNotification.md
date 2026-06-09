# DaSiteMgrGpConfigurationChangeNotification

- ea: `0x18003a930`
- end: `0x18003aabb`
- name: `DaSiteMgrGpConfigurationChangeNotification`
- size: `395`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006f8b0`

## callees

- `0x180004f50`
- `0x18000d7b0`
- `0x18003a930`
- `0x18003ec08`
- `0x18003edbc`
- `0x18004319c`
- `0x18006feb8`
- `0x1800702dc`
- `0x180070858`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003aa72`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003aa72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a97b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a97b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aa4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aa4d`

## string_xrefs

- `0x18003aa99`: `onecoreuap\net\netio\iphlpsvc\service\stmgr.c`
- `0x18003aaa0`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x18003a94b`: `DaSiteMgrGpConfigurationChangeNotification started`
- `0x18003a987`: `DaSiteMgrGpConfigurationChangeNotification obtained site manager lock`
- `0x18003aa85`: `DaSiteMgrGpConfigurationChangeNotification exiting, with current instance (%p)`
- `0x18003a9b7`: `DaSiteMgrGpConfigurationChangeNotification detected no changes in configuration`
- `0x18003a9d0`: `DaSiteMgrGpConfigurationChangeNotification detected changes in configuration, destroying old instance (%p)`
- `0x18003aa05`: `DaSiteMgrGpConfigurationChangeNotification creating new instance (%p)`

## pseudocode

```c
void __fastcall DaSiteMgrGpConfigurationChangeNotification(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  int v2; // eax
  __int64 InstanceStubFromPolicyStore; // rax
  LPCRITICAL_SECTION v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rdi

  _InterlockedIncrement(&g_DaSiteMgrAdSiteTableEpoch);
  EventWrite0(0x80000000LL, L"DaSiteMgrGpConfigurationChangeNotification started");
  while ( 1 )
  {
    v2 = g_DaSiteMgrModuleReferenceObject;
    if ( (g_DaSiteMgrModuleReferenceObject & 1) != 0 )
      break;
    if ( v2 == _InterlockedCompareExchange(
                 &g_DaSiteMgrModuleReferenceObject,
                 g_DaSiteMgrModuleReferenceObject + 2,
                 g_DaSiteMgrModuleReferenceObject) )
    {
      EnterCriticalSection(&g_DaSiteMgrLock);
      EventWrite0(0x80000000LL, L"DaSiteMgrGpConfigurationChangeNotification obtained site manager lock");
      InstanceStubFromPolicyStore = DaSiteMgrCreateInstanceStubFromPolicyStore();
      v4 = g_DaSiteMgrInstance;
      v5 = (struct _RTL_CRITICAL_SECTION *)InstanceStubFromPolicyStore;
      if ( g_DaSiteMgrInstance )
      {
        if ( (unsigned int)DaSiteMgrCompareInstanceStubs(InstanceStubFromPolicyStore) )
        {
          EventWrite0(0x80000000LL, L"DaSiteMgrGpConfigurationChangeNotification detected no changes in configuration");
          DaSiteMgrDestroyInstanceStub(v5);
LABEL_14:
          LeaveCriticalSection(&g_DaSiteMgrLock);
          if ( _InterlockedExchangeAdd(&g_DaSiteMgrModuleReferenceObject, 0xFFFFFFFE) == 3 )
            SetEvent(g_DaSiteMgrModuleReferenceObjectEvent);
          EventWrite0(
            0x80000000LL,
            L"DaSiteMgrGpConfigurationChangeNotification exiting, with current instance (%p)",
            g_DaSiteMgrInstance);
          break;
        }
        EventWrite0(
          0x80000000LL,
          L"DaSiteMgrGpConfigurationChangeNotification detected changes in configuration, destroying old instance (%p)",
          v4);
        DaSiteMgrDestroyInstance();
        DaSiteMgrDestroyInstanceStub(g_DaSiteMgrInstance);
        v4 = 0;
        g_DaSiteMgrInstance = 0;
      }
      if ( v5 )
      {
        g_DaSiteMgrInstance = v5;
        EventWrite0(0x80000000LL, L"DaSiteMgrGpConfigurationChangeNotification creating new instance (%p)", v5);
        if ( (unsigned int)DaSiteMgrCreateInstance() )
        {
          v4 = g_DaSiteMgrInstance;
        }
        else
        {
          DaSiteMgrDestroyInstanceStub(g_DaSiteMgrInstance);
          v4 = 0;
          g_DaSiteMgrInstance = 0;
        }
      }
      if ( !v4 )
        DaSiteMgrUnconfigureSite(0);
      goto LABEL_14;
    }
  }
  DereferenceServiceEx(
    "DaSiteMgrGpConfigurationChangeNotification",
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\stmgr.c",
    239);
}

```

## disassembly

```asm
0x18003a930  mov     [rsp+arg_0], rbx
0x18003a935  mov     [rsp+arg_8], rsi
0x18003a93a  push    rdi
0x18003a93b  sub     rsp, 20h
0x18003a93f  lock inc cs:g_DaSiteMgrAdSiteTableEpoch
0x18003a946  mov     esi, 80000000h
0x18003a94b  lea     rdx, aDasitemgrgpcon_5; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a952  mov     ecx, esi
0x18003a954  call    EventWrite0
0x18003a959  mov     eax, cs:g_DaSiteMgrModuleReferenceObject
0x18003a95f  test    al, 1
0x18003a961  jnz     loc_18003AA93
0x18003a967  lea     ecx, [rax+2]
0x18003a96a  lock cmpxchg cs:g_DaSiteMgrModuleReferenceObject, ecx
0x18003a972  jnz     short loc_18003A959
0x18003a974  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18003a97b  call    cs:__imp_EnterCriticalSection
0x18003a982  nop     dword ptr [rax+rax+00h]
0x18003a987  lea     rdx, aDasitemgrgpcon_3; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a98e  mov     ecx, esi
0x18003a990  call    EventWrite0
0x18003a995  call    DaSiteMgrCreateInstanceStubFromPolicyStore
0x18003a99a  mov     rbx, cs:g_DaSiteMgrInstance
0x18003a9a1  mov     rdi, rax
0x18003a9a4  test    rbx, rbx
0x18003a9a7  jz      short loc_18003A9F6
0x18003a9a9  mov     rcx, rax
0x18003a9ac  call    DaSiteMgrCompareInstanceStubs
0x18003a9b1  mov     ecx, esi
0x18003a9b3  test    eax, eax
0x18003a9b5  jz      short loc_18003A9CD
0x18003a9b7  lea     rdx, aDasitemgrgpcon_1; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a9be  call    EventWrite0
0x18003a9c3  mov     rcx, rdi
0x18003a9c6  call    DaSiteMgrDestroyInstanceStub
0x18003a9cb  jmp     short loc_18003AA46
0x18003a9cd  mov     r8, rbx
0x18003a9d0  lea     rdx, aDasitemgrgpcon_0; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a9d7  call    EventWrite0
0x18003a9dc  call    DaSiteMgrDestroyInstance
0x18003a9e1  mov     rcx, cs:g_DaSiteMgrInstance
0x18003a9e8  call    DaSiteMgrDestroyInstanceStub
0x18003a9ed  xor     ebx, ebx
0x18003a9ef  mov     cs:g_DaSiteMgrInstance, rbx
0x18003a9f6  test    rdi, rdi
0x18003a9f9  jz      short loc_18003AA3A
0x18003a9fb  mov     r8, rdi
0x18003a9fe  mov     cs:g_DaSiteMgrInstance, rdi
0x18003aa05  lea     rdx, aDasitemgrgpcon_4; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003aa0c  mov     ecx, esi
0x18003aa0e  call    EventWrite0
0x18003aa13  call    DaSiteMgrCreateInstance
0x18003aa18  test    eax, eax
0x18003aa1a  jnz     short loc_18003AA33
0x18003aa1c  mov     rcx, cs:g_DaSiteMgrInstance
0x18003aa23  call    DaSiteMgrDestroyInstanceStub
0x18003aa28  xor     ebx, ebx
0x18003aa2a  mov     cs:g_DaSiteMgrInstance, rbx
0x18003aa31  jmp     short loc_18003AA3A
0x18003aa33  mov     rbx, cs:g_DaSiteMgrInstance
0x18003aa3a  test    rbx, rbx
0x18003aa3d  jnz     short loc_18003AA46
0x18003aa3f  xor     ecx, ecx
0x18003aa41  call    DaSiteMgrUnconfigureSite
0x18003aa46  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18003aa4d  call    cs:__imp_LeaveCriticalSection
0x18003aa54  nop     dword ptr [rax+rax+00h]
0x18003aa59  mov     eax, 0FFFFFFFEh
0x18003aa5e  lock xadd cs:g_DaSiteMgrModuleReferenceObject, eax
0x18003aa66  cmp     eax, 3
0x18003aa69  jnz     short loc_18003AA7E
0x18003aa6b  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hEvent
0x18003aa72  call    cs:__imp_SetEvent
0x18003aa79  nop     dword ptr [rax+rax+00h]
0x18003aa7e  mov     r8, cs:g_DaSiteMgrInstance
0x18003aa85  lea     rdx, aDasitemgrgpcon_2; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003aa8c  mov     ecx, esi
0x18003aa8e  call    EventWrite0
0x18003aa93  mov     r8d, 0EFh
0x18003aa99  lea     rdx, aOnecoreuapNetN_46; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003aaa0  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003aaa7  mov     rbx, [rsp+28h+arg_0]
0x18003aaac  mov     rsi, [rsp+28h+arg_8]
0x18003aab1  add     rsp, 20h
0x18003aab5  pop     rdi
0x18003aab6  jmp     DereferenceServiceEx
```
