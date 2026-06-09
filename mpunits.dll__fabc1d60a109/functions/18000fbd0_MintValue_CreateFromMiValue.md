# MintValue_CreateFromMiValue

- ea: `0x18000fbd0`
- end: `0x18000ffc9`
- name: `MintValue_CreateFromMiValue`
- size: `1017`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f9d0`
- `0x180017fc0`
- `0x180031674`
- `0x180031b70`
- `0x180033090`
- `0x18003b8b0`

## callees

- `0x180007d60`
- `0x180007ea0`
- `0x18000f9d0`
- `0x18000fbd0`
- `0x18001046c`
- `0x1800104f0`
- `0x180013b30`
- `0x180044836`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fe73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fe73`

## pseudocode

```c
__m128i *__fastcall MintValue_CreateFromMiValue(__m128i *a1, int a2, _QWORD *a3)
{
  unsigned __int64 v6; // rax
  __m128i v7; // xmm0
  char v8; // al
  int v9; // eax
  __m128i v11; // xmm0
  __int64 v12; // rcx
  double v13; // xmm0_8
  __int64 v14; // rax
  size_t v15; // r14
  __m128i v16; // xmm0
  unsigned int v17; // esi
  void *v18; // rcx
  _QWORD *v19; // r15
  __int64 v20; // rbx
  __int64 v21; // rdi
  _QWORD *v22; // rcx
  int v23; // ecx
  __int64 v24; // rdi
  __int64 v25; // r14
  __int64 v26; // rax
  __m128i v27; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v28[24]; // [rsp+30h] [rbp-18h] BYREF

  v27 = 0;
  v27.m128i_i32[0] = (unsigned __int8)a2;
  if ( a2 > 16 )
  {
    if ( a2 > 24 )
    {
      if ( a2 != 25 && a2 != 26 && a2 != 27 && a2 != 28 && a2 != 29 && a2 != 31 )
        goto LABEL_69;
      if ( a2 == 25 )
        goto LABEL_60;
      if ( a2 != 26 )
      {
        if ( a2 == 27 )
          goto LABEL_61;
        if ( a2 == 28 )
        {
          v14 = 36;
          goto LABEL_78;
        }
      }
    }
    else if ( a2 != 24 )
    {
      if ( a2 != 17 && a2 != 18 && a2 != 19 && a2 != 20 && a2 != 21 && (unsigned int)(a2 - 22) > 1 )
        goto LABEL_69;
      if ( a2 != 23 )
      {
        if ( a2 == 17 || a2 == 18 )
          goto LABEL_62;
        if ( a2 != 19 && a2 != 20 )
        {
          if ( (unsigned int)(a2 - 21) <= 1 )
          {
LABEL_60:
            v14 = 4;
            goto LABEL_78;
          }
          v14 = 0;
LABEL_78:
          v15 = v14 * *((unsigned int *)a3 + 2);
          if ( v15 <= 0xFFFFFFFFFFFFFFEFuLL )
          {
            v16 = *(__m128i *)MintValue_CreateUninitializedHeaderObject(
                                v28,
                                (unsigned int)a2,
                                v15 + 32,
                                MintValue_ObjectDestructor_Array);
            v8 = _mm_cvtsi128_si32(v16);
            v27 = v16;
            if ( v8 == -2 )
              goto LABEL_30;
            v17 = *((_DWORD *)a3 + 2);
            *(_DWORD *)(v27.m128i_i64[1] + 24) = v17;
            if ( v17 )
              v18 = (void *)(v27.m128i_i64[1] + 32);
            else
              v18 = 0;
            *(_QWORD *)(v27.m128i_i64[1] + 16) = v18;
            v19 = (_QWORD *)*a3;
            if ( a2 != 29 )
            {
              if ( a2 != 31 )
              {
                memcpy_0(v18, (const void *)*a3, v15);
                goto LABEL_22;
              }
              v20 = 0;
              v21 = *(_QWORD *)(v27.m128i_i64[1] + 16);
              if ( !v17 )
                goto LABEL_22;
              while ( 1 )
              {
                v22 = (_QWORD *)v19[v20];
                if ( !v22 || !*v22 )
                  break;
                v23 = (*(__int64 (__fastcall **)(_QWORD *, __int64))*v22)(v22, v21 + 8 * v20);
                if ( v23 )
                  goto LABEL_95;
                v20 = (unsigned int)(v20 + 1);
                if ( (unsigned int)v20 >= v17 )
                  goto LABEL_22;
              }
              v23 = 4;
LABEL_95:
              *(_DWORD *)(v27.m128i_i64[1] + 24) = v20;
              MI_ReportErrorDetails_ForMiResult(v23);
              goto LABEL_80;
            }
            v24 = 0;
            v25 = *(_QWORD *)(v27.m128i_i64[1] + 16);
            if ( !v17 )
              goto LABEL_22;
            while ( 1 )
            {
              v26 = PoolTls_Tcsdup((void *)v19[v24]);
              *(_QWORD *)(v25 + 8 * v24) = v26;
              if ( !v26 )
                break;
              v24 = (unsigned int)(v24 + 1);
              if ( (unsigned int)v24 >= v17 )
                goto LABEL_22;
            }
            *(_DWORD *)(v27.m128i_i64[1] + 24) = v24;
          }
          MI_ReportErrorDetails_OutOfMemory();
LABEL_80:
          v8 = v27.m128i_i8[0];
          goto LABEL_30;
        }
LABEL_61:
        v14 = 2;
        goto LABEL_78;
      }
    }
    v14 = 8;
    goto LABEL_78;
  }
  if ( a2 == 16 )
  {
LABEL_62:
    v14 = 1;
    goto LABEL_78;
  }
  if ( a2 <= 8 )
  {
    switch ( a2 )
    {
      case 8:
        goto LABEL_13;
      case 0:
        v6 = *(_BYTE *)a3 != 0;
        goto LABEL_21;
      case 1:
        v6 = *(unsigned __int8 *)a3;
        goto LABEL_21;
      case 2:
        v6 = *(char *)a3;
        goto LABEL_21;
    }
    if ( a2 != 3 )
    {
      switch ( a2 )
      {
        case 4:
          v6 = *(__int16 *)a3;
          goto LABEL_21;
        case 5:
          v6 = *(unsigned int *)a3;
          goto LABEL_21;
        case 6:
          v6 = *(int *)a3;
          goto LABEL_21;
        case 7:
LABEL_13:
          v6 = *a3;
LABEL_21:
          v27.m128i_i64[1] = v6;
LABEL_22:
          *a1 = v27;
          return a1;
      }
LABEL_69:
      RaiseException(0xC0000025, 1u, 0, 0);
      goto LABEL_22;
    }
LABEL_17:
    v6 = *(unsigned __int16 *)a3;
    goto LABEL_21;
  }
  switch ( a2 )
  {
    case 9:
      v13 = *(float *)a3;
      goto LABEL_45;
    case 10:
      v13 = *(double *)a3;
LABEL_45:
      *(double *)&v27.m128i_i64[1] = v13;
      goto LABEL_22;
    case 11:
      goto LABEL_17;
    case 12:
      v11 = *(__m128i *)MintValue_CreateUninitializedHeaderObject(v28, 12, 56, MintValue_ObjectDestructor_FreeOnly);
      v8 = _mm_cvtsi128_si32(v11);
      v27 = v11;
      if ( v8 != -2 )
      {
        v12 = v27.m128i_i64[1];
        *(_OWORD *)(v27.m128i_i64[1] + 16) = *(_OWORD *)a3;
        *(_OWORD *)(v12 + 32) = *((_OWORD *)a3 + 1);
        *(_DWORD *)(v12 + 48) = *((_DWORD *)a3 + 8);
        goto LABEL_22;
      }
      break;
    case 13:
      v27 = *(__m128i *)MintValue_CreateViaStrdup(v28, *a3);
      goto LABEL_22;
    case 15:
      v7 = *(__m128i *)MintValue_CreateFromInstance(v28, *a3, 0);
      v8 = _mm_cvtsi128_si32(v7);
      v27 = v7;
      if ( v8 != -2 )
        goto LABEL_22;
      break;
    default:
      goto LABEL_69;
  }
LABEL_30:
  if ( (v8 & 0x10) != 0 && v8 < 32 )
  {
    if ( v27.m128i_i64[1] )
    {
      if ( v8 >= 12 && (v27.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v27.m128i_i64[1] != -1 )
      {
        v9 = *(_DWORD *)v27.m128i_i64[1] - 1;
        *(_DWORD *)v27.m128i_i64[1] = v9;
        if ( !v9 )
          (*(void (__fastcall **)(__m128i *))(v27.m128i_i64[1] + 8))(&v27);
      }
    }
  }
  a1->m128i_i32[1] = 0;
  a1->m128i_i64[1] = 0;
  a1->m128i_i32[0] = 254;
  return a1;
}

```

