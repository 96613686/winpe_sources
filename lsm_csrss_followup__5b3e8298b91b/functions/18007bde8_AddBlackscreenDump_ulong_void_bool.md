# AddBlackscreenDump(ulong,void *,bool)

- ea: `0x18007bde8`
- end: `0x18007bf67`
- name: `?AddBlackscreenDump@@YAJKPEAX_N@Z`
- size: `383`
- prototype: `__int64 __fastcall(DWORD dwProcessId, HREPORT hReportHandle, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007c448`

## callees

- `0x180024ce0`
- `0x180025890`
- `0x18007bbe0`
- `0x18007bde8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007beb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007beb7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007be69`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007be69`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterAdditionalProcess` at `0x18007be07`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterAdditionalProcess` at `0x18007be07`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x18007befc`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x18007befc`

## string_xrefs

- `0x18007be8b`: `Not including extra dump because we couldn't open process handle`

## pseudocode

```c
__int64 __fastcall AddBlackscreenDump(DWORD dwProcessId, HREPORT hReportHandle, char a3)
{
  HRESULT v6; // eax
  int v7; // ecx
  int v8; // r8d
  DWORD LastError; // ebx
  HANDLE v10; // rax
  int v11; // r8d
  int v12; // r9d
  HRESULT v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char *v18; // [rsp+40h] [rbp-10h] BYREF
  HANDLE v19; // [rsp+48h] [rbp-8h] BYREF
  DWORD v20; // [rsp+70h] [rbp+20h] BYREF
  const char *v21; // [rsp+88h] [rbp+38h] BYREF

  v6 = WerRegisterAdditionalProcess(dwProcessId, 0);
  LastError = v6;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v20 = v6;
    LODWORD(v21) = dwProcessId;
    v18 = "WerRegisterAdditionalProcess";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&dword_1800C7A4C,
      v8,
      dword_1800DA020,
      (__int64)&v18,
      (__int64)&v21,
      (__int64)&v20);
  }
  if ( dwProcessId )
  {
    v10 = OpenProcess(0x100C7Bu, 1, dwProcessId);
    v19 = v10;
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      if ( a3 )
        v13 = WerReportAddDump(hReportHandle, v10, 0, WerDumpTypeHeapDump, 0, 0, 2u);
      else
        v13 = WerReportAddDump(hReportHandle, v10, 0, WerDumpTypeHeapDump, 0, 0, 0);
      LastError = v13;
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v20 = v13;
        v18 = "Got process dump for pid";
        LODWORD(v21) = dwProcessId;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)&byte_1800C7A17,
          v15,
          v16,
          (__int64)&v18,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    else
    {
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v20 = dwProcessId;
        v21 = "Not including extra dump because we couldn't open process handle";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v10 + 1,
          (unsigned int)&byte_1800C79E7,
          v11,
          v12,
          (__int64)&v21,
          (__int64)&v20);
      }
      LastError = GetLastError();
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  }
  return LastError;
}

```

## disassembly

