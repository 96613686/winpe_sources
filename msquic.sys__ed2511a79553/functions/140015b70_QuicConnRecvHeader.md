# QuicConnRecvHeader

- ea: `0x140015b70`
- end: `0x140016206`
- name: `QuicConnRecvHeader`
- size: `1686`
- prototype: `char __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140015480`

## callees

- `0x140005184`
- `0x1400123b0`
- `0x140015b70`
- `0x14001f900`
- `0x140021340`
- `0x14002157c`
- `0x140026a88`
- `0x140029ef0`
- `0x14002a048`
- `0x14002a5b8`
- `0x14002bb4c`
- `0x14002bb84`
- `0x14002f204`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`
- `0x14003ed00`
- `0x1400419ac`
- `0x140041d3c`
- `0x1400424d4`
- `0x140042e10`
- `0x1400430f0`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001614e`
- `ntoskrnl!_snprintf_s` at `0x14001614e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015e7f`
- `ntoskrnl!ExAllocatePool2` at `0x140015e9e`
- `ntoskrnl!ExAllocatePool2` at `0x140015f49`
- `ntoskrnl!ExAllocatePool2` at `0x140015e9e`
- `ntoskrnl!ExAllocatePool2` at `0x140015f49`

## string_xrefs

- `0x140015dc7`: `SH packet during version negotiation`
- `0x140015e55`: `Retry token decrypt failure`

## pseudocode

