# NlDnsUpdate(_NL_DNS_NAME *,uchar)

- ea: `0x1800229ec`
- end: `0x18002300e`
- name: `?NlDnsUpdate@@YAKPEAU_NL_DNS_NAME@@E@Z`
- size: `1570`
- prototype: `unsigned int __fastcall(struct _NL_DNS_NAME *, unsigned __int8)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800204e8`
- `0x18002197c`

## callees

- `0x18000e270`
- `0x18000ed34`
- `0x18000edf4`
- `0x180020e38`
- `0x18002110c`
- `0x1800229ec`
- `0x180024aa0`
- `0x180028750`
- `0x18003f684`
- `0x180083094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180022df1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180022df1`
- `netutils!NetApiBufferFree` at `0x180022f2c`
- `netutils!NetApiBufferFree` at `0x180022fd7`
- `netutils!NetApiBufferFree` at `0x180022f2c`
- `netutils!NetApiBufferFree` at `0x180022fd7`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x180022cda`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x180022cda`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180022d0a`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180022d0a`
- `WS2_32!GetNameInfoW` at `0x180022dd7`
- `WS2_32!GetNameInfoW` at `0x180022dd7`

## pseudocode

```c
DNS_STATUS __fastcall NlDnsUpdate(struct _NL_DNS_NAME *a1, char a2)
{
  DNS_STATUS result; // eax
  int v5; // r12d
  __int16 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  DWORD v10; // ebx
  __int64 v11; // rax
  DNS_RECORDA *p_pReplaceSet; // rdx
  DNS_RECORDA *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ecx
  const SOCKADDR *v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbx
  _DWORD *pReserved; // [rsp+20h] [rbp-E0h]
  _DWORD *v20; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v22[7]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v23[2]; // [rsp+6Ch] [rbp-94h] BYREF
  __int16 v24; // [rsp+6Eh] [rbp-92h] BYREF
  _BYTE v25[6]; // [rsp+70h] [rbp-90h]
  __int128 v26; // [rsp+78h] [rbp-88h]
  DNS_RECORDA pReplaceSet; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD pSockaddr[3]; // [rsp+110h] [rbp+10h] BYREF
  int v29; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v30[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v31; // [rsp+140h] [rbp+40h]
  wchar_t *v32; // [rsp+150h] [rbp+50h]
  wchar_t Buffer[16]; // [rsp+158h] [rbp+58h] BYREF
  wchar_t v34[20]; // [rsp+178h] [rbp+78h] BYREF
  WCHAR pNodeBuffer[72]; // [rsp+1A0h] [rbp+A0h] BYREF

  *(_DWORD *)v21 = 0;
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  v32 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  memset_0(v22, 0, 0x60u);
  wcscpy(Buffer, L"<UNAILABLE>");
  wcscpy(v34, L"<UNAILABLE>");
  if ( !(unsigned int)GiveInstallHints(0) )
    return 9851;
  if ( !dword_1800F1250 )
  {
    result = 9004;
    *(_DWORD *)v21 = 9004;
    if ( NlGlobalNoDynamicDnsLogged )
      return result;
    NlpWriteEventlogEx(0x16AEu, 2u, 0, 0xFFFFFFFF, 0, 0, 0, 0);
    NlGlobalNoDynamicDnsLogged = 1;
    return *(_DWORD *)v21;
  }
  NlGlobalNoDynamicDnsLogged = 0;
  v5 = 0;
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  pReplaceSet.pName = (PSTR)*((_QWORD *)a1 + 8);
  pReplaceSet.dwTtl = dword_1800F1158;
  v6 = *((_WORD *)&NlDcDnsNameTypeDesc + 16 * *((int *)a1 + 4) + 12);
  if ( v6 != 1 )
  {
    v8 = *((_QWORD *)a1 + 11);
    pReplaceSet.Data.AAAA.Ip6Address.IP6Dword[1] = HIDWORD(v8);
    if ( v6 == 5 )
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
    v7 = *((_QWORD *)a1 + 12);
    *(_DWORD *)&pReplaceSet.wType = 262145;
    LODWORD(v8) = *(_DWORD *)(v7 + 4);
LABEL_15:
    pReplaceSet.Data.A.IpAddress = v8;
    goto LABEL_16;
  }
  if ( *((_WORD *)a1 + 56) == 23 )
  {
    v9 = *((_QWORD *)a1 + 12);
    *(_DWORD *)&pReplaceSet.wType = 1048604;
    *(_OWORD *)&pReplaceSet.Data.A.IpAddress = *(_OWORD *)(v9 + 8);
  }
LABEL_16:
  v22[0] = -2147483647;
  if ( !dword_1800F1264 )
    v5 = 0x2000;
  v10 = v5 | 0x4000;
  if ( v6 != 5 )
    v10 = v5;
  v22[4] = ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) != 0)
         + 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) )
  {
    if ( a2 )
    {
      v11 = 32LL * *((int *)a1 + 4);
      if ( *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v11 + 24) == 5
        || *(_DWORD *)((char *)&NlDcDnsNameTypeDesc + v11 + 20) == 1 )
      {
        result = DnsReplaceRecordSetUTF8(&pReplaceSet, v10, 0, v22, 0);
        goto LABEL_41;
      }
      v20 = 0;
      pReserved = v22;
      goto LABEL_25;
    }
    if ( NlGlobalDcDemotionInProgress )
      v10 |= 0x4000u;
    v20 = 0;
    pReserved = v22;
LABEL_39:
    v13 = 0;
    p_pReplaceSet = &pReplaceSet;
    goto LABEL_40;
  }
  if ( !a2 )
  {
    if ( NlGlobalDcDemotionInProgress )
      v10 |= 0x4000u;
    v20 = v22;
    pReserved = 0;
    goto LABEL_39;
  }
  v14 = 32LL * *((int *)a1 + 4);
  if ( *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v14 + 24) != 5
    && *(_DWORD *)((char *)&NlDcDnsNameTypeDesc + v14 + 20) != 1 )
  {
    v20 = v22;
    pReserved = 0;
LABEL_25:
    p_pReplaceSet = 0;
    v13 = &pReplaceSet;
LABEL_40:
    result = DnsModifyRecordsInSet_UTF8(v13, p_pReplaceSet, v10, 0, pReserved, v20);
    goto LABEL_41;
  }
  result = DnsReplaceRecordSetUTF8(&pReplaceSet, v10, 0, 0, v22);
LABEL_41:
  *(_DWORD *)v21 = result;
  switch ( result )
  {
    case 0:
      *((_DWORD *)a1 + 61) = 0;
      return result;
    case 1460:
    case 9002:
      if ( NlDnsWriteServerFailureEventLog )
      {
        *((_DWORD *)a1 + 61) = result;
        v17 = NlDnsNameToDomainName(a1);
        v18 = v17;
        if ( v17 )
        {
          v30[0] = v17;
          NlpWriteEventlogEx(0x1695u, 2u, 0, 0xFFFFFFFF, v30, 1u, v21, 4u);
          NetApiBufferFree(v18);
        }
      }
      return 9002;
    case 9851:
    case 9852:
    case 10047:
      *((_DWORD *)a1 + 61) = result;
      v30[0] = (unsigned __int16 *)(unsigned int)result;
      NlpWriteEventlogEx(0x1696u, 2u, 0x40000000u, 0xFFFFFFFF, v30, 1u, v21, 4u);
      return 9851;
  }
  *((_DWORD *)a1 + 61) = result;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) )
  {
    if ( v24 == 2 )
    {
      v15 = *(_DWORD *)&v25[2];
LABEL_52:
      NetpIpAddressToWStr(v15, pNodeBuffer);
      goto LABEL_56;
    }
    v16 = (const SOCKADDR *)&v24;
  }
  else
  {
    v15 = *(_DWORD *)v25;
    if ( *(_DWORD *)v25 )
      goto LABEL_52;
    pSockaddr[0] = 23;
    v16 = (const SOCKADDR *)pSockaddr;
    *(_OWORD *)&pSockaddr[1] = v26;
    v29 = 0;
  }
  if ( GetNameInfoW(v16, 28, pNodeBuffer, 0x42u, 0, 0, 2) )
    _o_wcscpy_s(pNodeBuffer, 66);
LABEL_56:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl);
  swprintf_s(Buffer, 0xEu, L"%lu", *(unsigned __int16 *)v23);
  swprintf_s(v34, 0xEu, L"%lu", v22[6]);
  result = *(_DWORD *)v21;
  if ( *(_DWORD *)v21 == 9004 )
  {
    v30[0] = pNodeBuffer;
    v30[1] = Buffer;
    *(_QWORD *)&v31 = v34;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl);
    NlpWriteEventlogEx(0x168Du, 2u, 0, 0xFFFFFFFF, v30, 3u, v23, 2u);
    return 9004;
  }
  else if ( !*((_DWORD *)a1 + 18) )
  {
    v30[0] = NlDnsNameToWStr(a1, dword_1800F1158);
    if ( v30[0] )
    {
      v30[1] = (unsigned __int16 *)*(unsigned int *)v21;
      *(_QWORD *)&v31 = pNodeBuffer;
      *((_QWORD *)&v31 + 1) = Buffer;
      v32 = v34;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl);
      NlpWriteEventlogEx(5775 - (a2 != 0), 1u, 0x40000000u, 1u, v30, 5u, v23, 2u);
      NetApiBufferFree(v30[0]);
    }
    return *(_DWORD *)v21;
  }
  return result;
}

```

