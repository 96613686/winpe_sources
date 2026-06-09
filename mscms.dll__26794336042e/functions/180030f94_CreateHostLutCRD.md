# CreateHostLutCRD

- ea: `0x180030f94`
- end: `0x180031433`
- name: `CreateHostLutCRD`
- size: `1183`
- prototype: `__int64(unsigned int **, unsigned int, void **, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180034560`

## callees

- `0x18002b058`
- `0x18002f2dc`
- `0x180030e18`
- `0x180030f94`
- `0x180033ad4`
- `0x180033c48`
- `0x1800366f0`
- `0x1800399f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800312a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031410`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800312a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031410`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180031223`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180031223`

## pseudocode

```c
__int64 CreateHostLutCRD(unsigned int **a1, unsigned int a2, void **a3, ...)
{
  unsigned int *v3; // rax
  _DWORD *v4; // rdi
  int *v5; // r12
  unsigned int v7; // ebx
  unsigned __int32 v8; // ebx
  unsigned int *v9; // rsi
  int v10; // r15d
  int v11; // r14d
  int v12; // ecx
  char v13; // al
  unsigned int *v14; // rcx
  int v15; // ecx
  unsigned int v16; // ebx
  bool v17; // zf
  unsigned int *v18; // rsi
  __int64 v19; // r12
  unsigned int v20; // ecx
  int v21; // r9d
  unsigned __int64 v22; // r8
  unsigned int v23; // esi
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // rax
  DWORD v26; // ecx
  unsigned int v27; // r12d
  unsigned int v28; // eax
  unsigned __int64 v29; // rdx
  int *v30; // r8
  _WORD *v31; // r9
  unsigned int v32; // edi
  int *v33; // rax
  unsigned int i; // edx
  __int64 result; // rax
  int v36; // r9d
  DWORD v37; // ecx
  size_t Size; // [rsp+20h] [rbp-60h]
  size_t Sizea; // [rsp+20h] [rbp-60h]
  __int64 v40; // [rsp+38h] [rbp-48h]
  int v41; // [rsp+40h] [rbp-40h]
  size_t v42; // [rsp+50h] [rbp-30h] BYREF
  size_t v43; // [rsp+58h] [rbp-28h] BYREF
  UINT uMinuend[2]; // [rsp+60h] [rbp-20h] BYREF
  int v45; // [rsp+68h] [rbp-18h] BYREF
  int v46; // [rsp+6Ch] [rbp-14h] BYREF
  unsigned int *v47; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int64 v49; // [rsp+C0h] [rbp+40h]
  unsigned int v50; // [rsp+D0h] [rbp+50h] BYREF
  int *pulResult; // [rsp+D8h] [rbp+58h] BYREF
  va_list pulResulta; // [rsp+D8h] [rbp+58h]
  __int64 v53; // [rsp+E0h] [rbp+60h]
  va_list va1; // [rsp+E8h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(pulResulta, a3);
  pulResult = va_arg(va1, int *);
  v53 = va_arg(va1, _QWORD);
  v3 = *a1;
  LODWORD(v4) = 0;
  v5 = pulResult;
  v47 = 0;
  uMinuend[0] = 0;
  v7 = v3[5];
  v45 = 0;
  v50 = 0;
  v42 = 0;
  v43 = 0;
  v46 = 0;
  v8 = _byteswap_ulong(v7);
  if ( !(unsigned int)GetTagAtIndex((__int64)a1, a2, 0x30u, &v47, uMinuend, 0, (_DWORD *)&v42 + 1) )
    goto LABEL_57;
  v9 = v47;
  v10 = _byteswap_ulong(*v47);
  if ( v10 != 1835430961 )
  {
    if ( v10 == 1835430962 && UIntSub(uMinuend[0], 0x34u, (UINT *)&v42 + 1) >= 0 )
    {
      *(_QWORD *)uMinuend = v9 + 13;
      LODWORD(v4) = 0;
      goto LABEL_7;
    }
LABEL_57:
    v37 = 2011;
    goto LABEL_58;
  }
  *(_QWORD *)uMinuend = v47 + 12;
LABEL_7:
  GetCLUTInfo(
    v10,
    (_DWORD)v9,
    (unsigned int)&v45,
    (unsigned int)&v43 + 4,
    (__int64)&v50,
    (__int64)&v42,
    (__int64)&v43,
    (__int64)&v46);
  v11 = HIDWORD(v43);
  if ( (unsigned int)(HIDWORD(v43) - 3) > 1 || v45 != 3 )
    return 0;
  if ( a3 )
  {
    v4 = *a3;
    if ( *a3 )
    {
      v12 = *v5;
      if ( (unsigned int)*v5 >= 0xA0 )
      {
        *a3 = v4 + 40;
        *v4 = 160;
        *v5 = v12 - 160;
        v4[3] = v53;
        v13 = 8;
        v4[2] = v8;
        if ( v10 != 1835430961 )
          v13 = 16;
        v14 = *a1;
        *((_BYTE *)v4 + 43) = v13;
        v4[4] = _byteswap_ulong(v14[17]);
        v4[5] = _byteswap_ulong(v14[18]);
        v4[6] = _byteswap_ulong(v14[19]);
        if ( !(unsigned int)GetCPMediaWhitePoint(a1, v4 + 7) )
        {
          v4[7] = v4[4];
          v4[8] = v4[5];
          v4[9] = v4[6];
        }
        v15 = v42;
        *((_BYTE *)v4 + 42) = v50;
        *((_WORD *)v4 + 41) = v43;
        v41 = HIDWORD(v42);
        v40 = *(_QWORD *)uMinuend;
        *((_WORD *)v4 + 40) = v15;
        LODWORD(Size) = v15;
        *((_BYTE *)v4 + 40) = 3;
        *((_BYTE *)v4 + 41) = v11;
        if ( (unsigned int)CreateHostInputOutputArray((int)a3, (int)v5, (int)v4 + 88, 3, Size, 0, v10, v40, v41) )
        {
          LODWORD(Sizea) = v43;
          if ( (unsigned int)CreateHostInputOutputArray(
                               (int)a3,
                               (int)v5,
                               (int)v4 + 120,
                               v11,
                               Sizea,
                               3 * v42 + v11 * v50 * v50 * v50,
                               v10,
                               *(__int64 *)uMinuend,
                               SHIDWORD(v42)) )
          {
            v17 = v8 == 1482250784;
            v16 = 1;
            if ( v17 )
            {
              v18 = v9 + 3;
              v19 = 0;
              do
              {
                v4[v19 + 11] = MulDiv(_byteswap_ulong(*v18++), 0x10000, 131052);
                v19 = (unsigned int)(v19 + 1);
              }
              while ( (unsigned int)v19 < 9 );
              v11 = HIDWORD(v43);
            }
LABEL_24:
            if ( !v16 )
              return v16;
            v20 = v50;
            v21 = v42;
            v22 = 3LL * (unsigned int)v42;
            v49 = v22;
            v23 = v11 * v20 * v20;
            LODWORD(v24) = 0;
            if ( v22 > 0xFFFFFFFF )
              goto LABEL_31;
            v24 = v50 * (unsigned __int64)v23;
            if ( v24 > 0xFFFFFFFF )
              goto LABEL_30;
            if ( v10 == 1835430961 )
            {
              LODWORD(v25) = 3 * v42;
            }
            else
            {
              v25 = 2LL * (unsigned int)v22;
              if ( v25 > 0xFFFFFFFF )
              {
LABEL_31:
                SetLastError(0x7DBu);
                v21 = v42;
                v16 = 0;
                v22 = v49;
                v20 = v50;
                goto LABEL_32;
              }
              v24 = 2LL * (unsigned int)v24;
              if ( v24 > 0xFFFFFFFF )
              {
LABEL_30:
                LODWORD(v24) = -1;
                goto LABEL_31;
              }
            }
            LODWORD(v24) = v25 + v24;
            if ( (unsigned int)v24 < (unsigned int)v25 )
            {
LABEL_33:
              v26 = 2011;
LABEL_52:
              SetLastError(v26);
              return 0;
            }
LABEL_32:
            if ( (unsigned int)v24 <= HIDWORD(v42) )
            {
              if ( v16 )
              {
                v27 = 0;
                *((_QWORD *)v4 + 19) = *a3;
                v28 = 0;
                while ( v28 < v20 )
                {
                  if ( v10 == 1835430961 )
                    v29 = (unsigned int)(3 * v21) + (unsigned __int64)(v23 * v28);
                  else
                    v29 = 2 * (v22 + v23 * (unsigned __int64)v28);
                  v30 = pulResult;
                  v31 = (_WORD *)(v29 + *(_QWORD *)uMinuend);
                  v32 = *pulResult;
                  if ( v10 == 1835430961 )
                  {
                    if ( v32 < v23 )
                      goto LABEL_51;
                    memcpy_0(*a3, (const void *)(v29 + *(_QWORD *)uMinuend), v23);
                    v33 = pulResult;
                    *a3 = (char *)*a3 + v23;
                    *v33 = v32 - v23;
                  }
                  else
                  {
                    if ( v32 < v23 )
                    {
LABEL_51:
                      v26 = 122;
                      goto LABEL_52;
                    }
                    for ( i = 0; i < v23; *a3 = (char *)*a3 + 1 )
                    {
                      ++i;
                      *(_BYTE *)*a3 = __ROR2__(*v31, 8) >> 8;
                    }
                    *v30 = v32 - v23;
                  }
                  v20 = v50;
                  ++v27;
                  v22 = v49;
                  v28 = v27;
                  v21 = v42;
                }
              }
              return v16;
            }
            goto LABEL_33;
          }
        }
      }
      else
      {
        v4 = 0;
        SetLastError(0x7Au);
      }
      v16 = 0;
      goto LABEL_24;
    }
  }
  LODWORD(pulResult) = (_DWORD)v4;
  if ( ULongLongToULong(
         2LL
       * ((HIDWORD(v43) * (_DWORD)v43 * v46 + 3 * ((_DWORD)v42 * v46 + 736) + HIDWORD(v43) * v50 * v50 * v50) / 0xF0 + 1),
         (ULONG *)pulResulta) >= 0 )
  {
    result = 1;
    *v5 = v36 + (_DWORD)pulResult;
    return result;
  }
  v37 = 87;
LABEL_58:
  SetLastError(v37);
  return 0;
}

