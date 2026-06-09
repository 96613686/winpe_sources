# IrdaConnect(_LCMINIPORT *)

- ea: `0x1800e1f74`
- end: `0x1800e22ae`
- name: `?IrdaConnect@@YAKPEAU_LCMINIPORT@@@Z`
- size: `826`
- prototype: `unsigned int __fastcall(struct _LCMINIPORT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800e2348`

## callees

- `0x180046650`
- `0x180047330`
- `0x1800df488`
- `0x1800e1f74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e204c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e204c`
- `SPOOLSS!DllFreeSplMem` at `0x1800e20ba`
- `SPOOLSS!DllFreeSplMem` at `0x1800e225b`
- `SPOOLSS!DllFreeSplMem` at `0x1800e2279`
- `SPOOLSS!DllFreeSplMem` at `0x1800e20ba`
- `SPOOLSS!DllFreeSplMem` at `0x1800e225b`
- `SPOOLSS!DllFreeSplMem` at `0x1800e2279`
- `SPOOLSS!DllAllocSplMem` at `0x1800e203e`
- `SPOOLSS!DllAllocSplMem` at `0x1800e20c4`
- `SPOOLSS!DllAllocSplMem` at `0x1800e2214`
- `SPOOLSS!DllAllocSplMem` at `0x1800e203e`
- `SPOOLSS!DllAllocSplMem` at `0x1800e20c4`
- `SPOOLSS!DllAllocSplMem` at `0x1800e2214`
- `WS2_32!WSASocketW` at `0x1800e2070`
- `WS2_32!WSASocketW` at `0x1800e2070`
- `WS2_32!__imp_closesocket` at `0x1800e226f`
- `WS2_32!__imp_closesocket` at `0x1800e226f`
- `WS2_32!__imp_connect` at `0x1800e21b1`
- `WS2_32!__imp_connect` at `0x1800e21b1`
- `WS2_32!__imp_getsockopt` at `0x1800e209e`
- `WS2_32!__imp_getsockopt` at `0x1800e20f1`
- `WS2_32!__imp_getsockopt` at `0x1800e21db`
- `WS2_32!__imp_getsockopt` at `0x1800e209e`
- `WS2_32!__imp_getsockopt` at `0x1800e20f1`
- `WS2_32!__imp_getsockopt` at `0x1800e21db`
- `WS2_32!__imp_setsockopt` at `0x1800e2196`
- `WS2_32!__imp_setsockopt` at `0x1800e21fe`
- `WS2_32!__imp_setsockopt` at `0x1800e2196`
- `WS2_32!__imp_setsockopt` at `0x1800e21fe`
- `WS2_32!__imp_WSAGetLastError` at `0x1800e224c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800e224c`
- `WS2_32!__imp_WSAStartup` at `0x1800e202a`
- `WS2_32!__imp_WSAStartup` at `0x1800e202a`

## pseudocode

