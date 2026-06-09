# GetMatchingAxisValueRecords<array_ref<GDI::StatAxis const>,array_ref<GDI::MatchingAxisValueRecord>>(array_ref<DWRITE_FONT_AXIS_VALUE_FIXED const>,array_ref<GDI::StatAxis const>,array_ref<GDI::MatchingAxisValueRecord> &)

- ea: `0x1400069e8`
- end: `0x140006c84`
- name: `??$GetMatchingAxisValueRecords@V?$array_ref@$$CBUStatAxis@GDI@@@@V?$array_ref@UMatchingAxisValueRecord@GDI@@@@@@YAXV?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE_FIXED@@@@V?$array_ref@$$CBUStatAxis@GDI@@@@AEAV?$array_ref@UMatchingAxisValueRecord@GDI@@@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140005ce8`

## callees

- `0x1400069e8`
- `0x140054c04`
- `0x140059bec`
- `0x14005d26c`
- `0x14005dedc`
- `0x140075de0`
- `0x14007680c`
- `0x140076f0e`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006bd5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006bd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GetMatchingAxisValueRecords<array_ref<GDI::StatAxis const>,array_ref<GDI::MatchingAxisValueRecord>>(
        _DWORD **a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rsi
  __int64 v9; // rax
  unsigned int *v10; // r11
  unsigned int *v11; // rbp
  __int64 v12; // r12
  _DWORD *i; // rax
  signed int v14; // edx
  signed int v15; // ecx
  int *v16; // r10
  int v17; // r9d
  int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r11
  __int64 v22; // rax
  unsigned int *v23; // r8
  unsigned int *v24; // r10
  unsigned int *j; // r9
  _OWORD *v26; // rdx
  _OWORD *k; // rax
  __int64 v28; // rcx
  _OWORD *m; // rcx
  signed int v30; // [rsp+20h] [rbp-98h] BYREF
  int pExceptionObject; // [rsp+28h] [rbp-90h] BYREF
  unsigned int *v32; // [rsp+30h] [rbp-88h]
  void *v33[8]; // [rsp+40h] [rbp-78h] BYREF

  v6 = a3[1];
  v7 = *a3;
  if ( v7 != v6 )
  {
    do
    {
      v8 = 0;
      v9 = *(_QWORD *)(v7 + 16);
      v10 = *(unsigned int **)(v9 + 8);
      v11 = *(unsigned int **)(v9 + 16);
      if ( v10 != v11 )
      {
        v12 = *a2;
        do
        {
          for ( i = *a1; i != a1[1]; i += 2 )
          {
            if ( *i == *(_DWORD *)(v12 + 8LL * *v10) )
            {
              v14 = i[1];
              goto LABEL_8;
            }
          }
          v14 = 0;
LABEL_8:
          v30 = v14;
          v15 = v10[3];
          v16 = &v30;
          if ( v15 < v14 )
            v16 = (int *)(v10 + 3);
          v17 = v10[2];
          if ( v15 >= v14 )
            v15 = v14;
          if ( v15 >= v17 )
            v17 = *v16;
          if ( v14 == 0x7FFFFFFF )
          {
            v18 = 0x80000000;
          }
          else if ( v14 == 0x80000000 )
          {
            v18 = 0x7FFFFFFF;
          }
          else
          {
            v18 = -v14;
          }
          if ( (unsigned int)(v17 + 0x7FFFFFFF) <= 0xFFFFFFFD )
          {
            if ( (unsigned int)(v18 + 0x7FFFFFFF) <= 0xFFFFFFFD )
              v18 = Fixed16_16::SaturateToInfinity(v17 - (__int64)v14);
          }
          else
          {
            v18 = v17;
          }
          v8 += ((unsigned __int64)(unsigned int)v18 >> 31) + 2 * ((v18 * (__int64)v18) >> 16);
          v10 += 4;
        }
        while ( v10 != v11 );
      }
      *(_QWORD *)(v7 + 8) = v8;
      v7 += 32;
    }
    while ( v7 != v6 );
    LOBYTE(v7) = 0;
    std::stable_sort<GDI::MatchingAxisValueRecord *,std::less<void>>(*a3, a3[1], v7);
    v19 = (a2[1] - *a2) >> 3;
    ScopedArray<bool,20>::ScopedArray<bool,20>(v33, (unsigned int)v19);
    memset_0(v33[0], 0, (char *)v33[1] - (char *)v33[0]);
    v20 = *a3;
    v21 = a3[1];
    while ( v20 != v21 )
    {
      v22 = *(_QWORD *)(v20 + 16);
      v23 = *(unsigned int **)(v22 + 8);
      v24 = *(unsigned int **)(v22 + 16);
      for ( j = v23; j != v24; j += 4 )
      {
        if ( *j >= (unsigned int)v19 )
        {
          pExceptionObject = -2147024809;
          v32 = j;
          throw (InvalidCacheDataException *)&pExceptionObject;
        }
        if ( *((_BYTE *)v33[0] + *j) )
        {
          *(_BYTE *)v20 |= 2u;
          goto LABEL_29;
        }
      }
      while ( v23 != v24 )
      {
        *((_BYTE *)v33[0] + *v23) = 1;
        v23 += 4;
      }
LABEL_29:
      v20 += 32;
    }
    v26 = (_OWORD *)a3[1];
    for ( k = (_OWORD *)*a3; k != v26 && (*(_BYTE *)k & 2) == 0; k += 2 )
      ;
    if ( k != v26 )
    {
      for ( m = k + 2; m != v26; m += 2 )
      {
        if ( (*(_BYTE *)m & 2) == 0 )
        {
          *k = *m;
          k[1] = m[1];
          k += 2;
        }
      }
    }
    v28 = *a3;
    *a3 = *a3;
    a3[1] = (((unsigned __int64)k - v28) & 0xFFFFFFFFFFFFFFE0uLL) + v28;
    std::stable_sort<GDI::MatchingAxisValueRecord *,bool (*)(GDI::MatchingAxisValueRecord const &,GDI::MatchingAxisValueRecord const &)>(v28);
    free(v33[2]);
  }
}

