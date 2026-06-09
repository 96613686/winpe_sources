# AddBlackscreenDump(ulong,void *,bool)

- ea: `0x1800806ac`
- end: `0x180080844`
- name: `?AddBlackscreenDump@@YAJKPEAX_N@Z`
- size: `408`
- prototype: `__int64 __fastcall(DWORD dwProcessId, HREPORT hReportHandle, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180080d9c`

## callees

- `0x180026c8c`
- `0x18002772c`
- `0x180080474`
- `0x1800806ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080787`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180080733`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180080733`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterAdditionalProcess` at `0x1800806cb`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterAdditionalProcess` at `0x1800806cb`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800807d2`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800807d2`

## string_xrefs

- `0x18008075b`: `Not including extra dump because we couldn't open process handle`

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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v20 = v6;
    LODWORD(v21) = dwProcessId;
    v18 = "WerRegisterAdditionalProcess";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&dword_1800CCBD4,
      v8,
      dword_1800DF020,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v20 = v13;
        v18 = "Got process dump for pid";
        LODWORD(v21) = dwProcessId;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)&byte_1800CCB6F,
          v15,
          v16,
          (__int64)&v18,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    else
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v20 = dwProcessId;
        v21 = "Not including extra dump because we couldn't open process handle";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v10 + 1,
          (unsigned int)&dword_1800CCBA4,
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
0x1800806ac  mov     [rsp-18h+arg_8], rbx
0x1800806b1  mov     [rsp-18h+arg_10], rsi
0x1800806b6  push    rbp
0x1800806b7  push    rdi
0x1800806b8  push    r14
0x1800806ba  mov     rbp, rsp
0x1800806bd  sub     rsp, 50h
0x1800806c1  mov     r14, rdx
0x1800806c4  mov     sil, r8b
0x1800806c7  xor     edx, edx; captureExtraInfoForThreadId
0x1800806c9  mov     edi, ecx
0x1800806cb  call    cs:__imp_WerRegisterAdditionalProcess
0x1800806d2  nop     dword ptr [rax+rax+00h]
0x1800806d7  mov     r9d, cs:dword_1800DF020
0x1800806de  mov     ebx, eax
0x1800806e0  cmp     r9d, 4
0x1800806e4  jbe     short loc_18008071E
0x1800806e6  mov     [rbp+arg_0], eax
0x1800806e9  lea     rdx, dword_1800CCBD4
0x1800806f0  lea     rax, aWerregisteradd; "WerRegisterAdditionalProcess"
0x1800806f7  mov     dword ptr [rbp+arg_18], edi
0x1800806fa  mov     [rbp+var_10], rax
0x1800806fe  lea     rax, [rbp+arg_0]
0x180080702  mov     qword ptr [rsp+50h+dwFlags], rax
0x180080707  lea     rax, [rbp+arg_18]
0x18008070b  mov     [rsp+50h+pDumpCustomOptions], rax
0x180080710  lea     rax, [rbp+var_10]
0x180080714  mov     [rsp+50h+pExceptionParam], rax
0x180080719  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008071e  test    edi, edi
0x180080720  jz      loc_18008082C
0x180080726  mov     r8d, edi; dwProcessId
0x180080729  mov     edx, 1; bInheritHandle
0x18008072e  mov     ecx, 100C7Bh; dwDesiredAccess
0x180080733  call    cs:__imp_OpenProcess
0x18008073a  nop     dword ptr [rax+rax+00h]
0x18008073f  mov     [rbp+var_8], rax
0x180080743  lea     rcx, [rax+1]
0x180080747  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18008074e  jnz     short loc_18008079A
0x180080750  mov     eax, cs:dword_1800DF020
0x180080756  cmp     eax, 3
0x180080759  jbe     short loc_180080787
0x18008075b  lea     rax, aNotIncludingEx; "Not including extra dump because we cou"...
0x180080762  mov     [rbp+arg_0], edi
0x180080765  mov     [rbp+arg_18], rax
0x180080769  lea     rdx, dword_1800CCBA4
0x180080770  lea     rax, [rbp+arg_0]
0x180080774  mov     [rsp+50h+pDumpCustomOptions], rax
0x180080779  lea     rax, [rbp+arg_18]
0x18008077d  mov     [rsp+50h+pExceptionParam], rax
0x180080782  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180080787  call    cs:__imp_GetLastError
0x18008078e  nop     dword ptr [rax+rax+00h]
0x180080793  mov     ebx, eax
0x180080795  jmp     loc_180080823
0x18008079a  xor     r8d, r8d; hThread
0x18008079d  mov     r9d, 3; dumpType
0x1800807a3  mov     rdx, rax; hProcess
0x1800807a6  mov     rcx, r14; hReportHandle
0x1800807a9  test    sil, sil
0x1800807ac  jz      short loc_1800807B8
0x1800807ae  mov     [rsp+50h+dwFlags], 2
0x1800807b6  jmp     short loc_1800807C0
0x1800807b8  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800807c0  mov     [rsp+50h+pDumpCustomOptions], 0; pDumpCustomOptions
0x1800807c9  mov     [rsp+50h+pExceptionParam], 0; pExceptionParam
0x1800807d2  call    cs:__imp_WerReportAddDump
0x1800807d9  nop     dword ptr [rax+rax+00h]
0x1800807de  mov     ebx, eax
0x1800807e0  mov     eax, cs:dword_1800DF020
0x1800807e6  cmp     eax, 4
0x1800807e9  jbe     short loc_180080823
0x1800807eb  lea     rax, aGotProcessDump; "Got process dump for pid"
0x1800807f2  mov     [rbp+arg_0], ebx
0x1800807f5  mov     [rbp+var_10], rax
0x1800807f9  lea     rdx, byte_1800CCB6F
0x180080800  lea     rax, [rbp+arg_0]
0x180080804  mov     dword ptr [rbp+arg_18], edi
0x180080807  mov     qword ptr [rsp+50h+dwFlags], rax
0x18008080c  lea     rax, [rbp+arg_18]
0x180080810  mov     [rsp+50h+pDumpCustomOptions], rax
0x180080815  lea     rax, [rbp+var_10]
0x180080819  mov     [rsp+50h+pExceptionParam], rax
0x18008081e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180080823  lea     rcx, [rbp+var_8]
0x180080827  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008082c  lea     r11, [rsp+50h+var_s0]
0x180080831  mov     eax, ebx
0x180080833  mov     rbx, [r11+28h]
0x180080837  mov     rsi, [r11+30h]
0x18008083b  mov     rsp, r11
0x18008083e  pop     r14
0x180080840  pop     rdi
0x180080841  pop     rbp
0x180080842  retn
```
