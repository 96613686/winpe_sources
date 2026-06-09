# WerpAcquireReportingForProcess(ulong,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18001b828`
- end: `0x18001b990`
- name: `?WerpAcquireReportingForProcess@@YAJKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@0@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014c34`

## callees

- `0x180002890`
- `0x180006684`
- `0x18001b828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b912`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b937`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b8b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b8b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001b924`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001b924`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001b957`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001b957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b87b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b8c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b96d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b87b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b8c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b96d`

## string_xrefs

- `0x18001b884`: `Local\WERReportingForProcessComplete%u`

## pseudocode

```c
signed int __fastcall WerpAcquireReportingForProcess(unsigned int a1, void **a2, HANDLE *a3)
{
  void *v5; // rcx
  HANDLE v7; // rcx
  signed int result; // eax
  HANDLE EventW; // rax
  HANDLE v10; // rcx
  HANDLE MutexW; // rdi
  void *v12; // rcx
  WCHAR Name[64]; // [rsp+20h] [rbp-A8h] BYREF

  v5 = *a2;
  *a2 = 0;
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
  v7 = *a3;
  *a3 = 0;
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  result = StringCchPrintfW(Name, 0x40u, L"Local\\WERReportingForProcessComplete%u", a1);
  if ( result >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, Name);
    v10 = *a3;
    *a3 = EventW;
    if ( (unsigned __int64)v10 + 1 > 1 )
      CloseHandle(v10);
    if ( *a3 == (HANDLE)-1LL || (char *)*a3 + 1 == HANDLE_FLAG_INHERIT )
      goto LABEL_9;
    result = StringCchPrintfW(Name, 0x40u, L"Local\\WERReportingForProcess%u", a1);
    if ( result < 0 )
      return result;
    SetLastError(0);
    MutexW = CreateMutexW(0, 1, Name);
    if ( (unsigned __int64)MutexW + 1 <= 1 )
    {
LABEL_9:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else if ( GetLastError() == 183 )
    {
      CloseHandle(MutexW);
      return -2145681404;
    }
    else
    {
      ResetEvent(*a3);
      v12 = *a2;
      *a2 = MutexW;
      if ( (unsigned __int64)v12 + 1 > 1 )
        CloseHandle(v12);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b828  push    rbx
0x18001b82a  push    rsi
0x18001b82b  push    rdi
0x18001b82c  sub     rsp, 0B0h
0x18001b833  mov     rax, cs:__security_cookie
0x18001b83a  xor     rax, rsp
0x18001b83d  mov     [rsp+0C8h+var_28], rax
0x18001b845  mov     edi, ecx
0x18001b847  mov     rbx, r8
0x18001b84a  mov     rcx, [rdx]; hObject
0x18001b84d  mov     rsi, rdx
0x18001b850  mov     qword ptr [rdx], 0
0x18001b857  lea     rax, [rcx+1]
0x18001b85b  cmp     rax, 1
0x18001b85f  jbe     short loc_18001B867
0x18001b861  call    cs:__imp_CloseHandle
0x18001b867  mov     rcx, [rbx]; hObject
0x18001b86a  mov     qword ptr [rbx], 0
0x18001b871  lea     rax, [rcx+1]
0x18001b875  cmp     rax, 1
0x18001b879  jbe     short loc_18001B881
0x18001b87b  call    cs:__imp_CloseHandle
0x18001b881  mov     r9d, edi
0x18001b884  lea     r8, aLocalWerreport; "Local\\WERReportingForProcessComplete%u"
0x18001b88b  mov     edx, 40h ; '@'; unsigned __int64
0x18001b890  lea     rcx, [rsp+0C8h+Name]; wchar_t *
0x18001b895  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001b89a  test    eax, eax
0x18001b89c  js      loc_18001B975
0x18001b8a2  xor     r8d, r8d; bInitialState
0x18001b8a5  lea     r9, [rsp+0C8h+Name]; lpName
0x18001b8aa  xor     ecx, ecx; lpEventAttributes
0x18001b8ac  lea     edx, [r8+1]; bManualReset
0x18001b8b0  call    cs:__imp_CreateEventW
0x18001b8b6  mov     rcx, [rbx]; hObject
0x18001b8b9  mov     [rbx], rax
0x18001b8bc  lea     rax, [rcx+1]
0x18001b8c0  cmp     rax, 1
0x18001b8c4  jbe     short loc_18001B8CC
0x18001b8c6  call    cs:__imp_CloseHandle
0x18001b8cc  mov     rax, [rbx]
0x18001b8cf  inc     rax
0x18001b8d2  cmp     rax, 1
0x18001b8d6  ja      short loc_18001B8F3
0x18001b8d8  call    cs:__imp_GetLastError
0x18001b8de  test    eax, eax
0x18001b8e0  jle     loc_18001B975
0x18001b8e6  movzx   eax, ax
0x18001b8e9  or      eax, 80070000h
0x18001b8ee  jmp     loc_18001B975
0x18001b8f3  mov     r9d, edi
0x18001b8f6  lea     r8, aLocalWerreport_0; "Local\\WERReportingForProcess%u"
0x18001b8fd  mov     edx, 40h ; '@'; unsigned __int64
0x18001b902  lea     rcx, [rsp+0C8h+Name]; wchar_t *
0x18001b907  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001b90c  test    eax, eax
0x18001b90e  js      short loc_18001B975
0x18001b910  xor     ecx, ecx; dwErrCode
0x18001b912  call    cs:__imp_SetLastError
0x18001b918  lea     r8, [rsp+0C8h+Name]; lpName
0x18001b91d  mov     edx, 1; bInitialOwner
0x18001b922  xor     ecx, ecx; lpMutexAttributes
0x18001b924  call    cs:__imp_CreateMutexW
0x18001b92a  mov     rdi, rax
0x18001b92d  lea     rcx, [rax+1]
0x18001b931  cmp     rcx, 1
0x18001b935  jbe     short loc_18001B8D8
0x18001b937  call    cs:__imp_GetLastError
0x18001b93d  cmp     eax, 0B7h
0x18001b942  jnz     short loc_18001B954
0x18001b944  mov     rcx, rdi; hObject
0x18001b947  call    cs:__imp_CloseHandle
0x18001b94d  mov     eax, 801B8004h
0x18001b952  jmp     short loc_18001B975
0x18001b954  mov     rcx, [rbx]; hEvent
0x18001b957  call    cs:__imp_ResetEvent
0x18001b95d  mov     rcx, [rsi]; hObject
0x18001b960  mov     [rsi], rdi
0x18001b963  lea     rax, [rcx+1]
0x18001b967  cmp     rax, 1
0x18001b96b  jbe     short loc_18001B973
0x18001b96d  call    cs:__imp_CloseHandle
0x18001b973  xor     eax, eax
0x18001b975  mov     rcx, [rsp+0C8h+var_28]
0x18001b97d  xor     rcx, rsp; StackCookie
0x18001b980  call    __security_check_cookie
0x18001b985  add     rsp, 0B0h
0x18001b98c  pop     rdi
0x18001b98d  pop     rsi
0x18001b98e  pop     rbx
0x18001b98f  retn
```
