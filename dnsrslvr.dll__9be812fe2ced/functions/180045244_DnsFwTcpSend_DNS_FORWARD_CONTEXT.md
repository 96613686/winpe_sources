# DnsFwTcpSend(_DNS_FORWARD_CONTEXT *)

- ea: `0x180045244`
- end: `0x180045395`
- name: `?DnsFwTcpSend@@YAKPEAU_DNS_FORWARD_CONTEXT@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct _DNS_FORWARD_CONTEXT *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004368c`

## callees

- `0x180008b00`
- `0x1800432fc`
- `0x18004368c`
- `0x180045244`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800452ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800452ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045329`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045329`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800452d2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800452d2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180045343`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180045343`
- `WS2_32!WSASend` at `0x180045303`
- `WS2_32!WSASend` at `0x180045303`
- `WS2_32!__imp_WSAGetLastError` at `0x18004530e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004530e`

## pseudocode

```c
__int64 __fastcall DnsFwTcpSend(struct _DNS_FORWARD_CONTEXT *lpMem)
{
  unsigned int v2; // esi
  unsigned int Error; // edi
  __int64 v4; // rcx
  unsigned int v5; // eax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 38, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, lpMem);
  if ( lpMem )
  {
    Error = 0;
    *((_DWORD *)lpMem + 9) = 5;
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 8);
    AcquireSRWLockShared((PSRWLOCK)(*((_QWORD *)lpMem + 8) + 32LL));
    v4 = *((_QWORD *)lpMem + 8);
    if ( *(_QWORD *)(v4 + 48) == -1 )
    {
      v2 = 995;
    }
    else
    {
      v2 = 0;
      StartThreadpoolIo(*(PTP_IO *)(v4 + 72));
      if ( WSASend(
             *(_QWORD *)(*((_QWORD *)lpMem + 8) + 48LL),
             (LPWSABUF)((char *)lpMem + 408),
             1u,
             0,
             0,
             (LPWSAOVERLAPPED)lpMem + 15,
             0) == -1 )
      {
        Error = WSAGetLastError();
        if ( Error == 997 )
          Error = 0;
      }
    }
    ReleaseSRWLockShared((PSRWLOCK)(*((_QWORD *)lpMem + 8) + 32LL));
    DnsFwDerefContext(lpMem);
    if ( Error )
    {
      CancelThreadpoolIo(*(PTP_IO *)(*((_QWORD *)lpMem + 8) + 72LL));
      DnsFwIoCompletionRoutine(lpMem, Error, 0);
    }
  }
  else
  {
    v2 = -2147024809;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v5 = WX_WIN32_FROM_HR(v2);
    WPP_SF_d(1035, 39, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v5);
  }
  return WX_WIN32_FROM_HR(v2);
}

```

## disassembly

```asm
0x180045244  mov     [rsp+arg_8], rbx
0x180045249  mov     [rsp+arg_10], rsi
0x18004524e  push    rdi
0x18004524f  sub     rsp, 40h
0x180045253  mov     rbx, rcx
0x180045256  mov     [rsp+48h+arg_4], 0
0x18004525e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180045265  jz      short loc_180045280
0x180045267  mov     edx, 26h ; '&'
0x18004526c  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180045273  mov     ecx, 40Bh
0x180045278  mov     r9, rbx
0x18004527b  call    WPP_SF_q
0x180045280  test    rbx, rbx
0x180045283  jnz     short loc_180045297
0x180045285  mov     esi, 80070057h
0x18004528a  mov     [rsp+48h+arg_4], 46Eh
0x180045292  jmp     loc_180045356
0x180045297  xor     edi, edi
0x180045299  mov     dword ptr [rbx+24h], 5
0x1800452a0  lock inc dword ptr [rbx+20h]
0x1800452a4  mov     rcx, [rbx+40h]
0x1800452a8  add     rcx, 20h ; ' '; SRWLock
0x1800452ac  call    cs:__imp_AcquireSRWLockShared
0x1800452b2  mov     rcx, [rbx+40h]
0x1800452b6  cmp     qword ptr [rcx+30h], 0FFFFFFFFFFFFFFFFh
0x1800452bb  jnz     short loc_1800452CC
0x1800452bd  mov     esi, 3E3h
0x1800452c2  mov     [rsp+48h+arg_4], 47Fh
0x1800452ca  jmp     short loc_180045321
0x1800452cc  mov     rcx, [rcx+48h]; pio
0x1800452d0  xor     esi, esi
0x1800452d2  call    cs:__imp_StartThreadpoolIo
0x1800452d8  mov     rcx, [rbx+40h]
0x1800452dc  lea     rax, [rbx+1E0h]
0x1800452e3  mov     [rsp+48h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x1800452e8  lea     rdx, [rbx+198h]; lpBuffers
0x1800452ef  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x1800452f4  lea     r8d, [rsi+1]; dwBufferCount
0x1800452f8  xor     r9d, r9d; lpNumberOfBytesSent
0x1800452fb  mov     [rsp+48h+dwFlags], esi; dwFlags
0x1800452ff  mov     rcx, [rcx+30h]; s
0x180045303  call    cs:__imp_WSASend
0x180045309  cmp     eax, 0FFFFFFFFh
0x18004530c  jnz     short loc_180045321
0x18004530e  call    cs:__imp_WSAGetLastError
0x180045314  mov     edi, eax
0x180045316  xor     eax, eax
0x180045318  cmp     edi, 3E5h
0x18004531e  cmovz   edi, eax
0x180045321  mov     rcx, [rbx+40h]
0x180045325  add     rcx, 20h ; ' '; SRWLock
0x180045329  call    cs:__imp_ReleaseSRWLockShared
0x18004532f  mov     rcx, rbx; lpMem
0x180045332  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x180045337  test    edi, edi
0x180045339  jz      short loc_180045356
0x18004533b  mov     rcx, [rbx+40h]
0x18004533f  mov     rcx, [rcx+48h]; pio
0x180045343  call    cs:__imp_CancelThreadpoolIo
0x180045349  xor     r8d, r8d; unsigned int
0x18004534c  mov     edx, edi; unsigned int
0x18004534e  mov     rcx, rbx; lpMem
0x180045351  call    ?DnsFwIoCompletionRoutine@@YAKPEAU_DNS_FORWARD_CONTEXT@@KK@Z; DnsFwIoCompletionRoutine(_DNS_FORWARD_CONTEXT *,ulong,ulong)
0x180045356  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004535d  jz      short loc_18004537F
0x18004535f  mov     ecx, esi
0x180045361  call    WX_WIN32_FROM_HR
0x180045366  mov     r9d, eax
0x180045369  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180045370  mov     edx, 27h ; '''
0x180045375  mov     ecx, 40Bh
0x18004537a  call    WPP_SF_d
0x18004537f  mov     ecx, esi
0x180045381  mov     rbx, [rsp+48h+arg_8]
0x180045386  mov     rsi, [rsp+48h+arg_10]
0x18004538b  add     rsp, 40h
0x18004538f  pop     rdi
0x180045390  jmp     WX_WIN32_FROM_HR
```
