# FSMSynchronizeEndpoint

- ea: `0x1800a9484`
- end: `0x1800a964f`
- name: `FSMSynchronizeEndpoint`
- size: `459`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800a0720`
- `0x1800a0ff0`
- `0x1800a1cb4`

## callees

- `0x18001ceb4`
- `0x1800a269c`
- `0x1800a9484`
- `0x1800ace9c`

## import_xrefs

- `WS2_32!WSAResetEvent` at `0x1800a957f`
- `WS2_32!WSAResetEvent` at `0x1800a957f`
- `WS2_32!WSACloseEvent` at `0x1800a95f3`
- `WS2_32!WSACloseEvent` at `0x1800a95f3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a958f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a9603`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a958f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a9603`
- `KERNEL32!WaitForSingleObject` at `0x1800a9526`
- `KERNEL32!WaitForSingleObject` at `0x1800a9526`
- `KERNEL32!SetEvent` at `0x1800a94be`
- `KERNEL32!SetEvent` at `0x1800a94be`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a94cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a9510`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a9557`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a95e0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a94cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a9510`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a9557`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800a95e0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a94af`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a94ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a953a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a95c2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a94af`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a94ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a953a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800a95c2`
- `KERNEL32!GetLastError` at `0x1800a94df`
- `KERNEL32!GetLastError` at `0x1800a94df`

## string_xrefs

- `0x1800a9615`: `WSACloseEvent`

## pseudocode

```c
DWORD __fastcall FSMSynchronizeEndpoint(__int64 a1, void *a2, int a3)
{
  RTL_SRWLOCK *v3; // rbp
  unsigned int v7; // esi
  _DWORD *v9; // rbx
  void *v10; // rcx
  _DWORD *v11; // r14
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
    if ( !*v9 )
      v7 = 20127;
    *v11 = 0;
    ReleaseSRWLockExclusive(v3);
  }
  return v7;
}

