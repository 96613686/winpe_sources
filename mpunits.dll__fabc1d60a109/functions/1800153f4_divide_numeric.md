# divide_numeric

- ea: `0x1800153f4`
- end: `0x18001575d`
- name: `divide_numeric`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180014950`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000be30`
- `0x1800153f4`
- `0x180015764`
- `0x18001588c`
- `0x18001594c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180015583`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180015583`

## string_xrefs

- `0x180015578`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall divide_numeric(__int64 a1, __int128 *a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __m128i v6; // xmm0
  char v7; // di
  int v8; // ecx
  int v9; // r8d
  int v10; // ecx
  int v11; // eax
  int *v12; // rsi
  int *v13; // rbx
  __int64 v14; // rcx
  HMODULE ModuleHandleA; // rax
  int v16; // eax
  int v17; // eax
  __int128 *v19; // rax
  __int128 v20; // xmm6
  int v21; // eax
  int v22; // eax
  __m128i v23; // [rsp+30h] [rbp-50h] BYREF
  __m128i v24; // [rsp+40h] [rbp-40h] BYREF
  __int128 v25; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v26[16]; // [rsp+60h] [rbp-20h] BYREF

  v3 = *a2;
  v24 = (__m128i)0x10FuLL;
  v23 = (__m128i)0x10FuLL;
  v25 = v3;
  v24 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v26, MintValue_CoerceToNumber, &v25, 10);
  if ( (unsigned __int8)_mm_cvtsi128_si32(v24) == 0xFE )
    goto LABEL_46;
  v25 = *a3;
  v6 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v26, MintValue_CoerceToNumber, &v25, 10);
  v7 = _mm_cvtsi128_si32(v6);
  v23 = v6;
  if ( v7 == -2 )
  {
LABEL_41:
    if ( v24.m128i_i8[0] < 12 || (v24.m128i_i16[0] & 0x100) != 0 || *(_DWORD *)v24.m128i_i64[1] == -1 )
      goto LABEL_47;
    v16 = *(_DWORD *)v24.m128i_i64[1] - 1;
    *(_DWORD *)v24.m128i_i64[1] = v16;
    if ( !v16 )
      (*(void (__fastcall **)(__m128i *))(v24.m128i_i64[1] + 8))(&v24);
LABEL_46:
    v7 = v23.m128i_i8[0];
LABEL_47:
    if ( v7 >= 12 && (v23.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v23.m128i_i64[1] != -1 )
    {
      v17 = *(_DWORD *)v23.m128i_i64[1] - 1;
      *(_DWORD *)v23.m128i_i64[1] = v17;
      if ( !v17 )
        (*(void (__fastcall **)(__m128i *))(v23.m128i_i64[1] + 8))(&v23);
    }
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  if ( v24.m128i_i8[0] > 6 )
  {
    if ( v24.m128i_i8[0] != 7 )
    {
      if ( v24.m128i_i8[0] == 8 )
        goto LABEL_9;
      if ( v24.m128i_i8[0] == 9 || (v8 = v24.m128i_i8[0] - 10, v24.m128i_i8[0] == 10) )
      {
        v9 = 3;
        goto LABEL_18;
      }
      goto LABEL_14;
    }
  }
  else
  {
    switch ( v24.m128i_i8[0] )
    {
      case 6:
        goto LABEL_9;
      case 1:
        goto LABEL_17;
      case 2:
LABEL_9:
        v9 = 1;
        goto LABEL_18;
    }
    if ( v24.m128i_i8[0] != 3 )
    {
      v8 = v24.m128i_i8[0] - 4;
      if ( v24.m128i_i8[0] == 4 )
        goto LABEL_9;
LABEL_14:
      if ( v8 != 1 )
      {
        v9 = 0;
        goto LABEL_18;
      }
    }
  }
LABEL_17:
  v9 = 2;
LABEL_18:
  if ( v7 > 6 )
  {
    if ( v7 != 7 )
    {
      if ( v7 == 8 )
        goto LABEL_24;
      if ( v7 == 9 || (v10 = v7 - 10, v7 == 10) )
      {
        v11 = 3;
        goto LABEL_33;
      }
      goto LABEL_29;
    }
  }
  else
  {
    switch ( v7 )
    {
      case 6:
        goto LABEL_24;
      case 1:
        goto LABEL_32;
      case 2:
LABEL_24:
        v11 = 1;
        goto LABEL_33;
    }
    if ( v7 != 3 )
    {
      v10 = v7 - 4;
      if ( v7 == 4 )
        goto LABEL_24;
LABEL_29:
      if ( v10 != 1 )
      {
        v11 = 0;
        goto LABEL_33;
      }
    }
  }
LABEL_32:
  v11 = 2;
LABEL_33:
  v12 = (int *)v24.m128i_i64[1];
  v13 = (int *)v23.m128i_i64[1];
  if ( v9 == 3 || v11 == 3 )
    goto LABEL_60;
  if ( v11 == 1 || v11 == 2 )
    v14 = v23.m128i_i64[1];
  else
    v14 = (unsigned int)(int)*(double *)&v23.m128i_i64[1];
  if ( !v14 )
  {
    v25 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v25 = Intlstr_GetString_LoadString(ModuleHandleA, 2064);
    BYTE8(v25) = 0;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    v7 = v23.m128i_i8[0];
    goto LABEL_41;
  }
  if ( v9 == 2 && v11 == 1 && v23.m128i_i64[1] < 0 )
    goto LABEL_60;
  if ( v11 == 2 && v9 == 1 )
  {
    if ( v24.m128i_i64[1] < 0 )
    {
LABEL_60:
      v19 = (__int128 *)divide_numeric_real((unsigned int)v26, (unsigned int)&v24, v9, (unsigned int)&v23, v11);
      goto LABEL_61;
    }
  }
  else if ( v9 != 2 && v11 != 2 )
  {
    v19 = (__int128 *)divide_numeric_signed((unsigned int)v26, (unsigned int)&v24, v9, (unsigned int)&v23, v11);
    goto LABEL_61;
  }
  v19 = (__int128 *)divide_numeric_positive_integers((unsigned int)v26, (unsigned int)&v24, v9, (unsigned int)&v23, v11);
LABEL_61:
  v20 = *v19;
  if ( v24.m128i_i8[0] >= 12 && (v24.m128i_i16[0] & 0x100) == 0 && *v12 != -1 )
  {
    v21 = *v12 - 1;
    *v12 = v21;
    if ( !v21 )
      (*(void (__fastcall **)(__m128i *))(v24.m128i_i64[1] + 8))(&v24);
    v7 = v23.m128i_i8[0];
    v13 = (int *)v23.m128i_i64[1];
  }
  if ( v7 >= 12 && (v23.m128i_i16[0] & 0x100) == 0 && *v13 != -1 )
  {
    v22 = *v13 - 1;
    *v13 = v22;
    if ( !v22 )
      (*(void (__fastcall **)(__m128i *))(v23.m128i_i64[1] + 8))(&v23);
  }
  *(_OWORD *)a1 = v20;
  return a1;
}

```

