# subtract_interval

- ea: `0x180016d50`
- end: `0x180016f6f`
- name: `subtract_interval`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800149b0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000be30`
- `0x180010080`
- `0x180016d50`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180016e49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180016e49`

## string_xrefs

- `0x180016e3e`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall subtract_interval(__int64 a1, __int64 a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __m128i v6; // xmm0
  unsigned int *v7; // r8
  unsigned int *v8; // xmm0_8
  __int64 v9; // r9
  __int64 v10; // rdx
  HMODULE ModuleHandleA; // rax
  __int64 IntervalFromMicroseconds; // rax
  char v13; // di
  __int64 v14; // xmm6_8
  int v15; // esi
  __int16 v16; // r14
  char v17; // r15
  int v18; // eax
  int v20; // eax
  __m128i v21; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-28h] BYREF

  v3 = *a3;
  v21 = (__m128i)0x10FuLL;
  v22 = v3;
  v6 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException(v23, MintValue_CoerceToInterval, &v22, 4294966295LL);
  v21 = v6;
  if ( (unsigned __int8)_mm_cvtsi128_si32(v6) == 0xFE )
  {
LABEL_12:
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  v7 = *(unsigned int **)(a2 + 8);
  v8 = (unsigned int *)_mm_srli_si128(v6, 8).m128i_u64[0];
  v9 = v7[9] + 1000000 * (v7[8] + 60 * (v7[7] + 60 * (v7[6] + 24LL * v7[5])));
  v10 = v8[9] + 1000000 * (v8[8] + 60 * (v8[7] + 60 * (v8[6] + 24LL * v8[5])));
  if ( v9 == 8639999999999000000LL )
  {
    if ( v10 == 8639999999999000000LL )
    {
      v22 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v22 = Intlstr_GetString_LoadString(ModuleHandleA, 2055);
      BYTE8(v22) = 0;
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
LABEL_7:
      if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
      {
        v18 = *(_DWORD *)v21.m128i_i64[1] - 1;
        *(_DWORD *)v21.m128i_i64[1] = v18;
        if ( !v18 )
          (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
      }
      goto LABEL_12;
    }
    v10 = 0;
  }
  IntervalFromMicroseconds = MintValue_CreateIntervalFromMicroseconds((__int64)v23, v9 - v10);
  v13 = *(_BYTE *)IntervalFromMicroseconds;
  v14 = *(_QWORD *)(IntervalFromMicroseconds + 1);
  v15 = *(_DWORD *)(IntervalFromMicroseconds + 9);
  v16 = *(_WORD *)(IntervalFromMicroseconds + 13);
  v17 = *(_BYTE *)(IntervalFromMicroseconds + 15);
  if ( *(_BYTE *)IntervalFromMicroseconds == 0xFE )
    goto LABEL_7;
  if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
  {
    v20 = *(_DWORD *)v21.m128i_i64[1] - 1;
    *(_DWORD *)v21.m128i_i64[1] = v20;
    if ( !v20 )
      (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
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
0x180016d50  push    rbp
0x180016d52  push    rbx
0x180016d53  push    rsi
0x180016d54  push    rdi
0x180016d55  push    r14
0x180016d57  push    r15
0x180016d59  mov     rbp, rsp
0x180016d5c  sub     rsp, 78h
0x180016d60  movups  xmm0, xmmword ptr [r8]
0x180016d64  mov     rdi, rdx
0x180016d67  mov     rbx, rcx
0x180016d6a  lea     r8, [rbp+var_38]
0x180016d6e  movaps  [rsp+78h+var_18], xmm6
0x180016d73  mov     r9d, 0FFFFFC17h
0x180016d79  mov     qword ptr [rbp+var_48], 10Fh
0x180016d81  lea     rdx, MintValue_CoerceToInterval
0x180016d88  mov     qword ptr [rbp+var_48+8], 0
0x180016d90  lea     rcx, [rbp+var_28]
0x180016d94  movdqu  [rbp+var_38], xmm0
0x180016d99  call    MintValue_CoerceAndRaiseInvalidCastException
0x180016d9e  movups  xmm0, xmmword ptr [rax]
0x180016da1  movd    eax, xmm0
0x180016da5  movups  [rbp+var_48], xmm0
0x180016da9  cmp     al, 0FEh
0x180016dab  jz      loc_180016EF8
0x180016db1  mov     r8, [rdi+8]
0x180016db5  psrldq  xmm0, 8
0x180016dba  mov     eax, [r8+14h]
0x180016dbe  lea     rcx, [rax+rax*2]
0x180016dc2  mov     eax, [r8+18h]
0x180016dc6  lea     rcx, [rax+rcx*8]
0x180016dca  mov     eax, [r8+1Ch]
0x180016dce  imul    rdx, rcx, 3Ch ; '<'
0x180016dd2  add     rdx, rax
0x180016dd5  mov     eax, [r8+20h]
0x180016dd9  imul    rcx, rdx, 3Ch ; '<'
0x180016ddd  add     rcx, rax
0x180016de0  mov     eax, [r8+24h]
0x180016de4  imul    r9, rcx, 0F4240h
0x180016deb  movq    r8, xmm0
0x180016df0  add     r9, rax
0x180016df3  mov     eax, [r8+14h]
0x180016df7  lea     rcx, [rax+rax*2]
0x180016dfb  mov     eax, [r8+18h]
0x180016dff  lea     rcx, [rax+rcx*8]
0x180016e03  mov     eax, [r8+1Ch]
0x180016e07  imul    rdx, rcx, 3Ch ; '<'
0x180016e0b  add     rdx, rax
0x180016e0e  mov     eax, [r8+20h]
0x180016e12  imul    rcx, rdx, 3Ch ; '<'
0x180016e16  add     rcx, rax
0x180016e19  mov     eax, [r8+24h]
0x180016e1d  imul    rdx, rcx, 0F4240h
0x180016e24  add     rdx, rax
0x180016e27  mov     rax, 77E772392B50BDC0h
0x180016e31  cmp     r9, rax
0x180016e34  jnz     short loc_180016E9D
0x180016e36  cmp     rdx, rax
0x180016e39  jnz     short loc_180016E9B
0x180016e3b  xorps   xmm0, xmm0
0x180016e3e  lea     rcx, ModuleName; "mpunits.dll"
0x180016e45  movups  [rbp+var_38], xmm0
0x180016e49  call    cs:__imp_GetModuleHandleA
0x180016e4f  mov     rcx, rax
0x180016e52  mov     edx, 807h
0x180016e57  call    _Intlstr_GetString_LoadString
0x180016e5c  mov     qword ptr [rbp+var_38], rax
0x180016e60  lea     r9, [rbp+var_38]
0x180016e64  mov     byte ptr [rbp+var_38+8], 0
0x180016e68  lea     rdx, aMi; "MI"
0x180016e6f  movaps  xmm0, [rbp+var_38]
0x180016e73  mov     r8d, 5
0x180016e79  mov     [rsp+78h+var_50], 0; __int64
0x180016e82  movdqa  [rbp+var_38], xmm0
0x180016e87  mov     [rsp+78h+var_58], 0; __int64
0x180016e90  lea     ecx, [r8-1]; int
0x180016e94  call    MI_ReportErrorDetails_ForCustomError
0x180016e99  jmp     short loc_180016EC6
0x180016e9b  xor     edx, edx
0x180016e9d  sub     r9, rdx
0x180016ea0  lea     rcx, [rbp+var_28]
0x180016ea4  mov     rdx, r9
0x180016ea7  call    MintValue_CreateIntervalFromMicroseconds
0x180016eac  mov     dil, [rax]
0x180016eaf  movsd   xmm6, qword ptr [rax+1]
0x180016eb4  mov     esi, [rax+9]
0x180016eb7  movzx   r14d, word ptr [rax+0Dh]
0x180016ebc  mov     r15b, [rax+0Fh]
0x180016ec0  cmp     dil, 0FEh
0x180016ec4  jnz     short loc_180016F27
0x180016ec6  cmp     byte ptr [rbp+var_48], 0Ch
0x180016eca  jl      short loc_180016EF8
0x180016ecc  test    dword ptr [rbp+var_48], 100h
0x180016ed3  jnz     short loc_180016EF8
0x180016ed5  mov     rcx, qword ptr [rbp+var_48+8]
0x180016ed9  mov     eax, [rcx]
0x180016edb  cmp     eax, 0FFFFFFFFh
0x180016ede  jz      short loc_180016EF8
0x180016ee0  sub     eax, 1
0x180016ee3  mov     [rcx], eax
0x180016ee5  jnz     short loc_180016EF8
0x180016ee7  mov     rax, qword ptr [rbp+var_48+8]
0x180016eeb  lea     rcx, [rbp+var_48]
0x180016eef  mov     rax, [rax+8]
0x180016ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ef8  xor     edx, edx
0x180016efa  xor     ecx, ecx
0x180016efc  mov     eax, 0FFh
0x180016f01  mov     [rbx+4], edx
0x180016f04  and     eax, 0FFFFFFFEh
0x180016f07  mov     [rbx+8], rcx
0x180016f0b  or      eax, 0FEh
0x180016f10  mov     [rbx], eax
0x180016f12  movaps  xmm6, [rsp+78h+var_18]
0x180016f17  mov     rax, rbx
0x180016f1a  add     rsp, 78h
0x180016f1e  pop     r15
0x180016f20  pop     r14
0x180016f22  pop     rdi
0x180016f23  pop     rsi
0x180016f24  pop     rbx
0x180016f25  pop     rbp
0x180016f26  retn
0x180016f27  cmp     byte ptr [rbp+var_48], 0Ch
0x180016f2b  jl      short loc_180016F59
0x180016f2d  test    dword ptr [rbp+var_48], 100h
0x180016f34  jnz     short loc_180016F59
0x180016f36  mov     rcx, qword ptr [rbp+var_48+8]
0x180016f3a  mov     eax, [rcx]
0x180016f3c  cmp     eax, 0FFFFFFFFh
0x180016f3f  jz      short loc_180016F59
0x180016f41  sub     eax, 1
0x180016f44  mov     [rcx], eax
0x180016f46  jnz     short loc_180016F59
0x180016f48  mov     rax, qword ptr [rbp+var_48+8]
0x180016f4c  lea     rcx, [rbp+var_48]
0x180016f50  mov     rax, [rax+8]
0x180016f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f59  movsd   qword ptr [rbx+1], xmm6
0x180016f5e  mov     [rbx+9], esi
0x180016f61  mov     [rbx+0Dh], r14w
0x180016f66  mov     [rbx+0Fh], r15b
0x180016f6a  mov     [rbx], dil
0x180016f6d  jmp     short loc_180016F12
```
