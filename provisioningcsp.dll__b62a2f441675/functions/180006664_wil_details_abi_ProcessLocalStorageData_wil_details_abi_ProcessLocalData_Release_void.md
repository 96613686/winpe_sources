# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180006664`
- end: `0x1800067d6`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `370`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800379e0`

## callees

- `0x180004830`
- `0x180004988`
- `0x1800051a4`
- `0x18000526c`
- `0x180006664`
- `0x180007834`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000670a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000670a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800066a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800066a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000676b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000676b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006741`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006731`

## string_xrefs

- `0x1800067a4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // ebp
  unsigned int v7; // r8d
  const char *v8; // r9
  void *v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

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
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v13, v14);
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
      wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(lpMem + 5);
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      v9 = (void *)lpMem[1];
      if ( v9 )
      {
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
      }
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006664  push    rbx
0x180006666  push    rbp
0x180006667  push    rsi
0x180006668  push    rdi
0x180006669  sub     rsp, 28h
0x18000666d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006674  mov     rbx, rcx
0x180006677  jnz     loc_18000677D
0x18000667d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006684  test    rax, rax
0x180006687  jz      short loc_180006696
0x180006689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668e  test    al, al
0x180006690  jnz     loc_18000677D
0x180006696  mov     rdi, [rbx+8]
0x18000669a  xor     r8d, r8d; bAlertable
0x18000669d  mov     rcx, rdi; hHandle
0x1800066a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800066a3  call    cs:__imp_WaitForSingleObjectEx
0x1800066aa  nop     dword ptr [rax+rax+00h]
0x1800066af  cmp     eax, 102h
0x1800066b4  jz      short loc_1800066C3
0x1800066b6  test    eax, 0FFFFFF7Fh
0x1800066bb  jnz     loc_18000679F
0x1800066c1  jmp     short loc_1800066C5
0x1800066c3  xor     edi, edi
0x1800066c5  mov     eax, [rbx]
0x1800066c7  dec     eax
0x1800066c9  mov     [rbx], eax
0x1800066cb  mov     eax, [rbx]
0x1800066cd  test    eax, eax
0x1800066cf  jnz     loc_180006763
0x1800066d5  lea     rcx, [rbx+10h]; this
0x1800066d9  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800066de  test    rdi, rdi
0x1800066e1  jz      short loc_180006716
0x1800066e3  call    cs:__imp_GetLastError
0x1800066ea  nop     dword ptr [rax+rax+00h]
0x1800066ef  mov     rcx, rdi; hMutex
0x1800066f2  mov     ebp, eax
0x1800066f4  call    cs:__imp_ReleaseMutex
0x1800066fb  nop     dword ptr [rax+rax+00h]
0x180006700  test    eax, eax
0x180006702  jz      loc_1800067C6
0x180006708  mov     ecx, ebp; dwErrCode
0x18000670a  call    cs:__imp_SetLastError
0x180006711  nop     dword ptr [rax+rax+00h]
0x180006716  lea     rcx, [rbx+28h]
0x18000671a  call    ??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)
0x18000671f  lea     rcx, [rbx+10h]; this
0x180006723  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006728  mov     rcx, [rbx+8]; hObject
0x18000672c  test    rcx, rcx
0x18000672f  jz      short loc_180006741
0x180006731  call    cs:__imp_CloseHandle
0x180006738  nop     dword ptr [rax+rax+00h]
0x18000673d  test    eax, eax
0x18000673f  jz      short loc_18000678F
0x180006741  call    cs:__imp_GetProcessHeap
0x180006748  nop     dword ptr [rax+rax+00h]
0x18000674d  mov     r8, rbx; lpMem
0x180006750  xor     edx, edx; dwFlags
0x180006752  mov     rcx, rax; hHeap
0x180006755  call    cs:__imp_HeapFree
0x18000675c  nop     dword ptr [rax+rax+00h]
0x180006761  jmp     short loc_180006785
0x180006763  test    rdi, rdi
0x180006766  jz      short loc_180006785
0x180006768  mov     rcx, rdi; hMutex
0x18000676b  call    cs:__imp_ReleaseMutex
0x180006772  nop     dword ptr [rax+rax+00h]
0x180006777  test    eax, eax
0x180006779  jz      short loc_1800067B6
0x18000677b  jmp     short loc_180006785
0x18000677d  mov     eax, [rbx]
0x18000677f  dec     eax
0x180006781  mov     [rbx], eax
0x180006783  mov     eax, [rbx]
0x180006785  add     rsp, 28h
0x180006789  pop     rdi
0x18000678a  pop     rsi
0x18000678b  pop     rbp
0x18000678c  pop     rbx
0x18000678d  retn
0x18000678f  mov     rcx, [rsp+48h]; this
0x180006794  mov     edx, 0A0Bh; void *
0x180006799  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000679f  mov     rcx, [rsp+48h]; this
0x1800067a4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800067ab  mov     edx, 0E01h; void *
0x1800067b0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800067b6  mov     rcx, [rsp+48h]; this
0x1800067bb  mov     edx, 0A15h; void *
0x1800067c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067c6  mov     rcx, [rsp+48h]; this
0x1800067cb  mov     edx, 0A15h; void *
0x1800067d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
