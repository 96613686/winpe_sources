# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1800096b0`
- end: `0x1800097c9`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180046cb0`

## callees

- `0x1800072e8`
- `0x180008320`
- `0x1800083c4`
- `0x1800096b0`
- `0x18000ad18`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009750`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000975e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000975e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009736`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000976e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009736`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000976e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800096f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800096f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009742`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000972b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000972b`

## string_xrefs

- `0x1800097a7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  __int64 v7; // r8
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return --*(_DWORD *)lpMem;
  }
  else
  {
    v2 = (void *)lpMem[1];
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v10, v11);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v7, v8);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(lpMem);
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800096b0  mov     [rsp+arg_0], rbx
0x1800096b5  mov     [rsp+arg_8], rsi
0x1800096ba  push    rdi
0x1800096bb  sub     rsp, 20h
0x1800096bf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800096c6  mov     rbx, rcx
0x1800096c9  jnz     loc_18000977A
0x1800096cf  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800096d6  test    rax, rax
0x1800096d9  jz      short loc_1800096E8
0x1800096db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e0  test    al, al
0x1800096e2  jnz     loc_18000977A
0x1800096e8  mov     rdi, [rbx+8]
0x1800096ec  xor     r8d, r8d; bAlertable
0x1800096ef  mov     rcx, rdi; hHandle
0x1800096f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800096f5  call    cs:__imp_WaitForSingleObjectEx
0x1800096fb  cmp     eax, 102h
0x180009700  jz      short loc_18000970F
0x180009702  test    eax, 0FFFFFF7Fh
0x180009707  jnz     loc_1800097A2
0x18000970d  jmp     short loc_180009711
0x18000970f  xor     edi, edi
0x180009711  mov     eax, [rbx]
0x180009713  dec     eax
0x180009715  mov     [rbx], eax
0x180009717  mov     eax, [rbx]
0x180009719  test    eax, eax
0x18000971b  jnz     short loc_180009766
0x18000971d  lea     rcx, [rbx+10h]; this
0x180009721  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180009726  test    rdi, rdi
0x180009729  jz      short loc_180009748
0x18000972b  call    cs:__imp_GetLastError
0x180009731  mov     rcx, rdi; hMutex
0x180009734  mov     esi, eax
0x180009736  call    cs:__imp_ReleaseMutex
0x18000973c  test    eax, eax
0x18000973e  jz      short loc_180009792
0x180009740  mov     ecx, esi; dwErrCode
0x180009742  call    cs:__imp_SetLastError
0x180009748  mov     rcx, rbx
0x18000974b  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180009750  call    cs:__imp_GetProcessHeap
0x180009756  mov     r8, rbx; lpMem
0x180009759  xor     edx, edx; dwFlags
0x18000975b  mov     rcx, rax; hHeap
0x18000975e  call    cs:__imp_HeapFree
0x180009764  jmp     short loc_180009782
0x180009766  test    rdi, rdi
0x180009769  jz      short loc_180009782
0x18000976b  mov     rcx, rdi; hMutex
0x18000976e  call    cs:__imp_ReleaseMutex
0x180009774  test    eax, eax
0x180009776  jz      short loc_1800097B9
0x180009778  jmp     short loc_180009782
0x18000977a  mov     eax, [rbx]
0x18000977c  dec     eax
0x18000977e  mov     [rbx], eax
0x180009780  mov     eax, [rbx]
0x180009782  mov     rbx, [rsp+28h+arg_0]
0x180009787  mov     rsi, [rsp+28h+arg_8]
0x18000978c  add     rsp, 20h
0x180009790  pop     rdi
0x180009791  retn
0x180009792  mov     rcx, [rsp+28h]; this
0x180009797  mov     edx, 0A15h; void *
0x18000979c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800097a2  mov     rcx, [rsp+28h]; this
0x1800097a7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800097ae  mov     edx, 0E01h; void *
0x1800097b3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800097b9  mov     rcx, [rsp+28h]; this
0x1800097be  mov     edx, 0A15h; void *
0x1800097c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
