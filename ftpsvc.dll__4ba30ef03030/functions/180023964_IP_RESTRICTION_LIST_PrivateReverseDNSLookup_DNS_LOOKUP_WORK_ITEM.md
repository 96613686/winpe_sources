# IP_RESTRICTION_LIST::PrivateReverseDNSLookup(DNS_LOOKUP_WORK_ITEM *)

- ea: `0x180023964`
- end: `0x180023d07`
- name: `?PrivateReverseDNSLookup@IP_RESTRICTION_LIST@@CAXPEAVDNS_LOOKUP_WORK_ITEM@@@Z`
- size: `931`
- prototype: `void __fastcall(struct DNS_LOOKUP_WORK_ITEM *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023d10`

## callees

- `0x180001210`
- `0x180001250`
- `0x180023964`
- `0x180046feb`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180023bfa`
- `KERNEL32!GetTickCount64` at `0x180023c8f`
- `KERNEL32!GetTickCount64` at `0x180023bfa`
- `KERNEL32!GetTickCount64` at `0x180023c8f`
- `WS2_32!GetAddrInfoW` at `0x180023a4f`
- `WS2_32!GetAddrInfoW` at `0x180023a4f`
- `WS2_32!GetNameInfoW` at `0x1800239fe`
- `WS2_32!GetNameInfoW` at `0x1800239fe`
- `WS2_32!FreeAddrInfoW` at `0x180023ce2`
- `WS2_32!FreeAddrInfoW` at `0x180023ce2`
- `WS2_32!__imp_WSAGetLastError` at `0x180023a59`
- `WS2_32!__imp_WSAGetLastError` at `0x180023a59`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180023c14`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180023ca9`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180023c14`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180023ca9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023a1c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023abd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023bc2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023c57`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023a1c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023abd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023bc2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023c57`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023af3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023b7b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023af3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023b7b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023c29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023cbf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023c29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023cbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IP_RESTRICTION_LIST::PrivateReverseDNSLookup(STRU **a1)
{
  STRU *v2; // rsi
  socklen_t v3; // edx
  signed int v4; // ebx
  int Error; // eax
  PADDRINFOW v6; // rbx
  __int16 v7; // di
  struct sockaddr *ai_addr; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  signed int *v14; // rax
  PADDRINFOW ppResult; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v16; // [rsp+48h] [rbp-B8h]
  ADDRINFOW pHints; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pNodeBuffer[1032]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(pNodeBuffer, 0, 0x804u);
  memset(&pHints, 0, sizeof(pHints));
  ppResult = 0;
  v2 = *a1;
  if ( *(_WORD *)*a1 == 2 )
  {
    v3 = 16;
  }
  else
  {
    v3 = 0;
    if ( *(_WORD *)v2 == 23 )
      v3 = 28;
  }
  if ( GetNameInfoW((const SOCKADDR *)v2, v3, pNodeBuffer, 0x401u, 0, 0, 4) )
    goto LABEL_9;
  if ( !*((_DWORD *)a1 + 4) )
  {
    v4 = STRU::Copy(a1[1], pNodeBuffer);
    goto LABEL_11;
  }
  pHints.ai_family = *(unsigned __int16 *)v2;
  pHints.ai_socktype = 1;
  pHints.ai_protocol = 6;
  if ( GetAddrInfoW(pNodeBuffer, L"80", &pHints, &ppResult) )
  {
LABEL_9:
    Error = WSAGetLastError();
    v4 = Error;
    if ( Error > 0 )
      v4 = (unsigned __int16)Error | 0x80070000;
LABEL_11:
    if ( v4 < 0 )
      goto LABEL_28;
    goto LABEL_52;
  }
  v6 = ppResult;
  v7 = *(_WORD *)v2;
  while ( 1 )
  {
    ai_addr = v6->ai_addr;
    if ( v7 != ai_addr->sa_family )
      goto LABEL_26;
    if ( v7 != 2 )
      break;
    if ( !memcmp_0((char *)v2 + 4, &ai_addr->sa_data[2], 4u) )
      goto LABEL_17;
LABEL_26:
    v6 = v6->ai_next;
    if ( !v6 )
    {
      v4 = -2147023728;
      goto LABEL_28;
    }
  }
  if ( v7 != 23 )
    goto LABEL_26;
  if ( *((_QWORD *)v2 + 2) != *(_QWORD *)&ai_addr[1].sa_family || *((_QWORD *)v2 + 1) != *(_QWORD *)&ai_addr->sa_data[6] )
    goto LABEL_26;
LABEL_17:
  v4 = STRU::Copy(a1[1], pNodeBuffer);
  if ( v4 < 0 )
    goto LABEL_28;
  v9 = operator new(0xE8u);
  v10 = v9;
  v16 = v9;
  if ( v9 )
  {
    *v9 = 1;
    STRU::STRU(v9 + 1);
    v10[28] = 0;
    *((_OWORD *)v10 + 12) = 0;
    *(_OWORD *)((char *)v10 + 204) = 0;
  }
  else
  {
    v10 = 0;
  }
  if ( v10 )
  {
    *((_DWORD *)v10 + 1) = 0;
    if ( (int)STRU::Copy((STRU *)(v10 + 1), pNodeBuffer) >= 0 )
    {
      if ( *(_WORD *)v2 == 2 )
      {
        *((_OWORD *)v10 + 12) = *(_OWORD *)v2;
      }
      else if ( *(_WORD *)v2 == 23 )
      {
        *((_OWORD *)v10 + 12) = *(_OWORD *)v2;
        *(_OWORD *)((char *)v10 + 204) = *(_OWORD *)((char *)v2 + 12);
      }
      v10[28] = GetTickCount64();
      CLKRHashTable::InsertRecord(IP_RESTRICTION_LIST::sm_pFastDNSLookupTable, v10, 0);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
    {
      STRU::~STRU(v10 + 1);
      operator delete(v10);
    }
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
LABEL_28:
    v12 = operator new(0xE8u);
    v13 = v12;
    v16 = v12;
    if ( v12 )
    {
      *v12 = 1;
      STRU::STRU(v12 + 1);
      v13[28] = 0;
      *((_OWORD *)v13 + 12) = 0;
      *(_OWORD *)((char *)v13 + 204) = 0;
    }
    else
    {
      v13 = 0;
    }
    if ( v13 )
    {
      *((_DWORD *)v13 + 1) = v4;
      if ( (int)STRU::Copy((STRU *)(v13 + 1), &WideCharStr) >= 0 )
      {
        if ( *(_WORD *)v2 == 2 )
        {
          *((_OWORD *)v13 + 12) = *(_OWORD *)v2;
        }
        else if ( *(_WORD *)v2 == 23 )
        {
          *((_OWORD *)v13 + 12) = *(_OWORD *)v2;
          *(_OWORD *)((char *)v13 + 204) = *(_OWORD *)((char *)v2 + 12);
        }
        v13[28] = GetTickCount64();
      }
      CLKRHashTable::InsertRecord(IP_RESTRICTION_LIST::sm_pFastDNSLookupTable, v13, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
      {
        STRU::~STRU(v13 + 1);
        operator delete(v13);
      }
    }
  }
LABEL_52:
  v14 = (signed int *)a1[3];
  if ( v14 )
    *v14 = v4;
  if ( ppResult )
    FreeAddrInfoW(ppResult);
}

```

## disassembly

```asm
0x180023964  push    rbp
0x180023966  push    rbx
0x180023967  push    rsi
0x180023968  push    rdi
0x180023969  push    r14
0x18002396b  push    r15
0x18002396d  lea     rbp, [rsp-7A8h]
0x180023975  sub     rsp, 8A8h
0x18002397c  mov     rax, cs:__security_cookie
0x180023983  xor     rax, rsp
0x180023986  mov     [rbp+7D0h+var_40], rax
0x18002398d  mov     r15, rcx
0x180023990  xor     edx, edx; Val
0x180023992  mov     r8d, 804h; Size
0x180023998  lea     rcx, [rbp+7D0h+pNodeBuffer]; void *
0x18002399c  call    memset_0
0x1800239a1  xorps   xmm0, xmm0
0x1800239a4  movups  xmmword ptr [rsp+8D0h+pHints.ai_flags], xmm0
0x1800239a9  movups  xmmword ptr [rsp+8D0h+pHints.ai_addrlen], xmm0
0x1800239ae  movups  xmmword ptr [rsp+8D0h+pHints.ai_addr], xmm0
0x1800239b3  mov     [rsp+8D0h+ppResult], 0
0x1800239bc  mov     rsi, [r15]
0x1800239bf  cmp     word ptr [rsi], 2
0x1800239c3  jnz     short loc_1800239CC
0x1800239c5  mov     edx, 10h
0x1800239ca  jmp     short loc_1800239D8
0x1800239cc  xor     edx, edx
0x1800239ce  lea     eax, [rdx+1Ch]
0x1800239d1  cmp     word ptr [rsi], 17h
0x1800239d5  cmovz   edx, eax; SockaddrLength
0x1800239d8  mov     [rsp+8D0h+Flags], 4; Flags
0x1800239e0  mov     [rsp+8D0h+ServiceBufferSize], 0; ServiceBufferSize
0x1800239e8  mov     [rsp+8D0h+pServiceBuffer], 0; pServiceBuffer
0x1800239f1  mov     r9d, 401h; NodeBufferSize
0x1800239f7  lea     r8, [rbp+7D0h+pNodeBuffer]; pNodeBuffer
0x1800239fb  mov     rcx, rsi; pSockaddr
0x1800239fe  call    cs:__imp_GetNameInfoW
0x180023a04  mov     r14d, 1
0x180023a0a  test    eax, eax
0x180023a0c  jnz     short loc_180023A59
0x180023a0e  cmp     [r15+10h], eax
0x180023a12  jnz     short loc_180023A26
0x180023a14  lea     rdx, [rbp+7D0h+pNodeBuffer]
0x180023a18  mov     rcx, [r15+8]
0x180023a1c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180023a22  mov     ebx, eax
0x180023a24  jmp     short loc_180023A6E
0x180023a26  movzx   eax, word ptr [rsi]
0x180023a29  mov     [rsp+8D0h+pHints.ai_family], eax
0x180023a2d  mov     [rsp+8D0h+pHints.ai_socktype], r14d
0x180023a32  mov     [rsp+8D0h+pHints.ai_protocol], 6
0x180023a3a  lea     r9, [rsp+8D0h+ppResult]; ppResult
0x180023a3f  lea     r8, [rsp+8D0h+pHints]; pHints
0x180023a44  lea     rdx, pServiceName; "80"
0x180023a4b  lea     rcx, [rbp+7D0h+pNodeBuffer]; pNodeName
0x180023a4f  call    cs:__imp_GetAddrInfoW
0x180023a55  test    eax, eax
0x180023a57  jz      short loc_180023A7B
0x180023a59  call    cs:__imp_WSAGetLastError
0x180023a5f  test    eax, eax
0x180023a61  mov     ebx, eax
0x180023a63  jle     short loc_180023A6E
0x180023a65  movzx   ebx, ax
0x180023a68  or      ebx, 80070000h
0x180023a6e  test    ebx, ebx
0x180023a70  jns     loc_180023CCD
0x180023a76  jmp     loc_180023B55
0x180023a7b  mov     rbx, [rsp+8D0h+ppResult]
0x180023a80  movzx   edi, word ptr [rsi]
0x180023a83  mov     rcx, [rbx+20h]
0x180023a87  cmp     di, [rcx]
0x180023a8a  jnz     loc_180023B43
0x180023a90  cmp     di, 2
0x180023a94  jnz     loc_180023B1A
0x180023a9a  lea     rdx, [rcx+4]; Buf2
0x180023a9e  lea     rcx, [rsi+4]; Buf1
0x180023aa2  mov     r8d, 4; Size
0x180023aa8  call    memcmp_0
0x180023aad  test    eax, eax
0x180023aaf  jnz     loc_180023B43
0x180023ab5  lea     rdx, [rbp+7D0h+pNodeBuffer]
0x180023ab9  mov     rcx, [r15+8]
0x180023abd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180023ac3  mov     ebx, eax
0x180023ac5  test    eax, eax
0x180023ac7  js      loc_180023B55
0x180023acd  mov     ecx, 0E8h; Size
0x180023ad2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023ad7  mov     rbx, rax
0x180023ada  mov     [rsp+8D0h+var_888], rax
0x180023adf  test    rax, rax
0x180023ae2  jz      loc_180023BA2
0x180023ae8  mov     qword ptr [rax], 1
0x180023aef  lea     rcx, [rax+8]
0x180023af3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180023af9  mov     qword ptr [rbx+0E0h], 0
0x180023b04  xorps   xmm0, xmm0
0x180023b07  movups  xmmword ptr [rbx+0C0h], xmm0
0x180023b0e  movups  xmmword ptr [rbx+0CCh], xmm0
0x180023b15  jmp     loc_180023BA4
0x180023b1a  cmp     di, 17h
0x180023b1e  jnz     short loc_180023B43
0x180023b20  mov     rax, [rcx+10h]
0x180023b24  cmp     [rsi+10h], rax
0x180023b28  jnz     short loc_180023B39
0x180023b2a  mov     rax, [rcx+8]
0x180023b2e  cmp     [rsi+8], rax
0x180023b32  jnz     short loc_180023B39
0x180023b34  mov     al, r14b
0x180023b37  jmp     short loc_180023B3B
0x180023b39  xor     al, al
0x180023b3b  test    al, al
0x180023b3d  jnz     loc_180023AB5
0x180023b43  mov     rbx, [rbx+28h]
0x180023b47  test    rbx, rbx
0x180023b4a  jnz     loc_180023A83
0x180023b50  mov     ebx, 80070490h
0x180023b55  mov     ecx, 0E8h; Size
0x180023b5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023b5f  mov     rdi, rax
0x180023b62  mov     [rsp+8D0h+var_888], rax
0x180023b67  test    rax, rax
0x180023b6a  jz      loc_180023C3E
0x180023b70  mov     qword ptr [rax], 1
0x180023b77  lea     rcx, [rax+8]
0x180023b7b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180023b81  mov     qword ptr [rdi+0E0h], 0
0x180023b8c  xorps   xmm0, xmm0
0x180023b8f  movups  xmmword ptr [rdi+0C0h], xmm0
0x180023b96  movups  xmmword ptr [rdi+0CCh], xmm0
0x180023b9d  jmp     loc_180023C40
0x180023ba2  xor     ebx, ebx
0x180023ba4  test    rbx, rbx
0x180023ba7  jnz     short loc_180023BB0
0x180023ba9  mov     ebx, 8007000Eh
0x180023bae  jmp     short loc_180023B55
0x180023bb0  mov     dword ptr [rbx+4], 0
0x180023bb7  lea     rdi, [rbx+8]
0x180023bbb  lea     rdx, [rbp+7D0h+pNodeBuffer]
0x180023bbf  mov     rcx, rdi
0x180023bc2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180023bc8  test    eax, eax
0x180023bca  js      short loc_180023C1A
0x180023bcc  cmp     word ptr [rsi], 2
0x180023bd0  jnz     short loc_180023BDF
0x180023bd2  movups  xmm0, xmmword ptr [rsi]
0x180023bd5  movdqu  xmmword ptr [rbx+0C0h], xmm0
0x180023bdd  jmp     short loc_180023BFA
0x180023bdf  cmp     word ptr [rsi], 17h
0x180023be3  jnz     short loc_180023BFA
0x180023be5  movups  xmm0, xmmword ptr [rsi]
0x180023be8  movups  xmmword ptr [rbx+0C0h], xmm0
0x180023bef  movups  xmm1, xmmword ptr [rsi+0Ch]
0x180023bf3  movups  xmmword ptr [rbx+0CCh], xmm1
0x180023bfa  call    cs:__imp_GetTickCount64
0x180023c00  mov     [rbx+0E0h], rax
0x180023c07  xor     r8d, r8d
0x180023c0a  mov     rdx, rbx
0x180023c0d  mov     rcx, cs:?sm_pFastDNSLookupTable@IP_RESTRICTION_LIST@@0PEAVFAST_DNS_LOOKUP_HASH@@EA; FAST_DNS_LOOKUP_HASH * IP_RESTRICTION_LIST::sm_pFastDNSLookupTable
0x180023c14  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180023c1a  or      eax, 0FFFFFFFFh
0x180023c1d  lock xadd [rbx], eax
0x180023c21  cmp     eax, 1
0x180023c24  jnz     short loc_180023C37
0x180023c26  mov     rcx, rdi
0x180023c29  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180023c2f  mov     rcx, rbx; Block
0x180023c32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023c37  xor     ebx, ebx
0x180023c39  jmp     loc_180023CCD
0x180023c3e  xor     edi, edi
0x180023c40  test    rdi, rdi
0x180023c43  jz      loc_180023CCD
0x180023c49  mov     [rdi+4], ebx
0x180023c4c  lea     rdx, WideCharStr
0x180023c53  lea     rcx, [rdi+8]
0x180023c57  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180023c5d  test    eax, eax
0x180023c5f  js      short loc_180023C9C
0x180023c61  cmp     word ptr [rsi], 2
0x180023c65  jnz     short loc_180023C74
0x180023c67  movups  xmm0, xmmword ptr [rsi]
0x180023c6a  movdqu  xmmword ptr [rdi+0C0h], xmm0
0x180023c72  jmp     short loc_180023C8F
0x180023c74  cmp     word ptr [rsi], 17h
0x180023c78  jnz     short loc_180023C8F
0x180023c7a  movups  xmm0, xmmword ptr [rsi]
0x180023c7d  movups  xmmword ptr [rdi+0C0h], xmm0
0x180023c84  movups  xmm1, xmmword ptr [rsi+0Ch]
0x180023c88  movups  xmmword ptr [rdi+0CCh], xmm1
0x180023c8f  call    cs:__imp_GetTickCount64
0x180023c95  mov     [rdi+0E0h], rax
0x180023c9c  xor     r8d, r8d
0x180023c9f  mov     rdx, rdi
0x180023ca2  mov     rcx, cs:?sm_pFastDNSLookupTable@IP_RESTRICTION_LIST@@0PEAVFAST_DNS_LOOKUP_HASH@@EA; FAST_DNS_LOOKUP_HASH * IP_RESTRICTION_LIST::sm_pFastDNSLookupTable
0x180023ca9  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180023caf  or      eax, 0FFFFFFFFh
0x180023cb2  lock xadd [rdi], eax
0x180023cb6  cmp     eax, 1
0x180023cb9  jnz     short loc_180023CCD
0x180023cbb  lea     rcx, [rdi+8]
0x180023cbf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180023cc5  mov     rcx, rdi; Block
0x180023cc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023ccd  mov     rax, [r15+18h]
0x180023cd1  test    rax, rax
0x180023cd4  jz      short loc_180023CD8
0x180023cd6  mov     [rax], ebx
0x180023cd8  mov     rcx, [rsp+8D0h+ppResult]; pAddrInfo
0x180023cdd  test    rcx, rcx
0x180023ce0  jz      short loc_180023CE8
0x180023ce2  call    cs:__imp_FreeAddrInfoW
0x180023ce8  mov     rcx, [rbp+7D0h+var_40]
0x180023cef  xor     rcx, rsp; StackCookie
0x180023cf2  call    __security_check_cookie
0x180023cf7  add     rsp, 8A8h
0x180023cfe  pop     r15
0x180023d00  pop     r14
0x180023d02  pop     rdi
0x180023d03  pop     rsi
0x180023d04  pop     rbx
0x180023d05  pop     rbp
0x180023d06  retn
```
