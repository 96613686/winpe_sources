# CreateEAPTLVPacket(_PEAP_CONTROL_BLOCK *,_RAS_AUTH_ATTRIBUTE const *,_PPP_EAP_PACKET *,ulong,uchar *,int,int)

- ea: `0x18001ac80`
- end: `0x18001b21c`
- name: `?CreateEAPTLVPacket@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEBU_RAS_AUTH_ATTRIBUTE@@PEAU_PPP_EAP_PACKET@@KPEAEHH@Z`
- size: `1436`
- prototype: `__int64 __fastcall(struct _PEAP_CONTROL_BLOCK *, const struct _RAS_AUTH_ATTRIBUTE *, struct _PPP_EAP_PACKET *, unsigned int, unsigned __int8 *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180008b28`
- `0x18005d1f4`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001ac80`
- `0x18001b230`
- `0x180035680`
- `0x18003623c`
- `0x18004acb8`
- `0x18005cc50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b044`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b032`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b032`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b024`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001b146`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001b1ca`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001b146`
- `eapputil!EapConvertHostToWireFormat16` at `0x18001b1ca`
- `eapputil!EapConvertHostToWireFormat32` at `0x18001b132`
- `eapputil!EapConvertHostToWireFormat32` at `0x18001b132`
- `eapputil!EapConvertWireToHostFormat16` at `0x18001addd`
- `eapputil!EapConvertWireToHostFormat16` at `0x18001addd`
- `rtutils!TraceDumpExA` at `0x18001adc8`
- `rtutils!TraceDumpExA` at `0x18001adc8`

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
      WPP_SF_dd(*((_QWORD *)v11 + 2), 22, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, v7, v12);
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
        WPP_SF_dd(*((_QWORD *)v11 + 2), 23, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, raaType, 8102);
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
      EapConvertHostToWireFormat16((unsigned __int16)(CryptoBindingTLV + 6 + *((_WORD *)a1 + 1368)), a3->Length);
      return CryptoBindingTLV;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        CryptoBindingTLV + 35,
        WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids,
        v7 - 6,
        v31);
    return 234;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
  return CryptoBindingTLV;
}

```

## disassembly