```c
__int64 __fastcall IrdaConnect(struct _LCMINIPORT *a1)
{
  int v2; // r14d
  __int64 v3; // r8
  SOCKET v4; // rdi
  unsigned int v5; // esi
  char *v6; // rbx
  DWORD LastError; // eax
  int v8; // r8d
  unsigned int v9; // edx
  unsigned int v10; // r11d
  int v11; // r10d
  unsigned int v12; // r9d
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 result; // rax
  int optlen; // [rsp+30h] [rbp-D0h] BYREF
  char v18[4]; // [rsp+34h] [rbp-CCh] BYREF
  char v19[4]; // [rsp+38h] [rbp-C8h] BYREF
  char optval[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  _BYTE name[31]; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+5Fh] [rbp-A1h]
  struct WSAData WSAData; // [rsp+60h] [rbp-A0h] BYREF

  optlen = 152;
  v2 = 0;
  *(_DWORD *)optval = 1;
  *(_DWORD *)v18 = 0;
  *(_DWORD *)v19 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v3 = *((_QWORD *)a1 + 3);
  strcpy(&name[6], "IrLPT");
  v4 = -1;
  memset(&name[12], 0, 19);
  v22 = 0;
  *(_DWORD *)name = 26;
  *(_WORD *)&name[4] = 0;
  LocalMonTelemetry::WriteDbgTraceInfo("IrdaConnect", L"Port: %ws", v3);
  v5 = WSAStartup(0x101u, &WSAData);
  if ( v5 )
  {
    v6 = 0;
    goto LABEL_29;
  }
  v6 = (char *)DllAllocSplMem((unsigned int)optlen);
  if ( !v6 )
  {
LABEL_3:
    LastError = GetLastError();
LABEL_27:
    v5 = LastError;
    goto LABEL_29;
  }
  v4 = WSASocketW(26, 1, 0, 0, 0, 1u);
  if ( v4 == -1 || getsockopt(v4, 255, 16, v6, &optlen) == -1 )
    goto LABEL_26;
  if ( (unsigned int)optlen > 0x98 )
  {
    DllFreeSplMem(v6);
    v6 = (char *)DllAllocSplMem((unsigned int)optlen);
    if ( !v6 )
      goto LABEL_3;
    if ( getsockopt(v4, 255, 16, v6, &optlen) == -1 )
    {
LABEL_26:
      LastError = WSAGetLastError();
      goto LABEL_27;
    }
  }
  *(_DWORD *)v18 = 0;
  v8 = *(_DWORD *)v6;
  if ( *(_DWORD *)v6 )
  {
    v9 = 0;
    v10 = 0;
    do
    {
      v11 = v8;
      v12 = v9;
      if ( (v6[29 * v9 + 30] & 8) != 0 )
        break;
      if ( (v6[29 * v10 + 31] & 8) != 0 )
        break;
      *(_DWORD *)v18 = ++v9;
      v12 = v9;
      v8 = *(_DWORD *)v6;
      v10 = v9;
      v11 = *(_DWORD *)v6;
    }
    while ( v9 < *(_DWORD *)v6 );
  }
  else
  {
    v12 = 0;
    v11 = 0;
  }
  if ( v12 == v11 )
  {
    v5 = 3012;
    goto LABEL_29;
  }
  v13 = *(_DWORD *)&v6[29 * v12 + 4];
  *(_DWORD *)v18 = 0;
  *(_DWORD *)&name[2] = v13;
  optlen = 4;
  if ( setsockopt(v4, 255, 21, optval, 4) == -1
    || connect(v4, (const struct sockaddr *)name, 32) == -1
    || getsockopt(v4, 255, 19, v19, &optlen) == -1
    || setsockopt(v4, 0xFFFF, 4097, v18, 4) == -1 )
  {
    v2 = 0;
    goto LABEL_26;
  }
  optlen = *(_DWORD *)v19 + 64;
  v14 = DllAllocSplMem((unsigned int)(*(_DWORD *)v19 + 64));
  if ( v14 )
  {
    v15 = *(_DWORD *)v19;
    v2 = 1;
    *((_QWORD *)a1 + 4) = v4;
    *((_QWORD *)a1 + 11) = v14;
    *(_DWORD *)(v14 + 4) = v15;
    *(_QWORD *)(v14 + 56) = v14 + 64;
  }
  else
  {
    v2 = 0;
    v5 = 8;
  }
LABEL_29:
  DllFreeSplMem(v6);
  if ( !v2 )
  {
    if ( v4 != -1 )
      closesocket(v4);
    DllFreeSplMem(*((_QWORD *)a1 + 11));
    *((_QWORD *)a1 + 11) = 0;
  }
  result = 0;
  if ( !v2 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x1800e1f74  push    rbp
0x1800e1f76  push    rbx
0x1800e1f77  push    rsi
0x1800e1f78  push    rdi
0x1800e1f79  push    r14
0x1800e1f7b  push    r15
0x1800e1f7d  lea     rbp, [rsp-118h]
0x1800e1f85  sub     rsp, 218h
0x1800e1f8c  mov     rax, cs:__security_cookie
0x1800e1f93  xor     rax, rsp
0x1800e1f96  mov     [rbp+140h+var_40], rax
0x1800e1f9d  mov     r15, rcx
0x1800e1fa0  mov     [rsp+240h+optlen], 98h
0x1800e1fa8  xor     r14d, r14d
0x1800e1fab  mov     dword ptr [rsp+240h+optval], 1
0x1800e1fb3  lea     rcx, [rsp+240h+WSAData]; void *
0x1800e1fb8  mov     dword ptr [rsp+240h+var_20C], r14d
0x1800e1fbd  xor     edx, edx; Val
0x1800e1fbf  mov     dword ptr [rsp+240h+var_208], r14d
0x1800e1fc4  mov     r8d, 198h; Size
0x1800e1fca  call    memset_0
0x1800e1fcf  mov     eax, dword ptr cs:aIrlpt; "IrLPT"
0x1800e1fd5  lea     rdx, aPortWs_0; "Port: %ws"
0x1800e1fdc  mov     r8, [r15+18h]
0x1800e1fe0  lea     rcx, aIrdaconnect; "IrdaConnect"
0x1800e1fe7  mov     dword ptr [rsp+240h+name+6], eax
0x1800e1feb  xorps   xmm0, xmm0
0x1800e1fee  movzx   eax, word ptr cs:aIrlpt+4; "T"
0x1800e1ff5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800e1ff9  mov     word ptr [rsp+240h+name+0Ah], ax
0x1800e1ffe  xor     eax, eax
0x1800e2000  movups  xmmword ptr [rsp+240h+name+0Ch], xmm0
0x1800e2005  mov     dword ptr [rsp+240h+name+1Bh], eax
0x1800e2009  mov     [rsp+240h+var_1E1], al
0x1800e200d  mov     dword ptr [rsp+240h+name], 1Ah
0x1800e2015  mov     word ptr [rsp+240h+name+4], r14w
0x1800e201b  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e2020  mov     ecx, 101h; wVersionRequested
0x1800e2025  lea     rdx, [rsp+240h+WSAData]; lpWSAData
0x1800e202a  call    cs:__imp_WSAStartup
0x1800e2030  mov     esi, eax
0x1800e2032  test    eax, eax
0x1800e2034  jnz     loc_1800E2256
0x1800e203a  mov     ecx, [rsp+240h+optlen]
0x1800e203e  call    cs:__imp_DllAllocSplMem
0x1800e2044  mov     rbx, rax
0x1800e2047  test    rax, rax
0x1800e204a  jnz     short loc_1800E2057
0x1800e204c  call    cs:__imp_GetLastError
0x1800e2052  jmp     loc_1800E2252
0x1800e2057  mov     eax, 1
0x1800e205c  xor     r9d, r9d; lpProtocolInfo
0x1800e205f  mov     [rsp+240h+dwFlags], eax; dwFlags
0x1800e2063  xor     r8d, r8d; protocol
0x1800e2066  mov     edx, eax; type
0x1800e2068  mov     [rsp+240h+g], r14d; g
0x1800e206d  lea     ecx, [rax+19h]; af
0x1800e2070  call    cs:__imp_WSASocketW
0x1800e2076  mov     rdi, rax
0x1800e2079  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e207d  jz      loc_1800E224C
0x1800e2083  lea     rax, [rsp+240h+optlen]
0x1800e2088  mov     r9, rbx; optval
0x1800e208b  mov     edx, 0FFh; level
0x1800e2090  mov     qword ptr [rsp+240h+g], rax; optlen
0x1800e2095  mov     r8d, 10h; optname
0x1800e209b  mov     rcx, rdi; s
0x1800e209e  call    cs:__imp_getsockopt
0x1800e20a4  cmp     eax, 0FFFFFFFFh
0x1800e20a7  jz      loc_1800E224C
0x1800e20ad  cmp     [rsp+240h+optlen], 98h
0x1800e20b5  jbe     short loc_1800E2100
0x1800e20b7  mov     rcx, rbx
0x1800e20ba  call    cs:__imp_DllFreeSplMem
0x1800e20c0  mov     ecx, [rsp+240h+optlen]
0x1800e20c4  call    cs:__imp_DllAllocSplMem
0x1800e20ca  mov     rbx, rax
0x1800e20cd  test    rax, rax
0x1800e20d0  jz      loc_1800E204C
0x1800e20d6  lea     rax, [rsp+240h+optlen]
0x1800e20db  mov     r9, rbx; optval
0x1800e20de  mov     edx, 0FFh; level
0x1800e20e3  mov     qword ptr [rsp+240h+g], rax; optlen
0x1800e20e8  mov     r8d, 10h; optname
0x1800e20ee  mov     rcx, rdi; s
0x1800e20f1  call    cs:__imp_getsockopt
0x1800e20f7  cmp     eax, 0FFFFFFFFh
0x1800e20fa  jz      loc_1800E224C
0x1800e2100  mov     dword ptr [rsp+240h+var_20C], r14d
0x1800e2105  mov     r8d, [rbx]
0x1800e2108  test    r8d, r8d
0x1800e210b  jz      short loc_1800E214C
0x1800e210d  xor     edx, edx
0x1800e210f  xor     r11d, r11d
0x1800e2112  mov     eax, edx
0x1800e2114  mov     r10d, r8d
0x1800e2117  imul    rcx, rax, 1Dh
0x1800e211b  mov     r9d, edx
0x1800e211e  test    byte ptr [rcx+rbx+1Eh], 8
0x1800e2123  jnz     short loc_1800E2152
0x1800e2125  mov     eax, r11d
0x1800e2128  imul    rcx, rax, 1Dh
0x1800e212c  test    byte ptr [rcx+rbx+1Fh], 8
0x1800e2131  jnz     short loc_1800E2152
0x1800e2133  inc     edx
0x1800e2135  mov     dword ptr [rsp+240h+var_20C], edx
0x1800e2139  mov     r9d, edx
0x1800e213c  mov     r8d, [rbx]
0x1800e213f  mov     r11d, edx
0x1800e2142  mov     r10d, r8d
0x1800e2145  cmp     edx, r8d
0x1800e2148  jb      short loc_1800E2112
0x1800e214a  jmp     short loc_1800E2152
0x1800e214c  xor     r9d, r9d
0x1800e214f  mov     r10d, r8d
0x1800e2152  cmp     r9d, r10d
0x1800e2155  jnz     short loc_1800E2161
0x1800e2157  mov     esi, 0BC4h
0x1800e215c  jmp     loc_1800E2258
0x1800e2161  mov     eax, r9d
0x1800e2164  mov     edx, 0FFh; level
0x1800e2169  imul    rcx, rax, 1Dh
0x1800e216d  lea     r9, [rsp+240h+optval]; optval
0x1800e2172  mov     eax, [rcx+rbx+4]
0x1800e2176  mov     rcx, rdi; s
0x1800e2179  mov     dword ptr [rsp+240h+var_20C], r14d
0x1800e217e  mov     r14d, 4
0x1800e2184  mov     dword ptr [rsp+240h+name+2], eax
0x1800e2188  mov     [rsp+240h+optlen], r14d
0x1800e218d  mov     [rsp+240h+g], r14d; optlen
0x1800e2192  lea     r8d, [r14+11h]; optname
0x1800e2196  call    cs:__imp_setsockopt
0x1800e219c  cmp     eax, 0FFFFFFFFh
0x1800e219f  jz      loc_1800E2249
0x1800e21a5  lea     r8d, [r14+1Ch]; namelen
0x1800e21a9  mov     rcx, rdi; s
0x1800e21ac  lea     rdx, [rsp+240h+name]; name
0x1800e21b1  call    cs:__imp_connect
0x1800e21b7  cmp     eax, 0FFFFFFFFh
0x1800e21ba  jz      loc_1800E2249
0x1800e21c0  lea     rax, [rsp+240h+optlen]
0x1800e21c5  mov     edx, 0FFh; level
0x1800e21ca  lea     r9, [rsp+240h+var_208]; optval
0x1800e21cf  mov     qword ptr [rsp+240h+g], rax; optlen
0x1800e21d4  lea     r8d, [r14+0Fh]; optname
0x1800e21d8  mov     rcx, rdi; s
0x1800e21db  call    cs:__imp_getsockopt
0x1800e21e1  cmp     eax, 0FFFFFFFFh
0x1800e21e4  jz      short loc_1800E2249
0x1800e21e6  lea     r9, [rsp+240h+var_20C]; optval
0x1800e21eb  mov     [rsp+240h+g], r14d; optlen
0x1800e21f0  mov     edx, 0FFFFh; level
0x1800e21f5  mov     r8d, 1001h; optname
0x1800e21fb  mov     rcx, rdi; s
0x1800e21fe  call    cs:__imp_setsockopt
0x1800e2204  cmp     eax, 0FFFFFFFFh
0x1800e2207  jz      short loc_1800E2249
0x1800e2209  mov     ecx, dword ptr [rsp+240h+var_208]
0x1800e220d  add     ecx, 40h ; '@'
0x1800e2210  mov     [rsp+240h+optlen], ecx
0x1800e2214  call    cs:__imp_DllAllocSplMem
0x1800e221a  mov     rcx, rax
0x1800e221d  test    rax, rax
0x1800e2220  jnz     short loc_1800E222A
0x1800e2222  xor     r14d, r14d
0x1800e2225  lea     esi, [rax+8]
0x1800e2228  jmp     short loc_1800E2258
0x1800e222a  mov     eax, dword ptr [rsp+240h+var_208]
0x1800e222e  mov     r14d, 1
0x1800e2234  mov     [r15+20h], rdi
0x1800e2238  mov     [r15+58h], rcx
0x1800e223c  mov     [rcx+4], eax
0x1800e223f  lea     rax, [rcx+40h]
0x1800e2243  mov     [rcx+38h], rax
0x1800e2247  jmp     short loc_1800E2258
0x1800e2249  xor     r14d, r14d
0x1800e224c  call    cs:__imp_WSAGetLastError
0x1800e2252  mov     esi, eax
0x1800e2254  jmp     short loc_1800E2258
0x1800e2256  xor     ebx, ebx
0x1800e2258  mov     rcx, rbx
0x1800e225b  call    cs:__imp_DllFreeSplMem
0x1800e2261  test    r14d, r14d
0x1800e2264  jnz     short loc_1800E2287
0x1800e2266  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800e226a  jz      short loc_1800E2275
0x1800e226c  mov     rcx, rdi; s
0x1800e226f  call    cs:__imp_closesocket
0x1800e2275  mov     rcx, [r15+58h]
0x1800e2279  call    cs:__imp_DllFreeSplMem
0x1800e227f  mov     qword ptr [r15+58h], 0
0x1800e2287  xor     eax, eax
0x1800e2289  test    r14d, r14d
0x1800e228c  cmovz   eax, esi
0x1800e228f  mov     rcx, [rbp+140h+var_40]
0x1800e2296  xor     rcx, rsp; StackCookie
0x1800e2299  call    __security_check_cookie
0x1800e229e  add     rsp, 218h
0x1800e22a5  pop     r15
0x1800e22a7  pop     r14
0x1800e22a9  pop     rdi
0x1800e22aa  pop     rsi
0x1800e22ab  pop     rbx
0x1800e22ac  pop     rbp
0x1800e22ad  retn
```