```

## disassembly

```asm
0x1400069e8  mov     [rsp+arg_0], rbx
0x1400069ed  mov     [rsp+arg_18], rbp
0x1400069f2  push    rsi
0x1400069f3  push    rdi
0x1400069f4  push    r12
0x1400069f6  push    r14
0x1400069f8  push    r15
0x1400069fa  sub     rsp, 90h
0x140006a01  mov     rax, cs:__security_cookie
0x140006a08  xor     rax, rsp
0x140006a0b  mov     [rsp+0B8h+var_38], rax
0x140006a13  mov     rbx, r8
0x140006a16  mov     r14, rdx
0x140006a19  mov     r15, rcx
0x140006a1c  mov     rdi, [r8+8]
0x140006a20  mov     r8, [r8]
0x140006a23  cmp     r8, rdi
0x140006a26  jz      loc_140006BDB
0x140006a2c  xor     esi, esi
0x140006a2e  mov     rax, [r8+10h]
0x140006a32  mov     r11, [rax+8]
0x140006a36  mov     rbp, [rax+10h]
0x140006a3a  cmp     r11, rbp
0x140006a3d  jz      loc_140006ADD
0x140006a43  mov     r12, [r14]
0x140006a46  mov     eax, [r11]
0x140006a49  mov     ecx, [r12+rax*8]
0x140006a4d  mov     rax, [r15]
0x140006a50  cmp     rax, [r15+8]
0x140006a54  jz      loc_140006B3E
0x140006a5a  cmp     [rax], ecx
0x140006a5c  jnz     loc_140006B35
0x140006a62  mov     edx, [rax+4]
0x140006a65  mov     [rsp+0B8h+var_98], edx
0x140006a69  lea     rax, [r11+0Ch]
0x140006a6d  mov     ecx, [rax]
0x140006a6f  lea     r10, [rsp+0B8h+var_98]
0x140006a74  cmp     ecx, edx
0x140006a76  cmovl   r10, rax
0x140006a7a  mov     r9d, [r11+8]
0x140006a7e  cmovge  ecx, edx
0x140006a81  cmp     ecx, r9d
0x140006a84  jl      short loc_140006A89
0x140006a86  mov     r9d, [r10]
0x140006a89  cmp     edx, 7FFFFFFFh
0x140006a8f  jz      loc_140006C07
0x140006a95  cmp     edx, 80000000h
0x140006a9b  jz      loc_140006C5B
0x140006aa1  mov     eax, edx
0x140006aa3  neg     eax
0x140006aa5  lea     ecx, [r9+7FFFFFFFh]
0x140006aac  cmp     ecx, 0FFFFFFFDh
0x140006aaf  jbe     loc_140006C39
0x140006ab5  mov     eax, r9d
0x140006ab8  movsxd  rdx, eax
0x140006abb  imul    rdx, rdx
0x140006abf  sar     rdx, 10h
0x140006ac3  mov     ecx, eax
0x140006ac5  shr     rcx, 1Fh
0x140006ac9  add     rcx, rsi
0x140006acc  lea     rsi, [rcx+rdx*2]
0x140006ad0  add     r11, 10h
0x140006ad4  cmp     r11, rbp
0x140006ad7  jnz     loc_140006A46
0x140006add  mov     [r8+8], rsi
0x140006ae1  add     r8, 20h ; ' '
0x140006ae5  cmp     r8, rdi
0x140006ae8  jnz     loc_140006A2C
0x140006aee  xor     r8b, r8b
0x140006af1  mov     rdx, [rbx+8]
0x140006af5  mov     rcx, [rbx]
0x140006af8  call    ??$stable_sort@PEAUMatchingAxisValueRecord@GDI@@U?$less@X@std@@@std@@YAXQEAUMatchingAxisValueRecord@GDI@@0U?$less@X@0@@Z; std::stable_sort<GDI::MatchingAxisValueRecord *,std::less<void>>(GDI::MatchingAxisValueRecord * const,GDI::MatchingAxisValueRecord * const,std::less<void>)
0x140006afd  mov     rdi, [r14+8]
0x140006b01  sub     rdi, [r14]
0x140006b04  sar     rdi, 3
0x140006b08  mov     edx, edi
0x140006b0a  lea     rcx, [rsp+0B8h+var_78]
0x140006b0f  call    ??0?$ScopedArray@_N$0BE@@@QEAA@_K@Z; ScopedArray<bool,20>::ScopedArray<bool,20>(unsigned __int64)
0x140006b14  nop
0x140006b15  mov     r8, [rsp+0B8h+var_70]
0x140006b1a  mov     rcx, [rsp+0B8h+var_78]; void *
0x140006b1f  sub     r8, rcx; Size
0x140006b22  xor     edx, edx; Val
0x140006b24  call    memset_0
0x140006b29  mov     rdx, [rbx]
0x140006b2c  mov     r11, [rbx+8]
0x140006b30  mov     sil, 2
0x140006b33  jmp     short loc_140006B77
0x140006b35  add     rax, 8
0x140006b39  jmp     loc_140006A50
0x140006b3e  xor     edx, edx
0x140006b40  jmp     loc_140006A65
0x140006b45  mov     rax, [rdx+10h]
0x140006b49  mov     r8, [rax+8]
0x140006b4d  mov     r10, [rax+10h]
0x140006b51  mov     r9, r8
0x140006b54  cmp     r9, r10
0x140006b57  jz      short loc_140006B95
0x140006b59  cmp     [r9], edi
0x140006b5c  jnb     loc_140006C65
0x140006b62  mov     ecx, [r9]
0x140006b65  mov     rax, [rsp+0B8h+var_78]
0x140006b6a  cmp     byte ptr [rcx+rax], 0
0x140006b6e  jz      short loc_140006B9C
0x140006b70  or      [rdx], sil
0x140006b73  add     rdx, 20h ; ' '
0x140006b77  cmp     rdx, r11
0x140006b7a  jnz     short loc_140006B45
0x140006b7c  mov     rdx, [rbx+8]
0x140006b80  mov     rax, [rbx]
0x140006b83  jmp     short loc_140006BAB
0x140006b85  mov     ecx, [r8]
0x140006b88  mov     rax, [rsp+0B8h+var_78]
0x140006b8d  mov     byte ptr [rcx+rax], 1
0x140006b91  add     r8, 10h
0x140006b95  cmp     r8, r10
0x140006b98  jz      short loc_140006B73
0x140006b9a  jmp     short loc_140006B85
0x140006b9c  add     r9, 10h
0x140006ba0  jmp     short loc_140006B54
0x140006ba2  test    [rax], sil
0x140006ba5  jnz     short loc_140006BB0
0x140006ba7  add     rax, 20h ; ' '
0x140006bab  cmp     rax, rdx
0x140006bae  jnz     short loc_140006BA2
0x140006bb0  cmp     rax, rdx
0x140006bb3  jnz     short loc_140006C11
0x140006bb5  mov     rcx, [rbx]
0x140006bb8  mov     [rbx], rcx
0x140006bbb  sub     rax, rcx
0x140006bbe  and     rax, 0FFFFFFFFFFFFFFE0h
0x140006bc2  lea     rdx, [rax+rcx]
0x140006bc6  mov     [rbx+8], rdx
0x140006bca  call    ??$stable_sort@PEAUMatchingAxisValueRecord@GDI@@P6A_NAEBU12@0@Z@std@@YAXQEAUMatchingAxisValueRecord@GDI@@0P6A_NAEBU12@1@Z@Z; std::stable_sort<GDI::MatchingAxisValueRecord *,bool (*)(GDI::MatchingAxisValueRecord const &,GDI::MatchingAxisValueRecord const &)>(GDI::MatchingAxisValueRecord * const,GDI::MatchingAxisValueRecord * const,bool (*)(GDI::MatchingAxisValueRecord const &,GDI::MatchingAxisValueRecord const &))
0x140006bcf  nop
0x140006bd0  mov     rcx, [rsp+0B8h+Block]; Block
0x140006bd5  call    cs:__imp_free
0x140006bdb  mov     rcx, [rsp+0B8h+var_38]
0x140006be3  xor     rcx, rsp; StackCookie
0x140006be6  call    __security_check_cookie
0x140006beb  lea     r11, [rsp+0B8h+var_28]
0x140006bf3  mov     rbx, [r11+30h]
0x140006bf7  mov     rbp, [r11+48h]
0x140006bfb  mov     rsp, r11
0x140006bfe  pop     r15
0x140006c00  pop     r14
0x140006c02  pop     r12
0x140006c04  pop     rdi
0x140006c05  pop     rsi
0x140006c06  retn
0x140006c07  mov     eax, 80000000h
0x140006c0c  jmp     loc_140006AA5
0x140006c11  lea     rcx, [rax+20h]
0x140006c15  jmp     short loc_140006C2D
0x140006c17  movups  xmm0, xmmword ptr [rcx]
0x140006c1a  movups  xmmword ptr [rax], xmm0
0x140006c1d  movups  xmm1, xmmword ptr [rcx+10h]
0x140006c21  movups  xmmword ptr [rax+10h], xmm1
0x140006c25  add     rax, 20h ; ' '
0x140006c29  add     rcx, 20h ; ' '
0x140006c2d  cmp     rcx, rdx
0x140006c30  jz      short loc_140006BB5
0x140006c32  test    [rcx], sil
0x140006c35  jnz     short loc_140006C29
0x140006c37  jmp     short loc_140006C17
0x140006c39  lea     ecx, [rax+7FFFFFFFh]
0x140006c3f  cmp     ecx, 0FFFFFFFDh
0x140006c42  ja      loc_140006AB8
0x140006c48  movsxd  rax, edx
0x140006c4b  movsxd  rcx, r9d
0x140006c4e  sub     rcx, rax; __int64
0x140006c51  call    ?SaturateToInfinity@Fixed16_16@@CAH_J@Z; Fixed16_16::SaturateToInfinity(__int64)
0x140006c56  jmp     loc_140006AB8
0x140006c5b  mov     eax, 7FFFFFFFh
0x140006c60  jmp     loc_140006AA5
0x140006c65  mov     [rsp+0B8h+pExceptionObject], 80070057h
0x140006c6d  mov     [rsp+0B8h+var_88], r9
0x140006c72  lea     rdx, _TI2?AVInvalidCacheDataException@@; pThrowInfo
0x140006c79  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x140006c7e  call    _CxxThrowException_0
```
