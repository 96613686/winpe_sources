# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1400049fc`
- end: `0x140004b7b`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `383`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140005c30`

## callees

- `0x140002824`
- `0x140003364`
- `0x1400049fc`
- `0x14000565c`
- `0x140006010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x140004adb`
- `KERNEL32!ReleaseMutex` at `0x140004b13`
- `KERNEL32!ReleaseMutex` at `0x140004adb`
- `KERNEL32!ReleaseMutex` at `0x140004b13`
- `KERNEL32!GetLastError` at `0x140004a70`
- `KERNEL32!GetLastError` at `0x140004aa2`
- `KERNEL32!GetLastError` at `0x140004ad0`
- `KERNEL32!GetLastError` at `0x140004a70`
- `KERNEL32!GetLastError` at `0x140004aa2`
- `KERNEL32!GetLastError` at `0x140004ad0`
- `KERNEL32!WaitForSingleObjectEx` at `0x140004a3b`
- `KERNEL32!WaitForSingleObjectEx` at `0x140004a3b`
- `KERNEL32!CloseHandle` at `0x140004a7b`
- `KERNEL32!CloseHandle` at `0x140004aad`
- `KERNEL32!CloseHandle` at `0x140004a7b`
- `KERNEL32!CloseHandle` at `0x140004aad`
- `KERNEL32!GetProcessHeap` at `0x140004af5`
- `KERNEL32!GetProcessHeap` at `0x140004af5`
- `KERNEL32!SetLastError` at `0x140004a8b`
- `KERNEL32!SetLastError` at `0x140004abd`
- `KERNEL32!SetLastError` at `0x140004ae7`
- `KERNEL32!SetLastError` at `0x140004a8b`
- `KERNEL32!SetLastError` at `0x140004abd`
- `KERNEL32!SetLastError` at `0x140004ae7`
- `KERNEL32!HeapFree` at `0x140004b03`
- `KERNEL32!HeapFree` at `0x140004b03`

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
0x1400049fc  push    rbx
0x1400049fe  push    rbp
0x1400049ff  push    rsi
0x140004a00  push    rdi
0x140004a01  sub     rsp, 28h
0x140004a05  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140004a0c  mov     rbx, rcx
0x140004a0f  jnz     loc_140004B1F
0x140004a15  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140004a1c  test    rax, rax
0x140004a1f  jz      short loc_140004A2E
0x140004a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a26  test    al, al
0x140004a28  jnz     loc_140004B1F
0x140004a2e  mov     rdi, [rbx+8]
0x140004a32  xor     r8d, r8d; bAlertable
0x140004a35  mov     rcx, rdi; hHandle
0x140004a38  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004a3b  call    cs:__imp_WaitForSingleObjectEx
0x140004a41  cmp     eax, 102h
0x140004a46  jz      short loc_140004A55
0x140004a48  test    eax, 0FFFFFF7Fh
0x140004a4d  jnz     loc_140004B40
0x140004a53  jmp     short loc_140004A57
0x140004a55  xor     edi, edi
0x140004a57  mov     eax, [rbx]
0x140004a59  dec     eax
0x140004a5b  mov     [rbx], eax
0x140004a5d  mov     eax, [rbx]
0x140004a5f  test    eax, eax
0x140004a61  jnz     loc_140004B0B
0x140004a67  mov     rsi, [rbx+10h]
0x140004a6b  test    rsi, rsi
0x140004a6e  jz      short loc_140004A91
0x140004a70  call    cs:__imp_GetLastError
0x140004a76  mov     rcx, rsi; hObject
0x140004a79  mov     ebp, eax
0x140004a7b  call    cs:__imp_CloseHandle
0x140004a81  test    eax, eax
0x140004a83  jz      loc_140004B5B
0x140004a89  mov     ecx, ebp; dwErrCode
0x140004a8b  call    cs:__imp_SetLastError
0x140004a91  mov     qword ptr [rbx+10h], 0
0x140004a99  mov     rsi, [rbx+18h]
0x140004a9d  test    rsi, rsi
0x140004aa0  jz      short loc_140004AC3
0x140004aa2  call    cs:__imp_GetLastError
0x140004aa8  mov     rcx, rsi; hObject
0x140004aab  mov     ebp, eax
0x140004aad  call    cs:__imp_CloseHandle
0x140004ab3  test    eax, eax
0x140004ab5  jz      loc_140004B6B
0x140004abb  mov     ecx, ebp; dwErrCode
0x140004abd  call    cs:__imp_SetLastError
0x140004ac3  mov     qword ptr [rbx+18h], 0
0x140004acb  test    rdi, rdi
0x140004ace  jz      short loc_140004AED
0x140004ad0  call    cs:__imp_GetLastError
0x140004ad6  mov     rcx, rdi; hMutex
0x140004ad9  mov     esi, eax
0x140004adb  call    cs:__imp_ReleaseMutex
0x140004ae1  test    eax, eax
0x140004ae3  jz      short loc_140004B30
0x140004ae5  mov     ecx, esi; dwErrCode
0x140004ae7  call    cs:__imp_SetLastError
0x140004aed  mov     rcx, rbx
0x140004af0  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x140004af5  call    cs:__imp_GetProcessHeap
0x140004afb  mov     r8, rbx; lpMem
0x140004afe  xor     edx, edx; dwFlags
0x140004b00  mov     rcx, rax; hHeap
0x140004b03  call    cs:__imp_HeapFree
0x140004b09  jmp     short loc_140004B27
0x140004b0b  test    rdi, rdi
0x140004b0e  jz      short loc_140004B27
0x140004b10  mov     rcx, rdi; hMutex
0x140004b13  call    cs:__imp_ReleaseMutex
0x140004b19  test    eax, eax
0x140004b1b  jz      short loc_140004B4B
0x140004b1d  jmp     short loc_140004B27
0x140004b1f  mov     eax, [rbx]
0x140004b21  dec     eax
0x140004b23  mov     [rbx], eax
0x140004b25  mov     eax, [rbx]
0x140004b27  add     rsp, 28h
0x140004b2b  pop     rdi
0x140004b2c  pop     rsi
0x140004b2d  pop     rbp
0x140004b2e  pop     rbx
0x140004b2f  retn
0x140004b30  mov     rcx, [rsp+48h]; this
0x140004b35  mov     edx, 0A15h; void *
0x140004b3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004b40  mov     rcx, [rsp+48h]; this
0x140004b45  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004b4b  mov     rcx, [rsp+48h]; this
0x140004b50  mov     edx, 0A15h; void *
0x140004b55  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004b5b  mov     rcx, [rsp+48h]; this
0x140004b60  mov     edx, 0A0Bh; void *
0x140004b65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004b6b  mov     rcx, [rsp+48h]; this
0x140004b70  mov     edx, 0A0Bh; void *
0x140004b75  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