## disassembly

```asm
0x18000fbd0  push    rbp
0x18000fbd2  push    rbx
0x18000fbd3  push    rsi
0x18000fbd4  push    rdi
0x18000fbd5  push    r12
0x18000fbd7  push    r13
0x18000fbd9  push    r14
0x18000fbdb  push    r15
0x18000fbdd  mov     rbp, rsp
0x18000fbe0  sub     rsp, 48h
0x18000fbe4  mov     ebx, edx
0x18000fbe6  movzx   eax, dl
0x18000fbe9  mov     edx, 4
0x18000fbee  xorps   xmm0, xmm0
0x18000fbf1  mov     rdi, r8
0x18000fbf4  mov     r12, rcx
0x18000fbf7  movups  [rbp+var_28], xmm0
0x18000fbfb  mov     dword ptr [rbp+var_28], eax
0x18000fbfe  lea     r13d, [rdx-3]
0x18000fc02  cmp     ebx, 10h
0x18000fc05  jg      loc_18000FDCC
0x18000fc0b  jz      loc_18000FE3B
0x18000fc11  lea     eax, [rdx+4]
0x18000fc14  cmp     ebx, eax
0x18000fc16  jg      short loc_18000FC87
0x18000fc18  jz      short loc_18000FC45
0x18000fc1a  test    ebx, ebx
0x18000fc1c  jz      short loc_18000FC6C
0x18000fc1e  sub     ebx, r13d
0x18000fc21  jz      short loc_18000FC66
0x18000fc23  sub     ebx, r13d
0x18000fc26  jz      short loc_18000FC60
0x18000fc28  sub     ebx, r13d
0x18000fc2b  jz      short loc_18000FC5A
0x18000fc2d  sub     ebx, r13d
0x18000fc30  jz      short loc_18000FC54
0x18000fc32  sub     ebx, r13d
0x18000fc35  jz      short loc_18000FC4F
0x18000fc37  sub     ebx, r13d
0x18000fc3a  jz      short loc_18000FC4A
0x18000fc3c  cmp     ebx, r13d
0x18000fc3f  jnz     loc_18000FE65
0x18000fc45  mov     rax, [r8]
0x18000fc48  jmp     short loc_18000FC74
0x18000fc4a  movsxd  rax, dword ptr [r8]
0x18000fc4d  jmp     short loc_18000FC74
0x18000fc4f  mov     eax, [r8]
0x18000fc52  jmp     short loc_18000FC74
0x18000fc54  movsx   rax, word ptr [r8]
0x18000fc58  jmp     short loc_18000FC74
0x18000fc5a  movzx   eax, word ptr [r8]
0x18000fc5e  jmp     short loc_18000FC74
0x18000fc60  movsx   rax, byte ptr [r8]
0x18000fc64  jmp     short loc_18000FC74
0x18000fc66  movzx   eax, byte ptr [r8]
0x18000fc6a  jmp     short loc_18000FC74
0x18000fc6c  xor     eax, eax
0x18000fc6e  cmp     [r8], al
0x18000fc71  setnz   al
0x18000fc74  mov     qword ptr [rbp+var_28+8], rax
0x18000fc78  movups  xmm0, [rbp+var_28]
0x18000fc7c  movdqu  xmmword ptr [r12], xmm0
0x18000fc82  jmp     loc_18000FD3C
0x18000fc87  sub     ebx, 9
0x18000fc8a  jz      loc_18000FDBA
0x18000fc90  sub     ebx, r13d
0x18000fc93  jz      loc_18000FDB3
0x18000fc99  sub     ebx, r13d
0x18000fc9c  jz      short loc_18000FC5A
0x18000fc9e  sub     ebx, r13d
0x18000fca1  jz      loc_18000FD69
0x18000fca7  sub     ebx, r13d
0x18000fcaa  jz      loc_18000FD50
0x18000fcb0  sub     ebx, r13d
0x18000fcb3  jz      loc_18000FE65
0x18000fcb9  cmp     ebx, r13d
0x18000fcbc  jnz     loc_18000FE65
0x18000fcc2  mov     rdx, [rdi]
0x18000fcc5  lea     rcx, [rbp+var_18]
0x18000fcc9  xor     r8d, r8d
0x18000fccc  call    MintValue_CreateFromInstance
0x18000fcd1  movups  xmm0, xmmword ptr [rax]
0x18000fcd4  movd    eax, xmm0
0x18000fcd8  movups  [rbp+var_28], xmm0
0x18000fcdc  cmp     al, 0FEh
0x18000fcde  jnz     short loc_18000FC78
0x18000fce0  test    al, 10h
0x18000fce2  jz      short loc_18000FD1D
0x18000fce4  cmp     al, 20h ; ' '
0x18000fce6  jge     short loc_18000FD1D
0x18000fce8  mov     rcx, qword ptr [rbp+var_28+8]
0x18000fcec  test    rcx, rcx
0x18000fcef  jz      short loc_18000FD1D
0x18000fcf1  cmp     al, 0Ch
0x18000fcf3  jl      short loc_18000FD1D
0x18000fcf5  test    dword ptr [rbp+var_28], 100h
0x18000fcfc  jnz     short loc_18000FD1D
0x18000fcfe  mov     eax, [rcx]
0x18000fd00  cmp     eax, 0FFFFFFFFh
0x18000fd03  jz      short loc_18000FD1D
0x18000fd05  sub     eax, r13d
0x18000fd08  mov     [rcx], eax
0x18000fd0a  jnz     short loc_18000FD1D
0x18000fd0c  mov     rax, qword ptr [rbp+var_28+8]
0x18000fd10  lea     rcx, [rbp+var_28]
0x18000fd14  mov     rax, [rax+8]
0x18000fd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd1d  xor     edx, edx
0x18000fd1f  xor     ecx, ecx
0x18000fd21  mov     eax, 0FFh
0x18000fd26  mov     [r12+4], edx
0x18000fd2b  and     eax, 0FFFFFFFEh
0x18000fd2e  mov     [r12+8], rcx
0x18000fd33  or      eax, 0FEh
0x18000fd38  mov     [r12], eax
0x18000fd3c  mov     rax, r12
0x18000fd3f  add     rsp, 48h
0x18000fd43  pop     r15
0x18000fd45  pop     r14
0x18000fd47  pop     r13
0x18000fd49  pop     r12
0x18000fd4b  pop     rdi
0x18000fd4c  pop     rsi
0x18000fd4d  pop     rbx
0x18000fd4e  pop     rbp
0x18000fd4f  retn
0x18000fd50  mov     rdx, [r8]
0x18000fd53  lea     rcx, [rbp+var_18]
0x18000fd57  call    MintValue_CreateViaStrdup
0x18000fd5c  movups  xmm0, xmmword ptr [rax]
0x18000fd5f  movdqu  [rbp+var_28], xmm0
0x18000fd64  jmp     loc_18000FC78
0x18000fd69  mov     edx, 0Ch
0x18000fd6e  lea     r9, MintValue_ObjectDestructor_FreeOnly
0x18000fd75  lea     rcx, [rbp+var_18]
0x18000fd79  lea     r8d, [rdx+2Ch]
0x18000fd7d  call    MintValue_CreateUninitializedHeaderObject
0x18000fd82  movups  xmm0, xmmword ptr [rax]
0x18000fd85  movd    eax, xmm0
0x18000fd89  movups  [rbp+var_28], xmm0
0x18000fd8d  cmp     al, 0FEh
0x18000fd8f  jz      loc_18000FCE0
0x18000fd95  mov     rcx, qword ptr [rbp+var_28+8]
0x18000fd99  movups  xmm0, xmmword ptr [rdi]
0x18000fd9c  movups  xmmword ptr [rcx+10h], xmm0
0x18000fda0  movups  xmm1, xmmword ptr [rdi+10h]
0x18000fda4  movups  xmmword ptr [rcx+20h], xmm1
0x18000fda8  mov     eax, [rdi+20h]
0x18000fdab  mov     [rcx+30h], eax
0x18000fdae  jmp     loc_18000FC78
0x18000fdb3  movsd   xmm0, qword ptr [r8]
0x18000fdb8  jmp     short loc_18000FDC2
0x18000fdba  movss   xmm0, dword ptr [r8]
0x18000fdbf  cvtps2pd xmm0, xmm0
0x18000fdc2  movsd   qword ptr [rbp+var_28+8], xmm0
0x18000fdc7  jmp     loc_18000FC78
0x18000fdcc  cmp     ebx, 18h
0x18000fdcf  jg      short loc_18000FE40
0x18000fdd1  jz      loc_18000FEB2
0x18000fdd7  mov     ecx, ebx
0x18000fdd9  sub     ecx, 11h
0x18000fddc  jz      short loc_18000FDFC
0x18000fdde  sub     ecx, r13d
0x18000fde1  jz      short loc_18000FDFC
0x18000fde3  sub     ecx, r13d
0x18000fde6  jz      short loc_18000FDFC
0x18000fde8  sub     ecx, r13d
0x18000fdeb  jz      short loc_18000FDFC
0x18000fded  sub     ecx, r13d
0x18000fdf0  jz      short loc_18000FDFC
0x18000fdf2  sub     ecx, r13d
0x18000fdf5  jz      short loc_18000FDFC
0x18000fdf7  cmp     ecx, r13d
0x18000fdfa  jnz     short loc_18000FE65
0x18000fdfc  cmp     ebx, 17h
0x18000fdff  jg      short loc_18000FE7E
0x18000fe01  jz      loc_18000FEB2
0x18000fe07  mov     ecx, ebx
0x18000fe09  sub     ecx, 10h
0x18000fe0c  jz      short loc_18000FE3B
0x18000fe0e  sub     ecx, r13d
0x18000fe11  jz      short loc_18000FE3B
0x18000fe13  sub     ecx, r13d
0x18000fe16  jz      short loc_18000FE3B
0x18000fe18  sub     ecx, r13d
0x18000fe1b  jz      short loc_18000FE34
0x18000fe1d  sub     ecx, r13d
0x18000fe20  jz      short loc_18000FE34
0x18000fe22  sub     ecx, r13d
0x18000fe25  jz      short loc_18000FE2C
0x18000fe27  cmp     ecx, r13d
0x18000fe2a  jnz     short loc_18000FEA7
0x18000fe2c  mov     rax, rdx
0x18000fe2f  jmp     loc_18000FEB7
0x18000fe34  mov     eax, 2
0x18000fe39  jmp     short loc_18000FEB7
0x18000fe3b  mov     rax, r13
0x18000fe3e  jmp     short loc_18000FEB7
0x18000fe40  mov     ecx, ebx
0x18000fe42  sub     ecx, 19h
0x18000fe45  jz      short loc_18000FE7E
0x18000fe47  sub     ecx, r13d
0x18000fe4a  jz      short loc_18000FE7E
0x18000fe4c  sub     ecx, r13d
0x18000fe4f  jz      short loc_18000FE7E
0x18000fe51  sub     ecx, r13d
0x18000fe54  jz      short loc_18000FE7E
0x18000fe56  sub     ecx, r13d
0x18000fe59  jz      short loc_18000FE7E
0x18000fe5b  sub     ecx, r13d
0x18000fe5e  jz      short loc_18000FE65
0x18000fe60  cmp     ecx, r13d
0x18000fe63  jz      short loc_18000FE7E
0x18000fe65  xor     r9d, r9d; lpArguments
0x18000fe68  xor     r8d, r8d; nNumberOfArguments
0x18000fe6b  mov     edx, r13d; dwExceptionFlags
0x18000fe6e  mov     ecx, 0C0000025h; dwExceptionCode
0x18000fe73  call    cs:__imp_RaiseException
0x18000fe79  jmp     loc_18000FC78
0x18000fe7e  mov     ecx, ebx
0x18000fe80  sub     ecx, 18h
0x18000fe83  jz      short loc_18000FEB2
0x18000fe85  sub     ecx, r13d
0x18000fe88  jz      short loc_18000FE2C
0x18000fe8a  sub     ecx, r13d
0x18000fe8d  jz      short loc_18000FEB2
0x18000fe8f  sub     ecx, r13d
0x18000fe92  jz      short loc_18000FE34
0x18000fe94  sub     ecx, r13d
0x18000fe97  jz      short loc_18000FEAB
0x18000fe99  sub     ecx, r13d
0x18000fe9c  jz      short loc_18000FEB2
0x18000fe9e  mov     eax, 2
0x18000fea3  cmp     ecx, eax
0x18000fea5  jz      short loc_18000FEB2
0x18000fea7  xor     eax, eax
0x18000fea9  jmp     short loc_18000FEB7
0x18000feab  mov     eax, 24h ; '$'
0x18000feb0  jmp     short loc_18000FEB7
0x18000feb2  mov     eax, 8
0x18000feb7  mov     r14d, [r8+8]
0x18000febb  imul    r14, rax
0x18000febf  cmp     r14, 0FFFFFFFFFFFFFFEFh
0x18000fec3  jbe     short loc_18000FED2
0x18000fec5  call    MI_ReportErrorDetails_OutOfMemory
0x18000feca  mov     al, byte ptr [rbp+var_28]
0x18000fecd  jmp     loc_18000FCE0
0x18000fed2  lea     r8, [r14+20h]
0x18000fed6  mov     edx, ebx
0x18000fed8  lea     r9, MintValue_ObjectDestructor_Array
0x18000fedf  lea     rcx, [rbp+var_18]
0x18000fee3  call    MintValue_CreateUninitializedHeaderObject
0x18000fee8  movups  xmm0, xmmword ptr [rax]
0x18000feeb  movd    eax, xmm0
0x18000feef  movups  [rbp+var_28], xmm0
0x18000fef3  cmp     al, 0FEh
0x18000fef5  jz      loc_18000FCE0
0x18000fefb  mov     rax, qword ptr [rbp+var_28+8]
0x18000feff  mov     esi, [rdi+8]
0x18000ff02  mov     [rax+18h], esi
0x18000ff05  mov     rax, qword ptr [rbp+var_28+8]
0x18000ff09  test    esi, esi
0x18000ff0b  jnz     short loc_18000FF11
0x18000ff0d  xor     ecx, ecx
0x18000ff0f  jmp     short loc_18000FF15
0x18000ff11  lea     rcx, [rax+20h]; void *
0x18000ff15  mov     [rax+10h], rcx
0x18000ff19  mov     r15, [rdi]
0x18000ff1c  cmp     ebx, 1Dh
0x18000ff1f  jz      short loc_18000FF8D
0x18000ff21  cmp     ebx, 1Fh
0x18000ff24  jz      short loc_18000FF36
0x18000ff26  mov     r8, r14; Size
0x18000ff29  mov     rdx, r15; Src
0x18000ff2c  call    memcpy_0
0x18000ff31  jmp     loc_18000FC78
0x18000ff36  mov     rax, qword ptr [rbp+var_28+8]
0x18000ff3a  xor     ebx, ebx
0x18000ff3c  mov     rdi, [rax+10h]
0x18000ff40  test    esi, esi
0x18000ff42  jz      loc_18000FC78
0x18000ff48  mov     rcx, [r15+rbx*8]
0x18000ff4c  test    rcx, rcx
0x18000ff4f  jz      short loc_18000FF77
0x18000ff51  mov     rax, [rcx]
0x18000ff54  test    rax, rax
0x18000ff57  jz      short loc_18000FF77
0x18000ff59  mov     rax, [rax]
0x18000ff5c  lea     rdx, [rdi+rbx*8]
0x18000ff60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff65  mov     ecx, eax
0x18000ff67  test    eax, eax
0x18000ff69  jnz     short loc_18000FF7C
0x18000ff6b  add     ebx, r13d
0x18000ff6e  cmp     ebx, esi
0x18000ff70  jb      short loc_18000FF48
0x18000ff72  jmp     loc_18000FC78
0x18000ff77  mov     ecx, 4; int
0x18000ff7c  mov     rax, qword ptr [rbp+var_28+8]
0x18000ff80  mov     [rax+18h], ebx
  ... truncated ...
```
