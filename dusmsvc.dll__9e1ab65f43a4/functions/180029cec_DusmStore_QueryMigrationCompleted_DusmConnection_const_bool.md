# DusmStore::QueryMigrationCompleted(DusmConnection const &,bool *)

- ea: `0x180029cec`
- end: `0x180029df2`
- name: `?QueryMigrationCompleted@DusmStore@@SAKAEBVDusmConnection@@PEA_N@Z`
- size: `262`
- prototype: `unsigned int __fastcall(const struct DusmConnection *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037984`
- `0x18003a1e4`

## callees

- `0x180005324`
- `0x180013444`
- `0x18001742c`
- `0x180026fa0`
- `0x180027bf4`
- `0x180029cec`
- `0x18002de88`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029d60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029d60`

## string_xrefs

- `0x180029d4f`: `MigrationCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DusmStore::QueryMigrationCompleted(const struct DusmConnection *a1, bool *a2)
{
  unsigned int ValueW; // ebx
  unsigned int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  HKEY hkey; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+48h] [rbp-30h] BYREF
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h] BYREF

  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  ValueW = DusmStore::OpenMigrationKey(a1, 0, &hkey);
  if ( !ValueW )
  {
    v5 = *((_DWORD *)a1 + 4);
    ValueW = RegGetValueW(hkey, 0, L"MigrationCompleted", 0x10u, 0, 0, 0);
    if ( ValueW == 2 )
    {
      *a2 = 0;
LABEL_8:
      ValueW = 0;
      goto LABEL_9;
    }
    if ( !ValueW )
    {
      *a2 = 1;
      goto LABEL_8;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v8, v7) + 8) > 2u )
    {
      v14 = (__int64)L"MigrationCompleted";
      v15 = DusmMediaTypeToSz(v5);
      LODWORD(v13) = ValueW;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v9,
        (int)&byte_180058623,
        v9,
        v10,
        (__int64)&v13,
        (const WCHAR **)&v15,
        (const WCHAR **)&v14);
    }
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return ValueW;
}

```

## disassembly

```asm
0x180029cec  mov     [rsp+arg_10], rbx
0x180029cf1  push    rsi
0x180029cf2  push    rdi
0x180029cf3  push    r14
0x180029cf5  sub     rsp, 60h
0x180029cf9  mov     rdi, rdx
0x180029cfc  mov     rsi, rcx
0x180029cff  mov     [rsp+78h+hkey], 0
0x180029d08  xor     edx, edx
0x180029d0a  lea     rcx, [rsp+78h+hkey]
0x180029d0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029d14  lea     r8, [rsp+78h+hkey]; HKEY *
0x180029d19  xor     edx, edx; bool
0x180029d1b  mov     rcx, rsi; struct DusmConnection *
0x180029d1e  call    ?OpenMigrationKey@DusmStore@@SAKAEBVDusmConnection@@_NPEAPEAUHKEY__@@@Z; DusmStore::OpenMigrationKey(DusmConnection const &,bool,HKEY__ * *)
0x180029d23  mov     ebx, eax
0x180029d25  test    eax, eax
0x180029d27  jnz     loc_180029DD5
0x180029d2d  mov     esi, [rsi+10h]
0x180029d30  mov     [rsp+78h+pcbData], 0; pcbData
0x180029d39  mov     [rsp+78h+pvData], 0; pvData
0x180029d42  mov     [rsp+78h+pdwType], 0; pdwType
0x180029d4b  lea     r9d, [rax+10h]; dwFlags
0x180029d4f  lea     r14, aMigrationcompl; "MigrationCompleted"
0x180029d56  mov     r8, r14; lpValue
0x180029d59  xor     edx, edx; lpSubKey
0x180029d5b  mov     rcx, [rsp+78h+hkey]; hkey
0x180029d60  call    cs:__imp_RegGetValueW
0x180029d66  mov     ebx, eax
0x180029d68  cmp     eax, 2
0x180029d6b  jnz     short loc_180029D72
0x180029d6d  mov     byte ptr [rdi], 0
0x180029d70  jmp     short loc_180029DD3
0x180029d72  test    ebx, ebx
0x180029d74  jz      short loc_180029DD0
0x180029d76  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029d7b  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180029d80  mov     r8, [rax+8]
0x180029d84  mov     eax, [r8]
0x180029d87  cmp     eax, 2
0x180029d8a  jbe     short loc_180029DD5
0x180029d8c  mov     [rsp+78h+var_28], r14
0x180029d91  mov     ecx, esi
0x180029d93  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x180029d98  mov     [rsp+78h+var_20], rax
0x180029d9d  mov     dword ptr [rsp+78h+var_30], ebx
0x180029da1  lea     rax, [rsp+78h+var_28]
0x180029da6  mov     [rsp+78h+pcbData], rax; __int64
0x180029dab  lea     rax, [rsp+78h+var_20]
0x180029db0  mov     [rsp+78h+pvData], rax; __int64
0x180029db5  lea     rax, [rsp+78h+var_30]
0x180029dba  mov     [rsp+78h+pdwType], rax; __int64
0x180029dbf  lea     rdx, byte_180058623; int
0x180029dc6  mov     rcx, r8; int
0x180029dc9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180029dce  jmp     short loc_180029DD5
0x180029dd0  mov     byte ptr [rdi], 1
0x180029dd3  xor     ebx, ebx
0x180029dd5  lea     rcx, [rsp+78h+hkey]
0x180029dda  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029ddf  mov     eax, ebx
0x180029de1  mov     rbx, [rsp+78h+arg_10]
0x180029de9  add     rsp, 60h
0x180029ded  pop     r14
0x180029def  pop     rdi
0x180029df0  pop     rsi
0x180029df1  retn
```
