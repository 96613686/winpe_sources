# divide_interval

- ea: `0x18001514c`
- end: `0x1800153eb`
- name: `divide_interval`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014950`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000be30`
- `0x180010190`
- `0x18001514c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180015263`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800152ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180015263`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800152ce`

## string_xrefs

- `0x180015258`: `mpunits.dll`
- `0x1800152c3`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall divide_interval(__int64 a1, __int64 a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __m128d v5; // xmm0
  char v6; // al
  int v7; // ecx
  __int64 v8; // rcx
  double v9; // xmm0_8
  HMODULE ModuleHandleA; // rax
  __int64 v11; // rdx
  __int64 IntervalFromMicroseconds_Real; // rax
  char v13; // di
  __int64 v14; // xmm6_8
  int v15; // esi
  __int16 v16; // r14
  char v17; // r15
  int v18; // eax
  int v20; // eax
  __m128d v21; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-28h] BYREF

  v3 = *a3;
  v21 = (__m128d)0x10FuLL;
  v22 = v3;
  v5 = *(__m128d *)MintValue_CoerceAndRaiseInvalidCastException(v23, MintValue_CoerceToNumber, &v22, 10);
  v6 = _mm_cvtsi128_si32((__m128i)v5);
  v21 = v5;
  if ( v6 == -2 )
  {
LABEL_31:
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  if ( v6 <= 6 )
  {
    if ( v6 != 6 && (v6 == 1 || v6 != 2 && v6 != 4) )
    {
      if ( v6 == 1 )
        goto LABEL_10;
      if ( v6 == 2 )
      {
LABEL_17:
        *(_QWORD *)&v9 = *(_OWORD *)&_mm_unpackhi_pd(v5, v5);
        goto LABEL_20;
      }
      v7 = v6 - 3;
      if ( v6 == 3 )
        goto LABEL_10;
      goto LABEL_16;
    }
LABEL_18:
    v9 = (double)_mm_srli_si128((__m128i)v5, 8).m128i_i32[0];
    goto LABEL_20;
  }
  if ( v6 == 8 )
    goto LABEL_18;
  if ( v6 == 7 )
    goto LABEL_10;
  if ( v6 == 8 )
    goto LABEL_17;
  v7 = v6 - 9;
  if ( v6 == 9 )
    goto LABEL_17;
LABEL_16:
  if ( v7 != 2 )
    goto LABEL_17;
LABEL_10:
  v8 = _mm_srli_si128((__m128i)v5, 8).m128i_u64[0];
  if ( v8 < 0 )
    v9 = (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1)) + (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1));
  else
    v9 = (double)(int)v8;
