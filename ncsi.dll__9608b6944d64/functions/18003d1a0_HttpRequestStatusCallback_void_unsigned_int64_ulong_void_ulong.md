# HttpRequestStatusCallback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x18003d1a0`
- end: `0x18003d912`
- name: `?HttpRequestStatusCallback@@YAXPEAX_KK0K@Z`
- size: `1906`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021d8`
- `0x18000840c`
- `0x18000e59c`
- `0x18001814c`
- `0x18001a0e0`
- `0x180026b80`
- `0x180027850`
- `0x18002b84c`
- `0x18002bad4`
- `0x18002cea4`
- `0x18002d454`
- `0x18003d1a0`
- `0x180047240`
- `0x180047f78`
- `0x18004f5f0`
- `0x180055860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d811`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d811`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d847`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d1e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d571`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d5ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d5ca`
- `WINHTTP!WinHttpReceiveResponse` at `0x18003d242`
- `WINHTTP!WinHttpReceiveResponse` at `0x18003d242`
- `WINHTTP!WinHttpQueryHeaders` at `0x18003d56b`
- `WINHTTP!WinHttpQueryHeaders` at `0x18003d605`
- `WINHTTP!WinHttpQueryHeaders` at `0x18003d66e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18003d56b`
- `WINHTTP!WinHttpQueryHeaders` at `0x18003d605`
- `WINHTTP!WinHttpQueryHeaders` at `0x18003d66e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18003d339`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18003d699`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18003d339`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18003d699`
- `WINHTTP!WinHttpReadData` at `0x18003d49f`
- `WINHTTP!WinHttpReadData` at `0x18003d49f`
- `IPHLPAPI!ParseNetworkString` at `0x18003d7b5`
- `IPHLPAPI!ParseNetworkString` at `0x18003d7b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HttpRequestStatusCallback(
        HINTERNET hInternet,
        DWORD_PTR dwContext,
        DWORD dwInternetStatus,
        const size_t *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  size_t *v9; // r13
  void *v10; // rdx
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  BOOL v14; // eax
  const char *v15; // r9
  _QWORD *v16; // rsi
  __int64 v17; // rcx
  _QWORD *v18; // r15
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  size_t v21; // r14
  size_t v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  BOOL v26; // eax
  const char *v27; // r9
  __int64 v29; // rax
  LPVOID *v30; // rdi
  char *v31; // rdx
  unsigned __int64 v32; // rcx
  size_t v33; // r8
  size_t v34; // rbx
  BOOL Data; // eax
  const char *v36; // r9
  __int64 v37; // rax
  DWORD v38; // ecx
  DWORD v39; // ebx
  DWORD v40; // eax
  SIZE_T v41; // rdx
  HLOCAL v42; // rax
  const char *v43; // r9
  const char *v44; // r9
  BOOL DataAvailable; // eax
  const char *v46; // r9
  wil::details::in1diag3 *v48; // rdx
  _QWORD *v49; // rax
  void *v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // eax
  DWORD_PTR v55; // rcx
  void *v56; // rdx
  int lpdwBufferLength; // [rsp+20h] [rbp-288h]
  int lpdwBufferLengtha; // [rsp+20h] [rbp-288h]
  HLOCAL v59; // [rsp+30h] [rbp-278h] BYREF
  size_t *v60; // [rsp+38h] [rbp-270h] BYREF
  DWORD_PTR v61; // [rsp+40h] [rbp-268h]
  DWORD dwBufferLength; // [rsp+48h] [rbp-260h] BYREF
  DWORD dwNumberOfBytesToRead; // [rsp+4Ch] [rbp-25Ch] BYREF
  int v64; // [rsp+50h] [rbp-258h] BYREF
  _OWORD v65[32]; // [rsp+54h] [rbp-254h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v61 = dwContext;
  v9 = (size_t *)(dwContext + 256);
  EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 256));
  try
  {
    v60 = v9;
    dwNumberOfBytesToRead = 0;
    if ( dwInternetStatus != 2 )
    {
      if ( dwInternetStatus == 8 )
      {
        memset_0(&v64, 0, 0x210u);
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          v60 = (size_t *)lpvStatusInformation;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v51,
            (int)byte_18008DD61,
            v52,
            v53,
            (const size_t **)&v60);
        }
        if ( !(unsigned int)ParseNetworkString(lpvStatusInformation, 9, &v64) )
        {
          if ( v64 == 2 )
          {
            memset_0((void *)(dwContext + 72), 0, 0x70u);
            *(_OWORD *)(dwContext + 56) = v65[0];
          }
          else if ( v64 == 3 )
          {
            memset_0((void *)(dwContext + 84), 0, 0x64u);
            *(_OWORD *)(dwContext + 56) = v65[0];
            *(_OWORD *)(dwContext + 68) = *(_OWORD *)((char *)v65 + 12);
          }
        }
        goto LABEL_90;
      }
      if ( dwInternetStatus == 2048 )
      {
        if ( dwStatusInformationLength != 8 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v11);
          if ( dwStatusInformationLength < 8 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
              (const char *)0x8000FFFFLL,
              lpdwBufferLength);
        }
        if ( (unsigned int)dword_18009A048 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            (__int64)retaddr,
            (unsigned __int8 *)byte_18008DCCD);
        v11 = (wil::details::in1diag3 *)dwContext;
        v48 = (wil::details::in1diag3 *)(dwContext + 24);
        do
        {
          if ( *(_QWORD *)v11 == *lpvStatusInformation )
            *(_QWORD *)v11 = 0;
          v11 = (wil::details::in1diag3 *)((char *)v11 + 8);
        }
        while ( v11 != v48 );
        v49 = (_QWORD *)dwContext;
        while ( !*v49 )
        {
          if ( ++v49 == (_QWORD *)v48 )
          {
            if ( (unsigned int)dword_18009A048 > 5 )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                (__int64)v11,
                (unsigned __int8 *)&word_18008DCA6);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
              &v60,
              0);
            wil::details::SetEvent(*(wil::details **)(dwContext + 32), v50);
            v9 = v60;
            goto LABEL_90;
          }
        }
        goto LABEL_90;
      }
      if ( dwInternetStatus == 0x20000 )
      {
        dwBufferLength = 0;
        WinHttpQueryHeaders(hInternet, 0x21u, 0, 0, &dwBufferLength, 0);
        if ( GetLastError() == 122 )
        {
          v38 = dwBufferLength;
          if ( dwBufferLength )
          {
            v39 = dwBufferLength & 1;
            if ( (dwBufferLength & 1) != 0 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(dwBufferLength);
              v38 = dwBufferLength;
            }
            v40 = v39 + v38;
            v41 = 0xFFFFFFFFLL;
            if ( v39 + v38 >= v38 )
              v41 = v40;
            dwBufferLength = v41;
            if ( v40 < v38 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xA2,
                (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
                v40 < v38 ? (const char *)0x80070216LL : 0,
                lpdwBufferLengtha);
            v42 = LocalAlloc(0x40u, v41);
            v59 = v42;
            if ( !v42 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xA6,
                (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
                (const char *)0x8007000ELL,
                lpdwBufferLengtha);
            if ( !WinHttpQueryHeaders(hInternet, 0x21u, 0, v42, &dwBufferLength, 0) )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0xA9,
                (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
                v43);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              dwContext + 192,
              &v59);
            *(_DWORD *)(dwContext + 200) = dwBufferLength >> 1;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v59);
          }
        }
        dwNumberOfBytesToRead = 4;
        if ( !WinHttpQueryHeaders(hInternet, 0x20000013u, 0, (LPVOID)(dwContext + 204), &dwNumberOfBytesToRead, 0) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xB7,
            (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
            v44);
        if ( (unsigned int)(*(_DWORD *)(dwContext + 204) - 200) <= 0x63 )
        {
          DataAvailable = WinHttpQueryDataAvailable(hInternet, 0);
          v11 = retaddr;
          if ( !DataAvailable )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xBD,
              (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
              v46);
          goto LABEL_90;
        }
      }
      else if ( dwInternetStatus == 0x40000 )
      {
        if ( dwStatusInformationLength != 4 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v11);
          if ( dwStatusInformationLength < 4 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
              (const char *)0x8000FFFFLL,
              lpdwBufferLength);
        }
        v29 = *(unsigned int *)lpvStatusInformation;
        dwNumberOfBytesToRead = v29;
        if ( !(_DWORD)v29 )
        {
          wil::details::SetEvent(*(wil::details **)(dwContext + 24), v10);
          if ( (unsigned int)dword_18009A048 > 5 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              (__int64)v11,
              (unsigned __int8 *)&dword_18008DAB4);
          goto LABEL_90;
        }
        if ( (unsigned __int64)(*(_QWORD *)(dwContext + 240) + v29 - *(_QWORD *)(dwContext + 232)) <= 0x10000 )
        {
          if ( (unsigned int)dword_18009A048 > 5 )
          {
            v59 = (HLOCAL)(*(_QWORD *)(dwContext + 240) - *(_QWORD *)(dwContext + 232));
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
              (__int64)retaddr,
              (int)&word_18008DC6E,
              v12,
              v13,
              (__int64)&v59);
          }
          v30 = (LPVOID *)(dwContext + 208);
          v31 = (char *)*v30;
          v32 = (_BYTE *)v30[1] - (_BYTE *)*v30;
          if ( dwNumberOfBytesToRead >= v32 )
          {
            if ( dwNumberOfBytesToRead > v32 )
            {
              if ( dwNumberOfBytesToRead <= (unsigned __int64)((_BYTE *)v30[2] - v31) )
              {
                v33 = dwNumberOfBytesToRead - v32;
                v34 = (size_t)v30[1] + v33;
                memset_0(v30[1], 0, v33);
                v30[1] = (LPVOID)v34;
              }
              else
              {
                std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v30, dwNumberOfBytesToRead);
              }
            }
          }
          else
          {
            v30[1] = &v31[dwNumberOfBytesToRead];
          }
          Data = WinHttpReadData(hInternet, *v30, dwNumberOfBytesToRead, 0);
          v11 = retaddr;
          if ( !Data )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xFB,
              (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
              v36);
          goto LABEL_90;
        }
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          dwBufferLength = dwNumberOfBytesToRead;
          v60 = (size_t *)(*(_QWORD *)(dwContext + 240) - *(_QWORD *)(dwContext + 232));
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            (__int64)retaddr,
            (int)byte_18008DC09,
            v12,
            v13,
            (__int64)&v60,
            (__int64)&dwBufferLength);
        }
        v37 = *(_QWORD *)(dwContext + 232);
        if ( v37 != *(_QWORD *)(dwContext + 240) )
          *(_QWORD *)(dwContext + 240) = v37;
      }
      else
      {
        if ( dwInternetStatus != 0x80000 )
        {
          if ( dwInternetStatus == 0x400000 )
          {
            v14 = WinHttpReceiveResponse(hInternet, 0);
            v11 = retaddr;
            if ( !v14 )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0xEB,
                (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
                v15);
          }
          goto LABEL_90;
        }
        v16 = (_QWORD *)(dwContext + 232);
        v17 = dwStatusInformationLength;
        if ( (unsigned __int64)dwStatusInformationLength + *(_QWORD *)(dwContext + 240) - *(_QWORD *)(dwContext + 232) <= 0x10000 )
        {
          v18 = (_QWORD *)(dwContext + 208);
          if ( *(_QWORD *)(dwContext + 216) - *(_QWORD *)(dwContext + 208) < (unsigned __int64)dwStatusInformationLength )
            MicrosoftTelemetryAssertTriggeredNoArgs(dwStatusInformationLength);
          v19 = *v18;
          v20 = *(_QWORD *)(dwContext + 216) - *(_QWORD *)(dwContext + 208);
          if ( dwStatusInformationLength >= v20 )
          {
            if ( dwStatusInformationLength > v20 )
            {
              if ( dwStatusInformationLength <= (unsigned __int64)(*(_QWORD *)(dwContext + 224) - v19) )
              {
                v21 = dwStatusInformationLength - v20;
                v22 = v21 + *(_QWORD *)(dwContext + 216);
                memset_0(*(void **)(dwContext + 216), 0, v21);
                *(_QWORD *)(dwContext + 216) = v22;
              }
              else
              {
                std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
                  dwContext + 208,
                  dwStatusInformationLength);
              }
            }
          }
          else
          {
            *(_QWORD *)(dwContext + 216) = dwStatusInformationLength + v19;
          }
          std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(
            dwContext + 232,
            *(_QWORD *)(dwContext + 240),
            *v18,
            *(_QWORD *)(dwContext + 216) - *v18);
          if ( (unsigned int)dword_18009A048 > 5 )
          {
            v59 = (HLOCAL)(*(_QWORD *)(dwContext + 240) - *v16);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
              v23,
              (int)&word_18008DBCE,
              v24,
              v25,
              (__int64)&v59);
          }
          v26 = WinHttpQueryDataAvailable(hInternet, 0);
          v11 = retaddr;
          if ( !v26 )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xD6,
              (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
              v27);
          goto LABEL_90;
        }
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          dwBufferLength = dwStatusInformationLength;
          v59 = (HLOCAL)(*(_QWORD *)(dwContext + 240) - *v16);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            dwStatusInformationLength,
            (int)byte_18008DB63,
            v12,
            v13,
            (__int64)&v59,
            (__int64)&dwBufferLength);
        }
        MicrosoftTelemetryAssertTriggeredNoArgs(v17);
        if ( *(_QWORD *)(dwContext + 232) != *(_QWORD *)(dwContext + 240) )
          *(_QWORD *)(dwContext + 240) = *v16;
      }
      wil::details::SetEvent(*(wil::details **)(dwContext + 24), v10);
LABEL_90:
      if ( v9 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v9);
      return;
    }
    *(_BYTE *)(dwContext + 40) = 1;
    if ( v9 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v9);
  }
  catch ( ... )
  {
    v54 = wil::ResultFromCaughtException(v11);
    v55 = v61;
    *(_DWORD *)(v61 + 184) = v54;
    wil::details::SetEvent(*(wil::details **)(v55 + 24), v56);
  }
}

```

