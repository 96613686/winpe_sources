# McastRequestAddress

- ea: `0x18000cfe0`
- end: `0x18000d3c5`
- name: `McastRequestAddress`
- size: `997`
- prototype: `DWORD __stdcall(IP_ADDR_FAMILY AddrFamily, LPMCAST_CLIENT_UID pRequestID, PMCAST_SCOPE_CTX pScopeCtx, PMCAST_LEASE_REQUEST pAddrRequest, PMCAST_LEASE_RESPONSE pAddrResponse)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x180002c50`
- `0x1800048c0`
- `0x18000cfe0`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d24c`
- `RPCRT4!NdrClientCall3` at `0x18000d24c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010cfa`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010cfa`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d1e0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d268`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d2a1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d1e0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d268`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d2a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000d0b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000d138`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000d1c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000d0b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000d138`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000d1c0`

## pseudocode

```c
DWORD __stdcall McastRequestAddress(
        IP_ADDR_FAMILY AddrFamily,
        LPMCAST_CLIENT_UID pRequestID,
        PMCAST_SCOPE_CTX pScopeCtx,
        PMCAST_LEASE_REQUEST pAddrRequest,
        PMCAST_LEASE_RESPONSE pAddrResponse)
{
  DWORD Pointer; // ebx
  DWORD ClientUIDLength; // eax
  HLOCAL v10; // rax
  unsigned int AddrCount; // ecx
  HLOCAL v12; // rax
  WORD *p_AddrCount; // rdi
  LPWSTR CommandLineW; // rax
  CLIENT_CALL_RETURN v15; // rax
  LPWSTR v16; // rax
  void *v17; // rdx
  unsigned int v18; // eax
  __int128 v20; // [rsp+58h] [rbp-E0h] BYREF
  CLIENT_CALL_RETURN v21; // [rsp+68h] [rbp-D0h]
  PMCAST_LEASE_RESPONSE v22; // [rsp+70h] [rbp-C8h]
  WORD *v23; // [rsp+80h] [rbp-B8h]
  LONG *p_LeaseEndTime; // [rsp+88h] [rbp-B0h]
  IPNG_ADDRESS *p_ServerAddress; // [rsp+90h] [rbp-A8h]
  _OWORD v26[2]; // [rsp+98h] [rbp-A0h] BYREF
  void *Src; // [rsp+B8h] [rbp-80h] BYREF
  __int128 v28; // [rsp+C0h] [rbp-78h]
  IPNG_ADDRESS ServerAddress; // [rsp+D0h] [rbp-68h]
  __int128 v30; // [rsp+E0h] [rbp-58h] BYREF

  v22 = pAddrResponse;
  v20 = 0;
  v28 = 0;
  ServerAddress = 0;
  v30 = 0;
  memset(v26, 0, sizeof(v26));
  Src = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 277, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( !(unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( !pRequestID
      || !pAddrRequest
      || !pScopeCtx
      || !pRequestID->ClientUID
      || (ClientUIDLength = pRequestID->ClientUIDLength) == 0 )
    {
      Pointer = 87;
      goto LABEL_28;
    }
    DWORD2(v20) = pRequestID->ClientUIDLength;
    v10 = LocalAlloc(0x40u, ClientUIDLength);
    *(_QWORD *)&v20 = v10;
    if ( !v10 )
      goto LABEL_11;
    memcpy_0(v10, pRequestID->ClientUID, pRequestID->ClientUIDLength);
    AddrCount = pAddrRequest->AddrCount;
    WORD1(v30) = pAddrRequest->AddrCount;
    DWORD2(v28) = pAddrRequest->LeaseDuration;
    *(_QWORD *)&v28 = *(_QWORD *)&pAddrRequest->LeaseStartTime;
    LOWORD(v30) = pAddrRequest->MinAddrCount;
    HIDWORD(v28) = pAddrRequest->MinLeaseDuration;
    ServerAddress = pAddrRequest->ServerAddress;
    if ( pAddrRequest->pAddrBuf )
    {
      v12 = LocalAlloc(0x40u, 4LL * AddrCount);
      *((_QWORD *)&v30 + 1) = v12;
      if ( !v12 )
        goto LABEL_11;
      memcpy_0(v12, pAddrRequest->pAddrBuf, 4LL * pAddrRequest->AddrCount);
    }
    p_AddrCount = &pAddrResponse->AddrCount;
    v23 = &pAddrResponse->AddrCount;
    WORD4(v26[1]) = pAddrResponse->AddrCount;
    p_LeaseEndTime = &pAddrResponse->LeaseEndTime;
    *(_QWORD *)&v26[0] = *(_QWORD *)&pAddrResponse->LeaseStartTime;
    p_ServerAddress = &pAddrResponse->ServerAddress;
    *(IPNG_ADDRESS *)((char *)v26 + 8) = pAddrResponse->ServerAddress;
    Src = LocalAlloc(0x40u, 4LL * WORD4(v26[1]));
    if ( Src )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_S(1028, 279, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
      }
      v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x29u, 0).Pointer;
      Pointer = (DWORD)v15.Pointer;
      v21.Pointer = v15.Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v16 = GetCommandLineW();
        WPP_SF_DS(1028, 280, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v16);
      }
      if ( !Pointer )
      {
        *(_QWORD *)&pAddrResponse->LeaseStartTime = *(_QWORD *)&v26[0];
        pAddrResponse->ServerAddress = *(IPNG_ADDRESS *)((char *)v26 + 8);
        v17 = Src;
        if ( Src && (v18 = WORD4(v26[1]), WORD4(v26[1]) <= *p_AddrCount) )
        {
          *p_AddrCount = WORD4(v26[1]);
          memcpy_0(pAddrResponse->pAddrBuf, v17, 4LL * v18);
        }
        else if ( WORD4(v26[1]) > *p_AddrCount )
        {
          Pointer = 122;
        }
      }
      goto LABEL_28;
    }
