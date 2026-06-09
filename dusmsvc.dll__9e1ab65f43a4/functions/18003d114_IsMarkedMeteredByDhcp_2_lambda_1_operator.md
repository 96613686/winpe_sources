# _IsMarkedMeteredByDhcp_::_2_::_lambda_1_::operator()

- ea: `0x18003d114`
- end: `0x18003d1be`
- name: `_IsMarkedMeteredByDhcp_::_2_::_lambda_1_::operator()`
- size: `170`
- prototype: `__int64(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18003d060`

## callees

- `0x180001234`
- `0x180013444`
- `0x18003d114`
- `0x18003d5b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d12d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d12d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d14e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d14e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d181`

## string_xrefs

- `0x18003d120`: `dhcpcsvc.dll`

## pseudocode

```c
__int64 IsMarkedMeteredByDhcp_::_2_::_lambda_1_::operator()(__int64 a1, __int64 a2, __int64 a3, ...)
{
  HMODULE Library; // rax
  __int64 v4; // rcx
  DWORD LastError; // ebx
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rdx
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF
  va_list va; // [rsp+58h] [rbp+20h]
  va_list va1; // [rsp+60h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  Library = LoadLibraryExW(L"dhcpcsvc.dll", 0, 0x800u);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    v4,
    Library);
  if ( g_dhcpModule )
  {
    g_dhcpIsMeteredDetected = (unsigned int (*)(const wchar_t *, int *))GetProcAddress(
                                                                          g_dhcpModule,
                                                                          "DhcpIsMeteredDetected");
    if ( !g_dhcpIsMeteredDetected )
    {
      LastError = GetLastError();
      v6 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
      if ( *v6 > 5u )
      {
        v9 = byte_18005B92D;
LABEL_7:
        LODWORD(v11) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v6,
          (_DWORD)v9,
          v7,
          v8,
          (__int64)va);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
    if ( *v6 > 5u )
    {
      v9 = &byte_18005B8F7;
      goto LABEL_7;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18003d114  mov     [rsp+arg_18], r9
0x18003d119  push    rbx
0x18003d11a  sub     rsp, 30h
0x18003d11e  xor     edx, edx; hFile
0x18003d120  lea     rcx, LibFileName; "dhcpcsvc.dll"
0x18003d127  mov     r8d, 800h; dwFlags
0x18003d12d  call    cs:__imp_LoadLibraryExW
0x18003d133  mov     rdx, rax
0x18003d136  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18003d13b  mov     rcx, cs:?g_dhcpModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18003d142  test    rcx, rcx
0x18003d145  jz      short loc_18003D181
0x18003d147  lea     rdx, ProcName; "DhcpIsMeteredDetected"
0x18003d14e  call    cs:__imp_GetProcAddress
0x18003d154  mov     cs:?g_dhcpIsMeteredDetected@@3P6AKPEB_WPEAH@ZEA, rax; ulong (*g_dhcpIsMeteredDetected)(wchar_t const *,int *)
0x18003d15b  test    rax, rax
0x18003d15e  jnz     short loc_18003D1B3
0x18003d160  call    cs:__imp_GetLastError
0x18003d166  mov     ebx, eax
0x18003d168  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003d16d  mov     rcx, [rax+8]
0x18003d171  mov     edx, [rcx]
0x18003d173  cmp     edx, 5
0x18003d176  jbe     short loc_18003D1B3
0x18003d178  lea     rdx, byte_18005B92D
0x18003d17f  jmp     short loc_18003D1A0
0x18003d181  call    cs:__imp_GetLastError
0x18003d187  mov     ebx, eax
0x18003d189  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003d18e  mov     rcx, [rax+8]
0x18003d192  mov     edx, [rcx]
0x18003d194  cmp     edx, 5
0x18003d197  jbe     short loc_18003D1B3
0x18003d199  lea     rdx, byte_18005B8F7
0x18003d1a0  lea     rax, [rsp+38h+arg_18]
0x18003d1a5  mov     [rsp+38h+var_18], rax
0x18003d1aa  mov     dword ptr [rsp+38h+arg_18], ebx
0x18003d1ae  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003d1b3  mov     eax, 1
0x18003d1b8  add     rsp, 30h
0x18003d1bc  pop     rbx
0x18003d1bd  retn
```
