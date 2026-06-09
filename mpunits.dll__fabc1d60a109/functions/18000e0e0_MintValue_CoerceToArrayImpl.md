# MintValue_CoerceToArrayImpl

- ea: `0x18000e0e0`
- end: `0x18000e423`
- name: `MintValue_CoerceToArrayImpl`
- size: `835`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000db80`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000db80`
- `0x18000e0e0`
- `0x18000f830`
- `0x18000f870`
- `0x180010570`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e2b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e2b0`

## string_xrefs

- `0x18000e2a5`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CoerceToArrayImpl(__int64 a1, __m128i *a2, unsigned int a3)
{
  bool v3; // zf
  unsigned int v7; // r14d
  unsigned int v8; // r12d
  __m128i v9; // xmm0
  unsigned int v10; // edi
  __m128i *ArrayElement; // rax
  char v12; // cl
  int v13; // eax
  int v14; // r15d
  int v15; // ecx
  HMODULE ModuleHandleA; // rax
  int appended; // edi
  int v18; // ecx
  int v19; // eax
  __m128i v21; // [rsp+30h] [rbp-39h] BYREF
  __m128i v22; // [rsp+40h] [rbp-29h] BYREF
  __m128i v23; // [rsp+50h] [rbp-19h] BYREF
  __m128i v24; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v25[16]; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v26[64]; // [rsp+80h] [rbp+17h] BYREF

  v3 = a2->m128i_i8[0] == -1;
  v21 = (__m128i)0x10FuLL;
  if ( v3 || (a2->m128i_i32[0] & 0x100) != 0 )
  {
    *(_OWORD *)a1 = 0x100 | (unsigned __int128)(unsigned __int8)a3;
    return a1;
  }
  v7 = a3 & 0xFFFFFFEF;
  if ( (a2->m128i_i8[0] & 0xF0) != 0x10 )
  {
    v3 = a2->m128i_i8[0] == 15;
    v22 = (__m128i)0x10FuLL;
    if ( v3 && ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(a2->m128i_i64[1] + 24)) )
    {
      v23 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v23.m128i_i64[0] = Intlstr_GetString_LoadString(ModuleHandleA, 2067);
      v23.m128i_i8[8] = 0;
      v24 = v23;
      MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
    }
    else
    {
      v21 = *(__m128i *)MintValue_CreateEmptyArray(v26, a3);
      if ( (unsigned __int8)_mm_cvtsi128_si32(v21) == 0xFE )
        goto LABEL_39;
      v24 = *a2;
      v22 = *(__m128i *)MintValue_Coerce(v26, &v24, v7);
      if ( (unsigned __int8)_mm_cvtsi128_si32(v22) != 0xFE )
      {
        appended = MintValue_AppendArrayElement(&v21, &v22);
        if ( v22.m128i_i8[0] >= 12 && (v22.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v22.m128i_i64[1] != -1 )
        {
          v18 = *(_DWORD *)v22.m128i_i64[1] - 1;
          *(_DWORD *)v22.m128i_i64[1] = v18;
          if ( !v18 )
            (*(void (__fastcall **)(__m128i *))(v22.m128i_i64[1] + 8))(&v22);
        }
        if ( !appended )
        {
LABEL_32:
          v9 = v21;
          goto LABEL_33;
        }
      }
    }
LABEL_34:
    if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
    {
      v19 = *(_DWORD *)v21.m128i_i64[1] - 1;
      *(_DWORD *)v21.m128i_i64[1] = v19;
      if ( !v19 )
        (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
    }
    goto LABEL_39;
  }
  v8 = *(_DWORD *)(a2->m128i_i64[1] + 24);
  v9 = *(__m128i *)MintValue_CreateEmptyArray(&v24, a3);
  v21 = v9;
  if ( (unsigned __int8)_mm_cvtsi128_si32(v9) == 0xFE )
  {
LABEL_39:
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  v10 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      v23 = (__m128i)0x10FuLL;
      v22 = (__m128i)0x10FuLL;
      ArrayElement = (__m128i *)MintValue_GetArrayElement(v25, a2, v10);
      v12 = _mm_cvtsi128_si32(*ArrayElement);
      v23 = *ArrayElement;
      if ( v12 == -2 )
        goto LABEL_34;
      v24 = *ArrayElement;
      v22 = *(__m128i *)MintValue_Coerce(v26, &v24, v7);
      if ( v23.m128i_i8[0] >= 12 && (v23.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v23.m128i_i64[1] != -1 )
      {
        v13 = *(_DWORD *)v23.m128i_i64[1] - 1;
        *(_DWORD *)v23.m128i_i64[1] = v13;
        if ( !v13 )
          (*(void (__fastcall **)(__m128i *))(v23.m128i_i64[1] + 8))(&v23);
      }
      if ( v22.m128i_i8[0] == -2 )
        goto LABEL_34;
      v14 = MintValue_AppendArrayElement(&v21, &v22);
      if ( v22.m128i_i8[0] >= 12 && (v22.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v22.m128i_i64[1] != -1 )
      {
        v15 = *(_DWORD *)v22.m128i_i64[1] - 1;
        *(_DWORD *)v22.m128i_i64[1] = v15;
        if ( !v15 )
          (*(void (__fastcall **)(__m128i *))(v22.m128i_i64[1] + 8))(&v22);
      }
      if ( v14 )
        goto LABEL_34;
      if ( ++v10 >= v8 )
        goto LABEL_32;
    }
  }
LABEL_33:
  *(__m128i *)a1 = v9;
  return a1;
}

```