LABEL_11:
    Pointer = 8;
    goto LABEL_28;
  }
  Pointer = 50;
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_d(1025, 278, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
LABEL_28:
  DhcpMidlUserFree(&v20);
  DhcpMidlUserFree((char *)&v30 + 8);
  DhcpMidlUserFree(&Src);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 281, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000cfe0  mov     r11, rsp
0x18000cfe3  push    rbx
0x18000cfe4  push    rsi
0x18000cfe5  push    rdi
0x18000cfe6  push    r12
0x18000cfe8  push    r13
0x18000cfea  push    r14
0x18000cfec  push    r15
0x18000cfee  sub     rsp, 100h
0x18000cff5  mov     rax, cs:__security_cookie
0x18000cffc  xor     rax, rsp
0x18000cfff  mov     [rsp+138h+var_48], rax
0x18000d007  mov     rbx, r9
0x18000d00a  mov     r13, r8
0x18000d00d  mov     rdi, rdx
0x18000d010  mov     [rsp+138h+var_E8], cx
0x18000d015  mov     r12, [rsp+138h+pAddrResponse]
0x18000d01d  mov     r15, r12
0x18000d020  mov     [rsp+138h+var_C8], r12
0x18000d025  xorps   xmm0, xmm0
0x18000d028  movups  [rsp+138h+var_E0], xmm0
0x18000d02d  xorps   xmm1, xmm1
0x18000d030  movups  xmmword ptr [r11-78h], xmm1
0x18000d035  movups  xmmword ptr [r11-68h], xmm1
0x18000d03a  movups  xmmword ptr [r11-58h], xmm1
0x18000d03f  xor     eax, eax
0x18000d041  movups  [rsp+138h+var_A0], xmm0
0x18000d049  movups  [rsp+138h+var_90], xmm0
0x18000d051  mov     [r11-80h], rax
0x18000d055  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d05c  jz      short loc_18000D074
0x18000d05e  mov     edx, 115h
0x18000d063  mov     ecx, 404h
0x18000d068  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000d06f  call    WPP_SF_
0x18000d074  call    DhcpIsFSEGuestSystem
0x18000d079  test    eax, eax
0x18000d07b  jnz     loc_18000D332
0x18000d081  test    rdi, rdi
0x18000d084  jnz     short loc_18000D090
0x18000d086  mov     ebx, 57h ; 'W'
0x18000d08b  jmp     loc_18000D35A
0x18000d090  test    rbx, rbx
0x18000d093  jz      short loc_18000D086
0x18000d095  test    r13, r13
0x18000d098  jz      short loc_18000D086
0x18000d09a  cmp     qword ptr [rdi], 0
0x18000d09e  jz      short loc_18000D086
0x18000d0a0  mov     eax, [rdi+8]
0x18000d0a3  test    eax, eax
0x18000d0a5  jz      short loc_18000D086
0x18000d0a7  mov     dword ptr [rsp+138h+var_E0+8], eax
0x18000d0ab  mov     edx, eax; uBytes
0x18000d0ad  mov     esi, 40h ; '@'
0x18000d0b2  mov     ecx, esi; uFlags
0x18000d0b4  call    cs:__imp_LocalAlloc
0x18000d0ba  mov     qword ptr [rsp+138h+var_E0], rax
0x18000d0bf  test    rax, rax
0x18000d0c2  jnz     short loc_18000D0CE
0x18000d0c4  mov     ebx, 8
0x18000d0c9  jmp     loc_18000D35A
0x18000d0ce  mov     r8d, [rdi+8]; Size
0x18000d0d2  mov     rdx, [rdi]; Src
0x18000d0d5  mov     rcx, rax; void *
0x18000d0d8  call    memcpy_0
0x18000d0dd  movzx   ecx, word ptr [rbx+22h]
0x18000d0e1  mov     [rsp+138h+var_56], cx
0x18000d0e9  mov     eax, [rbx+8]
0x18000d0ec  mov     [rsp+138h+var_70], eax
0x18000d0f3  mov     eax, [rbx]
0x18000d0f5  mov     [rsp+138h+var_78], eax
0x18000d0fc  mov     eax, [rbx+4]
0x18000d0ff  mov     [rsp+138h+var_74], eax
0x18000d106  movzx   eax, word ptr [rbx+20h]
0x18000d10a  mov     [rsp+138h+var_58], ax
0x18000d112  mov     eax, [rbx+0Ch]
0x18000d115  mov     [rsp+138h+var_6C], eax
0x18000d11c  movups  xmm0, xmmword ptr [rbx+10h]
0x18000d120  movdqu  [rsp+138h+var_68], xmm0
0x18000d129  cmp     qword ptr [rbx+28h], 0
0x18000d12e  jz      short loc_18000D164
0x18000d130  mov     edx, ecx
0x18000d132  shl     rdx, 2; uBytes
0x18000d136  mov     ecx, esi; uFlags
0x18000d138  call    cs:__imp_LocalAlloc
0x18000d13e  mov     [rsp+138h+var_50], rax
0x18000d146  test    rax, rax
0x18000d149  jz      loc_18000D0C4
0x18000d14f  movzx   r8d, word ptr [rbx+22h]
0x18000d154  shl     r8, 2; Size
0x18000d158  mov     rdx, [rbx+28h]; Src
0x18000d15c  mov     rcx, rax; void *
0x18000d15f  call    memcpy_0
0x18000d164  lea     rdi, [r12+18h]
0x18000d169  mov     [rsp+138h+var_B8], rdi
0x18000d171  movzx   edx, word ptr [rdi]
0x18000d174  mov     word ptr [rsp+138h+var_90+8], dx
0x18000d17c  lea     rsi, [r12+4]
0x18000d181  mov     [rsp+138h+var_B0], rsi
0x18000d189  mov     eax, [rsi]
0x18000d18b  mov     dword ptr [rsp+138h+var_A0+4], eax
0x18000d192  mov     eax, [r12]
0x18000d196  mov     dword ptr [rsp+138h+var_A0], eax
0x18000d19d  lea     r14, [r12+8]
0x18000d1a2  mov     [rsp+138h+var_A8], r14
0x18000d1aa  movups  xmm0, xmmword ptr [r14]
0x18000d1ae  movdqu  [rsp+138h+var_A0+8], xmm0
0x18000d1b7  shl     rdx, 2; uBytes
0x18000d1bb  mov     ecx, 40h ; '@'; uFlags
0x18000d1c0  call    cs:__imp_LocalAlloc
0x18000d1c6  mov     [rsp+138h+Src], rax
0x18000d1ce  test    rax, rax
0x18000d1d1  jz      loc_18000D0C4
0x18000d1d7  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d1de  jz      short loc_18000D200
0x18000d1e0  call    cs:__imp_GetCommandLineW
0x18000d1e6  mov     r9, rax
0x18000d1e9  mov     edx, 117h
0x18000d1ee  mov     ecx, 404h
0x18000d1f3  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000d1fa  call    WPP_SF_S
0x18000d1ff  nop
0x18000d200  mov     [rsp+138h+var_D0], 0
0x18000d209  movzx   eax, [rsp+138h+var_E8]
0x18000d20e  lea     rcx, [rsp+138h+var_A0]
0x18000d216  mov     [rsp+138h+var_F8], rcx
0x18000d21b  lea     rcx, [rsp+138h+var_78]
0x18000d223  mov     [rsp+138h+var_100], rcx
0x18000d228  mov     [rsp+138h+var_108], r13
0x18000d22d  lea     rcx, [rsp+138h+var_E0]
0x18000d232  mov     [rsp+138h+var_110], rcx
0x18000d237  mov     dword ptr [rsp+138h+var_118], eax
0x18000d23b  xor     r9d, r9d
0x18000d23e  xor     r8d, r8d; pReturnValue
0x18000d241  lea     edx, [r9+29h]; nProcNum
0x18000d245  lea     rcx, pProxyInfo; pProxyInfo
0x18000d24c  call    cs:__imp_NdrClientCall3
0x18000d252  mov     rbx, rax
0x18000d255  mov     [rsp+138h+var_D0], rax
0x18000d25a  mov     [rsp+138h+var_E4], eax
0x18000d25e  jmp     short loc_18000D298
0x18000d260  mov     edi, eax
0x18000d262  mov     ebx, eax
0x18000d264  mov     [rsp+138h+var_E4], eax
0x18000d268  call    cs:__imp_GetCommandLineW
0x18000d26e  mov     rdx, rax
0x18000d271  mov     ecx, ebx
0x18000d273  call    TraceRpcException
0x18000d278  mov     r15, [rsp+138h+var_C8]
0x18000d27d  mov     r12, r15
0x18000d280  mov     rdi, [rsp+138h+var_B8]
0x18000d288  mov     rsi, [rsp+138h+var_B0]
0x18000d290  mov     r14, [rsp+138h+var_A8]
0x18000d298  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d29f  jz      short loc_18000D2C5
0x18000d2a1  call    cs:__imp_GetCommandLineW
0x18000d2a7  mov     edx, 118h
0x18000d2ac  mov     ecx, 404h
0x18000d2b1  mov     [rsp+138h+var_118], rax
0x18000d2b6  mov     r9d, ebx
0x18000d2b9  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000d2c0  call    WPP_SF_DS
0x18000d2c5  test    ebx, ebx
0x18000d2c7  jnz     loc_18000D35A
0x18000d2cd  mov     eax, dword ptr [rsp+138h+var_A0+4]
0x18000d2d4  mov     [rsi], eax
0x18000d2d6  mov     eax, dword ptr [rsp+138h+var_A0]
0x18000d2dd  mov     [r12], eax
0x18000d2e1  movups  xmm0, [rsp+138h+var_A0+8]
0x18000d2e9  movdqu  xmmword ptr [r14], xmm0
0x18000d2ee  mov     rdx, [rsp+138h+Src]; Src
0x18000d2f6  test    rdx, rdx
0x18000d2f9  jz      short loc_18000D31E
0x18000d2fb  movzx   eax, word ptr [rsp+138h+var_90+8]
0x18000d303  cmp     ax, [rdi]
0x18000d306  ja      short loc_18000D31E
0x18000d308  mov     r8d, eax
0x18000d30b  mov     [rdi], r8w
0x18000d30f  shl     r8, 2; Size
0x18000d313  mov     rcx, [r15+20h]; void *
0x18000d317  call    memcpy_0
0x18000d31c  jmp     short loc_18000D35A
0x18000d31e  movzx   eax, word ptr [rdi]
0x18000d321  cmp     word ptr [rsp+138h+var_90+8], ax
0x18000d329  jbe     short loc_18000D35A
0x18000d32b  mov     ebx, 7Ah ; 'z'
0x18000d330  jmp     short loc_18000D35A
0x18000d332  mov     r9d, 32h ; '2'
0x18000d338  mov     ebx, r9d
0x18000d33b  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000d342  jz      short loc_18000D35A
0x18000d344  mov     edx, 116h
0x18000d349  mov     ecx, 401h
0x18000d34e  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000d355  call    WPP_SF_d
0x18000d35a  lea     rcx, [rsp+138h+var_E0]
0x18000d35f  call    DhcpMidlUserFree
0x18000d364  lea     rcx, [rsp+138h+var_50]
0x18000d36c  call    DhcpMidlUserFree
0x18000d371  lea     rcx, [rsp+138h+Src]
0x18000d379  call    DhcpMidlUserFree
0x18000d37e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d385  jz      short loc_18000D3A0
0x18000d387  mov     edx, 119h
0x18000d38c  mov     ecx, 404h
0x18000d391  mov     r9d, ebx
0x18000d394  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000d39b  call    WPP_SF_d
0x18000d3a0  mov     eax, ebx
0x18000d3a2  mov     rcx, [rsp+138h+var_48]
0x18000d3aa  xor     rcx, rsp; StackCookie
0x18000d3ad  call    __security_check_cookie
0x18000d3b2  add     rsp, 100h
0x18000d3b9  pop     r15
0x18000d3bb  pop     r14
0x18000d3bd  pop     r13
0x18000d3bf  pop     r12
0x18000d3c1  pop     rdi
0x18000d3c2  pop     rsi
0x18000d3c3  pop     rbx
0x18000d3c4  retn
0x180010cec  push    rbp
0x180010cee  sub     rsp, 50h
0x180010cf2  mov     rbp, rdx
0x180010cf5  mov     rcx, [rcx]
0x180010cf8  mov     ecx, [rcx]; ExceptionCode
0x180010cfa  call    cs:__imp_I_RpcExceptionFilter
0x180010d00  nop
0x180010d01  add     rsp, 50h
0x180010d05  pop     rbp
0x180010d06  retn
```
