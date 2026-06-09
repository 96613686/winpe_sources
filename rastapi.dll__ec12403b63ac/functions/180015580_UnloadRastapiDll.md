# UnloadRastapiDll

- ea: `0x180015580`
- end: `0x180015762`
- name: `UnloadRastapiDll`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000232c`

## callees

- `0x1800022a0`
- `0x18000d92c`
- `0x180012340`
- `0x180015580`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001561a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015638`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015681`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001561a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015638`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015681`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001565e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001565e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015654`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001569d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800156e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015654`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001569d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800156e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015722`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015722`
- `rtutils!TraceDeregisterA` at `0x180015756`
- `rtutils!TraceDeregisterA` at `0x180015756`
- `ext-ms-win-ras-tapi32-l1-1-1!lineShutdown` at `0x1800155d3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineShutdown` at `0x1800155d3`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180015710`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180015710`

## string_xrefs

- `0x1800155e8`: `RemovePorts`
- `0x180015669`: `RemoveDevices`
- `0x1800156b2`: `RemoveLines`

## pseudocode

```c
void __fastcall UnloadRastapiDll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  void *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  HLOCAL v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  HLOCAL v17; // rcx

  if ( g_fDllLoaded )
  {
    if ( g_hAsyMac != (HANDLE)-1LL )
    {
      CloseHandle(g_hAsyMac);
      g_hAsyMac = (HANDLE)-1LL;
    }
    if ( g_hAsyncMacSwenum != (HANDLE)-1LL )
    {
      CloseHandle(g_hAsyncMacSwenum);
      g_hAsyncMacSwenum = (HANDLE)-1LL;
    }
    v4 = RasLine;
    if ( RasLine )
    {
      lineShutdown(RasLine);
      RasLine = 0;
    }
    GetMutex(v4, a2, a3, a4);
    RasTapiTrace("RemovePorts");
    v5 = RasPortsList;
    if ( RasPortsList )
    {
      v6 = RasPortsList;
      do
      {
        v7 = (void *)v5[108];
        RasPortsList = (HLOCAL)v6[1];
        if ( v7 )
        {
          LocalFree(v7);
          v5[108] = 0;
          *((_DWORD *)v5 + 218) = 0;
        }
        LocalFree(v5);
        v5 = RasPortsList;
        v6 = RasPortsList;
      }
      while ( RasPortsList );
    }
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    GetMutex(v9, v8, v10, v11);
    RasTapiTrace("RemoveDevices");
    while ( 1 )
    {
      v12 = g_pDeviceInfoList;
      if ( !g_pDeviceInfoList )
        break;
      g_pDeviceInfoList = *(HLOCAL *)g_pDeviceInfoList;
      LocalFree(v12);
    }
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    GetMutex(v14, v13, v15, v16);
    RasTapiTrace("RemoveLines");
    while ( 1 )
    {
      v17 = RasTapiLineInfoList;
      if ( !RasTapiLineInfoList )
        break;
      RasTapiLineInfoList = *(HLOCAL *)RasTapiLineInfoList;
      LocalFree(v17);
    }
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    g_fDllLoaded = 0;
    PostThreadMessageA(TapiThreadId, 0x12u, 0, 0);
    if ( TapiThreadHandle )
    {
      CloseHandle(TapiThreadHandle);
      TapiThreadHandle = 0;
    }
    CleanupDriverIoControl();
    RasTapiTrace("------------------------------------------------------------");
    RasTapiTrace(word_18002E776);
    TraceDeregisterA(dwTraceId);
  }
}

