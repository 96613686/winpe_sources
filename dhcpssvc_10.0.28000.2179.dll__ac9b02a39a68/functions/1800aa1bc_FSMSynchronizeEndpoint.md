# FSMSynchronizeEndpoint

- ea: `0x1800aa1bc`
- end: `0x1800aa38a`
- name: `FSMSynchronizeEndpoint`
- size: `462`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800a1404`
- `0x1800a1ce4`
- `0x1800a29c4`

## callees

- `0x18001c45c`
- `0x1800a33c8`
- `0x1800aa1bc`
- `0x1800adbf0`

## import_xrefs

- `WS2_32!WSAResetEvent` at `0x1800aa2b7`
- `WS2_32!WSAResetEvent` at `0x1800aa2b7`
- `WS2_32!WSACloseEvent` at `0x1800aa32e`
- `WS2_32!WSACloseEvent` at `0x1800aa32e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aa2c7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aa33e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aa2c7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aa33e`
- `KERNEL32!WaitForSingleObject` at `0x1800aa25e`
- `KERNEL32!WaitForSingleObject` at `0x1800aa25e`
- `KERNEL32!SetEvent` at `0x1800aa1f6`
- `KERNEL32!SetEvent` at `0x1800aa1f6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa207`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa248`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa28f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa31b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa207`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa248`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa28f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aa31b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa1e7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa237`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa272`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa2fa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa1e7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa237`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa272`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa2fa`
- `KERNEL32!GetLastError` at `0x1800aa217`
- `KERNEL32!GetLastError` at `0x1800aa217`

## string_xrefs

- `0x1800aa350`: `WSACloseEvent`

## pseudocode

```c
DWORD __fastcall FSMSynchronizeEndpoint(__int64 a1, void *a2, int a3)
{
  RTL_SRWLOCK *v3; // rbp
  unsigned int v7; // esi
  _DWORD *v9; // rbx
  void *v10; // rcx
  _DWORD *v11; // r14
  bool v12; // zf
  unsigned int Error; // eax

  v3 = (RTL_SRWLOCK *)(a1 + 72);
  v7 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  LODWORD(a2) = SetEvent(a2);
  ReleaseSRWLockExclusive(v3);
  if ( !(_DWORD)a2 )
    return GetLastError();
  v9 = (_DWORD *)(a1 + 560);
  if ( !a3 )
  {
    AcquireSRWLockExclusive(v3);
    *v9 = 0;
    ReleaseSRWLockExclusive(v3);
  }
  if ( WaitForSingleObject(*(HANDLE *)(a1 + 248), 0xFFFFFFFF) == -1 )
  {
    AcquireSRWLockExclusive(v3);
    *(_DWORD *)(a1 + 500) |= GetErrorBitMask(0xFFFFFFFFLL);
    ReleaseSRWLockExclusive(v3);
    DhcpFSMHandleError(a1);
  }
  v10 = *(void **)(a1 + 248);
  if ( a3 )
  {
    if ( v10 )
    {
      if ( !WSACloseEvent(v10) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "FSMSynchronizeEndpoint", "WSACloseEvent", 6141);
      }
      *(_QWORD *)(a1 + 248) = 0;
    }
  }
  else
  {
    v11 = (_DWORD *)(a1 + 560);
    if ( v10 && !WSAResetEvent(v10) )
    {
      v7 = WSAGetLastError();
      DhcpPrintFOErrorEx(v7, "FSMSynchronizeEndpoint", "WSAResetEvent", 6138);
      v11 = (_DWORD *)(a1 + 560);
    }
    AcquireSRWLockExclusive(v3);
    v12 = *v9 == 0;
    *v11 = 0;
    if ( v12 )
      v7 = 20127;
    ReleaseSRWLockExclusive(v3);
  }
  return v7;
}

