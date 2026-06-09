# NlDnsUpdate(_NL_DNS_NAME *,uchar)

- ea: `0x180023b54`
- end: `0x180024099`
- name: `?NlDnsUpdate@@YAKPEAU_NL_DNS_NAME@@E@Z`
- size: `1349`
- prototype: `unsigned int __fastcall(struct _NL_DNS_NAME *, unsigned __int8)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800213d8`
- `0x1800229dc`

## callees

- `0x18000e910`
- `0x18000f3e4`
- `0x18000f4a4`
- `0x180021db0`
- `0x1800220f8`
- `0x180023b54`
- `0x180029c68`
- `0x180041f80`
- `0x180041fbc`
- `0x180089228`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180023ea0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180023ea0`
- `netutils!NetApiBufferFree` at `0x180023fbf`
- `netutils!NetApiBufferFree` at `0x18002405c`
- `netutils!NetApiBufferFree` at `0x180023fbf`
- `netutils!NetApiBufferFree` at `0x18002405c`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x180023d9a`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x180023d9a`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180023dce`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180023dce`
- `WS2_32!GetNameInfoW` at `0x180023e7f`
- `WS2_32!GetNameInfoW` at `0x180023e7f`

## pseudocode

```c
DNS_STATUS __fastcall NlDnsUpdate(struct _NL_DNS_NAME *a1, char a2)
{
  DNS_STATUS result; // eax
  int v5; // r14d
  __int64 v6; // r9
  __int16 v7; // dx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  DWORD v11; // eax
  unsigned int v12; // ecx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  unsigned __int8 v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD pReserved[7]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v17[2]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+78h] [rbp-88h]
  DNS_RECORDA pReplaceSet; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pSockaddr[24]; // [rsp+110h] [rbp+10h] BYREF
  int v22; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v23[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v24; // [rsp+140h] [rbp+40h]
  wchar_t *v25; // [rsp+150h] [rbp+50h]
  wchar_t Buffer[16]; // [rsp+158h] [rbp+58h] BYREF
  wchar_t v27[20]; // [rsp+178h] [rbp+78h] BYREF
  WCHAR pNodeBuffer[72]; // [rsp+1A0h] [rbp+A0h] BYREF

  *(_DWORD *)v15 = 0;
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  v25 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  memset_0(pReserved, 0, 0x60u);
  wcscpy(Buffer, L"<UNAILABLE>");
  wcscpy(v27, L"<UNAILABLE>");
  if ( !(unsigned int)GiveInstallHints(0) )
    return 9851;
  if ( !dword_1800F8250 )
  {
    result = 9004;
    *(_DWORD *)v15 = 9004;
    if ( NlGlobalNoDynamicDnsLogged )
      return result;
    NlpWriteEventlog(0x16AEu, 2u, 0, 0, 0, 0, 0);
    NlGlobalNoDynamicDnsLogged = 1;
    return *(_DWORD *)v15;
  }
  NlGlobalNoDynamicDnsLogged = 0;
  v5 = 0;
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  v6 = 32LL * *((int *)a1 + 4);
  pReplaceSet.pName = (PSTR)*((_QWORD *)a1 + 8);
  pReplaceSet.dwTtl = dword_1800F8158;
  v7 = *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v6 + 24);
  if ( v7 != 1 )
  {
    v9 = *((_QWORD *)a1 + 11);
    pReplaceSet.Data.AAAA.Ip6Address.IP6Dword[1] = HIDWORD(v9);
    if ( v7 == 5 )
    {
      *(_DWORD *)&pReplaceSet.wType = 524293;
    }
    else
    {
      pReplaceSet.Data.MX.wPreference = *((_WORD *)a1 + 38);
      pReplaceSet.Data.MX.Pad = *((_WORD *)a1 + 40);
      pReplaceSet.Data.AAAA.Ip6Address.IP6Word[6] = *((_WORD *)a1 + 42);
      *(_DWORD *)&pReplaceSet.wType = 1048609;
    }
    goto LABEL_15;
  }
  if ( *((_WORD *)a1 + 56) == 2 )
  {
    v8 = *((_QWORD *)a1 + 12);
    *(_DWORD *)&pReplaceSet.wType = 262145;
    LODWORD(v9) = *(_DWORD *)(v8 + 4);
LABEL_15:
    pReplaceSet.Data.A.IpAddress = v9;
    goto LABEL_16;
  }
  if ( *((_WORD *)a1 + 56) == 23 )
  {
    v10 = *((_QWORD *)a1 + 12);
    *(_DWORD *)&pReplaceSet.wType = 1048604;
    *(_OWORD *)&pReplaceSet.Data.A.IpAddress = *(_OWORD *)(v10 + 8);
  }
LABEL_16:
  pReserved[0] = -2147483647;
  if ( !dword_1800F8264 )
    v5 = 0x2000;
  pReserved[4] = 1;
  v11 = v5 | 0x4000;
  if ( v7 != 5 )
    v11 = v5;
  if ( a2 )
  {
    if ( v7 == 5 || *(_DWORD *)((char *)&NlDcDnsNameTypeDesc + v6 + 20) == 1 )
      result = DnsReplaceRecordSetUTF8(&pReplaceSet, v11, 0, 0, pReserved);
    else
      result = DnsModifyRecordsInSet_UTF8(&pReplaceSet, 0, v11, 0, 0, pReserved);
  }
  else
  {
    if ( NlGlobalDcDemotionInProgress )
      v11 |= 0x4000u;
    result = DnsModifyRecordsInSet_UTF8(0, &pReplaceSet, v11, 0, 0, pReserved);
  }
  *(_DWORD *)v15 = result;
  if ( result )
  {
    if ( result == 1460 || result == 9002 )
    {
      if ( NlDnsWriteServerFailureEventLog )
      {
        *((_DWORD *)a1 + 61) = result;
        v13 = NlDnsNameToDomainName(a1);
        v14 = v13;
        if ( v13 )
        {
          v23[0] = v13;
          NlpWriteEventlog(0x1695u, 2u, 0, v23, 1u, v15, 4u);
          NetApiBufferFree(v14);
        }
      }
      return 9002;
    }
    else
    {
      if ( result == 9851 || result == 9852 || result == 10047 )
      {
        *((_DWORD *)a1 + 61) = result;
        v23[0] = (unsigned __int16 *)(unsigned int)result;
        NlpWriteEventlog(0x1696u, 2u, 0x40000000u, v23, 1u, v15, 4u);
        return 9851;
      }
      v12 = v18;
      *((_DWORD *)a1 + 61) = result;
      if ( v12 )
      {
        NetpIpAddressToWStr(v12, pNodeBuffer);
      }
      else
      {
        *(_DWORD *)&pSockaddr[2] = 0;
        *(_WORD *)&pSockaddr[6] = 0;
        v22 = 0;
        *(_WORD *)pSockaddr = 23;
        *(_OWORD *)&pSockaddr[8] = v19;
        if ( GetNameInfoW((const SOCKADDR *)pSockaddr, 28, pNodeBuffer, 0x42u, 0, 0, 2) )
          _o_wcscpy_s(pNodeBuffer, 66, L"<UNAVAILABLE>");
      }
      swprintf_s(Buffer, 0xEu, L"%lu", *(unsigned __int16 *)v17);
      swprintf_s(v27, 0xEu, L"%lu", pReserved[6]);
      result = *(_DWORD *)v15;
      if ( *(_DWORD *)v15 == 9004 )
      {
        v23[0] = pNodeBuffer;
        v23[1] = Buffer;
        *(_QWORD *)&v24 = v27;
        NlpWriteEventlog(0x168Du, 2u, 0, v23, 3u, v17, 2u);
        return 9004;
      }
      else if ( !*((_DWORD *)a1 + 18) )
      {
        v23[0] = NlDnsNameToWStr(a1, dword_1800F8158);
        if ( v23[0] )
        {
          v23[1] = (unsigned __int16 *)*(unsigned int *)v15;
          *(_QWORD *)&v24 = pNodeBuffer;
          *((_QWORD *)&v24 + 1) = Buffer;
          v25 = v27;
          NlpWriteEventlogEx(5775 - (a2 != 0), 1u, 0x40000000u, 1u, v23, 5u, v17, 2u);
          NetApiBufferFree(v23[0]);
        }
        return *(_DWORD *)v15;
      }
    }
  }
  else
  {
    *((_DWORD *)a1 + 61) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180023b54  push    rbp
0x180023b56  push    rbx
0x180023b57  push    rsi
0x180023b58  push    rdi
0x180023b59  push    r12
0x180023b5b  push    r13
0x180023b5d  push    r14
0x180023b5f  push    r15
0x180023b61  lea     rbp, [rsp-148h]
0x180023b69  sub     rsp, 248h
0x180023b70  mov     rax, cs:__security_cookie
0x180023b77  xor     rax, rsp
0x180023b7a  mov     [rbp+180h+var_50], rax
0x180023b81  xor     r12d, r12d
0x180023b84  mov     r15b, dl
0x180023b87  mov     rbx, rcx
0x180023b8a  mov     dword ptr [rsp+280h+var_240], r12d
0x180023b8f  xor     edx, edx; Val
0x180023b91  lea     rcx, [rbp+180h+pReplaceSet]; void *
0x180023b95  lea     edi, [r12+58h]
0x180023b9a  mov     r8d, edi; Size
0x180023b9d  call    memset_0
0x180023ba2  xorps   xmm0, xmm0
0x180023ba5  lea     r8d, [r12+60h]; Size
0x180023baa  xor     eax, eax
0x180023bac  lea     rcx, [rsp+280h+var_230]; void *
0x180023bb1  xor     edx, edx; Val
0x180023bb3  mov     [rbp+180h+var_130], rax
0x180023bb7  movups  xmmword ptr [rbp+180h+var_150], xmm0
0x180023bbb  movups  [rbp+180h+var_140], xmm0
0x180023bbf  call    memset_0
0x180023bc4  movups  xmm1, xmmword ptr cs:aUnavailable
0x180023bcb  xor     ecx, ecx; int
0x180023bcd  movups  xmm0, xmmword ptr cs:aUnavailable+0Ch
0x180023bd4  movups  xmmword ptr [rbp+180h+Buffer], xmm1
0x180023bd8  movups  xmmword ptr [rbp+180h+var_108], xmm1
0x180023bdc  movups  xmmword ptr [rbp+180h+Buffer+0Ch], xmm0
0x180023be0  movups  xmmword ptr [rbp+180h+var_108+0Ch], xmm0
0x180023be7  call    ?GiveInstallHints@@YAHH@Z
0x180023bec  test    eax, eax
0x180023bee  jnz     short loc_180023BFA
0x180023bf0  mov     eax, 267Bh
0x180023bf5  jmp     loc_180024075
0x180023bfa  cmp     cs:dword_1800F8250, r12d
0x180023c01  jnz     short loc_180023C50
0x180023c03  cmp     cs:?NlGlobalNoDynamicDnsLogged@@3HA, r12d
0x180023c0a  mov     eax, 232Ch
0x180023c0f  mov     dword ptr [rsp+280h+var_240], eax
0x180023c13  jnz     loc_180024075
0x180023c19  xor     r9d, r9d; unsigned __int16 **
0x180023c1c  mov     [rsp+280h+Flags], r12d; unsigned int
0x180023c21  mov     [rsp+280h+var_258], r12; unsigned __int8 *
0x180023c26  xor     r8d, r8d; unsigned int
0x180023c29  mov     ecx, 16AEh; unsigned int
0x180023c2e  mov     dword ptr [rsp+280h+pReserved], r12d; unsigned int
0x180023c33  lea     edx, [r9+2]; unsigned int
0x180023c37  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z
0x180023c3c  mov     esi, 1
0x180023c41  mov     cs:?NlGlobalNoDynamicDnsLogged@@3HA, esi
0x180023c47  mov     eax, dword ptr [rsp+280h+var_240]
0x180023c4b  jmp     loc_180024075
0x180023c50  mov     r8, rdi; Size
0x180023c53  mov     cs:?NlGlobalNoDynamicDnsLogged@@3HA, r12d
0x180023c5a  xor     edx, edx; Val
0x180023c5c  lea     rcx, [rbp+180h+pReplaceSet]; void *
0x180023c60  mov     r14d, r12d
0x180023c63  call    memset_0
0x180023c68  mov     rax, [rbx+40h]
0x180023c6c  lea     r10, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A
0x180023c73  movsxd  r9, dword ptr [rbx+10h]
0x180023c77  mov     edi, 2
0x180023c7c  shl     r9, 5
0x180023c80  mov     [rbp+180h+pReplaceSet.pName], rax
0x180023c84  mov     eax, cs:dword_1800F8158
0x180023c8a  lea     esi, [rdi-1]
0x180023c8d  mov     [rbp+180h+pReplaceSet.dwTtl], eax
0x180023c90  movzx   edx, word ptr [r9+r10+18h]
0x180023c96  lea     ecx, [rdi+15h]
0x180023c99  lea     r13d, [rdi+3]
0x180023c9d  cmp     dx, si
0x180023ca0  jnz     short loc_180023CF3
0x180023ca2  cmp     [rbx+70h], di
0x180023ca6  jnz     short loc_180023CB8
0x180023ca8  mov     rax, [rbx+60h]
0x180023cac  mov     dword ptr [rbp+180h+pReplaceSet.wType], 40001h
0x180023cb3  mov     ecx, [rax+4]
0x180023cb6  jmp     short loc_180023D2F
0x180023cb8  cmp     [rbx+70h], cx
0x180023cbc  jnz     short loc_180023D32
0x180023cbe  mov     rcx, [rbx+60h]
0x180023cc2  mov     dword ptr [rbp+180h+pReplaceSet.wType], 10001Ch
0x180023cc9  mov     rax, [rcx+8]
0x180023ccd  mov     qword ptr [rbp+180h+pReplaceSet.Data], rax
0x180023cd1  movzx   eax, word ptr [rcx+10h]
0x180023cd5  mov     word ptr [rbp+180h+pReplaceSet.Data+8], ax
0x180023cd9  movzx   eax, word ptr [rcx+12h]
0x180023cdd  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ah], ax
0x180023ce1  movzx   eax, word ptr [rcx+14h]
0x180023ce5  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ch], ax
0x180023ce9  movzx   eax, word ptr [rcx+16h]
0x180023ced  mov     word ptr [rbp+180h+pReplaceSet.Data+0Eh], ax
0x180023cf1  jmp     short loc_180023D32
0x180023cf3  mov     rcx, [rbx+58h]
0x180023cf7  mov     rax, rcx
0x180023cfa  sar     rax, 20h
0x180023cfe  mov     dword ptr [rbp+180h+pReplaceSet.Data+4], eax
0x180023d01  cmp     dx, r13w
0x180023d05  jnz     short loc_180023D10
0x180023d07  mov     dword ptr [rbp+180h+pReplaceSet.wType], 80005h
0x180023d0e  jmp     short loc_180023D2F
0x180023d10  movzx   eax, word ptr [rbx+4Ch]
0x180023d14  mov     word ptr [rbp+180h+pReplaceSet.Data+8], ax
0x180023d18  movzx   eax, word ptr [rbx+50h]
0x180023d1c  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ah], ax
0x180023d20  movzx   eax, word ptr [rbx+54h]
0x180023d24  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ch], ax
0x180023d28  mov     dword ptr [rbp+180h+pReplaceSet.wType], 100021h
0x180023d2f  mov     dword ptr [rbp+180h+pReplaceSet.Data], ecx
0x180023d32  cmp     cs:dword_1800F8264, r12d
0x180023d39  mov     eax, 2000h
0x180023d3e  mov     ecx, 4000h
0x180023d43  mov     [rsp+280h+var_230], 80000001h
0x180023d4b  cmovz   r14d, eax
0x180023d4f  mov     [rsp+280h+var_220], esi
0x180023d53  mov     eax, r14d
0x180023d56  or      eax, ecx
0x180023d58  cmp     dx, r13w
0x180023d5c  cmovnz  eax, r14d
0x180023d60  test    r15b, r15b
0x180023d63  jz      short loc_180023DA8
0x180023d65  cmp     dx, r13w
0x180023d69  jz      short loc_180023D84
0x180023d6b  cmp     [r9+r10+14h], esi
0x180023d70  jz      short loc_180023D84
0x180023d72  lea     rcx, [rsp+280h+var_230]
0x180023d77  xor     edx, edx
0x180023d79  mov     [rsp+280h+var_258], rcx
0x180023d7e  lea     rcx, [rbp+180h+pReplaceSet]
0x180023d82  jmp     short loc_180023DC3
0x180023d84  lea     rcx, [rsp+280h+var_230]
0x180023d89  xor     r9d, r9d; pExtraInfo
0x180023d8c  mov     [rsp+280h+pReserved], rcx; pReserved
0x180023d91  xor     r8d, r8d; hContext
0x180023d94  lea     rcx, [rbp+180h+pReplaceSet]; pReplaceSet
0x180023d98  mov     edx, eax; Options
0x180023d9a  call    cs:__imp_DnsReplaceRecordSetUTF8
0x180023da1  nop     dword ptr [rax+rax+00h]
0x180023da6  jmp     short loc_180023DDA
0x180023da8  cmp     cs:?NlGlobalDcDemotionInProgress@@3EA, r12b
0x180023daf  jz      short loc_180023DB3
0x180023db1  or      eax, ecx
0x180023db3  lea     rcx, [rsp+280h+var_230]
0x180023db8  mov     [rsp+280h+var_258], rcx; pReserved
0x180023dbd  lea     rdx, [rbp+180h+pReplaceSet]; pDeleteRecords
0x180023dc1  xor     ecx, ecx; pAddRecords
0x180023dc3  xor     r9d, r9d; hCredentials
0x180023dc6  mov     [rsp+280h+pReserved], r12; pExtraList
0x180023dcb  mov     r8d, eax; Options
0x180023dce  call    cs:__imp_DnsModifyRecordsInSet_UTF8
0x180023dd5  nop     dword ptr [rax+rax+00h]
0x180023dda  mov     dword ptr [rsp+280h+var_240], eax
0x180023dde  mov     ecx, eax
0x180023de0  test    eax, eax
0x180023de2  jz      loc_18002406F
0x180023de8  sub     ecx, 5B4h
0x180023dee  jz      loc_18002400D
0x180023df4  sub     ecx, 1D76h
0x180023dfa  jz      loc_18002400D
0x180023e00  sub     ecx, 351h
0x180023e06  jz      loc_180023FD0
0x180023e0c  sub     ecx, esi
0x180023e0e  jz      loc_180023FD0
0x180023e14  cmp     ecx, 0C3h
0x180023e1a  jz      loc_180023FD0
0x180023e20  mov     ecx, [rsp+280h+var_210]; unsigned int
0x180023e24  mov     [rbx+0F4h], eax
0x180023e2a  test    ecx, ecx
0x180023e2c  jz      short loc_180023E3C
0x180023e2e  lea     rdx, [rbp+180h+pNodeBuffer]; unsigned __int16 *
0x180023e35  call    ?NetpIpAddressToWStr@@YAXKQEAG@Z
0x180023e3a  jmp     short loc_180023EAC
0x180023e3c  movups  xmm0, [rsp+280h+var_208]
0x180023e41  mov     eax, 17h
0x180023e46  mov     [rsp+280h+Flags], edi; Flags
0x180023e4a  mov     dword ptr [rsp+280h+var_258], r12d; ServiceBufferSize
0x180023e4f  lea     r8, [rbp+180h+pNodeBuffer]; pNodeBuffer
0x180023e56  lea     rcx, [rbp+180h+pSockaddr]; pSockaddr
0x180023e5a  mov     dword ptr [rbp+180h+pSockaddr+2], r12d
0x180023e5e  mov     word ptr [rbp+180h+pSockaddr+6], r12w
0x180023e63  lea     r14d, [rax+2Bh]
0x180023e67  mov     [rbp+180h+var_158], r12d
0x180023e6b  mov     r9d, r14d; NodeBufferSize
0x180023e6e  mov     word ptr [rbp+180h+pSockaddr], ax
0x180023e72  lea     edx, [rax+5]; SockaddrLength
0x180023e75  mov     [rsp+280h+pReserved], r12; pServiceBuffer
0x180023e7a  movdqu  xmmword ptr [rbp+180h+pSockaddr+8], xmm0
0x180023e7f  call    cs:__imp_GetNameInfoW
0x180023e86  nop     dword ptr [rax+rax+00h]
0x180023e8b  test    eax, eax
0x180023e8d  jz      short loc_180023EAC
0x180023e8f  lea     r8, aUnavailable
0x180023e96  mov     edx, r14d
0x180023e99  lea     rcx, [rbp+180h+pNodeBuffer]
0x180023ea0  call    cs:__imp__o_wcscpy_s
0x180023ea7  nop     dword ptr [rax+rax+00h]
0x180023eac  movzx   r9d, word ptr [rsp+280h+var_214]
0x180023eb2  lea     r8, aLu_0
0x180023eb9  mov     r14d, 0Eh
0x180023ebf  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180023ec3  mov     edx, r14d; BufferCount
0x180023ec6  call    swprintf_s
0x180023ecb  mov     r9d, [rsp+280h+var_218]
0x180023ed0  lea     r8, aLu_0
0x180023ed7  mov     edx, r14d; BufferCount
0x180023eda  lea     rcx, [rbp+180h+var_108]; Buffer
0x180023ede  call    swprintf_s
0x180023ee3  mov     eax, dword ptr [rsp+280h+var_240]
0x180023ee7  cmp     eax, 232Ch
0x180023eec  jnz     short loc_180023F3C
0x180023eee  lea     rax, [rbp+180h+pNodeBuffer]
0x180023ef5  mov     [rsp+280h+Flags], edi; unsigned int
0x180023ef9  mov     [rbp+180h+var_150], rax
0x180023efd  lea     r9, [rbp+180h+var_150]; unsigned __int16 **
0x180023f01  lea     rax, [rbp+180h+Buffer]
0x180023f05  xor     r8d, r8d; unsigned int
0x180023f08  mov     [rbp+180h+var_150+8], rax
0x180023f0c  mov     edx, edi; unsigned int
0x180023f0e  lea     rax, [rbp+180h+var_108]
0x180023f12  mov     ecx, 168Dh; unsigned int
0x180023f17  mov     qword ptr [rbp+180h+var_140], rax
0x180023f1b  lea     rax, [rsp+280h+var_214]
0x180023f20  mov     [rsp+280h+var_258], rax; unsigned __int8 *
0x180023f25  mov     dword ptr [rsp+280h+pReserved], 3; unsigned int
0x180023f2d  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z
0x180023f32  mov     eax, 232Ch
0x180023f37  jmp     loc_180024075
0x180023f3c  cmp     [rbx+48h], r12d
0x180023f40  jnz     loc_180024075
0x180023f46  mov     edx, cs:dword_1800F8158; unsigned int
0x180023f4c  mov     rcx, rbx; struct _NL_DNS_NAME *
0x180023f4f  call    ?NlDnsNameToWStr@@YAPEAGPEAU_NL_DNS_NAME@@K@Z
0x180023f54  mov     [rbp+180h+var_150], rax
0x180023f58  test    rax, rax
0x180023f5b  jz      loc_180023C47
0x180023f61  mov     eax, dword ptr [rsp+280h+var_240]
0x180023f65  neg     r15b
0x180023f68  mov     [rbp+180h+var_150+8], rax
0x180023f6c  mov     r9d, esi; unsigned int
0x180023f6f  mov     [rsp+280h+var_248], edi; unsigned int
0x180023f73  lea     rax, [rbp+180h+pNodeBuffer]
0x180023f7a  mov     qword ptr [rbp+180h+var_140], rax
0x180023f7e  sbb     ecx, ecx
0x180023f80  lea     rax, [rbp+180h+Buffer]
0x180023f84  add     ecx, 168Fh; unsigned int
0x180023f8a  mov     qword ptr [rbp+180h+var_140+8], rax
0x180023f8e  mov     r8d, 40000000h; unsigned int
0x180023f94  lea     rax, [rbp+180h+var_108]
0x180023f98  mov     edx, esi; unsigned int
0x180023f9a  mov     [rbp+180h+var_130], rax
0x180023f9e  lea     rax, [rsp+280h+var_214]
0x180023fa3  mov     qword ptr [rsp+280h+Flags], rax; unsigned __int8 *
0x180023fa8  lea     rax, [rbp+180h+var_150]
0x180023fac  mov     dword ptr [rsp+280h+var_258], r13d; unsigned int
0x180023fb1  mov     [rsp+280h+pReserved], rax; unsigned __int16 **
0x180023fb6  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z
0x180023fbb  mov     rcx, [rbp+180h+var_150]; Buffer
0x180023fbf  call    cs:__imp_NetApiBufferFree
0x180023fc6  nop     dword ptr [rax+rax+00h]
0x180023fcb  jmp     loc_180023C47
0x180023fd0  mov     [rbx+0F4h], eax
0x180023fd6  lea     r9, [rbp+180h+var_150]; unsigned __int16 **
0x180023fda  mov     eax, eax
0x180023fdc  mov     r8d, 40000000h; unsigned int
0x180023fe2  mov     [rbp+180h+var_150], rax
0x180023fe6  mov     edx, edi; unsigned int
0x180023fe8  lea     rax, [rsp+280h+var_240]
0x180023fed  mov     [rsp+280h+Flags], 4; unsigned int
0x180023ff5  mov     [rsp+280h+var_258], rax; unsigned __int8 *
0x180023ffa  mov     ecx, 1696h; unsigned int
0x180023fff  mov     dword ptr [rsp+280h+pReserved], esi; unsigned int
0x180024003  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z
0x180024008  jmp     loc_180023BF0
0x18002400d  cmp     cs:?NlDnsWriteServerFailureEventLog@@3HA, r12d
0x180024014  jz      short loc_180024068
0x180024016  mov     rcx, rbx; struct _NL_DNS_NAME *
0x180024019  mov     [rbx+0F4h], eax
0x18002401f  call    ?NlDnsNameToDomainName@@YAPEAGPEAU_NL_DNS_NAME@@@Z
0x180024024  mov     rbx, rax
0x180024027  test    rax, rax
0x18002402a  jz      short loc_180024068
0x18002402c  mov     [rbp+180h+var_150], rax
0x180024030  lea     r9, [rbp+180h+var_150]; unsigned __int16 **
0x180024034  lea     rax, [rsp+280h+var_240]
0x180024039  mov     [rsp+280h+Flags], 4; unsigned int
0x180024041  mov     [rsp+280h+var_258], rax; unsigned __int8 *
0x180024046  xor     r8d, r8d; unsigned int
0x180024049  mov     edx, edi; unsigned int
0x18002404b  mov     dword ptr [rsp+280h+pReserved], esi; unsigned int
0x18002404f  mov     ecx, 1695h; unsigned int
0x180024054  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z
  ... truncated ...
```