## disassembly

```asm
0x18000e0e0  push    rbp
0x18000e0e2  push    rbx
0x18000e0e3  push    rsi
0x18000e0e4  push    rdi
0x18000e0e5  push    r12
0x18000e0e7  push    r14
0x18000e0e9  push    r15
0x18000e0eb  lea     rbp, [rsp-27h]
0x18000e0f0  sub     rsp, 90h
0x18000e0f7  cmp     byte ptr [rdx], 0FFh
0x18000e0fa  mov     edi, r8d
0x18000e0fd  mov     rsi, rdx
0x18000e100  mov     qword ptr [rbp+57h+var_90], 10Fh
0x18000e108  mov     rbx, rcx
0x18000e10b  mov     qword ptr [rbp+57h+var_90+8], 0
0x18000e113  mov     r15d, 100h
0x18000e119  jz      loc_18000E3ED
0x18000e11f  test    [rdx], r15d
0x18000e122  jnz     loc_18000E3ED
0x18000e128  mov     al, [rdx]
0x18000e12a  mov     r14d, r8d
0x18000e12d  and     r14d, 0FFFFFFEFh
0x18000e131  and     al, 0F0h
0x18000e133  cmp     al, 10h
0x18000e135  jnz     loc_18000E26C
0x18000e13b  mov     rax, [rdx+8]
0x18000e13f  lea     rcx, [rbp+57h+var_60]
0x18000e143  mov     edx, edi
0x18000e145  mov     r12d, [rax+18h]
0x18000e149  mov     r8d, r12d
0x18000e14c  call    MintValue_CreateEmptyArray
0x18000e151  movups  xmm0, xmmword ptr [rax]
0x18000e154  movd    eax, xmm0
0x18000e158  movups  [rbp+57h+var_90], xmm0
0x18000e15c  cmp     al, 0FEh
0x18000e15e  jz      loc_18000E3D1
0x18000e164  xor     edi, edi
0x18000e166  test    r12d, r12d
0x18000e169  jz      loc_18000E396
0x18000e16f  mov     r8d, edi
0x18000e172  mov     qword ptr [rbp+57h+var_70], 10Fh
0x18000e17a  mov     rdx, rsi
0x18000e17d  mov     qword ptr [rbp+57h+var_70+8], 0
0x18000e185  lea     rcx, [rbp+57h+var_50]
0x18000e189  mov     qword ptr [rbp+57h+var_80], 10Fh
0x18000e191  mov     qword ptr [rbp+57h+var_80+8], 0
0x18000e199  call    MintValue_GetArrayElement
0x18000e19e  movups  xmm0, xmmword ptr [rax]
0x18000e1a1  movd    ecx, xmm0
0x18000e1a5  movups  [rbp+57h+var_70], xmm0
0x18000e1a9  cmp     cl, 0FEh
0x18000e1ac  jz      loc_18000E3A2
0x18000e1b2  movups  xmm0, xmmword ptr [rax]
0x18000e1b5  mov     r8d, r14d
0x18000e1b8  lea     rdx, [rbp+57h+var_60]
0x18000e1bc  lea     rcx, [rbp+57h+var_40]
0x18000e1c0  movdqu  [rbp+57h+var_60], xmm0
0x18000e1c5  call    MintValue_Coerce
0x18000e1ca  cmp     byte ptr [rbp+57h+var_70], 0Ch
0x18000e1ce  movups  xmm0, xmmword ptr [rax]
0x18000e1d1  movdqu  [rbp+57h+var_80], xmm0
0x18000e1d6  jl      short loc_18000E201
0x18000e1d8  test    dword ptr [rbp+57h+var_70], r15d
0x18000e1dc  jnz     short loc_18000E201
0x18000e1de  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x18000e1e2  mov     eax, [rcx]
0x18000e1e4  cmp     eax, 0FFFFFFFFh
0x18000e1e7  jz      short loc_18000E201
0x18000e1e9  sub     eax, 1
0x18000e1ec  mov     [rcx], eax
0x18000e1ee  jnz     short loc_18000E201
0x18000e1f0  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18000e1f4  lea     rcx, [rbp+57h+var_70]
0x18000e1f8  mov     rax, [rax+8]
0x18000e1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e201  cmp     byte ptr [rbp+57h+var_80], 0FEh
0x18000e205  jz      loc_18000E3A2
0x18000e20b  lea     rdx, [rbp+57h+var_80]
0x18000e20f  lea     rcx, [rbp+57h+var_90]
0x18000e213  call    MintValue_AppendArrayElement
0x18000e218  cmp     byte ptr [rbp+57h+var_80], 0Ch
0x18000e21c  mov     r15d, eax
0x18000e21f  jl      short loc_18000E24D
0x18000e221  test    dword ptr [rbp+57h+var_80], 100h
0x18000e228  jnz     short loc_18000E24D
0x18000e22a  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18000e22e  mov     ecx, [rdx]
0x18000e230  cmp     ecx, 0FFFFFFFFh
0x18000e233  jz      short loc_18000E24D
0x18000e235  sub     ecx, 1
0x18000e238  mov     [rdx], ecx
0x18000e23a  jnz     short loc_18000E24D
0x18000e23c  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18000e240  lea     rcx, [rbp+57h+var_80]
0x18000e244  mov     rax, [rax+8]
0x18000e248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e24d  test    r15d, r15d
0x18000e250  jnz     loc_18000E39C
0x18000e256  inc     edi
0x18000e258  cmp     edi, r12d
0x18000e25b  jnb     loc_18000E392
0x18000e261  mov     r15d, 100h
0x18000e267  jmp     loc_18000E16F
0x18000e26c  cmp     byte ptr [rdx], 0Fh
0x18000e26f  mov     qword ptr [rbp+57h+var_80], 10Fh
0x18000e277  mov     qword ptr [rbp+57h+var_80+8], 0
0x18000e27f  jnz     loc_18000E305
0x18000e285  mov     rcx, [rdx+8]
0x18000e289  mov     rax, cs:off_180047B90
0x18000e290  mov     rcx, [rcx+18h]
0x18000e294  mov     rax, [rax+8]
0x18000e298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e29d  test    rax, rax
0x18000e2a0  jz      short loc_18000E305
0x18000e2a2  xorps   xmm0, xmm0
0x18000e2a5  lea     rcx, ModuleName; "mpunits.dll"
0x18000e2ac  movups  [rbp+57h+var_70], xmm0
0x18000e2b0  call    cs:__imp_GetModuleHandleA
0x18000e2b6  mov     rcx, rax
0x18000e2b9  mov     edx, 813h
0x18000e2be  call    _Intlstr_GetString_LoadString
0x18000e2c3  mov     r8d, 0Bh
0x18000e2c9  mov     qword ptr [rbp+57h+var_70], rax
0x18000e2cd  mov     byte ptr [rbp+57h+var_70+8], 0
0x18000e2d1  lea     r9, [rbp+57h+var_60]
0x18000e2d5  movaps  xmm0, [rbp+57h+var_70]
0x18000e2d9  lea     rdx, aMi; "MI"
0x18000e2e0  mov     [rsp+0C0h+var_98], 0; __int64
0x18000e2e9  lea     ecx, [r8-4]; int
0x18000e2ed  movdqa  [rbp+57h+var_60], xmm0
0x18000e2f2  mov     [rsp+0C0h+var_A0], 0; __int64
0x18000e2fb  call    MI_ReportErrorDetails_ForCustomError
0x18000e300  jmp     loc_18000E3A2
0x18000e305  mov     r8d, 1
0x18000e30b  lea     rcx, [rbp+57h+var_40]
0x18000e30f  mov     edx, edi
0x18000e311  call    MintValue_CreateEmptyArray
0x18000e316  movups  xmm0, xmmword ptr [rax]
0x18000e319  movd    eax, xmm0
0x18000e31d  movups  [rbp+57h+var_90], xmm0
0x18000e321  cmp     al, 0FEh
0x18000e323  jz      loc_18000E3D1
0x18000e329  movups  xmm0, xmmword ptr [rsi]
0x18000e32c  mov     r8d, r14d
0x18000e32f  lea     rdx, [rbp+57h+var_60]
0x18000e333  lea     rcx, [rbp+57h+var_40]
0x18000e337  movdqu  [rbp+57h+var_60], xmm0
0x18000e33c  call    MintValue_Coerce
0x18000e341  movups  xmm0, xmmword ptr [rax]
0x18000e344  movd    eax, xmm0
0x18000e348  movups  [rbp+57h+var_80], xmm0
0x18000e34c  cmp     al, 0FEh
0x18000e34e  jz      short loc_18000E3A2
0x18000e350  lea     rdx, [rbp+57h+var_80]
0x18000e354  lea     rcx, [rbp+57h+var_90]
0x18000e358  call    MintValue_AppendArrayElement
0x18000e35d  cmp     byte ptr [rbp+57h+var_80], 0Ch
0x18000e361  mov     edi, eax
0x18000e363  jl      short loc_18000E38E
0x18000e365  test    dword ptr [rbp+57h+var_80], r15d
0x18000e369  jnz     short loc_18000E38E
0x18000e36b  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18000e36f  mov     ecx, [rdx]
0x18000e371  cmp     ecx, 0FFFFFFFFh
0x18000e374  jz      short loc_18000E38E
0x18000e376  sub     ecx, 1
0x18000e379  mov     [rdx], ecx
0x18000e37b  jnz     short loc_18000E38E
0x18000e37d  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18000e381  lea     rcx, [rbp+57h+var_80]
0x18000e385  mov     rax, [rax+8]
0x18000e389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38e  test    edi, edi
0x18000e390  jnz     short loc_18000E3A2
0x18000e392  movups  xmm0, [rbp+57h+var_90]
0x18000e396  movdqu  xmmword ptr [rbx], xmm0
0x18000e39a  jmp     short loc_18000E40E
0x18000e39c  mov     r15d, 100h
0x18000e3a2  cmp     byte ptr [rbp+57h+var_90], 0Ch
0x18000e3a6  jl      short loc_18000E3D1
0x18000e3a8  test    dword ptr [rbp+57h+var_90], r15d
0x18000e3ac  jnz     short loc_18000E3D1
0x18000e3ae  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x18000e3b2  mov     eax, [rcx]
0x18000e3b4  cmp     eax, 0FFFFFFFFh
0x18000e3b7  jz      short loc_18000E3D1
0x18000e3b9  sub     eax, 1
0x18000e3bc  mov     [rcx], eax
0x18000e3be  jnz     short loc_18000E3D1
0x18000e3c0  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18000e3c4  lea     rcx, [rbp+57h+var_90]
0x18000e3c8  mov     rax, [rax+8]
0x18000e3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3d1  xor     edx, edx
0x18000e3d3  xor     ecx, ecx
0x18000e3d5  mov     eax, 0FFh
0x18000e3da  mov     [rbx+4], edx
0x18000e3dd  and     eax, 0FFFFFFFEh
0x18000e3e0  mov     [rbx+8], rcx
0x18000e3e4  or      eax, 0FEh
0x18000e3e9  mov     [rbx], eax
0x18000e3eb  jmp     short loc_18000E40E
0x18000e3ed  movzx   eax, dil
0x18000e3f1  or      eax, r15d
0x18000e3f4  mov     dword ptr [rbp+57h+var_70+4], 0
0x18000e3fb  mov     dword ptr [rbp+57h+var_70], eax
0x18000e3fe  mov     qword ptr [rbp+57h+var_70+8], 0
0x18000e406  movups  xmm0, [rbp+57h+var_70]
0x18000e40a  movdqu  xmmword ptr [rcx], xmm0
0x18000e40e  mov     rax, rbx
0x18000e411  add     rsp, 90h
0x18000e418  pop     r15
0x18000e41a  pop     r14
0x18000e41c  pop     r12
0x18000e41e  pop     rdi
0x18000e41f  pop     rsi
0x18000e420  pop     rbx
0x18000e421  pop     rbp
0x18000e422  retn
```