LABEL_20:
  if ( v9 < 0.0 )
  {
    v22 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v11 = 2065;
LABEL_22:
    *(_QWORD *)&v22 = Intlstr_GetString_LoadString(ModuleHandleA, v11);
    BYTE8(v22) = 0;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
LABEL_26:
    if ( SLOBYTE(v21.m128d_f64[0]) >= 12
      && (LOWORD(v21.m128d_f64[0]) & 0x100) == 0
      && **(_DWORD **)&v21.m128d_f64[1] != -1 )
    {
      v18 = **(_DWORD **)&v21.m128d_f64[1] - 1;
      **(_DWORD **)&v21.m128d_f64[1] = v18;
      if ( !v18 )
        (*(void (__fastcall **)(__m128d *))(*(_QWORD *)&v21.m128d_f64[1] + 8LL))(&v21);
    }
    goto LABEL_31;
  }
  if ( v9 == 0.0 )
  {
    v22 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v11 = 2064;
    goto LABEL_22;
  }
  IntervalFromMicroseconds_Real = MintValue_CreateIntervalFromMicroseconds_Real(v23);
  v13 = *(_BYTE *)IntervalFromMicroseconds_Real;
  v14 = *(_QWORD *)(IntervalFromMicroseconds_Real + 1);
  v15 = *(_DWORD *)(IntervalFromMicroseconds_Real + 9);
  v16 = *(_WORD *)(IntervalFromMicroseconds_Real + 13);
  v17 = *(_BYTE *)(IntervalFromMicroseconds_Real + 15);
  if ( *(_BYTE *)IntervalFromMicroseconds_Real == 0xFE )
    goto LABEL_26;
  if ( SLOBYTE(v21.m128d_f64[0]) >= 12
    && (LOWORD(v21.m128d_f64[0]) & 0x100) == 0
    && **(_DWORD **)&v21.m128d_f64[1] != -1 )
  {
    v20 = **(_DWORD **)&v21.m128d_f64[1] - 1;
    **(_DWORD **)&v21.m128d_f64[1] = v20;
    if ( !v20 )
      (*(void (__fastcall **)(__m128d *))(*(_QWORD *)&v21.m128d_f64[1] + 8LL))(&v21);
  }
  *(_QWORD *)(a1 + 1) = v14;
  *(_DWORD *)(a1 + 9) = v15;
  *(_WORD *)(a1 + 13) = v16;
  *(_BYTE *)(a1 + 15) = v17;
  *(_BYTE *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x18001514c  push    rbp
0x18001514e  push    rbx
0x18001514f  push    rsi
0x180015150  push    rdi
0x180015151  push    r14
0x180015153  push    r15
0x180015155  mov     rbp, rsp
0x180015158  sub     rsp, 78h
0x18001515c  movups  xmm0, xmmword ptr [r8]
0x180015160  mov     rdi, rdx
0x180015163  mov     rbx, rcx
0x180015166  lea     r8, [rbp+var_38]
0x18001516a  movaps  [rsp+78h+var_18], xmm6
0x18001516f  mov     r9d, 0Ah
0x180015175  mov     qword ptr [rbp+var_48], 10Fh
0x18001517d  lea     rdx, MintValue_CoerceToNumber
0x180015184  mov     qword ptr [rbp+var_48+8], 0
0x18001518c  lea     rcx, [rbp+var_28]
0x180015190  movdqu  [rbp+var_38], xmm0
0x180015195  call    MintValue_CoerceAndRaiseInvalidCastException
0x18001519a  movups  xmm0, xmmword ptr [rax]
0x18001519d  movd    eax, xmm0
0x1800151a1  movups  [rbp+var_48], xmm0
0x1800151a5  cmp     al, 0FEh
0x1800151a7  jz      loc_180015374
0x1800151ad  movsx   ecx, al
0x1800151b0  cmp     ecx, 6
0x1800151b3  jg      short loc_1800151F5
0x1800151b5  jz      short loc_180015223
0x1800151b7  mov     edx, ecx
0x1800151b9  sub     edx, 1
0x1800151bc  jz      short loc_1800151CD
0x1800151be  sub     edx, 1
0x1800151c1  jz      short loc_180015223
0x1800151c3  sub     edx, 1
0x1800151c6  jz      short loc_1800151CD
0x1800151c8  cmp     edx, 1
0x1800151cb  jz      short loc_180015223
0x1800151cd  sub     ecx, 1
0x1800151d0  jz      short loc_1800151DC
0x1800151d2  sub     ecx, 1
0x1800151d5  jz      short loc_18001521D
0x1800151d7  sub     ecx, 1
0x1800151da  jnz     short loc_180015213
0x1800151dc  psrldq  xmm0, 8
0x1800151e1  movq    rcx, xmm0
0x1800151e6  xorps   xmm0, xmm0
0x1800151e9  test    rcx, rcx
0x1800151ec  js      short loc_180015237
0x1800151ee  cvtsi2sd xmm0, rcx
0x1800151f3  jmp     short loc_18001524C
0x1800151f5  mov     edx, ecx
0x1800151f7  sub     edx, 7
0x1800151fa  jz      short loc_180015204
0x1800151fc  sub     edx, 1
0x1800151ff  jz      short loc_180015223
0x180015201  sub     edx, 1
0x180015204  sub     ecx, 7
0x180015207  jz      short loc_1800151DC
0x180015209  sub     ecx, 1
0x18001520c  jz      short loc_18001521D
0x18001520e  sub     ecx, 1
0x180015211  jz      short loc_18001521D
0x180015213  sub     ecx, 1
0x180015216  jz      short loc_18001521D
0x180015218  cmp     ecx, 1
0x18001521b  jz      short loc_1800151DC
0x18001521d  unpckhpd xmm0, xmm0
0x180015221  jmp     short loc_18001524C
0x180015223  psrldq  xmm0, 8
0x180015228  movq    rax, xmm0
0x18001522d  xorps   xmm0, xmm0
0x180015230  cvtsi2sd xmm0, rax
0x180015235  jmp     short loc_18001524C
0x180015237  mov     rax, rcx
0x18001523a  and     ecx, 1
0x18001523d  shr     rax, 1
0x180015240  or      rax, rcx
0x180015243  cvtsi2sd xmm0, rax
0x180015248  addsd   xmm0, xmm0
0x18001524c  xorps   xmm1, xmm1
0x18001524f  comisd  xmm1, xmm0
0x180015253  jbe     short loc_1800152B8
0x180015255  xorps   xmm0, xmm0
0x180015258  lea     rcx, ModuleName; "mpunits.dll"
0x18001525f  movups  [rbp+var_38], xmm0
0x180015263  call    cs:__imp_GetModuleHandleA
0x180015269  mov     edx, 811h
0x18001526e  mov     rcx, rax
0x180015271  call    _Intlstr_GetString_LoadString
0x180015276  mov     qword ptr [rbp+var_38], rax
0x18001527a  lea     r9, [rbp+var_38]
0x18001527e  mov     byte ptr [rbp+var_38+8], 0
0x180015282  lea     rdx, aMi; "MI"
0x180015289  movaps  xmm0, [rbp+var_38]
0x18001528d  mov     r8d, 5
0x180015293  mov     [rsp+78h+var_50], 0; __int64
0x18001529c  movdqa  [rbp+var_38], xmm0
0x1800152a1  mov     [rsp+78h+var_58], 0; __int64
0x1800152aa  lea     ecx, [r8-1]; int
0x1800152ae  call    MI_ReportErrorDetails_ForCustomError
0x1800152b3  jmp     loc_180015342
0x1800152b8  ucomisd xmm0, xmm1
0x1800152bc  jp      short loc_1800152DB
0x1800152be  jnz     short loc_1800152DB
0x1800152c0  xorps   xmm0, xmm0
0x1800152c3  lea     rcx, ModuleName; "mpunits.dll"
0x1800152ca  movups  [rbp+var_38], xmm0
0x1800152ce  call    cs:__imp_GetModuleHandleA
0x1800152d4  mov     edx, 810h
0x1800152d9  jmp     short loc_18001526E
0x1800152db  mov     r8, [rdi+8]
0x1800152df  xorps   xmm1, xmm1
0x1800152e2  mov     eax, [r8+14h]
0x1800152e6  mov     edx, [r8+18h]
0x1800152ea  lea     rcx, [rax+rax*2]
0x1800152ee  lea     rax, [rdx+rcx*8]
0x1800152f2  imul    rcx, rax, 3Ch ; '<'
0x1800152f6  mov     eax, [r8+1Ch]
0x1800152fa  add     rcx, rax
0x1800152fd  mov     eax, [r8+20h]
0x180015301  imul    rdx, rcx, 3Ch ; '<'
0x180015305  add     rdx, rax
0x180015308  mov     eax, [r8+24h]
0x18001530c  imul    rcx, rdx, 0F4240h
0x180015313  add     rcx, rax
0x180015316  cvtsi2sd xmm1, rcx
0x18001531b  lea     rcx, [rbp+var_28]
0x18001531f  divsd   xmm1, xmm0
0x180015323  call    MintValue_CreateIntervalFromMicroseconds_Real
0x180015328  mov     dil, [rax]
0x18001532b  movsd   xmm6, qword ptr [rax+1]
0x180015330  mov     esi, [rax+9]
0x180015333  movzx   r14d, word ptr [rax+0Dh]
0x180015338  mov     r15b, [rax+0Fh]
0x18001533c  cmp     dil, 0FEh
0x180015340  jnz     short loc_1800153A3
0x180015342  cmp     byte ptr [rbp+var_48], 0Ch
0x180015346  jl      short loc_180015374
0x180015348  test    dword ptr [rbp+var_48], 100h
0x18001534f  jnz     short loc_180015374
0x180015351  mov     rcx, qword ptr [rbp+var_48+8]
0x180015355  mov     eax, [rcx]
0x180015357  cmp     eax, 0FFFFFFFFh
0x18001535a  jz      short loc_180015374
0x18001535c  sub     eax, 1
0x18001535f  mov     [rcx], eax
0x180015361  jnz     short loc_180015374
0x180015363  mov     rax, qword ptr [rbp+var_48+8]
0x180015367  lea     rcx, [rbp+var_48]
0x18001536b  mov     rax, [rax+8]
0x18001536f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015374  xor     edx, edx
0x180015376  xor     ecx, ecx
0x180015378  mov     eax, 0FFh
0x18001537d  mov     [rbx+4], edx
0x180015380  and     eax, 0FFFFFFFEh
0x180015383  mov     [rbx+8], rcx
0x180015387  or      eax, 0FEh
0x18001538c  mov     [rbx], eax
0x18001538e  movaps  xmm6, [rsp+78h+var_18]
0x180015393  mov     rax, rbx
0x180015396  add     rsp, 78h
0x18001539a  pop     r15
0x18001539c  pop     r14
0x18001539e  pop     rdi
0x18001539f  pop     rsi
0x1800153a0  pop     rbx
0x1800153a1  pop     rbp
0x1800153a2  retn
0x1800153a3  cmp     byte ptr [rbp+var_48], 0Ch
0x1800153a7  jl      short loc_1800153D5
0x1800153a9  test    dword ptr [rbp+var_48], 100h
0x1800153b0  jnz     short loc_1800153D5
0x1800153b2  mov     rcx, qword ptr [rbp+var_48+8]
0x1800153b6  mov     eax, [rcx]
0x1800153b8  cmp     eax, 0FFFFFFFFh
0x1800153bb  jz      short loc_1800153D5
0x1800153bd  sub     eax, 1
0x1800153c0  mov     [rcx], eax
0x1800153c2  jnz     short loc_1800153D5
0x1800153c4  mov     rax, qword ptr [rbp+var_48+8]
0x1800153c8  lea     rcx, [rbp+var_48]
0x1800153cc  mov     rax, [rax+8]
0x1800153d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d5  movsd   qword ptr [rbx+1], xmm6
0x1800153da  mov     [rbx+9], esi
0x1800153dd  mov     [rbx+0Dh], r14w
0x1800153e2  mov     [rbx+0Fh], r15b
0x1800153e6  mov     [rbx], dil
0x1800153e9  jmp     short loc_18001538E
```
