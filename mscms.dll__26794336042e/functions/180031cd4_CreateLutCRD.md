# CreateLutCRD

- ea: `0x180031cd4`
- end: `0x1800325c5`
- name: `CreateLutCRD`
- size: `2289`
- prototype: `__int64 __fastcall(__int64, unsigned int, void **, unsigned int *, unsigned int, int)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x180036bc0`

## callees

- `0x18002b058`
- `0x18002e5f0`
- `0x180030440`
- `0x180031a00`
- `0x180031cd4`
- `0x1800333e4`
- `0x180033a1c`
- `0x180033a84`
- `0x180033ad4`
- `0x180033c48`
- `0x180038458`
- `0x1800387e4`
- `0x1800388e8`
- `0x180038b98`
- `0x180038cf8`
- `0x1800399f4`
- `0x180039a18`
- `0x180039cf4`
- `0x180039d74`
- `0x180039df4`
- `0x180039e74`
- `0x180039ff8`
- `0x18003a054`
- `0x18003a124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003259d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003259d`

## pseudocode

```c
__int64 __fastcall CreateLutCRD(__int64 a1, unsigned int a2, void **a3, unsigned int *a4, unsigned int a5, int a6)
{
  unsigned int *v6; // rax
  UINT v9; // r9d
  __int64 v11; // rax
  unsigned int v12; // r10d
  unsigned int v13; // r10d
  unsigned int *v14; // r11
  int v15; // r10d
  unsigned int v16; // r14d
  unsigned int v17; // r15d
  int v18; // ecx
  unsigned int v19; // edx
  unsigned int v20; // r9d
  unsigned int v21; // ecx
  unsigned int i; // r8d
  int v23; // eax
  int v24; // ebx
  int v25; // r11d
  UINT v26; // r9d
  unsigned int j; // r10d
  ULONGLONG v28; // rcx
  UINT v29; // r9d
  int v30; // r10d
  int v31; // ecx
  int v32; // r9d
  DWORD v33; // ecx
  UINT v34; // r8d
  unsigned int v35; // r9d
  unsigned int v36; // eax
  unsigned int *v37; // rax
  unsigned int v38; // r14d
  unsigned int v39; // r15d
  unsigned __int32 v40; // ebx
  unsigned __int32 v41; // r14d
  unsigned __int32 v42; // r15d
  UINT v43; // ebx
  int v44; // r15d
  int v45; // r14d
  unsigned int v46; // r13d
  int v47; // ebx
  const char *v48; // r8
  unsigned int v49; // r15d
  const char *v50; // r8
  __int64 v51; // r12
  unsigned int k; // r13d
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // r14
  int v56; // eax
  _WORD *v57; // r14
  void *v58; // r12
  UINT m; // r15d
  unsigned int v60; // r9d
  int v61; // r11d
  unsigned int v63; // r12d
  int v65; // [rsp+30h] [rbp-99h]
  UINT puResult; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v67; // [rsp+64h] [rbp-65h] BYREF
  unsigned int *v68; // [rsp+68h] [rbp-61h]
  int v69; // [rsp+70h] [rbp-59h]
  unsigned int v70; // [rsp+74h] [rbp-55h] BYREF
  unsigned int v71; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v72; // [rsp+7Ch] [rbp-4Dh] BYREF
  unsigned int v73; // [rsp+80h] [rbp-49h] BYREF
  unsigned int v74; // [rsp+84h] [rbp-45h]
  unsigned __int32 v75; // [rsp+88h] [rbp-41h]
  UINT v76; // [rsp+8Ch] [rbp-3Dh]
  UINT v77; // [rsp+90h] [rbp-39h]
  _DWORD v78[4]; // [rsp+98h] [rbp-31h] BYREF
  _DWORD v79[4]; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int32 v80; // [rsp+B8h] [rbp-11h] BYREF
  char v81; // [rsp+BCh] [rbp-Dh]

  v6 = *(unsigned int **)a1;
  v70 = 0;
  v71 = 0;
  v9 = *(_DWORD *)(a1 + 32);
  v75 = _byteswap_ulong(v6[5]);
  v67 = 0;
  v72 = 0;
  v73 = 0;
  v76 = v9;
  v11 = *(_QWORD *)(a1 + 8);
  puResult = v9;
  v12 = *(_DWORD *)(v11 + 12LL * a2 + 4);
  v80 = _byteswap_ulong(*(_DWORD *)(v11 + 12LL * a2));
  v77 = _byteswap_ulong(v12);
  if ( UIntSub(v9, v77, &puResult) < 0 )
    goto LABEL_124;
  if ( UIntSub(puResult, 0x30u, &puResult) < 0 )
    goto LABEL_124;
  v14 = (unsigned int *)(v13 + *(_QWORD *)(a1 + 24));
  v68 = v14;
  v15 = _byteswap_ulong(*v14);
  v69 = v15;
  if ( v15 != 1835430961 && (v15 != 1835430962 || UIntSub(puResult, 4u, &puResult) < 0) )
    goto LABEL_124;
  GetCLUTInfo(v15, (__int64)v14, &v70, &v71, &v67, &v72, &v73, 0);
  v16 = v70;
  if ( v70 > 0xFFFFFFFF / v72 )
    goto LABEL_124;
  v17 = v71;
  if ( v71 > 0xFFFFFFFF / v73 )
    goto LABEL_124;
  v18 = v71 * v73;
  v19 = v70 * v72;
  v74 = v70 * v72;
  if ( v70 * v72 > ~(v71 * v73) )
    goto LABEL_124;
  v20 = v18 + v19;
  if ( v18 + v19 > 0x2AAAAAAA )
    goto LABEL_124;
  v21 = 1;
  for ( i = 0; i < 3; ++i )
  {
    if ( v21 > 0xFFFFFFFF / v67 )
      goto LABEL_124;
    v21 *= v67;
  }
  if ( v21 > 0xFFFFFFFF / v71 )
    goto LABEL_124;
  v23 = v21 * v71;
  if ( v21 * v71 > 0x7FFFFFFF )
    goto LABEL_124;
  v24 = 2 * v23;
  v25 = 6 * v20;
  if ( 6 * v20 > ~(2 * v23) || v70 > -1 - v71 )
    goto LABEL_124;
  v26 = 0;
  for ( j = 0; j < 3; j = v30 + 1 )
  {
    puResult = 0;
    v28 = -1;
    do
      ++v28;
    while ( off_1800863B0[j][v28] );
    if ( ULongLongToULong(v28, &puResult) < 0 )
      goto LABEL_29;
    if ( v29 > -1 - puResult )
      goto LABEL_124;
    v26 = puResult + v29;
  }
  if ( v17 + v16 > 0xFFFFFFFF / v26 )
    goto LABEL_124;
  v31 = v26 * (v17 + v16);
  if ( v24 + v25 > (unsigned int)~v31 || (unsigned int)(v24 + v25 + v31) > 0xFFFFF7FF )
    goto LABEL_124;
  puResult = 0;
  if ( ULongLongToULong(2u, &puResult) < 0 )
  {
LABEL_29:
    v33 = 87;
    goto LABEL_125;
  }
  v34 = v32 + 2048;
  v35 = (v32 + 2048) / 0xF0u + 1;
  if ( v35 > 0xFFFFFFFF / puResult || v34 > ~(v35 * puResult) )
  {
LABEL_124:
    v33 = 2011;
    goto LABEL_125;
  }
  v36 = v34 + v35 * puResult;
  if ( !a3 || !*a3 )
  {
    *a4 = v36;
    return 1;
  }
  if ( *a4 < v36 )
  {
    v33 = 122;
LABEL_125:
    SetLastError(v33);
    return 0;
  }
  v37 = *(unsigned int **)a1;
  puResult = 0;
  v38 = v37[18];
  v39 = v37[19];
  v40 = _byteswap_ulong(v37[17]);
  v78[0] = v40;
  v41 = _byteswap_ulong(v38);
  v78[1] = v41;
  v42 = _byteswap_ulong(v39);
  v78[2] = v42;
  if ( a5 == 3 && !(unsigned int)GetCPMediaWhitePoint(a1, v79) )
  {
    v79[0] = v40;
    v79[1] = v41;
    v79[2] = v42;
  }
  v81 = 0;
  if ( !(unsigned int)WriteNewLineObject(a3, a4, "%** CRD Begin ")
    || !(unsigned int)EnableGlobalDict(a3, a4)
    || !(unsigned int)BeginGlobalDict(a3, a4) )
  {
    v46 = v70;
    v44 = a6;
    v45 = v69;
LABEL_48:
    v47 = 0;
    goto LABEL_49;
  }
  v43 = v76 - v77;
  v44 = a6;
  v45 = v69;
  v46 = v70;
  if ( !(unsigned int)CreateInputArray(a3, a4, v70, v72, (__int64)&v80, v69, (__int64)v68, v76 - v77, a6, 0)
    || !(unsigned int)CreateOutputArray(
                        (_DWORD)a3,
                        (_DWORD)a4,
                        v71,
                        v73,
                        v74 + v71 * v67 * v67 * v67,
                        (__int64)&v80,
                        v45,
                        (__int64)v68,
                        v43,
                        a6,
                        0)
    || !(unsigned int)EndGlobalDict(a3, a4) )
  {
    goto LABEL_48;
  }
  v47 = 1;
  if ( (unsigned int)WriteNewLineObject(a3, a4, "<<") )
  {
LABEL_49:
    if ( (unsigned int)WriteObject(a3, a4, "/ColorRenderingType 1 ") )
      goto LABEL_51;
  }
  v47 = 0;
LABEL_51:
  switch ( a5 )
  {
    case 0u:
      if ( v47 )
      {
        if ( !(unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
          goto LABEL_58;
        v48 = "/Perceptual";
        goto LABEL_79;
      }
LABEL_68:
      v49 = puResult;
      goto LABEL_69;
    case 1u:
      if ( !v47 )
        goto LABEL_68;
      if ( (unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
      {
        v50 = "/RelativeColorimetric";
LABEL_65:
        if ( (unsigned int)WriteObject(a3, a4, v50) )
          goto LABEL_80;
      }
LABEL_66:
      v47 = 0;
LABEL_67:
      if ( !v47 )
        goto LABEL_68;
LABEL_80:
      if ( (unsigned int)SendCRDBWPoint(a3, a4, v78) && (unsigned int)SendCRDPQR(a3, a4, a5, v78) )
      {
        v56 = SendCRDLMN((_DWORD)a3, (_DWORD)a4, a5, (unsigned int)v78, (__int64)v79, v75);
        v51 = (__int64)v68;
        if ( v56
          && (unsigned int)SendCRDABC(
                             (_DWORD)a3,
                             (_DWORD)a4,
                             (unsigned int)&v80,
                             v75,
                             v46,
                             (__int64)v68,
                             v65,
                             0,
                             v45,
                             v44)
          && (unsigned int)WriteNewLineObject(a3, a4, "/RenderTable ")
          && (unsigned int)WriteObject(a3, a4, "[")
          && (unsigned int)WriteInt(a3, a4, v67)
          && (unsigned int)WriteInt(a3, a4, v67)
          && (unsigned int)WriteInt(a3, a4, v67)
          && (unsigned int)WriteNewLineObject(a3, a4, "[") )
        {
          v49 = v71 * v67 * v67;
          puResult = v49;
        }
        else
        {
          v47 = 0;
          v49 = 0;
        }
        goto LABEL_70;
      }
      goto LABEL_58;
    case 2u:
      if ( !v47 )
        goto LABEL_68;
      if ( (unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
      {
        v50 = "/Saturation";
        goto LABEL_65;
      }
      goto LABEL_66;
  }
  if ( a5 != 3 )
    goto LABEL_67;
  if ( !v47 )
    goto LABEL_68;
  if ( !(unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
    goto LABEL_58;
  v48 = "/AbsoluteColorimetric";
LABEL_79:
  if ( (unsigned int)WriteObject(a3, a4, v48) )
    goto LABEL_80;
LABEL_58:
  v47 = 0;
  v49 = 0;
LABEL_69:
  v51 = (__int64)v68;
LABEL_70:
  for ( k = 0; k < v67; ++k )
  {
    if ( !v47 )
      goto LABEL_118;
    if ( !(unsigned int)WriteObject(a3, a4, "\r\n") )
      goto LABEL_117;
    v54 = k * v49;
    if ( v45 == 1835430961 )
    {
      v55 = v74 + 48LL;
    }
    else
    {
      v54 = (unsigned int)(2 * v54);
      v55 = 2 * v74 + 52LL;
    }
    v57 = (_WORD *)(v54 + v51 + v55);
    if ( a6 )
    {
      if ( !(unsigned int)WriteStringToken(a3, a4, v53, v49) )
        goto LABEL_117;
      if ( !(v69 == v61 ? WriteByteString(a3, a4, v57, v60) : (unsigned int)WriteInt2ByteString(a3, a4, v57)) )
        goto LABEL_117;
    }
    else
    {
      v58 = *a3;
      if ( !(unsigned int)WriteObject(a3, a4, "<") )
        goto LABEL_117;
      if ( v69 == 1835430961 )
      {
        if ( !(unsigned int)WriteHexBuffer((_DWORD)a3, (_DWORD)a4, (_DWORD)v57, (_DWORD)v58, v49) )
          goto LABEL_117;
      }
      else
      {
        for ( m = 0; m < puResult; ++m )
        {
          if ( !(unsigned int)WriteHex(a3, a4, __ROR2__(*v57, 8) >> 8)
            || (unsigned int)(*(_DWORD *)a3 - (_DWORD)v58) > 0xF0
            && (v58 = *a3, !(unsigned int)WriteObject(a3, a4, "\r\n")) )
          {
            v47 = 0;
            goto LABEL_98;
          }
          ++v57;
        }
      }
      if ( !(unsigned int)WriteObject(a3, a4, ">") )
        goto LABEL_117;
LABEL_98:
      v51 = (__int64)v68;
    }
    v49 = puResult;
    v45 = v69;
  }
  if ( !v47 )
    goto LABEL_118;
  if ( !(unsigned int)WriteObject(a3, a4, "]") || (v63 = v71, !(unsigned int)WriteInt(a3, a4, v71)) )
  {
LABEL_117:
    v47 = 0;
    goto LABEL_118;
  }
  if ( !(unsigned int)SendCRDOutputTable((_DWORD)a3, (_DWORD)a4, (unsigned int)&v80, v63, v45, 0, a6) )
    return 0;
LABEL_118:
  if ( !(unsigned int)WriteObject(a3, a4, "]") || !(unsigned int)WriteObject(a3, a4, ">>") )
    return 0;
  if ( v47 )
    return v47 & (unsigned int)-((unsigned int)WriteNewLineObject(a3, a4, "%** CRD End ") != 0);
  else
    return 0;
}

```