## disassembly

```asm
0x1800153f4  push    rbp
0x1800153f6  push    rbx
0x1800153f7  push    rsi
0x1800153f8  push    rdi
0x1800153f9  push    r14
0x1800153fb  mov     rbp, rsp
0x1800153fe  sub     rsp, 80h
0x180015405  movups  xmm0, xmmword ptr [rdx]
0x180015408  mov     rbx, r8
0x18001540b  mov     r14, rcx
0x18001540e  lea     r8, [rbp+var_30]
0x180015412  movaps  [rsp+80h+var_10], xmm6
0x180015417  mov     edi, 0Ah
0x18001541c  mov     qword ptr [rbp+var_40], 10Fh
0x180015424  mov     r9d, edi
0x180015427  mov     qword ptr [rbp+var_40+8], 0
0x18001542f  lea     rdx, MintValue_CoerceToNumber
0x180015436  mov     qword ptr [rbp+var_50], 10Fh
0x18001543e  lea     rcx, [rbp+var_20]
0x180015442  mov     qword ptr [rbp+var_50+8], 0
0x18001544a  movdqu  [rbp+var_30], xmm0
0x18001544f  call    MintValue_CoerceAndRaiseInvalidCastException
0x180015454  movups  xmm0, xmmword ptr [rax]
0x180015457  movd    eax, xmm0
0x18001545b  movups  [rbp+var_40], xmm0
0x18001545f  cmp     al, 0FEh
0x180015461  jz      loc_180015609
0x180015467  movups  xmm0, xmmword ptr [rbx]
0x18001546a  mov     r9d, edi
0x18001546d  lea     r8, [rbp+var_30]
0x180015471  lea     rdx, MintValue_CoerceToNumber
0x180015478  lea     rcx, [rbp+var_20]
0x18001547c  movdqu  [rbp+var_30], xmm0
0x180015481  call    MintValue_CoerceAndRaiseInvalidCastException
0x180015486  movups  xmm0, xmmword ptr [rax]
0x180015489  movd    edi, xmm0
0x18001548d  movups  [rbp+var_50], xmm0
0x180015491  cmp     dil, 0FEh
0x180015495  jz      loc_1800155D7
0x18001549b  movsx   ecx, byte ptr [rbp+var_40]
0x18001549f  mov     edx, 2
0x1800154a4  lea     r10d, [rdx+1]
0x1800154a8  lea     r9d, [rdx-1]
0x1800154ac  cmp     ecx, 6
0x1800154af  jg      short loc_1800154CC
0x1800154b1  jz      short loc_1800154C7
0x1800154b3  sub     ecx, r9d
0x1800154b6  jz      short loc_1800154EF
0x1800154b8  sub     ecx, r9d
0x1800154bb  jz      short loc_1800154C7
0x1800154bd  sub     ecx, r9d
0x1800154c0  jz      short loc_1800154EF
0x1800154c2  sub     ecx, r9d
0x1800154c5  jnz     short loc_1800154E0
0x1800154c7  mov     r8d, r9d
0x1800154ca  jmp     short loc_1800154F2
0x1800154cc  sub     ecx, 7
0x1800154cf  jz      short loc_1800154EF
0x1800154d1  sub     ecx, r9d
0x1800154d4  jz      short loc_1800154C7
0x1800154d6  sub     ecx, r9d
0x1800154d9  jz      short loc_1800154EA
0x1800154db  sub     ecx, r9d
0x1800154de  jz      short loc_1800154EA
0x1800154e0  cmp     ecx, r9d
0x1800154e3  jz      short loc_1800154EF
0x1800154e5  xor     r8d, r8d
0x1800154e8  jmp     short loc_1800154F2
0x1800154ea  mov     r8d, r10d
0x1800154ed  jmp     short loc_1800154F2
0x1800154ef  mov     r8d, edx
0x1800154f2  movsx   ecx, dil
0x1800154f6  cmp     ecx, 6
0x1800154f9  jg      short loc_180015516
0x1800154fb  jz      short loc_180015511
0x1800154fd  sub     ecx, r9d
0x180015500  jz      short loc_180015538
0x180015502  sub     ecx, r9d
0x180015505  jz      short loc_180015511
0x180015507  sub     ecx, r9d
0x18001550a  jz      short loc_180015538
0x18001550c  sub     ecx, r9d
0x18001550f  jnz     short loc_18001552A
0x180015511  mov     eax, r9d
0x180015514  jmp     short loc_18001553A
0x180015516  sub     ecx, 7
0x180015519  jz      short loc_180015538
0x18001551b  sub     ecx, r9d
0x18001551e  jz      short loc_180015511
0x180015520  sub     ecx, r9d
0x180015523  jz      short loc_180015533
0x180015525  sub     ecx, r9d
0x180015528  jz      short loc_180015533
0x18001552a  cmp     ecx, r9d
0x18001552d  jz      short loc_180015538
0x18001552f  xor     eax, eax
0x180015531  jmp     short loc_18001553A
0x180015533  mov     eax, r10d
0x180015536  jmp     short loc_18001553A
0x180015538  mov     eax, edx
0x18001553a  mov     rsi, qword ptr [rbp+var_40+8]
0x18001553e  mov     rbx, qword ptr [rbp+var_50+8]
0x180015542  cmp     r8d, r10d
0x180015545  jz      loc_18001569A
0x18001554b  cmp     eax, r10d
0x18001554e  jz      loc_18001569A
0x180015554  cmp     eax, r9d
0x180015557  jz      short loc_18001555D
0x180015559  cmp     eax, edx
0x18001555b  jnz     short loc_180015562
0x18001555d  mov     rcx, rbx
0x180015560  jmp     short loc_18001556C
0x180015562  movq    xmm0, rbx
0x180015567  cvttsd2si rcx, xmm0
0x18001556c  test    rcx, rcx
0x18001556f  jnz     loc_180015671
0x180015575  xorps   xmm0, xmm0
0x180015578  lea     rcx, ModuleName; "mpunits.dll"
0x18001557f  movups  [rbp+var_30], xmm0
0x180015583  call    cs:__imp_GetModuleHandleA
0x180015589  mov     rcx, rax
0x18001558c  mov     edx, 810h
0x180015591  call    _Intlstr_GetString_LoadString
0x180015596  mov     qword ptr [rbp+var_30], rax
0x18001559a  lea     r9, [rbp+var_30]
0x18001559e  mov     byte ptr [rbp+var_30+8], 0
0x1800155a2  lea     rdx, aMi; "MI"
0x1800155a9  movaps  xmm0, [rbp+var_30]
0x1800155ad  mov     r8d, 5
0x1800155b3  mov     [rsp+80h+var_58], 0; __int64
0x1800155bc  movdqa  [rbp+var_30], xmm0
0x1800155c1  mov     [rsp+80h+var_60], 0; __int64
0x1800155ca  lea     ecx, [r8-1]; int
0x1800155ce  call    MI_ReportErrorDetails_ForCustomError
0x1800155d3  mov     dil, byte ptr [rbp+var_50]
0x1800155d7  cmp     byte ptr [rbp+var_40], 0Ch
0x1800155db  jl      short loc_18001560D
0x1800155dd  test    dword ptr [rbp+var_40], 100h
0x1800155e4  jnz     short loc_18001560D
0x1800155e6  mov     rcx, qword ptr [rbp+var_40+8]
0x1800155ea  mov     eax, [rcx]
0x1800155ec  cmp     eax, 0FFFFFFFFh
0x1800155ef  jz      short loc_18001560D
0x1800155f1  sub     eax, 1
0x1800155f4  mov     [rcx], eax
0x1800155f6  jnz     short loc_180015609
0x1800155f8  mov     rax, qword ptr [rbp+var_40+8]
0x1800155fc  lea     rcx, [rbp+var_40]
0x180015600  mov     rax, [rax+8]
0x180015604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015609  mov     dil, byte ptr [rbp+var_50]
0x18001560d  cmp     dil, 0Ch
0x180015611  jl      short loc_18001563F
0x180015613  test    dword ptr [rbp+var_50], 100h
0x18001561a  jnz     short loc_18001563F
0x18001561c  mov     rcx, qword ptr [rbp+var_50+8]
0x180015620  mov     eax, [rcx]
0x180015622  cmp     eax, 0FFFFFFFFh
0x180015625  jz      short loc_18001563F
0x180015627  sub     eax, 1
0x18001562a  mov     [rcx], eax
0x18001562c  jnz     short loc_18001563F
0x18001562e  mov     rax, qword ptr [rbp+var_50+8]
0x180015632  lea     rcx, [rbp+var_50]
0x180015636  mov     rax, [rax+8]
0x18001563a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001563f  xor     edx, edx
0x180015641  xor     ecx, ecx
0x180015643  mov     eax, 0FFh
0x180015648  mov     [r14+4], edx
0x18001564c  and     eax, 0FFFFFFFEh
0x18001564f  mov     [r14+8], rcx
0x180015653  or      eax, 0FEh
0x180015658  mov     [r14], eax
0x18001565b  movaps  xmm6, [rsp+80h+var_10]
0x180015660  mov     rax, r14
0x180015663  add     rsp, 80h
0x18001566a  pop     r14
0x18001566c  pop     rdi
0x18001566d  pop     rsi
0x18001566e  pop     rbx
0x18001566f  pop     rbp
0x180015670  retn
0x180015671  cmp     r8d, edx
0x180015674  jnz     short loc_180015680
0x180015676  cmp     eax, r9d
0x180015679  jnz     short loc_180015680
0x18001567b  test    rbx, rbx
0x18001567e  js      short loc_18001569A
0x180015680  cmp     eax, edx
0x180015682  jnz     loc_180015720
0x180015688  cmp     r8d, r9d
0x18001568b  jnz     loc_180015720
0x180015691  test    rsi, rsi
0x180015694  jns     loc_180015743
0x18001569a  lea     r9, [rbp+var_50]
0x18001569e  mov     dword ptr [rsp+80h+var_60], eax
0x1800156a2  lea     rdx, [rbp+var_40]
0x1800156a6  lea     rcx, [rbp+var_20]
0x1800156aa  call    divide_numeric_real
0x1800156af  cmp     byte ptr [rbp+var_40], 0Ch
0x1800156b3  movups  xmm6, xmmword ptr [rax]
0x1800156b6  jl      short loc_1800156E8
0x1800156b8  test    dword ptr [rbp+var_40], 100h
0x1800156bf  jnz     short loc_1800156E8
0x1800156c1  mov     eax, [rsi]
0x1800156c3  cmp     eax, 0FFFFFFFFh
0x1800156c6  jz      short loc_1800156E8
0x1800156c8  sub     eax, 1
0x1800156cb  mov     [rsi], eax
0x1800156cd  jnz     short loc_1800156E0
0x1800156cf  mov     rax, qword ptr [rbp+var_40+8]
0x1800156d3  lea     rcx, [rbp+var_40]
0x1800156d7  mov     rax, [rax+8]
0x1800156db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e0  mov     dil, byte ptr [rbp+var_50]
0x1800156e4  mov     rbx, qword ptr [rbp+var_50+8]
0x1800156e8  cmp     dil, 0Ch
0x1800156ec  jl      short loc_180015716
0x1800156ee  test    dword ptr [rbp+var_50], 100h
0x1800156f5  jnz     short loc_180015716
0x1800156f7  mov     eax, [rbx]
0x1800156f9  cmp     eax, 0FFFFFFFFh
0x1800156fc  jz      short loc_180015716
0x1800156fe  sub     eax, 1
0x180015701  mov     [rbx], eax
0x180015703  jnz     short loc_180015716
0x180015705  mov     rax, qword ptr [rbp+var_50+8]
0x180015709  lea     rcx, [rbp+var_50]
0x18001570d  mov     rax, [rax+8]
0x180015711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015716  movdqu  xmmword ptr [r14], xmm6
0x18001571b  jmp     loc_18001565B
0x180015720  cmp     r8d, edx
0x180015723  jz      short loc_180015743
0x180015725  cmp     eax, edx
0x180015727  jz      short loc_180015743
0x180015729  lea     r9, [rbp+var_50]
0x18001572d  mov     dword ptr [rsp+80h+var_60], eax
0x180015731  lea     rdx, [rbp+var_40]
0x180015735  lea     rcx, [rbp+var_20]
0x180015739  call    divide_numeric_signed
0x18001573e  jmp     loc_1800156AF
0x180015743  lea     r9, [rbp+var_50]
0x180015747  mov     dword ptr [rsp+80h+var_60], eax
0x18001574b  lea     rdx, [rbp+var_40]
0x18001574f  lea     rcx, [rbp+var_20]
0x180015753  call    divide_numeric_positive_integers
0x180015758  jmp     loc_1800156AF
```
