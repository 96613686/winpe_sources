# FIStreamSetFileInfo

- ea: `0x14001334c`
- end: `0x140013553`
- name: `FIStreamSetFileInfo`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14001313c`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x1400033f0`
- `0x14001334c`
- `0x140013fb0`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x140013542`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013542`
- `FLTMGR!FltReferenceFileNameInformation` at `0x1400134f1`
- `FLTMGR!FltReferenceFileNameInformation` at `0x1400134f1`

## pseudocode

```c
__int64 __fastcall FIStreamSetFileInfo(__m128i *a1, __m128i *a2, int a3)
{
  __m128i v6; // xmm2
  __int64 v7; // xmm3_8
  __m128i v8; // xmm0
  unsigned __int64 v9; // rcx
  __int64 v10; // xmm1_8
  unsigned int v11; // ebx
  __int64 *v13; // rcx
  __m128i v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+30h] [rbp-40h]
  int v16; // [rsp+38h] [rbp-38h] BYREF
  int v17; // [rsp+3Ch] [rbp-34h]
  __int64 v18; // [rsp+40h] [rbp-30h]
  __m128i *v19; // [rsp+48h] [rbp-28h]
  int v20; // [rsp+50h] [rbp-20h]
  int v21; // [rsp+54h] [rbp-1Ch]
  __m128i *v22; // [rsp+58h] [rbp-18h]
  __int64 v23; // [rsp+60h] [rbp-10h]

  v21 = 0;
  v14 = 0;
  v15 = 0;
  FILockSharedAcquire(&qword_140009A78);
  if ( dword_140009A70 != 1 )
  {
    v11 = -1073741431;
LABEL_16:
    FILockExclusiveRelease(&qword_140009A78);
    return v11;
  }
  FILockExclusiveAcquire(&a1[2].m128i_u64[1]);
  if ( a3 != a1[4].m128i_i32[0] )
  {
    v13 = &a1[2].m128i_i64[1];
    v11 = -1073741267;
    FILockExclusiveRelease(v13);
    goto LABEL_16;
  }
  v7 = a2[1].m128i_i64[0];
  v8 = a1[3];
  v14 = *a2;
  v6 = v14;
  *a2 = v8;
  a2[1].m128i_i64[0] = a1[4].m128i_i64[0];
  v9 = _mm_srli_si128(v6, 8).m128i_u64[0];
  v15 = v7;
  a1[3].m128i_i64[0] = v6.m128i_i64[0];
  a1[3].m128i_i32[3] = HIDWORD(v9);
  a1[4].m128i_i32[0] = v7;
  if ( (v9 & 4) != 0 )
  {
    FIStreamVolatileBitFieldBitSet(a1, 2, 1);
    LOBYTE(v9) = v14.m128i_i8[8];
  }
  if ( (v9 & 8) != 0 )
    FIStreamVolatileBitFieldBitSet(a1, 3, 1);
  if ( v6.m128i_i64[0] )
  {
    FIStreamVolatileBitFieldBitSet(a1, 0, 0);
    FltReferenceFileNameInformation((PFLT_FILE_NAME_INFORMATION)v6.m128i_i64[0]);
  }
  v10 = a1[4].m128i_i64[0];
  v14 = a1[3];
  v15 = v10;
  FILockExclusiveRelease(&a1[2].m128i_u64[1]);
  FILockExclusiveRelease(&qword_140009A78);
  if ( a2[1].m128i_i32[0] != (_DWORD)v10 )
  {
    v16 = dword_140009A74;
    v18 = 0;
    v17 = 0;
    v19 = a1;
    v20 = 3;
    v22 = a2;
    v23 = 0;
    FIStreamLog((__int64)&v16);
  }
  v16 = dword_140009A74;
  v22 = &v14;
  v18 = 0;
  v17 = 0;
  v19 = a1;
  v20 = 2;
  v23 = 0;
  FIStreamLog((__int64)&v16);
  v11 = 0;
  if ( v6.m128i_i64[0] )
    FltReleaseFileNameInformation((PFLT_FILE_NAME_INFORMATION)v6.m128i_i64[0]);
  return v11;
}

```

## disassembly

