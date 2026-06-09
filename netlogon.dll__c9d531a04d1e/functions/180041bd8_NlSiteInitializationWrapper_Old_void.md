# NlSiteInitializationWrapper_Old(void)

- ea: `0x180041bd8`
- end: `0x180041d6c`
- name: `?NlSiteInitializationWrapper_Old@@YAKXZ`
- size: `404`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18006f490`

## callees

- `0x180003200`
- `0x180003670`
- `0x180007278`
- `0x18000d710`
- `0x180028750`
- `0x180041bd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041cc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041cc1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041c2e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180041ca7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180041ca7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180041c9e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180041c9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180041c6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180041c6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041d3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041d3d`

## string_xrefs

- `0x180041ce4`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x180041c43`: `NlSiteInitializationWrapper: Can't CreateEvent. Error: %u\n`
- `0x180041c82`: `NlSiteInitializationWrapper: Can't CreateThreadpoolWork. Error: %u\n`
- `0x180041d1e`: `NlSiteInitializationWrapper: GiveInstallHints failed\n`

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
              4736,
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
0x180041bd8  mov     [rsp+arg_0], rbx
0x180041bdd  push    rdi
0x180041bde  sub     rsp, 20h
0x180041be2  lea     rdx, aEnterNlsiteini; "Enter NlSiteInitializationWrapper\n"
0x180041be9  mov     ecx, 20h ; ' '; unsigned int
0x180041bee  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041bf3  mov     ecx, 10h
0x180041bf8  call    NetpMemoryAllocate
0x180041bfd  mov     rdi, rax
0x180041c00  test    rax, rax
0x180041c03  jnz     short loc_180041C1E
0x180041c05  lea     rdx, aNlsiteinitiali; "NlSiteInitializationWrapper: Failed to "...
0x180041c0c  mov     ecx, 100h; unsigned int
0x180041c11  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041c16  lea     eax, [rdi+8]
0x180041c19  jmp     loc_180041D61
0x180041c1e  xorps   xmm0, xmm0
0x180041c21  xor     r9d, r9d; lpName
0x180041c24  xor     r8d, r8d; bInitialState
0x180041c27  xor     edx, edx; bManualReset
0x180041c29  xor     ecx, ecx; lpEventAttributes
0x180041c2b  movups  xmmword ptr [rax], xmm0
0x180041c2e  call    cs:__imp_CreateEventW
0x180041c34  mov     [rdi+8], rax
0x180041c38  test    rax, rax
0x180041c3b  jnz     short loc_180041C61
0x180041c3d  call    cs:__imp_GetLastError
0x180041c43  lea     rdx, aNlsiteinitiali_5; "NlSiteInitializationWrapper: Can't Crea"...
0x180041c4a  mov     ecx, 100h; unsigned int
0x180041c4f  mov     r8d, eax
0x180041c52  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041c57  mov     ebx, 6
0x180041c5c  jmp     loc_180041D34
0x180041c61  xor     r8d, r8d; pcbe
0x180041c64  lea     rcx, ?NlSiteInitializeCallback_Old@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180041c6b  mov     rdx, rdi; pv
0x180041c6e  call    cs:__imp_CreateThreadpoolWork
0x180041c74  mov     rbx, rax
0x180041c77  test    rax, rax
0x180041c7a  jnz     short loc_180041C9B
0x180041c7c  call    cs:__imp_GetLastError
0x180041c82  lea     rdx, aNlsiteinitiali_1; "NlSiteInitializationWrapper: Can't Crea"...
0x180041c89  mov     r8d, eax
0x180041c8c  mov     ecx, 100h; unsigned int
0x180041c91  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041c96  jmp     loc_180041D2F
0x180041c9b  mov     rcx, rbx; pwk
0x180041c9e  call    cs:__imp_SubmitThreadpoolWork
0x180041ca4  mov     rcx, rbx; pwk
0x180041ca7  call    cs:__imp_CloseThreadpoolWork
0x180041cad  xor     ecx, ecx; int
0x180041caf  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x180041cb4  test    eax, eax
0x180041cb6  jz      short loc_180041D1E
0x180041cb8  mov     rcx, [rdi+8]; hHandle
0x180041cbc  mov     edx, 2710h; dwMilliseconds
0x180041cc1  call    cs:__imp_WaitForSingleObject
0x180041cc7  test    eax, eax
0x180041cc9  jz      short loc_180041D1A
0x180041ccb  cmp     eax, 0FFFFFFFFh
0x180041cce  jz      short loc_180041D08
0x180041cd0  cmp     eax, 80h
0x180041cd5  jz      short loc_180041CF9
0x180041cd7  cmp     eax, 102h
0x180041cdc  jz      short loc_180041CAD
0x180041cde  mov     r8d, 1280h; unsigned int
0x180041ce4  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180041ceb  lea     rcx, aWaitstatusWait; "WaitStatus == WAIT_TIMEOUT"
0x180041cf2  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180041cf7  jmp     short loc_180041CAD
0x180041cf9  call    cs:__imp_GetLastError
0x180041cff  lea     rdx, aNlsiteinitiali_2; "NlSiteInitializationWrapper: WaitForSin"...
0x180041d06  jmp     short loc_180041C89
0x180041d08  call    cs:__imp_GetLastError
0x180041d0e  lea     rdx, aNlsiteinitiali_7; "NlSiteInitializationWrapper: WaitForSin"...
0x180041d15  jmp     loc_180041C89
0x180041d1a  mov     ebx, [rdi]
0x180041d1c  jmp     short loc_180041D34
0x180041d1e  lea     rdx, aNlsiteinitiali_4; "NlSiteInitializationWrapper: GiveInstal"...
0x180041d25  mov     ecx, 100h; unsigned int
0x180041d2a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041d2f  mov     ebx, 54Fh
0x180041d34  mov     rcx, [rdi+8]; hObject
0x180041d38  test    rcx, rcx
0x180041d3b  jz      short loc_180041D43
0x180041d3d  call    cs:__imp_CloseHandle
0x180041d43  mov     rcx, rdi
0x180041d46  call    NetpMemoryFree
0x180041d4b  mov     r8d, ebx
0x180041d4e  lea     rdx, aNlsiteinitiali_6; "NlSiteInitializationWrapper: Exit with "...
0x180041d55  mov     ecx, 20h ; ' '; unsigned int
0x180041d5a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041d5f  mov     eax, ebx
0x180041d61  mov     rbx, [rsp+28h+arg_0]
0x180041d66  add     rsp, 20h
0x180041d6a  pop     rdi
0x180041d6b  retn
```
