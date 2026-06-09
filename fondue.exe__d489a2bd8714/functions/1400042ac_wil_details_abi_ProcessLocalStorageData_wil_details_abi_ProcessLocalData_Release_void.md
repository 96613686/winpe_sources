# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1400042ac`
- end: `0x14000442b`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `383`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140004e60`

## callees

- `0x140002968`
- `0x140003080`
- `0x1400042ac`
- `0x140004c0c`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004320`
- `KERNEL32!GetLastError` at `0x140004352`
- `KERNEL32!GetLastError` at `0x140004380`
- `KERNEL32!GetLastError` at `0x140004320`
- `KERNEL32!GetLastError` at `0x140004352`
- `KERNEL32!GetLastError` at `0x140004380`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000433b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000436d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004397`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000433b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000436d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004397`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400042eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400042eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000438b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400043c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000438b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400043c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000432b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000435d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000432b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000435d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400043a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400043a5`

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
  unsigned int v10; // r8d
  const char *v11; // r9
  void *v12; // rsi
  DWORD v13; // ebp
  unsigned int v14; // r8d
  const char *v15; // r9
  DWORD v16; // esi
  unsigned int v17; // r8d
  const char *v18; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
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
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v20, v21);
      }
    }
    else
    {
      v8 = (void *)lpMem[2];
      if ( v8 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v12 = (void *)lpMem[3];
      if ( v12 )
      {
        v13 = GetLastError();
        if ( !CloseHandle(v12) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
        SetLastError(v13);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v16 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
        SetLastError(v16);
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
0x1400042ac  push    rbx
0x1400042ae  push    rbp
0x1400042af  push    rsi
0x1400042b0  push    rdi
0x1400042b1  sub     rsp, 28h
0x1400042b5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400042bc  mov     rbx, rcx
0x1400042bf  jnz     loc_1400043CF
0x1400042c5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400042cc  test    rax, rax
0x1400042cf  jz      short loc_1400042DE
0x1400042d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042d6  test    al, al
0x1400042d8  jnz     loc_1400043CF
0x1400042de  mov     rdi, [rbx+8]
0x1400042e2  xor     r8d, r8d; bAlertable
0x1400042e5  mov     rcx, rdi; hHandle
0x1400042e8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400042eb  call    cs:__imp_WaitForSingleObjectEx
0x1400042f1  cmp     eax, 102h
0x1400042f6  jz      short loc_140004305
0x1400042f8  test    eax, 0FFFFFF7Fh
0x1400042fd  jnz     loc_1400043F0
0x140004303  jmp     short loc_140004307
0x140004305  xor     edi, edi
0x140004307  mov     eax, [rbx]
0x140004309  dec     eax
0x14000430b  mov     [rbx], eax
0x14000430d  mov     eax, [rbx]
0x14000430f  test    eax, eax
0x140004311  jnz     loc_1400043BB
0x140004317  mov     rsi, [rbx+10h]
0x14000431b  test    rsi, rsi
0x14000431e  jz      short loc_140004341
0x140004320  call    cs:__imp_GetLastError
0x140004326  mov     rcx, rsi; hObject
0x140004329  mov     ebp, eax
0x14000432b  call    cs:__imp_CloseHandle
0x140004331  test    eax, eax
0x140004333  jz      loc_14000440B
0x140004339  mov     ecx, ebp; dwErrCode
0x14000433b  call    cs:__imp_SetLastError
0x140004341  mov     qword ptr [rbx+10h], 0
0x140004349  mov     rsi, [rbx+18h]
0x14000434d  test    rsi, rsi
0x140004350  jz      short loc_140004373
0x140004352  call    cs:__imp_GetLastError
0x140004358  mov     rcx, rsi; hObject
0x14000435b  mov     ebp, eax
0x14000435d  call    cs:__imp_CloseHandle
0x140004363  test    eax, eax
0x140004365  jz      loc_14000441B
0x14000436b  mov     ecx, ebp; dwErrCode
0x14000436d  call    cs:__imp_SetLastError
0x140004373  mov     qword ptr [rbx+18h], 0
0x14000437b  test    rdi, rdi
0x14000437e  jz      short loc_14000439D
0x140004380  call    cs:__imp_GetLastError
0x140004386  mov     rcx, rdi; hMutex
0x140004389  mov     esi, eax
0x14000438b  call    cs:__imp_ReleaseMutex
0x140004391  test    eax, eax
0x140004393  jz      short loc_1400043E0
0x140004395  mov     ecx, esi; dwErrCode
0x140004397  call    cs:__imp_SetLastError
0x14000439d  mov     rcx, rbx
0x1400043a0  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x1400043a5  call    cs:__imp_GetProcessHeap
0x1400043ab  mov     r8, rbx; lpMem
0x1400043ae  xor     edx, edx; dwFlags
0x1400043b0  mov     rcx, rax; hHeap
0x1400043b3  call    cs:__imp_HeapFree
0x1400043b9  jmp     short loc_1400043D7
0x1400043bb  test    rdi, rdi
0x1400043be  jz      short loc_1400043D7
0x1400043c0  mov     rcx, rdi; hMutex
0x1400043c3  call    cs:__imp_ReleaseMutex
0x1400043c9  test    eax, eax
0x1400043cb  jz      short loc_1400043FB
0x1400043cd  jmp     short loc_1400043D7
0x1400043cf  mov     eax, [rbx]
0x1400043d1  dec     eax
0x1400043d3  mov     [rbx], eax
0x1400043d5  mov     eax, [rbx]
0x1400043d7  add     rsp, 28h
0x1400043db  pop     rdi
0x1400043dc  pop     rsi
0x1400043dd  pop     rbp
0x1400043de  pop     rbx
0x1400043df  retn
0x1400043e0  mov     rcx, [rsp+48h]; this
0x1400043e5  mov     edx, 0A15h; void *
0x1400043ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400043f0  mov     rcx, [rsp+48h]; this
0x1400043f5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400043fb  mov     rcx, [rsp+48h]; this
0x140004400  mov     edx, 0A15h; void *
0x140004405  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000440b  mov     rcx, [rsp+48h]; this
0x140004410  mov     edx, 0A0Bh; void *
0x140004415  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000441b  mov     rcx, [rsp+48h]; this
0x140004420  mov     edx, 0A0Bh; void *
0x140004425  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
