# DaSiteMgrInitialize

- ea: `0x18006f8d0`
- end: `0x18006f9e1`
- name: `DaSiteMgrInitialize`
- size: `273`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f60`
- `0x18000d7c0`
- `0x18002dcc0`
- `0x18003a940`
- `0x18006f8d0`
- `0x18006fa5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f9b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f9b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f906`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f906`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8ee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f8ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f925`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f938`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f925`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f950`

## string_xrefs

- `0x18006f979`: `onecoreuap\net\netio\iphlpsvc\service\stmgr.c`
- `0x18006f9ca`: `onecoreuap\net\netio\iphlpsvc\service\stmgr.c`
- `0x18006f980`: `DaSiteMgrGpConfigurationChangeNotification`
- `0x18006f997`: `DaSiteMgrInitialize calls DaSiteMgrGpConfigurationChangeNotification`

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
0x18006f8d0  sub     rsp, 28h
0x18006f8d4  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006f8db  call    cs:__imp_InitializeCriticalSection
0x18006f8e2  nop     dword ptr [rax+rax+00h]
0x18006f8e7  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18006f8ee  call    cs:__imp_InitializeCriticalSection
0x18006f8f5  nop     dword ptr [rax+rax+00h]
0x18006f8fa  xor     r9d, r9d; lpName
0x18006f8fd  xor     r8d, r8d; bInitialState
0x18006f900  xor     ecx, ecx; lpEventAttributes
0x18006f902  lea     edx, [r9+1]; bManualReset
0x18006f906  call    cs:__imp_CreateEventW
0x18006f90d  nop     dword ptr [rax+rax+00h]
0x18006f912  mov     cs:g_DaSiteMgrModuleReferenceObjectEvent, rax
0x18006f919  test    rax, rax
0x18006f91c  jnz     short loc_18006F969
0x18006f91e  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18006f925  call    cs:__imp_DeleteCriticalSection
0x18006f92c  nop     dword ptr [rax+rax+00h]
0x18006f931  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006f938  call    cs:__imp_DeleteCriticalSection
0x18006f93f  nop     dword ptr [rax+rax+00h]
0x18006f944  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hObject
0x18006f94b  test    rcx, rcx
0x18006f94e  jz      short loc_18006F9B1
0x18006f950  call    cs:__imp_CloseHandle
0x18006f957  nop     dword ptr [rax+rax+00h]
0x18006f95c  mov     cs:g_DaSiteMgrModuleReferenceObjectEvent, 0
0x18006f967  jmp     short loc_18006F9B1
0x18006f969  mov     r8d, 59h ; 'Y'
0x18006f96f  mov     cs:g_DaSiteMgrModuleReferenceObject, 2
0x18006f979  lea     rdx, aOnecoreuapNetN_46; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f980  lea     rcx, aDasitemgrgpcon; "DaSiteMgrGpConfigurationChangeNotificat"...
0x18006f987  call    ReferenceServiceEx
0x18006f98c  test    eax, eax
0x18006f98e  jnz     short loc_18006F997
0x18006f990  call    DaSiteMgrUninitialize
0x18006f995  jmp     short loc_18006F9B1
0x18006f997  lea     rdx, aDasitemgriniti; "DaSiteMgrInitialize calls DaSiteMgrGpCo"...
0x18006f99e  mov     ecx, 80000000h
0x18006f9a3  call    EventWrite0
0x18006f9a8  xor     edx, edx; Context
0x18006f9aa  xor     ecx, ecx; Instance
0x18006f9ac  call    DaSiteMgrGpConfigurationChangeNotification
0x18006f9b1  mov     rcx, cs:g_DaSiteMgrStartCompleteEvent; hEvent
0x18006f9b8  call    cs:__imp_SetEvent
0x18006f9bf  nop     dword ptr [rax+rax+00h]
0x18006f9c4  mov     r8d, 72h ; 'r'
0x18006f9ca  lea     rdx, aOnecoreuapNetN_46; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f9d1  lea     rcx, aInitializedasi; "InitializeDaSiteMgr"
0x18006f9d8  add     rsp, 28h
0x18006f9dc  jmp     DereferenceServiceEx
```
