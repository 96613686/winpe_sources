# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001a964`
- end: `0x18001ac48`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `740`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011070`
- `0x1800219a0`

## callees

- `0x18001a964`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // ecx
  unsigned __int32 v10; // ett
  int v11; // edx
  signed __int32 v12; // eax
  int v13; // ebx
  char v14; // r9
  signed __int32 v15; // r8d
  signed __int32 v16; // ett
  signed __int32 v17; // eax
  BOOL v18; // edi
  unsigned int v19; // ecx
  char v20; // r9
  int v21; // edx
  int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // edx
  signed __int32 v25; // ett
  signed __int32 v26; // eax
  BOOL v27; // ebp
  unsigned int v28; // ecx
  char v29; // di
  int v30; // r9d
  unsigned int v31; // r9d
  unsigned int v32; // r8d
  signed __int32 v33; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_47;
    case 1:
      goto LABEL_33;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_47:
      v26 = *a2;
      v27 = a3 == 4;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v28 = v26 | 1;
        v29 = v26;
        if ( (((v26 | 1u) >> 14) & 1) != v27 )
        {
          if ( ((v28 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v28 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v28 = v26 & 0xFFFFC01E | 1;
          }
          v30 = 0;
          if ( a3 == 4 )
            v30 = 0x4000;
          v28 = v28 & 0xFFFFBFFF | v30;
        }
        v31 = (v28 >> 5) & 0x1FF;
        v32 = v31 + 1;
        if ( v31 + 1 > 0x1FF || v32 < v31 )
        {
          LOWORD(v32) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v31;
        }
        v33 = v26;
        v26 = _InterlockedCompareExchange(
                a2,
                ((unsigned __int16)v28 ^ (unsigned __int16)(32 * v32)) & 0x3FE0 ^ v28,
                v26);
      }
      while ( v33 != v26 );
      *(_DWORD *)a1 = (v29 & 1) == 0;
      goto LABEL_59;
    case 5:
LABEL_33:
      v17 = *a2;
      v18 = a3 == 5;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v19 = v17 | 1;
        v20 = v17;
        if ( (((v17 | 1u) >> 22) & 1) != v18 )
        {
          if ( ((v19 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v19 >> 15) & 0x7F;
            v21 = 5;
            if ( a3 != 1 )
              v21 = 1;
            v19 = v17 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v21;
          }
          v22 = 0;
          if ( a3 == 5 )
            v22 = 0x400000;
          v19 = v19 & 0xFFBFFFFF | v22;
        }
        v23 = (v19 >> 15) & 0x7F;
        v24 = v23 + 1;
        if ( v23 + 1 > 0x7F || v24 < v23 )
        {
          v24 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v23;
        }
        v25 = v17;
        v17 = _InterlockedCompareExchange(a2, (v19 ^ (v24 << 15)) & 0x3F8000 ^ v19, v17);
      }
      while ( v25 != v17 );
      *(_DWORD *)a1 = (v20 & 1) == 0;
LABEL_59:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  do
  {
    v14 = v12;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    v15 = v12 | v11 | 1;
    if ( (v12 | v11) == v12 )
      v15 = v12 | v11;
    v16 = v12;
    v12 = _InterlockedCompareExchange(a2, v15, v12);
  }
  while ( v16 != v12 );
  if ( (v15 & 1) == 0 || (v14 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x18001a964  mov     rax, rsp
0x18001a967  mov     [rax+8], rbx
0x18001a96b  mov     [rax+10h], rbp
0x18001a96f  mov     [rax+18h], rsi
0x18001a973  mov     [rax+20h], rdi
0x18001a977  push    r14
0x18001a979  xor     eax, eax
0x18001a97b  xorps   xmm0, xmm0
0x18001a97e  mov     r10, rcx
0x18001a981  mov     edi, r9d
0x18001a984  mov     r11d, r8d
0x18001a987  mov     r14, rdx
0x18001a98a  movups  xmmword ptr [rcx], xmm0
0x18001a98d  mov     [rcx+10h], rax
0x18001a991  mov     ecx, r8d
0x18001a994  test    r8d, r8d
0x18001a997  jz      loc_18001AB67
0x18001a99d  sub     ecx, 1
0x18001a9a0  jz      loc_18001AAB5
0x18001a9a6  sub     ecx, 1
0x18001a9a9  jz      loc_18001AA3F
0x18001a9af  sub     ecx, 1
0x18001a9b2  jz      loc_18001AA3F
0x18001a9b8  sub     ecx, 1
0x18001a9bb  jz      loc_18001AB67
0x18001a9c1  sub     ecx, 1
0x18001a9c4  jz      loc_18001AAB5
0x18001a9ca  sub     ecx, 1
0x18001a9cd  jz      short loc_18001AA3F
0x18001a9cf  cmp     ecx, 1
0x18001a9d2  jz      short loc_18001AA3F
0x18001a9d4  add     r8d, 0FFFFFEC0h
0x18001a9db  lea     ebx, [rax+1]
0x18001a9de  cmp     r8d, 40h ; '@'
0x18001a9e2  jge     short loc_18001AA2E
0x18001a9e4  mov     eax, [rdx+4]
0x18001a9e7  mov     r9d, r8d
0x18001a9ea  shl     r9d, 5
0x18001a9ee  lea     edx, [rbx+0Fh]
0x18001a9f1  test    dl, al
0x18001a9f3  jz      short loc_18001AA06
0x18001a9f5  mov     ecx, eax
0x18001a9f7  shr     ecx, 5
0x18001a9fa  and     ecx, 3Fh
0x18001a9fd  cmp     ecx, r8d
0x18001aa00  jnz     short loc_18001AA06
0x18001aa02  mov     ecx, ebx
0x18001aa04  jmp     short loc_18001AA08
0x18001aa06  xor     ecx, ecx
0x18001aa08  mov     [r10+10h], ecx
0x18001aa0c  mov     ecx, r9d
0x18001aa0f  xor     ecx, eax
0x18001aa11  and     ecx, 7E0h
0x18001aa17  xor     ecx, eax
0x18001aa19  or      ecx, edx
0x18001aa1b  lock cmpxchg [r14+4], ecx
0x18001aa21  jnz     short loc_18001A9F1
0x18001aa23  cmp     dword ptr [r10+10h], 0
0x18001aa28  jnz     loc_18001AC2D
0x18001aa2e  mov     [r10+8], r11d
0x18001aa32  mov     [r10+4], ebx
0x18001aa36  mov     [r10+0Ch], edi
0x18001aa3a  jmp     loc_18001AC2D
0x18001aa3f  xor     edx, edx
0x18001aa41  sub     r11d, 2
0x18001aa45  jz      short loc_18001AA6D
0x18001aa47  sub     r11d, 1
0x18001aa4b  jz      short loc_18001AA66
0x18001aa4d  sub     r11d, 3
0x18001aa51  jz      short loc_18001AA5F
0x18001aa53  cmp     r11d, 1
0x18001aa57  jnz     short loc_18001AA72
0x18001aa59  lea     edx, [r11+0Fh]
0x18001aa5d  jmp     short loc_18001AA72
0x18001aa5f  mov     edx, 4
0x18001aa64  jmp     short loc_18001AA72
0x18001aa66  mov     edx, 8
0x18001aa6b  jmp     short loc_18001AA72
0x18001aa6d  mov     edx, 2
0x18001aa72  mov     eax, [r14]
0x18001aa75  mov     ebx, 1
0x18001aa7a  xor     r8d, r8d
0x18001aa7d  mov     ecx, edx
0x18001aa7f  or      ecx, eax
0x18001aa81  mov     r9d, eax
0x18001aa84  cmp     ecx, eax
0x18001aa86  setz    r8b
0x18001aa8a  mov     [r10+10h], r8d
0x18001aa8e  mov     r8d, ecx
0x18001aa91  or      r8d, ebx
0x18001aa94  cmp     ecx, eax
0x18001aa96  cmovz   r8d, ecx
0x18001aa9a  lock cmpxchg [r14], r8d
0x18001aa9f  jnz     short loc_18001AA7A
0x18001aaa1  test    bl, r8b
0x18001aaa4  jz      short loc_18001AAAB
0x18001aaa6  test    bl, r9b
0x18001aaa9  jz      short loc_18001AAAD
0x18001aaab  xor     ebx, ebx
0x18001aaad  mov     [r10], ebx
0x18001aab0  jmp     loc_18001AC2D
0x18001aab5  mov     eax, [rdx]
0x18001aab7  xor     edi, edi
0x18001aab9  cmp     r11d, 5
0x18001aabd  mov     ebx, 1
0x18001aac2  setz    dil
0x18001aac6  and     dword ptr [r10+4], 0
0x18001aacb  mov     ecx, eax
0x18001aacd  or      ecx, ebx
0x18001aacf  mov     r9d, eax
0x18001aad2  mov     edx, ecx
0x18001aad4  shr     edx, 16h
0x18001aad7  and     edx, ebx
0x18001aad9  cmp     edx, edi
0x18001aadb  jz      short loc_18001AB1E
0x18001aadd  mov     r8d, ecx
0x18001aae0  shr     r8d, 0Fh
0x18001aae4  and     r8d, 7Fh
0x18001aae8  jbe     short loc_18001AB03
0x18001aaea  cmp     r11d, ebx
0x18001aaed  mov     [r10+4], r8d
0x18001aaf1  mov     edx, 5
0x18001aaf6  cmovnz  edx, ebx
0x18001aaf9  and     ecx, 0FFC07FFFh
0x18001aaff  mov     [r10+8], edx
0x18001ab03  xor     r8d, r8d
0x18001ab06  mov     edx, 400000h
0x18001ab0b  cmp     r11d, 5
0x18001ab0f  cmovz   r8d, edx
0x18001ab13  mov     edx, ecx
0x18001ab15  btr     edx, 16h
0x18001ab19  mov     ecx, r8d
0x18001ab1c  or      ecx, edx
0x18001ab1e  mov     r8d, ecx
0x18001ab21  shr     r8d, 0Fh
0x18001ab25  and     r8d, 7Fh
0x18001ab29  lea     edx, [r8+1]
0x18001ab2d  cmp     edx, 7Fh
0x18001ab30  ja      short loc_18001AB37
0x18001ab32  cmp     edx, r8d
0x18001ab35  jnb     short loc_18001AB41
0x18001ab37  mov     edx, ebx
0x18001ab39  mov     [r10+8], r11d
0x18001ab3d  mov     [r10+4], r8d
0x18001ab41  shl     edx, 0Fh
0x18001ab44  xor     edx, ecx
0x18001ab46  and     edx, 3F8000h
0x18001ab4c  xor     ecx, edx
0x18001ab4e  lock cmpxchg [r14], ecx
0x18001ab53  jnz     loc_18001AAC6
0x18001ab59  not     r9d
0x18001ab5c  and     r9d, ebx
0x18001ab5f  mov     [r10], r9d
0x18001ab62  jmp     loc_18001AC28
0x18001ab67  mov     eax, [rdx]
0x18001ab69  xor     ebp, ebp
0x18001ab6b  lea     edx, [rbp+4]
0x18001ab6e  cmp     r11d, edx
0x18001ab71  lea     ebx, [rdx-3]
0x18001ab74  setz    bpl
0x18001ab78  and     dword ptr [r10+4], 0
0x18001ab7d  mov     ecx, eax
0x18001ab7f  or      ecx, ebx
0x18001ab81  mov     edi, eax
0x18001ab83  mov     r8d, ecx
0x18001ab86  shr     r8d, 0Eh
0x18001ab8a  and     r8d, ebx
0x18001ab8d  cmp     r8d, ebp
0x18001ab90  jz      short loc_18001ABDA
0x18001ab92  mov     esi, ecx
0x18001ab94  shr     esi, 5
0x18001ab97  and     esi, 1FFh
0x18001ab9d  jbe     short loc_18001ABBC
0x18001ab9f  mov     r8d, r11d
0x18001aba2  mov     [r10+4], esi
0x18001aba6  neg     r8d
0x18001aba9  sbb     r9d, r9d
0x18001abac  not     r9d
0x18001abaf  and     r9d, edx
0x18001abb2  mov     [r10+8], r9d
0x18001abb6  and     ecx, 0FFFFC01Fh
0x18001abbc  xor     r9d, r9d
0x18001abbf  mov     r8d, 4000h
0x18001abc5  cmp     r11d, edx
0x18001abc8  cmovz   r9d, r8d
0x18001abcc  mov     r8d, ecx
0x18001abcf  btr     r8d, 0Eh
0x18001abd4  mov     ecx, r9d
0x18001abd7  or      ecx, r8d
0x18001abda  mov     r9d, ecx
0x18001abdd  shr     r9d, 5
0x18001abe1  and     r9d, 1FFh
0x18001abe8  lea     r8d, [r9+1]
0x18001abec  cmp     r8d, 1FFh
0x18001abf3  ja      short loc_18001ABFA
0x18001abf5  cmp     r8d, r9d
0x18001abf8  jnb     short loc_18001AC05
0x18001abfa  mov     r8d, ebx
0x18001abfd  mov     [r10+8], r11d
0x18001ac01  mov     [r10+4], r9d
0x18001ac05  shl     r8d, 5
0x18001ac09  xor     r8d, ecx
0x18001ac0c  and     r8d, 3FE0h
0x18001ac13  xor     ecx, r8d
0x18001ac16  lock cmpxchg [r14], ecx
0x18001ac1b  jnz     loc_18001AB78
0x18001ac21  not     edi
0x18001ac23  and     edi, ebx
0x18001ac25  mov     [r10], edi
0x18001ac28  and     dword ptr [r10+10h], 0
0x18001ac2d  mov     rbx, [rsp+8+arg_0]
0x18001ac32  mov     rax, r10
0x18001ac35  mov     rbp, [rsp+8+arg_8]
0x18001ac3a  mov     rsi, [rsp+8+arg_10]
0x18001ac3f  mov     rdi, [rsp+8+arg_18]
0x18001ac44  pop     r14
0x18001ac46  retn
```
