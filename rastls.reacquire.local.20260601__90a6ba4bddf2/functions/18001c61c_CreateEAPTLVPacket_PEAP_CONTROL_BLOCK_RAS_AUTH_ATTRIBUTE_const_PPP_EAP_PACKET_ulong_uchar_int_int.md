# CreateEAPTLVPacket(_PEAP_CONTROL_BLOCK *,_RAS_AUTH_ATTRIBUTE const *,_PPP_EAP_PACKET *,ulong,uchar *,int,int)

- ea: `0x18001c61c`
- end: `0x18001cbe9`
- name: `?CreateEAPTLVPacket@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEBU_RAS_AUTH_ATTRIBUTE@@PEAU_PPP_EAP_PACKET@@KPEAEHH@Z`
- size: `1485`
- prototype: `unsigned int __usercall@<eax>(struct _PEAP_CONTROL_BLOCK *@<rcx>, const struct _RAS_AUTH_ATTRIBUTE *@<rdx>, struct _PPP_EAP_PACKET *@<r8>, unsigned int@<r9d>, unsigned __int8 *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180009418`
- `0x180060968`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18001c61c`
- `0x18001cbf0`
- `0x180038270`
- `0x180038e4c`
- `0x18004d58c`
- `0x1800602c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c9e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c9e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9cc`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001cb06`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001cb90`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001cb06`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001cb90`
- `eapputil!EapConvertHostToWireFormat32` at `0x18001caec`
- `eapputil!EapConvertHostToWireFormat32` at `0x18001caec`
- `eapputil!EapConvertWireToHostFormat16` at `0x18001c77f`
- `eapputil!EapConvertWireToHostFormat16` at `0x18001c77f`
- `rtutils!TraceDumpExA` at `0x18001c764`
- `rtutils!TraceDumpExA` at `0x18001c764`

## pseudocode

```c
__int64 __fastcall CreateEAPTLVPacket(
        struct _PEAP_CONTROL_BLOCK *a1,
        const struct _RAS_AUTH_ATTRIBUTE *a2,
        struct _PPP_EAP_PACKET *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        int a6,
        int a7)
{
  unsigned int v7; // r13d
  struct _EAPTLS_CONTROL_BLOCK *v11; // rcx
  unsigned int v12; // r14d
  DWORD CryptoBindingTLV; // ebx
  DWORD v14; // eax
  BYTE *v15; // r12
  __int64 raaType; // r9
  _BYTE *Value; // r13
  __int16 v18; // r12
  struct _EAPTLS_CONTROL_BLOCK *v19; // rcx
  DWORD v20; // r15d
  void *v21; // rcx
  _OWORD *v22; // rax
  struct _EAPTLS_CONTROL_BLOCK *v23; // rcx
  __int64 v24; // rdx
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  BYTE *v28; // rdx
  BYTE v29; // cl
  BYTE Code; // al
  size_t v31; // r8
  BOOL bAddressPrefix; // [rsp+28h] [rbp-89h]
  DWORD v34; // [rsp+40h] [rbp-71h]
  int v35; // [rsp+44h] [rbp-6Dh]
  BYTE *v36; // [rsp+48h] [rbp-69h]
  __int128 v38; // [rsp+60h] [rbp-51h] BYREF
  __int128 v39; // [rsp+70h] [rbp-41h]
  _OWORD v40[2]; // [rsp+80h] [rbp-31h] BYREF

  v7 = a4;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  v12 = a6 != 0 ? 14 : 11;
  if ( v7 < v12 )
  {
    if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_DD(*((_QWORD *)v11 + 2), 22, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, v7, v12);
    return 234;
  }
  v14 = 0;
  CryptoBindingTLV = 0;
  v34 = 0;
  v35 = 0;
  v15 = &a3->Code + v12;
  while ( 1 )
  {
    v36 = v15;
    if ( !a2 )
      break;
    raaType = (unsigned int)a2->raaType;
    if ( !(_DWORD)raaType )
      break;
    if ( (_DWORD)raaType != 8102 )
    {
      if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_DD(*((_QWORD *)v11 + 2), 23, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, raaType, 8102);
LABEL_33:
        v11 = WPP_GLOBAL_Control;
      }
LABEL_34:
      CryptoBindingTLV = 1359;
      break;
    }
    v34 = a2->dwLength + v14;
    if ( v12 + v34 > v7 )
    {
      if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v11 + 2), 24, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
        goto LABEL_33;
      }
      goto LABEL_34;
    }
    Value = a2->Value;
    if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v11 + 2), 25, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
    TraceDumpExA(g_dwEapTlsTraceId, 1u, (LPBYTE)a2->Value, a2->dwLength, 1u, 1, 0);
    if ( Value[1] == 3 )
    {
      v18 = EapConvertWireToHostFormat16(Value + 4);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
        v19 = WPP_GLOBAL_Control;
      }
      if ( v18 == 1 )
      {
        if ( v19 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)v19 + 2), 27, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
        if ( a7 || *((_QWORD *)a1 + 349) )
          v35 = 1;
      }
      else if ( v19 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v19 + 2), 28, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
      }
      v15 = v36;
    }
    else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids,
        (unsigned __int8)Value[1]);
    }
    memcpy_0(v15, a2->Value, a2->dwLength);
    v11 = WPP_GLOBAL_Control;
    v15 += a2->dwLength;
    v7 = a4;
    ++a2;
    v14 = v34;
  }
  if ( v35 )
  {
    if ( CryptoBindingTLV )
      return CryptoBindingTLV;
    memset(v40, 0, 28);
    v38 = 0;
    v39 = 0;
    if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)v11 + 2), 30, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    memset(v40, 0, 28);
    v38 = 0;
    v39 = 0;
    if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)v11 + 2), 31, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    v20 = v34 + 60;
    v34 = v20;
    if ( v20 + v12 > v7 )
    {
      if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v11 + 2), 32, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
      return 1359;
    }
    CryptoBindingTLV = CreateCryptoBindingTLV(a1, 0, (struct _CRYPTO_BINDING_TLV *)&v38, a5, a7, bAddressPrefix);
    if ( CryptoBindingTLV )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        return CryptoBindingTLV;
      v24 = 34;
      goto LABEL_52;
    }
    if ( a7 )
    {
      v21 = (void *)*((_QWORD *)a1 + 349);
      if ( v21 )
        LocalFree(v21);
      v22 = LocalAlloc(0x40u, 0x3Cu);
      *((_QWORD *)a1 + 349) = v22;
      if ( !v22 )
      {
        CryptoBindingTLV = GetLastError();
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          return CryptoBindingTLV;
        v24 = 33;
LABEL_52:
        WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, CryptoBindingTLV);
        return CryptoBindingTLV;
      }
      *v22 = v38;
      v22[1] = v39;
      v22[2] = v40[0];
      *(_OWORD *)((char *)v22 + 44) = *(_OWORD *)((char *)v40 + 12);
    }
    v25 = v39;
    *(_OWORD *)v15 = v38;
    v26 = v40[0];
    *((_OWORD *)v15 + 1) = v25;
    v27 = *(_OWORD *)((char *)v40 + 12);
    *((_OWORD *)v15 + 2) = v26;
    *(_OWORD *)(v15 + 44) = v27;
  }
  else
  {
    if ( CryptoBindingTLV )
      return CryptoBindingTLV;
    v20 = v34;
  }
  if ( a7 )
  {
    a3->Code = 1;
    ++*((_BYTE *)a1 + 16);
  }
  else
  {
    a3->Code = 2;
  }
  v28 = &a3[1].Length[1];
  v29 = *((_BYTE *)a1 + 16);
  a3->Id = v29;
  *(_WORD *)a3->Data = 25;
  if ( a6 )
  {
    *v28 = 1;
    *(_WORD *)&a3[1].Id = 254;
    a3[1].Data[0] = 55;
    EapConvertHostToWireFormat32(33, &a3[2]);
  }
  else
  {
    Code = a3->Code;
    a3[1].Length[0] = v29;
    a3[1].Id = Code;
    EapConvertHostToWireFormat16(v20 + 5, v28);
    a3[2].Code = 33;
  }
  CryptoBindingTLV = PeapEncryptTunnelData(a1, &a3[1].Id, v12 + v34 - 6);
  if ( !CryptoBindingTLV )
  {
    v31 = *((unsigned int *)a1 + 684);
    if ( v31 <= (unsigned __int64)v7 - 6 )
    {
      memcpy_0(&a3[1].Id, *((const void **)a1 + 341), v31);
      EapConvertHostToWireFormat16((unsigned __int16)(*((_WORD *)a1 + 1368) + 6), a3->Length);
      return CryptoBindingTLV;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, v7 - 6, v31);
    return 234;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
  return CryptoBindingTLV;
}

