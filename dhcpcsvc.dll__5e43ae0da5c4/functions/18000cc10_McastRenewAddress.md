# McastRenewAddress

- ea: `0x18000cc10`
- end: `0x18000cfd2`
- name: `McastRenewAddress`
- size: `962`
- prototype: `DWORD __stdcall(IP_ADDR_FAMILY AddrFamily, LPMCAST_CLIENT_UID pRequestID, PMCAST_LEASE_REQUEST pRenewRequest, PMCAST_LEASE_RESPONSE pRenewResponse)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x180002c50`
- `0x1800048c0`
- `0x18000cc10`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ce5f`
- `RPCRT4!NdrClientCall3` at `0x18000ce5f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cdfc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ce7b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ceae`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000cdfc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ce7b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ceae`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000ccd6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000cd5a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000cddc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000ccd6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000cd5a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000cddc`

## pseudocode

```c
DWORD __stdcall McastRenewAddress(
        IP_ADDR_FAMILY AddrFamily,
        LPMCAST_CLIENT_UID pRequestID,
        PMCAST_LEASE_REQUEST pRenewRequest,
        PMCAST_LEASE_RESPONSE pRenewResponse)
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
  __int128 v20; // [rsp+48h] [rbp-E0h] BYREF
  CLIENT_CALL_RETURN v21; // [rsp+58h] [rbp-D0h]
  PMCAST_LEASE_RESPONSE v22; // [rsp+60h] [rbp-C8h]
  WORD *v23; // [rsp+70h] [rbp-B8h]
  LONG *p_LeaseEndTime; // [rsp+78h] [rbp-B0h]
  IPNG_ADDRESS *p_ServerAddress; // [rsp+80h] [rbp-A8h]
  _OWORD v26[2]; // [rsp+88h] [rbp-A0h] BYREF
  void *Src; // [rsp+A8h] [rbp-80h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-78h]
  IPNG_ADDRESS ServerAddress; // [rsp+C0h] [rbp-68h]
  __int128 v30; // [rsp+D0h] [rbp-58h] BYREF

  v22 = pRenewResponse;
  v20 = 0;
  v28 = 0;
  ServerAddress = 0;
  v30 = 0;
  memset(v26, 0, sizeof(v26));
  Src = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 282, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( !(unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( !pRequestID || !pRenewRequest || !pRequestID->ClientUID || (ClientUIDLength = pRequestID->ClientUIDLength) == 0 )
    {
      Pointer = 87;
      goto LABEL_27;
    }
    DWORD2(v20) = pRequestID->ClientUIDLength;
    v10 = LocalAlloc(0x40u, ClientUIDLength);
    *(_QWORD *)&v20 = v10;
    if ( !v10 )
      goto LABEL_10;
    memcpy_0(v10, pRequestID->ClientUID, pRequestID->ClientUIDLength);
    AddrCount = pRenewRequest->AddrCount;
    WORD1(v30) = pRenewRequest->AddrCount;
    DWORD2(v28) = pRenewRequest->LeaseDuration;
    *(_QWORD *)&v28 = *(_QWORD *)&pRenewRequest->LeaseStartTime;
    LOWORD(v30) = pRenewRequest->MinAddrCount;
    HIDWORD(v28) = pRenewRequest->MinLeaseDuration;
    ServerAddress = pRenewRequest->ServerAddress;
    if ( pRenewRequest->pAddrBuf )
    {
      v12 = LocalAlloc(0x40u, 4LL * AddrCount);
      *((_QWORD *)&v30 + 1) = v12;
      if ( !v12 )
        goto LABEL_10;
      memcpy_0(v12, pRenewRequest->pAddrBuf, 4LL * pRenewRequest->AddrCount);
    }
    p_AddrCount = &pRenewResponse->AddrCount;
    v23 = &pRenewResponse->AddrCount;
    WORD4(v26[1]) = pRenewResponse->AddrCount;
    p_LeaseEndTime = &pRenewResponse->LeaseEndTime;
    *(_QWORD *)&v26[0] = *(_QWORD *)&pRenewResponse->LeaseStartTime;
    p_ServerAddress = &pRenewResponse->ServerAddress;
    *(IPNG_ADDRESS *)((char *)v26 + 8) = pRenewResponse->ServerAddress;
    Src = LocalAlloc(0x40u, 4LL * WORD4(v26[1]));
    if ( Src )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_S(1028, 284, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
      }
      v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Au, 0).Pointer;
      Pointer = (DWORD)v15.Pointer;
      v21.Pointer = v15.Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v16 = GetCommandLineW();
        WPP_SF_DS(1028, 285, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v16);
      }
      if ( !Pointer )
      {
        *(_QWORD *)&pRenewResponse->LeaseStartTime = *(_QWORD *)&v26[0];
        pRenewResponse->ServerAddress = *(IPNG_ADDRESS *)((char *)v26 + 8);
        v17 = Src;
        if ( Src && (v18 = WORD4(v26[1]), WORD4(v26[1]) <= *p_AddrCount) )
        {
          *p_AddrCount = WORD4(v26[1]);
          memcpy_0(pRenewResponse->pAddrBuf, v17, 4LL * v18);
        }
        else if ( WORD4(v26[1]) > *p_AddrCount )
        {
          Pointer = 122;
        }
      }
      goto LABEL_27;
    }
