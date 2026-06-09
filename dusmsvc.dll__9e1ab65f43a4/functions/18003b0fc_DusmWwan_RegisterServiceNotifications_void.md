# DusmWwan::RegisterServiceNotifications(void)

- ea: `0x18003b0fc`
- end: `0x18003b2c6`
- name: `?RegisterServiceNotifications@DusmWwan@@AEAAKXZ`
- size: `458`
- prototype: `unsigned int __fastcall(DusmWwan *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180039db4`

## callees

- `0x180001234`
- `0x18000438c`
- `0x180007c90`
- `0x180013444`
- `0x180030cf4`
- `0x18003b0fc`
- `0x18003b56c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b146`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003b193`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003b193`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003b12f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003b12f`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18003b1f3`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18003b1f3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003b24b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003b24b`

## pseudocode

```c
DWORD __fastcall DusmWwan::RegisterServiceNotifications(DusmWwan *this)
{
  DusmWwan *v1; // rdi
  SC_HANDLE v2; // rax
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  SC_HANDLE *v7; // rsi
  SC_HANDLE v8; // rax
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD v12; // ebx
  _DWORD *v13; // r8
  __int64 v14; // r9
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  wil *v18; // rcx
  wil *v19; // rcx
  DWORD v20; // ebx
  const wil::ResultException *v21; // rdi
  _DWORD *v22; // r8
  __int64 v23; // r9
  DWORD v24; // eax
  DWORD v25; // edi
  DWORD v26; // ebx
  _DWORD *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  DWORD dwCurrentState; // [rsp+50h] [rbp-68h] BYREF
  DWORD v31; // [rsp+54h] [rbp-64h] BYREF
  SC_HANDLE v32; // [rsp+58h] [rbp-60h] BYREF
  int v33; // [rsp+60h] [rbp-58h] BYREF
  const WCHAR *v34; // [rsp+68h] [rbp-50h] BYREF
  const wchar_t *v35; // [rsp+70h] [rbp-48h] BYREF
  const wil::ResultException *v36; // [rsp+78h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-38h] BYREF

  v1 = DusmWwan::s_pInstance;
  v2 = OpenSCManagerW(0, 0, 5u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    v1,
    v2);
  if ( !*(_QWORD *)v1 )
    return GetLastError();
  v4 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
  if ( *v4 > 5u )
  {
    v32 = *(SC_HANDLE *)v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (int)v4,
      (int)byte_18005A7FB,
      v5,
      v6,
      (__int64)&v32);
  }
  v7 = (SC_HANDLE *)((char *)v1 + 8);
  v8 = OpenServiceW(*(SC_HANDLE *)v1, L"wwansvc", 4u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    (char *)v1 + 8,
    v8);
  if ( !*((_QWORD *)v1 + 1) )
    return GetLastError();
  v9 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
  if ( *v9 > 5u )
  {
    v32 = *v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (int)v9,
      (int)byte_18005A62D,
      v10,
      v11,
      (__int64)&v32);
  }
  v12 = SubscribeServiceChangeNotifications(*v7, 2, DusmWwan::ServiceNotificationCallback, v1, (char *)v1 + 16);
  v13 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
  if ( *v13 > 5u )
  {
    dwCurrentState = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)v13,
      (int)&unk_18005A688,
      (__int64)v13,
      v14,
      (__int64)&dwCurrentState);
  }
  if ( !v12 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(*v7, &ServiceStatus) )
    {
      v15 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
      if ( *v15 > 5u )
      {
        dwCurrentState = ServiceStatus.dwCurrentState;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)v15,
          (int)&byte_18005A58F,
          v16,
          v17,
          (__int64)&dwCurrentState);
      }
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        try
        {
          DusmWwan::Start(v1);
        }
        catch ( const wil::ResultException *v36 )
        {
          if ( (wil::ResultFromCaughtException(v18) & 0x1FFF0000) == 0x70000 )
            v20 = (unsigned __int16)wil::ResultFromCaughtException(v19);
          else
            v20 = wil::ResultFromCaughtException(v19);
          dwCurrentState = v20;
          v21 = v36;
          v22 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
          if ( *v22 > 5u )
          {
            v34 = (const WCHAR *)*((_QWORD *)v21 + 6);
            v33 = *((_DWORD *)v21 + 22);
            v35 = (const wchar_t *)*((_QWORD *)v21 + 10);
            v31 = *((_DWORD *)v21 + 8);
            LODWORD(v32) = v20;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
              (int)v22,
              (int)&byte_18005A5E7,
              (__int64)v22,
              v23,
              (__int64)&v32,
              (__int64)&v31,
              &v35,
              (__int64)&v33,
              &v34);
          }
          return dwCurrentState;
        }
        catch ( ... )
        {
          v24 = wil::ResultFromCaughtException(v18);
          v25 = v24;
          v26 = (unsigned __int16)v24;
          if ( (v24 & 0x1FFF0000) != 0x70000 )
            v26 = v24;
          dwCurrentState = v26;
          v27 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
          if ( *v27 > 5u )
          {
            LODWORD(v32) = v25;
            v31 = v26;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (int)v27,
              (int)&word_18005A51E,
              v28,
              v29,
              (__int64)&v31,
              (__int64)&v32);
          }
          return dwCurrentState;
        }
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18003b0fc  mov     [rsp+arg_0], rbx
0x18003b101  mov     [rsp+arg_8], rsi
0x18003b106  push    rdi
0x18003b107  sub     rsp, 0B0h
0x18003b10e  mov     rax, cs:__security_cookie
0x18003b115  xor     rax, rsp
0x18003b118  mov     [rsp+0B8h+var_18], rax
0x18003b120  mov     rdi, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; DusmWwan * DusmWwan::s_pInstance
0x18003b127  xor     edx, edx; lpDatabaseName
0x18003b129  xor     ecx, ecx; lpMachineName
0x18003b12b  lea     r8d, [rdx+5]; dwDesiredAccess
0x18003b12f  call    cs:__imp_OpenSCManagerW
0x18003b135  mov     rdx, rax
0x18003b138  mov     rcx, rdi
0x18003b13b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x18003b140  cmp     qword ptr [rdi], 0
0x18003b144  jnz     short loc_18003B151
0x18003b146  call    cs:__imp_GetLastError
0x18003b14c  jmp     loc_18003B2A1
0x18003b151  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b156  mov     rcx, [rax+8]
0x18003b15a  mov     eax, [rcx]
0x18003b15c  cmp     eax, 5
0x18003b15f  jbe     short loc_18003B17F
0x18003b161  mov     rax, [rdi]
0x18003b164  mov     [rsp+0B8h+var_60], rax
0x18003b169  lea     rax, [rsp+0B8h+var_60]
0x18003b16e  mov     [rsp+0B8h+var_98], rax
0x18003b173  lea     rdx, byte_18005A7FB
0x18003b17a  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003b17f  lea     rsi, [rdi+8]
0x18003b183  mov     r8d, 4; dwDesiredAccess
0x18003b189  lea     rdx, aWwansvc; "wwansvc"
0x18003b190  mov     rcx, [rdi]; hSCManager
0x18003b193  call    cs:__imp_OpenServiceW
0x18003b199  mov     rdx, rax
0x18003b19c  mov     rcx, rsi
0x18003b19f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x18003b1a4  cmp     qword ptr [rsi], 0
0x18003b1a8  jz      short loc_18003B146
0x18003b1aa  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b1af  mov     rcx, [rax+8]
0x18003b1b3  mov     eax, [rcx]
0x18003b1b5  cmp     eax, 5
0x18003b1b8  jbe     short loc_18003B1D8
0x18003b1ba  mov     rax, [rsi]
0x18003b1bd  mov     [rsp+0B8h+var_60], rax
0x18003b1c2  lea     rax, [rsp+0B8h+var_60]
0x18003b1c7  mov     [rsp+0B8h+var_98], rax
0x18003b1cc  lea     rdx, byte_18005A62D
0x18003b1d3  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003b1d8  lea     rax, [rdi+10h]
0x18003b1dc  mov     [rsp+0B8h+var_98], rax
0x18003b1e1  mov     r9, rdi
0x18003b1e4  lea     r8, ?ServiceNotificationCallback@DusmWwan@@CAXKPEAX@Z; DusmWwan::ServiceNotificationCallback(ulong,void *)
0x18003b1eb  mov     edx, 2
0x18003b1f0  mov     rcx, [rsi]
0x18003b1f3  call    cs:__imp_SubscribeServiceChangeNotifications
0x18003b1f9  mov     ebx, eax
0x18003b1fb  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b200  mov     r8, [rax+8]
0x18003b204  mov     ecx, [r8]
0x18003b207  cmp     ecx, 5
0x18003b20a  jbe     short loc_18003B229
0x18003b20c  mov     [rsp+0B8h+var_68], ebx
0x18003b210  lea     rax, [rsp+0B8h+var_68]
0x18003b215  mov     [rsp+0B8h+var_98], rax
0x18003b21a  lea     rdx, unk_18005A688
0x18003b221  mov     rcx, r8
0x18003b224  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003b229  test    ebx, ebx
0x18003b22b  jnz     short loc_18003B29F
0x18003b22d  xorps   xmm0, xmm0
0x18003b230  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwServiceType], xmm0
0x18003b238  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003b240  lea     rdx, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x18003b248  mov     rcx, [rsi]; hService
0x18003b24b  call    cs:__imp_QueryServiceStatus
0x18003b251  test    eax, eax
0x18003b253  jz      short loc_18003B29F
0x18003b255  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b25a  mov     rcx, [rax+8]
0x18003b25e  mov     eax, [rcx]
0x18003b260  cmp     eax, 5
0x18003b263  jbe     short loc_18003B286
0x18003b265  mov     eax, [rsp+0B8h+ServiceStatus.dwCurrentState]
0x18003b26c  mov     [rsp+0B8h+var_68], eax
0x18003b270  lea     rax, [rsp+0B8h+var_68]
0x18003b275  mov     [rsp+0B8h+var_98], rax
0x18003b27a  lea     rdx, byte_18005A58F
0x18003b281  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003b286  cmp     [rsp+0B8h+ServiceStatus.dwCurrentState], 4
0x18003b28e  jnz     short loc_18003B29F
0x18003b290  mov     rcx, rdi; this
0x18003b293  call    ?Start@DusmWwan@@AEAAXXZ; DusmWwan::Start(void)
0x18003b298  nop
0x18003b299  jmp     short loc_18003B29F
0x18003b29b  mov     ebx, [rsp+0B8h+var_68]
0x18003b29f  mov     eax, ebx
0x18003b2a1  mov     rcx, [rsp+0B8h+var_18]
0x18003b2a9  xor     rcx, rsp; StackCookie
0x18003b2ac  call    __security_check_cookie
0x18003b2b1  lea     r11, [rsp+0B8h+var_8]
0x18003b2b9  mov     rbx, [r11+10h]
0x18003b2bd  mov     rsi, [r11+18h]
0x18003b2c1  mov     rsp, r11
0x18003b2c4  pop     rdi
0x18003b2c5  retn
```