```

## disassembly

```asm
0x1800aa1bc  mov     rax, rsp
0x1800aa1bf  mov     [rax+8], rbx
0x1800aa1c3  mov     [rax+10h], rbp
0x1800aa1c7  mov     [rax+18h], rsi
0x1800aa1cb  mov     [rax+20h], rdi
0x1800aa1cf  push    r14
0x1800aa1d1  sub     rsp, 20h
0x1800aa1d5  lea     rbp, [rcx+48h]
0x1800aa1d9  mov     rdi, rcx
0x1800aa1dc  mov     rcx, rbp; SRWLock
0x1800aa1df  mov     r14d, r8d
0x1800aa1e2  mov     rbx, rdx
0x1800aa1e5  xor     esi, esi
0x1800aa1e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa1ee  nop     dword ptr [rax+rax+00h]
0x1800aa1f3  mov     rcx, rbx; hEvent
0x1800aa1f6  call    cs:__imp_SetEvent
0x1800aa1fd  nop     dword ptr [rax+rax+00h]
0x1800aa202  mov     rcx, rbp; SRWLock
0x1800aa205  mov     ebx, eax
0x1800aa207  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa20e  nop     dword ptr [rax+rax+00h]
0x1800aa213  test    ebx, ebx
0x1800aa215  jnz     short loc_1800AA228
0x1800aa217  call    cs:__imp_GetLastError
0x1800aa21e  nop     dword ptr [rax+rax+00h]
0x1800aa223  jmp     loc_1800AA36E
0x1800aa228  lea     rbx, [rdi+230h]
0x1800aa22f  test    r14d, r14d
0x1800aa232  jnz     short loc_1800AA254
0x1800aa234  mov     rcx, rbp; SRWLock
0x1800aa237  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa23e  nop     dword ptr [rax+rax+00h]
0x1800aa243  mov     rcx, rbp; SRWLock
0x1800aa246  mov     [rbx], esi
0x1800aa248  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa24f  nop     dword ptr [rax+rax+00h]
0x1800aa254  mov     rcx, [rdi+0F8h]; hHandle
0x1800aa25b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800aa25e  call    cs:__imp_WaitForSingleObject
0x1800aa265  nop     dword ptr [rax+rax+00h]
0x1800aa26a  cmp     eax, 0FFFFFFFFh
0x1800aa26d  jnz     short loc_1800AA2A3
0x1800aa26f  mov     rcx, rbp; SRWLock
0x1800aa272  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa279  nop     dword ptr [rax+rax+00h]
0x1800aa27e  or      ecx, 0FFFFFFFFh
0x1800aa281  call    GetErrorBitMask
0x1800aa286  or      [rdi+1F4h], eax
0x1800aa28c  mov     rcx, rbp; SRWLock
0x1800aa28f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa296  nop     dword ptr [rax+rax+00h]
0x1800aa29b  mov     rcx, rdi
0x1800aa29e  call    DhcpFSMHandleError
0x1800aa2a3  mov     rcx, [rdi+0F8h]; hEvent
0x1800aa2aa  test    r14d, r14d
0x1800aa2ad  jnz     short loc_1800AA329
0x1800aa2af  mov     r14, rbx
0x1800aa2b2  test    rcx, rcx
0x1800aa2b5  jz      short loc_1800AA2F7
0x1800aa2b7  call    cs:__imp_WSAResetEvent
0x1800aa2be  nop     dword ptr [rax+rax+00h]
0x1800aa2c3  test    eax, eax
0x1800aa2c5  jnz     short loc_1800AA2F7
0x1800aa2c7  call    cs:__imp_WSAGetLastError
0x1800aa2ce  nop     dword ptr [rax+rax+00h]
0x1800aa2d3  mov     r9d, 17FAh
0x1800aa2d9  lea     r8, aWsaresetevent; "WSAResetEvent"
0x1800aa2e0  mov     ecx, eax
0x1800aa2e2  lea     rdx, aFsmsynchronize; "FSMSynchronizeEndpoint"
0x1800aa2e9  mov     esi, eax
0x1800aa2eb  call    DhcpPrintFOErrorEx
0x1800aa2f0  lea     r14, [rdi+230h]
0x1800aa2f7  mov     rcx, rbp; SRWLock
0x1800aa2fa  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa301  nop     dword ptr [rax+rax+00h]
0x1800aa306  cmp     dword ptr [rbx], 0
0x1800aa309  mov     eax, 4E9Fh
0x1800aa30e  mov     rcx, rbp; SRWLock
0x1800aa311  mov     dword ptr [r14], 0
0x1800aa318  cmovz   esi, eax
0x1800aa31b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa322  nop     dword ptr [rax+rax+00h]
0x1800aa327  jmp     short loc_1800AA36C
0x1800aa329  test    rcx, rcx
0x1800aa32c  jz      short loc_1800AA36C
0x1800aa32e  call    cs:__imp_WSACloseEvent
0x1800aa335  nop     dword ptr [rax+rax+00h]
0x1800aa33a  test    eax, eax
0x1800aa33c  jnz     short loc_1800AA365
0x1800aa33e  call    cs:__imp_WSAGetLastError
0x1800aa345  nop     dword ptr [rax+rax+00h]
0x1800aa34a  mov     r9d, 17FDh
0x1800aa350  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800aa357  mov     ecx, eax
0x1800aa359  lea     rdx, aFsmsynchronize; "FSMSynchronizeEndpoint"
0x1800aa360  call    DhcpPrintFOErrorEx
0x1800aa365  mov     [rdi+0F8h], rsi
0x1800aa36c  mov     eax, esi
0x1800aa36e  mov     rbx, [rsp+28h+arg_0]
0x1800aa373  mov     rbp, [rsp+28h+arg_8]
0x1800aa378  mov     rsi, [rsp+28h+arg_10]
0x1800aa37d  mov     rdi, [rsp+28h+arg_18]
0x1800aa382  add     rsp, 20h
0x1800aa386  pop     r14
0x1800aa388  retn
```
