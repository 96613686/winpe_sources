# NlSiteInitializationWrapper_Old(void)

- ea: `0x180044818`
- end: `0x1800449ec`
- name: `?NlSiteInitializationWrapper_Old@@YAKXZ`
- size: `468`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800747cc`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x180007518`
- `0x18000dd00`
- `0x180029c68`
- `0x180044818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044925`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044925`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004486e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004486e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800448ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004497b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800448ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004497b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180044905`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180044905`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800448f6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800448f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800448ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800448ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800449b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800449b6`

## string_xrefs

- `0x18004494e`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x18004488f`: `NlSiteInitializationWrapper: Can't CreateEvent. Error: %u\n`
- `0x1800448da`: `NlSiteInitializationWrapper: Can't CreateThreadpoolWork. Error: %u\n`
- `0x180044997`: `NlSiteInitializationWrapper: GiveInstallHints failed\n`

## pseudocode

```c
__int64 NlSiteInitializationWrapper_Old(void)
{
  HANDLE *v0; // rax
  HANDLE *v1; // rdi
  HANDLE EventW; // rax
  DWORD v4; // eax
  unsigned int v5; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rbx
  DWORD v8; // eax
  DWORD v9; // eax
  char *v10; // r9
  DWORD v11; // eax
  DWORD LastError; // eax
  HANDLE v13; // rcx

  NlPrintRoutine(0x20u, L"Enter NlSiteInitializationWrapper\n");
  v0 = (HANDLE *)NetpMemoryAllocate(16);
  v1 = v0;
  if ( v0 )
  {
    *(_OWORD *)v0 = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    v1[1] = EventW;
    if ( EventW )
    {
      ThreadpoolWork = CreateThreadpoolWork(NlSiteInitializeCallback_Old, v1, 0);
      v7 = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        CloseThreadpoolWork(v7);
        while ( (unsigned int)GiveInstallHints(0) )
        {
          v9 = WaitForSingleObject(v1[1], 0x2710u);
          switch ( v9 )
          {
            case 0u:
              v5 = *(_DWORD *)v1;
              goto LABEL_20;
            case 0xFFFFFFFF:
              LastError = GetLastError();
              NlPrintRoutine(
                0x100u,
                L"NlSiteInitializationWrapper: WaitForSingleObject failed. Last Error: %u\n",
                LastError);
              goto LABEL_19;
            case 0x80u:
              v11 = GetLastError();
              NlPrintRoutine(
                0x100u,
                L"NlSiteInitializationWrapper: WaitForSingleObject returned with WAIT_ABANDONED. Last Error: %u\n",
                v11);
              goto LABEL_19;
          }
          if ( v9 != 258 )
            NlAssertFailed(
              "WaitStatus == WAIT_TIMEOUT",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\nlsite.cxx",
              0x1280u,
              v10);
        }
        NlPrintRoutine(0x100u, L"NlSiteInitializationWrapper: GiveInstallHints failed\n");
      }
      else
      {
        v8 = GetLastError();
        NlPrintRoutine(0x100u, L"NlSiteInitializationWrapper: Can't CreateThreadpoolWork. Error: %u\n", v8);
      }
LABEL_19:
      v5 = 1359;
    }
    else
    {
      v4 = GetLastError();
      NlPrintRoutine(0x100u, L"NlSiteInitializationWrapper: Can't CreateEvent. Error: %u\n", v4);
      v5 = 6;
    }
LABEL_20:
    v13 = v1[1];
    if ( v13 )
      CloseHandle(v13);
    NetpMemoryFree(v1);
    NlPrintRoutine(0x20u, L"NlSiteInitializationWrapper: Exit with status:%ld\n", v5);
    return v5;
  }
  else
  {
    NlPrintRoutine(0x100u, L"NlSiteInitializationWrapper: Failed to allocate the EventAndStatus context\n");
    return 8;
  }
}

```

## disassembly

