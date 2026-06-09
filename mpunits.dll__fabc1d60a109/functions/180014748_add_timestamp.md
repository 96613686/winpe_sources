# add_timestamp

- ea: `0x180014748`
- end: `0x180014946`
- name: `add_timestamp`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014de0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000be30`
- `0x1800103c8`
- `0x180012820`
- `0x180014748`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014823`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014823`

## string_xrefs

- `0x180014818`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall add_timestamp(__int64 a1, __int64 a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __m128i v6; // xmm6
  __int64 v7; // r10
  unsigned int *v8; // r9
  __int64 v9; // rdx
  HMODULE ModuleHandleA; // rax
  __int64 TimestampFromMicroseconds; // rax
  char v12; // di
  __int64 v13; // xmm6_8
  int v14; // esi
  __int16 v15; // r14
  char v16; // r15
  int v17; // eax
  int v19; // eax
  __m128i v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v22[16]; // [rsp+50h] [rbp-28h] BYREF

  v3 = *a3;
  v20 = (__m128i)0x10FuLL;
  v21 = v3;
  v6 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v22, MintValue_CoerceToInterval, &v21, 4294966295LL);
  v20 = v6;
  if ( (unsigned __int8)_mm_cvtsi128_si32(v6) == 0xFE )
  {
LABEL_12:
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  v7 = Timestamp_ToMicroseconds(*(_QWORD *)(a2 + 8) + 20LL);
  v8 = (unsigned int *)_mm_srli_si128(v6, 8).m128i_u64[0];
  v9 = v8[9] + 1000000 * (v8[8] + 60 * (v8[7] + 60 * (v8[6] + 24LL * v8[5])));
  if ( v7 == 0xFFFFFFF5F123923FuLL )
  {
    if ( v9 == 8639999999999000000LL )
    {
      v21 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v21 = Intlstr_GetString_LoadString(ModuleHandleA, 2047);
      BYTE8(v21) = 0;
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
LABEL_7:
      if ( v20.m128i_i8[0] >= 12 && (v20.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v20.m128i_i64[1] != -1 )
      {
        v17 = *(_DWORD *)v20.m128i_i64[1] - 1;
        *(_DWORD *)v20.m128i_i64[1] = v17;
        if ( !v17 )
          (*(void (__fastcall **)(__m128i *))(v20.m128i_i64[1] + 8))(&v20);
      }
      goto LABEL_12;
    }
    v9 = 0;
  }
  TimestampFromMicroseconds = MintValue_CreateTimestampFromMicroseconds(v22, v7 + v9);
  v12 = *(_BYTE *)TimestampFromMicroseconds;
  v13 = *(_QWORD *)(TimestampFromMicroseconds + 1);
  v14 = *(_DWORD *)(TimestampFromMicroseconds + 9);
  v15 = *(_WORD *)(TimestampFromMicroseconds + 13);
  v16 = *(_BYTE *)(TimestampFromMicroseconds + 15);
  if ( *(_BYTE *)TimestampFromMicroseconds == 0xFE )
    goto LABEL_7;
  if ( v20.m128i_i8[0] >= 12 && (v20.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v20.m128i_i64[1] != -1 )
  {
    v19 = *(_DWORD *)v20.m128i_i64[1] - 1;
    *(_DWORD *)v20.m128i_i64[1] = v19;
    if ( !v19 )
      (*(void (__fastcall **)(__m128i *))(v20.m128i_i64[1] + 8))(&v20);
  }
  *(_QWORD *)(a1 + 1) = v13;
  *(_DWORD *)(a1 + 9) = v14;
  *(_WORD *)(a1 + 13) = v15;
  *(_BYTE *)(a1 + 15) = v16;
  *(_BYTE *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x180014748  push    rbp
0x18001474a  push    rbx
0x18001474b  push    rsi
0x18001474c  push    rdi
0x18001474d  push    r14
0x18001474f  push    r15
0x180014751  mov     rbp, rsp
0x180014754  sub     rsp, 78h
0x180014758  movups  xmm0, xmmword ptr [r8]
0x18001475c  mov     rdi, rdx
0x18001475f  mov     rbx, rcx
0x180014762  lea     r8, [rbp+var_38]
0x180014766  movaps  [rsp+78h+var_18], xmm6
0x18001476b  mov     r9d, 0FFFFFC17h
0x180014771  mov     qword ptr [rbp+var_48], 10Fh
0x180014779  lea     rdx, MintValue_CoerceToInterval
0x180014780  mov     qword ptr [rbp+var_48+8], 0
0x180014788  lea     rcx, [rbp+var_28]
0x18001478c  movdqu  [rbp+var_38], xmm0
0x180014791  call    MintValue_CoerceAndRaiseInvalidCastException
0x180014796  movups  xmm6, xmmword ptr [rax]
0x180014799  movd    eax, xmm6
0x18001479d  movups  [rbp+var_48], xmm6
0x1800147a1  cmp     al, 0FEh
0x1800147a3  jz      loc_1800148CF
0x1800147a9  mov     rcx, [rdi+8]
0x1800147ad  add     rcx, 14h
0x1800147b1  call    Timestamp_ToMicroseconds
0x1800147b6  mov     r10, rax
0x1800147b9  psrldq  xmm6, 8
0x1800147be  movq    r9, xmm6
0x1800147c3  mov     ecx, [r9+14h]
0x1800147c7  mov     r8d, [r9+18h]
0x1800147cb  mov     eax, [r9+24h]
0x1800147cf  lea     rdx, [rcx+rcx*2]
0x1800147d3  lea     rcx, [r8+rdx*8]
0x1800147d7  imul    rdx, rcx, 3Ch ; '<'
0x1800147db  mov     ecx, [r9+1Ch]
0x1800147df  add     rdx, rcx
0x1800147e2  mov     ecx, [r9+20h]
0x1800147e6  imul    r8, rdx, 3Ch ; '<'
0x1800147ea  add     r8, rcx
0x1800147ed  imul    rdx, r8, 0F4240h
0x1800147f4  add     rdx, rax
0x1800147f7  mov     rax, 0FFFFFFF5F123923Fh
0x180014801  cmp     r10, rax
0x180014804  jnz     short loc_180014877
0x180014806  mov     rax, 77E772392B50BDC0h
0x180014810  cmp     rdx, rax
0x180014813  jnz     short loc_180014875
0x180014815  xorps   xmm0, xmm0
0x180014818  lea     rcx, ModuleName; "mpunits.dll"
0x18001481f  movups  [rbp+var_38], xmm0
0x180014823  call    cs:__imp_GetModuleHandleA
0x180014829  mov     rcx, rax
0x18001482c  mov     edx, 7FFh
0x180014831  call    _Intlstr_GetString_LoadString
0x180014836  mov     qword ptr [rbp+var_38], rax
0x18001483a  lea     r9, [rbp+var_38]
0x18001483e  mov     byte ptr [rbp+var_38+8], 0
0x180014842  lea     rdx, aMi; "MI"
0x180014849  movaps  xmm0, [rbp+var_38]
0x18001484d  mov     r8d, 5
0x180014853  mov     [rsp+78h+var_50], 0; __int64
0x18001485c  movdqa  [rbp+var_38], xmm0
0x180014861  mov     [rsp+78h+var_58], 0; __int64
0x18001486a  lea     ecx, [r8-1]; int
0x18001486e  call    MI_ReportErrorDetails_ForCustomError
0x180014873  jmp     short loc_18001489D
0x180014875  xor     edx, edx
0x180014877  add     rdx, r10
0x18001487a  lea     rcx, [rbp+var_28]
0x18001487e  call    MintValue_CreateTimestampFromMicroseconds
0x180014883  mov     dil, [rax]
0x180014886  movsd   xmm6, qword ptr [rax+1]
0x18001488b  mov     esi, [rax+9]
0x18001488e  movzx   r14d, word ptr [rax+0Dh]
0x180014893  mov     r15b, [rax+0Fh]
0x180014897  cmp     dil, 0FEh
0x18001489b  jnz     short loc_1800148FE
0x18001489d  cmp     byte ptr [rbp+var_48], 0Ch
0x1800148a1  jl      short loc_1800148CF
0x1800148a3  test    dword ptr [rbp+var_48], 100h
0x1800148aa  jnz     short loc_1800148CF
0x1800148ac  mov     rcx, qword ptr [rbp+var_48+8]
0x1800148b0  mov     eax, [rcx]
0x1800148b2  cmp     eax, 0FFFFFFFFh
0x1800148b5  jz      short loc_1800148CF
0x1800148b7  sub     eax, 1
0x1800148ba  mov     [rcx], eax
0x1800148bc  jnz     short loc_1800148CF
0x1800148be  mov     rax, qword ptr [rbp+var_48+8]
0x1800148c2  lea     rcx, [rbp+var_48]
0x1800148c6  mov     rax, [rax+8]
0x1800148ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148cf  xor     edx, edx
0x1800148d1  xor     ecx, ecx
0x1800148d3  mov     eax, 0FFh
0x1800148d8  mov     [rbx+4], edx
0x1800148db  and     eax, 0FFFFFFFEh
0x1800148de  mov     [rbx+8], rcx
0x1800148e2  or      eax, 0FEh
0x1800148e7  mov     [rbx], eax
0x1800148e9  movaps  xmm6, [rsp+78h+var_18]
0x1800148ee  mov     rax, rbx
0x1800148f1  add     rsp, 78h
0x1800148f5  pop     r15
0x1800148f7  pop     r14
0x1800148f9  pop     rdi
0x1800148fa  pop     rsi
0x1800148fb  pop     rbx
0x1800148fc  pop     rbp
0x1800148fd  retn
0x1800148fe  cmp     byte ptr [rbp+var_48], 0Ch
0x180014902  jl      short loc_180014930
0x180014904  test    dword ptr [rbp+var_48], 100h
0x18001490b  jnz     short loc_180014930
0x18001490d  mov     rcx, qword ptr [rbp+var_48+8]
0x180014911  mov     eax, [rcx]
0x180014913  cmp     eax, 0FFFFFFFFh
0x180014916  jz      short loc_180014930
0x180014918  sub     eax, 1
0x18001491b  mov     [rcx], eax
0x18001491d  jnz     short loc_180014930
0x18001491f  mov     rax, qword ptr [rbp+var_48+8]
0x180014923  lea     rcx, [rbp+var_48]
0x180014927  mov     rax, [rax+8]
0x18001492b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014930  movsd   qword ptr [rbx+1], xmm6
0x180014935  mov     [rbx+9], esi
0x180014938  mov     [rbx+0Dh], r14w
0x18001493d  mov     [rbx+0Fh], r15b
0x180014941  mov     [rbx], dil
0x180014944  jmp     short loc_1800148E9
```