```

## disassembly

```asm
0x180030f94  mov     [rsp-38h+arg_8], rbx
0x180030f99  mov     [rsp-38h+pulResult], r9
0x180030f9e  mov     [rsp-38h+arg_0], rcx
0x180030fa3  push    rbp
0x180030fa4  push    rsi
0x180030fa5  push    rdi
0x180030fa6  push    r12
0x180030fa8  push    r13
0x180030faa  push    r14
0x180030fac  push    r15
0x180030fae  mov     rbp, rsp
0x180030fb1  sub     rsp, 80h
0x180030fb8  mov     rax, [rcx]
0x180030fbb  xor     edi, edi
0x180030fbd  mov     r12, r9
0x180030fc0  mov     [rbp+var_10], rdi
0x180030fc4  mov     r13, r8
0x180030fc7  mov     [rbp+uMinuend], edi
0x180030fca  lea     r9, [rbp+var_10]
0x180030fce  mov     dword ptr [rbp+var_30+4], edi
0x180030fd1  mov     ebx, [rax+14h]
0x180030fd4  lea     r8d, [rdi+30h]
0x180030fd8  lea     rax, [rbp+var_30+4]
0x180030fdc  mov     [rbp+var_18], edi
0x180030fdf  mov     qword ptr [rsp+80h+var_50], rax
0x180030fe4  lea     rax, [rbp+uMinuend]
0x180030fe8  mov     qword ptr [rsp+80h+var_58], rdi
0x180030fed  mov     [rsp+80h+Size], rax
0x180030ff2  mov     dword ptr [rbp+var_28+4], edi
0x180030ff5  mov     [rbp+arg_10], edi
0x180030ff8  mov     dword ptr [rbp+var_30], edi
0x180030ffb  mov     dword ptr [rbp+var_28], edi
0x180030ffe  mov     [rbp+var_14], edi
0x180031001  bswap   ebx
0x180031003  call    GetTagAtIndex
0x180031008  test    eax, eax
0x18003100a  jz      loc_18003140B
0x180031010  mov     rsi, [rbp+var_10]
0x180031014  mov     r15d, [rsi]
0x180031017  bswap   r15d
0x18003101a  cmp     r15d, 6D667431h
0x180031021  jz      short loc_180031053
0x180031023  cmp     r15d, 6D667432h
0x18003102a  jnz     loc_18003140B
0x180031030  mov     ecx, [rbp+uMinuend]; uMinuend
0x180031033  lea     r8, [rbp+var_30+4]; puResult
0x180031037  lea     edx, [rdi+34h]; uSubtrahend
0x18003103a  call    UIntSub
0x18003103f  test    eax, eax
0x180031041  js      loc_18003140B
0x180031047  lea     rdi, [rsi+34h]
0x18003104b  mov     qword ptr [rbp+uMinuend], rdi
0x18003104f  xor     edi, edi
0x180031051  jmp     short loc_18003105B
0x180031053  lea     rax, [rsi+30h]
0x180031057  mov     qword ptr [rbp+uMinuend], rax
0x18003105b  lea     rax, [rbp+var_14]
0x18003105f  mov     rdx, rsi
0x180031062  mov     [rsp+80h+var_48], rax
0x180031067  lea     r9, [rbp+var_28+4]
0x18003106b  lea     rax, [rbp+var_28]
0x18003106f  mov     ecx, r15d
0x180031072  mov     qword ptr [rsp+80h+var_50], rax
0x180031077  lea     r8, [rbp+var_18]
0x18003107b  lea     rax, [rbp+var_30]
0x18003107f  mov     qword ptr [rsp+80h+var_58], rax
0x180031084  lea     rax, [rbp+arg_10]
0x180031088  mov     [rsp+80h+Size], rax
0x18003108d  call    GetCLUTInfo
0x180031092  mov     r14d, dword ptr [rbp+var_28+4]
0x180031096  lea     eax, [r14-3]
0x18003109a  cmp     eax, 1
0x18003109d  ja      loc_180031416
0x1800310a3  cmp     [rbp+var_18], 3
0x1800310a7  jnz     loc_180031416
0x1800310ad  test    r13, r13
0x1800310b0  jz      loc_1800313A1
0x1800310b6  mov     rdi, [r13+0]
0x1800310ba  test    rdi, rdi
0x1800310bd  jz      loc_1800313A1
0x1800310c3  mov     ecx, [r12]
0x1800310c7  mov     edx, 0A0h
0x1800310cc  cmp     ecx, edx
0x1800310ce  jnb     short loc_1800310E0
0x1800310d0  xor     edi, edi
0x1800310d2  lea     ecx, [rdx-26h]; dwErrCode
0x1800310d5  call    cs:__imp_SetLastError
0x1800310db  jmp     loc_1800311AC
0x1800310e0  mov     r8, [rbp+arg_0]
0x1800310e4  lea     rax, [rdi+0A0h]
0x1800310eb  mov     [r13+0], rax
0x1800310ef  cmp     r15d, 6D667431h
0x1800310f6  mov     [rdi], edx
0x1800310f8  lea     eax, [rcx-0A0h]
0x1800310fe  mov     [r12], eax
0x180031102  lea     rdx, [rdi+1Ch]
0x180031106  mov     eax, dword ptr [rbp+arg_20]
0x180031109  mov     [rdi+0Ch], eax
0x18003110c  mov     eax, 8
0x180031111  mov     [rdi+8], ebx
0x180031114  lea     ecx, [rax+8]
0x180031117  cmovnz  eax, ecx
0x18003111a  mov     rcx, [r8]
0x18003111d  mov     [rdi+2Bh], al
0x180031120  mov     eax, [rcx+44h]
0x180031123  bswap   eax
0x180031125  mov     [rdi+10h], eax
0x180031128  mov     eax, [rcx+48h]
0x18003112b  bswap   eax
0x18003112d  mov     [rdi+14h], eax
0x180031130  mov     eax, [rcx+4Ch]
0x180031133  mov     rcx, r8
0x180031136  bswap   eax
0x180031138  mov     [rdi+18h], eax
0x18003113b  call    GetCPMediaWhitePoint
0x180031140  test    eax, eax
0x180031142  jnz     short loc_180031156
0x180031144  mov     eax, [rdi+10h]
0x180031147  mov     [rdi+1Ch], eax
0x18003114a  mov     eax, [rdi+14h]
0x18003114d  mov     [rdi+20h], eax
0x180031150  mov     eax, [rdi+18h]
0x180031153  mov     [rdi+24h], eax
0x180031156  mov     eax, [rbp+arg_10]
0x180031159  lea     r8, [rdi+58h]; int
0x18003115d  mov     ecx, dword ptr [rbp+var_30]
0x180031160  mov     r9d, 3; int
0x180031166  mov     [rdi+2Ah], al
0x180031169  mov     rdx, r12; int
0x18003116c  mov     eax, dword ptr [rbp+var_28]
0x18003116f  mov     [rdi+52h], ax
0x180031173  mov     eax, dword ptr [rbp+var_30+4]
0x180031176  mov     [rsp+80h+var_40], eax; int
0x18003117a  mov     rax, qword ptr [rbp+uMinuend]
0x18003117e  mov     [rsp+80h+var_48], rax; __int64
0x180031183  mov     [rsp+80h+var_50], r15d; int
0x180031188  mov     [rdi+50h], cx
0x18003118c  mov     [rsp+80h+var_58], 0; int
0x180031194  mov     dword ptr [rsp+80h+Size], ecx; Size
0x180031198  mov     rcx, r13; int
0x18003119b  mov     byte ptr [rdi+28h], 3
0x18003119f  mov     [rdi+29h], r14b
0x1800311a3  call    CreateHostInputOutputArray
0x1800311a8  test    eax, eax
0x1800311aa  jnz     short loc_1800311B3
0x1800311ac  xor     ebx, ebx
0x1800311ae  jmp     loc_18003123F
0x1800311b3  mov     eax, [rbp+arg_10]
0x1800311b6  lea     r8, [rdi+78h]; int
0x1800311ba  mov     ecx, eax
0x1800311bc  mov     r9d, r14d; int
0x1800311bf  imul    ecx, eax
0x1800311c2  mov     rdx, r12; int
0x1800311c5  imul    ecx, eax
0x1800311c8  mov     eax, dword ptr [rbp+var_30]
0x1800311cb  lea     eax, [rax+rax*2]
0x1800311ce  imul    ecx, r14d
0x1800311d2  add     ecx, eax
0x1800311d4  mov     eax, dword ptr [rbp+var_30+4]
0x1800311d7  mov     [rsp+80h+var_40], eax; int
0x1800311db  mov     rax, qword ptr [rbp+uMinuend]
0x1800311df  mov     [rsp+80h+var_48], rax; __int64
0x1800311e4  mov     eax, dword ptr [rbp+var_28]
0x1800311e7  mov     [rsp+80h+var_50], r15d; int
0x1800311ec  mov     [rsp+80h+var_58], ecx; int
0x1800311f0  mov     rcx, r13; int
0x1800311f3  mov     dword ptr [rsp+80h+Size], eax; Size
0x1800311f7  call    CreateHostInputOutputArray
0x1800311fc  test    eax, eax
0x1800311fe  jz      short loc_1800311AC
0x180031200  cmp     ebx, 58595A20h
0x180031206  mov     ebx, 1
0x18003120b  jnz     short loc_18003123F
0x18003120d  add     rsi, 0Ch
0x180031211  xor     r12d, r12d
0x180031214  mov     ecx, [rsi]
0x180031216  mov     edx, 10000h; nNumerator
0x18003121b  bswap   ecx; nNumber
0x18003121d  mov     r8d, 1FFECh; nDenominator
0x180031223  call    cs:__imp_MulDiv
0x180031229  mov     [rdi+r12*4+2Ch], eax
0x18003122e  lea     rsi, [rsi+4]
0x180031232  inc     r12d
0x180031235  cmp     r12d, 9
0x180031239  jb      short loc_180031214
0x18003123b  mov     r14d, dword ptr [rbp+var_28+4]
0x18003123f  test    ebx, ebx
0x180031241  jz      loc_18003139D
0x180031247  mov     ecx, [rbp+arg_10]
0x18003124a  mov     edx, 0FFFFFFFFh
0x18003124f  mov     r9d, dword ptr [rbp+var_30]
0x180031253  mov     esi, ecx
0x180031255  imul    esi, ecx
0x180031258  mov     r12d, 7DBh
0x18003125e  lea     r8, [r9+r9*2]
0x180031262  mov     [rbp+arg_0], r8
0x180031266  imul    esi, r14d
0x18003126a  xor     r14d, r14d
0x18003126d  cmp     r8, rdx
0x180031270  ja      short loc_1800312A0
0x180031272  mov     r14d, esi
0x180031275  imul    r14, rcx
0x180031279  cmp     r14, rdx
0x18003127c  ja      short loc_18003129D
0x18003127e  cmp     r15d, 6D667431h
0x180031285  jz      short loc_1800312C4
0x180031287  mov     eax, r8d
0x18003128a  add     rax, rax
0x18003128d  cmp     rax, rdx
0x180031290  ja      short loc_1800312A0
0x180031292  mov     r14d, r14d
0x180031295  add     r14, r14
0x180031298  cmp     r14, rdx
0x18003129b  jbe     short loc_1800312C7
0x18003129d  mov     r14d, edx
0x1800312a0  mov     ecx, r12d; dwErrCode
0x1800312a3  call    cs:__imp_SetLastError
0x1800312a9  mov     r9d, dword ptr [rbp+var_30]
0x1800312ad  xor     ebx, ebx
0x1800312af  mov     r8, [rbp+arg_0]
0x1800312b3  mov     ecx, [rbp+arg_10]
0x1800312b6  cmp     r14d, dword ptr [rbp+var_30+4]
0x1800312ba  jbe     short loc_1800312D1
0x1800312bc  mov     ecx, r12d
0x1800312bf  jmp     loc_180031395
0x1800312c4  mov     eax, r8d
0x1800312c7  add     r14d, eax
0x1800312ca  cmp     r14d, eax
0x1800312cd  jb      short loc_1800312BC
0x1800312cf  jmp     short loc_1800312B6
0x1800312d1  test    ebx, ebx
0x1800312d3  jz      loc_18003139D
0x1800312d9  mov     rax, [r13+0]
0x1800312dd  xor     r12d, r12d
0x1800312e0  mov     [rdi+98h], rax
0x1800312e7  xor     eax, eax
0x1800312e9  cmp     eax, ecx
0x1800312eb  jnb     loc_18003139D
0x1800312f1  mov     r14d, esi
0x1800312f4  cmp     r15d, 6D667431h
0x1800312fb  jnz     short loc_18003130B
0x1800312fd  imul    eax, esi
0x180031300  lea     ecx, [r9+r9*2]
0x180031304  mov     edx, eax
0x180031306  add     rdx, rcx
0x180031309  jmp     short loc_180031317
0x18003130b  mov     edx, eax
0x18003130d  imul    rdx, r14
0x180031311  add     rdx, r8
0x180031314  add     rdx, rdx
0x180031317  mov     r9, qword ptr [rbp+uMinuend]
0x18003131b  mov     r8, [rbp+pulResult]
0x18003131f  add     r9, rdx
0x180031322  mov     edi, [r8]
0x180031325  cmp     r15d, 6D667431h
0x18003132c  jnz     short loc_18003134F
0x18003132e  cmp     edi, esi
0x180031330  jb      short loc_180031390
0x180031332  mov     rcx, [r13+0]; void *
0x180031336  mov     r8, r14; Size
0x180031339  mov     rdx, r9; Src
0x18003133c  call    memcpy_0
0x180031341  mov     rax, [rbp+pulResult]
0x180031345  add     [r13+0], r14
0x180031349  sub     edi, esi
0x18003134b  mov     [rax], edi
0x18003134d  jmp     short loc_18003137A
0x18003134f  cmp     edi, esi
0x180031351  jb      short loc_180031390
0x180031353  xor     edx, edx
0x180031355  test    esi, esi
0x180031357  jz      short loc_180031375
0x180031359  movzx   ecx, word ptr [r9]
0x18003135d  inc     edx
0x18003135f  mov     rax, [r13+0]
0x180031363  ror     cx, 8
0x180031367  shr     cx, 8
0x18003136b  mov     [rax], cl
0x18003136d  inc     qword ptr [r13+0]
0x180031371  cmp     edx, esi
0x180031373  jb      short loc_180031359
0x180031375  sub     edi, esi
0x180031377  mov     [r8], edi
0x18003137a  mov     ecx, [rbp+arg_10]
0x18003137d  inc     r12d
0x180031380  mov     r8, [rbp+arg_0]
0x180031384  mov     eax, r12d
0x180031387  mov     r9d, dword ptr [rbp+var_30]
0x18003138b  jmp     loc_1800312E9
0x180031390  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180031395  call    cs:__imp_SetLastError
0x18003139b  xor     ebx, ebx
0x18003139d  mov     eax, ebx
0x18003139f  jmp     short loc_180031418
0x1800313a1  mov     eax, [rbp+arg_10]
0x1800313a4  mov     r9d, eax
0x1800313a7  mov     ecx, [rbp+var_14]
0x1800313aa  imul    r9d, eax
0x1800313ae  mov     dword ptr [rbp+pulResult], edi
0x1800313b1  imul    r9d, eax
  ... truncated ...
```
