# CsInitializeModule

- ea: `0x1800b0990`
- end: `0x1800b0ae8`
- name: `CsInitializeModule`
- size: `344`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800b0660`
- `0x1800b07b0`

## callees

- `0x1800b0990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0ada`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b099d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b099d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0aad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0a93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0a93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b09e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b09e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b09c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b09c2`
- `rtutils!TracePrintfExA` at `0x1800b0ac8`
- `rtutils!TracePrintfExA` at `0x1800b0ac8`

## string_xrefs

- `0x1800b0a5f`: `CoTaskMemFree`
- `0x1800b09b5`: `OLE32.DLL`
- `0x1800b0a1f`: `CoCreateInstance`

## pseudocode

```c
__int64 CsInitializeModule()
{
  unsigned int v0; // ebx
  HMODULE Library; // rax
  DWORD LastError; // eax

  EnterCriticalSection(&CriticalSection);
  if ( byte_1800FDFA0 )
    goto LABEL_2;
  Library = LoadLibraryExW(L"OLE32.DLL", 0, 0x800u);
  hLibModule = Library;
  if ( Library )
  {
    g_pCoInitializeEx = (__int64)GetProcAddress(Library, "CoInitializeEx");
    if ( g_pCoInitializeEx )
    {
      g_pCoUninitialize = (__int64)GetProcAddress(hLibModule, "CoUninitialize");
      if ( g_pCoUninitialize )
      {
        g_pCoCreateInstance = (__int64)GetProcAddress(hLibModule, "CoCreateInstance");
        if ( g_pCoCreateInstance )
        {
          g_pCoSetProxyBlanket = (__int64)GetProcAddress(hLibModule, "CoSetProxyBlanket");
          if ( g_pCoSetProxyBlanket )
          {
            g_pCoTaskMemFree = (__int64)GetProcAddress(hLibModule, "CoTaskMemFree");
            if ( g_pCoTaskMemFree )
            {
              byte_1800FDFA0 = 1;
LABEL_2:
              v0 = 0;
              goto LABEL_15;
            }
          }
        }
      }
    }
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
  }
  if ( g_dwTraceId != -1 )
  {
    LastError = GetLastError();
    TracePrintfExA(g_dwTraceId, 0xCu, "CsInitializeModule: %d", LastError);
  }
  v0 = 127;
LABEL_15:
  LeaveCriticalSection(&CriticalSection);
  return v0;
}

```

## disassembly

```asm
0x1800b0990  push    rbx
0x1800b0992  sub     rsp, 20h
0x1800b0996  lea     rcx, CriticalSection; lpCriticalSection
0x1800b099d  call    cs:__imp_EnterCriticalSection
0x1800b09a3  cmp     cs:byte_1800FDFA0, 0
0x1800b09aa  jz      short loc_1800B09B3
0x1800b09ac  xor     ebx, ebx
0x1800b09ae  jmp     loc_1800B0AD3
0x1800b09b3  xor     edx, edx; hFile
0x1800b09b5  lea     rcx, c_szOle32Dll; "OLE32.DLL"
0x1800b09bc  mov     r8d, 800h; dwFlags
0x1800b09c2  call    cs:__imp_LoadLibraryExW
0x1800b09c8  mov     cs:hLibModule, rax
0x1800b09cf  test    rax, rax
0x1800b09d2  jz      loc_1800B0AA4
0x1800b09d8  lea     rdx, c_szCoInitializeEx; "CoInitializeEx"
0x1800b09df  mov     rcx, rax; hModule
0x1800b09e2  call    cs:__imp_GetProcAddress
0x1800b09e8  mov     cs:g_pCoInitializeEx, rax
0x1800b09ef  test    rax, rax
0x1800b09f2  jz      loc_1800B0A84
0x1800b09f8  mov     rcx, cs:hLibModule; hModule
0x1800b09ff  lea     rdx, c_szCoUninitialize; "CoUninitialize"
0x1800b0a06  call    cs:__imp_GetProcAddress
0x1800b0a0c  mov     cs:g_pCoUninitialize, rax
0x1800b0a13  test    rax, rax
0x1800b0a16  jz      short loc_1800B0A84
0x1800b0a18  mov     rcx, cs:hLibModule; hModule
0x1800b0a1f  lea     rdx, c_szCoCreateInstance; "CoCreateInstance"
0x1800b0a26  call    cs:__imp_GetProcAddress
0x1800b0a2c  mov     cs:g_pCoCreateInstance, rax
0x1800b0a33  test    rax, rax
0x1800b0a36  jz      short loc_1800B0A84
0x1800b0a38  mov     rcx, cs:hLibModule; hModule
0x1800b0a3f  lea     rdx, c_szCoSetProxyBlanket; "CoSetProxyBlanket"
0x1800b0a46  call    cs:__imp_GetProcAddress
0x1800b0a4c  mov     cs:g_pCoSetProxyBlanket, rax
0x1800b0a53  test    rax, rax
0x1800b0a56  jz      short loc_1800B0A84
0x1800b0a58  mov     rcx, cs:hLibModule; hModule
0x1800b0a5f  lea     rdx, c_szCoTaskMemFree; "CoTaskMemFree"
0x1800b0a66  call    cs:__imp_GetProcAddress
0x1800b0a6c  mov     cs:g_pCoTaskMemFree, rax
0x1800b0a73  test    rax, rax
0x1800b0a76  jz      short loc_1800B0A84
0x1800b0a78  mov     cs:byte_1800FDFA0, 1
0x1800b0a7f  jmp     loc_1800B09AC
0x1800b0a84  mov     rax, cs:hLibModule
0x1800b0a8b  test    rax, rax
0x1800b0a8e  jz      short loc_1800B0AA4
0x1800b0a90  mov     rcx, rax; hLibModule
0x1800b0a93  call    cs:__imp_FreeLibrary
0x1800b0a99  mov     cs:hLibModule, 0
0x1800b0aa4  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800b0aab  jz      short loc_1800B0ACE
0x1800b0aad  call    cs:__imp_GetLastError
0x1800b0ab3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800b0ab9  lea     r8, aCsinitializemo; "CsInitializeModule: %d"
0x1800b0ac0  mov     r9d, eax
0x1800b0ac3  mov     edx, 0Ch; dwFlags
0x1800b0ac8  call    cs:__imp_TracePrintfExA
0x1800b0ace  mov     ebx, 7Fh
0x1800b0ad3  lea     rcx, CriticalSection; lpCriticalSection
0x1800b0ada  call    cs:__imp_LeaveCriticalSection
0x1800b0ae0  mov     eax, ebx
0x1800b0ae2  add     rsp, 20h
0x1800b0ae6  pop     rbx
0x1800b0ae7  retn
```
