# CThreadPool::AddWorkItem(ulong (*)(void *),void *,void *,ulong)

- ea: `0x180023d74`
- end: `0x180023e7e`
- name: `?AddWorkItem@CThreadPool@@QEAAJP6AKPEAX@Z00K@Z`
- size: `266`
- prototype: `__int64 __fastcall(CThreadPool *this, unsigned int (*)(void *), void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036c28`

## callees

- `0x180023d74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023d9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023d9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023d8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023d8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023e69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023e69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e76`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180023e3f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180023e3f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180023dde`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180023dde`

## pseudocode

```c
__int64 __fastcall CThreadPool::AddWorkItem(CThreadPool *this, unsigned int (*a2)(void *), void *a3, void *a4)
{
  HANDLE ProcessHeap; // rax
  HANDLE *v9; // rax
  HANDLE *v10; // rdi
  unsigned int v11; // ebx
  HANDLE *v12; // rsi
  signed int v13; // eax
  HANDLE v14; // rax
  signed int LastError; // eax

  ProcessHeap = GetProcessHeap();
  v9 = (HANDLE *)HeapAlloc(ProcessHeap, 0, 0x20u);
  v10 = v9;
  if ( !v9 )
  {
    SetLastError(8u);
    return (unsigned int)-2147024882;
  }
  v11 = 0;
  v9[1] = a3;
  *v9 = a2;
  v12 = v9 + 2;
  v9[2] = 0;
  *((_DWORD *)v9 + 6) = 16;
  if ( !a4 || DuplicateTokenEx(a4, 0xCu, 0, SecurityImpersonation, TokenImpersonation, v9 + 2) )
    goto LABEL_18;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( (v11 & 0x80000000) == 0 )
  {
LABEL_18:
    if ( TrySubmitThreadpoolCallback(
           (PTP_SIMPLE_CALLBACK)_WorkItemWrapper,
           v10,
           (PTP_CALLBACK_ENVIRON)((char *)this + 8)) )
    {
      return v11;
    }
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( *v12 )
    CloseHandle(*v12);
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v10);
  return v11;
}

```

## disassembly

```asm
0x180023d74  push    rbx
0x180023d76  push    rbp
0x180023d77  push    rsi
0x180023d78  push    rdi
0x180023d79  push    r14
0x180023d7b  push    r15
0x180023d7d  sub     rsp, 38h
0x180023d81  mov     rbp, r9
0x180023d84  mov     rsi, r8
0x180023d87  mov     r14, rdx
0x180023d8a  mov     r15, rcx
0x180023d8d  call    cs:__imp_GetProcessHeap
0x180023d93  xor     edx, edx; dwFlags
0x180023d95  mov     rcx, rax; hHeap
0x180023d98  lea     r8d, [rdx+20h]; dwBytes
0x180023d9c  call    cs:__imp_HeapAlloc
0x180023da2  mov     rdi, rax
0x180023da5  test    rax, rax
0x180023da8  jz      loc_180023E64
0x180023dae  xor     ebx, ebx
0x180023db0  mov     [rax+8], rsi
0x180023db4  mov     [rax], r14
0x180023db7  lea     rsi, [rax+10h]
0x180023dbb  mov     [rsi], rbx
0x180023dbe  mov     r14d, 80070000h
0x180023dc4  mov     dword ptr [rax+18h], 10h
0x180023dcb  test    rbp, rbp
0x180023dce  jnz     short loc_180023E25
0x180023dd0  lea     r8, [r15+8]; pcbe
0x180023dd4  mov     rdx, rdi; pv
0x180023dd7  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180023dde  call    cs:__imp_TrySubmitThreadpoolCallback
0x180023de4  test    eax, eax
0x180023de6  jnz     short loc_180023E16
0x180023de8  call    cs:__imp_GetLastError
0x180023dee  mov     ebx, eax
0x180023df0  test    eax, eax
0x180023df2  jle     short loc_180023DFA
0x180023df4  movzx   ebx, ax
0x180023df7  or      ebx, r14d
0x180023dfa  mov     rcx, [rsi]; hObject
0x180023dfd  test    rcx, rcx
0x180023e00  jnz     short loc_180023E76
0x180023e02  call    cs:__imp_GetProcessHeap
0x180023e08  mov     r8, rdi; lpMem
0x180023e0b  xor     edx, edx; dwFlags
0x180023e0d  mov     rcx, rax; hHeap
0x180023e10  call    cs:__imp_HeapFree
0x180023e16  mov     eax, ebx
0x180023e18  add     rsp, 38h
0x180023e1c  pop     r15
0x180023e1e  pop     r14
0x180023e20  pop     rdi
0x180023e21  pop     rsi
0x180023e22  pop     rbp
0x180023e23  pop     rbx
0x180023e24  retn
0x180023e25  mov     r9d, 2; ImpersonationLevel
0x180023e2b  mov     [rsp+68h+phNewToken], rsi; phNewToken
0x180023e30  xor     r8d, r8d; lpTokenAttributes
0x180023e33  mov     [rsp+68h+TokenType], r9d; TokenType
0x180023e38  mov     rcx, rbp; hExistingToken
0x180023e3b  lea     edx, [r9+0Ah]; dwDesiredAccess
0x180023e3f  call    cs:__imp_DuplicateTokenEx
0x180023e45  test    eax, eax
0x180023e47  jnz     short loc_180023DD0
0x180023e49  call    cs:__imp_GetLastError
0x180023e4f  mov     ebx, eax
0x180023e51  test    eax, eax
0x180023e53  jle     short loc_180023E5B
0x180023e55  movzx   ebx, ax
0x180023e58  or      ebx, r14d
0x180023e5b  test    ebx, ebx
0x180023e5d  js      short loc_180023DFA
0x180023e5f  jmp     loc_180023DD0
0x180023e64  mov     ecx, 8; dwErrCode
0x180023e69  call    cs:__imp_SetLastError
0x180023e6f  mov     ebx, 8007000Eh
0x180023e74  jmp     short loc_180023E16
0x180023e76  call    cs:__imp_CloseHandle
0x180023e7c  jmp     short loc_180023E02
```
