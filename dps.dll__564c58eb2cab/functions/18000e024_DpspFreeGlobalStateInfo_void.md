# DpspFreeGlobalStateInfo(void)

- ea: `0x18000e024`
- end: `0x18000e1ad`
- name: `?DpspFreeGlobalStateInfo@@YAXXZ`
- size: `393`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f774`

## callees

- `0x180008ea0`
- `0x18000e024`
- `0x18000f45c`
- `0x18000f71c`
- `0x180019010`

## import_xrefs

- `ntdll!TpReleaseAlpcCompletion` at `0x18000e158`
- `ntdll!TpReleaseAlpcCompletion` at `0x18000e158`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e103`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e13f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e103`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e13f`

## pseudocode

```c
void DpspFreeGlobalStateInfo(void)
{
  WdipDeleteServerPortName();
  WdipFree(g_pLocalSysSid);
  g_pLocalSysSid = 0;
  WdipFree(g_pLocalServSid);
  g_pLocalServSid = 0;
  WdipFree(g_pNullSid);
  g_pNullSid = 0;
  WdipFree(g_pAdminSid);
  g_pAdminSid = 0;
  WdipFree(g_pEveryoneSid);
  g_pEveryoneSid = 0;
  WdipFree(g_WdiDir);
  g_WdiDir = 0;
  WdipFree(g_PreAllocatedBuffer);
  g_PreAllocatedBuffer = 0;
  if ( (char *)g_hServerPort - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hServerPort);
    g_hServerPort = 0;
  }
  if ( (char *)g_hWorkerShutdown - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hWorkerShutdown);
    g_hWorkerShutdown = 0;
  }
  if ( (char *)g_hTPShutdown - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hTPShutdown);
    g_hTPShutdown = 0;
  }
  if ( (char *)g_hGroupPolicyControl - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hGroupPolicyControl);
    g_hGroupPolicyControl = 0;
  }
  if ( (char *)g_hDataRetentionControl - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hDataRetentionControl);
    g_hDataRetentionControl = 0;
  }
  if ( g_pAlpcCompletion )
  {
    TpReleaseAlpcCompletion();
    g_pAlpcCompletion = 0;
  }
  if ( g_pTaskService )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pTaskService + 16LL))(g_pTaskService);
    g_pTaskService = 0;
  }
  if ( g_pTaskFolder )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pTaskFolder + 16LL))(g_pTaskFolder);
    g_pTaskFolder = 0;
  }
  DpspDeleteCriticalSections();
}

```

## disassembly

```asm
0x18000e024  push    rbx
0x18000e026  sub     rsp, 20h
0x18000e02a  call    ?WdipDeleteServerPortName@@YAJXZ; WdipDeleteServerPortName(void)
0x18000e02f  mov     rcx, cs:g_pLocalSysSid
0x18000e036  call    WdipFree
0x18000e03b  mov     rcx, cs:g_pLocalServSid
0x18000e042  xor     ebx, ebx
0x18000e044  mov     cs:g_pLocalSysSid, rbx
0x18000e04b  call    WdipFree
0x18000e050  mov     rcx, cs:g_pNullSid
0x18000e057  mov     cs:g_pLocalServSid, rbx
0x18000e05e  call    WdipFree
0x18000e063  mov     rcx, cs:g_pAdminSid
0x18000e06a  mov     cs:g_pNullSid, rbx
0x18000e071  call    WdipFree
0x18000e076  mov     rcx, cs:g_pEveryoneSid
0x18000e07d  mov     cs:g_pAdminSid, rbx
0x18000e084  call    WdipFree
0x18000e089  mov     rcx, cs:g_WdiDir
0x18000e090  mov     cs:g_pEveryoneSid, rbx
0x18000e097  call    WdipFree
0x18000e09c  mov     rcx, cs:g_PreAllocatedBuffer
0x18000e0a3  mov     cs:g_WdiDir, rbx
0x18000e0aa  call    WdipFree
0x18000e0af  mov     rcx, cs:g_hServerPort; hObject
0x18000e0b6  mov     cs:g_PreAllocatedBuffer, rbx
0x18000e0bd  lea     rax, [rcx-1]
0x18000e0c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e0c5  ja      short loc_18000E0D4
0x18000e0c7  call    cs:__imp_CloseHandle
0x18000e0cd  mov     cs:g_hServerPort, rbx
0x18000e0d4  mov     rcx, cs:g_hWorkerShutdown; hObject
0x18000e0db  lea     rax, [rcx-1]
0x18000e0df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e0e3  ja      short loc_18000E0F2
0x18000e0e5  call    cs:__imp_CloseHandle
0x18000e0eb  mov     cs:g_hWorkerShutdown, rbx
0x18000e0f2  mov     rcx, cs:g_hTPShutdown; hObject
0x18000e0f9  lea     rax, [rcx-1]
0x18000e0fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e101  ja      short loc_18000E110
0x18000e103  call    cs:__imp_CloseHandle
0x18000e109  mov     cs:g_hTPShutdown, rbx
0x18000e110  mov     rcx, cs:g_hGroupPolicyControl; hObject
0x18000e117  lea     rax, [rcx-1]
0x18000e11b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e11f  ja      short loc_18000E12E
0x18000e121  call    cs:__imp_CloseHandle
0x18000e127  mov     cs:g_hGroupPolicyControl, rbx
0x18000e12e  mov     rcx, cs:g_hDataRetentionControl; hObject
0x18000e135  lea     rax, [rcx-1]
0x18000e139  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e13d  ja      short loc_18000E14C
0x18000e13f  call    cs:__imp_CloseHandle
0x18000e145  mov     cs:g_hDataRetentionControl, rbx
0x18000e14c  mov     rcx, cs:g_pAlpcCompletion
0x18000e153  test    rcx, rcx
0x18000e156  jz      short loc_18000E165
0x18000e158  call    cs:__imp_TpReleaseAlpcCompletion
0x18000e15e  mov     cs:g_pAlpcCompletion, rbx
0x18000e165  mov     rcx, cs:g_pTaskService
0x18000e16c  test    rcx, rcx
0x18000e16f  jz      short loc_18000E184
0x18000e171  mov     rax, [rcx]
0x18000e174  mov     rax, [rax+10h]
0x18000e178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17d  mov     cs:g_pTaskService, rbx
0x18000e184  mov     rcx, cs:g_pTaskFolder
0x18000e18b  test    rcx, rcx
0x18000e18e  jz      short loc_18000E1A3
0x18000e190  mov     rax, [rcx]
0x18000e193  mov     rax, [rax+10h]
0x18000e197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e19c  mov     cs:g_pTaskFolder, rbx
0x18000e1a3  add     rsp, 20h
0x18000e1a7  pop     rbx
0x18000e1a8  jmp     DpspDeleteCriticalSections
```
