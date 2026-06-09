# DnsWinhttpCreateSession

- ea: `0x18004413c`
- end: `0x1800444a8`
- name: `DnsWinhttpCreateSession`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180043d04`

## callees

- `0x180043180`
- `0x18004413c`
- `0x18008b5f0`
- `0x1800dc9e0`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004442e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004442e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180044223`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180044223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800441e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800441e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044200`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044200`
- `WINHTTP!WinHttpCloseHandle` at `0x18004443f`
- `WINHTTP!WinHttpCloseHandle` at `0x18004443f`
- `WINHTTP!WinHttpOpen` at `0x180044242`
- `WINHTTP!WinHttpOpen` at `0x180044242`
- `WINHTTP!WinHttpSetOption` at `0x18004428a`
- `WINHTTP!WinHttpSetOption` at `0x1800442b3`
- `WINHTTP!WinHttpSetOption` at `0x1800442d5`
- `WINHTTP!WinHttpSetOption` at `0x1800442f8`
- `WINHTTP!WinHttpSetOption` at `0x18004431a`
- `WINHTTP!WinHttpSetOption` at `0x18004433d`
- `WINHTTP!WinHttpSetOption` at `0x180044360`
- `WINHTTP!WinHttpSetOption` at `0x180044392`
- `WINHTTP!WinHttpSetOption` at `0x1800443b4`
- `WINHTTP!WinHttpSetOption` at `0x1800443d3`
- `WINHTTP!WinHttpSetOption` at `0x1800443ff`
- `WINHTTP!WinHttpSetOption` at `0x18004441e`
- `WINHTTP!WinHttpSetOption` at `0x18004428a`
- `WINHTTP!WinHttpSetOption` at `0x1800442b3`
- `WINHTTP!WinHttpSetOption` at `0x1800442d5`
- `WINHTTP!WinHttpSetOption` at `0x1800442f8`
- `WINHTTP!WinHttpSetOption` at `0x18004431a`
- `WINHTTP!WinHttpSetOption` at `0x18004433d`
- `WINHTTP!WinHttpSetOption` at `0x180044360`
- `WINHTTP!WinHttpSetOption` at `0x180044392`
- `WINHTTP!WinHttpSetOption` at `0x1800443b4`
- `WINHTTP!WinHttpSetOption` at `0x1800443d3`
- `WINHTTP!WinHttpSetOption` at `0x1800443ff`
- `WINHTTP!WinHttpSetOption` at `0x18004441e`

## pseudocode