## disassembly

```asm
0x1800229ec  push    rbp
0x1800229ee  push    rbx
0x1800229ef  push    rsi
0x1800229f0  push    rdi
0x1800229f1  push    r12
0x1800229f3  push    r13
0x1800229f5  push    r14
0x1800229f7  push    r15
0x1800229f9  lea     rbp, [rsp-148h]
0x180022a01  sub     rsp, 248h
0x180022a08  mov     rax, cs:__security_cookie
0x180022a0f  xor     rax, rsp
0x180022a12  mov     [rbp+180h+var_50], rax
0x180022a19  xor     r13d, r13d
0x180022a1c  mov     r15b, dl
0x180022a1f  mov     rdi, rcx
0x180022a22  mov     dword ptr [rsp+280h+var_240], r13d
0x180022a27  xor     edx, edx; Val
0x180022a29  lea     rcx, [rbp+180h+pReplaceSet]; void *
0x180022a2d  lea     ebx, [r13+58h]
0x180022a31  mov     r8d, ebx; Size
0x180022a34  call    memset_0
0x180022a39  xorps   xmm0, xmm0
0x180022a3c  lea     r8d, [r13+60h]; Size
0x180022a40  xor     eax, eax
0x180022a42  lea     rcx, [rsp+280h+var_230]; void *
0x180022a47  xor     edx, edx; Val
0x180022a49  mov     [rbp+180h+var_130], rax
0x180022a4d  movups  xmmword ptr [rbp+180h+var_150], xmm0
0x180022a51  movups  [rbp+180h+var_140], xmm0
0x180022a55  call    memset_0
0x180022a5a  movups  xmm1, xmmword ptr cs:aUnavailable
0x180022a61  xor     ecx, ecx; int
0x180022a63  movups  xmm0, xmmword ptr cs:aUnavailable+0Ch
0x180022a6a  movups  xmmword ptr [rbp+180h+Buffer], xmm1
0x180022a6e  movups  xmmword ptr [rbp+180h+var_108], xmm1
0x180022a72  movups  xmmword ptr [rbp+180h+Buffer+0Ch], xmm0
0x180022a76  movups  xmmword ptr [rbp+180h+var_108+0Ch], xmm0
0x180022a7d  call    ?GiveInstallHints@@YAHH@Z
0x180022a82  test    eax, eax
0x180022a84  jnz     short loc_180022A90
0x180022a86  mov     eax, 267Bh
0x180022a8b  jmp     loc_180022FEB
0x180022a90  cmp     cs:dword_1800F1250, r13d
0x180022a97  jnz     short loc_180022AEE
0x180022a99  cmp     cs:?NlGlobalNoDynamicDnsLogged@@3HA, r13d
0x180022aa0  mov     eax, 232Ch
0x180022aa5  mov     dword ptr [rsp+280h+var_240], eax
0x180022aa9  jnz     loc_180022FEB
0x180022aaf  mov     [rsp+280h+var_248], r13d; unsigned int
0x180022ab4  xor     r8d, r8d; unsigned int
0x180022ab7  mov     qword ptr [rsp+280h+Flags], r13; unsigned __int8 *
0x180022abc  or      r9d, 0FFFFFFFFh; unsigned int
0x180022ac0  mov     dword ptr [rsp+280h+var_258], r13d; unsigned int
0x180022ac5  mov     ecx, 16AEh; unsigned int
0x180022aca  mov     [rsp+280h+pReserved], r13; unsigned __int16 **
0x180022acf  lea     edx, [r8+2]; unsigned int
0x180022ad3  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z
0x180022ad8  mov     r14d, 1
0x180022ade  mov     cs:?NlGlobalNoDynamicDnsLogged@@3HA, r14d
0x180022ae5  mov     eax, dword ptr [rsp+280h+var_240]
0x180022ae9  jmp     loc_180022FEB
0x180022aee  mov     r8, rbx; Size
0x180022af1  mov     cs:?NlGlobalNoDynamicDnsLogged@@3HA, r13d
0x180022af8  xor     edx, edx; Val
0x180022afa  lea     rcx, [rbp+180h+pReplaceSet]; void *
0x180022afe  mov     r12d, r13d
0x180022b01  call    memset_0
0x180022b06  mov     rax, [rdi+40h]
0x180022b0a  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A
0x180022b11  mov     [rbp+180h+pReplaceSet.pName], rax
0x180022b15  mov     esi, 2
0x180022b1a  mov     eax, cs:dword_1800F1158
0x180022b20  mov     [rbp+180h+pReplaceSet.dwTtl], eax
0x180022b23  movsxd  rax, dword ptr [rdi+10h]
0x180022b27  shl     rax, 5
0x180022b2b  lea     r14d, [rsi-1]
0x180022b2f  lea     edx, [rsi+15h]
0x180022b32  lea     r9d, [rsi+3]
0x180022b36  movzx   r8d, word ptr [rax+rcx+18h]
0x180022b3c  cmp     r8w, r14w
0x180022b40  jnz     short loc_180022B93
0x180022b42  cmp     [rdi+70h], si
0x180022b46  jnz     short loc_180022B58
0x180022b48  mov     rax, [rdi+60h]
0x180022b4c  mov     dword ptr [rbp+180h+pReplaceSet.wType], 40001h
0x180022b53  mov     ecx, [rax+4]
0x180022b56  jmp     short loc_180022BCF
0x180022b58  cmp     [rdi+70h], dx
0x180022b5c  jnz     short loc_180022BD2
0x180022b5e  mov     rcx, [rdi+60h]
0x180022b62  mov     dword ptr [rbp+180h+pReplaceSet.wType], 10001Ch
0x180022b69  mov     rax, [rcx+8]
0x180022b6d  mov     qword ptr [rbp+180h+pReplaceSet.Data], rax
0x180022b71  movzx   eax, word ptr [rcx+10h]
0x180022b75  mov     word ptr [rbp+180h+pReplaceSet.Data+8], ax
0x180022b79  movzx   eax, word ptr [rcx+12h]
0x180022b7d  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ah], ax
0x180022b81  movzx   eax, word ptr [rcx+14h]
0x180022b85  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ch], ax
0x180022b89  movzx   eax, word ptr [rcx+16h]
0x180022b8d  mov     word ptr [rbp+180h+pReplaceSet.Data+0Eh], ax
0x180022b91  jmp     short loc_180022BD2
0x180022b93  mov     rcx, [rdi+58h]
0x180022b97  mov     rax, rcx
0x180022b9a  sar     rax, 20h
0x180022b9e  mov     dword ptr [rbp+180h+pReplaceSet.Data+4], eax
0x180022ba1  cmp     r8w, r9w
0x180022ba5  jnz     short loc_180022BB0
0x180022ba7  mov     dword ptr [rbp+180h+pReplaceSet.wType], 80005h
0x180022bae  jmp     short loc_180022BCF
0x180022bb0  movzx   eax, word ptr [rdi+4Ch]
0x180022bb4  mov     word ptr [rbp+180h+pReplaceSet.Data+8], ax
0x180022bb8  movzx   eax, word ptr [rdi+50h]
0x180022bbc  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ah], ax
0x180022bc0  movzx   eax, word ptr [rdi+54h]
0x180022bc4  mov     word ptr [rbp+180h+pReplaceSet.Data+0Ch], ax
0x180022bc8  mov     dword ptr [rbp+180h+pReplaceSet.wType], 100021h
0x180022bcf  mov     dword ptr [rbp+180h+pReplaceSet.Data], ecx
0x180022bd2  cmp     cs:dword_1800F1264, r13d
0x180022bd9  mov     eax, 2000h
0x180022bde  mov     [rsp+280h+var_230], 80000001h
0x180022be6  cmovz   r12d, eax
0x180022bea  mov     ebx, r12d
0x180022bed  bts     ebx, 0Eh
0x180022bf1  cmp     r8w, r9w
0x180022bf5  cmovnz  ebx, r12d
0x180022bf9  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_6086_9425@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@3@XZ@4V453@A
0x180022c00  mov     rcx, r12
0x180022c03  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ
0x180022c08  neg     al
0x180022c0a  sbb     ecx, ecx
0x180022c0c  neg     ecx
0x180022c0e  add     ecx, r14d
0x180022c11  mov     [rsp+280h+var_220], ecx
0x180022c15  mov     rcx, r12
0x180022c18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ
0x180022c1d  test    al, al
0x180022c1f  jz      short loc_180022C8C
0x180022c21  test    r15b, r15b
0x180022c24  jz      short loc_180022C6E
0x180022c26  movsxd  rax, dword ptr [rdi+10h]
0x180022c2a  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A
0x180022c31  shl     rax, 5
0x180022c35  mov     edx, 5
0x180022c3a  cmp     [rax+rcx+18h], dx
0x180022c3f  jz      short loc_180022C62
0x180022c41  cmp     [rax+rcx+14h], r14d
0x180022c46  jz      short loc_180022C62
0x180022c48  lea     rax, [rsp+280h+var_230]
0x180022c4d  mov     [rsp+280h+var_258], r13
0x180022c52  mov     [rsp+280h+pReserved], rax
0x180022c57  xor     edx, edx
0x180022c59  lea     rcx, [rbp+180h+pReplaceSet]
0x180022c5d  jmp     loc_180022D04
0x180022c62  mov     [rsp+280h+pReserved], r13
0x180022c67  lea     r9, [rsp+280h+var_230]
0x180022c6c  jmp     short loc_180022CD1
0x180022c6e  cmp     cs:?NlGlobalDcDemotionInProgress@@3EA, r13b
0x180022c75  jz      short loc_180022C7B
0x180022c77  bts     ebx, 0Eh
0x180022c7b  lea     rax, [rsp+280h+var_230]
0x180022c80  mov     [rsp+280h+var_258], r13
0x180022c85  mov     [rsp+280h+pReserved], rax
0x180022c8a  jmp     short loc_180022CFE
0x180022c8c  test    r15b, r15b
0x180022c8f  jz      short loc_180022CE2
0x180022c91  movsxd  rax, dword ptr [rdi+10h]
0x180022c95  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A
0x180022c9c  shl     rax, 5
0x180022ca0  mov     edx, 5
0x180022ca5  cmp     [rax+rcx+18h], dx
0x180022caa  jz      short loc_180022CC4
0x180022cac  cmp     [rax+rcx+14h], r14d
0x180022cb1  jz      short loc_180022CC4
0x180022cb3  lea     rax, [rsp+280h+var_230]
0x180022cb8  mov     [rsp+280h+var_258], rax
0x180022cbd  mov     [rsp+280h+pReserved], r13
0x180022cc2  jmp     short loc_180022C57
0x180022cc4  lea     rax, [rsp+280h+var_230]
0x180022cc9  xor     r9d, r9d; pExtraInfo
0x180022ccc  mov     [rsp+280h+pReserved], rax; pReserved
0x180022cd1  xor     r8d, r8d; hContext
0x180022cd4  lea     rcx, [rbp+180h+pReplaceSet]; pReplaceSet
0x180022cd8  mov     edx, ebx; Options
0x180022cda  call    cs:__imp_DnsReplaceRecordSetUTF8
0x180022ce0  jmp     short loc_180022D10
0x180022ce2  cmp     cs:?NlGlobalDcDemotionInProgress@@3EA, r13b
0x180022ce9  jz      short loc_180022CEF
0x180022ceb  bts     ebx, 0Eh
0x180022cef  lea     rax, [rsp+280h+var_230]
0x180022cf4  mov     [rsp+280h+var_258], rax; pReserved
0x180022cf9  mov     [rsp+280h+pReserved], r13; pExtraList
0x180022cfe  xor     ecx, ecx; pAddRecords
0x180022d00  lea     rdx, [rbp+180h+pReplaceSet]; pDeleteRecords
0x180022d04  xor     r9d, r9d; hCredentials
0x180022d07  mov     r8d, ebx; Options
0x180022d0a  call    cs:__imp_DnsModifyRecordsInSet_UTF8
0x180022d10  mov     dword ptr [rsp+280h+var_240], eax
0x180022d14  mov     ecx, eax
0x180022d16  test    eax, eax
0x180022d18  jz      loc_180022FE4
0x180022d1e  sub     ecx, 5B4h
0x180022d24  jz      loc_180022F7E
0x180022d2a  sub     ecx, 1D76h
0x180022d30  jz      loc_180022F7E
0x180022d36  sub     ecx, 351h
0x180022d3c  jz      loc_180022F37
0x180022d42  sub     ecx, r14d
0x180022d45  jz      loc_180022F37
0x180022d4b  cmp     ecx, 0C3h
0x180022d51  jz      loc_180022F37
0x180022d57  mov     [rdi+0F4h], eax
0x180022d5d  mov     rcx, r12
0x180022d60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ
0x180022d65  test    al, al
0x180022d67  jz      short loc_180022D7D
0x180022d69  cmp     [rsp+280h+var_212], si
0x180022d6e  jnz     short loc_180022D76
0x180022d70  mov     ecx, [rsp+280h+var_20E]
0x180022d74  jmp     short loc_180022D85
0x180022d76  lea     rcx, [rsp+280h+var_212]
0x180022d7b  jmp     short loc_180022DB7
0x180022d7d  mov     ecx, [rsp+70h]; unsigned int
0x180022d81  test    ecx, ecx
0x180022d83  jz      short loc_180022D93
0x180022d85  lea     rdx, [rbp+180h+pNodeBuffer]; unsigned __int16 *
0x180022d8c  call    ?NetpIpAddressToWStr@@YAXKQEAG@Z
0x180022d91  jmp     short loc_180022DF7
0x180022d93  movups  xmm0, [rsp+280h+var_208]
0x180022d98  mov     eax, 17h
0x180022d9d  mov     dword ptr [rbp+180h+pSockaddr+2], r13d
0x180022da1  mov     word ptr [rbp+180h+pSockaddr+6], r13w
0x180022da6  lea     rcx, [rbp+180h+pSockaddr]; pSockaddr
0x180022daa  movdqu  xmmword ptr [rbp+180h+pSockaddr+8], xmm0
0x180022daf  mov     [rbp+180h+var_158], r13d
0x180022db3  mov     word ptr [rbp+180h+pSockaddr], ax
0x180022db7  mov     ebx, 42h ; 'B'
0x180022dbc  mov     [rsp+280h+Flags], esi; Flags
0x180022dc0  mov     dword ptr [rsp+280h+var_258], r13d; ServiceBufferSize
0x180022dc5  lea     r8, [rbp+180h+pNodeBuffer]; pNodeBuffer
0x180022dcc  mov     r9d, ebx; NodeBufferSize
0x180022dcf  mov     [rsp+280h+pReserved], r13; pServiceBuffer
0x180022dd4  lea     edx, [rbx-26h]; SockaddrLength
0x180022dd7  call    cs:__imp_GetNameInfoW
0x180022ddd  test    eax, eax
0x180022ddf  jz      short loc_180022DF7
0x180022de1  lea     r8, aUnavailable
0x180022de8  mov     edx, ebx
0x180022dea  lea     rcx, [rbp+180h+pNodeBuffer]
0x180022df1  call    cs:__imp__o_wcscpy_s
0x180022df7  mov     rcx, r12
0x180022dfa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ
0x180022dff  movzx   r9d, word ptr [rsp+280h+var_214]
0x180022e05  lea     r8, aLu_0
0x180022e0c  mov     ebx, 0Eh
0x180022e11  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180022e15  mov     edx, ebx; BufferCount
0x180022e17  call    swprintf_s
0x180022e1c  mov     r9d, [rsp+280h+var_218]
0x180022e21  lea     r8, aLu_0
0x180022e28  mov     edx, ebx; BufferCount
0x180022e2a  lea     rcx, [rbp+180h+var_108]; Buffer
0x180022e2e  call    swprintf_s
0x180022e33  mov     eax, dword ptr [rsp+280h+var_240]
0x180022e37  cmp     eax, 232Ch
0x180022e3c  jnz     short loc_180022E9D
0x180022e3e  lea     rax, [rbp+180h+pNodeBuffer]
0x180022e45  mov     [rbp+180h+var_150], rax
0x180022e49  lea     rax, [rbp+180h+Buffer]
0x180022e4d  mov     [rbp+180h+var_150+8], rax
0x180022e51  lea     rax, [rbp+180h+var_108]
0x180022e55  mov     qword ptr [rbp+180h+var_140], rax
0x180022e59  mov     rcx, r12
0x180022e5c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ
0x180022e61  mov     [rsp+280h+var_248], esi; unsigned int
0x180022e65  lea     rax, [rsp+280h+var_214]
0x180022e6a  mov     qword ptr [rsp+280h+Flags], rax; unsigned __int8 *
0x180022e6f  or      r9d, 0FFFFFFFFh; unsigned int
0x180022e73  lea     rax, [rbp+180h+var_150]
0x180022e77  mov     dword ptr [rsp+280h+var_258], 3; unsigned int
0x180022e7f  xor     r8d, r8d; unsigned int
0x180022e82  mov     [rsp+280h+pReserved], rax; unsigned __int16 **
0x180022e87  mov     edx, esi; unsigned int
0x180022e89  mov     ecx, 168Dh; unsigned int
0x180022e8e  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z
0x180022e93  mov     eax, 232Ch
0x180022e98  jmp     loc_180022FEB
0x180022e9d  cmp     [rdi+48h], r13d
0x180022ea1  jnz     loc_180022FEB
0x180022ea7  mov     edx, cs:dword_1800F1158; unsigned int
0x180022ead  mov     rcx, rdi; struct _NL_DNS_NAME *
0x180022eb0  call    ?NlDnsNameToWStr@@YAPEAGPEAU_NL_DNS_NAME@@K@Z
0x180022eb5  mov     [rbp+180h+var_150], rax
0x180022eb9  test    rax, rax
0x180022ebc  jz      loc_180022AE5
0x180022ec2  mov     eax, dword ptr [rsp+280h+var_240]
0x180022ec6  mov     [rbp+180h+var_150+8], rax
0x180022eca  lea     rax, [rbp+180h+pNodeBuffer]
0x180022ed1  mov     qword ptr [rbp+180h+var_140], rax
  ... truncated ...
```
