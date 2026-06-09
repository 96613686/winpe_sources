# remainder_numeric

- ea: `0x1800166fc`
- end: `0x180016b46`
- name: `remainder_numeric`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180015060`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000be30`
- `0x180015a18`
- `0x180015b28`
- `0x1800166fc`
- `0x180016b4c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001691e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001691e`

## string_xrefs

- `0x180016913`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall remainder_numeric(__int64 a1, __int128 *a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __m128i v6; // xmm0
  char v7; // r14
  int v8; // eax
  int v9; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // ecx
  int v14; // ecx
  int *v15; // rdi
  int *v16; // rbx
  double v17; // xmm1_8
  __int64 v18; // rax
  HMODULE ModuleHandleA; // rax
  __int128 *v20; // rax
  __int128 v21; // xmm6
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  unsigned __int64 v26; // rcx
  double v27; // xmm0_8
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  __m128i v31; // [rsp+30h] [rbp-50h] BYREF
  __m128i v32; // [rsp+40h] [rbp-40h] BYREF
  __int128 v33; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v34[16]; // [rsp+60h] [rbp-20h] BYREF

  v3 = *a2;
  v32 = (__m128i)0x10FuLL;
  v31 = (__m128i)0x10FuLL;
  v33 = v3;
  v32 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v34, MintValue_CoerceToNumber, &v33, 10);
  if ( (unsigned __int8)_mm_cvtsi128_si32(v32) == 0xFE )
    goto LABEL_8;
  v33 = *a3;
  v6 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v34, MintValue_CoerceToNumber, &v33, 10);
  v7 = _mm_cvtsi128_si32(v6);
  v31 = v6;
  if ( v7 == -2 )
  {
    if ( v32.m128i_i8[0] < 12 || (v32.m128i_i16[0] & 0x100) != 0 || *(_DWORD *)v32.m128i_i64[1] == -1 )
    {
LABEL_9:
      if ( v7 >= 12 && (v31.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v31.m128i_i64[1] != -1 )
      {
        v9 = *(_DWORD *)v31.m128i_i64[1] - 1;
        *(_DWORD *)v31.m128i_i64[1] = v9;
        if ( !v9 )
          (*(void (__fastcall **)(__m128i *))(v31.m128i_i64[1] + 8))(&v31);
      }
      goto LABEL_14;
    }
    v8 = *(_DWORD *)v32.m128i_i64[1] - 1;
    *(_DWORD *)v32.m128i_i64[1] = v8;
    if ( !v8 )
      (*(void (__fastcall **)(__m128i *))(v32.m128i_i64[1] + 8))(&v32);
LABEL_8:
    v7 = v31.m128i_i8[0];
    goto LABEL_9;
  }
  if ( v32.m128i_i8[0] > 6 )
  {
    if ( v32.m128i_i8[0] != 7 )
    {
      if ( v32.m128i_i8[0] == 8 )
        goto LABEL_22;
      if ( v32.m128i_i8[0] == 9 || (v11 = v32.m128i_i8[0] - 10, v32.m128i_i8[0] == 10) )
      {
        v12 = 3;
        goto LABEL_31;
      }
      goto LABEL_27;
    }
  }
  else
  {
    switch ( v32.m128i_i8[0] )
    {
      case 6:
        goto LABEL_22;
      case 1:
        goto LABEL_30;
      case 2:
LABEL_22:
        v12 = 1;
        goto LABEL_31;
    }
    if ( v32.m128i_i8[0] != 3 )
    {
      v11 = v32.m128i_i8[0] - 4;
      if ( v32.m128i_i8[0] == 4 )
        goto LABEL_22;
LABEL_27:
      if ( v11 != 1 )
      {
        v12 = 0;
        goto LABEL_31;
      }
    }
  }
LABEL_30:
  v12 = 2;
LABEL_31:
  if ( v7 > 6 )
  {
    if ( v7 != 7 )
    {
      if ( v7 == 8 )
        goto LABEL_37;
      if ( v7 == 9 || (v13 = v7 - 10, v7 == 10) )
      {
        v14 = 3;
        goto LABEL_46;
      }
      goto LABEL_42;
    }
  }
  else
  {
    switch ( v7 )
    {
      case 6:
        goto LABEL_37;
      case 1:
        goto LABEL_45;
      case 2:
LABEL_37:
        v14 = 1;
        goto LABEL_46;
    }
    if ( v7 != 3 )
    {
      v13 = v7 - 4;
      if ( v7 == 4 )
        goto LABEL_37;
LABEL_42:
      if ( v13 != 1 )
      {
        v14 = 0;
        goto LABEL_46;
      }
    }
  }
LABEL_45:
  v14 = 2;
LABEL_46:
  v15 = (int *)v32.m128i_i64[1];
  v16 = (int *)v31.m128i_i64[1];
  if ( v12 == 3 || v14 == 3 )
    goto LABEL_59;
  v17 = *(double *)&v31.m128i_i64[1];
  v18 = v31.m128i_i64[1];
  if ( v14 != 1 && v14 != 2 )
    v18 = (unsigned int)(int)*(double *)&v31.m128i_i64[1];
  if ( !v18 )
  {
    v33 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v33 = Intlstr_GetString_LoadString(ModuleHandleA, 2064);
    BYTE8(v33) = 0;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
LABEL_14:
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 4) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  if ( v12 == 2 && v14 == 1 && v31.m128i_i64[1] < 0 )
    goto LABEL_59;
  if ( v14 == 2 && v12 == 1 )
  {
    if ( v32.m128i_i64[1] < 0 )
    {
LABEL_59:
      v20 = (__int128 *)remainder_numeric_real((unsigned int)v34, (unsigned int)&v32, v12, (unsigned int)&v31, v14);
LABEL_60:
      v21 = *v20;
      goto LABEL_61;
    }
    goto LABEL_89;
  }
  if ( v12 == 2 )
    goto LABEL_89;
  if ( v14 == 2 )
  {
    if ( v12 != 1 )
    {
      v26 = 0;
      v27 = *(double *)&v32.m128i_i64[1];
      if ( *(double *)&v32.m128i_i64[1] >= 9.223372036854776e18 )
      {
        v27 = *(double *)&v32.m128i_i64[1] - 9.223372036854776e18;
        if ( *(double *)&v32.m128i_i64[1] - 9.223372036854776e18 < 9.223372036854776e18 )
          v26 = 0x8000000000000000uLL;
      }
      v28 = v26 + (unsigned int)(int)v27;
      goto LABEL_91;
    }
LABEL_89:
    v28 = v32.m128i_u64[1];
    if ( v14 != 1 && v14 != 2 )
    {
      v30 = 0;
      if ( *(double *)&v31.m128i_i64[1] >= 9.223372036854776e18 )
      {
        v17 = *(double *)&v31.m128i_i64[1] - 9.223372036854776e18;
        if ( *(double *)&v31.m128i_i64[1] - 9.223372036854776e18 < 9.223372036854776e18 )
          v30 = 0x8000000000000000uLL;
      }
      v29 = v30 + (unsigned int)(int)v17;
      goto LABEL_96;
    }
LABEL_91:
    v29 = v31.m128i_u64[1];
LABEL_96:
    v20 = (__int128 *)fit_result_unsigned((unsigned int)v34, v28 % v29, (unsigned int)&v32, 1, (__int64)&v31);
    goto LABEL_60;
  }
  if ( v12 == 1 )
    v24 = v32.m128i_i64[1];
  else
    v24 = (unsigned int)(int)*(double *)&v32.m128i_i64[1];
  v25 = v31.m128i_i64[1];
  if ( v14 != 1 )
    v25 = (unsigned int)(int)*(double *)&v31.m128i_i64[1];
  if ( v24 != 0x8000000000000000uLL || v25 != -1 )
  {
    v20 = (__int128 *)fit_result_signed((unsigned int)v34, v24 % v25, (unsigned int)&v32, v12, (__int64)&v31, v14);
    goto LABEL_60;
  }
  v33 = 8u;
  v21 = 8u;
LABEL_61:
  if ( v32.m128i_i8[0] >= 12 && (v32.m128i_i16[0] & 0x100) == 0 && *v15 != -1 )
  {
    v22 = *v15 - 1;
    *v15 = v22;
    if ( !v22 )
      (*(void (__fastcall **)(__m128i *))(v32.m128i_i64[1] + 8))(&v32);
    v7 = v31.m128i_i8[0];
    v16 = (int *)v31.m128i_i64[1];
  }
  if ( v7 >= 12 && (v31.m128i_i16[0] & 0x100) == 0 && *v16 != -1 )
  {
    v23 = *v16 - 1;
    *v16 = v23;
    if ( !v23 )
      (*(void (__fastcall **)(__m128i *))(v31.m128i_i64[1] + 8))(&v31);
  }
  *(_OWORD *)a1 = v21;
  return a1;
}