```asm
0x18007bde8  mov     [rsp-18h+arg_8], rbx
0x18007bded  mov     [rsp-18h+arg_10], rsi
0x18007bdf2  push    rbp
0x18007bdf3  push    rdi
0x18007bdf4  push    r14
0x18007bdf6  mov     rbp, rsp
0x18007bdf9  sub     rsp, 50h
0x18007bdfd  mov     r14, rdx
0x18007be00  mov     sil, r8b
0x18007be03  xor     edx, edx; captureExtraInfoForThreadId
0x18007be05  mov     edi, ecx
0x18007be07  call    cs:__imp_WerRegisterAdditionalProcess
0x18007be0d  mov     r9d, cs:dword_1800DA020
0x18007be14  mov     ebx, eax
0x18007be16  cmp     r9d, 4
0x18007be1a  jbe     short loc_18007BE54
0x18007be1c  mov     [rbp+arg_0], eax
0x18007be1f  lea     rdx, dword_1800C7A4C
0x18007be26  lea     rax, aWerregisteradd; "WerRegisterAdditionalProcess"
0x18007be2d  mov     dword ptr [rbp+arg_18], edi
0x18007be30  mov     [rbp+var_10], rax
0x18007be34  lea     rax, [rbp+arg_0]
0x18007be38  mov     qword ptr [rsp+50h+dwFlags], rax
0x18007be3d  lea     rax, [rbp+arg_18]
0x18007be41  mov     [rsp+50h+pDumpCustomOptions], rax
0x18007be46  lea     rax, [rbp+var_10]
0x18007be4a  mov     [rsp+50h+pExceptionParam], rax
0x18007be4f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007be54  test    edi, edi
0x18007be56  jz      loc_18007BF50
0x18007be5c  mov     r8d, edi; dwProcessId
0x18007be5f  mov     edx, 1; bInheritHandle
0x18007be64  mov     ecx, 100C7Bh; dwDesiredAccess
0x18007be69  call    cs:__imp_OpenProcess
0x18007be6f  mov     [rbp+var_8], rax
0x18007be73  lea     rcx, [rax+1]
0x18007be77  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18007be7e  jnz     short loc_18007BEC4
0x18007be80  mov     eax, cs:dword_1800DA020
0x18007be86  cmp     eax, 3
0x18007be89  jbe     short loc_18007BEB7
0x18007be8b  lea     rax, aNotIncludingEx; "Not including extra dump because we cou"...
0x18007be92  mov     [rbp+arg_0], edi
0x18007be95  mov     [rbp+arg_18], rax
0x18007be99  lea     rdx, byte_1800C79E7
0x18007bea0  lea     rax, [rbp+arg_0]
0x18007bea4  mov     [rsp+50h+pDumpCustomOptions], rax
0x18007bea9  lea     rax, [rbp+arg_18]
0x18007bead  mov     [rsp+50h+pExceptionParam], rax
0x18007beb2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007beb7  call    cs:__imp_GetLastError
0x18007bebd  mov     ebx, eax
0x18007bebf  jmp     loc_18007BF47
0x18007bec4  xor     r8d, r8d; hThread
0x18007bec7  mov     r9d, 3; dumpType
0x18007becd  mov     rdx, rax; hProcess
0x18007bed0  mov     rcx, r14; hReportHandle
0x18007bed3  test    sil, sil
0x18007bed6  jz      short loc_18007BEE2
0x18007bed8  mov     [rsp+50h+dwFlags], 2
0x18007bee0  jmp     short loc_18007BEEA
0x18007bee2  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18007beea  mov     [rsp+50h+pDumpCustomOptions], 0; pDumpCustomOptions
0x18007bef3  mov     [rsp+50h+pExceptionParam], 0; pExceptionParam
0x18007befc  call    cs:__imp_WerReportAddDump
0x18007bf02  mov     ebx, eax
0x18007bf04  mov     eax, cs:dword_1800DA020
0x18007bf0a  cmp     eax, 4
0x18007bf0d  jbe     short loc_18007BF47
0x18007bf0f  lea     rax, aGotProcessDump; "Got process dump for pid"
0x18007bf16  mov     [rbp+arg_0], ebx
0x18007bf19  mov     [rbp+var_10], rax
0x18007bf1d  lea     rdx, byte_1800C7A17
0x18007bf24  lea     rax, [rbp+arg_0]
0x18007bf28  mov     dword ptr [rbp+arg_18], edi
0x18007bf2b  mov     qword ptr [rsp+50h+dwFlags], rax
0x18007bf30  lea     rax, [rbp+arg_18]
0x18007bf34  mov     [rsp+50h+pDumpCustomOptions], rax
0x18007bf39  lea     rax, [rbp+var_10]
0x18007bf3d  mov     [rsp+50h+pExceptionParam], rax
0x18007bf42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007bf47  lea     rcx, [rbp+var_8]
0x18007bf4b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007bf50  lea     r11, [rsp+50h+var_s0]
0x18007bf55  mov     eax, ebx
0x18007bf57  mov     rbx, [r11+28h]
0x18007bf5b  mov     rsi, [r11+30h]
0x18007bf5f  mov     rsp, r11
0x18007bf62  pop     r14
0x18007bf64  pop     rdi
0x18007bf65  pop     rbp
0x18007bf66  retn
```
