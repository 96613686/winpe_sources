# DnsFwTcpReceive(_DNS_FORWARD_CONTEXT *)

- ea: `0x1800439f8`
- end: `0x180043b98`
- name: `?DnsFwTcpReceive@@YAKPEAU_DNS_FORWARD_CONTEXT@@@Z`
- size: `416`
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
- `0x1800439f8`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043aae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180043aae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180043b28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180043b28`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180043ad4`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180043ad4`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180043b42`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180043b42`
- `WS2_32!WSARecv` at `0x180043b02`
- `WS2_32!WSARecv` at `0x180043b02`
- `WS2_32!__imp_WSAGetLastError` at `0x180043b0d`
- `WS2_32!__imp_WSAGetLastError` at `0x180043b0d`

## pseudocode

```c
__int64 __fastcall DnsFwTcpReceive(struct _DNS_FORWARD_CONTEXT *lpMem)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  unsigned int v4; // ecx
  unsigned int Error; // esi
  __int64 v6; // rcx
  unsigned int v7; // eax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 26, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, lpMem);
  if ( lpMem )
  {
    v3 = *((unsigned int *)lpMem + 94);
    v4 = *((_DWORD *)lpMem + 95);
    *((_DWORD *)lpMem + 9) = 2;
    *((_DWORD *)lpMem + 91) = 0;
    if ( (unsigned int)v3 < v4 )
    {
      Error = 0;
      *((_QWORD *)lpMem + 50) = *((_QWORD *)lpMem + 46) + v3;
      *((_DWORD *)lpMem + 98) = v4 - v3;
      _InterlockedIncrement((volatile signed __int32 *)lpMem + 8);
      AcquireSRWLockShared((PSRWLOCK)(*((_QWORD *)lpMem + 8) + 32LL));
      v6 = *((_QWORD *)lpMem + 8);
      if ( *(_QWORD *)(v6 + 48) == -1 )
      {
        v2 = 995;
      }
      else
      {
        v2 = 0;
        StartThreadpoolIo(*(PTP_IO *)(v6 + 72));
        if ( WSARecv(
               *(_QWORD *)(*((_QWORD *)lpMem + 8) + 48LL),
               (LPWSABUF)((char *)lpMem + 392),
               1u,
               0,
               (LPDWORD)lpMem + 91,
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
      v2 = 111;
    }
  }
  else
  {
    v2 = -2147024809;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v7 = WX_WIN32_FROM_HR(v2);
    WPP_SF_d(1035, 27, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v7);
  }
  return WX_WIN32_FROM_HR(v2);
}

```

## disassembly

```asm
0x1800439f8  mov     [rsp+arg_8], rbx
0x1800439fd  mov     [rsp+arg_10], rsi
0x180043a02  push    rdi
0x180043a03  push    r14
0x180043a05  push    r15
0x180043a07  sub     rsp, 40h
0x180043a0b  mov     rbx, rcx
0x180043a0e  mov     [rsp+58h+arg_4], 0
0x180043a16  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180043a1d  jz      short loc_180043A38
0x180043a1f  mov     edx, 1Ah
0x180043a24  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180043a2b  mov     ecx, 40Bh
0x180043a30  mov     r9, rbx
0x180043a33  call    WPP_SF_q
0x180043a38  test    rbx, rbx
0x180043a3b  jnz     short loc_180043A4F
0x180043a3d  mov     edi, 80070057h
0x180043a42  mov     [rsp+58h+arg_4], 2E6h
0x180043a4a  jmp     loc_180043B55
0x180043a4f  mov     edx, [rbx+178h]
0x180043a55  lea     r14, [rbx+16Ch]
0x180043a5c  mov     ecx, [rbx+17Ch]
0x180043a62  mov     dword ptr [rbx+24h], 2
0x180043a69  mov     dword ptr [r14], 0
0x180043a70  cmp     edx, ecx
0x180043a72  jb      short loc_180043A86
0x180043a74  mov     edi, 6Fh ; 'o'
0x180043a79  mov     [rsp+58h+arg_4], 2F5h
0x180043a81  jmp     loc_180043B55
0x180043a86  lea     r15, [rbx+188h]
0x180043a8d  mov     rax, rdx
0x180043a90  add     rax, [rbx+170h]
0x180043a97  xor     esi, esi
0x180043a99  sub     ecx, edx
0x180043a9b  mov     [r15+8], rax
0x180043a9f  mov     [r15], ecx
0x180043aa2  lock inc dword ptr [rbx+20h]
0x180043aa6  mov     rcx, [rbx+40h]
0x180043aaa  add     rcx, 20h ; ' '; SRWLock
0x180043aae  call    cs:__imp_AcquireSRWLockShared
0x180043ab4  mov     rcx, [rbx+40h]
0x180043ab8  cmp     qword ptr [rcx+30h], 0FFFFFFFFFFFFFFFFh
0x180043abd  jnz     short loc_180043ACE
0x180043abf  mov     edi, 3E3h
0x180043ac4  mov     [rsp+58h+arg_4], 305h
0x180043acc  jmp     short loc_180043B20
0x180043ace  mov     rcx, [rcx+48h]; pio
0x180043ad2  xor     edi, edi
0x180043ad4  call    cs:__imp_StartThreadpoolIo
0x180043ada  mov     rcx, [rbx+40h]
0x180043ade  lea     rax, [rbx+1E0h]
0x180043ae5  mov     [rsp+58h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x180043aea  lea     r8d, [rdi+1]; dwBufferCount
0x180043aee  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x180043af3  xor     r9d, r9d; lpNumberOfBytesRecvd
0x180043af6  mov     rdx, r15; lpBuffers
0x180043af9  mov     [rsp+58h+lpFlags], r14; lpFlags
0x180043afe  mov     rcx, [rcx+30h]; s
0x180043b02  call    cs:__imp_WSARecv
0x180043b08  cmp     eax, 0FFFFFFFFh
0x180043b0b  jnz     short loc_180043B20
0x180043b0d  call    cs:__imp_WSAGetLastError
0x180043b13  mov     esi, eax
0x180043b15  xor     eax, eax
0x180043b17  cmp     esi, 3E5h
0x180043b1d  cmovz   esi, eax
0x180043b20  mov     rcx, [rbx+40h]
0x180043b24  add     rcx, 20h ; ' '; SRWLock
0x180043b28  call    cs:__imp_ReleaseSRWLockShared
0x180043b2e  mov     rcx, rbx; lpMem
0x180043b31  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x180043b36  test    esi, esi
0x180043b38  jz      short loc_180043B55
0x180043b3a  mov     rcx, [rbx+40h]
0x180043b3e  mov     rcx, [rcx+48h]; pio
0x180043b42  call    cs:__imp_CancelThreadpoolIo
0x180043b48  xor     r8d, r8d; unsigned int
0x180043b4b  mov     edx, esi; unsigned int
0x180043b4d  mov     rcx, rbx; lpMem
0x180043b50  call    ?DnsFwIoCompletionRoutine@@YAKPEAU_DNS_FORWARD_CONTEXT@@KK@Z; DnsFwIoCompletionRoutine(_DNS_FORWARD_CONTEXT *,ulong,ulong)
0x180043b55  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180043b5c  jz      short loc_180043B7E
0x180043b5e  mov     ecx, edi
0x180043b60  call    WX_WIN32_FROM_HR
0x180043b65  mov     r9d, eax
0x180043b68  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180043b6f  mov     edx, 1Bh
0x180043b74  mov     ecx, 40Bh
0x180043b79  call    WPP_SF_d
0x180043b7e  mov     ecx, edi
0x180043b80  mov     rbx, [rsp+58h+arg_8]
0x180043b85  mov     rsi, [rsp+58h+arg_10]
0x180043b8a  add     rsp, 40h
0x180043b8e  pop     r15
0x180043b90  pop     r14
0x180043b92  pop     rdi
0x180043b93  jmp     WX_WIN32_FROM_HR
```