```

## disassembly

```asm
0x18001c61c  push    rbp
0x18001c61e  push    rbx
0x18001c61f  push    rsi
0x18001c620  push    rdi
0x18001c621  push    r12
0x18001c623  push    r13
0x18001c625  push    r14
0x18001c627  push    r15
0x18001c629  lea     rbp, [rsp-7]
0x18001c62e  sub     rsp, 0B8h
0x18001c635  mov     rax, cs:__security_cookie
0x18001c63c  xor     rax, rsp
0x18001c63f  mov     [rbp+3Fh+var_50], rax
0x18001c643  mov     rax, [rbp+3Fh+arg_20]
0x18001c647  mov     r13d, r9d
0x18001c64a  mov     [rbp+3Fh+var_98], rax
0x18001c64e  mov     rdi, r8
0x18001c651  mov     [rbp+3Fh+var_A0], r9d
0x18001c655  mov     r15, rdx
0x18001c658  mov     rsi, rcx
0x18001c65b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c662  lea     rdx, WPP_GLOBAL_Control
0x18001c669  cmp     rcx, rdx
0x18001c66c  jz      short loc_18001C691
0x18001c66e  mov     rcx, [rcx+10h]
0x18001c672  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c679  mov     edx, 15h
0x18001c67e  call    WPP_SF_
0x18001c683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c68a  lea     rdx, WPP_GLOBAL_Control
0x18001c691  mov     eax, [rbp+3Fh+arg_28]
0x18001c694  neg     eax
0x18001c696  sbb     r14d, r14d
0x18001c699  and     r14d, 3
0x18001c69d  add     r14d, 0Bh
0x18001c6a1  cmp     r13d, r14d
0x18001c6a4  jnb     short loc_18001C6D2
0x18001c6a6  cmp     rcx, rdx
0x18001c6a9  jz      short loc_18001C6C8
0x18001c6ab  mov     edx, 16h
0x18001c6b0  mov     [rsp+0F0h+dwGroupSize], r14d
0x18001c6b5  mov     r9d, r13d
0x18001c6b8  mov     rcx, [rcx+10h]
0x18001c6bc  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c6c3  call    WPP_SF_DD
0x18001c6c8  mov     ebx, 0EAh
0x18001c6cd  jmp     loc_18001CBC6
0x18001c6d2  xor     eax, eax
0x18001c6d4  mov     r12d, r14d
0x18001c6d7  xor     ebx, ebx
0x18001c6d9  mov     [rbp+3Fh+var_B0], eax
0x18001c6dc  mov     [rbp+3Fh+var_AC], eax
0x18001c6df  add     r12, rdi
0x18001c6e2  mov     [rbp+3Fh+var_A8], r12
0x18001c6e6  mov     r10d, 1
0x18001c6ec  test    r15, r15
0x18001c6ef  jz      loc_18001C8D5
0x18001c6f5  mov     r9d, [r15]
0x18001c6f8  test    r9d, r9d
0x18001c6fb  jz      loc_18001C8D5
0x18001c701  cmp     r9d, 1FA6h
0x18001c708  jnz     loc_18001C8A0
0x18001c70e  add     eax, [r15+4]
0x18001c712  mov     [rbp+3Fh+var_B0], eax
0x18001c715  add     eax, r14d
0x18001c718  cmp     eax, r13d
0x18001c71b  ja      loc_18001C884
0x18001c721  mov     r13, [r15+8]
0x18001c725  cmp     rcx, rdx
0x18001c728  jz      short loc_18001C744
0x18001c72a  mov     rcx, [rcx+10h]
0x18001c72e  lea     edx, [r10+18h]
0x18001c732  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c739  call    WPP_SF_
0x18001c73e  mov     r10d, 1
0x18001c744  mov     r9d, [r15+4]; dwByteCount
0x18001c748  mov     edx, r10d; dwFlags
0x18001c74b  mov     r8, [r15+8]; lpbBytes
0x18001c74f  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x18001c755  mov     [rsp+0F0h+lpszPrefix], rbx; lpszPrefix
0x18001c75a  mov     [rsp+0F0h+bAddressPrefix], r10d; bAddressPrefix
0x18001c75f  mov     [rsp+0F0h+dwGroupSize], r10d; dwGroupSize
0x18001c764  call    cs:__imp_TraceDumpExA
0x18001c76b  nop     dword ptr [rax+rax+00h]
0x18001c770  cmp     byte ptr [r13+1], 3
0x18001c775  jnz     loc_18001C855
0x18001c77b  lea     rcx, [r13+4]
0x18001c77f  call    cs:__imp_EapConvertWireToHostFormat16
0x18001c786  nop     dword ptr [rax+rax+00h]
0x18001c78b  movzx   r12d, ax
0x18001c78f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c796  lea     rax, WPP_GLOBAL_Control
0x18001c79d  cmp     rcx, rax
0x18001c7a0  jz      short loc_18001C7C5
0x18001c7a2  mov     rcx, [rcx+10h]
0x18001c7a6  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c7ad  mov     edx, 1Ah
0x18001c7b2  call    WPP_SF_
0x18001c7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7be  lea     rax, WPP_GLOBAL_Control
0x18001c7c5  mov     edx, 1
0x18001c7ca  cmp     r12w, dx
0x18001c7ce  jnz     short loc_18001C839
0x18001c7d0  cmp     rcx, rax
0x18001c7d3  jz      short loc_18001C7EF
0x18001c7d5  mov     rcx, [rcx+10h]
0x18001c7d9  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c7e0  mov     edx, 1Bh
0x18001c7e5  call    WPP_SF_
0x18001c7ea  mov     edx, 1
0x18001c7ef  cmp     [rbp+3Fh+arg_30], ebx
0x18001c7f2  jnz     short loc_18001C7FD
0x18001c7f4  cmp     [rsi+0AE8h], rbx
0x18001c7fb  jz      short loc_18001C800
0x18001c7fd  mov     [rbp+3Fh+var_AC], edx
0x18001c800  mov     r12, [rbp+3Fh+var_A8]
0x18001c804  mov     r8d, [r15+4]; Size
0x18001c808  mov     rcx, r12; void *
0x18001c80b  mov     rdx, [r15+8]; Src
0x18001c80f  call    memcpy_0
0x18001c814  mov     eax, [r15+4]
0x18001c818  lea     rdx, WPP_GLOBAL_Control
0x18001c81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c826  add     r12, rax
0x18001c829  mov     r13d, [rbp+3Fh+var_A0]
0x18001c82d  add     r15, 10h
0x18001c831  mov     eax, [rbp+3Fh+var_B0]
0x18001c834  jmp     loc_18001C6E2
0x18001c839  cmp     rcx, rax
0x18001c83c  jz      short loc_18001C800
0x18001c83e  mov     rcx, [rcx+10h]
0x18001c842  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c849  mov     edx, 1Ch
0x18001c84e  call    WPP_SF_
0x18001c853  jmp     short loc_18001C800
0x18001c855  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c85c  lea     rax, WPP_GLOBAL_Control
0x18001c863  cmp     rcx, rax
0x18001c866  jz      short loc_18001C804
0x18001c868  movzx   r9d, byte ptr [r13+1]
0x18001c86d  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c874  mov     rcx, [rcx+10h]
0x18001c878  mov     edx, 1Dh
0x18001c87d  call    WPP_SF_d
0x18001c882  jmp     short loc_18001C804
0x18001c884  cmp     rcx, rdx
0x18001c887  jz      short loc_18001C8D0
0x18001c889  mov     rcx, [rcx+10h]
0x18001c88d  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c894  mov     edx, 18h
0x18001c899  call    WPP_SF_
0x18001c89e  jmp     short loc_18001C8C2
0x18001c8a0  cmp     rcx, rdx
0x18001c8a3  jz      short loc_18001C8D0
0x18001c8a5  mov     rcx, [rcx+10h]
0x18001c8a9  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c8b0  mov     edx, 17h
0x18001c8b5  mov     [rsp+0F0h+dwGroupSize], 1FA6h
0x18001c8bd  call    WPP_SF_DD
0x18001c8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8c9  lea     rdx, WPP_GLOBAL_Control
0x18001c8d0  mov     ebx, 54Fh
0x18001c8d5  cmp     [rbp+3Fh+var_AC], 0
0x18001c8d9  jz      loc_18001CAA0
0x18001c8df  test    ebx, ebx
0x18001c8e1  jnz     loc_18001CBC6
0x18001c8e7  xorps   xmm0, xmm0
0x18001c8ea  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18001c8ee  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x18001c8f2  movups  [rbp+3Fh+var_90], xmm0
0x18001c8f6  movups  [rbp+3Fh+var_80], xmm0
0x18001c8fa  cmp     rcx, rdx
0x18001c8fd  jz      short loc_18001C920
0x18001c8ff  mov     rcx, [rcx+10h]
0x18001c903  lea     edx, [rbx+1Eh]
0x18001c906  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c90d  call    WPP_SF_
0x18001c912  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c919  lea     rdx, WPP_GLOBAL_Control
0x18001c920  xorps   xmm0, xmm0
0x18001c923  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18001c927  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x18001c92b  movups  [rbp+3Fh+var_90], xmm0
0x18001c92f  movups  [rbp+3Fh+var_80], xmm0
0x18001c933  cmp     rcx, rdx
0x18001c936  jz      short loc_18001C95B
0x18001c938  mov     rcx, [rcx+10h]
0x18001c93c  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c943  mov     edx, 1Fh
0x18001c948  call    WPP_SF_
0x18001c94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c954  lea     rdx, WPP_GLOBAL_Control
0x18001c95b  mov     r15d, [rbp+3Fh+var_B0]
0x18001c95f  add     r15d, 3Ch ; '<'
0x18001c963  mov     [rbp+3Fh+var_B0], r15d
0x18001c967  lea     eax, [r15+r14]
0x18001c96b  cmp     eax, r13d
0x18001c96e  jbe     short loc_18001C994
0x18001c970  cmp     rcx, rdx
0x18001c973  jz      short loc_18001C98A
0x18001c975  mov     rcx, [rcx+10h]
0x18001c979  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001c980  mov     edx, 20h ; ' '
0x18001c985  call    WPP_SF_
0x18001c98a  mov     ebx, 54Fh
0x18001c98f  jmp     loc_18001CBC6
0x18001c994  mov     eax, [rbp+3Fh+arg_30]
0x18001c997  lea     r8, [rbp+3Fh+var_90]; struct _CRYPTO_BINDING_TLV *
0x18001c99b  mov     r9, [rbp+3Fh+var_98]; unsigned __int8 *
0x18001c99f  xor     edx, edx; unsigned __int8 *
0x18001c9a1  mov     rcx, rsi; struct _PEAP_CONTROL_BLOCK *
0x18001c9a4  mov     [rsp+0F0h+dwGroupSize], eax; int
0x18001c9a8  call    ?CreateCryptoBindingTLV@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEPEAU_CRYPTO_BINDING_TLV@@1HH@Z; CreateCryptoBindingTLV(_PEAP_CONTROL_BLOCK *,uchar *,_CRYPTO_BINDING_TLV *,uchar *,int,int)
0x18001c9ad  mov     ebx, eax
0x18001c9af  test    eax, eax
0x18001c9b1  jnz     loc_18001CA82
0x18001c9b7  cmp     [rbp+3Fh+arg_30], eax
0x18001c9ba  jz      loc_18001CA59
0x18001c9c0  mov     rcx, [rsi+0AE8h]; hMem
0x18001c9c7  test    rcx, rcx
0x18001c9ca  jz      short loc_18001C9D8
0x18001c9cc  call    cs:__imp_LocalFree
0x18001c9d3  nop     dword ptr [rax+rax+00h]
0x18001c9d8  mov     edx, 3Ch ; '<'; uBytes
0x18001c9dd  lea     ecx, [rdx+4]; uFlags
0x18001c9e0  call    cs:__imp_LocalAlloc
0x18001c9e7  nop     dword ptr [rax+rax+00h]
0x18001c9ec  mov     [rsi+0AE8h], rax
0x18001c9f3  test    rax, rax
0x18001c9f6  jnz     short loc_18001CA3A
0x18001c9f8  call    cs:__imp_GetLastError
0x18001c9ff  nop     dword ptr [rax+rax+00h]
0x18001ca04  mov     ebx, eax
0x18001ca06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca0d  lea     rax, WPP_GLOBAL_Control
0x18001ca14  cmp     rcx, rax
0x18001ca17  jz      loc_18001CBC6
0x18001ca1d  mov     edx, 21h ; '!'
0x18001ca22  mov     rcx, [rcx+10h]
0x18001ca26  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001ca2d  mov     r9d, ebx
0x18001ca30  call    WPP_SF_d
0x18001ca35  jmp     loc_18001CBC6
0x18001ca3a  movups  xmm0, [rbp+3Fh+var_90]
0x18001ca3e  movups  xmmword ptr [rax], xmm0
0x18001ca41  movups  xmm1, [rbp+3Fh+var_80]
0x18001ca45  movups  xmmword ptr [rax+10h], xmm1
0x18001ca49  movups  xmm0, xmmword ptr [rbp+3Fh+var_70]
0x18001ca4d  movups  xmmword ptr [rax+20h], xmm0
0x18001ca51  movups  xmm1, xmmword ptr [rbp+3Fh+var_70+0Ch]
0x18001ca55  movups  xmmword ptr [rax+2Ch], xmm1
0x18001ca59  movups  xmm0, [rbp+3Fh+var_90]
0x18001ca5d  movups  xmm1, [rbp+3Fh+var_80]
0x18001ca61  movups  xmmword ptr [r12], xmm0
0x18001ca66  movups  xmm0, xmmword ptr [rbp+3Fh+var_70]
0x18001ca6a  movups  xmmword ptr [r12+10h], xmm1
0x18001ca70  movups  xmm1, xmmword ptr [rbp+3Fh+var_70+0Ch]
0x18001ca74  movups  xmmword ptr [r12+20h], xmm0
0x18001ca7a  movups  xmmword ptr [r12+2Ch], xmm1
0x18001ca80  jmp     short loc_18001CAAC
0x18001ca82  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca89  lea     rax, WPP_GLOBAL_Control
0x18001ca90  cmp     rcx, rax
0x18001ca93  jz      loc_18001CBC6
0x18001ca99  mov     edx, 22h ; '"'
0x18001ca9e  jmp     short loc_18001CA22
0x18001caa0  test    ebx, ebx
0x18001caa2  jnz     loc_18001CBC6
0x18001caa8  mov     r15d, [rbp+3Fh+var_B0]
0x18001caac  cmp     [rbp+3Fh+arg_30], 0
0x18001cab0  mov     eax, 1
0x18001cab5  jz      short loc_18001CABE
0x18001cab7  mov     [rdi], al
0x18001cab9  add     [rsi+10h], al
0x18001cabc  jmp     short loc_18001CAC1
0x18001cabe  mov     byte ptr [rdi], 2
0x18001cac1  cmp     [rbp+3Fh+arg_28], 0
0x18001cac5  lea     rdx, [rdi+8]
0x18001cac9  mov     cl, [rsi+10h]
0x18001cacc  mov     [rdi+1], cl
0x18001cacf  mov     word ptr [rdi+4], 19h
0x18001cad5  jz      short loc_18001CAFA
0x18001cad7  mov     [rdx], al
0x18001cad9  mov     ecx, 21h ; '!'
0x18001cade  lea     rdx, [rdi+0Ah]
0x18001cae2  mov     word ptr [rdi+6], 0FEh
0x18001cae8  mov     byte ptr [rdi+9], 37h ; '7'
0x18001caec  call    cs:__imp_EapConvertHostToWireFormat32
0x18001caf3  nop     dword ptr [rax+rax+00h]
0x18001caf8  jmp     short loc_18001CB16
0x18001cafa  mov     al, [rdi]
0x18001cafc  mov     [rdi+7], cl
0x18001caff  lea     ecx, [r15+5]
0x18001cb03  mov     [rdi+6], al
0x18001cb06  call    cs:__imp_EapConvertHostToWireFormat16
0x18001cb0d  nop     dword ptr [rax+rax+00h]
0x18001cb12  mov     byte ptr [rdi+0Ah], 21h ; '!'
0x18001cb16  mov     r8d, [rbp+3Fh+var_B0]
0x18001cb1a  lea     rdx, [rdi+6]; Src
0x18001cb1e  add     r8d, 0FFFFFFFAh
  ... truncated ...
```
