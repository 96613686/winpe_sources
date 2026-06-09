# basicOps_newArray

- ea: `0x180018830`
- end: `0x180018bf0`
- name: `basicOps_newArray`
- size: `960`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x180007ea0`
- `0x18000db80`
- `0x18000e010`
- `0x18000f1a0`
- `0x18000f830`
- `0x18000f870`
- `0x180013bb0`
- `0x180018830`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018969`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018a17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018ad2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018969`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018a17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018ad2`

## string_xrefs

- `0x18001895e`: `mpunits.dll`
- `0x180018a0c`: `mpunits.dll`
- `0x180018ac7`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_newArray(__int64 a1, __m128i *a2, int a3)
{
  __int64 v3; // r14
  int v6; // edi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  HMODULE ModuleHandleA; // rax
  __int64 v12; // rdx
  int v13; // ebx
  bool v14; // zf
  __int64 v15; // rax
  __m128i v16; // xmm0
  __int8 v17; // dl
  __int64 v18; // xmm0_8
  unsigned __int64 v19; // xmm0_8
  HMODULE v20; // rax
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // eax
  __m128i v24; // [rsp+30h] [rbp-39h] BYREF
  __m128i v25; // [rsp+40h] [rbp-29h] BYREF
  __m128i v26; // [rsp+50h] [rbp-19h] BYREF
  __m128i v27; // [rsp+60h] [rbp-9h] BYREF
  __m128i v28; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v29[64]; // [rsp+80h] [rbp+17h] BYREF

  v3 = a3;
  v25 = (__m128i)0x10FuLL;
  v24 = (__m128i)0x10FuLL;
  v6 = 2;
  v26 = (__m128i)0x10FuLL;
  if ( a3 < 2 )
  {
    BuiltinsError_WrongNumberOfArguments(&v28, (unsigned int)a3);
    goto LABEL_3;
  }
  if ( a2->m128i_i8[0] != -4 )
  {
    v27 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v12 = 2069;
LABEL_22:
    v27.m128i_i64[0] = Intlstr_GetString_LoadString(ModuleHandleA, v12);
    v27.m128i_i8[8] = 0;
LABEL_23:
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    goto LABEL_3;
  }
  v13 = a2->m128i_i32[2];
  if ( v13 > 23 )
  {
    if ( v13 == 24 || v13 == 25 || v13 == 26 || v13 == 27 || v13 == 28 || v13 == 29 )
      goto LABEL_42;
    v14 = v13 == 31;
  }
  else
  {
    if ( v13 == 23 || v13 == 16 || v13 == 17 || v13 == 18 || v13 == 19 || v13 == 20 || v13 == 21 )
      goto LABEL_42;
    v14 = v13 == 22;
  }
  if ( !v14 )
  {
    v27 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v12 = 2070;
    goto LABEL_22;
  }
LABEL_42:
  v28 = a2[1];
  v27 = v28;
  v15 = MintValue_CoerceToUint64(v29, &v27);
  if ( *(_BYTE *)v15 == 0xFF )
  {
    v16 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException_Impl(v29, &v28, 7);
    v17 = _mm_cvtsi128_si32(v16);
  }
  else
  {
    v18 = *(_QWORD *)(v15 + 1);
    v17 = *(_BYTE *)v15;
    *(__int32 *)((char *)&v27.m128i_i32[2] + 1) = *(_DWORD *)(v15 + 9);
    *(__int16 *)((char *)&v27.m128i_i16[6] + 1) = *(_WORD *)(v15 + 13);
    v27.m128i_i8[15] = *(_BYTE *)(v15 + 15);
    v27.m128i_i8[0] = v17;
    *(__int64 *)((char *)v27.m128i_i64 + 1) = v18;
    v16 = v27;
  }
  v25 = v16;
  if ( v17 == -2 )
  {
LABEL_3:
    if ( v26.m128i_i8[0] >= 12 && (v26.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v26.m128i_i64[1] != -1 )
    {
      v7 = *(_DWORD *)v26.m128i_i64[1] - 1;
      *(_DWORD *)v26.m128i_i64[1] = v7;
      if ( !v7 )
        (*(void (__fastcall **)(__m128i *))(v26.m128i_i64[1] + 8))(&v26);
    }
    goto LABEL_8;
  }
  v19 = _mm_srli_si128(v16, 8).m128i_u64[0];
  if ( v19 >= 0xFFFFFFFF )
  {
    MI_ReportErrorDetails_OutOfMemory();
    goto LABEL_3;
  }
  if ( v19 != v3 - 2 )
  {
    v27 = 0;
    v20 = GetModuleHandleA("mpunits.dll");
    v27.m128i_i64[0] = Intlstr_GetString_LoadString(v20, 2071);
    v27.m128i_i8[8] = 0;
    v28 = v27;
    goto LABEL_23;
  }
  v26 = *(__m128i *)MintValue_CreateEmptyArray(v29, (unsigned int)v13);
  if ( (unsigned __int8)_mm_cvtsi128_si32(v26) == 0xFE )
  {
LABEL_8:
    if ( v25.m128i_i8[0] >= 12 && (v25.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v25.m128i_i64[1] != -1 )
    {
      v8 = *(_DWORD *)v25.m128i_i64[1] - 1;
      *(_DWORD *)v25.m128i_i64[1] = v8;
      if ( !v8 )
        (*(void (__fastcall **)(__m128i *))(v25.m128i_i64[1] + 8))(&v25);
    }
    if ( v24.m128i_i8[0] >= 12 && (v24.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v24.m128i_i64[1] != -1 )
    {
      v9 = *(_DWORD *)v24.m128i_i64[1] - 1;
      *(_DWORD *)v24.m128i_i64[1] = v9;
      if ( !v9 )
        (*(void (__fastcall **)(__m128i *))(v24.m128i_i64[1] + 8))(&v24);
    }
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  v21 = v13 & 0xFFFFFFEF;
  if ( (int)v3 > 2 )
  {
    do
    {
      v28 = a2[v6];
      v24 = *(__m128i *)MintValue_Coerce(v29, &v28, v21);
      v24.m128i_i8[0] = _mm_cvtsi128_si32(v24);
      if ( v24.m128i_i8[0] == -2 || (unsigned int)MintValue_AppendArrayElement(&v26, &v24) )
        goto LABEL_3;
      if ( v24.m128i_i8[0] >= 12 && (v24.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v24.m128i_i64[1] != -1 )
      {
        v22 = *(_DWORD *)v24.m128i_i64[1] - 1;
        *(_DWORD *)v24.m128i_i64[1] = v22;
        if ( !v22 )
          (*(void (__fastcall **)(__m128i *))(v24.m128i_i64[1] + 8))(&v24);
      }
    }
    while ( ++v6 < (int)v3 );
  }
  if ( v25.m128i_i8[0] >= 12 && (v25.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v25.m128i_i64[1] != -1 )
  {
    v23 = *(_DWORD *)v25.m128i_i64[1] - 1;
    *(_DWORD *)v25.m128i_i64[1] = v23;
    if ( !v23 )
      (*(void (__fastcall **)(__m128i *))(v25.m128i_i64[1] + 8))(&v25);
  }
  *(__m128i *)a1 = v26;
  return a1;
}

```

## disassembly

```asm
0x180018830  push    rbp
0x180018832  push    rbx
0x180018833  push    rsi
0x180018834  push    rdi
0x180018835  push    r12
0x180018837  push    r14
0x180018839  push    r15
0x18001883b  lea     rbp, [rsp-27h]
0x180018840  sub     rsp, 90h
0x180018847  xor     r12d, r12d
0x18001884a  movsxd  r14, r8d
0x18001884d  mov     r15, rdx
0x180018850  mov     qword ptr [rbp+57h+var_80], 10Fh
0x180018858  mov     rsi, rcx
0x18001885b  mov     qword ptr [rbp+57h+var_80+8], r12
0x18001885f  mov     qword ptr [rbp+57h+var_90], 10Fh
0x180018867  lea     edi, [r12+2]
0x18001886c  mov     qword ptr [rbp+57h+var_90+8], r12
0x180018870  mov     qword ptr [rbp+57h+var_70], 10Fh
0x180018878  mov     qword ptr [rbp+57h+var_70+8], r12
0x18001887c  cmp     r14d, edi
0x18001887f  jge     loc_180018956
0x180018885  mov     edx, r14d
0x180018888  lea     rcx, [rbp+57h+var_50]
0x18001888c  call    BuiltinsError_WrongNumberOfArguments
0x180018891  cmp     byte ptr [rbp+57h+var_70], 0Ch
0x180018895  jl      short loc_1800188C3
0x180018897  test    dword ptr [rbp+57h+var_70], 100h
0x18001889e  jnz     short loc_1800188C3
0x1800188a0  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x1800188a4  mov     eax, [rcx]
0x1800188a6  cmp     eax, 0FFFFFFFFh
0x1800188a9  jz      short loc_1800188C3
0x1800188ab  sub     eax, 1
0x1800188ae  mov     [rcx], eax
0x1800188b0  jnz     short loc_1800188C3
0x1800188b2  mov     rax, qword ptr [rbp+57h+var_70+8]
0x1800188b6  lea     rcx, [rbp+57h+var_70]
0x1800188ba  mov     rax, [rax+8]
0x1800188be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188c3  cmp     byte ptr [rbp+57h+var_80], 0Ch
0x1800188c7  jl      short loc_1800188F5
0x1800188c9  test    dword ptr [rbp+57h+var_80], 100h
0x1800188d0  jnz     short loc_1800188F5
0x1800188d2  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1800188d6  mov     eax, [rcx]
0x1800188d8  cmp     eax, 0FFFFFFFFh
0x1800188db  jz      short loc_1800188F5
0x1800188dd  sub     eax, 1
0x1800188e0  mov     [rcx], eax
0x1800188e2  jnz     short loc_1800188F5
0x1800188e4  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800188e8  lea     rcx, [rbp+57h+var_80]
0x1800188ec  mov     rax, [rax+8]
0x1800188f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188f5  cmp     byte ptr [rbp+57h+var_90], 0Ch
0x1800188f9  jl      short loc_180018927
0x1800188fb  test    dword ptr [rbp+57h+var_90], 100h
0x180018902  jnz     short loc_180018927
0x180018904  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x180018908  mov     eax, [rcx]
0x18001890a  cmp     eax, 0FFFFFFFFh
0x18001890d  jz      short loc_180018927
0x18001890f  sub     eax, 1
0x180018912  mov     [rcx], eax
0x180018914  jnz     short loc_180018927
0x180018916  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18001891a  lea     rcx, [rbp+57h+var_90]
0x18001891e  mov     rax, [rax+8]
0x180018922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018927  xor     edx, edx
0x180018929  xor     ecx, ecx
0x18001892b  mov     eax, 0FFh
0x180018930  mov     [rsi+4], edx
0x180018933  and     eax, 0FFFFFFFEh
0x180018936  mov     [rsi+8], rcx
0x18001893a  or      eax, 0FEh
0x18001893f  mov     [rsi], eax
0x180018941  mov     rax, rsi
0x180018944  add     rsp, 90h
0x18001894b  pop     r15
0x18001894d  pop     r14
0x18001894f  pop     r12
0x180018951  pop     rdi
0x180018952  pop     rsi
0x180018953  pop     rbx
0x180018954  pop     rbp
0x180018955  retn
0x180018956  cmp     byte ptr [rdx], 0FCh
0x180018959  jz      short loc_1800189B6
0x18001895b  xorps   xmm0, xmm0
0x18001895e  lea     rcx, ModuleName; "mpunits.dll"
0x180018965  movups  [rbp+57h+var_60], xmm0
0x180018969  call    cs:__imp_GetModuleHandleA
0x18001896f  mov     edx, 815h
0x180018974  mov     rcx, rax
0x180018977  call    _Intlstr_GetString_LoadString
0x18001897c  mov     qword ptr [rbp+57h+var_60], rax
0x180018980  lea     r9, [rbp+57h+var_60]
0x180018984  mov     byte ptr [rbp+57h+var_60+8], r12b
0x180018988  movaps  xmm0, [rbp+57h+var_60]
0x18001898c  movdqa  [rbp+57h+var_60], xmm0
0x180018991  mov     r8d, 5
0x180018997  mov     [rsp+0C0h+var_98], r12; __int64
0x18001899c  lea     rdx, aMi; "MI"
0x1800189a3  mov     [rsp+0C0h+var_A0], r12; __int64
0x1800189a8  lea     ecx, [r8-1]; int
0x1800189ac  call    MI_ReportErrorDetails_ForCustomError
0x1800189b1  jmp     loc_180018891
0x1800189b6  mov     ebx, [rdx+8]
0x1800189b9  cmp     ebx, 17h
0x1800189bc  jg      short loc_1800189E5
0x1800189be  jz      short loc_180018A27
0x1800189c0  mov     ecx, ebx
0x1800189c2  sub     ecx, 10h
0x1800189c5  jz      short loc_180018A27
0x1800189c7  sub     ecx, 1
0x1800189ca  jz      short loc_180018A27
0x1800189cc  sub     ecx, 1
0x1800189cf  jz      short loc_180018A27
0x1800189d1  sub     ecx, 1
0x1800189d4  jz      short loc_180018A27
0x1800189d6  sub     ecx, 1
0x1800189d9  jz      short loc_180018A27
0x1800189db  sub     ecx, 1
0x1800189de  jz      short loc_180018A27
0x1800189e0  cmp     ecx, 1
0x1800189e3  jmp     short loc_180018A07
0x1800189e5  mov     ecx, ebx
0x1800189e7  sub     ecx, 18h
0x1800189ea  jz      short loc_180018A27
0x1800189ec  sub     ecx, 1
0x1800189ef  jz      short loc_180018A27
0x1800189f1  sub     ecx, 1
0x1800189f4  jz      short loc_180018A27
0x1800189f6  sub     ecx, 1
0x1800189f9  jz      short loc_180018A27
0x1800189fb  sub     ecx, 1
0x1800189fe  jz      short loc_180018A27
0x180018a00  sub     ecx, 1
0x180018a03  jz      short loc_180018A27
0x180018a05  cmp     ecx, edi
0x180018a07  jz      short loc_180018A27
0x180018a09  xorps   xmm0, xmm0
0x180018a0c  lea     rcx, ModuleName; "mpunits.dll"
0x180018a13  movups  [rbp+57h+var_60], xmm0
0x180018a17  call    cs:__imp_GetModuleHandleA
0x180018a1d  mov     edx, 816h
0x180018a22  jmp     loc_180018974
0x180018a27  movups  xmm0, xmmword ptr [rdx+10h]
0x180018a2b  lea     rdx, [rbp+57h+var_60]
0x180018a2f  lea     rcx, [rbp+57h+var_40]
0x180018a33  movdqu  [rbp+57h+var_50], xmm0
0x180018a38  movdqu  [rbp+57h+var_60], xmm0
0x180018a3d  call    MintValue_CoerceToUint64
0x180018a42  mov     rcx, rax
0x180018a45  cmp     byte ptr [rax], 0FFh
0x180018a48  jnz     short loc_180018A66
0x180018a4a  mov     r8d, 7
0x180018a50  lea     rdx, [rbp+57h+var_50]
0x180018a54  lea     rcx, [rbp+57h+var_40]
0x180018a58  call    MintValue_CoerceAndRaiseInvalidCastException_Impl
0x180018a5d  movups  xmm0, xmmword ptr [rax]
0x180018a60  movd    edx, xmm0
0x180018a64  jmp     short loc_180018A8D
0x180018a66  movsd   xmm0, qword ptr [rax+1]
0x180018a6b  mov     dl, [rax]
0x180018a6d  mov     eax, [rax+9]
0x180018a70  mov     dword ptr [rbp+57h+var_60+9], eax
0x180018a73  movzx   eax, word ptr [rcx+0Dh]
0x180018a77  mov     word ptr [rbp+57h+var_60+0Dh], ax
0x180018a7b  mov     al, [rcx+0Fh]
0x180018a7e  mov     byte ptr [rbp+57h+var_60+0Fh], al
0x180018a81  mov     byte ptr [rbp+57h+var_60], dl
0x180018a84  movsd   qword ptr [rbp+57h+var_60+1], xmm0
0x180018a89  movaps  xmm0, [rbp+57h+var_60]
0x180018a8d  movdqa  [rbp+57h+var_80], xmm0
0x180018a92  cmp     dl, 0FEh
0x180018a95  jz      loc_180018891
0x180018a9b  psrldq  xmm0, 8
0x180018aa0  mov     eax, 0FFFFFFFFh
0x180018aa5  movq    r8, xmm0
0x180018aaa  cmp     r8, rax
0x180018aad  jb      short loc_180018AB9
0x180018aaf  call    MI_ReportErrorDetails_OutOfMemory
0x180018ab4  jmp     loc_180018891
0x180018ab9  mov     rax, r14
0x180018abc  sub     rax, rdi
0x180018abf  cmp     r8, rax
0x180018ac2  jz      short loc_180018AFF
0x180018ac4  xorps   xmm0, xmm0
0x180018ac7  lea     rcx, ModuleName; "mpunits.dll"
0x180018ace  movups  [rbp+57h+var_60], xmm0
0x180018ad2  call    cs:__imp_GetModuleHandleA
0x180018ad8  mov     rcx, rax
0x180018adb  mov     edx, 817h
0x180018ae0  call    _Intlstr_GetString_LoadString
0x180018ae5  mov     qword ptr [rbp+57h+var_60], rax
0x180018ae9  lea     r9, [rbp+57h+var_50]
0x180018aed  mov     byte ptr [rbp+57h+var_60+8], r12b
0x180018af1  movaps  xmm0, [rbp+57h+var_60]
0x180018af5  movdqa  [rbp+57h+var_50], xmm0
0x180018afa  jmp     loc_180018991
0x180018aff  mov     edx, ebx
0x180018b01  lea     rcx, [rbp+57h+var_40]
0x180018b05  call    MintValue_CreateEmptyArray
0x180018b0a  movups  xmm0, xmmword ptr [rax]
0x180018b0d  movd    eax, xmm0
0x180018b11  movups  [rbp+57h+var_70], xmm0
0x180018b15  cmp     al, 0FEh
0x180018b17  jz      loc_1800188C3
0x180018b1d  and     ebx, 0FFFFFFEFh
0x180018b20  cmp     r14d, edi
0x180018b23  jle     loc_180018BB1
0x180018b29  movsxd  rax, edi
0x180018b2c  lea     rdx, [rbp+57h+var_50]
0x180018b30  add     rax, rax
0x180018b33  lea     rcx, [rbp+57h+var_40]
0x180018b37  mov     r8d, ebx
0x180018b3a  movups  xmm0, xmmword ptr [r15+rax*8]
0x180018b3f  movdqu  [rbp+57h+var_50], xmm0
0x180018b44  call    MintValue_Coerce
0x180018b49  movups  xmm0, xmmword ptr [rax]
0x180018b4c  movd    eax, xmm0
0x180018b50  movups  [rbp+57h+var_90], xmm0
0x180018b54  mov     byte ptr [rbp+57h+var_90], al
0x180018b57  cmp     al, 0FEh
0x180018b59  jz      loc_180018891
0x180018b5f  lea     rdx, [rbp+57h+var_90]
0x180018b63  lea     rcx, [rbp+57h+var_70]
0x180018b67  call    MintValue_AppendArrayElement
0x180018b6c  test    eax, eax
0x180018b6e  jnz     loc_180018891
0x180018b74  cmp     byte ptr [rbp+57h+var_90], 0Ch
0x180018b78  jl      short loc_180018BA6
0x180018b7a  test    dword ptr [rbp+57h+var_90], 100h
0x180018b81  jnz     short loc_180018BA6
0x180018b83  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x180018b87  mov     eax, [rcx]
0x180018b89  cmp     eax, 0FFFFFFFFh
0x180018b8c  jz      short loc_180018BA6
0x180018b8e  sub     eax, 1
0x180018b91  mov     [rcx], eax
0x180018b93  jnz     short loc_180018BA6
0x180018b95  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180018b99  lea     rcx, [rbp+57h+var_90]
0x180018b9d  mov     rax, [rax+8]
0x180018ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ba6  inc     edi
0x180018ba8  cmp     edi, r14d
0x180018bab  jl      loc_180018B29
0x180018bb1  cmp     byte ptr [rbp+57h+var_80], 0Ch
0x180018bb5  jl      short loc_180018BE3
0x180018bb7  test    dword ptr [rbp+57h+var_80], 100h
0x180018bbe  jnz     short loc_180018BE3
0x180018bc0  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x180018bc4  mov     eax, [rcx]
0x180018bc6  cmp     eax, 0FFFFFFFFh
0x180018bc9  jz      short loc_180018BE3
0x180018bcb  sub     eax, 1
0x180018bce  mov     [rcx], eax
0x180018bd0  jnz     short loc_180018BE3
0x180018bd2  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180018bd6  lea     rcx, [rbp+57h+var_80]
0x180018bda  mov     rax, [rax+8]
0x180018bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018be3  movups  xmm0, [rbp+57h+var_70]
0x180018be7  movdqu  xmmword ptr [rsi], xmm0
0x180018beb  jmp     loc_180018941
```