```asm
0x180044818  mov     [rsp+arg_0], rbx
0x18004481d  push    rdi
0x18004481e  sub     rsp, 20h
0x180044822  lea     rdx, aEnterNlsiteini; "Enter NlSiteInitializationWrapper\n"
0x180044829  mov     ecx, 20h ; ' '; unsigned int
0x18004482e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180044833  mov     ecx, 10h
0x180044838  call    NetpMemoryAllocate
0x18004483d  mov     rdi, rax
0x180044840  test    rax, rax
0x180044843  jnz     short loc_18004485E
0x180044845  lea     rdx, aNlsiteinitiali; "NlSiteInitializationWrapper: Failed to "...
0x18004484c  mov     ecx, 100h; unsigned int
0x180044851  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180044856  lea     eax, [rdi+8]
0x180044859  jmp     loc_1800449E0
0x18004485e  xorps   xmm0, xmm0
0x180044861  xor     r9d, r9d; lpName
0x180044864  xor     r8d, r8d; bInitialState
0x180044867  xor     edx, edx; bManualReset
0x180044869  xor     ecx, ecx; lpEventAttributes
0x18004486b  movups  xmmword ptr [rax], xmm0
0x18004486e  call    cs:__imp_CreateEventW
0x180044875  nop     dword ptr [rax+rax+00h]
0x18004487a  mov     [rdi+8], rax
0x18004487e  test    rax, rax
0x180044881  jnz     short loc_1800448AD
0x180044883  call    cs:__imp_GetLastError
0x18004488a  nop     dword ptr [rax+rax+00h]
0x18004488f  lea     rdx, aNlsiteinitiali_5; "NlSiteInitializationWrapper: Can't Crea"...
0x180044896  mov     ecx, 100h; unsigned int
0x18004489b  mov     r8d, eax
0x18004489e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800448a3  mov     ebx, 6
0x1800448a8  jmp     loc_1800449AD
0x1800448ad  xor     r8d, r8d; pcbe
0x1800448b0  lea     rcx, ?NlSiteInitializeCallback_Old@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800448b7  mov     rdx, rdi; pv
0x1800448ba  call    cs:__imp_CreateThreadpoolWork
0x1800448c1  nop     dword ptr [rax+rax+00h]
0x1800448c6  mov     rbx, rax
0x1800448c9  test    rax, rax
0x1800448cc  jnz     short loc_1800448F3
0x1800448ce  call    cs:__imp_GetLastError
0x1800448d5  nop     dword ptr [rax+rax+00h]
0x1800448da  lea     rdx, aNlsiteinitiali_1; "NlSiteInitializationWrapper: Can't Crea"...
0x1800448e1  mov     r8d, eax
0x1800448e4  mov     ecx, 100h; unsigned int
0x1800448e9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800448ee  jmp     loc_1800449A8
0x1800448f3  mov     rcx, rbx; pwk
0x1800448f6  call    cs:__imp_SubmitThreadpoolWork
0x1800448fd  nop     dword ptr [rax+rax+00h]
0x180044902  mov     rcx, rbx; pwk
0x180044905  call    cs:__imp_CloseThreadpoolWork
0x18004490c  nop     dword ptr [rax+rax+00h]
0x180044911  xor     ecx, ecx; int
0x180044913  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x180044918  test    eax, eax
0x18004491a  jz      short loc_180044997
0x18004491c  mov     rcx, [rdi+8]; hHandle
0x180044920  mov     edx, 2710h; dwMilliseconds
0x180044925  call    cs:__imp_WaitForSingleObject
0x18004492c  nop     dword ptr [rax+rax+00h]
0x180044931  test    eax, eax
0x180044933  jz      short loc_180044993
0x180044935  cmp     eax, 0FFFFFFFFh
0x180044938  jz      short loc_18004497B
0x18004493a  cmp     eax, 80h
0x18004493f  jz      short loc_180044963
0x180044941  cmp     eax, 102h
0x180044946  jz      short loc_180044911
0x180044948  mov     r8d, 1280h; unsigned int
0x18004494e  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180044955  lea     rcx, aWaitstatusWait; "WaitStatus == WAIT_TIMEOUT"
0x18004495c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180044961  jmp     short loc_180044911
0x180044963  call    cs:__imp_GetLastError
0x18004496a  nop     dword ptr [rax+rax+00h]
0x18004496f  lea     rdx, aNlsiteinitiali_2; "NlSiteInitializationWrapper: WaitForSin"...
0x180044976  jmp     loc_1800448E1
0x18004497b  call    cs:__imp_GetLastError
0x180044982  nop     dword ptr [rax+rax+00h]
0x180044987  lea     rdx, aNlsiteinitiali_7; "NlSiteInitializationWrapper: WaitForSin"...
0x18004498e  jmp     loc_1800448E1
0x180044993  mov     ebx, [rdi]
0x180044995  jmp     short loc_1800449AD
0x180044997  lea     rdx, aNlsiteinitiali_4; "NlSiteInitializationWrapper: GiveInstal"...
0x18004499e  mov     ecx, 100h; unsigned int
0x1800449a3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800449a8  mov     ebx, 54Fh
0x1800449ad  mov     rcx, [rdi+8]; hObject
0x1800449b1  test    rcx, rcx
0x1800449b4  jz      short loc_1800449C2
0x1800449b6  call    cs:__imp_CloseHandle
0x1800449bd  nop     dword ptr [rax+rax+00h]
0x1800449c2  mov     rcx, rdi
0x1800449c5  call    NetpMemoryFree
0x1800449ca  mov     r8d, ebx
0x1800449cd  lea     rdx, aNlsiteinitiali_6; "NlSiteInitializationWrapper: Exit with "...
0x1800449d4  mov     ecx, 20h ; ' '; unsigned int
0x1800449d9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800449de  mov     eax, ebx
0x1800449e0  mov     rbx, [rsp+28h+arg_0]
0x1800449e5  add     rsp, 20h
0x1800449e9  pop     rdi
0x1800449ea  retn
```