```asm
0x14001334c  push    rbp
0x14001334e  push    rbx
0x14001334f  push    rsi
0x140013350  push    rdi
0x140013351  push    r14
0x140013353  mov     rbp, rsp
0x140013356  sub     rsp, 70h
0x14001335a  mov     rbx, rcx
0x14001335d  mov     [rbp+var_1C], 0
0x140013364  xorps   xmm0, xmm0
0x140013367  lea     rcx, qword_140009A78
0x14001336e  xor     eax, eax
0x140013370  mov     edi, r8d
0x140013373  movups  [rbp+var_50], xmm0
0x140013377  mov     [rbp+var_40], rax
0x14001337b  mov     r14, rdx
0x14001337e  call    FILockSharedAcquire
0x140013383  cmp     cs:dword_140009A70, 1
0x14001338a  jnz     loc_140013490
0x140013390  lea     rsi, [rbx+28h]
0x140013394  mov     rcx, rsi
0x140013397  call    FILockExclusiveAcquire
0x14001339c  cmp     edi, [rbx+40h]
0x14001339f  jnz     loc_140013497
0x1400133a5  movups  xmm2, xmmword ptr [r14]
0x1400133a9  movsd   xmm3, qword ptr [r14+10h]
0x1400133af  movups  xmm0, xmmword ptr [rbx+30h]
0x1400133b3  movups  [rbp+var_50], xmm2
0x1400133b7  movups  xmmword ptr [r14], xmm0
0x1400133bb  movsd   xmm1, qword ptr [rbx+40h]
0x1400133c0  movq    rdi, xmm2
0x1400133c5  movsd   qword ptr [r14+10h], xmm1
0x1400133cb  psrldq  xmm2, 8
0x1400133d0  movq    rcx, xmm2
0x1400133d5  movsd   [rbp+var_40], xmm3
0x1400133da  mov     rax, rcx
0x1400133dd  mov     [rbx+30h], rdi
0x1400133e1  shr     rax, 20h
0x1400133e5  mov     [rbx+3Ch], eax
0x1400133e8  movss   dword ptr [rbx+40h], xmm3
0x1400133ed  test    cl, 4
0x1400133f0  jnz     loc_1400134B2
0x1400133f6  test    cl, 8
0x1400133f9  jnz     loc_1400134CB
0x1400133ff  test    rdi, rdi
0x140013402  jnz     loc_1400134E1
0x140013408  movups  xmm0, xmmword ptr [rbx+30h]
0x14001340c  mov     rcx, rsi
0x14001340f  movsd   xmm1, qword ptr [rbx+40h]
0x140013414  movups  [rbp+var_50], xmm0
0x140013418  movsd   [rbp+var_40], xmm1
0x14001341d  call    FILockExclusiveRelease
0x140013422  lea     rcx, qword_140009A78
0x140013429  call    FILockExclusiveRelease
0x14001342e  mov     eax, dword ptr [rbp+var_40]
0x140013431  cmp     [r14+10h], eax
0x140013435  jnz     loc_140013502
0x14001343b  mov     eax, cs:dword_140009A74
0x140013441  lea     rcx, [rbp+var_38]
0x140013445  mov     [rbp+var_38], eax
0x140013448  lea     rax, [rbp+var_50]
0x14001344c  mov     [rbp+var_18], rax
0x140013450  mov     [rbp+var_30], 0
0x140013458  mov     [rbp+var_34], 0
0x14001345f  mov     [rbp+var_28], rbx
0x140013463  mov     [rbp+var_20], 2
0x14001346a  mov     [rbp+var_10], 0
0x140013472  call    FIStreamLog
0x140013477  xor     ebx, ebx
0x140013479  test    rdi, rdi
0x14001347c  jnz     loc_14001353F
0x140013482  mov     eax, ebx
0x140013484  add     rsp, 70h
0x140013488  pop     r14
0x14001348a  pop     rdi
0x14001348b  pop     rsi
0x14001348c  pop     rbx
0x14001348d  pop     rbp
0x14001348e  retn
0x140013490  mov     ebx, 0C0000189h
0x140013495  jmp     short loc_1400134A4
0x140013497  mov     rcx, rsi
0x14001349a  mov     ebx, 0C000022Dh
0x14001349f  call    FILockExclusiveRelease
0x1400134a4  lea     rcx, qword_140009A78
0x1400134ab  call    FILockExclusiveRelease
0x1400134b0  jmp     short loc_140013482
0x1400134b2  mov     edx, 2
0x1400134b7  mov     rcx, rbx
0x1400134ba  lea     r8d, [rdx-1]
0x1400134be  call    FIStreamVolatileBitFieldBitSet
0x1400134c3  mov     ecx, dword ptr [rbp+var_50+8]
0x1400134c6  jmp     loc_1400133F6
0x1400134cb  mov     edx, 3
0x1400134d0  mov     rcx, rbx
0x1400134d3  lea     r8d, [rdx-2]
0x1400134d7  call    FIStreamVolatileBitFieldBitSet
0x1400134dc  jmp     loc_1400133FF
0x1400134e1  xor     r8d, r8d
0x1400134e4  xor     edx, edx
0x1400134e6  mov     rcx, rbx
0x1400134e9  call    FIStreamVolatileBitFieldBitSet
0x1400134ee  mov     rcx, rdi; FileNameInformation
0x1400134f1  call    cs:__imp_FltReferenceFileNameInformation
0x1400134f8  nop     dword ptr [rax+rax+00h]
0x1400134fd  jmp     loc_140013408
0x140013502  mov     eax, cs:dword_140009A74
0x140013508  lea     rcx, [rbp+var_38]
0x14001350c  mov     [rbp+var_38], eax
0x14001350f  mov     [rbp+var_30], 0
0x140013517  mov     [rbp+var_34], 0
0x14001351e  mov     [rbp+var_28], rbx
0x140013522  mov     [rbp+var_20], 3
0x140013529  mov     [rbp+var_18], r14
0x14001352d  mov     [rbp+var_10], 0
0x140013535  call    FIStreamLog
0x14001353a  jmp     loc_14001343B
0x14001353f  mov     rcx, rdi; FileNameInformation
0x140013542  call    cs:__imp_FltReleaseFileNameInformation
0x140013549  nop     dword ptr [rax+rax+00h]
0x14001354e  jmp     loc_140013482
```
