# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1800070e4`
- end: `0x18000720b`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `295`
- prototype: `int __fastcall(__int64 *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180036bc0`

## callees

- `0x180004f90`
- `0x180005b08`
- `0x180005bb8`
- `0x1800070e4`
- `0x18000864c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000716a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800071a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000716a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800071a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007129`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007129`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007192`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007184`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000715f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000715f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007176`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007176`

## string_xrefs

- `0x1800071cb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800071e2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800071f9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(__int64 *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  const char *v9; // r9
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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v9);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v7);
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
0x1800070e4  mov     [rsp+arg_0], rbx
0x1800070e9  mov     [rsp+arg_8], rsi
0x1800070ee  push    rdi
0x1800070ef  sub     rsp, 20h
0x1800070f3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800070fa  mov     rbx, rcx
0x1800070fd  jnz     loc_1800071AE
0x180007103  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000710a  test    rax, rax
0x18000710d  jz      short loc_18000711C
0x18000710f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007114  test    al, al
0x180007116  jnz     loc_1800071AE
0x18000711c  mov     rdi, [rbx+8]
0x180007120  xor     r8d, r8d; bAlertable
0x180007123  mov     rcx, rdi; hHandle
0x180007126  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007129  call    cs:__imp_WaitForSingleObjectEx
0x18000712f  cmp     eax, 102h
0x180007134  jz      short loc_180007143
0x180007136  test    eax, 0FFFFFF7Fh
0x18000713b  jnz     loc_1800071DD
0x180007141  jmp     short loc_180007145
0x180007143  xor     edi, edi
0x180007145  mov     eax, [rbx]
0x180007147  dec     eax
0x180007149  mov     [rbx], eax
0x18000714b  mov     eax, [rbx]
0x18000714d  test    eax, eax
0x18000714f  jnz     short loc_18000719A
0x180007151  lea     rcx, [rbx+10h]; this
0x180007155  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000715a  test    rdi, rdi
0x18000715d  jz      short loc_18000717C
0x18000715f  call    cs:__imp_GetLastError
0x180007165  mov     rcx, rdi; hMutex
0x180007168  mov     esi, eax
0x18000716a  call    cs:__imp_ReleaseMutex
0x180007170  test    eax, eax
0x180007172  jz      short loc_1800071C6
0x180007174  mov     ecx, esi; dwErrCode
0x180007176  call    cs:__imp_SetLastError
0x18000717c  mov     rcx, rbx
0x18000717f  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180007184  call    cs:__imp_GetProcessHeap
0x18000718a  mov     r8, rbx; lpMem
0x18000718d  xor     edx, edx; dwFlags
0x18000718f  mov     rcx, rax; hHeap
0x180007192  call    cs:__imp_HeapFree
0x180007198  jmp     short loc_1800071B6
0x18000719a  test    rdi, rdi
0x18000719d  jz      short loc_1800071B6
0x18000719f  mov     rcx, rdi; hMutex
0x1800071a2  call    cs:__imp_ReleaseMutex
0x1800071a8  test    eax, eax
0x1800071aa  jz      short loc_1800071F4
0x1800071ac  jmp     short loc_1800071B6
0x1800071ae  mov     eax, [rbx]
0x1800071b0  dec     eax
0x1800071b2  mov     [rbx], eax
0x1800071b4  mov     eax, [rbx]
0x1800071b6  mov     rbx, [rsp+28h+arg_0]
0x1800071bb  mov     rsi, [rsp+28h+arg_8]
0x1800071c0  add     rsp, 20h
0x1800071c4  pop     rdi
0x1800071c5  retn
0x1800071c6  mov     rcx, [rsp+28h]; this
0x1800071cb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800071d2  mov     edx, 0A15h; void *
0x1800071d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071dd  mov     rcx, [rsp+28h]; this
0x1800071e2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800071e9  mov     edx, 0E01h; void *
0x1800071ee  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800071f4  mov     rcx, [rsp+28h]; this
0x1800071f9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007200  mov     edx, 0A15h; void *
0x180007205  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