```c
char __fastcall QuicConnRecvHeader(__int64 a1, __int64 a2, _OWORD *a3)
{
  int v6; // esi
  char v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rax
  char v10; // cl
  __int64 v11; // rsi
  __int64 v12; // r8
  char v13; // al
  unsigned int v14; // edx
  __int64 v15; // rcx
  int v16; // eax
  char result; // al
  void *v18; // rcx
  __int64 Pool2; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  unsigned __int8 *v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  int v26; // r8d
  char v27; // dl
  char v28; // al
  __int64 v29; // rax
  __int64 v30; // rsi
  __int64 v31; // rcx
  __int64 *v32; // rdx
  __int64 *i; // rcx
  __int64 v34; // rcx
  int v35; // r8d
  char v36[4]; // [rsp+30h] [rbp-79h] BYREF
  _WORD v37[2]; // [rsp+34h] [rbp-75h] BYREF
  __int64 v38; // [rsp+38h] [rbp-71h] BYREF
  char DstBuf[16]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v40; // [rsp+50h] [rbp-59h]
  __int128 Src; // [rsp+60h] [rbp-49h] BYREF
  __int128 v42; // [rsp+70h] [rbp-39h]
  __int128 v43; // [rsp+80h] [rbp-29h]

  if ( (*(_BYTE *)(a2 + 92) & 2) == 0 && !QuicPacketValidateInvariant(a1, a2, (*(_BYTE *)(a1 + 251) & 2) != 0) )
    return 0;
  v6 = *(_DWORD *)(a1 + 3636);
  if ( (*(_BYTE *)(a2 + 92) & 4) != 0 )
  {
    if ( v6 == 52651 )
      goto LABEL_15;
    if ( v6 != 0x1000000 && v6 != 486539519 && v6 != -817679509 )
    {
      QuicPacketLogDrop(a1, a2, "SH packet during version negotiation");
      return 0;
    }
  }
  else if ( *(_DWORD *)(*(_QWORD *)(a2 + 56) + 1LL) != v6 )
  {
    if ( !(unsigned __int8)QuicConnIsClient(a1)
      || (v7 = *(_BYTE *)(a1 + 251), (v7 & 0x40) != 0)
      || !(unsigned __int8)QuicVersionNegotiationExtIsVersionCompatible() )
    {
      if ( !(unsigned __int8)QuicConnIsClient(a1) || v14 || (v16 = *(_DWORD *)(a1 + 3632), (v16 & 1) != 0) )
      {
        QuicPacketLogDropWithValue(v15, a2, "Invalid version", _byteswap_ulong(v14));
        return 0;
      }
      else
      {
        *(_DWORD *)(a1 + 3632) = v16 | 1;
        QuicConnRecvVerNeg(v15, a2);
        return 0;
      }
    }
    *(_DWORD *)(a1 + 3884) = v6;
    *(_BYTE *)(a1 + 251) = v7 | 0x40;
    *(_DWORD *)(a1 + 3636) = *(_DWORD *)(*(_QWORD *)(a2 + 56) + 1LL);
    QuicConnOnQuicVersionSet(a1);
    if ( (int)QuicCryptoOnVersionChange(a1 + 2784) < 0 )
      return 0;
    v6 = *(_DWORD *)(a1 + 3636);
  }
  if ( v6 != 52651 && v6 != 0x1000000 && v6 != 486539519 && v6 != -817679509 )
  {
    CxPlatLogAssert(
      "C:\\__w\\1\\s\\msquic\\src\\core\\connection.c",
      3841,
      "QuicIsVersionSupported(Connection->Stats.QuicVersion)");
    __int2c();
  }
LABEL_15:
  v8 = *(unsigned __int8 *)(a2 + 92);
  if ( (v8 & 4) != 0 )
  {
    if ( (v8 & 8) == 0 )
    {
      if ( *(char *)(a1 + 235) >= 0 && (**(_BYTE **)(a2 + 56) & 0x40) == 0 )
      {
        QuicPacketLogDrop(a1, a2, "Invalid SH FixedBit bits values");
        return 0;
      }
      LOBYTE(v8) = v8 | 8;
      *(_WORD *)(a2 + 84) = *(_WORD *)(a2 + 80) - *(_WORD *)(a2 + 82);
      *(_BYTE *)(a2 + 92) = v8;
    }
    v26 = 3;
    *(_DWORD *)(a2 + 88) = 3;
    if ( (*(_BYTE *)(a1 + 249) & 0x10) != 0 || (*(_BYTE *)(a1 + 322) & 0x20) != 0 )
      v28 = 0;
    else
      v28 = 64;
    v27 = v28 | v8 & 0xBF;
    goto LABEL_71;
  }
  v9 = *(_QWORD *)(a2 + 56);
  v10 = *(_BYTE *)v9 & 0x30;
  if ( *(_DWORD *)(v9 + 1) != -817679509 )
  {
    if ( v10 != 48 )
      goto LABEL_18;
LABEL_37:
    QuicConnRecvRetry(a1, a2);
    return 0;
  }
  if ( !v10 )
    goto LABEL_37;
LABEL_18:
  v38 = 0;
  v11 = 0;
  v37[0] = 0;
  v12 = 0;
  if ( (v8 & 8) == 0 )
  {
    LOBYTE(v8) = *(_DWORD *)a1 == 4;
    if ( !(unsigned __int8)QuicPacketValidateLongHeaderV1(
                             a1,
                             v8,
                             a2,
                             (unsigned int)&v38,
                             (__int64)v37,
                             *(_BYTE *)(a1 + 235) >> 7) )
      return 0;
    v11 = v38;
    v12 = v37[0];
  }
  if ( (*(_BYTE *)(a1 + 321) & 0x20) != 0 )
    goto LABEL_51;
  v13 = *(_BYTE *)(a2 + 92) & 0x10;
  if ( !v13 && !(_WORD)v12 )
    goto LABEL_51;
  v36[0] = 0;
  if ( v13 )
  {
    QuicPacketDecodeRetryTokenV1(a2, &v38, v37);
    v11 = v38;
    goto LABEL_42;
  }
  if ( !(unsigned __int8)QuicPacketValidateInitialToken(a1, a2, v12, v11, (__int64)v36) )
  {
    if ( v36[0] )
      return 0;
    goto LABEL_42;
  }
  if ( !v36[0] )
  {
LABEL_42:
    *(_OWORD *)DstBuf = 0;
    v40 = 0;
    Src = 0;
    v42 = 0;
    v43 = 0;
    if ( !(unsigned __int8)QuicRetryTokenDecrypt(a2, v11, DstBuf) )
    {
      QuicPacketLogDrop(a1, a2, "Retry token decrypt failure");
      return 0;
    }
    v18 = *(void **)(a1 + 1304);
    if ( v18 )
      ExFreePoolWithTag(v18, 0x43306351u);
    Pool2 = ExAllocatePool2(66, BYTE8(v42) + 16LL, 1127244625);
    *(_QWORD *)(a1 + 1304) = Pool2;
    if ( !Pool2 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(0, v20, "OrigDestCID", BYTE8(v42) + 16LL);
      QuicPacketLogDrop(a1, a2, "OrigDestCID from Retry OOM");
      return 0;
    }
    *(_BYTE *)(Pool2 + 1) = BYTE8(v42);
    memmove((void *)(*(_QWORD *)(a1 + 1304) + 16LL), (char *)&Src + 4, BYTE8(v42));
    *(_BYTE *)(a1 + 250) |= 1u;
    QuicPathSetValid(a1, a1 + 320, 0);
  }
LABEL_51:
  if ( !*(_QWORD *)(a1 + 1304) )
  {
    v21 = ExAllocatePool2(66, *(unsigned __int8 *)(a2 + 86) + 16LL, 1127244625);
    *(_QWORD *)(a1 + 1304) = v21;
    if ( !v21 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(0, v22, "OrigDestCID", *(unsigned __int8 *)(a2 + 86) + 16LL);
      QuicPacketLogDrop(a1, a2, "OrigDestCID OOM");
      return 0;
    }
    *(_BYTE *)(v21 + 1) = *(_BYTE *)(a2 + 86);
    memmove((void *)(*(_QWORD *)(a1 + 1304) + 16LL), *(const void **)(a2 + 64), *(unsigned __int8 *)(a2 + 86));
  }
  v23 = *(unsigned __int8 **)(a2 + 56);
  v24 = *v23;
  LOBYTE(v24) = ((unsigned __int8)v24 >> 4) & 3;
  if ( *(_DWORD *)(v23 + 1) == -817679509 )
    v25 = QuicPacketTypeToKeyTypeV2(v24, v8, v12);
  else
    v25 = QuicPacketTypeToKeyTypeV1(v24, v8, v12);
  v26 = v25;
  v27 = *(_BYTE *)(a2 + 92) | 0x40;
  *(_DWORD *)(a2 + 88) = v25;
LABEL_71:
  *(_BYTE *)(a2 + 92) = v27;
  if ( (v27 & 0x40) != 0 && (*(_BYTE *)(a1 + 249) & 8) != 0 && *(_WORD *)(a2 + 84) < 0x14u )
  {
    QuicPacketLogDrop(a1, a2, "Too short for HP");
    return 0;
  }
  if ( v26 <= *(_DWORD *)(a1 + 2808) )
  {
    if ( !(unsigned __int8)QuicConnIsServer(a1) || (*(_BYTE *)(a1 + 250) & 2) != 0 || v35 != 3 )
    {
      if ( *(_QWORD *)(a1 + 8LL * v35 + 2872) )
      {
        result = 1;
        *a3 = *(_OWORD *)(*(unsigned __int16 *)(a2 + 82) + *(_QWORD *)(a2 + 56) + 4LL);
        return result;
      }
      QuicPacketLogDrop(v34, a2, "Key no longer accepted");
    }
    return 0;
  }
  if ( v26 == 1 )
  {
    if ( *(_DWORD *)(a1 + 2804) )
    {
      QuicPacketLogDrop(a1, a2, "0-RTT not currently accepted");
      return 0;
    }
    v29 = 2776;
    LOWORD(v26) = 1;
  }
  else if ( v26 )
  {
    if ( v26 == 2 )
    {
      v29 = 2768;
      LOWORD(v26) = 2;
    }
    else
    {
      v29 = 2776;
    }
  }
  else
  {
    v29 = 2760;
    LOWORD(v26) = 0;
  }
  v30 = *(_QWORD *)(v29 + a1);
  if ( *(_BYTE *)(v30 + 4) == 15 )
  {
    QuicPacketLogDrop(a1, a2, "Max deferred packet count reached");
    return 0;
  }
  else
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Deferring datagram (type=%hu)", (unsigned __int16)v26);
      McTemplateU0ps_EtwWriteTransfer(v31, QuicConnLogVerbose, a1, DstBuf);
    }
    ++*(_BYTE *)(v30 + 4);
    v32 = (__int64 *)(v30 + 40);
    *(_BYTE *)(a2 + 93) |= 1u;
    for ( i = *(__int64 **)(v30 + 40); i; i = (__int64 *)*i )
      v32 = i;
    *v32 = a2;
    result = 0;
    *(_QWORD *)a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140015b70  push    rbp
0x140015b72  push    rbx
0x140015b73  push    rsi
0x140015b74  push    rdi
0x140015b75  push    r12
0x140015b77  push    r14
0x140015b79  push    r15
0x140015b7b  lea     rbp, [rsp-27h]
0x140015b80  sub     rsp, 0D0h
0x140015b87  mov     rax, cs:__security_cookie
0x140015b8e  xor     rax, rsp
0x140015b91  mov     [rbp+57h+var_40], rax
0x140015b95  test    byte ptr [rdx+5Ch], 2
0x140015b99  mov     r12, r8
0x140015b9c  mov     rbx, rdx
0x140015b9f  mov     rdi, rcx
0x140015ba2  jnz     short loc_140015BC0
0x140015ba4  movzx   r8d, byte ptr [rcx+0FBh]
0x140015bac  shr     r8b, 1
0x140015baf  and     r8b, 1
0x140015bb3  call    QuicPacketValidateInvariant
0x140015bb8  test    al, al
0x140015bba  jz      loc_1400161CF
0x140015bc0  test    byte ptr [rbx+5Ch], 4
0x140015bc4  mov     esi, [rdi+0E34h]
0x140015bca  jnz     loc_140015D97
0x140015bd0  mov     rax, [rbx+38h]
0x140015bd4  mov     edx, [rax+1]
0x140015bd7  cmp     edx, esi
0x140015bd9  jz      short loc_140015C4A
0x140015bdb  mov     rcx, rdi
0x140015bde  call    QuicConnIsClient
0x140015be3  test    al, al
0x140015be5  jz      loc_140015D4A
0x140015beb  movzx   r15d, byte ptr [rdi+0FBh]
0x140015bf3  test    r15b, 40h
0x140015bf7  jnz     loc_140015D4A
0x140015bfd  call    QuicVersionNegotiationExtIsVersionCompatible
0x140015c02  test    al, al
0x140015c04  jz      loc_140015D4A
0x140015c0a  mov     [rdi+0F2Ch], esi
0x140015c10  or      r15b, 40h
0x140015c14  mov     [rdi+0FBh], r15b
0x140015c1b  mov     rax, [rbx+38h]
0x140015c1f  mov     ecx, [rax+1]
0x140015c22  mov     [rdi+0E34h], ecx
0x140015c28  mov     rcx, rdi
0x140015c2b  call    QuicConnOnQuicVersionSet
0x140015c30  lea     rcx, [rdi+0AE0h]
0x140015c37  call    QuicCryptoOnVersionChange
0x140015c3c  test    eax, eax
0x140015c3e  js      loc_1400161CF
0x140015c44  mov     esi, [rdi+0E34h]
0x140015c4a  cmp     esi, 0CDABh
0x140015c50  jz      short loc_140015C84
0x140015c52  cmp     esi, 1000000h
0x140015c58  jz      short loc_140015C84
0x140015c5a  cmp     esi, 1D0000FFh
0x140015c60  jz      short loc_140015C84
0x140015c62  cmp     esi, 0CF43336Bh
0x140015c68  jz      short loc_140015C84
0x140015c6a  lea     r8, aQuicisversions; "QuicIsVersionSupported(Connection->Stat"...
0x140015c71  mov     edx, 0F01h
0x140015c76  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x140015c7d  call    CxPlatLogAssert
0x140015c82  int     2Ch; Windows NT - assertion failure
0x140015c84  movzx   edx, byte ptr [rbx+5Ch]
0x140015c88  xor     r15d, r15d
0x140015c8b  test    dl, 4
0x140015c8e  jnz     loc_140015FF9
0x140015c94  mov     rax, [rbx+38h]
0x140015c98  movzx   ecx, byte ptr [rax]
0x140015c9b  and     cl, 30h
0x140015c9e  cmp     dword ptr [rax+1], 0CF43336Bh
0x140015ca5  jz      loc_140015DE0
0x140015cab  cmp     cl, 30h ; '0'
0x140015cae  jz      loc_140015DE8
0x140015cb4  mov     [rbp+57h+var_C8], r15
0x140015cb8  mov     rsi, r15
0x140015cbb  mov     [rbp+57h+var_CC], r15w
0x140015cc0  movzx   r8d, r15w
0x140015cc4  test    dl, 8
0x140015cc7  jnz     short loc_140015D06
0x140015cc9  movzx   eax, byte ptr [rdi+0EBh]
0x140015cd0  lea     r9, [rbp+57h+var_C8]
0x140015cd4  shr     al, 7
0x140015cd7  mov     r8, rbx
0x140015cda  cmp     dword ptr [rdi], 4
0x140015cdd  mov     rcx, rdi
0x140015ce0  mov     [rsp+100h+var_D8], al
0x140015ce4  lea     rax, [rbp+57h+var_CC]
0x140015ce8  setz    dl
0x140015ceb  mov     [rsp+100h+var_E0], rax
0x140015cf0  call    QuicPacketValidateLongHeaderV1
0x140015cf5  test    al, al
0x140015cf7  jz      loc_1400161CF
0x140015cfd  mov     rsi, [rbp+57h+var_C8]
0x140015d01  movzx   r8d, [rbp+57h+var_CC]
0x140015d06  test    byte ptr [rdi+141h], 20h
0x140015d0d  jnz     loc_140015F29
0x140015d13  movzx   eax, byte ptr [rbx+5Ch]
0x140015d17  and     al, 10h
0x140015d19  jnz     short loc_140015D25
0x140015d1b  test    r8w, r8w
0x140015d1f  jz      loc_140015F29
0x140015d25  mov     [rbp+57h+var_D0], r15b
0x140015d29  test    al, al
0x140015d2b  jz      loc_140015DFA
0x140015d31  lea     r8, [rbp+57h+var_CC]
0x140015d35  mov     rcx, rbx
0x140015d38  lea     rdx, [rbp+57h+var_C8]
0x140015d3c  call    QuicPacketDecodeRetryTokenV1
0x140015d41  mov     rsi, [rbp+57h+var_C8]
0x140015d45  jmp     loc_140015E2B
0x140015d4a  mov     rcx, rdi
0x140015d4d  call    QuicConnIsClient
0x140015d52  test    al, al
0x140015d54  jz      short loc_140015D7C
0x140015d56  test    edx, edx
0x140015d58  jnz     short loc_140015D7C
0x140015d5a  mov     eax, [rdi+0E30h]
0x140015d60  test    al, 1
0x140015d62  jnz     short loc_140015D7C
0x140015d64  or      eax, 1
0x140015d67  mov     rdx, rbx
0x140015d6a  mov     [rdi+0E30h], eax
0x140015d70  call    QuicConnRecvVerNeg
0x140015d75  xor     al, al
0x140015d77  jmp     loc_1400161E7
0x140015d7c  bswap   edx
0x140015d7e  mov     r9d, edx
0x140015d81  lea     r8, aInvalidVersion; "Invalid version"
0x140015d88  mov     rdx, rbx
0x140015d8b  call    QuicPacketLogDropWithValue
0x140015d90  xor     al, al
0x140015d92  jmp     loc_1400161E7
0x140015d97  cmp     esi, 0CDABh
0x140015d9d  jz      loc_140015C84
0x140015da3  cmp     esi, 1000000h
0x140015da9  jz      loc_140015C4A
0x140015daf  cmp     esi, 1D0000FFh
0x140015db5  jz      loc_140015C4A
0x140015dbb  cmp     esi, 0CF43336Bh
0x140015dc1  jz      loc_140015C4A
0x140015dc7  lea     r8, aShPacketDuring; "SH packet during version negotiation"
0x140015dce  mov     rdx, rbx
0x140015dd1  mov     rcx, rdi
0x140015dd4  call    QuicPacketLogDrop
0x140015dd9  xor     al, al
0x140015ddb  jmp     loc_1400161E7
0x140015de0  test    cl, cl
0x140015de2  jnz     loc_140015CB4
0x140015de8  mov     rdx, rbx
0x140015deb  mov     rcx, rdi
0x140015dee  call    QuicConnRecvRetry
0x140015df3  xor     al, al
0x140015df5  jmp     loc_1400161E7
0x140015dfa  lea     rax, [rbp+57h+var_D0]
0x140015dfe  mov     r9, rsi
0x140015e01  mov     rdx, rbx
0x140015e04  mov     [rsp+100h+var_E0], rax
0x140015e09  mov     rcx, rdi
0x140015e0c  call    QuicPacketValidateInitialToken
0x140015e11  test    al, al
0x140015e13  jnz     short loc_140015E21
0x140015e15  cmp     [rbp+57h+var_D0], r15b
0x140015e19  jnz     loc_1400161CF
0x140015e1f  jmp     short loc_140015E2B
0x140015e21  cmp     [rbp+57h+var_D0], r15b
0x140015e25  jnz     loc_140015F29
0x140015e2b  xorps   xmm0, xmm0
0x140015e2e  lea     r8, [rbp+57h+DstBuf]
0x140015e32  mov     rdx, rsi
0x140015e35  mov     rcx, rbx
0x140015e38  movups  xmmword ptr [rbp+57h+DstBuf], xmm0
0x140015e3c  movups  [rbp+57h+var_B0], xmm0
0x140015e40  movups  [rbp+57h+Src], xmm0
0x140015e44  movups  [rbp+57h+var_90], xmm0
0x140015e48  movups  [rbp+57h+var_80], xmm0
0x140015e4c  call    QuicRetryTokenDecrypt
0x140015e51  test    al, al
0x140015e53  jnz     short loc_140015E6E
0x140015e55  lea     r8, aRetryTokenDecr_0; "Retry token decrypt failure"
0x140015e5c  mov     rdx, rbx
0x140015e5f  mov     rcx, rdi
0x140015e62  call    QuicPacketLogDrop
0x140015e67  xor     al, al
0x140015e69  jmp     loc_1400161E7
0x140015e6e  mov     rcx, [rdi+518h]; P
0x140015e75  test    rcx, rcx
0x140015e78  jz      short loc_140015E8B
0x140015e7a  mov     edx, 43306351h; Tag
0x140015e7f  call    cs:__imp_ExFreePoolWithTag
0x140015e86  nop     dword ptr [rax+rax+00h]
0x140015e8b  movzx   edx, byte ptr [rbp+57h+var_90+8]
0x140015e8f  mov     ecx, 42h ; 'B'
0x140015e94  add     rdx, 10h
0x140015e98  mov     r8d, 43306351h
0x140015e9e  call    cs:__imp_ExAllocatePool2
0x140015ea5  nop     dword ptr [rax+rax+00h]
0x140015eaa  mov     [rdi+518h], rax
0x140015eb1  mov     rcx, rax
0x140015eb4  test    rax, rax
0x140015eb7  jnz     short loc_140015EF0
0x140015eb9  test    cs:Microsoft_QuicEnableBits, 2
0x140015ec0  jz      short loc_140015ED7
0x140015ec2  movzx   r9d, byte ptr [rbp+57h+var_90+8]
0x140015ec7  lea     r8, aOrigdestcid; "OrigDestCID"
0x140015ece  add     r9, 10h
0x140015ed2  call    McTemplateU0sx_EtwWriteTransfer
0x140015ed7  lea     r8, aOrigdestcidFro; "OrigDestCID from Retry OOM"
0x140015ede  mov     rdx, rbx
0x140015ee1  mov     rcx, rdi
0x140015ee4  call    QuicPacketLogDrop
0x140015ee9  xor     al, al
0x140015eeb  jmp     loc_1400161E7
0x140015ef0  movzx   eax, byte ptr [rbp+57h+var_90+8]
0x140015ef4  lea     rdx, [rbp+57h+Src+4]; Src
0x140015ef8  mov     [rcx+1], al
0x140015efb  mov     rcx, [rdi+518h]
0x140015f02  movzx   r8d, byte ptr [rbp+57h+var_90+8]; Size
0x140015f07  add     rcx, 10h; void *
0x140015f0b  call    memmove
0x140015f10  or      byte ptr [rdi+0FAh], 1
0x140015f17  lea     rdx, [rdi+140h]
0x140015f1e  xor     r8d, r8d
0x140015f21  mov     rcx, rdi
0x140015f24  call    QuicPathSetValid
0x140015f29  cmp     [rdi+518h], r15
0x140015f30  jnz     loc_140015FBB
0x140015f36  movzx   edx, byte ptr [rbx+56h]
0x140015f3a  mov     ecx, 42h ; 'B'
0x140015f3f  add     rdx, 10h
0x140015f43  mov     r8d, 43306351h
0x140015f49  call    cs:__imp_ExAllocatePool2
0x140015f50  nop     dword ptr [rax+rax+00h]
0x140015f55  mov     [rdi+518h], rax
0x140015f5c  mov     rcx, rax
0x140015f5f  test    rax, rax
0x140015f62  jnz     short loc_140015F9B
0x140015f64  test    cs:Microsoft_QuicEnableBits, 2
0x140015f6b  jz      short loc_140015F82
0x140015f6d  movzx   r9d, byte ptr [rbx+56h]
0x140015f72  lea     r8, aOrigdestcid; "OrigDestCID"
0x140015f79  add     r9, 10h
0x140015f7d  call    McTemplateU0sx_EtwWriteTransfer
0x140015f82  lea     r8, aOrigdestcidOom; "OrigDestCID OOM"
0x140015f89  mov     rdx, rbx
0x140015f8c  mov     rcx, rdi
0x140015f8f  call    QuicPacketLogDrop
0x140015f94  xor     al, al
0x140015f96  jmp     loc_1400161E7
0x140015f9b  movzx   eax, byte ptr [rbx+56h]
0x140015f9f  mov     [rcx+1], al
0x140015fa2  mov     rcx, [rdi+518h]
0x140015fa9  movzx   r8d, byte ptr [rbx+56h]; Size
0x140015fae  add     rcx, 10h; void *
0x140015fb2  mov     rdx, [rbx+40h]; Src
0x140015fb6  call    memmove
0x140015fbb  mov     rax, [rbx+38h]
0x140015fbf  movzx   ecx, byte ptr [rax]
0x140015fc2  shr     cl, 4
0x140015fc5  and     cl, 3
0x140015fc8  cmp     dword ptr [rax+1], 0CF43336Bh
0x140015fcf  jnz     short loc_140015FE5
0x140015fd1  call    QuicPacketTypeToKeyTypeV2
0x140015fd6  movzx   edx, byte ptr [rbx+5Ch]
0x140015fda  mov     r8d, eax
0x140015fdd  or      dl, 40h
0x140015fe0  mov     [rbx+58h], eax
0x140015fe3  jmp     short loc_140016062
0x140015fe5  call    QuicPacketTypeToKeyTypeV1
0x140015fea  movzx   edx, byte ptr [rbx+5Ch]
0x140015fee  mov     r8d, eax
0x140015ff1  or      dl, 40h
0x140015ff4  mov     [rbx+58h], eax
0x140015ff7  jmp     short loc_140016062
0x140015ff9  test    dl, 8
0x140015ffc  jnz     short loc_14001603B
0x140015ffe  cmp     [rdi+0EBh], r15b
0x140016005  jl      short loc_140016029
0x140016007  mov     rax, [rbx+38h]
0x14001600b  test    byte ptr [rax], 40h
0x14001600e  jnz     short loc_140016029
0x140016010  lea     r8, aInvalidShFixed; "Invalid SH FixedBit bits values"
0x140016017  mov     rcx, rdi
0x14001601a  mov     rdx, rbx
0x14001601d  call    QuicPacketLogDrop
0x140016022  xor     al, al
0x140016024  jmp     loc_1400161E7
0x140016029  movzx   ecx, word ptr [rbx+50h]
0x14001602d  sub     cx, [rbx+52h]
0x140016031  or      dl, 8
0x140016034  mov     [rbx+54h], cx
0x140016038  mov     [rbx+5Ch], dl
0x14001603b  mov     r8d, 3
0x140016041  mov     [rbx+58h], r8d
0x140016045  test    byte ptr [rdi+0F9h], 10h
0x14001604c  jnz     short loc_14001605B
0x14001604e  test    byte ptr [rdi+142h], 20h
  ... truncated ...
```
