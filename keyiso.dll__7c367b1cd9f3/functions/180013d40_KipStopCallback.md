# KipStopCallback

- ea: `0x180013d40`
- end: `0x180013ddd`
- name: `KipStopCallback`
- size: `157`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000d0ac`
- `0x180013c18`
- `0x180013d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013d5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013d5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013d9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013d9d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013d85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013d85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013dcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d4d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180013dc6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180013dc6`

## pseudocode

```c
__int64 __fastcall KipStopCallback(HANDLE *hMem)
{
  CloseHandle(hMem[1]);
  KipDisableRpcInterface();
  AcquireSRWLockExclusive(&g_ngcFuncLoadLock);
  memset_0(&g_NgcPopKeyFunctions, 0, 0x88u);
  if ( g_NgcPopKeyLibrary )
  {
    FreeLibrary(g_NgcPopKeyLibrary);
    g_NgcPopKeyLibrary = 0;
  }
  ReleaseSRWLockExclusive(&g_ngcFuncLoadLock);
  ServiceStatus.dwCurrentState = 1;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180013d40  push    rbx
0x180013d42  sub     rsp, 20h
0x180013d46  mov     rbx, rcx
0x180013d49  mov     rcx, [rcx+8]; hObject
0x180013d4d  call    cs:__imp_CloseHandle
0x180013d53  call    KipDisableRpcInterface
0x180013d58  lea     rcx, ?g_ngcFuncLoadLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180013d5f  call    cs:__imp_AcquireSRWLockExclusive
0x180013d65  xor     edx, edx; Val
0x180013d67  lea     rcx, ?g_NgcPopKeyFunctions@@3U_NGCPOPKEY_FUNCTION_TABLE@@A; void *
0x180013d6e  mov     r8d, 88h; Size
0x180013d74  call    memset_0
0x180013d79  mov     rcx, cs:?g_NgcPopKeyLibrary@@3PEAUHINSTANCE__@@EA; hLibModule
0x180013d80  test    rcx, rcx
0x180013d83  jz      short loc_180013D96
0x180013d85  call    cs:__imp_FreeLibrary
0x180013d8b  mov     cs:?g_NgcPopKeyLibrary@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_NgcPopKeyLibrary
0x180013d96  lea     rcx, ?g_ngcFuncLoadLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180013d9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180013da3  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180013daa  lea     rdx, ServiceStatus; lpServiceStatus
0x180013db1  mov     cs:ServiceStatus.dwCurrentState, 1
0x180013dbb  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x180013dc6  call    cs:__imp_SetServiceStatus
0x180013dcc  mov     rcx, rbx; hMem
0x180013dcf  call    cs:__imp_LocalFree
0x180013dd5  xor     eax, eax
0x180013dd7  add     rsp, 20h
0x180013ddb  pop     rbx
0x180013ddc  retn
```
