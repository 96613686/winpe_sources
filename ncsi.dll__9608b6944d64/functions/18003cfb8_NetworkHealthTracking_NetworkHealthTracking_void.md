# NetworkHealthTracking::NetworkHealthTracking(void)

- ea: `0x18003cfb8`
- end: `0x18003d040`
- name: `??0NetworkHealthTracking@@QEAA@XZ`
- size: `136`
- prototype: `NetworkHealthTracking *__fastcall(NetworkHealthTracking *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009230`

## callees

- `0x180027850`
- `0x18003cfb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003cffa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003cffa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003d02e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003d02e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18003cfc8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18003cfc8`

## string_xrefs

- `0x18003cff3`: `wcmapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
NetworkHealthTracking *__fastcall NetworkHealthTracking::NetworkHealthTracking(NetworkHealthTracking *this)
{
  HMODULE Library; // rax
  __int64 v2; // rcx

  InitializeCriticalSectionEx(&g_ncsiNetHealthTracking, 0, 0);
  qword_18009D7D8 = 0;
  xmmword_18009D7E0 = 0;
  byte_18009D7F0 = 0;
  Library = LoadLibraryExW(L"wcmapi.dll", 0, 0x800u);
  if ( Library )
  {
    g_isWcmApiPresent = 1;
    FreeLibrary(Library);
  }
  else
  {
    g_isWcmApiPresent = 0;
    if ( (unsigned int)dword_18009A048 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v2,
        (unsigned __int8 *)qword_18008D2C0);
  }
  return (NetworkHealthTracking *)&g_ncsiNetHealthTracking;
}

```

## disassembly

```asm
0x18003cfb8  sub     rsp, 28h
0x18003cfbc  xor     r8d, r8d; Flags
0x18003cfbf  lea     rcx, ?g_ncsiNetHealthTracking@@3VNetworkHealthTracking@@A; lpCriticalSection
0x18003cfc6  xor     edx, edx; dwSpinCount
0x18003cfc8  call    cs:__imp_InitializeCriticalSectionEx
0x18003cfce  xorps   xmm0, xmm0
0x18003cfd1  mov     cs:qword_18009D7D8, 0
0x18003cfdc  xor     edx, edx; hFile
0x18003cfde  movdqa  cs:xmmword_18009D7E0, xmm0
0x18003cfe6  mov     r8d, 800h; dwFlags
0x18003cfec  mov     cs:byte_18009D7F0, 0
0x18003cff3  lea     rcx, LibFileName; "wcmapi.dll"
0x18003cffa  call    cs:__imp_LoadLibraryExW
0x18003d000  test    rax, rax
0x18003d003  jnz     short loc_18003D024
0x18003d005  mov     cs:?g_isWcmApiPresent@@3_NA, al; bool g_isWcmApiPresent
0x18003d00b  mov     eax, cs:dword_18009A048
0x18003d011  cmp     eax, 5
0x18003d014  jbe     short loc_18003D034
0x18003d016  lea     rdx, qword_18008D2C0
0x18003d01d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003d022  jmp     short loc_18003D034
0x18003d024  mov     rcx, rax; hLibModule
0x18003d027  mov     cs:?g_isWcmApiPresent@@3_NA, 1; bool g_isWcmApiPresent
0x18003d02e  call    cs:__imp_FreeLibrary
0x18003d034  lea     rax, ?g_ncsiNetHealthTracking@@3VNetworkHealthTracking@@A; NetworkHealthTracking g_ncsiNetHealthTracking
0x18003d03b  add     rsp, 28h
0x18003d03f  retn
```