LABEL_10:
    Pointer = 8;
    goto LABEL_27;
  }
  Pointer = 50;
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_d(1025, 283, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
LABEL_27:
  DhcpMidlUserFree(&v20);
  DhcpMidlUserFree((char *)&v30 + 8);
  DhcpMidlUserFree(&Src);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 286, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000cc10  mov     r11, rsp
0x18000cc13  push    rbx
0x18000cc14  push    rsi
0x18000cc15  push    rdi
0x18000cc16  push    r12
0x18000cc18  push    r13
0x18000cc1a  push    r14
0x18000cc1c  push    r15
0x18000cc1e  sub     rsp, 0F0h
0x18000cc25  mov     rax, cs:__security_cookie
0x18000cc2c  xor     rax, rsp
0x18000cc2f  mov     [rsp+128h+var_48], rax
0x18000cc37  mov     r12, r9
0x18000cc3a  mov     rbx, r8
0x18000cc3d  mov     rdi, rdx
0x18000cc40  movzx   r13d, cx
0x18000cc44  mov     r15, r9
0x18000cc47  mov     [rsp+128h+var_C8], r9
0x18000cc4c  xorps   xmm0, xmm0
0x18000cc4f  movups  [rsp+128h+var_E0], xmm0
0x18000cc54  xorps   xmm1, xmm1
0x18000cc57  movups  xmmword ptr [r11-78h], xmm1
0x18000cc5c  movups  xmmword ptr [r11-68h], xmm1
0x18000cc61  movups  xmmword ptr [r11-58h], xmm1
0x18000cc66  xor     eax, eax
0x18000cc68  movups  [rsp+128h+var_A0], xmm0
0x18000cc70  movups  [rsp+128h+var_90], xmm0
0x18000cc78  mov     [r11-80h], rax
0x18000cc7c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000cc83  jz      short loc_18000CC9B
0x18000cc85  mov     edx, 11Ah
0x18000cc8a  mov     ecx, 404h
0x18000cc8f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cc96  call    WPP_SF_
0x18000cc9b  call    DhcpIsFSEGuestSystem
0x18000cca0  test    eax, eax
0x18000cca2  jnz     loc_18000CF3F
0x18000cca8  test    rdi, rdi
0x18000ccab  jnz     short loc_18000CCB7
0x18000ccad  mov     ebx, 57h ; 'W'
0x18000ccb2  jmp     loc_18000CF67
0x18000ccb7  test    rbx, rbx
0x18000ccba  jz      short loc_18000CCAD
0x18000ccbc  cmp     qword ptr [rdi], 0
0x18000ccc0  jz      short loc_18000CCAD
0x18000ccc2  mov     eax, [rdi+8]
0x18000ccc5  test    eax, eax
0x18000ccc7  jz      short loc_18000CCAD
0x18000ccc9  mov     dword ptr [rsp+128h+var_E0+8], eax
0x18000cccd  mov     edx, eax; uBytes
0x18000cccf  mov     esi, 40h ; '@'
0x18000ccd4  mov     ecx, esi; uFlags
0x18000ccd6  call    cs:__imp_LocalAlloc
0x18000ccdc  mov     qword ptr [rsp+128h+var_E0], rax
0x18000cce1  test    rax, rax
0x18000cce4  jnz     short loc_18000CCF0
0x18000cce6  mov     ebx, 8
0x18000cceb  jmp     loc_18000CF67
0x18000ccf0  mov     r8d, [rdi+8]; Size
0x18000ccf4  mov     rdx, [rdi]; Src
0x18000ccf7  mov     rcx, rax; void *
0x18000ccfa  call    memcpy_0
0x18000ccff  movzx   ecx, word ptr [rbx+22h]
0x18000cd03  mov     [rsp+128h+var_56], cx
0x18000cd0b  mov     eax, [rbx+8]
0x18000cd0e  mov     [rsp+128h+var_70], eax
0x18000cd15  mov     eax, [rbx]
0x18000cd17  mov     [rsp+128h+var_78], eax
0x18000cd1e  mov     eax, [rbx+4]
0x18000cd21  mov     [rsp+128h+var_74], eax
0x18000cd28  movzx   eax, word ptr [rbx+20h]
0x18000cd2c  mov     [rsp+128h+var_58], ax
0x18000cd34  mov     eax, [rbx+0Ch]
0x18000cd37  mov     [rsp+128h+var_6C], eax
0x18000cd3e  movups  xmm0, xmmword ptr [rbx+10h]
0x18000cd42  movdqu  [rsp+128h+var_68], xmm0
0x18000cd4b  cmp     qword ptr [rbx+28h], 0
0x18000cd50  jz      short loc_18000CD86
0x18000cd52  mov     edx, ecx
0x18000cd54  shl     rdx, 2; uBytes
0x18000cd58  mov     ecx, esi; uFlags
0x18000cd5a  call    cs:__imp_LocalAlloc
0x18000cd60  mov     [rsp+128h+var_50], rax
0x18000cd68  test    rax, rax
0x18000cd6b  jz      loc_18000CCE6
0x18000cd71  movzx   r8d, word ptr [rbx+22h]
0x18000cd76  shl     r8, 2; Size
0x18000cd7a  mov     rdx, [rbx+28h]; Src
0x18000cd7e  mov     rcx, rax; void *
0x18000cd81  call    memcpy_0
0x18000cd86  lea     rdi, [r12+18h]
0x18000cd8b  mov     [rsp+128h+var_B8], rdi
0x18000cd90  movzx   edx, word ptr [rdi]
0x18000cd93  mov     word ptr [rsp+128h+var_90+8], dx
0x18000cd9b  lea     rsi, [r12+4]
0x18000cda0  mov     [rsp+128h+var_B0], rsi
0x18000cda5  mov     eax, [rsi]
0x18000cda7  mov     dword ptr [rsp+128h+var_A0+4], eax
0x18000cdae  mov     eax, [r12]
0x18000cdb2  mov     dword ptr [rsp+128h+var_A0], eax
0x18000cdb9  lea     r14, [r12+8]
0x18000cdbe  mov     [rsp+128h+var_A8], r14
0x18000cdc6  movups  xmm0, xmmword ptr [r14]
0x18000cdca  movdqu  [rsp+128h+var_A0+8], xmm0
0x18000cdd3  shl     rdx, 2; uBytes
0x18000cdd7  mov     ecx, 40h ; '@'; uFlags
0x18000cddc  call    cs:__imp_LocalAlloc
0x18000cde2  mov     [rsp+128h+Src], rax
0x18000cdea  test    rax, rax
0x18000cded  jz      loc_18000CCE6
0x18000cdf3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000cdfa  jz      short loc_18000CE1C
0x18000cdfc  call    cs:__imp_GetCommandLineW
0x18000ce02  mov     r9, rax
0x18000ce05  mov     edx, 11Ch
0x18000ce0a  mov     ecx, 404h
0x18000ce0f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000ce16  call    WPP_SF_S
0x18000ce1b  nop
0x18000ce1c  mov     [rsp+128h+var_D0], 0
0x18000ce25  lea     rcx, [rsp+128h+var_A0]
0x18000ce2d  mov     [rsp+128h+var_F0], rcx
0x18000ce32  lea     rcx, [rsp+128h+var_78]
0x18000ce3a  mov     [rsp+128h+var_F8], rcx
0x18000ce3f  lea     rcx, [rsp+128h+var_E0]
0x18000ce44  mov     [rsp+128h+var_100], rcx
0x18000ce49  mov     dword ptr [rsp+128h+var_108], r13d
0x18000ce4e  xor     r9d, r9d
0x18000ce51  xor     r8d, r8d; pReturnValue
0x18000ce54  lea     edx, [r9+2Ah]; nProcNum
0x18000ce58  lea     rcx, pProxyInfo; pProxyInfo
0x18000ce5f  call    cs:__imp_NdrClientCall3
0x18000ce65  mov     rbx, rax
0x18000ce68  mov     [rsp+128h+var_D0], rax
0x18000ce6d  mov     [rsp+128h+var_E8], eax
0x18000ce71  jmp     short loc_18000CEA5
0x18000ce73  mov     edi, eax
0x18000ce75  mov     ebx, eax
0x18000ce77  mov     [rsp+128h+var_E8], eax
0x18000ce7b  call    cs:__imp_GetCommandLineW
0x18000ce81  mov     rdx, rax
0x18000ce84  mov     ecx, ebx
0x18000ce86  call    TraceRpcException
0x18000ce8b  mov     r15, [rsp+128h+var_C8]
0x18000ce90  mov     r12, r15
0x18000ce93  mov     rdi, [rsp+128h+var_B8]
0x18000ce98  mov     rsi, [rsp+128h+var_B0]
0x18000ce9d  mov     r14, [rsp+128h+var_A8]
0x18000cea5  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000ceac  jz      short loc_18000CED2
0x18000ceae  call    cs:__imp_GetCommandLineW
0x18000ceb4  mov     edx, 11Dh
0x18000ceb9  mov     ecx, 404h
0x18000cebe  mov     [rsp+128h+var_108], rax
0x18000cec3  mov     r9d, ebx
0x18000cec6  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cecd  call    WPP_SF_DS
0x18000ced2  test    ebx, ebx
0x18000ced4  jnz     loc_18000CF67
0x18000ceda  mov     eax, dword ptr [rsp+128h+var_A0+4]
0x18000cee1  mov     [rsi], eax
0x18000cee3  mov     eax, dword ptr [rsp+128h+var_A0]
0x18000ceea  mov     [r12], eax
0x18000ceee  movups  xmm0, [rsp+128h+var_A0+8]
0x18000cef6  movdqu  xmmword ptr [r14], xmm0
0x18000cefb  mov     rdx, [rsp+128h+Src]; Src
0x18000cf03  test    rdx, rdx
0x18000cf06  jz      short loc_18000CF2B
0x18000cf08  movzx   eax, word ptr [rsp+128h+var_90+8]
0x18000cf10  cmp     ax, [rdi]
0x18000cf13  ja      short loc_18000CF2B
0x18000cf15  mov     r8d, eax
0x18000cf18  mov     [rdi], r8w
0x18000cf1c  shl     r8, 2; Size
0x18000cf20  mov     rcx, [r15+20h]; void *
0x18000cf24  call    memcpy_0
0x18000cf29  jmp     short loc_18000CF67
0x18000cf2b  movzx   eax, word ptr [rdi]
0x18000cf2e  cmp     word ptr [rsp+128h+var_90+8], ax
0x18000cf36  jbe     short loc_18000CF67
0x18000cf38  mov     ebx, 7Ah ; 'z'
0x18000cf3d  jmp     short loc_18000CF67
0x18000cf3f  mov     r9d, 32h ; '2'
0x18000cf45  mov     ebx, r9d
0x18000cf48  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000cf4f  jz      short loc_18000CF67
0x18000cf51  mov     edx, 11Bh
0x18000cf56  mov     ecx, 401h
0x18000cf5b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cf62  call    WPP_SF_d
0x18000cf67  lea     rcx, [rsp+128h+var_E0]
0x18000cf6c  call    DhcpMidlUserFree
0x18000cf71  lea     rcx, [rsp+128h+var_50]
0x18000cf79  call    DhcpMidlUserFree
0x18000cf7e  lea     rcx, [rsp+128h+Src]
0x18000cf86  call    DhcpMidlUserFree
0x18000cf8b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000cf92  jz      short loc_18000CFAD
0x18000cf94  mov     edx, 11Eh
0x18000cf99  mov     ecx, 404h
0x18000cf9e  mov     r9d, ebx
0x18000cfa1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000cfa8  call    WPP_SF_d
0x18000cfad  mov     eax, ebx
0x18000cfaf  mov     rcx, [rsp+128h+var_48]
0x18000cfb7  xor     rcx, rsp; StackCookie
0x18000cfba  call    __security_check_cookie
0x18000cfbf  add     rsp, 0F0h
0x18000cfc6  pop     r15
0x18000cfc8  pop     r14
0x18000cfca  pop     r13
0x18000cfcc  pop     r12
0x18000cfce  pop     rdi
0x18000cfcf  pop     rsi
0x18000cfd0  pop     rbx
0x18000cfd1  retn
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
