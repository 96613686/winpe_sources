# DaSiteMgrInitialize

- ea: `0x18006f8b0`
- end: `0x18006f9c1`
- name: `DaSiteMgrInitialize`
- size: `273`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f50`
- `0x18000d7b0`
- `0x18002dcb0`
- `0x18003a930`
- `0x18006f8b0`
- `0x18006fa3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f998`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f998`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f8e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f8e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8ce`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f905`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f918`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f905`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f918`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f930`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f930`

## string_xrefs

- `0x18006f959`: `onecoreuap\net\netio\iphlpsvc\service\stmgr.c`
- `0x18006f9aa`: `onecoreuap\net\netio\iphlpsvc\service\stmgr.c`
- `0x18006f960`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x18006f977`: `DaSiteMgrInitialize calls DaSiteMgrGpConfigurationChangeNotification`

## pseudocode

```c
void __fastcall DaSiteMgrInitialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  InitializeCriticalSection(&g_DaSiteMgrLock);
  InitializeCriticalSection(&g_DaSiteMgrConfigLock);
  g_DaSiteMgrModuleReferenceObjectEvent = CreateEventW(0, 1, 0, 0);
  if ( g_DaSiteMgrModuleReferenceObjectEvent )
  {
    g_DaSiteMgrModuleReferenceObject = 2;
    if ( (unsigned int)ReferenceServiceEx(
                         "DaSiteMgrGpConfigurationChangeNotification",
                         L"onecoreuap\\net\\netio\\iphlpsvc\\service\\stmgr.c",
                         89) )
    {
      EventWrite0(0x80000000LL, L"DaSiteMgrInitialize calls DaSiteMgrGpConfigurationChangeNotification");
      DaSiteMgrGpConfigurationChangeNotification(0, 0);
    }
    else
    {
      DaSiteMgrUninitialize();
    }
  }
  else
  {
    DeleteCriticalSection(&g_DaSiteMgrConfigLock);
    DeleteCriticalSection(&g_DaSiteMgrLock);
    if ( g_DaSiteMgrModuleReferenceObjectEvent )
    {
      CloseHandle(g_DaSiteMgrModuleReferenceObjectEvent);
      g_DaSiteMgrModuleReferenceObjectEvent = 0;
    }
  }
  SetEvent(g_DaSiteMgrStartCompleteEvent);
  DereferenceServiceEx("InitializeDaSiteMgr", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\stmgr.c", 114);
}

```

## disassembly

```asm
0x18006f8b0  sub     rsp, 28h
0x18006f8b4  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006f8bb  call    cs:__imp_InitializeCriticalSection
0x18006f8c2  nop     dword ptr [rax+rax+00h]
0x18006f8c7  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18006f8ce  call    cs:__imp_InitializeCriticalSection
0x18006f8d5  nop     dword ptr [rax+rax+00h]
0x18006f8da  xor     r9d, r9d; lpName
0x18006f8dd  xor     r8d, r8d; bInitialState
0x18006f8e0  xor     ecx, ecx; lpEventAttributes
0x18006f8e2  lea     edx, [r9+1]; bManualReset
0x18006f8e6  call    cs:__imp_CreateEventW
0x18006f8ed  nop     dword ptr [rax+rax+00h]
0x18006f8f2  mov     cs:g_DaSiteMgrModuleReferenceObjectEvent, rax
0x18006f8f9  test    rax, rax
0x18006f8fc  jnz     short loc_18006F949
0x18006f8fe  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18006f905  call    cs:__imp_DeleteCriticalSection
0x18006f90c  nop     dword ptr [rax+rax+00h]
0x18006f911  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006f918  call    cs:__imp_DeleteCriticalSection
0x18006f91f  nop     dword ptr [rax+rax+00h]
0x18006f924  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hObject
0x18006f92b  test    rcx, rcx
0x18006f92e  jz      short loc_18006F991
0x18006f930  call    cs:__imp_CloseHandle
0x18006f937  nop     dword ptr [rax+rax+00h]
0x18006f93c  mov     cs:g_DaSiteMgrModuleReferenceObjectEvent, 0
0x18006f947  jmp     short loc_18006F991
0x18006f949  mov     r8d, 59h ; 'Y'
0x18006f94f  mov     cs:g_DaSiteMgrModuleReferenceObject, 2
0x18006f959  lea     rdx, aOnecoreuapNetN_46; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f960  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18006f967  call    ReferenceServiceEx
0x18006f96c  test    eax, eax
0x18006f96e  jnz     short loc_18006F977
0x18006f970  call    DaSiteMgrUninitialize
0x18006f975  jmp     short loc_18006F991
0x18006f977  lea     rdx, aDasitemgriniti; "DaSiteMgrInitialize calls DaSiteMgrGpCo"...
0x18006f97e  mov     ecx, 80000000h
0x18006f983  call    EventWrite0
0x18006f988  xor     edx, edx; Context
0x18006f98a  xor     ecx, ecx; Instance
0x18006f98c  call    DaSiteMgrGpConfigurationChangeNotification
0x18006f991  mov     rcx, cs:g_DaSiteMgrStartCompleteEvent; hEvent
0x18006f998  call    cs:__imp_SetEvent
0x18006f99f  nop     dword ptr [rax+rax+00h]
0x18006f9a4  mov     r8d, 72h ; 'r'
0x18006f9aa  lea     rdx, aOnecoreuapNetN_46; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f9b1  lea     rcx, aInitializedasi; "InitializeDaSiteMgr"
0x18006f9b8  add     rsp, 28h
0x18006f9bc  jmp     DereferenceServiceEx
```