## disassembly

```asm
0x18003d1a0  push    rbx
0x18003d1a2  push    rsi
0x18003d1a3  push    rdi
0x18003d1a4  push    r12
0x18003d1a6  push    r13
0x18003d1a8  push    r14
0x18003d1aa  push    r15
0x18003d1ac  sub     rsp, 270h
0x18003d1b3  mov     rax, cs:__security_cookie
0x18003d1ba  xor     rax, rsp
0x18003d1bd  mov     [rsp+2A8h+var_48], rax
0x18003d1c5  mov     rsi, r9
0x18003d1c8  mov     ebx, r8d
0x18003d1cb  mov     rdi, rdx
0x18003d1ce  mov     r12, rcx
0x18003d1d1  mov     [rsp+2A8h+var_268], rdx
0x18003d1d6  lea     r13, [rdx+100h]
0x18003d1dd  mov     rcx, r13; lpCriticalSection
0x18003d1e0  call    cs:__imp_EnterCriticalSection
0x18003d1e6  mov     [rsp+2A8h+var_270], r13
0x18003d1eb  xor     r15d, r15d
0x18003d1ee  mov     [rsp+2A8h+dwNumberOfBytesToRead], r15d
0x18003d1f3  cmp     ebx, 2
0x18003d1f6  jz      loc_18003D83B
0x18003d1fc  cmp     ebx, 8
0x18003d1ff  jz      loc_18003D769
0x18003d205  cmp     ebx, 800h
0x18003d20b  jz      loc_18003D6B4
0x18003d211  cmp     ebx, 20000h
0x18003d217  jz      loc_18003D548
0x18003d21d  cmp     ebx, 40000h
0x18003d223  jz      loc_18003D3AA
0x18003d229  cmp     ebx, 80000h
0x18003d22f  jz      short loc_18003D25D
0x18003d231  cmp     ebx, 400000h
0x18003d237  jnz     loc_18003D809
0x18003d23d  xor     edx, edx; lpReserved
0x18003d23f  mov     rcx, r12; hRequest
0x18003d242  call    cs:__imp_WinHttpReceiveResponse
0x18003d248  mov     rcx, [rsp+2A8h]; this
0x18003d250  test    eax, eax
0x18003d252  jz      loc_18003D84F
0x18003d258  jmp     loc_18003D809
0x18003d25d  lea     rsi, [rdi+0E8h]
0x18003d264  mov     ecx, [rsp+2A8h+dwStatusInformationLength]
0x18003d26b  mov     r14d, ecx
0x18003d26e  mov     rax, [rsi+8]
0x18003d272  sub     rax, [rsi]
0x18003d275  add     rax, rcx
0x18003d278  cmp     rax, 10000h
0x18003d27e  ja      loc_18003D354
0x18003d284  lea     r15, [rdi+0D0h]
0x18003d28b  mov     rax, [r15+8]
0x18003d28f  sub     rax, [r15]
0x18003d292  cmp     rax, rcx
0x18003d295  jnb     short loc_18003D29C
0x18003d297  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d29c  mov     rdx, [r15]
0x18003d29f  mov     r9, [r15+8]
0x18003d2a3  mov     rcx, r9
0x18003d2a6  sub     rcx, rdx
0x18003d2a9  cmp     r14, rcx
0x18003d2ac  jnb     short loc_18003D2B8
0x18003d2ae  lea     rax, [r14+rdx]
0x18003d2b2  mov     [r15+8], rax
0x18003d2b6  jmp     short loc_18003D2EB
0x18003d2b8  jbe     short loc_18003D2EB
0x18003d2ba  mov     rax, [r15+10h]
0x18003d2be  sub     rax, rdx
0x18003d2c1  cmp     r14, rax
0x18003d2c4  jbe     short loc_18003D2D3
0x18003d2c6  mov     rdx, r14
0x18003d2c9  mov     rcx, r15
0x18003d2cc  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003d2d1  jmp     short loc_18003D2EB
0x18003d2d3  sub     r14, rcx
0x18003d2d6  lea     rbx, [r14+r9]
0x18003d2da  mov     r8, r14; Size
0x18003d2dd  xor     edx, edx; Val
0x18003d2df  mov     rcx, r9; void *
0x18003d2e2  call    memset_0
0x18003d2e7  mov     [r15+8], rbx
0x18003d2eb  mov     r9, [rdi+0D8h]
0x18003d2f2  sub     r9, [r15]
0x18003d2f5  mov     r8, [r15]
0x18003d2f8  mov     rdx, [rdi+0F0h]
0x18003d2ff  mov     rcx, rsi
0x18003d302  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18003d307  mov     eax, cs:dword_18009A048
0x18003d30d  cmp     eax, 5
0x18003d310  jbe     short loc_18003D334
0x18003d312  mov     rax, [rsi+8]
0x18003d316  sub     rax, [rsi]
0x18003d319  mov     [rsp+2A8h+var_278], rax
0x18003d31e  lea     rax, [rsp+2A8h+var_278]
0x18003d323  mov     [rsp+2A8h+lpdwBufferLength], rax
0x18003d328  lea     rdx, word_18008DBCE
0x18003d32f  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003d334  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18003d336  mov     rcx, r12; hRequest
0x18003d339  call    cs:__imp_WinHttpQueryDataAvailable
0x18003d33f  mov     rcx, [rsp+2A8h]; this
0x18003d347  test    eax, eax
0x18003d349  jz      loc_18003D860
0x18003d34f  jmp     loc_18003D809
0x18003d354  mov     eax, cs:dword_18009A048
0x18003d35a  cmp     eax, 5
0x18003d35d  jbe     short loc_18003D38F
0x18003d35f  mov     [rsp+2A8h+dwBufferLength], ecx
0x18003d363  mov     rax, [rsi+8]
0x18003d367  sub     rax, [rsi]
0x18003d36a  mov     [rsp+2A8h+var_278], rax
0x18003d36f  lea     rax, [rsp+2A8h+dwBufferLength]
0x18003d374  mov     [rsp+2A8h+lpdwIndex], rax
0x18003d379  lea     rax, [rsp+2A8h+var_278]
0x18003d37e  mov     [rsp+2A8h+lpdwBufferLength], rax
0x18003d383  lea     rdx, byte_18008DB63
0x18003d38a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18003d38f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d394  mov     rax, [rsi]
0x18003d397  cmp     rax, [rsi+8]
0x18003d39b  jz      loc_18003D511
0x18003d3a1  mov     [rsi+8], rax
0x18003d3a5  jmp     loc_18003D511
0x18003d3aa  cmp     [rsp+2A8h+dwStatusInformationLength], 4
0x18003d3b2  jz      short loc_18003D3CA
0x18003d3b4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d3b9  cmp     [rsp+2A8h+dwStatusInformationLength], 4
0x18003d3c1  jnb     short loc_18003D3CA
0x18003d3c3  mov     eax, 1
0x18003d3c8  jmp     short loc_18003D3CD
0x18003d3ca  mov     al, r15b
0x18003d3cd  mov     rcx, [rsp+2A8h]; this
0x18003d3d5  test    al, al
0x18003d3d7  jnz     loc_18003D871
0x18003d3dd  mov     eax, [rsi]
0x18003d3df  mov     [rsp+2A8h+dwNumberOfBytesToRead], eax
0x18003d3e3  test    eax, eax
0x18003d3e5  jz      loc_18003D51F
0x18003d3eb  sub     rax, [rdi+0E8h]
0x18003d3f2  add     rax, [rdi+0F0h]
0x18003d3f9  cmp     rax, 10000h
0x18003d3ff  mov     eax, cs:dword_18009A048
0x18003d405  ja      loc_18003D4BA
0x18003d40b  cmp     eax, 5
0x18003d40e  jbe     short loc_18003D439
0x18003d410  mov     rax, [rdi+0F0h]
0x18003d417  sub     rax, [rdi+0E8h]
0x18003d41e  mov     [rsp+2A8h+var_278], rax
0x18003d423  lea     rax, [rsp+2A8h+var_278]
0x18003d428  mov     [rsp+2A8h+lpdwBufferLength], rax
0x18003d42d  lea     rdx, word_18008DC6E
0x18003d434  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003d439  add     rdi, 0D0h
0x18003d440  mov     r8d, [rsp+2A8h+dwNumberOfBytesToRead]
0x18003d445  mov     rdx, [rdi]
0x18003d448  mov     r9, [rdi+8]
0x18003d44c  mov     rcx, r9
0x18003d44f  sub     rcx, rdx
0x18003d452  cmp     r8, rcx
0x18003d455  jnb     short loc_18003D461
0x18003d457  lea     rax, [r8+rdx]
0x18003d45b  mov     [rdi+8], rax
0x18003d45f  jmp     short loc_18003D491
0x18003d461  jbe     short loc_18003D491
0x18003d463  mov     rax, [rdi+10h]
0x18003d467  sub     rax, rdx
0x18003d46a  cmp     r8, rax
0x18003d46d  jbe     short loc_18003D47C
0x18003d46f  mov     rdx, r8
0x18003d472  mov     rcx, rdi
0x18003d475  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003d47a  jmp     short loc_18003D491
0x18003d47c  sub     r8, rcx; Size
0x18003d47f  lea     rbx, [r8+r9]
0x18003d483  xor     edx, edx; Val
0x18003d485  mov     rcx, r9; void *
0x18003d488  call    memset_0
0x18003d48d  mov     [rdi+8], rbx
0x18003d491  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18003d494  mov     r8d, [rsp+2A8h+dwNumberOfBytesToRead]; dwNumberOfBytesToRead
0x18003d499  mov     rdx, [rdi]; lpBuffer
0x18003d49c  mov     rcx, r12; hRequest
0x18003d49f  call    cs:__imp_WinHttpReadData
0x18003d4a5  mov     rcx, [rsp+2A8h]; this
0x18003d4ad  test    eax, eax
0x18003d4af  jz      loc_18003D888
0x18003d4b5  jmp     loc_18003D809
0x18003d4ba  cmp     eax, 5
0x18003d4bd  jbe     short loc_18003D4FA
0x18003d4bf  mov     eax, [rsp+2A8h+dwNumberOfBytesToRead]
0x18003d4c3  mov     [rsp+2A8h+dwBufferLength], eax
0x18003d4c7  mov     rax, [rdi+0F0h]
0x18003d4ce  sub     rax, [rdi+0E8h]
0x18003d4d5  mov     [rsp+2A8h+var_270], rax
0x18003d4da  lea     rax, [rsp+2A8h+dwBufferLength]
0x18003d4df  mov     [rsp+2A8h+lpdwIndex], rax
0x18003d4e4  lea     rax, [rsp+2A8h+var_270]
0x18003d4e9  mov     [rsp+2A8h+lpdwBufferLength], rax
0x18003d4ee  lea     rdx, byte_18008DC09
0x18003d4f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18003d4fa  mov     rax, [rdi+0E8h]
0x18003d501  cmp     rax, [rdi+0F0h]
0x18003d508  jz      short loc_18003D511
0x18003d50a  mov     [rdi+0F0h], rax
0x18003d511  mov     rcx, [rdi+18h]; this
0x18003d515  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18003d51a  jmp     loc_18003D809
0x18003d51f  mov     rcx, [rdi+18h]; this
0x18003d523  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18003d528  mov     eax, cs:dword_18009A048
0x18003d52e  cmp     eax, 5
0x18003d531  jbe     loc_18003D809
0x18003d537  lea     rdx, dword_18008DAB4
0x18003d53e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003d543  jmp     loc_18003D809
0x18003d548  mov     [rsp+2A8h+dwBufferLength], r15d
0x18003d54d  mov     [rsp+2A8h+lpdwIndex], r15; lpdwIndex
0x18003d552  lea     rax, [rsp+2A8h+dwBufferLength]
0x18003d557  mov     [rsp+2A8h+lpdwBufferLength], rax; int
0x18003d55c  xor     r9d, r9d; lpBuffer
0x18003d55f  xor     r8d, r8d; pwszName
0x18003d562  lea     esi, [r9+21h]
0x18003d566  mov     edx, esi; dwInfoLevel
0x18003d568  mov     rcx, r12; hRequest
0x18003d56b  call    cs:__imp_WinHttpQueryHeaders
0x18003d571  call    cs:__imp_GetLastError
0x18003d577  cmp     eax, 7Ah ; 'z'
0x18003d57a  jnz     loc_18003D642
0x18003d580  mov     ecx, [rsp+2A8h+dwBufferLength]
0x18003d584  test    ecx, ecx
0x18003d586  jz      loc_18003D642
0x18003d58c  mov     ebx, ecx
0x18003d58e  and     ebx, 1
0x18003d591  jz      short loc_18003D59C
0x18003d593  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d598  mov     ecx, [rsp+2A8h+dwBufferLength]
0x18003d59c  lea     eax, [rbx+rcx]
0x18003d59f  or      edx, 0FFFFFFFFh
0x18003d5a2  cmp     eax, ecx
0x18003d5a4  cmovnb  edx, eax; uBytes
0x18003d5a7  sbb     r9d, r9d
0x18003d5aa  and     r9d, 80070216h; char *
0x18003d5b1  mov     [rsp+2A8h+dwBufferLength], edx
0x18003d5b5  mov     r10, [rsp+2A8h]
0x18003d5bd  cmp     eax, ecx
0x18003d5bf  jb      loc_18003D899
0x18003d5c5  mov     ecx, 40h ; '@'; uFlags
0x18003d5ca  call    cs:__imp_LocalAlloc
0x18003d5d0  mov     [rsp+2A8h+var_278], rax
0x18003d5d5  test    rax, rax
0x18003d5d8  setz    dl
0x18003d5db  mov     rcx, [rsp+2A8h]; this
0x18003d5e3  test    dl, dl
0x18003d5e5  jnz     loc_18003D8AE
0x18003d5eb  mov     [rsp+2A8h+lpdwIndex], r15; lpdwIndex
0x18003d5f0  lea     rcx, [rsp+2A8h+dwBufferLength]
0x18003d5f5  mov     [rsp+2A8h+lpdwBufferLength], rcx; lpdwBufferLength
0x18003d5fa  mov     r9, rax; lpBuffer
0x18003d5fd  xor     r8d, r8d; pwszName
0x18003d600  mov     edx, esi; dwInfoLevel
0x18003d602  mov     rcx, r12; hRequest
0x18003d605  call    cs:__imp_WinHttpQueryHeaders
0x18003d60b  mov     rcx, [rsp+2A8h]; this
0x18003d613  test    eax, eax
0x18003d615  jz      loc_18003D8C5
0x18003d61b  lea     rcx, [rdi+0C0h]
0x18003d622  lea     rdx, [rsp+2A8h+var_278]
0x18003d627  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d62c  mov     eax, [rsp+2A8h+dwBufferLength]
0x18003d630  shr     eax, 1
0x18003d632  mov     [rdi+0C8h], eax
0x18003d638  lea     rcx, [rsp+2A8h+var_278]
0x18003d63d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d642  mov     [rsp+2A8h+dwNumberOfBytesToRead], 4
0x18003d64a  lea     rbx, [rdi+0CCh]
0x18003d651  mov     [rsp+2A8h+lpdwIndex], r15; lpdwIndex
0x18003d656  lea     rax, [rsp+2A8h+dwNumberOfBytesToRead]
0x18003d65b  mov     [rsp+2A8h+lpdwBufferLength], rax; lpdwBufferLength
0x18003d660  mov     r9, rbx; lpBuffer
0x18003d663  xor     r8d, r8d; pwszName
0x18003d666  mov     edx, 20000013h; dwInfoLevel
0x18003d66b  mov     rcx, r12; hRequest
0x18003d66e  call    cs:__imp_WinHttpQueryHeaders
0x18003d674  mov     rcx, [rsp+2A8h]; this
0x18003d67c  test    eax, eax
0x18003d67e  jz      loc_18003D8D7
0x18003d684  mov     eax, [rbx]
0x18003d686  sub     eax, 0C8h
0x18003d68b  cmp     eax, 63h ; 'c'
0x18003d68e  ja      loc_18003D511
0x18003d694  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18003d696  mov     rcx, r12; hRequest
0x18003d699  call    cs:__imp_WinHttpQueryDataAvailable
0x18003d69f  mov     rcx, [rsp+2A8h]; this
0x18003d6a7  test    eax, eax
0x18003d6a9  jz      loc_18003D8E8
0x18003d6af  jmp     loc_18003D809
0x18003d6b4  cmp     [rsp+2A8h+dwStatusInformationLength], 8
0x18003d6bc  jz      short loc_18003D6D4
  ... truncated ...
```
