# TcpConnectionConnect

- ea: `0x180039798`
- end: `0x180039be9`
- name: `TcpConnectionConnect`
- size: `1105`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x18004fbd0`

## callees

- `0x180039328`
- `0x1800395e8`
- `0x1800396b0`
- `0x180039798`
- `0x180039c78`
- `0x180039e64`
- `0x18003a240`
- `0x18003b5d4`
- `0x18003eef4`
- `0x18007b280`
- `0x18008b5f0`
- `0x1800cfadc`
- `0x1800d21c8`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003984b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003984b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b67`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18003999d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18003999d`
- `WS2_32!WSAIoctl` at `0x180039958`
- `WS2_32!WSAIoctl` at `0x180039a16`
- `WS2_32!WSAIoctl` at `0x180039958`
- `WS2_32!WSAIoctl` at `0x180039a16`
- `WS2_32!__imp_WSAGetLastError` at `0x180039b42`
- `WS2_32!__imp_WSAGetLastError` at `0x180039b42`

## pseudocode

```c
__int64 __fastcall TcpConnectionConnect(unsigned __int16 *pv, __int64 a2)
{
  __int64 v4; // r14
  unsigned int EmptyDnsSocket; // eax
  unsigned int Error; // ebx
  SOCKET v7; // rax
  SOCKET v8; // rsi
  char v9; // al
  int v10; // ecx
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v14; // eax
  SOCKET v15; // rcx
  unsigned int v16; // ebx
  __int64 v17; // r8
  __int64 v18; // rcx
  DWORD v19; // eax
  int v20; // edx
  int v21; // ecx
  int v22; // r8d
  unsigned int v23; // eax
  DWORD LastError; // eax
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  unsigned int (__fastcall *vOutBuffer)(__int64, unsigned __int16 *, __int64, _QWORD, _DWORD, DWORD *, unsigned __int16 *); // [rsp+58h] [rbp-28h] BYREF
  DWORD cbBytesReturned; // [rsp+60h] [rbp-20h] BYREF
  int vInBuffer; // [rsp+64h] [rbp-1Ch] BYREF
  _DWORD v29[4]; // [rsp+68h] [rbp-18h] BYREF

  v29[0] = 631375801;
  cbBytesReturned = 0;
  v29[1] = 1180753395;
  v4 = 0;
  v29[2] = -445191794;
  v29[3] = 1040610444;
  vOutBuffer = 0;
  vInBuffer = 0;
  v25 = 0;
  if ( !g_DnsIsCache || (EmptyDnsSocket = DnsGetEmptyDnsSocket(1, &v25), v4 = v25, (Error = EmptyDnsSocket) == 0) )
  {
    v7 = Socket_CreateEx(pv[94], 1, 1u, 0);
    v8 = v7;
    if ( ((v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v11 = Socket_SetInterfaceIndexSocketOption(v7);
      Error = v11;
      if ( v11 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 24, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v11);
      }
      else
      {
        if ( !a2 )
          goto LABEL_18;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_(1035, 25, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids);
        v23 = AddSecureSocketOptions(v8, a2);
        if ( v23 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_d(1035, 26, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v23);
          Error = 10057;
        }
        else
        {
LABEL_18:
          LOWORD(vInBuffer) = 500;
          BYTE2(vInBuffer) = 3;
          if ( WSAIoctl(v8, 0x98000011, &vInBuffer, 4u, 0, 0, &cbBytesReturned, 0, 0) != -1 )
          {
            *((_QWORD *)pv + 6) = v4;
            v4 = 0;
            v25 = 0;
            *((_QWORD *)pv + 7) = v8;
            v14 = PrepareTcpConnectionIo(pv);
            Error = v14;
            if ( v14 )
            {
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_d(1035, 27, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, v14);
            }
            else
            {
              _InterlockedIncrement((volatile signed __int32 *)pv + 16471);
              StartThreadpoolIo(*((PTP_IO *)pv + 8));
              v15 = *((_QWORD *)pv + 7);
              *((_DWORD *)pv + 44) = 1;
              if ( ((v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
              {
                cbBytesReturned = 0;
                v16 = WSAIoctl(v15, 0xC8000006, v29, 0x10u, &vOutBuffer, 8u, &cbBytesReturned, 0, 0);
                if ( v16 == -1 )
                {
                  LastError = GetLastError();
                  v16 = LastError;
                  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                    WPP_SF_d(1035, 28, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, LastError);
                }
                else
                {
                  v17 = *((unsigned int *)pv + 55);
                  v18 = *((_QWORD *)pv + 7);
                  cbBytesReturned = 0;
                  if ( !vOutBuffer(v18, pv + 94, v17, 0, 0, &cbBytesReturned, pv + 36) )
                  {
                    v19 = GetLastError();
                    v16 = v19;
                    if ( v19 )
                    {
                      if ( v19 != 997 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
                        WPP_SF__SOCKADDR_dqD(v21, v20, v22, (_DWORD)pv + 188, *((_DWORD *)pv + 55), (__int64)pv, v19);
                    }
                  }
                }
              }
              else
              {
                v16 = 1460;
              }
              Error = Socket_ProcessReturnStatus2(pv, 1, v16);
            }
            goto LABEL_7;
          }
          Error = WSAGetLastError();
        }
      }
    }
    else
    {
      v9 = GetLastError();
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF__SOCKADDR_d(v10, 23, (unsigned int)WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, (_DWORD)pv + 188, v9);
      Error = 10038;
      if ( v8 == -1 || !v8 )
        goto LABEL_7;
    }
    v12 = v4;
    v25 = 0;
    v4 = 0;
    if ( v12 )
    {
      *(_QWORD *)(v12 + 24) = v8;
      DnsCloseDnsSocketsAsync();
      goto LABEL_14;
    }
    Socket_CloseEx(v8);
  }
LABEL_7:
  if ( v4 )
    DnsAddEmptyDnsSocket(&v25);
LABEL_14:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 30, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, Error);
  return Error;
}

```

## disassembly

```asm
0x180039798  mov     [rsp-38h+arg_10], rbx
0x18003979d  push    rbp
0x18003979e  push    rsi
0x18003979f  push    rdi
0x1800397a0  push    r12
0x1800397a2  push    r13
0x1800397a4  push    r14
0x1800397a6  push    r15
0x1800397a8  mov     rbp, rsp
0x1800397ab  sub     rsp, 80h
0x1800397b2  mov     rax, cs:__security_cookie
0x1800397b9  xor     rax, rsp
0x1800397bc  mov     [rbp+var_8], rax
0x1800397c0  xor     r13d, r13d
0x1800397c3  mov     [rbp+var_18], 25A207B9h
0x1800397ca  cmp     cs:g_DnsIsCache, r13d
0x1800397d1  mov     r12, rdx
0x1800397d4  mov     rdi, rcx
0x1800397d7  mov     [rbp+cbBytesReturned], r13d
0x1800397db  mov     [rbp+var_14], 4660DDF3h
0x1800397e2  mov     r14d, r13d
0x1800397e5  lea     esi, [r13+1]
0x1800397e9  mov     [rbp+var_10], 0E576E98Eh
0x1800397f0  mov     [rbp+var_C], 3E06748Ch
0x1800397f7  mov     [rbp+vOutBuffer], r13
0x1800397fb  mov     [rbp+vInBuffer], r13d
0x1800397ff  mov     [rbp+var_30], r13
0x180039803  jz      short loc_18003981A
0x180039805  lea     rdx, [rbp+var_30]
0x180039809  mov     ecx, esi
0x18003980b  call    DnsGetEmptyDnsSocket
0x180039810  mov     r14, [rbp+var_30]
0x180039814  mov     ebx, eax
0x180039816  test    eax, eax
0x180039818  jnz     short loc_180039887
0x18003981a  lea     r15, [rdi+0BCh]
0x180039821  mov     [rsp+80h+cbOutBuffer], r13d; int
0x180039826  movzx   ecx, word ptr [r15]; af
0x18003982a  xor     r9d, r9d
0x18003982d  xor     r8d, r8d
0x180039830  mov     dword ptr [rsp+80h+lpvOutBuffer], esi; DWORD
0x180039834  mov     edx, esi; type
0x180039836  call    Socket_CreateEx
0x18003983b  mov     rsi, rax
0x18003983e  lea     rcx, [rax+1]
0x180039842  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180039849  jnz     short loc_180039897
0x18003984b  call    cs:__imp_GetLastError
0x180039852  nop     dword ptr [rax+rax+00h]
0x180039857  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18003985e  jz      short loc_180039878
0x180039860  mov     edx, 17h
0x180039865  mov     dword ptr [rsp+80h+lpvOutBuffer], eax
0x180039869  mov     r9, r15
0x18003986c  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039873  call    WPP_SF__SOCKADDR_d
0x180039878  mov     ebx, 2736h
0x18003987d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180039881  jnz     loc_180039AB8
0x180039887  test    r14, r14
0x18003988a  jz      short loc_1800398DC
0x18003988c  lea     rcx, [rbp+var_30]
0x180039890  call    DnsAddEmptyDnsSocket
0x180039895  jmp     short loc_1800398DC
0x180039897  movzx   edx, word ptr [r15]
0x18003989b  xor     r8d, r8d
0x18003989e  mov     r9d, [rdi+10188h]
0x1800398a5  mov     rcx, rsi; s
0x1800398a8  call    Socket_SetInterfaceIndexSocketOption
0x1800398ad  mov     ebx, eax
0x1800398af  test    eax, eax
0x1800398b1  jz      short loc_180039913
0x1800398b3  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800398ba  jnz     loc_180039AC6
0x1800398c0  mov     rcx, r14
0x1800398c3  mov     [rbp+var_30], r13
0x1800398c7  mov     r14, r13
0x1800398ca  test    rcx, rcx
0x1800398cd  jz      loc_180039B55
0x1800398d3  mov     [rcx+18h], rsi
0x1800398d7  call    DnsCloseDnsSocketsAsync
0x1800398dc  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800398e3  jnz     loc_180039BCB
0x1800398e9  mov     eax, ebx
0x1800398eb  mov     rcx, [rbp+var_8]
0x1800398ef  xor     rcx, rsp; StackCookie
0x1800398f2  call    __security_check_cookie
0x1800398f7  mov     rbx, [rsp+80h+arg_10]
0x1800398ff  add     rsp, 80h
0x180039906  pop     r15
0x180039908  pop     r14
0x18003990a  pop     r13
0x18003990c  pop     r12
0x18003990e  pop     rdi
0x18003990f  pop     rsi
0x180039910  pop     rbp
0x180039911  retn
0x180039913  test    r12, r12
0x180039916  jnz     loc_180039AE4
0x18003991c  mov     [rsp+80h+lpCompletionRoutine], r13; lpCompletionRoutine
0x180039921  lea     r8, [rbp+vInBuffer]; lpvInBuffer
0x180039925  mov     [rsp+80h+lpOverlapped], r13; lpOverlapped
0x18003992a  mov     eax, 1F4h
0x18003992f  mov     word ptr [rbp+vInBuffer], ax
0x180039933  mov     r9d, 4; cbInBuffer
0x180039939  lea     rax, [rbp+cbBytesReturned]
0x18003993d  mov     byte ptr [rbp+vInBuffer+2], 3
0x180039941  mov     [rsp+80h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180039946  mov     edx, 98000011h; dwIoControlCode
0x18003994b  mov     [rsp+80h+cbOutBuffer], r13d; cbOutBuffer
0x180039950  mov     rcx, rsi; s
0x180039953  mov     [rsp+80h+lpvOutBuffer], r13; lpvOutBuffer
0x180039958  call    cs:__imp_WSAIoctl
0x18003995f  nop     dword ptr [rax+rax+00h]
0x180039964  or      r12d, 0FFFFFFFFh
0x180039968  cmp     eax, r12d
0x18003996b  jz      loc_180039B42
0x180039971  mov     [rdi+30h], r14
0x180039975  mov     rcx, rdi; pv
0x180039978  mov     r14, r13
0x18003997b  mov     [rbp+var_30], r13
0x18003997f  mov     [rdi+38h], rsi
0x180039983  call    PrepareTcpConnectionIo
0x180039988  mov     ebx, eax
0x18003998a  test    eax, eax
0x18003998c  jnz     loc_180039BA0
0x180039992  lock inc dword ptr [rdi+1015Ch]
0x180039999  mov     rcx, [rdi+40h]; pio
0x18003999d  call    cs:__imp_StartThreadpoolIo
0x1800399a4  nop     dword ptr [rax+rax+00h]
0x1800399a9  mov     rcx, [rdi+38h]; s
0x1800399ad  mov     dword ptr [rdi+0B0h], 1
0x1800399b7  lea     rax, [rcx+1]
0x1800399bb  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800399c1  jnz     short loc_1800399DF
0x1800399c3  mov     ebx, 5B4h
0x1800399c8  mov     r8d, ebx
0x1800399cb  mov     edx, 1
0x1800399d0  mov     rcx, rdi
0x1800399d3  call    Socket_ProcessReturnStatus2
0x1800399d8  mov     ebx, eax
0x1800399da  jmp     loc_180039887
0x1800399df  mov     [rsp+80h+lpCompletionRoutine], r13; lpCompletionRoutine
0x1800399e4  lea     rax, [rbp+cbBytesReturned]
0x1800399e8  mov     [rsp+80h+lpOverlapped], r13; lpOverlapped
0x1800399ed  lea     r8, [rbp+var_18]; lpvInBuffer
0x1800399f1  mov     [rsp+80h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800399f6  mov     r9d, 10h; cbInBuffer
0x1800399fc  lea     rax, [rbp+vOutBuffer]
0x180039a00  mov     [rsp+80h+cbOutBuffer], 8; cbOutBuffer
0x180039a08  mov     edx, 0C8000006h; dwIoControlCode
0x180039a0d  mov     [rsp+80h+lpvOutBuffer], rax; lpvOutBuffer
0x180039a12  mov     [rbp+cbBytesReturned], r13d
0x180039a16  call    cs:__imp_WSAIoctl
0x180039a1d  nop     dword ptr [rax+rax+00h]
0x180039a22  mov     ebx, eax
0x180039a24  cmp     eax, r12d
0x180039a27  jz      loc_180039B67
0x180039a2d  mov     r8d, [rdi+0DCh]
0x180039a34  lea     rcx, [rdi+48h]
0x180039a38  mov     [rsp+80h+lpcbBytesReturned], rcx
0x180039a3d  lea     rax, [rbp+cbBytesReturned]
0x180039a41  mov     rcx, [rdi+38h]
0x180039a45  xor     r9d, r9d
0x180039a48  mov     qword ptr [rsp+80h+cbOutBuffer], rax
0x180039a4d  mov     rdx, r15
0x180039a50  mov     rax, [rbp+vOutBuffer]
0x180039a54  mov     [rbp+cbBytesReturned], r13d
0x180039a58  mov     dword ptr [rsp+80h+lpvOutBuffer], r13d
0x180039a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a62  test    eax, eax
0x180039a64  jnz     loc_1800399C8
0x180039a6a  call    cs:__imp_GetLastError
0x180039a71  nop     dword ptr [rax+rax+00h]
0x180039a76  mov     ebx, eax
0x180039a78  test    eax, eax
0x180039a7a  jz      loc_1800399C8
0x180039a80  cmp     eax, 3E5h
0x180039a85  jz      loc_1800399C8
0x180039a8b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180039a92  jz      loc_1800399C8
0x180039a98  mov     dword ptr [rsp+80h+lpcbBytesReturned], eax
0x180039a9c  mov     r9, r15
0x180039a9f  mov     eax, [rdi+0DCh]
0x180039aa5  mov     qword ptr [rsp+80h+cbOutBuffer], rdi
0x180039aaa  mov     dword ptr [rsp+80h+lpvOutBuffer], eax
0x180039aae  call    WPP_SF__SOCKADDR_dqD
0x180039ab3  jmp     loc_1800399C8
0x180039ab8  test    rsi, rsi
0x180039abb  jz      loc_180039887
0x180039ac1  jmp     loc_1800398C0
0x180039ac6  mov     edx, 18h
0x180039acb  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039ad2  mov     ecx, 40Bh
0x180039ad7  mov     r9d, eax
0x180039ada  call    WPP_SF_d
0x180039adf  jmp     loc_1800398C0
0x180039ae4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180039aeb  jz      short loc_180039B03
0x180039aed  mov     edx, 19h
0x180039af2  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039af9  mov     ecx, 40Bh
0x180039afe  call    WPP_SF_
0x180039b03  mov     rdx, r12
0x180039b06  mov     rcx, rsi
0x180039b09  call    AddSecureSocketOptions
0x180039b0e  test    eax, eax
0x180039b10  jz      loc_18003991C
0x180039b16  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180039b1d  jz      short loc_180039B38
0x180039b1f  mov     edx, 1Ah
0x180039b24  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039b2b  mov     ecx, 40Bh
0x180039b30  mov     r9d, eax
0x180039b33  call    WPP_SF_d
0x180039b38  mov     ebx, 2749h
0x180039b3d  jmp     loc_1800398C0
0x180039b42  call    cs:__imp_WSAGetLastError
0x180039b49  nop     dword ptr [rax+rax+00h]
0x180039b4e  mov     ebx, eax
0x180039b50  jmp     loc_1800398C0
0x180039b55  mov     edx, 1
0x180039b5a  mov     rcx, rsi; s
0x180039b5d  call    Socket_CloseEx
0x180039b62  jmp     loc_180039887
0x180039b67  call    cs:__imp_GetLastError
0x180039b6e  nop     dword ptr [rax+rax+00h]
0x180039b73  mov     ebx, eax
0x180039b75  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180039b7c  jz      loc_1800399C8
0x180039b82  mov     edx, 1Ch
0x180039b87  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039b8e  mov     ecx, 40Bh
0x180039b93  mov     r9d, eax
0x180039b96  call    WPP_SF_d
0x180039b9b  jmp     loc_1800399C8
0x180039ba0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180039ba7  jz      loc_180039887
0x180039bad  mov     edx, 1Bh
0x180039bb2  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039bb9  mov     ecx, 40Bh
0x180039bbe  mov     r9d, eax
0x180039bc1  call    WPP_SF_d
0x180039bc6  jmp     loc_180039887
0x180039bcb  mov     edx, 1Eh
0x180039bd0  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x180039bd7  mov     ecx, 40Bh
0x180039bdc  mov     r9d, ebx
0x180039bdf  call    WPP_SF_d
0x180039be4  jmp     loc_1800398E9
```