```

## disassembly

```asm
0x1800166fc  push    rbp
0x1800166fe  push    rbx
0x1800166ff  push    rdi
0x180016700  push    r14
0x180016702  push    r15
0x180016704  mov     rbp, rsp
0x180016707  sub     rsp, 80h
0x18001670e  movups  xmm0, xmmword ptr [rdx]
0x180016711  mov     rbx, r8
0x180016714  mov     r15, rcx
0x180016717  lea     r8, [rbp+var_30]
0x18001671b  movaps  [rsp+80h+var_10], xmm6
0x180016720  mov     edi, 0Ah
0x180016725  mov     qword ptr [rbp+var_40], 10Fh
0x18001672d  mov     r9d, edi
0x180016730  mov     qword ptr [rbp+var_40+8], 0
0x180016738  lea     rdx, MintValue_CoerceToNumber
0x18001673f  mov     qword ptr [rbp+var_50], 10Fh
0x180016747  lea     rcx, [rbp+var_20]
0x18001674b  mov     qword ptr [rbp+var_50+8], 0
0x180016753  movdqu  [rbp+var_30], xmm0
0x180016758  call    MintValue_CoerceAndRaiseInvalidCastException
0x18001675d  movups  xmm0, xmmword ptr [rax]
0x180016760  movd    eax, xmm0
0x180016764  movups  [rbp+var_40], xmm0
0x180016768  cmp     al, 0FEh
0x18001676a  jz      short loc_1800167D3
0x18001676c  movups  xmm0, xmmword ptr [rbx]
0x18001676f  mov     r9d, edi
0x180016772  lea     r8, [rbp+var_30]
0x180016776  lea     rdx, MintValue_CoerceToNumber
0x18001677d  lea     rcx, [rbp+var_20]
0x180016781  movdqu  [rbp+var_30], xmm0
0x180016786  call    MintValue_CoerceAndRaiseInvalidCastException
0x18001678b  movups  xmm0, xmmword ptr [rax]
0x18001678e  movd    r14d, xmm0
0x180016793  movups  [rbp+var_50], xmm0
0x180016797  cmp     r14b, 0FEh
0x18001679b  jnz     loc_18001683C
0x1800167a1  cmp     byte ptr [rbp+var_40], 0Ch
0x1800167a5  jl      short loc_1800167D7
0x1800167a7  test    dword ptr [rbp+var_40], 100h
0x1800167ae  jnz     short loc_1800167D7
0x1800167b0  mov     rcx, qword ptr [rbp+var_40+8]
0x1800167b4  mov     eax, [rcx]
0x1800167b6  cmp     eax, 0FFFFFFFFh
0x1800167b9  jz      short loc_1800167D7
0x1800167bb  sub     eax, 1
0x1800167be  mov     [rcx], eax
0x1800167c0  jnz     short loc_1800167D3
0x1800167c2  mov     rax, qword ptr [rbp+var_40+8]
0x1800167c6  lea     rcx, [rbp+var_40]
0x1800167ca  mov     rax, [rax+8]
0x1800167ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167d3  mov     r14b, byte ptr [rbp+var_50]
0x1800167d7  cmp     r14b, 0Ch
0x1800167db  jl      short loc_180016809
0x1800167dd  test    dword ptr [rbp+var_50], 100h
0x1800167e4  jnz     short loc_180016809
0x1800167e6  mov     rcx, qword ptr [rbp+var_50+8]
0x1800167ea  mov     eax, [rcx]
0x1800167ec  cmp     eax, 0FFFFFFFFh
0x1800167ef  jz      short loc_180016809
0x1800167f1  sub     eax, 1
0x1800167f4  mov     [rcx], eax
0x1800167f6  jnz     short loc_180016809
0x1800167f8  mov     rax, qword ptr [rbp+var_50+8]
0x1800167fc  lea     rcx, [rbp+var_50]
0x180016800  mov     rax, [rax+8]
0x180016804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016809  xor     edx, edx
0x18001680b  xor     ecx, ecx
0x18001680d  mov     eax, 0FFh
0x180016812  mov     [r15+8], rcx
0x180016816  and     eax, 0FFFFFFFEh
0x180016819  mov     [r15+4], edx
0x18001681d  or      eax, 0FEh
0x180016822  mov     [r15], eax
0x180016825  movaps  xmm6, [rsp+80h+var_10]
0x18001682a  mov     rax, r15
0x18001682d  add     rsp, 80h
0x180016834  pop     r15
0x180016836  pop     r14
0x180016838  pop     rdi
0x180016839  pop     rbx
0x18001683a  pop     rbp
0x18001683b  retn
0x18001683c  movsx   ecx, byte ptr [rbp+var_40]
0x180016840  mov     edx, 2
0x180016845  lea     r10d, [rdx+1]
0x180016849  lea     r9d, [rdx-1]
0x18001684d  cmp     ecx, 6
0x180016850  jg      short loc_18001686D
0x180016852  jz      short loc_180016868
0x180016854  sub     ecx, r9d
0x180016857  jz      short loc_180016890
0x180016859  sub     ecx, r9d
0x18001685c  jz      short loc_180016868
0x18001685e  sub     ecx, r9d
0x180016861  jz      short loc_180016890
0x180016863  sub     ecx, r9d
0x180016866  jnz     short loc_180016881
0x180016868  mov     r8d, r9d
0x18001686b  jmp     short loc_180016893
0x18001686d  sub     ecx, 7
0x180016870  jz      short loc_180016890
0x180016872  sub     ecx, r9d
0x180016875  jz      short loc_180016868
0x180016877  sub     ecx, r9d
0x18001687a  jz      short loc_18001688B
0x18001687c  sub     ecx, r9d
0x18001687f  jz      short loc_18001688B
0x180016881  cmp     ecx, r9d
0x180016884  jz      short loc_180016890
0x180016886  xor     r8d, r8d
0x180016889  jmp     short loc_180016893
0x18001688b  mov     r8d, r10d
0x18001688e  jmp     short loc_180016893
0x180016890  mov     r8d, edx
0x180016893  movsx   ecx, r14b
0x180016897  cmp     ecx, 6
0x18001689a  jg      short loc_1800168B7
0x18001689c  jz      short loc_1800168B2
0x18001689e  sub     ecx, r9d
0x1800168a1  jz      short loc_1800168D9
0x1800168a3  sub     ecx, r9d
0x1800168a6  jz      short loc_1800168B2
0x1800168a8  sub     ecx, r9d
0x1800168ab  jz      short loc_1800168D9
0x1800168ad  sub     ecx, r9d
0x1800168b0  jnz     short loc_1800168CB
0x1800168b2  mov     ecx, r9d
0x1800168b5  jmp     short loc_1800168DB
0x1800168b7  sub     ecx, 7
0x1800168ba  jz      short loc_1800168D9
0x1800168bc  sub     ecx, r9d
0x1800168bf  jz      short loc_1800168B2
0x1800168c1  sub     ecx, r9d
0x1800168c4  jz      short loc_1800168D4
0x1800168c6  sub     ecx, r9d
0x1800168c9  jz      short loc_1800168D4
0x1800168cb  cmp     ecx, r9d
0x1800168ce  jz      short loc_1800168D9
0x1800168d0  xor     ecx, ecx
0x1800168d2  jmp     short loc_1800168DB
0x1800168d4  mov     ecx, r10d
0x1800168d7  jmp     short loc_1800168DB
0x1800168d9  mov     ecx, edx
0x1800168db  mov     rdi, qword ptr [rbp+var_40+8]
0x1800168df  mov     rbx, qword ptr [rbp+var_50+8]
0x1800168e3  cmp     r8d, r10d
0x1800168e6  jz      loc_18001699C
0x1800168ec  cmp     ecx, r10d
0x1800168ef  jz      loc_18001699C
0x1800168f5  movq    xmm1, rbx
0x1800168fa  mov     rax, rbx
0x1800168fd  cmp     ecx, r9d
0x180016900  jz      short loc_18001690B
0x180016902  cmp     ecx, edx
0x180016904  jz      short loc_18001690B
0x180016906  cvttsd2si rax, xmm1
0x18001690b  test    rax, rax
0x18001690e  jnz     short loc_180016973
0x180016910  xorps   xmm0, xmm0
0x180016913  lea     rcx, ModuleName; "mpunits.dll"
0x18001691a  movups  [rbp+var_30], xmm0
0x18001691e  call    cs:__imp_GetModuleHandleA
0x180016924  mov     rcx, rax
0x180016927  mov     edx, 810h
0x18001692c  call    _Intlstr_GetString_LoadString
0x180016931  mov     qword ptr [rbp+var_30], rax
0x180016935  lea     r9, [rbp+var_30]
0x180016939  mov     byte ptr [rbp+var_30+8], 0
0x18001693d  lea     rdx, aMi; "MI"
0x180016944  movaps  xmm0, [rbp+var_30]
0x180016948  mov     r8d, 5
0x18001694e  mov     [rsp+80h+var_58], 0; __int64
0x180016957  movdqa  [rbp+var_30], xmm0
0x18001695c  mov     [rsp+80h+var_60], 0; __int64
0x180016965  lea     ecx, [r8-1]; int
0x180016969  call    MI_ReportErrorDetails_ForCustomError
0x18001696e  jmp     loc_180016809
0x180016973  cmp     r8d, edx
0x180016976  jnz     short loc_180016982
0x180016978  cmp     ecx, r9d
0x18001697b  jnz     short loc_180016982
0x18001697d  test    rbx, rbx
0x180016980  js      short loc_18001699C
0x180016982  cmp     ecx, edx
0x180016984  jnz     loc_180016A22
0x18001698a  cmp     r8d, r9d
0x18001698d  jnz     loc_180016A22
0x180016993  test    rdi, rdi
0x180016996  jns     loc_180016AE3
0x18001699c  mov     dword ptr [rsp+80h+var_60], ecx
0x1800169a0  lea     r9, [rbp+var_50]
0x1800169a4  lea     rcx, [rbp+var_20]
0x1800169a8  lea     rdx, [rbp+var_40]
0x1800169ac  call    remainder_numeric_real
0x1800169b1  movups  xmm6, xmmword ptr [rax]
0x1800169b4  cmp     byte ptr [rbp+var_40], 0Ch
0x1800169b8  jl      short loc_1800169EA
0x1800169ba  test    dword ptr [rbp+var_40], 100h
0x1800169c1  jnz     short loc_1800169EA
0x1800169c3  mov     eax, [rdi]
0x1800169c5  cmp     eax, 0FFFFFFFFh
0x1800169c8  jz      short loc_1800169EA
0x1800169ca  sub     eax, 1
0x1800169cd  mov     [rdi], eax
0x1800169cf  jnz     short loc_1800169E2
0x1800169d1  mov     rax, qword ptr [rbp+var_40+8]
0x1800169d5  lea     rcx, [rbp+var_40]
0x1800169d9  mov     rax, [rax+8]
0x1800169dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e2  mov     r14b, byte ptr [rbp+var_50]
0x1800169e6  mov     rbx, qword ptr [rbp+var_50+8]
0x1800169ea  cmp     r14b, 0Ch
0x1800169ee  jl      short loc_180016A18
0x1800169f0  test    dword ptr [rbp+var_50], 100h
0x1800169f7  jnz     short loc_180016A18
0x1800169f9  mov     eax, [rbx]
0x1800169fb  cmp     eax, 0FFFFFFFFh
0x1800169fe  jz      short loc_180016A18
0x180016a00  sub     eax, 1
0x180016a03  mov     [rbx], eax
0x180016a05  jnz     short loc_180016A18
0x180016a07  mov     rax, qword ptr [rbp+var_50+8]
0x180016a0b  lea     rcx, [rbp+var_50]
0x180016a0f  mov     rax, [rax+8]
0x180016a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a18  movdqu  xmmword ptr [r15], xmm6
0x180016a1d  jmp     loc_180016825
0x180016a22  cmp     r8d, edx
0x180016a25  jz      loc_180016AE3
0x180016a2b  cmp     ecx, edx
0x180016a2d  jz      short loc_180016AA8
0x180016a2f  cmp     r8d, r9d
0x180016a32  jnz     short loc_180016A39
0x180016a34  mov     rdx, rdi
0x180016a37  jmp     short loc_180016A43
0x180016a39  movq    xmm0, rdi
0x180016a3e  cvttsd2si rdx, xmm0
0x180016a43  cmp     ecx, r9d
0x180016a46  mov     r9, rbx
0x180016a49  jz      short loc_180016A50
0x180016a4b  cvttsd2si r9, xmm1
0x180016a50  mov     rax, 8000000000000000h
0x180016a5a  cmp     rdx, rax
0x180016a5d  jnz     short loc_180016A7E
0x180016a5f  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180016a63  jnz     short loc_180016A7E
0x180016a65  mov     qword ptr [rbp+var_30], 8
0x180016a6d  mov     qword ptr [rbp+var_30+8], 0
0x180016a75  movaps  xmm6, [rbp+var_30]
0x180016a79  jmp     loc_1800169B4
0x180016a7e  mov     rax, rdx
0x180016a81  mov     dword ptr [rsp+80h+var_58], ecx
0x180016a85  cqo
0x180016a87  lea     rcx, [rbp+var_20]
0x180016a8b  idiv    r9
0x180016a8e  lea     rax, [rbp+var_50]
0x180016a92  mov     r9d, r8d
0x180016a95  lea     r8, [rbp+var_40]
0x180016a99  mov     [rsp+80h+var_60], rax
0x180016a9e  call    fit_result_signed
0x180016aa3  jmp     loc_1800169B1
0x180016aa8  cmp     r8d, r9d
0x180016aab  jz      short loc_180016AE3
0x180016aad  movsd   xmm1, cs:__real@43e0000000000000
0x180016ab5  xor     ecx, ecx
0x180016ab7  movq    xmm0, rdi
0x180016abc  comisd  xmm0, xmm1
0x180016ac0  jb      short loc_180016AD9
0x180016ac2  subsd   xmm0, xmm1
0x180016ac6  comisd  xmm0, xmm1
0x180016aca  jnb     short loc_180016AD9
0x180016acc  mov     rax, 8000000000000000h
0x180016ad6  mov     rcx, rax
0x180016ad9  cvttsd2si r8, xmm0
0x180016ade  add     r8, rcx
0x180016ae1  jmp     short loc_180016AEF
0x180016ae3  mov     r8, rdi
0x180016ae6  cmp     ecx, r9d
0x180016ae9  jz      short loc_180016AEF
0x180016aeb  cmp     ecx, edx
0x180016aed  jnz     short loc_180016AF4
0x180016aef  mov     rcx, rbx
0x180016af2  jmp     short loc_180016B23
0x180016af4  movsd   xmm0, cs:__real@43e0000000000000
0x180016afc  xor     edx, edx
0x180016afe  comisd  xmm1, xmm0
0x180016b02  jb      short loc_180016B1B
0x180016b04  subsd   xmm1, xmm0
0x180016b08  comisd  xmm1, xmm0
0x180016b0c  jnb     short loc_180016B1B
0x180016b0e  mov     rax, 8000000000000000h
0x180016b18  mov     rdx, rax
0x180016b1b  cvttsd2si rcx, xmm1
0x180016b20  add     rcx, rdx
0x180016b23  mov     rax, r8
  ... truncated ...
```
