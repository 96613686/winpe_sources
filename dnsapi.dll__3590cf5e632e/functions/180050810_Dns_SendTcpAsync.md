# Dns_SendTcpAsync

- ea: `0x180050810`
- end: `0x180050a82`
- name: `Dns_SendTcpAsync`
- size: `626`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18004f928`
- `0x18004fbd0`
- `0x180050508`

## callees

- `0x180050810`
- `0x180050a88`
- `0x180050ac8`
- `0x180051718`
- `0x1800dc9e0`
- `0x1800dfdc8`
- `0x1800e0f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005082b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050a37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005082b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050a37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050a71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050a71`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180050920`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180050920`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180050a50`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180050a50`
- `WS2_32!WSASend` at `0x18005096b`
- `WS2_32!WSASend` at `0x18005096b`
- `WS2_32!__imp_WSAGetLastError` at `0x180050980`
- `WS2_32!__imp_WSAGetLastError` at `0x180050980`

## pseudocode

```c
__int64 __fastcall Dns_SendTcpAsync(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // r14d
  unsigned int v4; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // rbp
  unsigned int v11; // eax
  struct _TP_IO *v12; // rcx
  int Error; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 65888);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 65888));
  if ( *(_DWORD *)(a1 + 164) || (unsigned __int64)(*(_QWORD *)(a1 + 56) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = 10038;
  }
  else if ( !*(_DWORD *)(a1 + 160) || (v6 = *(_QWORD **)(a1 + 16), v6 == (_QWORD *)(a1 + 16)) )
  {
    v4 = 997;
  }
  else
  {
    *(_DWORD *)(a1 + 160) = 0;
    v7 = *v6;
    if ( *(_QWORD **)(*v6 + 8LL) != v6
      || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6)
      || (*v8 = v7, *(_QWORD *)(v7 + 8) = v8, v9 = *(_QWORD **)(a1 + 40), *v9 != a1 + 32) )
    {
      __fastfail(3u);
    }
    *v6 = a1 + 32;
    v10 = (__int64)(v6 - 12);
    v6[1] = v9;
    *v9 = v6;
    *(_QWORD *)(a1 + 40) = v6;
    TcpConnectionCleanupSendBuffer(a1);
    v11 = CopyMessageData(a1, *(_QWORD *)(v10 + 88));
    v4 = v11;
    if ( v11 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_d(1035, 80, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v11);
    }
    else
    {
      v12 = *(struct _TP_IO **)(a1 + 64);
      v3 = 1;
      *(_DWORD *)(a1 + 180) = 1;
      StartThreadpoolIo(v12);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 65884));
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_qq(1035, 81, (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v10, a1);
      if ( WSASend(*(_QWORD *)(a1 + 56), (LPWSABUF)(a1 + 136), 1u, 0, 0, (LPWSAOVERLAPPED)(a1 + 104), 0) == -1 )
      {
        Error = WSAGetLastError();
        v4 = Error;
        if ( Error )
        {
          if ( Error != 997 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_qqD(1035, 82, (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, a1, v10);
        }
      }
    }
  }
  LeaveCriticalSection(v1);
  if ( v3 && v4 != 997 )
  {
    if ( v4 )
    {
      EnterCriticalSection(v1);
      if ( *(_DWORD *)(a1 + 180) )
      {
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 64));
        *(_DWORD *)(a1 + 180) = 0;
        DeRefTcpConnection(a1);
      }
      LeaveCriticalSection(v1);
    }
    else
    {
      return 997;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180050810  push    rbx
0x180050812  push    rbp
0x180050813  push    rsi
0x180050814  push    rdi
0x180050815  push    r14
0x180050817  sub     rsp, 40h
0x18005081b  lea     rsi, [rcx+10160h]
0x180050822  mov     rbx, rcx
0x180050825  mov     rcx, rsi; lpCriticalSection
0x180050828  xor     r14d, r14d
0x18005082b  call    cs:__imp_EnterCriticalSection
0x180050832  nop     dword ptr [rax+rax+00h]
0x180050837  cmp     [rbx+0A4h], r14d
0x18005083e  jnz     short loc_18005084D
0x180050840  mov     rax, [rbx+38h]
0x180050844  dec     rax
0x180050847  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005084b  jbe     short loc_18005088B
0x18005084d  mov     edi, 2736h
0x180050852  mov     rcx, rsi; lpCriticalSection
0x180050855  call    cs:__imp_LeaveCriticalSection
0x18005085c  nop     dword ptr [rax+rax+00h]
0x180050861  test    r14d, r14d
0x180050864  jz      short loc_18005086E
0x180050866  cmp     edi, 3E5h
0x18005086c  jnz     short loc_18005087C
0x18005086e  mov     eax, edi
0x180050870  add     rsp, 40h
0x180050874  pop     r14
0x180050876  pop     rdi
0x180050877  pop     rsi
0x180050878  pop     rbp
0x180050879  pop     rbx
0x18005087a  retn
0x18005087c  test    edi, edi
0x18005087e  jnz     loc_180050A34
0x180050884  mov     edi, 3E5h
0x180050889  jmp     short loc_18005086E
0x18005088b  cmp     [rbx+0A0h], r14d
0x180050892  jz      loc_1800509D5
0x180050898  lea     rax, [rbx+10h]
0x18005089c  mov     rcx, [rax]
0x18005089f  cmp     rcx, rax
0x1800508a2  jz      loc_1800509D5
0x1800508a8  mov     [rbx+0A0h], r14d
0x1800508af  mov     rax, [rcx]
0x1800508b2  cmp     [rax+8], rcx
0x1800508b6  jnz     loc_1800509DF
0x1800508bc  mov     rdx, [rcx+8]
0x1800508c0  cmp     [rdx], rcx
0x1800508c3  jnz     loc_1800509DF
0x1800508c9  mov     [rdx], rax
0x1800508cc  mov     [rax+8], rdx
0x1800508d0  lea     rax, [rbx+20h]
0x1800508d4  mov     rdx, [rax+8]
0x1800508d8  cmp     [rdx], rax
0x1800508db  jnz     loc_1800509DF
0x1800508e1  mov     [rcx], rax
0x1800508e4  lea     rbp, [rcx-60h]
0x1800508e8  mov     [rcx+8], rdx
0x1800508ec  mov     [rdx], rcx
0x1800508ef  mov     [rax+8], rcx
0x1800508f3  mov     rcx, rbx
0x1800508f6  call    TcpConnectionCleanupSendBuffer
0x1800508fb  mov     rdx, [rbp+58h]
0x1800508ff  mov     rcx, rbx
0x180050902  call    CopyMessageData
0x180050907  mov     edi, eax
0x180050909  test    eax, eax
0x18005090b  jnz     loc_180050A09
0x180050911  mov     rcx, [rbx+40h]; pio
0x180050915  lea     r14d, [rax+1]
0x180050919  mov     [rbx+0B4h], r14d
0x180050920  call    cs:__imp_StartThreadpoolIo
0x180050927  nop     dword ptr [rax+rax+00h]
0x18005092c  lock inc dword ptr [rbx+1015Ch]
0x180050933  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005093a  jnz     loc_1800509E6
0x180050940  mov     rcx, [rbx+38h]; s
0x180050944  lea     rax, [rbx+68h]
0x180050948  mov     [rsp+68h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180050951  lea     rdx, [rbx+88h]; lpBuffers
0x180050958  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18005095d  xor     r9d, r9d; lpNumberOfBytesSent
0x180050960  mov     r8d, r14d; dwBufferCount
0x180050963  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18005096b  call    cs:__imp_WSASend
0x180050972  nop     dword ptr [rax+rax+00h]
0x180050977  cmp     eax, 0FFFFFFFFh
0x18005097a  jnz     loc_180050852
0x180050980  call    cs:__imp_WSAGetLastError
0x180050987  nop     dword ptr [rax+rax+00h]
0x18005098c  mov     edi, eax
0x18005098e  test    eax, eax
0x180050990  jz      loc_180050852
0x180050996  cmp     eax, 3E5h
0x18005099b  jz      loc_180050852
0x1800509a1  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800509a8  jz      loc_180050852
0x1800509ae  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x1800509b2  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x1800509b9  mov     edx, 52h ; 'R'
0x1800509be  mov     qword ptr [rsp+68h+dwFlags], rbp
0x1800509c3  mov     ecx, 40Bh
0x1800509c8  mov     r9, rbx
0x1800509cb  call    WPP_SF_qqD
0x1800509d0  jmp     loc_180050852
0x1800509d5  mov     edi, 3E5h
0x1800509da  jmp     loc_180050852
0x1800509df  mov     ecx, 3
0x1800509e4  int     29h; Win8: RtlFailFast(ecx)
0x1800509e6  mov     edx, 51h ; 'Q'
0x1800509eb  mov     qword ptr [rsp+68h+dwFlags], rbx
0x1800509f0  mov     ecx, 40Bh
0x1800509f5  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x1800509fc  mov     r9, rbp
0x1800509ff  call    WPP_SF_qq
0x180050a04  jmp     loc_180050940
0x180050a09  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180050a10  jz      loc_180050852
0x180050a16  mov     edx, 50h ; 'P'
0x180050a1b  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180050a22  mov     ecx, 40Bh
0x180050a27  mov     r9d, eax
0x180050a2a  call    WPP_SF_d
0x180050a2f  jmp     loc_180050852
0x180050a34  mov     rcx, rsi; lpCriticalSection
0x180050a37  call    cs:__imp_EnterCriticalSection
0x180050a3e  nop     dword ptr [rax+rax+00h]
0x180050a43  cmp     dword ptr [rbx+0B4h], 0
0x180050a4a  jz      short loc_180050A6E
0x180050a4c  mov     rcx, [rbx+40h]; pio
0x180050a50  call    cs:__imp_CancelThreadpoolIo
0x180050a57  nop     dword ptr [rax+rax+00h]
0x180050a5c  mov     rcx, rbx
0x180050a5f  mov     dword ptr [rbx+0B4h], 0
0x180050a69  call    DeRefTcpConnection
0x180050a6e  mov     rcx, rsi; lpCriticalSection
0x180050a71  call    cs:__imp_LeaveCriticalSection
0x180050a78  nop     dword ptr [rax+rax+00h]
0x180050a7d  jmp     loc_18005086E
```
