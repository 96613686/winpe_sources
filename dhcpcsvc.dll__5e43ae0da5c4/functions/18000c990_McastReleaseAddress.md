# McastReleaseAddress

- ea: `0x18000c990`
- end: `0x18000cc01`
- name: `McastReleaseAddress`
- size: `625`
- prototype: `DWORD __stdcall(IP_ADDR_FAMILY AddrFamily, LPMCAST_CLIENT_UID pRequestID, PMCAST_LEASE_REQUEST pReleaseRequest)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x180002c50`
- `0x1800048c0`
- `0x18000c990`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000cb27`
- `RPCRT4!NdrClientCall3` at `0x18000cb27`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cad5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cb43`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cb5d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cad5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cb43`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cb5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000ca2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000caa4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000ca2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000caa4`

## pseudocode

```c
DWORD __stdcall McastReleaseAddress(
        IP_ADDR_FAMILY AddrFamily,
        LPMCAST_CLIENT_UID pRequestID,
        PMCAST_LEASE_REQUEST pReleaseRequest)
{
  DWORD Pointer; // ebx
  DWORD ClientUIDLength; // eax
  HLOCAL v7; // rax
  __int64 AddrCount; // rdx
  HLOCAL v9; // rax
  LPWSTR CommandLineW; // rax
  CLIENT_CALL_RETURN v11; // rax
  LPWSTR v12; // rax
  __int128 v14; // [rsp+48h] [rbp-70h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+58h] [rbp-60h]
  __int128 v16; // [rsp+60h] [rbp-58h]
  IPNG_ADDRESS ServerAddress; // [rsp+70h] [rbp-48h]
  __int128 v18; // [rsp+80h] [rbp-38h] BYREF

  v14 = 0;
  v16 = 0;
  ServerAddress = 0;
  v18 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 287, WPP_e15037783097355a5233924022d92169_Traceguids, AddrFamily);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 288, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else
  {
    if ( !pRequestID
      || !pReleaseRequest
      || !pRequestID->ClientUID
      || (ClientUIDLength = pRequestID->ClientUIDLength) == 0 )
    {
      Pointer = 87;
      goto LABEL_20;
    }
    DWORD2(v14) = pRequestID->ClientUIDLength;
    v7 = LocalAlloc(0x40u, ClientUIDLength);
    *(_QWORD *)&v14 = v7;
    if ( !v7 )
      goto LABEL_10;
    memcpy_0(v7, pRequestID->ClientUID, pRequestID->ClientUIDLength);
    AddrCount = pReleaseRequest->AddrCount;
    WORD1(v18) = pReleaseRequest->AddrCount;
    DWORD2(v16) = pReleaseRequest->LeaseDuration;
    *(_QWORD *)&v16 = *(_QWORD *)&pReleaseRequest->LeaseStartTime;
    LOWORD(v18) = pReleaseRequest->MinAddrCount;
    HIDWORD(v16) = pReleaseRequest->MinLeaseDuration;
    ServerAddress = pReleaseRequest->ServerAddress;
    if ( pReleaseRequest->pAddrBuf )
    {
      v9 = LocalAlloc(0x40u, 4 * AddrCount);
      *((_QWORD *)&v18 + 1) = v9;
      if ( !v9 )
      {
LABEL_10:
        Pointer = 8;
        goto LABEL_20;
      }
      memcpy_0(v9, pReleaseRequest->pAddrBuf, 4LL * pReleaseRequest->AddrCount);
    }
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 289, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Bu, 0).Pointer;
    Pointer = (DWORD)v11.Pointer;
    v15.Pointer = v11.Pointer;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v12 = GetCommandLineW();
      WPP_SF_DS(1028, 290, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v12);
    }
  }
LABEL_20:
  DhcpMidlUserFree(&v14);
  DhcpMidlUserFree((char *)&v18 + 8);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 291, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000c990  push    rbx
0x18000c992  push    rsi
0x18000c993  push    rdi
0x18000c994  sub     rsp, 0A0h
0x18000c99b  mov     rax, cs:__security_cookie
0x18000c9a2  xor     rax, rsp
0x18000c9a5  mov     [rsp+0B8h+var_28], rax
0x18000c9ad  mov     rbx, r8
0x18000c9b0  mov     rdi, rdx
0x18000c9b3  movzx   esi, cx
0x18000c9b6  xorps   xmm0, xmm0
0x18000c9b9  movups  [rsp+0B8h+var_70], xmm0
0x18000c9be  xorps   xmm1, xmm1
0x18000c9c1  movups  [rsp+0B8h+var_58], xmm1
0x18000c9c6  movups  [rsp+0B8h+var_48], xmm1
0x18000c9cb  movups  [rsp+0B8h+var_38], xmm1
0x18000c9d3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c9da  jz      short loc_18000C9F5
0x18000c9dc  mov     r9d, esi
0x18000c9df  mov     edx, 11Fh
0x18000c9e4  mov     ecx, 404h
0x18000c9e9  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c9f0  call    WPP_SF_d
0x18000c9f5  call    DhcpIsFSEGuestSystem
0x18000c9fa  test    eax, eax
0x18000c9fc  jnz     loc_18000CB83
0x18000ca02  test    rdi, rdi
0x18000ca05  jnz     short loc_18000CA11
0x18000ca07  mov     ebx, 57h ; 'W'
0x18000ca0c  jmp     loc_18000CBAB
0x18000ca11  test    rbx, rbx
0x18000ca14  jz      short loc_18000CA07
0x18000ca16  cmp     qword ptr [rdi], 0
0x18000ca1a  jz      short loc_18000CA07
0x18000ca1c  mov     eax, [rdi+8]
0x18000ca1f  test    eax, eax
0x18000ca21  jz      short loc_18000CA07
0x18000ca23  mov     dword ptr [rsp+0B8h+var_70+8], eax
0x18000ca27  mov     edx, eax; uBytes
0x18000ca29  mov     ecx, 40h ; '@'; uFlags
0x18000ca2e  call    cs:__imp_LocalAlloc
0x18000ca34  mov     qword ptr [rsp+0B8h+var_70], rax
0x18000ca39  test    rax, rax
0x18000ca3c  jnz     short loc_18000CA48
0x18000ca3e  mov     ebx, 8
0x18000ca43  jmp     loc_18000CBAB
0x18000ca48  mov     r8d, [rdi+8]; Size
0x18000ca4c  mov     rdx, [rdi]; Src
0x18000ca4f  mov     rcx, rax; void *
0x18000ca52  call    memcpy_0
0x18000ca57  movzx   edx, word ptr [rbx+22h]
0x18000ca5b  mov     word ptr [rsp+0B8h+var_38+2], dx
0x18000ca63  mov     eax, [rbx+8]
0x18000ca66  mov     dword ptr [rsp+0B8h+var_58+8], eax
0x18000ca6a  mov     eax, [rbx]
0x18000ca6c  mov     dword ptr [rsp+0B8h+var_58], eax
0x18000ca70  mov     eax, [rbx+4]
0x18000ca73  mov     dword ptr [rsp+0B8h+var_58+4], eax
0x18000ca77  movzx   eax, word ptr [rbx+20h]
0x18000ca7b  mov     word ptr [rsp+0B8h+var_38], ax
0x18000ca83  mov     eax, [rbx+0Ch]
0x18000ca86  mov     dword ptr [rsp+0B8h+var_58+0Ch], eax
0x18000ca8a  movups  xmm0, xmmword ptr [rbx+10h]
0x18000ca8e  movdqu  [rsp+0B8h+var_48], xmm0
0x18000ca94  cmp     qword ptr [rbx+28h], 0
0x18000ca99  jz      short loc_18000CACC
0x18000ca9b  shl     rdx, 2; uBytes
0x18000ca9f  mov     ecx, 40h ; '@'; uFlags
0x18000caa4  call    cs:__imp_LocalAlloc
0x18000caaa  mov     qword ptr [rsp+0B8h+var_38+8], rax
0x18000cab2  test    rax, rax
0x18000cab5  jz      short loc_18000CA3E
0x18000cab7  movzx   r8d, word ptr [rbx+22h]
0x18000cabc  shl     r8, 2; Size
0x18000cac0  mov     rdx, [rbx+28h]; Src
0x18000cac4  mov     rcx, rax; void *
0x18000cac7  call    memcpy_0
0x18000cacc  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000cad3  jz      short loc_18000CAF5
0x18000cad5  call    cs:__imp_GetCommandLineW
0x18000cadb  mov     r9, rax
0x18000cade  mov     edx, 121h
0x18000cae3  mov     ecx, 404h
0x18000cae8  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000caef  call    WPP_SF_S
0x18000caf4  nop
0x18000caf5  mov     [rsp+0B8h+var_60], 0
0x18000cafe  lea     rcx, [rsp+0B8h+var_58]
0x18000cb03  mov     [rsp+0B8h+var_88], rcx
0x18000cb08  lea     rcx, [rsp+0B8h+var_70]
0x18000cb0d  mov     [rsp+0B8h+var_90], rcx
0x18000cb12  mov     dword ptr [rsp+0B8h+var_98], esi
0x18000cb16  xor     r9d, r9d
0x18000cb19  xor     r8d, r8d; pReturnValue
0x18000cb1c  lea     edx, [r9+2Bh]; nProcNum
0x18000cb20  lea     rcx, pProxyInfo; pProxyInfo
0x18000cb27  call    cs:__imp_NdrClientCall3
0x18000cb2d  mov     rbx, rax
0x18000cb30  mov     [rsp+0B8h+var_60], rax
0x18000cb35  mov     [rsp+0B8h+var_78], eax
0x18000cb39  jmp     short loc_18000CB54
0x18000cb3b  mov     edi, eax
0x18000cb3d  mov     ebx, eax
0x18000cb3f  mov     [rsp+0B8h+var_78], eax
0x18000cb43  call    cs:__imp_GetCommandLineW
0x18000cb49  mov     rdx, rax
0x18000cb4c  mov     ecx, ebx
0x18000cb4e  call    TraceRpcException
0x18000cb53  nop
0x18000cb54  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000cb5b  jz      short loc_18000CBAB
0x18000cb5d  call    cs:__imp_GetCommandLineW
0x18000cb63  mov     edx, 122h
0x18000cb68  mov     ecx, 404h
0x18000cb6d  mov     [rsp+0B8h+var_98], rax
0x18000cb72  mov     r9d, ebx
0x18000cb75  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cb7c  call    WPP_SF_DS
0x18000cb81  jmp     short loc_18000CBAB
0x18000cb83  mov     r9d, 32h ; '2'
0x18000cb89  mov     ebx, r9d
0x18000cb8c  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000cb93  jz      short loc_18000CBAB
0x18000cb95  mov     edx, 120h
0x18000cb9a  mov     ecx, 401h
0x18000cb9f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cba6  call    WPP_SF_d
0x18000cbab  lea     rcx, [rsp+0B8h+var_70]
0x18000cbb0  call    DhcpMidlUserFree
0x18000cbb5  lea     rcx, [rsp+0B8h+var_38+8]
0x18000cbbd  call    DhcpMidlUserFree
0x18000cbc2  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000cbc9  jz      short loc_18000CBE4
0x18000cbcb  mov     edx, 123h
0x18000cbd0  mov     ecx, 404h
0x18000cbd5  mov     r9d, ebx
0x18000cbd8  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cbdf  call    WPP_SF_d
0x18000cbe4  mov     eax, ebx
0x18000cbe6  mov     rcx, [rsp+0B8h+var_28]
0x18000cbee  xor     rcx, rsp; StackCookie
0x18000cbf1  call    __security_check_cookie
0x18000cbf6  add     rsp, 0A0h
0x18000cbfd  pop     rdi
0x18000cbfe  pop     rsi
0x18000cbff  pop     rbx
0x18000cc00  retn
0x180010d30  push    rbp
0x180010d32  sub     rsp, 40h
0x180010d36  mov     rbp, rdx
0x180010d39  mov     rcx, [rcx]
0x180010d3c  mov     ecx, [rcx]; ExceptionCode
0x180010d3e  call    cs:__imp_I_RpcExceptionFilter
0x180010d44  nop
0x180010d45  add     rsp, 40h
0x180010d49  pop     rbp
0x180010d4a  retn
```
