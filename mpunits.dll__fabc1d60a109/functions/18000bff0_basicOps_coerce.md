# basicOps_coerce

- ea: `0x18000bff0`
- end: `0x18000c242`
- name: `basicOps_coerce`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000be30`
- `0x18000bff0`
- `0x18000db80`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c03a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c1c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c03a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c1c0`

## string_xrefs

- `0x18000c02f`: `mpunits.dll`
- `0x18000c1b5`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_coerce(__int64 a1, __int128 *a2, __int64 a3, __int128 *a4)
{
  bool v5; // zf
  HMODULE v8; // rax
  __int64 String_LoadString; // rax
  int v10; // ecx
  int v11; // eax
  __m128i v13; // xmm0
  __int64 v14; // r8
  __int64 v15; // r9
  char v16; // al
  __int128 v17; // xmm0
  __int128 *v18; // rax
  HMODULE ModuleHandleA; // rax
  __int64 (__fastcall *v20)(); // rdx
  __m128i v21; // [rsp+30h] [rbp-30h] BYREF
  __int128 v22; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-10h] BYREF

  *(_QWORD *)a1 = 271;
  *(_QWORD *)(a1 + 8) = 0;
  v5 = *(_BYTE *)a3 == 0xFC;
  v21 = (__m128i)0x10FuLL;
  if ( v5 )
  {
    v22 = *a4;
    v13 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v23, MintValue_CoerceToBoolean, &v22, 0);
    v21 = v13;
    v21.m128i_i8[0] = _mm_cvtsi128_si32(v13);
    if ( v21.m128i_i8[0] == -2 )
      goto LABEL_4;
    v14 = *(unsigned int *)(a3 + 8);
    v15 = 4294966294LL;
    v16 = _mm_cvtsi128_si32(_mm_srli_si128(v13, 8));
    if ( (_DWORD)v14 == -1002 )
    {
      if ( !v16 || (*(_DWORD *)a2 & 0x100) == 0 )
      {
        v20 = MintValue_CoerceToTimestamp;
        goto LABEL_30;
      }
    }
    else
    {
      v15 = 4294966295LL;
      if ( (_DWORD)v14 != -1001 )
      {
        if ( (_DWORD)v14 == -1 )
        {
          if ( *(_BYTE *)a2 != 15
            || (*(_DWORD *)a2 & 0x100) != 0
            || !((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL)) )
          {
            *(_QWORD *)a1 = 255;
            goto LABEL_5;
          }
          v22 = 0;
          ModuleHandleA = GetModuleHandleA("mpunits.dll");
          String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2067);
          v10 = 7;
          goto LABEL_3;
        }
        if ( v16 && (*(_DWORD *)a2 & 0x100) != 0 )
        {
          *(_QWORD *)&v22 = (unsigned __int8)v14 | 0x100LL;
LABEL_19:
          *((_QWORD *)&v22 + 1) = 0;
          v17 = (unsigned __int64)v22;
LABEL_20:
          *(_OWORD *)a1 = v17;
          goto LABEL_6;
        }
        v22 = *a2;
        v18 = (__int128 *)MintValue_Coerce(v23, &v22, v14);
LABEL_31:
        v17 = *v18;
        goto LABEL_20;
      }
      if ( !v16 || (*(_DWORD *)a2 & 0x100) == 0 )
      {
        v20 = MintValue_CoerceToInterval;
LABEL_30:
        v22 = *a2;
        v18 = (__int128 *)MintValue_CoerceAndRaiseInvalidCastException(v23, v20, &v22, v15);
        goto LABEL_31;
      }
    }
    *(_QWORD *)&v22 = 268;
    goto LABEL_19;
  }
  v22 = 0;
  v8 = GetModuleHandleA("mpunits.dll");
  String_LoadString = Intlstr_GetString_LoadString(v8, 2093);
  v10 = 4;
LABEL_3:
  *(_QWORD *)&v22 = String_LoadString;
  BYTE8(v22) = 0;
  MI_ReportErrorDetails_ForCustomError(v10, (int)L"MI", 0, 0);
LABEL_4:
  *(_DWORD *)(a1 + 4) = 0;
  *(_DWORD *)a1 = 254;
LABEL_5:
  *(_QWORD *)(a1 + 8) = 0;
