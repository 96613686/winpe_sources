# DnsFwUdpSend(_DNS_FORWARD_CONTEXT *)

- ea: `0x18004539c`
- end: `0x180045501`
- name: `?DnsFwUdpSend@@YAKPEAU_DNS_FORWARD_CONTEXT@@@Z`
- size: `357`
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
- `0x18004539c`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180045404`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180045404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045495`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045495`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18004542a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18004542a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800454af`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800454af`
- `WS2_32!WSASendTo` at `0x18004546f`
- `WS2_32!WSASendTo` at `0x18004546f`
- `WS2_32!__imp_WSAGetLastError` at `0x18004547a`
- `WS2_32!__imp_WSAGetLastError` at `0x18004547a`

## pseudocode

```c
__int64 __fastcall DnsFwUdpSend(struct _DNS_FORWARD_CONTEXT *lpMem)
{
  unsigned int v2; // esi
  unsigned int Error; // edi
  __int64 v4; // rcx
  unsigned int v5; // eax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 36, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, lpMem);
  if ( lpMem )
  {
    Error = 0;
    *((_DWORD *)lpMem + 9) = 5;
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 8);
    AcquireSRWLockShared((PSRWLOCK)(*((_QWORD *)lpMem + 7) + 32LL));
    v4 = *((_QWORD *)lpMem + 7);
    if ( *(_QWORD *)(v4 + 48) == -1 )
    {
      v2 = 995;
    }
    else
    {
      v2 = 0;
      StartThreadpoolIo(*(PTP_IO *)(v4 + 72));
      if ( WSASendTo(
             *(_QWORD *)(*((_QWORD *)lpMem + 7) + 48LL),
             (LPWSABUF)((char *)lpMem + 408),
             1u,
             0,
             0,
             (const struct sockaddr *)((char *)lpMem + 216),
             128,
             (LPWSAOVERLAPPED)lpMem + 15,
             0) == -1 )
      {
        Error = WSAGetLastError();
        if ( Error == 997 )
          Error = 0;
      }
    }
    ReleaseSRWLockShared((PSRWLOCK)(*((_QWORD *)lpMem + 7) + 32LL));
    DnsFwDerefContext(lpMem);
    if ( Error )
    {
      CancelThreadpoolIo(*(PTP_IO *)(*((_QWORD *)lpMem + 7) + 72LL));
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
    WPP_SF_d(1035, 37, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v5);
  }
  return WX_WIN32_FROM_HR(v2);
}

```

## disassembly

```asm
0x18004539c  mov     [rsp+arg_8], rbx
0x1800453a1  mov     [rsp+arg_10], rsi
0x1800453a6  push    rdi
0x1800453a7  sub     rsp, 50h
0x1800453ab  mov     rbx, rcx
0x1800453ae  mov     [rsp+58h+arg_4], 0
0x1800453b6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800453bd  jz      short loc_1800453D8
0x1800453bf  mov     edx, 24h ; '$'
0x1800453c4  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800453cb  mov     ecx, 40Bh
0x1800453d0  mov     r9, rbx
0x1800453d3  call    WPP_SF_q
0x1800453d8  test    rbx, rbx
0x1800453db  jnz     short loc_1800453EF
0x1800453dd  mov     esi, 80070057h
0x1800453e2  mov     [rsp+58h+arg_4], 420h
0x1800453ea  jmp     loc_1800454C2
0x1800453ef  xor     edi, edi
0x1800453f1  mov     dword ptr [rbx+24h], 5
0x1800453f8  lock inc dword ptr [rbx+20h]
0x1800453fc  mov     rcx, [rbx+38h]
0x180045400  add     rcx, 20h ; ' '; SRWLock
0x180045404  call    cs:__imp_AcquireSRWLockShared
0x18004540a  mov     rcx, [rbx+38h]
0x18004540e  cmp     qword ptr [rcx+30h], 0FFFFFFFFFFFFFFFFh
0x180045413  jnz     short loc_180045424
0x180045415  mov     esi, 3E3h
0x18004541a  mov     [rsp+58h+arg_4], 431h
0x180045422  jmp     short loc_18004548D
0x180045424  mov     rcx, [rcx+48h]; pio
0x180045428  xor     esi, esi
0x18004542a  call    cs:__imp_StartThreadpoolIo
0x180045430  mov     rcx, [rbx+38h]
0x180045434  lea     r8, [rbx+0D8h]
0x18004543b  mov     [rsp+58h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x180045440  lea     rax, [rbx+1E0h]
0x180045447  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18004544c  lea     rdx, [rbx+198h]; lpBuffers
0x180045453  mov     [rsp+58h+iTolen], 80h; iTolen
0x18004545b  xor     r9d, r9d; lpNumberOfBytesSent
0x18004545e  mov     rcx, [rcx+30h]; s
0x180045462  mov     [rsp+58h+lpTo], r8; lpTo
0x180045467  lea     r8d, [rsi+1]; dwBufferCount
0x18004546b  mov     [rsp+58h+dwFlags], esi; dwFlags
0x18004546f  call    cs:__imp_WSASendTo
0x180045475  cmp     eax, 0FFFFFFFFh
0x180045478  jnz     short loc_18004548D
0x18004547a  call    cs:__imp_WSAGetLastError
0x180045480  mov     edi, eax
0x180045482  xor     eax, eax
0x180045484  cmp     edi, 3E5h
0x18004548a  cmovz   edi, eax
0x18004548d  mov     rcx, [rbx+38h]
0x180045491  add     rcx, 20h ; ' '; SRWLock
0x180045495  call    cs:__imp_ReleaseSRWLockShared
0x18004549b  mov     rcx, rbx; lpMem
0x18004549e  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x1800454a3  test    edi, edi
0x1800454a5  jz      short loc_1800454C2
0x1800454a7  mov     rcx, [rbx+38h]
0x1800454ab  mov     rcx, [rcx+48h]; pio
0x1800454af  call    cs:__imp_CancelThreadpoolIo
0x1800454b5  xor     r8d, r8d; unsigned int
0x1800454b8  mov     edx, edi; unsigned int
0x1800454ba  mov     rcx, rbx; lpMem
0x1800454bd  call    ?DnsFwIoCompletionRoutine@@YAKPEAU_DNS_FORWARD_CONTEXT@@KK@Z; DnsFwIoCompletionRoutine(_DNS_FORWARD_CONTEXT *,ulong,ulong)
0x1800454c2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800454c9  jz      short loc_1800454EB
0x1800454cb  mov     ecx, esi
0x1800454cd  call    WX_WIN32_FROM_HR
0x1800454d2  mov     r9d, eax
0x1800454d5  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800454dc  mov     edx, 25h ; '%'
0x1800454e1  mov     ecx, 40Bh
0x1800454e6  call    WPP_SF_d
0x1800454eb  mov     ecx, esi
0x1800454ed  mov     rbx, [rsp+58h+arg_8]
0x1800454f2  mov     rsi, [rsp+58h+arg_10]
0x1800454f7  add     rsp, 50h
0x1800454fb  pop     rdi
0x1800454fc  jmp     WX_WIN32_FROM_HR
```
