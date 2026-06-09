# Microsoft::Diagnostics::DTraceManager::LookupProcessInfo(ulong)

- ea: `0x1802b61c0`
- end: `0x1802b646d`
- name: `?LookupProcessInfo@DTraceManager@Diagnostics@Microsoft@@CA?AV?$optional@UProcessInfo@DTraceManager@Diagnostics@Microsoft@@@std@@K@Z`
- size: `685`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802b5fd4`
- `0x1802b6510`

## callees

- `0x180001970`
- `0x180003ef0`
- `0x18002abec`
- `0x18002df00`
- `0x1800bc658`
- `0x180142fcc`
- `0x1801cd84c`
- `0x18020aac0`
- `0x1802b61c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b623c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b62ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b623c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b62ea`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802b6206`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802b6206`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1802b62a3`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1802b62a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1802b6367`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1802b6367`

## string_xrefs

- `0x1802b62b9`: `onecore\base\telemetry\utc\service\scenarios\base\dtracemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::DTraceManager::LookupProcessInfo(__int64 a1, DWORD a2)
{
  HANDLE v4; // rax
  signed int LastError; // eax
  int v6; // r8d
  int v7; // r9d
  const char *v9; // r9
  signed int v10; // eax
  int v11; // r8d
  int v12; // r9d
  LPWSTR FileNameW; // rdx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int128 *v17; // rax
  DWORD v18; // [rsp+30h] [rbp-478h] BYREF
  __int128 *v19; // [rsp+38h] [rbp-470h] BYREF
  _QWORD v20[3]; // [rsp+40h] [rbp-468h] BYREF
  __int128 v21; // [rsp+58h] [rbp-450h] BYREF
  __m128i si128; // [rsp+68h] [rbp-440h]
  DWORD v23; // [rsp+78h] [rbp-430h]
  WCHAR ImageFileName[520]; // [rsp+80h] [rbp-428h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  v20[2] = a1;
  if ( (a2 & 0xFFFFFFFB) != 0 )
  {
    v4 = OpenProcess(0x1000u, 0, a2);
    v20[0] = v4;
    if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 8) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        LODWORD(v19) = LastError;
        v18 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1804543B0,
          (unsigned int)&byte_1803F2EC7,
          v6,
          v7,
          (__int64)&v18,
          (__int64)&v19);
      }
LABEL_8:
      *(_BYTE *)(a1 + 40) = 0;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
      return a1;
    }
    if ( !K32GetProcessImageFileNameW(v4, ImageFileName, 0x208u) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\dtracemanager.cpp",
        v9);
      if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 8) )
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v18 = v10;
        LODWORD(v19) = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1804543B0,
          (unsigned int)byte_1803F2F1D,
          v11,
          v12,
          (__int64)&v19,
          (__int64)&v18);
      }
      goto LABEL_8;
    }
    v21 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v21) = 0;
    v23 = a2;
    FileNameW = PathFindFileNameW(ImageFileName);
    std::wstring::assign(&v21, FileNameW);
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 8) )
    {
      v17 = &v21;
      if ( si128.m128i_i64[1] > 7uLL )
        v17 = (__int128 *)v21;
      v19 = v17;
      v18 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v14,
        (unsigned int)&word_1803F2E76,
        v15,
        v16,
        (__int64)&v18,
        (__int64)&v19);
    }
    *(_OWORD *)a1 = 0;
    *(_OWORD *)a1 = v21;
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v21) = 0;
    *(_DWORD *)(a1 + 32) = v23;
    *(_BYTE *)(a1 + 40) = 1;
    std::wstring::_Tidy_deallocate(&v21);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
    return a1;
  }
  else
  {
    *(_BYTE *)(a1 + 40) = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x1802b61c0  mov     [rsp+arg_10], rbx
0x1802b61c5  mov     [rsp+arg_18], rsi
0x1802b61ca  push    rdi
0x1802b61cb  sub     rsp, 4A0h
0x1802b61d2  mov     rax, cs:__security_cookie
0x1802b61d9  xor     rax, rsp
0x1802b61dc  mov     [rsp+4A8h+var_18], rax
0x1802b61e4  mov     esi, edx
0x1802b61e6  mov     rdi, rcx
0x1802b61e9  mov     [rsp+4A8h+var_458], rcx
0x1802b61ee  xor     ebx, ebx
0x1802b61f0  test    edx, 0FFFFFFFBh
0x1802b61f6  jz      loc_1802B6435
0x1802b61fc  mov     r8d, edx; dwProcessId
0x1802b61ff  xor     edx, edx; bInheritHandle
0x1802b6201  mov     ecx, 1000h; dwDesiredAccess
0x1802b6206  call    cs:__imp_OpenProcess
0x1802b620c  mov     [rsp+4A8h+var_468], rax
0x1802b6211  lea     rcx, [rax+1]
0x1802b6215  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1802b621c  jnz     short loc_1802B6292
0x1802b621e  mov     eax, cs:dword_1804543B0
0x1802b6224  cmp     eax, 5
0x1802b6227  jbe     short loc_1802B627D
0x1802b6229  lea     edx, [rbx+8]
0x1802b622c  lea     rcx, dword_1804543B0
0x1802b6233  call    _tlgKeywordOn
0x1802b6238  test    al, al
0x1802b623a  jz      short loc_1802B627D
0x1802b623c  call    cs:__imp_GetLastError
0x1802b6242  test    eax, eax
0x1802b6244  jle     short loc_1802B624E
0x1802b6246  movzx   eax, ax
0x1802b6249  or      eax, 80070000h
0x1802b624e  mov     dword ptr [rsp+4A8h+var_470], eax
0x1802b6252  mov     [rsp+4A8h+var_478], esi
0x1802b6256  lea     rax, [rsp+4A8h+var_470]
0x1802b625b  mov     [rsp+4A8h+var_480], rax
0x1802b6260  lea     rax, [rsp+4A8h+var_478]
0x1802b6265  mov     [rsp+4A8h+var_488], rax
0x1802b626a  lea     rdx, byte_1803F2EC7
0x1802b6271  lea     rcx, dword_1804543B0
0x1802b6278  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1802b627d  mov     [rdi+28h], bl
0x1802b6280  lea     rcx, [rsp+4A8h+var_468]
0x1802b6285  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b628a  mov     rax, rdi
0x1802b628d  jmp     loc_1802B6447
0x1802b6292  mov     r8d, 208h; nSize
0x1802b6298  lea     rdx, [rsp+4A8h+ImageFileName]; lpImageFileName
0x1802b62a0  mov     rcx, rax; hProcess
0x1802b62a3  call    cs:__imp_K32GetProcessImageFileNameW
0x1802b62a9  test    eax, eax
0x1802b62ab  jnz     loc_1802B6340
0x1802b62b1  mov     rcx, [rsp+4A8h]; this
0x1802b62b9  lea     r8, aOnecoreBaseTel_95; "onecore\\base\\telemetry\\utc\\service"...
0x1802b62c0  mov     edx, 1AFh; void *
0x1802b62c5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1802b62ca  mov     eax, cs:dword_1804543B0
0x1802b62d0  cmp     eax, 5
0x1802b62d3  jbe     short loc_1802B632B
0x1802b62d5  mov     edx, 8
0x1802b62da  lea     rcx, dword_1804543B0
0x1802b62e1  call    _tlgKeywordOn
0x1802b62e6  test    al, al
0x1802b62e8  jz      short loc_1802B632B
0x1802b62ea  call    cs:__imp_GetLastError
0x1802b62f0  test    eax, eax
0x1802b62f2  jle     short loc_1802B62FC
0x1802b62f4  movzx   eax, ax
0x1802b62f7  or      eax, 80070000h
0x1802b62fc  mov     [rsp+4A8h+var_478], eax
0x1802b6300  mov     dword ptr [rsp+4A8h+var_470], esi
0x1802b6304  lea     rax, [rsp+4A8h+var_478]
0x1802b6309  mov     [rsp+4A8h+var_480], rax
0x1802b630e  lea     rax, [rsp+4A8h+var_470]
0x1802b6313  mov     [rsp+4A8h+var_488], rax
0x1802b6318  lea     rdx, byte_1803F2F1D
0x1802b631f  lea     rcx, dword_1804543B0
0x1802b6326  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1802b632b  mov     [rdi+28h], bl
0x1802b632e  lea     rcx, [rsp+4A8h+var_468]
0x1802b6333  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b6338  mov     rax, rdi
0x1802b633b  jmp     loc_1802B6447
0x1802b6340  xorps   xmm0, xmm0
0x1802b6343  movups  [rsp+4A8h+var_450], xmm0
0x1802b6348  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1802b6350  movdqu  [rsp+4A8h+var_440], xmm1
0x1802b6356  mov     word ptr [rsp+4A8h+var_450], bx
0x1802b635b  mov     [rsp+4A8h+var_430], esi
0x1802b635f  lea     rcx, [rsp+4A8h+ImageFileName]; pszPath
0x1802b6367  call    cs:__imp_PathFindFileNameW
0x1802b636d  mov     rdx, rax
0x1802b6370  lea     rcx, [rsp+4A8h+var_450]
0x1802b6375  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1802b637a  mov     eax, cs:dword_1804543B0
0x1802b6380  cmp     eax, 5
0x1802b6383  jbe     short loc_1802B63D4
0x1802b6385  mov     edx, 8
0x1802b638a  lea     rcx, dword_1804543B0
0x1802b6391  call    _tlgKeywordOn
0x1802b6396  test    al, al
0x1802b6398  jz      short loc_1802B63D4
0x1802b639a  lea     rax, [rsp+4A8h+var_450]
0x1802b639f  cmp     qword ptr [rsp+4A8h+var_440+8], 7
0x1802b63a5  cmova   rax, qword ptr [rsp+4A8h+var_450]
0x1802b63ab  mov     [rsp+4A8h+var_470], rax
0x1802b63b0  mov     [rsp+4A8h+var_478], esi
0x1802b63b4  lea     rax, [rsp+4A8h+var_470]
0x1802b63b9  mov     [rsp+4A8h+var_480], rax
0x1802b63be  lea     rax, [rsp+4A8h+var_478]
0x1802b63c3  mov     [rsp+4A8h+var_488], rax
0x1802b63c8  lea     rdx, word_1803F2E76
0x1802b63cf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1802b63d4  xorps   xmm0, xmm0
0x1802b63d7  movups  xmmword ptr [rdi], xmm0
0x1802b63da  mov     rax, qword ptr [rsp+4A8h+var_450]
0x1802b63df  mov     [rdi], rax
0x1802b63e2  mov     rax, qword ptr [rsp+4A8h+var_450+8]
0x1802b63e7  mov     [rdi+8], rax
0x1802b63eb  mov     rax, qword ptr [rsp+4A8h+var_440]
0x1802b63f0  mov     [rdi+10h], rax
0x1802b63f4  mov     rax, qword ptr [rsp+4A8h+var_440+8]
0x1802b63f9  mov     [rdi+18h], rax
0x1802b63fd  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1802b6405  movdqu  [rsp+4A8h+var_440], xmm0
0x1802b640b  mov     word ptr [rsp+4A8h+var_450], bx
0x1802b6410  mov     eax, [rsp+4A8h+var_430]
0x1802b6414  mov     [rdi+20h], eax
0x1802b6417  mov     byte ptr [rdi+28h], 1
0x1802b641b  lea     rcx, [rsp+4A8h+var_450]
0x1802b6420  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b6425  nop
0x1802b6426  lea     rcx, [rsp+4A8h+var_468]
0x1802b642b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b6430  mov     rax, rdi
0x1802b6433  jmp     short loc_1802B6447
0x1802b6435  mov     [rcx+28h], bl
0x1802b6438  mov     rax, rdi
0x1802b643b  jmp     short loc_1802B6447
0x1802b643d  xor     ebx, ebx
0x1802b643f  mov     rax, [rsp+4A8h+var_458]
0x1802b6444  mov     [rax+28h], bl
0x1802b6447  mov     rcx, [rsp+4A8h+var_18]
0x1802b644f  xor     rcx, rsp; StackCookie
0x1802b6452  call    __security_check_cookie
0x1802b6457  lea     r11, [rsp+4A8h+var_8]
0x1802b645f  mov     rbx, [r11+20h]
0x1802b6463  mov     rsi, [r11+28h]
0x1802b6467  mov     rsp, r11
0x1802b646a  pop     rdi
0x1802b646b  retn
```
