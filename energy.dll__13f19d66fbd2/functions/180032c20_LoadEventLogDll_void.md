# LoadEventLogDll(void)

- ea: `0x180032c20`
- end: `0x180032d3a`
- name: `?LoadEventLogDll@@YAKXZ`
- size: `282`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032b3c`

## callees

- `0x180008740`
- `0x180032c20`
- `0x18005eb1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032c76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032c9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032cba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032cda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032cfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032c76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032c9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032cba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032cda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032cfc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032c32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032c32`

## string_xrefs

- `0x180032cd3`: `EvtCreateRenderContext`

## pseudocode

```c
__int64 LoadEventLogDll(void)
{
  HMODULE Library; // rax
  DWORD LastError; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8

  Library = LoadLibraryExW(L"wevtapi", 0, 0);
  EventLogDll = Library;
  if ( !Library
    || (PEvtQuery = (void *(*)(void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int))GetProcAddress(Library, "EvtQuery")) == 0
    || (PEvtNext = (int (*)(void *, unsigned int, void **, unsigned int, unsigned int, unsigned int *))GetProcAddress(EventLogDll, "EvtNext")) == 0
    || (PEvtGetQueryInfo = (int (*)(void *, enum _EVT_QUERY_PROPERTY_ID, unsigned int, struct _EVT_VARIANT *, unsigned int *))GetProcAddress(EventLogDll, "EvtGetQueryInfo")) == 0
    || (PEvtClose = (int (*)(void *))GetProcAddress(EventLogDll, "EvtClose")) == 0
    || (PEvtCreateRenderContext = (void *(*)(unsigned int, const unsigned __int16 **, unsigned int))GetProcAddress(EventLogDll, "EvtCreateRenderContext")) == 0
    || (LastError = 0,
        (PEvtRender = (int (*)(void *, void *, unsigned int, unsigned int, void *, unsigned int *, unsigned int *))GetProcAddress(EventLogDll, "EvtRender")) == 0) )
  {
    LastError = GetLastError();
  }
  if ( EventLogDll && LastError && UnloadEventLogDll() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2, v4);
  return LastError;
}

```

## disassembly

```asm
0x180032c20  push    rbx
0x180032c22  sub     rsp, 20h
0x180032c26  xor     r8d, r8d; dwFlags
0x180032c29  lea     rcx, aWevtapi; "wevtapi"
0x180032c30  xor     edx, edx; hFile
0x180032c32  call    cs:__imp_LoadLibraryExW
0x180032c38  mov     cs:?EventLogDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * EventLogDll
0x180032c3f  test    rax, rax
0x180032c42  jz      loc_180032D0E
0x180032c48  lea     rdx, aEvtquery; "EvtQuery"
0x180032c4f  mov     rcx, rax; hModule
0x180032c52  call    cs:__imp_GetProcAddress
0x180032c58  mov     cs:?PEvtQuery@@3P6APEAXPEAXPEBG1K@ZEA, rax; void * (*PEvtQuery)(void *,ushort const *,ushort const *,ulong)
0x180032c5f  test    rax, rax
0x180032c62  jz      loc_180032D0E
0x180032c68  mov     rcx, cs:?EventLogDll@@3PEAUHINSTANCE__@@EA; hModule
0x180032c6f  lea     rdx, aEvtnext; "EvtNext"
0x180032c76  call    cs:__imp_GetProcAddress
0x180032c7c  mov     cs:?PEvtNext@@3P6AHPEAXKPEAPEAXKKPEAK@ZEA, rax; int (*PEvtNext)(void *,ulong,void * *,ulong,ulong,ulong *)
0x180032c83  test    rax, rax
0x180032c86  jz      loc_180032D0E
0x180032c8c  mov     rcx, cs:?EventLogDll@@3PEAUHINSTANCE__@@EA; hModule
0x180032c93  lea     rdx, aEvtgetqueryinf; "EvtGetQueryInfo"
0x180032c9a  call    cs:__imp_GetProcAddress
0x180032ca0  mov     cs:?PEvtGetQueryInfo@@3P6AHPEAXW4_EVT_QUERY_PROPERTY_ID@@KPEAU_EVT_VARIANT@@PEAK@ZEA, rax; int (*PEvtGetQueryInfo)(void *,_EVT_QUERY_PROPERTY_ID,ulong,_EVT_VARIANT *,ulong *)
0x180032ca7  test    rax, rax
0x180032caa  jz      short loc_180032D0E
0x180032cac  mov     rcx, cs:?EventLogDll@@3PEAUHINSTANCE__@@EA; hModule
0x180032cb3  lea     rdx, aEvtclose; "EvtClose"
0x180032cba  call    cs:__imp_GetProcAddress
0x180032cc0  mov     cs:?PEvtClose@@3P6AHPEAX@ZEA, rax; int (*PEvtClose)(void *)
0x180032cc7  test    rax, rax
0x180032cca  jz      short loc_180032D0E
0x180032ccc  mov     rcx, cs:?EventLogDll@@3PEAUHINSTANCE__@@EA; hModule
0x180032cd3  lea     rdx, aEvtcreaterende; "EvtCreateRenderContext"
0x180032cda  call    cs:__imp_GetProcAddress
0x180032ce0  mov     cs:?PEvtCreateRenderContext@@3P6APEAXKPEAPEBGK@ZEA, rax; void * (*PEvtCreateRenderContext)(ulong,ushort const * *,ulong)
0x180032ce7  test    rax, rax
0x180032cea  jz      short loc_180032D0E
0x180032cec  mov     rcx, cs:?EventLogDll@@3PEAUHINSTANCE__@@EA; hModule
0x180032cf3  lea     rdx, aEvtrender; "EvtRender"
0x180032cfa  xor     ebx, ebx
0x180032cfc  call    cs:__imp_GetProcAddress
0x180032d02  mov     cs:?PEvtRender@@3P6AHPEAX0KK0PEAK1@ZEA, rax; int (*PEvtRender)(void *,void *,ulong,ulong,void *,ulong *,ulong *)
0x180032d09  test    rax, rax
0x180032d0c  jnz     short loc_180032D16
0x180032d0e  call    cs:__imp_GetLastError
0x180032d14  mov     ebx, eax
0x180032d16  cmp     cs:?EventLogDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * EventLogDll
0x180032d1e  jz      short loc_180032D32
0x180032d20  test    ebx, ebx
0x180032d22  jz      short loc_180032D32
0x180032d24  call    ?UnloadEventLogDll@@YAKXZ; UnloadEventLogDll(void)
0x180032d29  test    eax, eax
0x180032d2b  jz      short loc_180032D32
0x180032d2d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032d32  mov     eax, ebx
0x180032d34  add     rsp, 20h
0x180032d38  pop     rbx
0x180032d39  retn
```
