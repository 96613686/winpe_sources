# CreateMonoCRD

- ea: `0x180032dd8`
- end: `0x1800333dd`
- name: `CreateMonoCRD`
- size: `1541`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180036bc0`

## callees

- `0x18000b828`
- `0x18000be44`
- `0x18002b058`
- `0x18002e5f0`
- `0x180032dd8`
- `0x180033c48`
- `0x1800364f0`
- `0x1800366f0`
- `0x1800387e4`
- `0x1800388e8`
- `0x180038cf8`
- `0x180039df4`
- `0x180039ff8`
- `0x18003a054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032e53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800331b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032e53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800331b4`

## pseudocode

```c
__int64 __fastcall CreateMonoCRD(__int64 a1, unsigned int a2, _BYTE **a3, unsigned int *a4, unsigned int a5)
{
  __int64 v5; // rax
  DWORD v9; // ecx
  __int64 v11; // r14
  int v12; // r9d
  unsigned int v13; // r10d
  unsigned int v14; // ecx
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned int v17; // r14d
  unsigned int v18; // r15d
  unsigned __int32 v19; // ebx
  unsigned __int32 v20; // r14d
  unsigned __int32 v21; // r15d
  unsigned int v22; // ebx
  const char *v23; // r8
  const char *v24; // r8
  const char *v25; // r8
  UINT v26; // r12d
  _BYTE *v27; // r13
  unsigned __int16 *v28; // r15
  UINT i; // r14d
  unsigned __int32 v30; // [rsp+40h] [rbp-51h]
  ULONG pulResult[2]; // [rsp+48h] [rbp-49h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-41h] BYREF
  unsigned int v33; // [rsp+54h] [rbp-3Dh] BYREF
  UINT v34; // [rsp+58h] [rbp-39h] BYREF
  __int64 v35; // [rsp+60h] [rbp-31h] BYREF
  _DWORD v36[4]; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int64 v37; // [rsp+78h] [rbp-19h]
  _DWORD v38[4]; // [rsp+80h] [rbp-11h] BYREF

  v5 = *(_QWORD *)a1;
  v35 = 0;
  v33 = 0;
  v32 = 0;
  v30 = _byteswap_ulong(*(_DWORD *)(v5 + 20));
  if ( !(unsigned int)GetTagAtIndex(a1, a2, 0xCu, &v35, &v34, &v32, &v33) )
  {
    v9 = 2011;
LABEL_3:
    SetLastError(v9);
    return 0;
  }
  v11 = v35;
  pulResult[0] = 0;
  v34 = _byteswap_ulong(*(_DWORD *)(v35 + 8));
  if ( ULongLongToULong(2LL * ((6 * v34 + 2048) / 0xF0 + 1), pulResult) < 0 )
  {
    v9 = 87;
    goto LABEL_3;
  }
  v14 = v12 + pulResult[0];
  if ( a3 && *a3 )
  {
    if ( *a4 < v14 )
    {
      v9 = 122;
      goto LABEL_3;
    }
    if ( v13 > 0x3FFFFFFF || (v15 = v13, v16 = MemAlloc(4LL * v13), (*(_QWORD *)pulResult = v16) == 0) )
    {
      v9 = 8;
      goto LABEL_3;
    }
    v37 = 2 * v15;
    GetRevCurve(v11, v32, 2 * v15 + v16, v16);
    v17 = *(_DWORD *)(*(_QWORD *)a1 + 72LL);
    v18 = *(_DWORD *)(*(_QWORD *)a1 + 76LL);
    v19 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)a1 + 68LL));
    v36[0] = v19;
    v20 = _byteswap_ulong(v17);
    v36[1] = v20;
    v21 = _byteswap_ulong(v18);
    v36[2] = v21;
    if ( a5 == 3 && !(unsigned int)GetCPMediaWhitePoint(a1, v38) )
    {
      v38[0] = v19;
      v38[1] = v20;
      v38[2] = v21;
    }
    if ( !(unsigned int)WriteNewLineObject(a3, a4, "<<")
      || (v22 = 1, !(unsigned int)WriteObject(a3, a4, "/ColorRenderingType 1 ")) )
    {
      v22 = 0;
    }
    switch ( a5 )
    {
      case 0u:
        if ( !v22 )
          goto LABEL_30;
        if ( !(unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
          goto LABEL_29;
        v23 = "/Perceptual";
LABEL_25:
        if ( (unsigned int)WriteObject(a3, a4, v23) )
        {
LABEL_26:
          if ( !(unsigned int)SendCRDBWPoint(a3, a4, v36)
            || !(unsigned int)SendCRDPQR(a3, a4, a5, v36)
            || !(unsigned int)SendCRDLMN((_DWORD)a3, (_DWORD)a4, a5, (unsigned int)v36, (__int64)v38, v30) )
          {
            goto LABEL_29;
          }
LABEL_30:
          if ( v30 == 1482250784 )
          {
            if ( !v22 )
              goto LABEL_53;
            if ( (unsigned int)WriteNewLineObject(a3, a4, "/MatrixABC ") )
            {
              v24 = "[0 1 0 1 0 0 0 0 1]";
              goto LABEL_51;
            }
          }
          else
          {
            if ( v30 != 1281450528 || !v22 )
            {
LABEL_53:
              v26 = v34;
              if ( !v34 )
              {
                if ( !v22 )
                  goto LABEL_90;
                goto LABEL_89;
              }
              if ( !v22 )
              {
LABEL_90:
                MemFree(*(LPVOID *)pulResult);
                return v22;
              }
              if ( !(unsigned int)WriteObject(a3, a4, "\r\n")
                || (v27 = *a3, !(unsigned int)WriteObject(a3, a4, "/EncodeABC "))
                || !(unsigned int)WriteObject(a3, a4, "[")
                || !(unsigned int)WriteObject(a3, a4, "{") )
              {
LABEL_61:
                v22 = 0;
                goto LABEL_90;
              }
              if ( v37 > v33 )
              {
                SetLastError(0x7DBu);
                goto LABEL_61;
              }
              if ( v26 == 1
                && (!(unsigned int)WriteInt(a3, a4, (unsigned __int16)__ROR2__(*(_WORD *)(v35 + 12), 8))
                 || !(unsigned int)WriteObject(a3, a4, "256 div 1.0 exch div exp ")) )
              {
                goto LABEL_61;
              }
              v28 = *(unsigned __int16 **)pulResult;
              if ( v30 != 1281450528 || (unsigned int)WriteObject(a3, a4, "16 sub 100 div ") )
              {
                if ( !(unsigned int)WriteObject(a3, a4, "dup 1.0 le{dup 0.0 ge{") )
                  goto LABEL_70;
              }
              else
              {
                v22 = 0;
              }
              if ( (unsigned int)WriteObject(a3, a4, "[") )
              {
LABEL_71:
                for ( i = 0; i < v26; ++i )
                {
                  if ( !v22 )
                    goto LABEL_90;
                  if ( !(unsigned int)WriteInt(a3, a4, *v28) )
                    goto LABEL_61;
                  if ( (unsigned int)(*(_DWORD *)a3 - (_DWORD)v27) > 0xF0 )
                  {
                    v27 = *a3;
                    if ( !(unsigned int)WriteObject(a3, a4, "\r\n") )
                      goto LABEL_61;
                  }
                  ++v28;
                }
                if ( !v22 )
                  goto LABEL_90;
                if ( !(unsigned int)WriteObject(a3, a4, "]")
                  || !(unsigned int)WriteNewLineObject(
                                      a3,
                                      a4,
                                      " dup length 1 sub 3 -1 roll mul dup dup floor cvi exch ceiling cvi 3 index exch ge"
                                      "t 4 -1 roll 3 -1 roll get dup 3 1 roll sub 3 -1 roll dup floor cvi sub mul add ")
                  || !(unsigned int)WriteObject(a3, a4, "65535 div ")
                  || !(unsigned int)WriteObject(a3, a4, "}if}if ")
                  || !(unsigned int)WriteObject(a3, a4, "}bind ")
                  || !(unsigned int)WriteObject(a3, a4, "dup ")
                  || !(unsigned int)WriteObject(a3, a4, "dup ")
                  || !(unsigned int)WriteObject(a3, a4, "]") )
                {
                  goto LABEL_61;
                }
LABEL_89:
                v22 &= -((unsigned int)WriteObject(a3, a4, ">>") != 0);
                goto LABEL_90;
              }
LABEL_70:
              v22 = 0;
              goto LABEL_71;
            }
            if ( (unsigned int)WriteNewLineObject(a3, a4, "/MatrixABC ") )
            {
              v24 = "[0 500 0 116 -500 200 0 0 -200]";
LABEL_51:
              if ( (unsigned int)WriteObject(a3, a4, v24) )
                goto LABEL_53;
            }
          }
          v22 = 0;
          goto LABEL_53;
        }
LABEL_29:
        v22 = 0;
        goto LABEL_30;
      case 1u:
        if ( !v22 )
          goto LABEL_30;
        if ( (unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
        {
          v25 = "/RelativeColorimetric";
LABEL_40:
          if ( (unsigned int)WriteObject(a3, a4, v25) )
            goto LABEL_26;
        }
        break;
      case 2u:
        if ( !v22 )
          goto LABEL_30;
        if ( (unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
        {
          v25 = "/Saturation";
          goto LABEL_40;
        }
        break;
      case 3u:
        if ( !v22 )
          goto LABEL_30;
        if ( !(unsigned int)WriteNewLineObject(a3, a4, "/RenderingIntent ") )
          goto LABEL_29;
        v23 = "/AbsoluteColorimetric";
        goto LABEL_25;
      default:
LABEL_42:
        if ( !v22 )
          goto LABEL_30;
        goto LABEL_26;
    }
    v22 = 0;
    goto LABEL_42;
  }
  *a4 = v14;
  return 1;
}

```

## disassembly

```asm
0x180032dd8  push    rbp
0x180032dda  push    rbx
0x180032ddb  push    rsi
0x180032ddc  push    rdi
0x180032ddd  push    r12
0x180032ddf  push    r13
0x180032de1  push    r14
0x180032de3  push    r15
0x180032de5  lea     rbp, [rsp-17h]
0x180032dea  sub     rsp, 0A8h
0x180032df1  mov     rax, cs:__security_cookie
0x180032df8  xor     rax, rsp
0x180032dfb  mov     [rbp+4Fh+var_50], rax
0x180032dff  mov     rax, [rcx]
0x180032e02  xor     r15d, r15d
0x180032e05  mov     rsi, r9
0x180032e08  mov     [rbp+4Fh+var_80], r15
0x180032e0c  mov     rdi, r8
0x180032e0f  mov     [rbp+4Fh+var_8C], r15d
0x180032e13  lea     r9, [rbp+4Fh+var_80]
0x180032e17  mov     [rbp+4Fh+var_90], r15d
0x180032e1b  mov     eax, [rax+14h]
0x180032e1e  lea     r8d, [r15+0Ch]
0x180032e22  bswap   eax
0x180032e24  mov     [rbp+4Fh+var_A0], eax
0x180032e27  mov     r12, rcx
0x180032e2a  lea     rax, [rbp+4Fh+var_8C]
0x180032e2e  mov     [rsp+0E0h+var_B0], rax
0x180032e33  lea     rax, [rbp+4Fh+var_90]
0x180032e37  mov     [rsp+0E0h+var_B8], rax
0x180032e3c  lea     rax, [rbp+4Fh+var_88]
0x180032e40  mov     [rsp+0E0h+var_C0], rax
0x180032e45  call    GetTagAtIndex
0x180032e4a  test    eax, eax
0x180032e4c  jnz     short loc_180032E60
0x180032e4e  mov     ecx, 7DBh; dwErrCode
0x180032e53  call    cs:__imp_SetLastError
0x180032e59  xor     eax, eax
0x180032e5b  jmp     loc_1800333BD
0x180032e60  mov     r14, [rbp+4Fh+var_80]
0x180032e64  mov     [rbp+4Fh+pulResult], r15d
0x180032e68  mov     r10d, [r14+8]
0x180032e6c  bswap   r10d
0x180032e6f  mov     [rbp+4Fh+var_88], r10d
0x180032e73  lea     eax, [r10+r10*2]
0x180032e77  lea     r9d, ds:800h[rax*2]
0x180032e7f  mov     eax, 88888889h
0x180032e84  mul     r9d
0x180032e87  shr     edx, 7
0x180032e8a  lea     ecx, [rdx+1]
0x180032e8d  add     rcx, rcx; ullOperand
0x180032e90  lea     rdx, [rbp+4Fh+pulResult]; pulResult
0x180032e94  call    ULongLongToULong
0x180032e99  test    eax, eax
0x180032e9b  jns     short loc_180032EA4
0x180032e9d  mov     ecx, 57h ; 'W'
0x180032ea2  jmp     short loc_180032E53
0x180032ea4  mov     ecx, [rbp+4Fh+pulResult]
0x180032ea7  add     ecx, r9d
0x180032eaa  test    rdi, rdi
0x180032ead  jz      loc_1800333B6
0x180032eb3  cmp     [rdi], r15
0x180032eb6  jz      loc_1800333B6
0x180032ebc  cmp     [rsi], ecx
0x180032ebe  jnb     short loc_180032EC7
0x180032ec0  mov     ecx, 7Ah ; 'z'
0x180032ec5  jmp     short loc_180032E53
0x180032ec7  cmp     r10d, 3FFFFFFFh
0x180032ece  ja      loc_1800333AC
0x180032ed4  mov     ebx, r10d
0x180032ed7  lea     rcx, ds:0[rbx*4]
0x180032edf  call    MemAlloc
0x180032ee4  mov     qword ptr [rbp+4Fh+pulResult], rax
0x180032ee8  test    rax, rax
0x180032eeb  jz      loc_1800333AC
0x180032ef1  mov     edx, [rbp+4Fh+var_90]
0x180032ef4  lea     rcx, [rbx+rbx]
0x180032ef8  mov     [rbp+4Fh+var_68], rcx
0x180032efc  lea     r8, [rcx+rax]
0x180032f00  mov     rcx, r14
0x180032f03  mov     r9, rax
0x180032f06  call    GetRevCurve
0x180032f0b  mov     rdx, [r12]
0x180032f0f  mov     r13d, [rbp+4Fh+arg_20]
0x180032f13  mov     ebx, [rdx+44h]
0x180032f16  mov     r14d, [rdx+48h]
0x180032f1a  mov     r15d, [rdx+4Ch]
0x180032f1e  bswap   ebx
0x180032f20  mov     [rbp+4Fh+var_78], ebx
0x180032f23  bswap   r14d
0x180032f26  mov     [rbp+4Fh+var_74], r14d
0x180032f2a  bswap   r15d
0x180032f2d  mov     [rbp+4Fh+var_70], r15d
0x180032f31  cmp     r13d, 3
0x180032f35  jnz     short loc_180032F52
0x180032f37  lea     rdx, [rbp+4Fh+var_60]
0x180032f3b  mov     rcx, r12
0x180032f3e  call    GetCPMediaWhitePoint
0x180032f43  test    eax, eax
0x180032f45  jnz     short loc_180032F52
0x180032f47  mov     [rbp+4Fh+var_60], ebx
0x180032f4a  mov     [rbp+4Fh+var_5C], r14d
0x180032f4e  mov     [rbp+4Fh+var_58], r15d
0x180032f52  lea     r8, BeginDict; "<<"
0x180032f59  mov     rdx, rsi
0x180032f5c  mov     rcx, rdi
0x180032f5f  call    WriteNewLineObject
0x180032f64  test    eax, eax
0x180032f66  jz      short loc_180032F83
0x180032f68  lea     r8, DictType; "/ColorRenderingType 1 "
0x180032f6f  mov     rdx, rsi
0x180032f72  mov     rcx, rdi
0x180032f75  mov     ebx, 1
0x180032f7a  call    WriteObject
0x180032f7f  test    eax, eax
0x180032f81  jnz     short loc_180032F85
0x180032f83  xor     ebx, ebx
0x180032f85  mov     eax, r13d
0x180032f88  test    r13d, r13d
0x180032f8b  jz      loc_1800330CF
0x180032f91  sub     eax, 1
0x180032f94  jz      loc_18003308C
0x180032f9a  sub     eax, 1
0x180032f9d  jz      loc_180033069
0x180032fa3  cmp     eax, 1
0x180032fa6  jnz     loc_1800330C2
0x180032fac  test    ebx, ebx
0x180032fae  jz      short loc_18003302D
0x180032fb0  lea     r8, IntentType; "/RenderingIntent "
0x180032fb7  mov     rdx, rsi
0x180032fba  mov     rcx, rdi
0x180032fbd  call    WriteNewLineObject
0x180032fc2  test    eax, eax
0x180032fc4  jz      short loc_18003302B
0x180032fc6  lea     r8, IntentACol; "/AbsoluteColorimetric"
0x180032fcd  mov     rdx, rsi
0x180032fd0  mov     rcx, rdi
0x180032fd3  call    WriteObject
0x180032fd8  test    eax, eax
0x180032fda  jz      short loc_18003302B
0x180032fdc  lea     r8, [rbp+4Fh+var_78]
0x180032fe0  mov     rdx, rsi
0x180032fe3  mov     rcx, rdi
0x180032fe6  call    SendCRDBWPoint
0x180032feb  test    eax, eax
0x180032fed  jz      short loc_18003302B
0x180032fef  lea     r9, [rbp+4Fh+var_78]
0x180032ff3  mov     r8d, r13d
0x180032ff6  mov     rdx, rsi
0x180032ff9  mov     rcx, rdi
0x180032ffc  call    SendCRDPQR
0x180033001  test    eax, eax
0x180033003  jz      short loc_18003302B
0x180033005  mov     eax, [rbp+4Fh+var_A0]
0x180033008  lea     r9, [rbp+4Fh+var_78]
0x18003300c  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180033010  mov     r8d, r13d
0x180033013  lea     rax, [rbp+4Fh+var_60]
0x180033017  mov     rdx, rsi
0x18003301a  mov     rcx, rdi
0x18003301d  mov     [rsp+0E0h+var_C0], rax
0x180033022  call    SendCRDLMN
0x180033027  test    eax, eax
0x180033029  jnz     short loc_18003302D
0x18003302b  xor     ebx, ebx
0x18003302d  mov     eax, [rbp+4Fh+var_A0]
0x180033030  cmp     eax, 58595A20h
0x180033035  jnz     loc_1800330FD
0x18003303b  test    ebx, ebx
0x18003303d  jz      loc_180033136
0x180033043  lea     r8, MatrixABCTag; "/MatrixABC "
0x18003304a  mov     rdx, rsi
0x18003304d  mov     rcx, rdi
0x180033050  call    WriteNewLineObject
0x180033055  test    eax, eax
0x180033057  jz      loc_180033134
0x18003305d  lea     r8, MatrixABCXYZCRD; "[0 1 0 1 0 0 0 0 1]"
0x180033064  jmp     loc_180033125
0x180033069  test    ebx, ebx
0x18003306b  jz      short loc_18003302D
0x18003306d  lea     r8, IntentType; "/RenderingIntent "
0x180033074  mov     rdx, rsi
0x180033077  mov     rcx, rdi
0x18003307a  call    WriteNewLineObject
0x18003307f  test    eax, eax
0x180033081  jz      short loc_1800330C0
0x180033083  lea     r8, IntentSat; "/Saturation"
0x18003308a  jmp     short loc_1800330AD
0x18003308c  test    ebx, ebx
0x18003308e  jz      short loc_18003302D
0x180033090  lea     r8, IntentType; "/RenderingIntent "
0x180033097  mov     rdx, rsi
0x18003309a  mov     rcx, rdi
0x18003309d  call    WriteNewLineObject
0x1800330a2  test    eax, eax
0x1800330a4  jz      short loc_1800330C0
0x1800330a6  lea     r8, IntentRCol; "/RelativeColorimetric"
0x1800330ad  mov     rdx, rsi
0x1800330b0  mov     rcx, rdi
0x1800330b3  call    WriteObject
0x1800330b8  test    eax, eax
0x1800330ba  jnz     loc_180032FDC
0x1800330c0  xor     ebx, ebx
0x1800330c2  test    ebx, ebx
0x1800330c4  jz      loc_18003302D
0x1800330ca  jmp     loc_180032FDC
0x1800330cf  test    ebx, ebx
0x1800330d1  jz      loc_18003302D
0x1800330d7  lea     r8, IntentType; "/RenderingIntent "
0x1800330de  mov     rdx, rsi
0x1800330e1  mov     rcx, rdi
0x1800330e4  call    WriteNewLineObject
0x1800330e9  test    eax, eax
0x1800330eb  jz      loc_18003302B
0x1800330f1  lea     r8, IntentPer; "/Perceptual"
0x1800330f8  jmp     loc_180032FCD
0x1800330fd  cmp     eax, 4C616220h
0x180033102  jnz     short loc_180033136
0x180033104  test    ebx, ebx
0x180033106  jz      short loc_180033136
0x180033108  lea     r8, MatrixABCTag; "/MatrixABC "
0x18003310f  mov     rdx, rsi
0x180033112  mov     rcx, rdi
0x180033115  call    WriteNewLineObject
0x18003311a  test    eax, eax
0x18003311c  jz      short loc_180033134
0x18003311e  lea     r8, MatrixABCLabCRD; "[0 500 0 116 -500 200 0 0 -200]"
0x180033125  mov     rdx, rsi
0x180033128  mov     rcx, rdi
0x18003312b  call    WriteObject
0x180033130  test    eax, eax
0x180033132  jnz     short loc_180033136
0x180033134  xor     ebx, ebx
0x180033136  mov     r12d, [rbp+4Fh+var_88]
0x18003313a  test    r12d, r12d
0x18003313d  jz      loc_180033383
0x180033143  test    ebx, ebx
0x180033145  jz      loc_18003339F
0x18003314b  lea     r8, NewLine; "\r\n"
0x180033152  mov     rdx, rsi
0x180033155  mov     rcx, rdi
0x180033158  call    WriteObject
0x18003315d  test    eax, eax
0x18003315f  jz      short loc_1800331BA
0x180033161  mov     r13, [rdi]
0x180033164  lea     r8, EncodeABCTag; "/EncodeABC "
0x18003316b  mov     rdx, rsi
0x18003316e  mov     rcx, rdi
0x180033171  call    WriteObject
0x180033176  test    eax, eax
0x180033178  jz      short loc_1800331BA
0x18003317a  lea     r8, BeginArray; "["
0x180033181  mov     rdx, rsi
0x180033184  mov     rcx, rdi
0x180033187  call    WriteObject
0x18003318c  test    eax, eax
0x18003318e  jz      short loc_1800331BA
0x180033190  lea     r8, BeginFunction; "{"
0x180033197  mov     rdx, rsi
0x18003319a  mov     rcx, rdi
0x18003319d  call    WriteObject
0x1800331a2  test    eax, eax
0x1800331a4  jz      short loc_1800331BA
0x1800331a6  mov     eax, [rbp+4Fh+var_8C]
0x1800331a9  cmp     [rbp+4Fh+var_68], rax
0x1800331ad  jbe     short loc_1800331C1
0x1800331af  mov     ecx, 7DBh; dwErrCode
0x1800331b4  call    cs:__imp_SetLastError
0x1800331ba  xor     ebx, ebx
0x1800331bc  jmp     loc_18003339F
0x1800331c1  cmp     r12d, 1
0x1800331c5  jnz     short loc_1800331FC
0x1800331c7  mov     rax, [rbp+4Fh+var_80]
0x1800331cb  mov     rdx, rsi
0x1800331ce  mov     rcx, rdi
0x1800331d1  movzx   eax, word ptr [rax+0Ch]
0x1800331d5  ror     ax, 8
0x1800331d9  movzx   r8d, ax
0x1800331dd  call    WriteInt
0x1800331e2  test    eax, eax
0x1800331e4  jz      short loc_1800331BA
0x1800331e6  lea     r8, DecodeA3Rev; "256 div 1.0 exch div exp "
0x1800331ed  mov     rdx, rsi
0x1800331f0  mov     rcx, rdi
0x1800331f3  call    WriteObject
0x1800331f8  test    eax, eax
0x1800331fa  jz      short loc_1800331BA
0x1800331fc  cmp     [rbp+4Fh+var_A0], 4C616220h
0x180033203  mov     r15, qword ptr [rbp+4Fh+pulResult]
0x180033207  jnz     short loc_180033223
0x180033209  lea     r8, EncodeABCLab1; "16 sub 100 div "
0x180033210  mov     rdx, rsi
0x180033213  mov     rcx, rdi
0x180033216  call    WriteObject
0x18003321b  test    eax, eax
0x18003321d  jnz     short loc_180033223
0x18003321f  xor     ebx, ebx
0x180033221  jmp     short loc_180033239
0x180033223  lea     r8, StartClip; "dup 1.0 le{dup 0.0 ge{"
0x18003322a  mov     rdx, rsi
  ... truncated ...
```