```asm
0x18001ac80  push    rbp
0x18001ac82  push    rbx
0x18001ac83  push    rsi
0x18001ac84  push    rdi
0x18001ac85  push    r12
0x18001ac87  push    r13
0x18001ac89  push    r14
0x18001ac8b  push    r15
0x18001ac8d  lea     rbp, [rsp-7]
0x18001ac92  sub     rsp, 0B8h
0x18001ac99  mov     rax, cs:__security_cookie
0x18001aca0  xor     rax, rsp
0x18001aca3  mov     [rbp+3Fh+var_50], rax
0x18001aca7  mov     rax, [rbp+3Fh+arg_20]
0x18001acab  mov     r13d, r9d
0x18001acae  mov     [rbp+3Fh+var_98], rax
0x18001acb2  mov     rdi, r8
0x18001acb5  mov     [rbp+3Fh+var_A0], r9d
0x18001acb9  mov     r15, rdx
0x18001acbc  mov     rsi, rcx
0x18001acbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acc6  lea     rdx, WPP_GLOBAL_Control
0x18001accd  cmp     rcx, rdx
0x18001acd0  jz      short loc_18001ACF5
0x18001acd2  mov     rcx, [rcx+10h]
0x18001acd6  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001acdd  mov     edx, 15h
0x18001ace2  call    WPP_SF_
0x18001ace7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acee  lea     rdx, WPP_GLOBAL_Control
0x18001acf5  mov     eax, [rbp+3Fh+arg_28]
0x18001acf8  neg     eax
0x18001acfa  sbb     r14d, r14d
0x18001acfd  and     r14d, 3
0x18001ad01  add     r14d, 0Bh
0x18001ad05  cmp     r13d, r14d
0x18001ad08  jnb     short loc_18001AD36
0x18001ad0a  cmp     rcx, rdx
0x18001ad0d  jz      short loc_18001AD2C
0x18001ad0f  mov     edx, 16h
0x18001ad14  mov     [rsp+0F0h+dwGroupSize], r14d
0x18001ad19  mov     r9d, r13d
0x18001ad1c  mov     rcx, [rcx+10h]
0x18001ad20  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001ad27  call    WPP_SF_dd
0x18001ad2c  mov     ebx, 0EAh
0x18001ad31  jmp     loc_18001B1FA
0x18001ad36  xor     eax, eax
0x18001ad38  mov     r12d, r14d
0x18001ad3b  xor     ebx, ebx
0x18001ad3d  mov     [rbp+3Fh+var_B0], eax
0x18001ad40  mov     [rbp+3Fh+var_AC], eax
0x18001ad43  add     r12, rdi
0x18001ad46  mov     [rbp+3Fh+var_A8], r12
0x18001ad4a  mov     r10d, 1
0x18001ad50  test    r15, r15
0x18001ad53  jz      loc_18001AF2D
0x18001ad59  mov     r9d, [r15]
0x18001ad5c  test    r9d, r9d
0x18001ad5f  jz      loc_18001AF2D
0x18001ad65  cmp     r9d, 1FA6h
0x18001ad6c  jnz     loc_18001AEF8
0x18001ad72  add     eax, [r15+4]
0x18001ad76  mov     [rbp+3Fh+var_B0], eax
0x18001ad79  add     eax, r14d
0x18001ad7c  cmp     eax, r13d
0x18001ad7f  ja      loc_18001AEDC
0x18001ad85  mov     r13, [r15+8]
0x18001ad89  cmp     rcx, rdx
0x18001ad8c  jz      short loc_18001ADA8
0x18001ad8e  mov     rcx, [rcx+10h]
0x18001ad92  lea     edx, [r10+18h]
0x18001ad96  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001ad9d  call    WPP_SF_
0x18001ada2  mov     r10d, 1
0x18001ada8  mov     r9d, [r15+4]; dwByteCount
0x18001adac  mov     edx, r10d; dwFlags
0x18001adaf  mov     r8, [r15+8]; lpbBytes
0x18001adb3  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x18001adb9  mov     [rsp+0F0h+lpszPrefix], rbx; lpszPrefix
0x18001adbe  mov     [rsp+0F0h+bAddressPrefix], r10d; bAddressPrefix
0x18001adc3  mov     [rsp+0F0h+dwGroupSize], r10d; dwGroupSize
0x18001adc8  call    cs:__imp_TraceDumpExA
0x18001adce  cmp     byte ptr [r13+1], 3
0x18001add3  jnz     loc_18001AEAD
0x18001add9  lea     rcx, [r13+4]
0x18001addd  call    cs:__imp_EapConvertWireToHostFormat16
0x18001ade3  movzx   r12d, ax
0x18001ade7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adee  lea     rax, WPP_GLOBAL_Control
0x18001adf5  cmp     rcx, rax
0x18001adf8  jz      short loc_18001AE1D
0x18001adfa  mov     rcx, [rcx+10h]
0x18001adfe  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001ae05  mov     edx, 1Ah
0x18001ae0a  call    WPP_SF_
0x18001ae0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae16  lea     rax, WPP_GLOBAL_Control
0x18001ae1d  mov     edx, 1
0x18001ae22  cmp     r12w, dx
0x18001ae26  jnz     short loc_18001AE91
0x18001ae28  cmp     rcx, rax
0x18001ae2b  jz      short loc_18001AE47
0x18001ae2d  mov     rcx, [rcx+10h]
0x18001ae31  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001ae38  mov     edx, 1Bh
0x18001ae3d  call    WPP_SF_
0x18001ae42  mov     edx, 1
0x18001ae47  cmp     [rbp+3Fh+arg_30], ebx
0x18001ae4a  jnz     short loc_18001AE55
0x18001ae4c  cmp     [rsi+0AE8h], rbx
0x18001ae53  jz      short loc_18001AE58
0x18001ae55  mov     [rbp+3Fh+var_AC], edx
0x18001ae58  mov     r12, [rbp+3Fh+var_A8]
0x18001ae5c  mov     r8d, [r15+4]; Size
0x18001ae60  mov     rcx, r12; void *
0x18001ae63  mov     rdx, [r15+8]; Src
0x18001ae67  call    memcpy_0
0x18001ae6c  mov     eax, [r15+4]
0x18001ae70  lea     rdx, WPP_GLOBAL_Control
0x18001ae77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae7e  add     r12, rax
0x18001ae81  mov     r13d, [rbp+3Fh+var_A0]
0x18001ae85  add     r15, 10h
0x18001ae89  mov     eax, [rbp+3Fh+var_B0]
0x18001ae8c  jmp     loc_18001AD46
0x18001ae91  cmp     rcx, rax
0x18001ae94  jz      short loc_18001AE58
0x18001ae96  mov     rcx, [rcx+10h]
0x18001ae9a  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001aea1  mov     edx, 1Ch
0x18001aea6  call    WPP_SF_
0x18001aeab  jmp     short loc_18001AE58
0x18001aead  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aeb4  lea     rax, WPP_GLOBAL_Control
0x18001aebb  cmp     rcx, rax
0x18001aebe  jz      short loc_18001AE5C
0x18001aec0  movzx   r9d, byte ptr [r13+1]
0x18001aec5  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001aecc  mov     rcx, [rcx+10h]
0x18001aed0  mov     edx, 1Dh
0x18001aed5  call    WPP_SF_d
0x18001aeda  jmp     short loc_18001AE5C
0x18001aedc  cmp     rcx, rdx
0x18001aedf  jz      short loc_18001AF28
0x18001aee1  mov     rcx, [rcx+10h]
0x18001aee5  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001aeec  mov     edx, 18h
0x18001aef1  call    WPP_SF_
0x18001aef6  jmp     short loc_18001AF1A
0x18001aef8  cmp     rcx, rdx
0x18001aefb  jz      short loc_18001AF28
0x18001aefd  mov     rcx, [rcx+10h]
0x18001af01  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001af08  mov     edx, 17h
0x18001af0d  mov     [rsp+0F0h+dwGroupSize], 1FA6h
0x18001af15  call    WPP_SF_dd
0x18001af1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af21  lea     rdx, WPP_GLOBAL_Control
0x18001af28  mov     ebx, 54Fh
0x18001af2d  cmp     [rbp+3Fh+var_AC], 0
0x18001af31  jz      loc_18001B0E6
0x18001af37  test    ebx, ebx
0x18001af39  jnz     loc_18001B1FA
0x18001af3f  xorps   xmm0, xmm0
0x18001af42  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18001af46  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x18001af4a  movups  [rbp+3Fh+var_90], xmm0
0x18001af4e  movups  [rbp+3Fh+var_80], xmm0
0x18001af52  cmp     rcx, rdx
0x18001af55  jz      short loc_18001AF78
0x18001af57  mov     rcx, [rcx+10h]
0x18001af5b  lea     edx, [rbx+1Eh]
0x18001af5e  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001af65  call    WPP_SF_
0x18001af6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af71  lea     rdx, WPP_GLOBAL_Control
0x18001af78  xorps   xmm0, xmm0
0x18001af7b  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18001af7f  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x18001af83  movups  [rbp+3Fh+var_90], xmm0
0x18001af87  movups  [rbp+3Fh+var_80], xmm0
0x18001af8b  cmp     rcx, rdx
0x18001af8e  jz      short loc_18001AFB3
0x18001af90  mov     rcx, [rcx+10h]
0x18001af94  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001af9b  mov     edx, 1Fh
0x18001afa0  call    WPP_SF_
0x18001afa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afac  lea     rdx, WPP_GLOBAL_Control
0x18001afb3  mov     r15d, [rbp+3Fh+var_B0]
0x18001afb7  add     r15d, 3Ch ; '<'
0x18001afbb  mov     [rbp+3Fh+var_B0], r15d
0x18001afbf  lea     eax, [r15+r14]
0x18001afc3  cmp     eax, r13d
0x18001afc6  jbe     short loc_18001AFEC
0x18001afc8  cmp     rcx, rdx
0x18001afcb  jz      short loc_18001AFE2
0x18001afcd  mov     rcx, [rcx+10h]
0x18001afd1  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001afd8  mov     edx, 20h ; ' '
0x18001afdd  call    WPP_SF_
0x18001afe2  mov     ebx, 54Fh
0x18001afe7  jmp     loc_18001B1FA
0x18001afec  mov     eax, [rbp+3Fh+arg_30]
0x18001afef  lea     r8, [rbp+3Fh+var_90]; struct _CRYPTO_BINDING_TLV *
0x18001aff3  mov     r9, [rbp+3Fh+var_98]; unsigned __int8 *
0x18001aff7  xor     edx, edx; unsigned __int8 *
0x18001aff9  mov     rcx, rsi; struct _PEAP_CONTROL_BLOCK *
0x18001affc  mov     [rsp+0F0h+dwGroupSize], eax; int
0x18001b000  call    ?CreateCryptoBindingTLV@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEPEAU_CRYPTO_BINDING_TLV@@1HH@Z; CreateCryptoBindingTLV(_PEAP_CONTROL_BLOCK *,uchar *,_CRYPTO_BINDING_TLV *,uchar *,int,int)
0x18001b005  mov     ebx, eax
0x18001b007  test    eax, eax
0x18001b009  jnz     loc_18001B0C8
0x18001b00f  cmp     [rbp+3Fh+arg_30], eax
0x18001b012  jz      loc_18001B09F
0x18001b018  mov     rcx, [rsi+0AE8h]; hMem
0x18001b01f  test    rcx, rcx
0x18001b022  jz      short loc_18001B02A
0x18001b024  call    cs:__imp_LocalFree
0x18001b02a  mov     edx, 3Ch ; '<'; uBytes
0x18001b02f  lea     ecx, [rdx+4]; uFlags
0x18001b032  call    cs:__imp_LocalAlloc
0x18001b038  mov     [rsi+0AE8h], rax
0x18001b03f  test    rax, rax
0x18001b042  jnz     short loc_18001B080
0x18001b044  call    cs:__imp_GetLastError
0x18001b04a  mov     ebx, eax
0x18001b04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b053  lea     rax, WPP_GLOBAL_Control
0x18001b05a  cmp     rcx, rax
0x18001b05d  jz      loc_18001B1FA
0x18001b063  mov     edx, 21h ; '!'
0x18001b068  mov     rcx, [rcx+10h]
0x18001b06c  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001b073  mov     r9d, ebx
0x18001b076  call    WPP_SF_d
0x18001b07b  jmp     loc_18001B1FA
0x18001b080  movups  xmm0, [rbp+3Fh+var_90]
0x18001b084  movups  xmmword ptr [rax], xmm0
0x18001b087  movups  xmm1, [rbp+3Fh+var_80]
0x18001b08b  movups  xmmword ptr [rax+10h], xmm1
0x18001b08f  movups  xmm0, xmmword ptr [rbp+3Fh+var_70]
0x18001b093  movups  xmmword ptr [rax+20h], xmm0
0x18001b097  movups  xmm1, xmmword ptr [rbp+3Fh+var_70+0Ch]
0x18001b09b  movups  xmmword ptr [rax+2Ch], xmm1
0x18001b09f  movups  xmm0, [rbp+3Fh+var_90]
0x18001b0a3  movups  xmm1, [rbp+3Fh+var_80]
0x18001b0a7  movups  xmmword ptr [r12], xmm0
0x18001b0ac  movups  xmm0, xmmword ptr [rbp+3Fh+var_70]
0x18001b0b0  movups  xmmword ptr [r12+10h], xmm1
0x18001b0b6  movups  xmm1, xmmword ptr [rbp+3Fh+var_70+0Ch]
0x18001b0ba  movups  xmmword ptr [r12+20h], xmm0
0x18001b0c0  movups  xmmword ptr [r12+2Ch], xmm1
0x18001b0c6  jmp     short loc_18001B0F2
0x18001b0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0cf  lea     rax, WPP_GLOBAL_Control
0x18001b0d6  cmp     rcx, rax
0x18001b0d9  jz      loc_18001B1FA
0x18001b0df  mov     edx, 22h ; '"'
0x18001b0e4  jmp     short loc_18001B068
0x18001b0e6  test    ebx, ebx
0x18001b0e8  jnz     loc_18001B1FA
0x18001b0ee  mov     r15d, [rbp+3Fh+var_B0]
0x18001b0f2  cmp     [rbp+3Fh+arg_30], 0
0x18001b0f6  mov     eax, 1
0x18001b0fb  jz      short loc_18001B104
0x18001b0fd  mov     [rdi], al
0x18001b0ff  add     [rsi+10h], al
0x18001b102  jmp     short loc_18001B107
0x18001b104  mov     byte ptr [rdi], 2
0x18001b107  cmp     [rbp+3Fh+arg_28], 0
0x18001b10b  lea     rdx, [rdi+8]
0x18001b10f  mov     cl, [rsi+10h]
0x18001b112  mov     [rdi+1], cl
0x18001b115  mov     word ptr [rdi+4], 19h
0x18001b11b  jz      short loc_18001B13A
0x18001b11d  mov     [rdx], al
0x18001b11f  mov     ecx, 21h ; '!'
0x18001b124  lea     rdx, [rdi+0Ah]
0x18001b128  mov     word ptr [rdi+6], 0FEh
0x18001b12e  mov     byte ptr [rdi+9], 37h ; '7'
0x18001b132  call    cs:__imp_EapConvertHostToWireFormat32
0x18001b138  jmp     short loc_18001B150
0x18001b13a  mov     al, [rdi]
0x18001b13c  mov     [rdi+7], cl
0x18001b13f  lea     ecx, [r15+5]
0x18001b143  mov     [rdi+6], al
0x18001b146  call    cs:__imp_EapConvertHostToWireFormat16
0x18001b14c  mov     byte ptr [rdi+0Ah], 21h ; '!'
0x18001b150  mov     r8d, [rbp+3Fh+var_B0]
0x18001b154  lea     rdx, [rdi+6]; Src
0x18001b158  add     r8d, 0FFFFFFFAh
0x18001b15c  mov     rcx, rsi; struct _PEAP_CONTROL_BLOCK *
0x18001b15f  add     r8d, r14d; Size
0x18001b162  call    ?PeapEncryptTunnelData@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEK@Z; PeapEncryptTunnelData(_PEAP_CONTROL_BLOCK *,uchar *,ulong)
0x18001b167  mov     ebx, eax
0x18001b169  test    eax, eax
0x18001b16b  jnz     short loc_18001B1D2
0x18001b16d  mov     r8d, [rsi+0AB0h]; Size
  ... truncated ...
```