```

## disassembly

```asm
0x180015580  push    rbx
0x180015582  sub     rsp, 20h
0x180015586  cmp     cs:g_fDllLoaded, 0
0x18001558d  jz      loc_18001575C
0x180015593  mov     rcx, cs:g_hAsyMac; hObject
0x18001559a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001559e  cmp     rcx, rbx
0x1800155a1  jz      short loc_1800155B0
0x1800155a3  call    cs:__imp_CloseHandle
0x1800155a9  mov     cs:g_hAsyMac, rbx
0x1800155b0  mov     rcx, cs:g_hAsyncMacSwenum; hObject
0x1800155b7  cmp     rcx, rbx
0x1800155ba  jz      short loc_1800155C9
0x1800155bc  call    cs:__imp_CloseHandle
0x1800155c2  mov     cs:g_hAsyncMacSwenum, rbx
0x1800155c9  mov     ecx, cs:RasLine; hLineApp
0x1800155cf  test    ecx, ecx
0x1800155d1  jz      short loc_1800155E3
0x1800155d3  call    cs:__imp_lineShutdown
0x1800155d9  mov     cs:RasLine, 0
0x1800155e3  call    GetMutex
0x1800155e8  lea     rcx, aRemoveports; "RemovePorts"
0x1800155ef  call    RasTapiTrace
0x1800155f4  mov     rbx, cs:RasPortsList
0x1800155fb  test    rbx, rbx
0x1800155fe  jz      short loc_18001564D
0x180015600  mov     rax, rbx
0x180015603  mov     rcx, [rbx+360h]; hMem
0x18001560a  mov     rax, [rax+8]
0x18001560e  mov     cs:RasPortsList, rax
0x180015615  test    rcx, rcx
0x180015618  jz      short loc_180015635
0x18001561a  call    cs:__imp_LocalFree
0x180015620  mov     qword ptr [rbx+360h], 0
0x18001562b  mov     dword ptr [rbx+368h], 0
0x180015635  mov     rcx, rbx; hMem
0x180015638  call    cs:__imp_LocalFree
0x18001563e  mov     rbx, cs:RasPortsList
0x180015645  mov     rax, rbx
0x180015648  test    rbx, rbx
0x18001564b  jnz     short loc_180015603
0x18001564d  mov     rcx, cs:RasTapiMutex; hMutex
0x180015654  call    cs:__imp_ReleaseMutex
0x18001565a  test    eax, eax
0x18001565c  jnz     short loc_180015664
0x18001565e  call    cs:__imp_GetLastError
0x180015664  call    GetMutex
0x180015669  lea     rcx, aRemovedevices; "RemoveDevices"
0x180015670  call    RasTapiTrace
0x180015675  jmp     short loc_180015687
0x180015677  mov     rax, [rax]
0x18001567a  mov     cs:g_pDeviceInfoList, rax
0x180015681  call    cs:__imp_LocalFree
0x180015687  mov     rax, cs:g_pDeviceInfoList
0x18001568e  mov     rcx, rax; hMem
0x180015691  test    rax, rax
0x180015694  jnz     short loc_180015677
0x180015696  mov     rcx, cs:RasTapiMutex; hMutex
0x18001569d  call    cs:__imp_ReleaseMutex
0x1800156a3  test    eax, eax
0x1800156a5  jnz     short loc_1800156AD
0x1800156a7  call    cs:__imp_GetLastError
0x1800156ad  call    GetMutex
0x1800156b2  lea     rcx, aRemovelines; "RemoveLines"
0x1800156b9  call    RasTapiTrace
0x1800156be  jmp     short loc_1800156D0
0x1800156c0  mov     rax, [rax]
0x1800156c3  mov     cs:RasTapiLineInfoList, rax
0x1800156ca  call    cs:__imp_LocalFree
0x1800156d0  mov     rax, cs:RasTapiLineInfoList
0x1800156d7  mov     rcx, rax; hMem
0x1800156da  test    rax, rax
0x1800156dd  jnz     short loc_1800156C0
0x1800156df  mov     rcx, cs:RasTapiMutex; hMutex
0x1800156e6  call    cs:__imp_ReleaseMutex
0x1800156ec  test    eax, eax
0x1800156ee  jnz     short loc_1800156F6
0x1800156f0  call    cs:__imp_GetLastError
0x1800156f6  mov     ecx, cs:TapiThreadId; idThread
0x1800156fc  xor     r9d, r9d; lParam
0x1800156ff  xor     r8d, r8d; wParam
0x180015702  mov     cs:g_fDllLoaded, 0
0x18001570c  lea     edx, [r9+12h]; Msg
0x180015710  call    cs:__imp_PostThreadMessageA
0x180015716  mov     rcx, cs:TapiThreadHandle; hObject
0x18001571d  test    rcx, rcx
0x180015720  jz      short loc_180015733
0x180015722  call    cs:__imp_CloseHandle
0x180015728  mov     cs:TapiThreadHandle, 0
0x180015733  call    CleanupDriverIoControl
0x180015738  lea     rcx, asc_180030180; "---------------------------------------"...
0x18001573f  call    RasTapiTrace
0x180015744  lea     rcx, word_18002E776; lpszFormat
0x18001574b  call    RasTapiTrace
0x180015750  mov     ecx, cs:dwTraceId; dwTraceID
0x180015756  call    cs:__imp_TraceDeregisterA
0x18001575c  add     rsp, 20h
0x180015760  pop     rbx
0x180015761  retn
```