LABEL_6:
  if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
  {
    v11 = *(_DWORD *)v21.m128i_i64[1] - 1;
    *(_DWORD *)v21.m128i_i64[1] = v11;
    if ( !v11 )
      (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
  }
  return a1;
}

```

## disassembly

```asm
0x18000bff0  push    rbp
0x18000bff2  push    rbx
0x18000bff3  push    rsi
0x18000bff4  push    r14
0x18000bff6  push    r15
0x18000bff8  mov     rbp, rsp
0x18000bffb  sub     rsp, 60h
0x18000bfff  xor     r15d, r15d
0x18000c002  mov     qword ptr [rcx], 10Fh
0x18000c009  mov     [rcx+8], r15
0x18000c00d  mov     r14, r8
0x18000c010  cmp     byte ptr [r8], 0FCh
0x18000c014  mov     rsi, rdx
0x18000c017  mov     rbx, rcx
0x18000c01a  mov     qword ptr [rbp+var_30], 10Fh
0x18000c022  mov     qword ptr [rbp+var_30+8], r15
0x18000c026  jz      loc_18000C0DB
0x18000c02c  xorps   xmm0, xmm0
0x18000c02f  lea     rcx, ModuleName; "mpunits.dll"
0x18000c036  movups  [rbp+var_20], xmm0
0x18000c03a  call    cs:__imp_GetModuleHandleA
0x18000c040  mov     rcx, rax
0x18000c043  mov     edx, 82Dh
0x18000c048  call    _Intlstr_GetString_LoadString
0x18000c04d  lea     r8d, [r15+5]
0x18000c051  lea     ecx, [r15+4]; int
0x18000c055  mov     qword ptr [rbp+var_20], rax
0x18000c059  lea     rdx, aMi; "MI"
0x18000c060  mov     byte ptr [rbp+var_20+8], r15b
0x18000c064  lea     r9, [rbp+var_20]
0x18000c068  movaps  xmm0, [rbp+var_20]
0x18000c06c  mov     [rsp+60h+var_38], r15; __int64
0x18000c071  movdqa  [rbp+var_20], xmm0
0x18000c076  mov     [rsp+60h+var_40], r15; __int64
0x18000c07b  call    MI_ReportErrorDetails_ForCustomError
0x18000c080  xor     edx, edx
0x18000c082  mov     eax, 0FFh
0x18000c087  and     eax, 0FFFFFFFEh
0x18000c08a  mov     [rbx+4], edx
0x18000c08d  xor     ecx, ecx
0x18000c08f  or      eax, 0FEh
0x18000c094  mov     [rbx], eax
0x18000c096  mov     [rbx+8], rcx
0x18000c09a  cmp     byte ptr [rbp+var_30], 0Ch
0x18000c09e  jl      short loc_18000C0CC
0x18000c0a0  test    dword ptr [rbp+var_30], 100h
0x18000c0a7  jnz     short loc_18000C0CC
0x18000c0a9  mov     rcx, qword ptr [rbp+var_30+8]
0x18000c0ad  mov     eax, [rcx]
0x18000c0af  cmp     eax, 0FFFFFFFFh
0x18000c0b2  jz      short loc_18000C0CC
0x18000c0b4  sub     eax, 1
0x18000c0b7  mov     [rcx], eax
0x18000c0b9  jnz     short loc_18000C0CC
0x18000c0bb  mov     rax, qword ptr [rbp+var_30+8]
0x18000c0bf  lea     rcx, [rbp+var_30]
0x18000c0c3  mov     rax, [rax+8]
0x18000c0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0cc  mov     rax, rbx
0x18000c0cf  add     rsp, 60h
0x18000c0d3  pop     r15
0x18000c0d5  pop     r14
0x18000c0d7  pop     rsi
0x18000c0d8  pop     rbx
0x18000c0d9  pop     rbp
0x18000c0da  retn
0x18000c0db  movups  xmm0, xmmword ptr [r9]
0x18000c0df  xor     r9d, r9d
0x18000c0e2  lea     r8, [rbp+var_20]
0x18000c0e6  lea     rdx, MintValue_CoerceToBoolean
0x18000c0ed  lea     rcx, [rbp+var_10]
0x18000c0f1  movdqu  [rbp+var_20], xmm0
0x18000c0f6  call    MintValue_CoerceAndRaiseInvalidCastException
0x18000c0fb  movups  xmm0, xmmword ptr [rax]
0x18000c0fe  movd    eax, xmm0
0x18000c102  movups  [rbp+var_30], xmm0
0x18000c106  mov     byte ptr [rbp+var_30], al
0x18000c109  cmp     al, 0FEh
0x18000c10b  jz      loc_18000C080
0x18000c111  mov     r8d, [r14+8]
0x18000c115  mov     r9d, 0FFFFFC16h
0x18000c11b  psrldq  xmm0, 8
0x18000c120  movd    eax, xmm0
0x18000c124  cmp     r8d, r9d
0x18000c127  jz      loc_18000C220
0x18000c12d  mov     r9d, 0FFFFFC17h
0x18000c133  cmp     r8d, r9d
0x18000c136  jz      loc_18000C1F0
0x18000c13c  cmp     r8d, 0FFFFFFFFh
0x18000c140  jz      short loc_18000C188
0x18000c142  test    al, al
0x18000c144  jz      short loc_18000C16E
0x18000c146  test    dword ptr [rsi], 100h
0x18000c14c  jz      short loc_18000C16E
0x18000c14e  movzx   eax, r8b
0x18000c152  bts     eax, 8
0x18000c156  mov     dword ptr [rbp+var_20+4], r15d
0x18000c15a  mov     dword ptr [rbp+var_20], eax
0x18000c15d  mov     qword ptr [rbp+var_20+8], r15
0x18000c161  movups  xmm0, [rbp+var_20]
0x18000c165  movdqu  xmmword ptr [rbx], xmm0
0x18000c169  jmp     loc_18000C09A
0x18000c16e  movups  xmm0, xmmword ptr [rsi]
0x18000c171  lea     rdx, [rbp+var_20]
0x18000c175  lea     rcx, [rbp+var_10]
0x18000c179  movdqu  [rbp+var_20], xmm0
0x18000c17e  call    MintValue_Coerce
0x18000c183  jmp     loc_18000C218
0x18000c188  cmp     byte ptr [rsi], 0Fh
0x18000c18b  jnz     short loc_18000C1E2
0x18000c18d  test    dword ptr [rsi], 100h
0x18000c193  jnz     short loc_18000C1E2
0x18000c195  mov     rcx, [rsi+8]
0x18000c199  mov     rax, cs:off_180047B90
0x18000c1a0  mov     rcx, [rcx+18h]
0x18000c1a4  mov     rax, [rax+8]
0x18000c1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ad  test    rax, rax
0x18000c1b0  jz      short loc_18000C1E2
0x18000c1b2  xorps   xmm0, xmm0
0x18000c1b5  lea     rcx, ModuleName; "mpunits.dll"
0x18000c1bc  movups  [rbp+var_20], xmm0
0x18000c1c0  call    cs:__imp_GetModuleHandleA
0x18000c1c6  mov     rcx, rax
0x18000c1c9  mov     edx, 813h
0x18000c1ce  call    _Intlstr_GetString_LoadString
0x18000c1d3  mov     r8d, 0Bh
0x18000c1d9  lea     ecx, [r8-4]
0x18000c1dd  jmp     loc_18000C055
0x18000c1e2  xor     ecx, ecx
0x18000c1e4  mov     qword ptr [rbx], 0FFh
0x18000c1eb  jmp     loc_18000C096
0x18000c1f0  test    al, al
0x18000c1f2  jz      short loc_18000C1FC
0x18000c1f4  test    dword ptr [rsi], 100h
0x18000c1fa  jnz     short loc_18000C22C
0x18000c1fc  lea     rdx, MintValue_CoerceToInterval
0x18000c203  movups  xmm0, xmmword ptr [rsi]
0x18000c206  lea     r8, [rbp+var_20]
0x18000c20a  lea     rcx, [rbp+var_10]
0x18000c20e  movdqu  [rbp+var_20], xmm0
0x18000c213  call    MintValue_CoerceAndRaiseInvalidCastException
0x18000c218  movups  xmm0, xmmword ptr [rax]
0x18000c21b  jmp     loc_18000C165
0x18000c220  test    al, al
0x18000c222  jz      short loc_18000C239
0x18000c224  test    dword ptr [rsi], 100h
0x18000c22a  jz      short loc_18000C239
0x18000c22c  mov     qword ptr [rbp+var_20], 10Ch
0x18000c234  jmp     loc_18000C15D
0x18000c239  lea     rdx, MintValue_CoerceToTimestamp
0x18000c240  jmp     short loc_18000C203
```
