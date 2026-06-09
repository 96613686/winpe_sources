# DaSiteMgrGpConfigurationChangeNotification

- ea: `0x18003a940`
- end: `0x18003aacb`
- name: `DaSiteMgrGpConfigurationChangeNotification`
- size: `395`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006f8d0`

## callees

- `0x180004f60`
- `0x18000d7c0`
- `0x18003a940`
- `0x18003ebc8`
- `0x18003ed7c`
- `0x18004315c`
- `0x18006fed8`
- `0x1800702fc`
- `0x180070878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003aa82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003aa82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a98b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a98b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aa5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aa5d`

## string_xrefs

- `0x18003aaa9`: `onecoreuap\net\netio\iphlpsvc\service\stmgr.c`
- `0x18003aab0`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x18003a95b`: `DaSiteMgrGpConfigurationChangeNotification started`
- `0x18003a997`: `DaSiteMgrGpConfigurationChangeNotification obtained site manager lock`
- `0x18003aa95`: `DaSiteMgrGpConfigurationChangeNotification exiting, with current instance (%p)`
- `0x18003a9c7`: `DaSiteMgrGpConfigurationChangeNotification detected no changes in configuration`
- `0x18003a9e0`: `DaSiteMgrGpConfigurationChangeNotification detected changes in configuration, destroying old instance (%p)`
- `0x18003aa15`: `DaSiteMgrGpConfigurationChangeNotification creating new instance (%p)`

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
0x18003a940  mov     [rsp+arg_0], rbx
0x18003a945  mov     [rsp+arg_8], rsi
0x18003a94a  push    rdi
0x18003a94b  sub     rsp, 20h
0x18003a94f  lock inc cs:g_DaSiteMgrAdSiteTableEpoch
0x18003a956  mov     esi, 80000000h
0x18003a95b  lea     rdx, aDasitemgrgpcon_5; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a962  mov     ecx, esi
0x18003a964  call    EventWrite0
0x18003a969  mov     eax, cs:g_DaSiteMgrModuleReferenceObject
0x18003a96f  test    al, 1
0x18003a971  jnz     loc_18003AAA3
0x18003a977  lea     ecx, [rax+2]
0x18003a97a  lock cmpxchg cs:g_DaSiteMgrModuleReferenceObject, ecx
0x18003a982  jnz     short loc_18003A969
0x18003a984  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18003a98b  call    cs:__imp_EnterCriticalSection
0x18003a992  nop     dword ptr [rax+rax+00h]
0x18003a997  lea     rdx, aDasitemgrgpcon_3; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a99e  mov     ecx, esi
0x18003a9a0  call    EventWrite0
0x18003a9a5  call    DaSiteMgrCreateInstanceStubFromPolicyStore
0x18003a9aa  mov     rbx, cs:g_DaSiteMgrInstance
0x18003a9b1  mov     rdi, rax
0x18003a9b4  test    rbx, rbx
0x18003a9b7  jz      short loc_18003AA06
0x18003a9b9  mov     rcx, rax
0x18003a9bc  call    DaSiteMgrCompareInstanceStubs
0x18003a9c1  mov     ecx, esi
0x18003a9c3  test    eax, eax
0x18003a9c5  jz      short loc_18003A9DD
0x18003a9c7  lea     rdx, aDasitemgrgpcon_1; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a9ce  call    EventWrite0
0x18003a9d3  mov     rcx, rdi
0x18003a9d6  call    DaSiteMgrDestroyInstanceStub
0x18003a9db  jmp     short loc_18003AA56
0x18003a9dd  mov     r8, rbx
0x18003a9e0  lea     rdx, aDasitemgrgpcon_0; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003a9e7  call    EventWrite0
0x18003a9ec  call    DaSiteMgrDestroyInstance
0x18003a9f1  mov     rcx, cs:g_DaSiteMgrInstance
0x18003a9f8  call    DaSiteMgrDestroyInstanceStub
0x18003a9fd  xor     ebx, ebx
0x18003a9ff  mov     cs:g_DaSiteMgrInstance, rbx
0x18003aa06  test    rdi, rdi
0x18003aa09  jz      short loc_18003AA4A
0x18003aa0b  mov     r8, rdi
0x18003aa0e  mov     cs:g_DaSiteMgrInstance, rdi
0x18003aa15  lea     rdx, aDasitemgrgpcon_4; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003aa1c  mov     ecx, esi
0x18003aa1e  call    EventWrite0
0x18003aa23  call    DaSiteMgrCreateInstance
0x18003aa28  test    eax, eax
0x18003aa2a  jnz     short loc_18003AA43
0x18003aa2c  mov     rcx, cs:g_DaSiteMgrInstance
0x18003aa33  call    DaSiteMgrDestroyInstanceStub
0x18003aa38  xor     ebx, ebx
0x18003aa3a  mov     cs:g_DaSiteMgrInstance, rbx
0x18003aa41  jmp     short loc_18003AA4A
0x18003aa43  mov     rbx, cs:g_DaSiteMgrInstance
0x18003aa4a  test    rbx, rbx
0x18003aa4d  jnz     short loc_18003AA56
0x18003aa4f  xor     ecx, ecx
0x18003aa51  call    DaSiteMgrUnconfigureSite
0x18003aa56  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18003aa5d  call    cs:__imp_LeaveCriticalSection
0x18003aa64  nop     dword ptr [rax+rax+00h]
0x18003aa69  mov     eax, 0FFFFFFFEh
0x18003aa6e  lock xadd cs:g_DaSiteMgrModuleReferenceObject, eax
0x18003aa76  cmp     eax, 3
0x18003aa79  jnz     short loc_18003AA8E
0x18003aa7b  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hEvent
0x18003aa82  call    cs:__imp_SetEvent
0x18003aa89  nop     dword ptr [rax+rax+00h]
0x18003aa8e  mov     r8, cs:g_DaSiteMgrInstance
0x18003aa95  lea     rdx, aDasitemgrgpcon_2; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003aa9c  mov     ecx, esi
0x18003aa9e  call    EventWrite0
0x18003aaa3  mov     r8d, 0EFh
0x18003aaa9  lea     rdx, aOnecoreuapNetN_46; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003aab0  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18003aab7  mov     rbx, [rsp+28h+arg_0]
0x18003aabc  mov     rsi, [rsp+28h+arg_8]
0x18003aac1  add     rsp, 20h
0x18003aac5  pop     rdi
0x18003aac6  jmp     DereferenceServiceEx
```
