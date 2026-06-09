# Dns_RecvTcpAsync

- ea: `0x1800393a8`
- end: `0x180039516`
- name: `Dns_RecvTcpAsync`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180050508`
- `0x1800517c8`

## callees

- `0x1800393a8`
- `0x1800396b0`
- `0x18008b5f0`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039403`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003942d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800394cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003942d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800394cb`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180039463`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180039463`
- `WS2_32!WSARecv` at `0x18003949e`
- `WS2_32!WSARecv` at `0x18003949e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800394af`
- `WS2_32!__imp_WSAGetLastError` at `0x1800394af`

## pseudocode

```c
__int64 __fastcall Dns_RecvTcpAsync(__int64 a1)
{
  struct _WSABUF *v2; // r14
  __int64 v3; // rcx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  unsigned int v5; // ebx
  struct _TP_IO *v7; // rcx
  unsigned int v8; // edi
  int Error; // eax
  DWORD Flags; // [rsp+40h] [rbp-38h] BYREF
  DWORD NumberOfBytesRecvd; // [rsp+44h] [rbp-34h] BYREF

  NumberOfBytesRecvd = 0;
  v2 = (struct _WSABUF *)(a1 + 320);
  Flags = 0;
  v3 = *(unsigned int *)(a1 + 336);
  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 65888);
  v2->buf = (CHAR *)(v3 + a1 + 340);
  v2->len = 65537 - v3;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 65888));
  if ( *(_DWORD *)(a1 + 164) || (unsigned __int64)(*(_QWORD *)(a1 + 56) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v5 = 10038;
    LeaveCriticalSection(v4);
  }
  else
  {
    v7 = *(struct _TP_IO **)(a1 + 64);
    v8 = 0;
    *(_DWORD *)(a1 + 176) = 1;
    StartThreadpoolIo(v7);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 65884));
    if ( WSARecv(*(_QWORD *)(a1 + 56), v2, 1u, &NumberOfBytesRecvd, &Flags, (LPWSAOVERLAPPED)(a1 + 72), 0) == -1 )
    {
      Error = WSAGetLastError();
      v8 = Error;
      if ( Error )
      {
        if ( Error != 997 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_qD(1035, 216, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, a1, Error);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 65888));
    return (unsigned int)Socket_ProcessReturnStatus2(a1, 1, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x1800393a8  push    rbx
0x1800393aa  push    rsi
0x1800393ab  push    rdi
0x1800393ac  push    r14
0x1800393ae  sub     rsp, 58h
0x1800393b2  mov     rax, cs:__security_cookie
0x1800393b9  xor     rax, rsp
0x1800393bc  mov     [rsp+78h+var_30], rax
0x1800393c1  mov     rbx, rcx
0x1800393c4  mov     [rsp+78h+NumberOfBytesRecvd], 0
0x1800393cc  lea     r14, [rcx+140h]
0x1800393d3  mov     [rsp+78h+Flags], 0
0x1800393db  mov     ecx, [rcx+150h]
0x1800393e1  lea     rax, [rbx+154h]
0x1800393e8  add     rax, rcx
0x1800393eb  lea     rsi, [rbx+10160h]
0x1800393f2  mov     [r14+8], rax
0x1800393f6  mov     eax, 10001h
0x1800393fb  sub     eax, ecx
0x1800393fd  mov     rcx, rsi; lpCriticalSection
0x180039400  mov     [r14], eax
0x180039403  call    cs:__imp_EnterCriticalSection
0x18003940a  nop     dword ptr [rax+rax+00h]
0x18003940f  cmp     dword ptr [rbx+0A4h], 0
0x180039416  jnz     short loc_180039425
0x180039418  mov     rax, [rbx+38h]
0x18003941c  dec     rax
0x18003941f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180039423  jbe     short loc_180039453
0x180039425  mov     ebx, 2736h
0x18003942a  mov     rcx, rsi; lpCriticalSection
0x18003942d  call    cs:__imp_LeaveCriticalSection
0x180039434  nop     dword ptr [rax+rax+00h]
0x180039439  mov     eax, ebx
0x18003943b  mov     rcx, [rsp+78h+var_30]
0x180039440  xor     rcx, rsp; StackCookie
0x180039443  call    __security_check_cookie
0x180039448  add     rsp, 58h
0x18003944c  pop     r14
0x18003944e  pop     rdi
0x18003944f  pop     rsi
0x180039450  pop     rbx
0x180039451  retn
0x180039453  mov     rcx, [rbx+40h]; pio
0x180039457  xor     edi, edi
0x180039459  mov     dword ptr [rbx+0B0h], 1
0x180039463  call    cs:__imp_StartThreadpoolIo
0x18003946a  nop     dword ptr [rax+rax+00h]
0x18003946f  lock inc dword ptr [rbx+1015Ch]
0x180039476  mov     rcx, [rbx+38h]; s
0x18003947a  lea     rax, [rbx+48h]
0x18003947e  mov     [rsp+78h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180039483  lea     r9, [rsp+78h+NumberOfBytesRecvd]; lpNumberOfBytesRecvd
0x180039488  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18003948d  lea     r8d, [rdi+1]; dwBufferCount
0x180039491  lea     rax, [rsp+78h+Flags]
0x180039496  mov     rdx, r14; lpBuffers
0x180039499  mov     [rsp+78h+lpFlags], rax; lpFlags
0x18003949e  call    cs:__imp_WSARecv
0x1800394a5  nop     dword ptr [rax+rax+00h]
0x1800394aa  cmp     eax, 0FFFFFFFFh
0x1800394ad  jnz     short loc_1800394C8
0x1800394af  call    cs:__imp_WSAGetLastError
0x1800394b6  nop     dword ptr [rax+rax+00h]
0x1800394bb  mov     edi, eax
0x1800394bd  test    eax, eax
0x1800394bf  jz      short loc_1800394C8
0x1800394c1  cmp     eax, 3E5h
0x1800394c6  jnz     short loc_1800394EE
0x1800394c8  mov     rcx, rsi; lpCriticalSection
0x1800394cb  call    cs:__imp_LeaveCriticalSection
0x1800394d2  nop     dword ptr [rax+rax+00h]
0x1800394d7  mov     r8d, edi
0x1800394da  mov     edx, 1
0x1800394df  mov     rcx, rbx
0x1800394e2  call    Socket_ProcessReturnStatus2
0x1800394e7  mov     ebx, eax
0x1800394e9  jmp     loc_180039439
0x1800394ee  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800394f5  jz      short loc_1800394C8
0x1800394f7  mov     edx, 0D8h
0x1800394fc  mov     dword ptr [rsp+78h+lpFlags], eax
0x180039500  mov     ecx, 40Bh
0x180039505  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18003950c  mov     r9, rbx
0x18003950f  call    WPP_SF_qD
0x180039514  jmp     short loc_1800394C8
```