## disassembly

```asm
0x180031cd4  push    rbp
0x180031cd6  push    rbx
0x180031cd7  push    rsi
0x180031cd8  push    rdi
0x180031cd9  push    r12
0x180031cdb  push    r13
0x180031cdd  push    r14
0x180031cdf  push    r15
0x180031ce1  lea     rbp, [rsp-0Fh]
0x180031ce6  sub     rsp, 0D8h
0x180031ced  mov     rax, cs:__security_cookie
0x180031cf4  xor     rax, rsp
0x180031cf7  mov     [rbp+47h+var_50], rax
0x180031cfb  mov     rax, [rcx]
0x180031cfe  xor     r12d, r12d
0x180031d01  mov     r13, rcx
0x180031d04  mov     [rbp+47h+var_9C], r12d
0x180031d08  mov     rsi, r9
0x180031d0b  mov     [rbp+47h+var_98], r12d
0x180031d0f  mov     r9d, [rcx+20h]
0x180031d13  mov     rdi, r8
0x180031d16  mov     eax, [rax+14h]
0x180031d19  lea     r8, [rbp+47h+puResult]; puResult
0x180031d1d  bswap   eax
0x180031d1f  mov     [rbp+47h+var_88], eax
0x180031d22  mov     eax, edx
0x180031d24  mov     [rbp+47h+var_AC], r12d
0x180031d28  mov     [rbp+47h+var_94], r12d
0x180031d2c  mov     [rbp+47h+var_90], r12d
0x180031d30  lea     rcx, [rax+rax*2]
0x180031d34  mov     [rbp+47h+var_84], r9d
0x180031d38  mov     rax, [r13+8]
0x180031d3c  mov     [rbp+47h+puResult], r9d
0x180031d40  mov     edx, [rax+rcx*4]
0x180031d43  mov     r10d, [rax+rcx*4+4]
0x180031d48  mov     ecx, r9d; uMinuend
0x180031d4b  bswap   edx
0x180031d4d  bswap   r10d
0x180031d50  mov     [rbp+47h+var_58], edx
0x180031d53  mov     edx, r10d; uSubtrahend
0x180031d56  mov     [rbp+47h+var_80], r10d
0x180031d5a  call    UIntSub
0x180031d5f  test    eax, eax
0x180031d61  js      loc_180032598
0x180031d67  mov     ecx, [rbp+47h+puResult]; uMinuend
0x180031d6a  lea     r8, [rbp+47h+puResult]; puResult
0x180031d6e  lea     edx, [r12+30h]; uSubtrahend
0x180031d73  call    UIntSub
0x180031d78  test    eax, eax
0x180031d7a  js      loc_180032598
0x180031d80  mov     r11, [r13+18h]
0x180031d84  mov     ecx, r10d
0x180031d87  add     r11, rcx
0x180031d8a  mov     [rbp+47h+var_A8], r11
0x180031d8e  mov     r10d, [r11]
0x180031d91  bswap   r10d
0x180031d94  mov     [rbp+47h+var_A0], r10d
0x180031d98  cmp     r10d, 6D667431h
0x180031d9f  jz      short loc_180031DC7
0x180031da1  cmp     r10d, 6D667432h
0x180031da8  jnz     loc_180032598
0x180031dae  mov     ecx, [rbp+47h+puResult]; uMinuend
0x180031db1  lea     r8, [rbp+47h+puResult]; puResult
0x180031db5  lea     edx, [r12+4]; uSubtrahend
0x180031dba  call    UIntSub
0x180031dbf  test    eax, eax
0x180031dc1  js      loc_180032598
0x180031dc7  mov     [rsp+110h+var_D8], r12
0x180031dcc  lea     rax, [rbp+47h+var_90]
0x180031dd0  mov     [rsp+110h+var_E0], rax
0x180031dd5  lea     r9, [rbp+47h+var_98]
0x180031dd9  lea     rax, [rbp+47h+var_94]
0x180031ddd  mov     rdx, r11
0x180031de0  mov     [rsp+110h+var_E8], rax
0x180031de5  lea     r8, [rbp+47h+var_9C]
0x180031de9  lea     rax, [rbp+47h+var_AC]
0x180031ded  mov     ecx, r10d
0x180031df0  mov     [rsp+110h+var_F0], rax
0x180031df5  call    GetCLUTInfo
0x180031dfa  mov     r14d, [rbp+47h+var_9C]
0x180031dfe  or      r10d, 0FFFFFFFFh
0x180031e02  xor     edx, edx
0x180031e04  mov     eax, r10d
0x180031e07  div     [rbp+47h+var_94]
0x180031e0a  cmp     r14d, eax
0x180031e0d  ja      loc_180032598
0x180031e13  mov     r15d, [rbp+47h+var_98]
0x180031e17  xor     edx, edx
0x180031e19  mov     eax, r10d
0x180031e1c  div     [rbp+47h+var_90]
0x180031e1f  cmp     r15d, eax
0x180031e22  ja      loc_180032598
0x180031e28  mov     ecx, [rbp+47h+var_90]
0x180031e2b  mov     edx, [rbp+47h+var_94]
0x180031e2e  imul    ecx, r15d
0x180031e32  imul    edx, r14d
0x180031e36  mov     eax, ecx
0x180031e38  not     eax
0x180031e3a  mov     [rbp+47h+var_8C], edx
0x180031e3d  cmp     edx, eax
0x180031e3f  ja      loc_180032598
0x180031e45  lea     r9d, [rcx+rdx]
0x180031e49  cmp     r9d, 2AAAAAAAh
0x180031e50  ja      loc_180032598
0x180031e56  mov     ecx, 1
0x180031e5b  mov     r8d, r12d
0x180031e5e  xor     edx, edx
0x180031e60  mov     eax, r10d
0x180031e63  cmp     r8d, 3
0x180031e67  jnb     short loc_180031E7D
0x180031e69  div     [rbp+47h+var_AC]
0x180031e6c  cmp     ecx, eax
0x180031e6e  ja      loc_180032598
0x180031e74  imul    ecx, [rbp+47h+var_AC]
0x180031e78  inc     r8d
0x180031e7b  jmp     short loc_180031E5E
0x180031e7d  div     r15d
0x180031e80  cmp     ecx, eax
0x180031e82  ja      loc_180032598
0x180031e88  mov     eax, r15d
0x180031e8b  imul    eax, ecx
0x180031e8e  cmp     eax, 7FFFFFFFh
0x180031e93  ja      loc_180032598
0x180031e99  lea     ebx, [rax+rax]
0x180031e9c  mov     eax, ebx
0x180031e9e  lea     r11d, [r9+r9*2]
0x180031ea2  not     eax
0x180031ea4  add     r11d, r11d
0x180031ea7  cmp     r11d, eax
0x180031eaa  ja      loc_180032598
0x180031eb0  mov     eax, r10d
0x180031eb3  sub     eax, r15d
0x180031eb6  cmp     r14d, eax
0x180031eb9  ja      loc_180032598
0x180031ebf  mov     r9d, r12d
0x180031ec2  mov     r10d, r12d
0x180031ec5  cmp     r10d, 3
0x180031ec9  jnb     short loc_180031F0F
0x180031ecb  mov     eax, r10d
0x180031ece  lea     rdx, off_1800863B0; " dup length 1 sub 3 -1 roll mul dup dup"...
0x180031ed5  mov     [rbp+47h+puResult], r12d
0x180031ed9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180031edd  mov     rdx, [rdx+rax*8]
0x180031ee1  inc     rcx; ullOperand
0x180031ee4  cmp     [rdx+rcx], r12b
0x180031ee8  jnz     short loc_180031EE1
0x180031eea  lea     rdx, [rbp+47h+puResult]; pulResult
0x180031eee  call    ULongLongToULong
0x180031ef3  test    eax, eax
0x180031ef5  js      short loc_180031F5E
0x180031ef7  or      eax, 0FFFFFFFFh
0x180031efa  sub     eax, [rbp+47h+puResult]
0x180031efd  cmp     r9d, eax
0x180031f00  ja      loc_180032598
0x180031f06  add     r9d, [rbp+47h+puResult]
0x180031f0a  inc     r10d
0x180031f0d  jmp     short loc_180031EC5
0x180031f0f  xor     edx, edx
0x180031f11  lea     ecx, [r15+r14]
0x180031f15  or      eax, 0FFFFFFFFh
0x180031f18  div     r9d
0x180031f1b  cmp     ecx, eax
0x180031f1d  ja      loc_180032598
0x180031f23  imul    ecx, r9d
0x180031f27  lea     edx, [rbx+r11]
0x180031f2b  mov     eax, ecx
0x180031f2d  not     eax
0x180031f2f  cmp     edx, eax
0x180031f31  ja      loc_180032598
0x180031f37  lea     r9d, [rdx+rcx]
0x180031f3b  cmp     r9d, 0FFFFF7FFh
0x180031f42  ja      loc_180032598
0x180031f48  lea     rdx, [rbp+47h+puResult]; pulResult
0x180031f4c  mov     [rbp+47h+puResult], r12d
0x180031f50  mov     ecx, 2; ullOperand
0x180031f55  call    ULongLongToULong
0x180031f5a  test    eax, eax
0x180031f5c  jns     short loc_180031F68
0x180031f5e  mov     ecx, 57h ; 'W'
0x180031f63  jmp     loc_18003259D
0x180031f68  mov     ecx, [rbp+47h+puResult]
0x180031f6b  lea     r8d, [r9+800h]
0x180031f72  mov     eax, 88888889h
0x180031f77  mul     r8d
0x180031f7a  or      eax, 0FFFFFFFFh
0x180031f7d  shr     edx, 7
0x180031f80  lea     r9d, [rdx+1]
0x180031f84  xor     edx, edx
0x180031f86  div     ecx
0x180031f88  cmp     r9d, eax
0x180031f8b  ja      loc_180032598
0x180031f91  imul    ecx, r9d
0x180031f95  mov     eax, ecx
0x180031f97  not     eax
0x180031f99  cmp     r8d, eax
0x180031f9c  ja      loc_180032598
0x180031fa2  lea     eax, [r8+rcx]
0x180031fa6  test    rdi, rdi
0x180031fa9  jz      loc_18003258F
0x180031faf  cmp     [rdi], r12
0x180031fb2  jz      loc_18003258F
0x180031fb8  cmp     [rsi], eax
0x180031fba  jnb     short loc_180031FC6
0x180031fbc  mov     ecx, 7Ah ; 'z'
0x180031fc1  jmp     loc_18003259D
0x180031fc6  mov     rax, [r13+0]
0x180031fca  mov     [rbp+47h+puResult], r12d
0x180031fce  mov     r12d, [rbp+47h+arg_20]
0x180031fd2  mov     ebx, [rax+44h]
0x180031fd5  mov     r14d, [rax+48h]
0x180031fd9  mov     r15d, [rax+4Ch]
0x180031fdd  bswap   ebx
0x180031fdf  mov     [rbp+47h+var_78], ebx
0x180031fe2  bswap   r14d
0x180031fe5  mov     [rbp+47h+var_74], r14d
0x180031fe9  bswap   r15d
0x180031fec  mov     [rbp+47h+var_70], r15d
0x180031ff0  cmp     r12d, 3
0x180031ff4  jnz     short loc_180032011
0x180031ff6  lea     rdx, [rbp+47h+var_68]
0x180031ffa  mov     rcx, r13
0x180031ffd  call    GetCPMediaWhitePoint
0x180032002  test    eax, eax
0x180032004  jnz     short loc_180032011
0x180032006  mov     [rbp+47h+var_68], ebx
0x180032009  mov     [rbp+47h+var_64], r14d
0x18003200d  mov     [rbp+47h+var_60], r15d
0x180032011  mov     eax, [rbp+47h+var_58]
0x180032014  lea     r8, CRDBegin; "%** CRD Begin "
0x18003201b  mov     rdx, rsi
0x18003201e  mov     [rbp+47h+var_58], eax
0x180032021  mov     rcx, rdi
0x180032024  mov     [rbp+47h+var_54], 0
0x180032028  call    WriteNewLineObject
0x18003202d  test    eax, eax
0x18003202f  jz      loc_180032131
0x180032035  mov     rdx, rsi
0x180032038  mov     rcx, rdi
0x18003203b  call    EnableGlobalDict
0x180032040  test    eax, eax
0x180032042  jz      loc_180032131
0x180032048  mov     rdx, rsi
0x18003204b  mov     rcx, rdi
0x18003204e  call    BeginGlobalDict
0x180032053  test    eax, eax
0x180032055  jz      loc_180032131
0x18003205b  mov     rax, [rbp+47h+var_A8]
0x18003205f  mov     rdx, rsi
0x180032062  mov     ebx, [rbp+47h+var_84]
0x180032065  mov     rcx, rdi
0x180032068  sub     ebx, [rbp+47h+var_80]
0x18003206b  mov     r15d, [rbp+47h+arg_28]
0x18003206f  mov     r14d, [rbp+47h+var_A0]
0x180032073  mov     r13d, [rbp+47h+var_9C]
0x180032077  mov     r8d, r13d
0x18003207a  mov     r9d, [rbp+47h+var_94]
0x18003207e  mov     [rsp+110h+var_C8], 0
0x180032087  mov     [rsp+110h+var_D0], r15d
0x18003208c  mov     dword ptr [rsp+110h+var_D8], ebx
0x180032090  mov     [rsp+110h+var_E0], rax
0x180032095  lea     rax, [rbp+47h+var_58]
0x180032099  mov     dword ptr [rsp+110h+var_E8], r14d
0x18003209e  mov     [rsp+110h+var_F0], rax
0x1800320a3  call    CreateInputArray
0x1800320a8  test    eax, eax
0x1800320aa  jz      loc_18003213D
0x1800320b0  mov     eax, [rbp+47h+var_AC]
0x1800320b3  mov     rdx, rsi
0x1800320b6  mov     r8d, [rbp+47h+var_98]
0x1800320ba  mov     rcx, [rbp+47h+var_A8]
0x1800320be  mov     r9d, [rbp+47h+var_90]
0x1800320c2  mov     [rsp+110h+var_C0], 0
0x1800320cb  mov     dword ptr [rsp+110h+var_C8], r15d
0x1800320d0  imul    eax, eax
0x1800320d3  mov     [rsp+110h+var_D0], ebx
0x1800320d7  mov     [rsp+110h+var_D8], rcx
0x1800320dc  lea     rcx, [rbp+47h+var_58]
0x1800320e0  mov     dword ptr [rsp+110h+var_E0], r14d
0x1800320e5  mov     [rsp+110h+var_E8], rcx
0x1800320ea  mov     rcx, rdi
0x1800320ed  imul    eax, [rbp+47h+var_AC]
0x1800320f1  imul    eax, r8d
0x1800320f5  add     eax, [rbp+47h+var_8C]
0x1800320f8  mov     dword ptr [rsp+110h+var_F0], eax
0x1800320fc  call    CreateOutputArray
0x180032101  test    eax, eax
0x180032103  jz      short loc_18003213D
0x180032105  mov     rdx, rsi
0x180032108  mov     rcx, rdi
0x18003210b  call    EndGlobalDict
0x180032110  test    eax, eax
0x180032112  jz      short loc_18003213D
0x180032114  lea     r8, BeginDict; "<<"
0x18003211b  mov     rdx, rsi
0x18003211e  mov     rcx, rdi
0x180032121  mov     ebx, 1
0x180032126  call    WriteNewLineObject
0x18003212b  test    eax, eax
0x18003212d  jz      short loc_180032155
0x18003212f  jmp     short loc_18003213F
  ... truncated ...
```