```c
__int64 __fastcall DnsWinhttpCreateSession(int a1, RTL_SRWLOCK **a2)
{
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v5; // rax
  RTL_SRWLOCK *v6; // rsi
  DWORD LastError; // ebx
  void *v8; // rdi
  int Buffer; // [rsp+30h] [rbp-40h] BYREF
  int v11; // [rsp+34h] [rbp-3Ch] BYREF
  int v12; // [rsp+38h] [rbp-38h] BYREF
  int v13; // [rsp+3Ch] [rbp-34h] BYREF
  int v14; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+44h] [rbp-2Ch] BYREF
  int v16; // [rsp+48h] [rbp-28h] BYREF
  int v17; // [rsp+4Ch] [rbp-24h] BYREF
  int v18; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF

  Buffer = 0;
  v13 = 1;
  v15 = 1;
  v16 = 1;
  v17 = 1;
  v18 = 1;
  v11 = 0;
  v14 = 2;
  v19 = 0;
  v12 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 16, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, a2, a1);
  ProcessHeap = g_hProcessHeap;
  *a2 = 0;
  if ( !ProcessHeap )
  {
    ProcessHeap = GetProcessHeap();
    g_hProcessHeap = ProcessHeap;
  }
  v5 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x30u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = 14;
    goto LABEL_25;
  }
  LODWORD(v5->Ptr) = 1;
  InitializeSRWLock(v5 + 2);
  v8 = WinHttpOpen(0, 1u, 0, 0, 0x10000000u);
  if ( !v8 )
  {
    LastError = GetLastError();
LABEL_23:
    DeRefDnsWinhttpSession(v6);
    goto LABEL_25;
  }
  BYTE2(Buffer) = 3;
  LOWORD(Buffer) = 500;
  if ( !WinHttpSetOption(v8, 0x71u, &Buffer, 4u)
    || (v11 = 10000, !WinHttpSetOption(v8, 5u, &v11, 4u))
    || !WinHttpSetOption(v8, 6u, &v11, 4u)
    || !WinHttpSetOption(v8, 0x89u, &v13, 4u)
    || !WinHttpSetOption(v8, 0x4Du, &v14, 4u)
    || !WinHttpSetOption(v8, 0x9Au, &v15, 4u)
    || !WinHttpSetOption(v8, 0x8Bu, &v16, 4u)
    || (v19 = 0x700000003LL, !WinHttpSetOption(v8, 0xA2u, &v19, 8u))
    || !WinHttpSetOption(v8, 0xC3u, 0, 0)
    || !WinHttpSetOption(v8, 0xC7u, &v17, 4u)
    || a1 == 1
    && ((v12 = dword_180111834, !WinHttpSetOption(v8, 0x49u, &v12, 4u)) || !WinHttpSetOption(v8, 0xA1u, &v18, 4u)) )
  {
    LastError = GetLastError();
    WinHttpCloseHandle(v8);
    goto LABEL_23;
  }
  v6[1].Ptr = v8;
  *a2 = v6;
  LastError = 0;
LABEL_25:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 17, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18004413c  mov     [rsp-28h+arg_0], rbx
0x180044141  mov     [rsp-28h+arg_10], rsi
0x180044146  push    rbp
0x180044147  push    rdi
0x180044148  push    r12
0x18004414a  push    r13
0x18004414c  push    r14
0x18004414e  mov     rbp, rsp
0x180044151  sub     rsp, 70h
0x180044155  mov     rax, cs:__security_cookie
0x18004415c  xor     rax, rsp
0x18004415f  mov     [rbp+var_10], rax
0x180044163  mov     r12d, 1
0x180044169  mov     [rbp+Buffer], 0
0x180044170  mov     [rbp+var_34], r12d
0x180044174  mov     rbx, rdx
0x180044177  mov     [rbp+var_2C], r12d
0x18004417b  mov     r14d, ecx
0x18004417e  mov     [rbp+var_28], r12d
0x180044182  mov     [rbp+var_24], r12d
0x180044186  mov     [rbp+var_20], r12d
0x18004418a  mov     [rbp+var_3C], 0
0x180044191  mov     [rbp+var_30], 2
0x180044198  mov     [rbp+var_18], 0
0x1800441a0  mov     [rbp+var_38], 0
0x1800441a7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800441ae  jz      short loc_1800441CE
0x1800441b0  lea     edx, [r12+0Fh]
0x1800441b5  mov     [rsp+70h+dwFlags], r14d
0x1800441ba  mov     ecx, 40Bh
0x1800441bf  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x1800441c6  mov     r9, rbx
0x1800441c9  call    WPP_SF_qD
0x1800441ce  mov     rax, cs:g_hProcessHeap
0x1800441d5  mov     qword ptr [rbx], 0
0x1800441dc  test    rax, rax
0x1800441df  jnz     short loc_1800441F4
0x1800441e1  call    cs:__imp_GetProcessHeap
0x1800441e8  nop     dword ptr [rax+rax+00h]
0x1800441ed  mov     cs:g_hProcessHeap, rax
0x1800441f4  mov     edx, 8; dwFlags
0x1800441f9  mov     rcx, rax; hHeap
0x1800441fc  lea     r8d, [rdx+28h]; dwBytes
0x180044200  call    cs:__imp_HeapAlloc
0x180044207  nop     dword ptr [rax+rax+00h]
0x18004420c  mov     rsi, rax
0x18004420f  test    rax, rax
0x180044212  jnz     short loc_18004421C
0x180044214  lea     ebx, [rax+0Eh]
0x180044217  jmp     loc_18004445E
0x18004421c  lea     rcx, [rax+10h]; SRWLock
0x180044220  mov     [rax], r12d
0x180044223  call    cs:__imp_InitializeSRWLock
0x18004422a  nop     dword ptr [rax+rax+00h]
0x18004422f  xor     r9d, r9d; pszProxyBypassW
0x180044232  mov     [rsp+70h+dwFlags], 10000000h; dwFlags
0x18004423a  xor     r8d, r8d; pszProxyW
0x18004423d  mov     edx, r12d; dwAccessType
0x180044240  xor     ecx, ecx; pszAgentW
0x180044242  call    cs:__imp_WinHttpOpen
0x180044249  nop     dword ptr [rax+rax+00h]
0x18004424e  mov     rdi, rax
0x180044251  test    rax, rax
0x180044254  jnz     short loc_180044269
0x180044256  call    cs:__imp_GetLastError
0x18004425d  nop     dword ptr [rax+rax+00h]
0x180044262  mov     ebx, eax
0x180044264  jmp     loc_18004444B
0x180044269  mov     r13d, 4
0x18004426f  mov     byte ptr [rbp+Buffer+2], 3
0x180044273  mov     eax, 1F4h
0x180044278  lea     r8, [rbp+Buffer]; lpBuffer
0x18004427c  mov     r9d, r13d; dwBufferLength
0x18004427f  mov     word ptr [rbp+Buffer], ax
0x180044283  mov     rcx, rdi; hInternet
0x180044286  lea     edx, [r13+6Dh]; dwOption
0x18004428a  call    cs:__imp_WinHttpSetOption
0x180044291  nop     dword ptr [rax+rax+00h]
0x180044296  test    eax, eax
0x180044298  jz      loc_18004442E
0x18004429e  mov     r9d, r13d; dwBufferLength
0x1800442a1  mov     [rbp+var_3C], 2710h
0x1800442a8  lea     r8, [rbp+var_3C]; lpBuffer
0x1800442ac  mov     rcx, rdi; hInternet
0x1800442af  lea     edx, [r13+1]; dwOption
0x1800442b3  call    cs:__imp_WinHttpSetOption
0x1800442ba  nop     dword ptr [rax+rax+00h]
0x1800442bf  test    eax, eax
0x1800442c1  jz      loc_18004442E
0x1800442c7  mov     r9d, r13d; dwBufferLength
0x1800442ca  lea     r8, [rbp+var_3C]; lpBuffer
0x1800442ce  lea     edx, [r13+2]; dwOption
0x1800442d2  mov     rcx, rdi; hInternet
0x1800442d5  call    cs:__imp_WinHttpSetOption
0x1800442dc  nop     dword ptr [rax+rax+00h]
0x1800442e1  test    eax, eax
0x1800442e3  jz      loc_18004442E
0x1800442e9  mov     r9d, r13d; dwBufferLength
0x1800442ec  lea     r8, [rbp+var_34]; lpBuffer
0x1800442f0  mov     edx, 89h; dwOption
0x1800442f5  mov     rcx, rdi; hInternet
0x1800442f8  call    cs:__imp_WinHttpSetOption
0x1800442ff  nop     dword ptr [rax+rax+00h]
0x180044304  test    eax, eax
0x180044306  jz      loc_18004442E
0x18004430c  mov     r9d, r13d; dwBufferLength
0x18004430f  lea     r8, [rbp+var_30]; lpBuffer
0x180044313  lea     edx, [r13+49h]; dwOption
0x180044317  mov     rcx, rdi; hInternet
0x18004431a  call    cs:__imp_WinHttpSetOption
0x180044321  nop     dword ptr [rax+rax+00h]
0x180044326  test    eax, eax
0x180044328  jz      loc_18004442E
0x18004432e  mov     r9d, r13d; dwBufferLength
0x180044331  lea     r8, [rbp+var_2C]; lpBuffer
0x180044335  mov     edx, 9Ah; dwOption
0x18004433a  mov     rcx, rdi; hInternet
0x18004433d  call    cs:__imp_WinHttpSetOption
0x180044344  nop     dword ptr [rax+rax+00h]
0x180044349  test    eax, eax
0x18004434b  jz      loc_18004442E
0x180044351  mov     r9d, r13d; dwBufferLength
0x180044354  lea     r8, [rbp+var_28]; lpBuffer
0x180044358  mov     edx, 8Bh; dwOption
0x18004435d  mov     rcx, rdi; hInternet
0x180044360  call    cs:__imp_WinHttpSetOption
0x180044367  nop     dword ptr [rax+rax+00h]
0x18004436c  test    eax, eax
0x18004436e  jz      loc_18004442E
0x180044374  lea     r9d, [r13+4]; dwBufferLength
0x180044378  mov     dword ptr [rbp+var_18], 3
0x18004437f  lea     r8, [rbp+var_18]; lpBuffer
0x180044383  mov     dword ptr [rbp+var_18+4], 7
0x18004438a  mov     edx, 0A2h; dwOption
0x18004438f  mov     rcx, rdi; hInternet
0x180044392  call    cs:__imp_WinHttpSetOption
0x180044399  nop     dword ptr [rax+rax+00h]
0x18004439e  test    eax, eax
0x1800443a0  jz      loc_18004442E
0x1800443a6  xor     r9d, r9d; dwBufferLength
0x1800443a9  xor     r8d, r8d; lpBuffer
0x1800443ac  mov     edx, 0C3h; dwOption
0x1800443b1  mov     rcx, rdi; hInternet
0x1800443b4  call    cs:__imp_WinHttpSetOption
0x1800443bb  nop     dword ptr [rax+rax+00h]
0x1800443c0  test    eax, eax
0x1800443c2  jz      short loc_18004442E
0x1800443c4  mov     r9d, r13d; dwBufferLength
0x1800443c7  lea     r8, [rbp+var_24]; lpBuffer
0x1800443cb  mov     edx, 0C7h; dwOption
0x1800443d0  mov     rcx, rdi; hInternet
0x1800443d3  call    cs:__imp_WinHttpSetOption
0x1800443da  nop     dword ptr [rax+rax+00h]
0x1800443df  test    eax, eax
0x1800443e1  jz      short loc_18004442E
0x1800443e3  cmp     r14d, r12d
0x1800443e6  jnz     short loc_180044455
0x1800443e8  mov     eax, cs:dword_180111834
0x1800443ee  lea     r8, [rbp+var_38]; lpBuffer
0x1800443f2  mov     r9d, r13d; dwBufferLength
0x1800443f5  mov     [rbp+var_38], eax
0x1800443f8  lea     edx, [r13+45h]; dwOption
0x1800443fc  mov     rcx, rdi; hInternet
0x1800443ff  call    cs:__imp_WinHttpSetOption
0x180044406  nop     dword ptr [rax+rax+00h]
0x18004440b  test    eax, eax
0x18004440d  jz      short loc_18004442E
0x18004440f  mov     r9d, r13d; dwBufferLength
0x180044412  lea     r8, [rbp+var_20]; lpBuffer
0x180044416  mov     edx, 0A1h; dwOption
0x18004441b  mov     rcx, rdi; hInternet
0x18004441e  call    cs:__imp_WinHttpSetOption
0x180044425  nop     dword ptr [rax+rax+00h]
0x18004442a  test    eax, eax
0x18004442c  jnz     short loc_180044455
0x18004442e  call    cs:__imp_GetLastError
0x180044435  nop     dword ptr [rax+rax+00h]
0x18004443a  mov     rcx, rdi; hInternet
0x18004443d  mov     ebx, eax
0x18004443f  call    cs:__imp_WinHttpCloseHandle
0x180044446  nop     dword ptr [rax+rax+00h]
0x18004444b  mov     rcx, rsi; lpMem
0x18004444e  call    DeRefDnsWinhttpSession
0x180044453  jmp     short loc_18004445E
0x180044455  mov     [rsi+8], rdi
0x180044459  mov     [rbx], rsi
0x18004445c  xor     ebx, ebx
0x18004445e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180044465  jz      short loc_180044480
0x180044467  mov     edx, 11h
0x18004446c  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180044473  mov     ecx, 40Bh
0x180044478  mov     r9d, ebx
0x18004447b  call    WPP_SF_d
0x180044480  mov     eax, ebx
0x180044482  mov     rcx, [rbp+var_10]
0x180044486  xor     rcx, rsp; StackCookie
0x180044489  call    __security_check_cookie
0x18004448e  lea     r11, [rsp+70h+var_s0]
0x180044493  mov     rbx, [r11+30h]
0x180044497  mov     rsi, [r11+40h]
0x18004449b  mov     rsp, r11
0x18004449e  pop     r14
0x1800444a0  pop     r13
0x1800444a2  pop     r12
0x1800444a4  pop     rdi
0x1800444a5  pop     rbp
0x1800444a6  retn
```
