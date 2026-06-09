# DusmWlanCloudSync::LoadWifiCloudStoreInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18003d610`
- end: `0x18003d6bd`
- name: `?LoadWifiCloudStoreInitOnceCallback@DusmWlanCloudSync@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800021e4`
- `0x180013444`
- `0x18003d610`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d63f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d63f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d679`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d679`

## string_xrefs

- `0x18003d632`: `WiFiCloudStore.dll`

## pseudocode

```c
__int64 __fastcall DusmWlanCloudSync::LoadWifiCloudStoreInitOnceCallback(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  HMODULE Library; // rax
  _DWORD *v5; // rcx
  _DWORD *v6; // rcx

  if ( !byte_1800688FC )
    return 0;
  Library = hModule;
  if ( !hModule )
  {
    Library = LoadLibraryExW(L"WiFiCloudStore.dll", 0, 0x800u);
    hModule = Library;
    if ( !Library )
    {
      v5 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
      if ( *v5 > 3u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v5,
          byte_18005BA73);
LABEL_10:
      byte_1800688FC = 0;
      return 0;
    }
  }
  DusmWlanCloudSync::g_functionTriggerCloudSyncOnCostChange = (int (*)(const struct _GUID *, const wchar_t *, int))GetProcAddress(Library, "TriggerCloudSyncOnCostChange");
  if ( !DusmWlanCloudSync::g_functionTriggerCloudSyncOnCostChange )
  {
    v6 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
    if ( *v6 > 2u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v6,
        byte_18005BAE5);
    goto LABEL_10;
  }
  return 1;
}

```

## disassembly

```asm
0x18003d610  sub     rsp, 28h
0x18003d614  cmp     cs:byte_1800688FC, 0
0x18003d61b  jnz     short loc_18003D624
0x18003d61d  xor     eax, eax
0x18003d61f  jmp     loc_18003D6B8
0x18003d624  mov     rax, cs:hModule
0x18003d62b  test    rax, rax
0x18003d62e  jnz     short loc_18003D66F
0x18003d630  xor     edx, edx; hFile
0x18003d632  lea     rcx, aWificloudstore; "WiFiCloudStore.dll"
0x18003d639  mov     r8d, 800h; dwFlags
0x18003d63f  call    cs:__imp_LoadLibraryExW
0x18003d645  mov     cs:hModule, rax
0x18003d64c  test    rax, rax
0x18003d64f  jnz     short loc_18003D66F
0x18003d651  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003d656  mov     rcx, [rax+8]
0x18003d65a  mov     eax, [rcx]
0x18003d65c  cmp     eax, 3
0x18003d65f  jbe     short loc_18003D6A7
0x18003d661  lea     rdx, byte_18005BA73
0x18003d668  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003d66d  jmp     short loc_18003D6A7
0x18003d66f  lea     rdx, aTriggercloudsy; "TriggerCloudSyncOnCostChange"
0x18003d676  mov     rcx, rax; hModule
0x18003d679  call    cs:__imp_GetProcAddress
0x18003d67f  mov     cs:?g_functionTriggerCloudSyncOnCostChange@DusmWlanCloudSync@@3P6AJPEBU_GUID@@PEB_WH@ZEA, rax; long (*DusmWlanCloudSync::g_functionTriggerCloudSyncOnCostChange)(_GUID const *,wchar_t const *,int)
0x18003d686  test    rax, rax
0x18003d689  jnz     short loc_18003D6B3
0x18003d68b  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003d690  mov     rcx, [rax+8]
0x18003d694  mov     eax, [rcx]
0x18003d696  cmp     eax, 2
0x18003d699  jbe     short loc_18003D6A7
0x18003d69b  lea     rdx, byte_18005BAE5
0x18003d6a2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003d6a7  mov     cs:byte_1800688FC, 0
0x18003d6ae  jmp     loc_18003D61D
0x18003d6b3  mov     eax, 1
0x18003d6b8  add     rsp, 28h
0x18003d6bc  retn
```
