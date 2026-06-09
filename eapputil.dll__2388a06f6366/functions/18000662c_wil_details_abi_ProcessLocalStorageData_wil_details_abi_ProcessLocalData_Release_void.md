# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000662c`
- end: `0x180006745`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180032990`

## callees

- `0x180004538`
- `0x180004fc0`
- `0x180005218`
- `0x18000662c`
- `0x180007a3c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006671`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a7`

## string_xrefs

- `0x180006723`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v10; // r8d
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
0x18000662c  mov     [rsp+arg_0], rbx
0x180006631  mov     [rsp+arg_8], rsi
0x180006636  push    rdi
0x180006637  sub     rsp, 20h
0x18000663b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006642  mov     rbx, rcx
0x180006645  jnz     loc_1800066F6
0x18000664b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006652  test    rax, rax
0x180006655  jz      short loc_180006664
0x180006657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665c  test    al, al
0x18000665e  jnz     loc_1800066F6
0x180006664  mov     rdi, [rbx+8]
0x180006668  xor     r8d, r8d; bAlertable
0x18000666b  mov     rcx, rdi; hHandle
0x18000666e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006671  call    cs:__imp_WaitForSingleObjectEx
0x180006677  cmp     eax, 102h
0x18000667c  jz      short loc_18000668B
0x18000667e  test    eax, 0FFFFFF7Fh
0x180006683  jnz     loc_18000671E
0x180006689  jmp     short loc_18000668D
0x18000668b  xor     edi, edi
0x18000668d  mov     eax, [rbx]
0x18000668f  dec     eax
0x180006691  mov     [rbx], eax
0x180006693  mov     eax, [rbx]
0x180006695  test    eax, eax
0x180006697  jnz     short loc_1800066E2
0x180006699  lea     rcx, [rbx+10h]; this
0x18000669d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800066a2  test    rdi, rdi
0x1800066a5  jz      short loc_1800066C4
0x1800066a7  call    cs:__imp_GetLastError
0x1800066ad  mov     rcx, rdi; hMutex
0x1800066b0  mov     esi, eax
0x1800066b2  call    cs:__imp_ReleaseMutex
0x1800066b8  test    eax, eax
0x1800066ba  jz      short loc_18000670E
0x1800066bc  mov     ecx, esi; dwErrCode
0x1800066be  call    cs:__imp_SetLastError
0x1800066c4  mov     rcx, rbx
0x1800066c7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x1800066cc  call    cs:__imp_GetProcessHeap
0x1800066d2  mov     r8, rbx; lpMem
0x1800066d5  xor     edx, edx; dwFlags
0x1800066d7  mov     rcx, rax; hHeap
0x1800066da  call    cs:__imp_HeapFree
0x1800066e0  jmp     short loc_1800066FE
0x1800066e2  test    rdi, rdi
0x1800066e5  jz      short loc_1800066FE
0x1800066e7  mov     rcx, rdi; hMutex
0x1800066ea  call    cs:__imp_ReleaseMutex
0x1800066f0  test    eax, eax
0x1800066f2  jz      short loc_180006735
0x1800066f4  jmp     short loc_1800066FE
0x1800066f6  mov     eax, [rbx]
0x1800066f8  dec     eax
0x1800066fa  mov     [rbx], eax
0x1800066fc  mov     eax, [rbx]
0x1800066fe  mov     rbx, [rsp+28h+arg_0]
0x180006703  mov     rsi, [rsp+28h+arg_8]
0x180006708  add     rsp, 20h
0x18000670c  pop     rdi
0x18000670d  retn
0x18000670e  mov     rcx, [rsp+28h]; this
0x180006713  mov     edx, 0A15h; void *
0x180006718  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000671e  mov     rcx, [rsp+28h]; this
0x180006723  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000672a  mov     edx, 0E01h; void *
0x18000672f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006735  mov     rcx, [rsp+28h]; this
0x18000673a  mov     edx, 0A15h; void *
0x18000673f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
