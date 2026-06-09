# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x14000473c`
- end: `0x1400048d7`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `411`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140005e60`

## callees

- `0x140002b08`
- `0x140003450`
- `0x14000473c`
- `0x1400057ac`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004843`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004843`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004835`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004835`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400047cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400047fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004827`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400047cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400047fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000477b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000477b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000481b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004853`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000481b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004853`

## string_xrefs

- `0x140004875`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140004897`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400048ae`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400048c5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  int result; // eax
  void *v8; // rsi
  DWORD LastError; // ebp
  const char *v10; // r9
  void *v11; // rsi
  DWORD v12; // ebp
  const char *v13; // r9
  DWORD v14; // esi
  const char *v15; // r9
  HANDLE ProcessHeap; // rax
  const char *v17; // r9
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v17);
      }
    }
    else
    {
      v8 = (void *)lpMem[2];
      if ( v8 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v10);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v11 = (void *)lpMem[3];
      if ( v11 )
      {
        v12 = GetLastError();
        if ( !CloseHandle(v11) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v13);
        SetLastError(v12);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v14 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v15);
        SetLastError(v14);
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
0x14000473c  push    rbx
0x14000473e  push    rbp
0x14000473f  push    rsi
0x140004740  push    rdi
0x140004741  sub     rsp, 28h
0x140004745  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000474c  mov     rbx, rcx
0x14000474f  jnz     loc_14000485F
0x140004755  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000475c  test    rax, rax
0x14000475f  jz      short loc_14000476E
0x140004761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004766  test    al, al
0x140004768  jnz     loc_14000485F
0x14000476e  mov     rdi, [rbx+8]
0x140004772  xor     r8d, r8d; bAlertable
0x140004775  mov     rcx, rdi; hHandle
0x140004778  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000477b  call    cs:__imp_WaitForSingleObjectEx
0x140004781  cmp     eax, 102h
0x140004786  jz      short loc_140004795
0x140004788  test    eax, 0FFFFFF7Fh
0x14000478d  jnz     loc_140004887
0x140004793  jmp     short loc_140004797
0x140004795  xor     edi, edi
0x140004797  mov     eax, [rbx]
0x140004799  dec     eax
0x14000479b  mov     [rbx], eax
0x14000479d  mov     eax, [rbx]
0x14000479f  test    eax, eax
0x1400047a1  jnz     loc_14000484B
0x1400047a7  mov     rsi, [rbx+10h]
0x1400047ab  test    rsi, rsi
0x1400047ae  jz      short loc_1400047D1
0x1400047b0  call    cs:__imp_GetLastError
0x1400047b6  mov     rcx, rsi; hObject
0x1400047b9  mov     ebp, eax
0x1400047bb  call    cs:__imp_CloseHandle
0x1400047c1  test    eax, eax
0x1400047c3  jz      loc_1400048A9
0x1400047c9  mov     ecx, ebp; dwErrCode
0x1400047cb  call    cs:__imp_SetLastError
0x1400047d1  mov     qword ptr [rbx+10h], 0
0x1400047d9  mov     rsi, [rbx+18h]
0x1400047dd  test    rsi, rsi
0x1400047e0  jz      short loc_140004803
0x1400047e2  call    cs:__imp_GetLastError
0x1400047e8  mov     rcx, rsi; hObject
0x1400047eb  mov     ebp, eax
0x1400047ed  call    cs:__imp_CloseHandle
0x1400047f3  test    eax, eax
0x1400047f5  jz      loc_1400048C0
0x1400047fb  mov     ecx, ebp; dwErrCode
0x1400047fd  call    cs:__imp_SetLastError
0x140004803  mov     qword ptr [rbx+18h], 0
0x14000480b  test    rdi, rdi
0x14000480e  jz      short loc_14000482D
0x140004810  call    cs:__imp_GetLastError
0x140004816  mov     rcx, rdi; hMutex
0x140004819  mov     esi, eax
0x14000481b  call    cs:__imp_ReleaseMutex
0x140004821  test    eax, eax
0x140004823  jz      short loc_140004870
0x140004825  mov     ecx, esi; dwErrCode
0x140004827  call    cs:__imp_SetLastError
0x14000482d  mov     rcx, rbx
0x140004830  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x140004835  call    cs:__imp_GetProcessHeap
0x14000483b  mov     r8, rbx; lpMem
0x14000483e  xor     edx, edx; dwFlags
0x140004840  mov     rcx, rax; hHeap
0x140004843  call    cs:__imp_HeapFree
0x140004849  jmp     short loc_140004867
0x14000484b  test    rdi, rdi
0x14000484e  jz      short loc_140004867
0x140004850  mov     rcx, rdi; hMutex
0x140004853  call    cs:__imp_ReleaseMutex
0x140004859  test    eax, eax
0x14000485b  jz      short loc_140004892
0x14000485d  jmp     short loc_140004867
0x14000485f  mov     eax, [rbx]
0x140004861  dec     eax
0x140004863  mov     [rbx], eax
0x140004865  mov     eax, [rbx]
0x140004867  add     rsp, 28h
0x14000486b  pop     rdi
0x14000486c  pop     rsi
0x14000486d  pop     rbp
0x14000486e  pop     rbx
0x14000486f  retn
0x140004870  mov     rcx, [rsp+48h]; this
0x140004875  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000487c  mov     edx, 0A15h; void *
0x140004881  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004887  mov     rcx, [rsp+48h]; this
0x14000488c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004892  mov     rcx, [rsp+48h]; this
0x140004897  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000489e  mov     edx, 0A15h; void *
0x1400048a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400048a9  mov     rcx, [rsp+48h]; this
0x1400048ae  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400048b5  mov     edx, 0A0Bh; void *
0x1400048ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400048c0  mov     rcx, [rsp+48h]; this
0x1400048c5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400048cc  mov     edx, 0A0Bh; void *
0x1400048d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