```

## disassembly

```asm
0x1800a9484  mov     rax, rsp
0x1800a9487  mov     [rax+8], rbx
0x1800a948b  mov     [rax+10h], rbp
0x1800a948f  mov     [rax+18h], rsi
0x1800a9493  mov     [rax+20h], rdi
0x1800a9497  push    r14
0x1800a9499  sub     rsp, 20h
0x1800a949d  lea     rbp, [rcx+48h]
0x1800a94a1  mov     rdi, rcx
0x1800a94a4  mov     rcx, rbp; SRWLock
0x1800a94a7  mov     r14d, r8d
0x1800a94aa  mov     rbx, rdx
0x1800a94ad  xor     esi, esi
0x1800a94af  call    cs:__imp_AcquireSRWLockExclusive
0x1800a94b6  nop     dword ptr [rax+rax+00h]
0x1800a94bb  mov     rcx, rbx; hEvent
0x1800a94be  call    cs:__imp_SetEvent
0x1800a94c5  nop     dword ptr [rax+rax+00h]
0x1800a94ca  mov     rcx, rbp; SRWLock
0x1800a94cd  mov     ebx, eax
0x1800a94cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a94d6  nop     dword ptr [rax+rax+00h]
0x1800a94db  test    ebx, ebx
0x1800a94dd  jnz     short loc_1800A94F0
0x1800a94df  call    cs:__imp_GetLastError
0x1800a94e6  nop     dword ptr [rax+rax+00h]
0x1800a94eb  jmp     loc_1800A9633
0x1800a94f0  lea     rbx, [rdi+230h]
0x1800a94f7  test    r14d, r14d
0x1800a94fa  jnz     short loc_1800A951C
0x1800a94fc  mov     rcx, rbp; SRWLock
0x1800a94ff  call    cs:__imp_AcquireSRWLockExclusive
0x1800a9506  nop     dword ptr [rax+rax+00h]
0x1800a950b  and     [rbx], esi
0x1800a950d  mov     rcx, rbp; SRWLock
0x1800a9510  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a9517  nop     dword ptr [rax+rax+00h]
0x1800a951c  mov     rcx, [rdi+0F8h]; hHandle
0x1800a9523  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a9526  call    cs:__imp_WaitForSingleObject
0x1800a952d  nop     dword ptr [rax+rax+00h]
0x1800a9532  cmp     eax, 0FFFFFFFFh
0x1800a9535  jnz     short loc_1800A956B
0x1800a9537  mov     rcx, rbp; SRWLock
0x1800a953a  call    cs:__imp_AcquireSRWLockExclusive
0x1800a9541  nop     dword ptr [rax+rax+00h]
0x1800a9546  or      ecx, 0FFFFFFFFh
0x1800a9549  call    GetErrorBitMask
0x1800a954e  or      [rdi+1F4h], eax
0x1800a9554  mov     rcx, rbp; SRWLock
0x1800a9557  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a955e  nop     dword ptr [rax+rax+00h]
0x1800a9563  mov     rcx, rdi
0x1800a9566  call    DhcpFSMHandleError
0x1800a956b  mov     rcx, [rdi+0F8h]; hEvent
0x1800a9572  test    r14d, r14d
0x1800a9575  jnz     short loc_1800A95EE
0x1800a9577  mov     r14, rbx
0x1800a957a  test    rcx, rcx
0x1800a957d  jz      short loc_1800A95BF
0x1800a957f  call    cs:__imp_WSAResetEvent
0x1800a9586  nop     dword ptr [rax+rax+00h]
0x1800a958b  test    eax, eax
0x1800a958d  jnz     short loc_1800A95BF
0x1800a958f  call    cs:__imp_WSAGetLastError
0x1800a9596  nop     dword ptr [rax+rax+00h]
0x1800a959b  mov     r9d, 17FAh
0x1800a95a1  lea     r8, aWsaresetevent; "WSAResetEvent"
0x1800a95a8  mov     ecx, eax
0x1800a95aa  lea     rdx, aFsmsynchronize; "FSMSynchronizeEndpoint"
0x1800a95b1  mov     esi, eax
0x1800a95b3  call    DhcpPrintFOErrorEx
0x1800a95b8  lea     r14, [rdi+230h]
0x1800a95bf  mov     rcx, rbp; SRWLock
0x1800a95c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800a95c9  nop     dword ptr [rax+rax+00h]
0x1800a95ce  cmp     dword ptr [rbx], 0
0x1800a95d1  mov     eax, 4E9Fh
0x1800a95d6  mov     rcx, rbp; SRWLock
0x1800a95d9  cmovz   esi, eax
0x1800a95dc  and     dword ptr [r14], 0
0x1800a95e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a95e7  nop     dword ptr [rax+rax+00h]
0x1800a95ec  jmp     short loc_1800A9631
0x1800a95ee  test    rcx, rcx
0x1800a95f1  jz      short loc_1800A9631
0x1800a95f3  call    cs:__imp_WSACloseEvent
0x1800a95fa  nop     dword ptr [rax+rax+00h]
0x1800a95ff  test    eax, eax
0x1800a9601  jnz     short loc_1800A962A
0x1800a9603  call    cs:__imp_WSAGetLastError
0x1800a960a  nop     dword ptr [rax+rax+00h]
0x1800a960f  mov     r9d, 17FDh
0x1800a9615  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800a961c  mov     ecx, eax
0x1800a961e  lea     rdx, aFsmsynchronize; "FSMSynchronizeEndpoint"
0x1800a9625  call    DhcpPrintFOErrorEx
0x1800a962a  and     [rdi+0F8h], rsi
0x1800a9631  mov     eax, esi
0x1800a9633  mov     rbx, [rsp+28h+arg_0]
0x1800a9638  mov     rbp, [rsp+28h+arg_8]
0x1800a963d  mov     rsi, [rsp+28h+arg_10]
0x1800a9642  mov     rdi, [rsp+28h+arg_18]
0x1800a9647  add     rsp, 20h
0x1800a964b  pop     r14
0x1800a964d  retn
```
