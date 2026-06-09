# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140010388`
- end: `0x14001065a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001078c`

## callees

- `0x140010388`

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
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
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
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x140010388  push    rbx
0x14001038a  push    rbp
0x14001038b  push    rsi
0x14001038c  push    rdi
0x14001038d  xor     eax, eax
0x14001038f  xorps   xmm0, xmm0
0x140010392  mov     r10, rcx
0x140010395  mov     edi, r9d
0x140010398  mov     r11d, r8d
0x14001039b  mov     rsi, rdx
0x14001039e  movups  xmmword ptr [rcx], xmm0
0x1400103a1  mov     [rcx+10h], rax
0x1400103a5  mov     ecx, r8d
0x1400103a8  test    r8d, r8d
0x1400103ab  jz      loc_140010584
0x1400103b1  sub     ecx, 1
0x1400103b4  jz      loc_1400104CB
0x1400103ba  sub     ecx, 1
0x1400103bd  jz      loc_140010452
0x1400103c3  sub     ecx, 1
0x1400103c6  jz      loc_140010452
0x1400103cc  sub     ecx, 1
0x1400103cf  jz      loc_140010584
0x1400103d5  sub     ecx, 1
0x1400103d8  jz      loc_1400104CB
0x1400103de  sub     ecx, 1
0x1400103e1  jz      short loc_140010452
0x1400103e3  cmp     ecx, 1
0x1400103e6  jz      short loc_140010452
0x1400103e8  add     r8d, 0FFFFFEC0h
0x1400103ef  lea     ebx, [rax+1]
0x1400103f2  cmp     r8d, 40h ; '@'
0x1400103f6  jge     short loc_140010441
0x1400103f8  mov     eax, [rdx+4]
0x1400103fb  lea     ecx, [rbx+0Fh]
0x1400103fe  mov     r9d, r8d
0x140010401  shl     r9d, 5
0x140010405  test    cl, al
0x140010407  jz      short loc_14001041A
0x140010409  mov     edx, eax
0x14001040b  shr     edx, 5
0x14001040e  and     edx, 3Fh
0x140010411  cmp     edx, r8d
0x140010414  jnz     short loc_14001041A
0x140010416  mov     edx, ebx
0x140010418  jmp     short loc_14001041C
0x14001041a  xor     edx, edx
0x14001041c  mov     [r10+10h], edx
0x140010420  mov     edx, r9d
0x140010423  xor     edx, eax
0x140010425  and     edx, 7E0h
0x14001042b  xor     edx, eax
0x14001042d  or      edx, ecx
0x14001042f  lock cmpxchg [rsi+4], edx
0x140010434  jnz     short loc_140010405
0x140010436  cmp     dword ptr [r10+10h], 0
0x14001043b  jnz     loc_140010652
0x140010441  mov     [r10+8], r11d
0x140010445  mov     [r10+4], ebx
0x140010449  mov     [r10+0Ch], edi
0x14001044d  jmp     loc_140010652
0x140010452  xor     ecx, ecx
0x140010454  sub     r11d, 2
0x140010458  jz      short loc_140010480
0x14001045a  sub     r11d, 1
0x14001045e  jz      short loc_140010479
0x140010460  sub     r11d, 3
0x140010464  jz      short loc_140010472
0x140010466  cmp     r11d, 1
0x14001046a  jnz     short loc_140010485
0x14001046c  lea     ecx, [r11+0Fh]
0x140010470  jmp     short loc_140010485
0x140010472  mov     ecx, 4
0x140010477  jmp     short loc_140010485
0x140010479  mov     ecx, 8
0x14001047e  jmp     short loc_140010485
0x140010480  mov     ecx, 2
0x140010485  mov     edx, [rdx]
0x140010487  mov     ebx, 1
0x14001048c  xor     eax, eax
0x14001048e  mov     r8d, ecx
0x140010491  or      r8d, edx
0x140010494  cmp     r8d, edx
0x140010497  mov     r9d, r8d
0x14001049a  setz    al
0x14001049d  or      r9d, ebx
0x1400104a0  cmp     r8d, edx
0x1400104a3  mov     [r10+10h], eax
0x1400104a7  mov     eax, edx
0x1400104a9  cmovz   r9d, r8d
0x1400104ad  lock cmpxchg [rsi], r9d
0x1400104b2  jz      short loc_1400104B8
0x1400104b4  mov     edx, eax
0x1400104b6  jmp     short loc_14001048C
0x1400104b8  test    bl, r9b
0x1400104bb  jz      short loc_1400104C1
0x1400104bd  test    bl, dl
0x1400104bf  jz      short loc_1400104C3
0x1400104c1  xor     ebx, ebx
0x1400104c3  mov     [r10], ebx
0x1400104c6  jmp     loc_140010652
0x1400104cb  mov     ecx, [rdx]
0x1400104cd  xor     r9d, r9d
0x1400104d0  cmp     r11d, 5
0x1400104d4  mov     ebx, 1
0x1400104d9  setz    r9b
0x1400104dd  mov     eax, ecx
0x1400104df  mov     dword ptr [r10+4], 0
0x1400104e7  or      eax, ebx
0x1400104e9  mov     edx, eax
0x1400104eb  shr     edx, 16h
0x1400104ee  and     edx, ebx
0x1400104f0  cmp     edx, r9d
0x1400104f3  jz      short loc_140010535
0x1400104f5  mov     r8d, eax
0x1400104f8  shr     r8d, 0Fh
0x1400104fc  and     r8d, 7Fh
0x140010500  jbe     short loc_14001051A
0x140010502  cmp     r11d, ebx
0x140010505  mov     [r10+4], r8d
0x140010509  mov     edx, 5
0x14001050e  cmovnz  edx, ebx
0x140010511  and     eax, 0FFC07FFFh
0x140010516  mov     [r10+8], edx
0x14001051a  xor     r8d, r8d
0x14001051d  mov     edx, 400000h
0x140010522  cmp     r11d, 5
0x140010526  cmovz   r8d, edx
0x14001052a  mov     edx, eax
0x14001052c  btr     edx, 16h
0x140010530  mov     eax, r8d
0x140010533  or      eax, edx
0x140010535  mov     edx, eax
0x140010537  shr     edx, 0Fh
0x14001053a  and     edx, 7Fh
0x14001053d  lea     r8d, [rdx+1]
0x140010541  cmp     r8d, 7Fh
0x140010545  ja      short loc_14001054C
0x140010547  cmp     r8d, edx
0x14001054a  jnb     short loc_140010557
0x14001054c  mov     r8d, ebx
0x14001054f  mov     [r10+8], r11d
0x140010553  mov     [r10+4], edx
0x140010557  shl     r8d, 0Fh
0x14001055b  xor     r8d, eax
0x14001055e  and     r8d, 3F8000h
0x140010565  xor     r8d, eax
0x140010568  mov     eax, ecx
0x14001056a  lock cmpxchg [rsi], r8d
0x14001056f  jz      short loc_140010578
0x140010571  mov     ecx, eax
0x140010573  jmp     loc_1400104DD
0x140010578  not     ecx
0x14001057a  and     ecx, ebx
0x14001057c  mov     [r10], ecx
0x14001057f  jmp     loc_14001064A
0x140010584  mov     edx, [rdx]
0x140010586  xor     ebp, ebp
0x140010588  lea     ecx, [rbp+4]
0x14001058b  cmp     r11d, ecx
0x14001058e  lea     ebx, [rcx-3]
0x140010591  setz    bpl
0x140010595  mov     eax, edx
0x140010597  mov     dword ptr [r10+4], 0
0x14001059f  or      eax, ebx
0x1400105a1  mov     r8d, eax
0x1400105a4  shr     r8d, 0Eh
0x1400105a8  and     r8d, ebx
0x1400105ab  cmp     r8d, ebp
0x1400105ae  jz      short loc_1400105F7
0x1400105b0  mov     edi, eax
0x1400105b2  shr     edi, 5
0x1400105b5  and     edi, 1FFh
0x1400105bb  jbe     short loc_1400105D9
0x1400105bd  mov     r8d, r11d
0x1400105c0  mov     [r10+4], edi
0x1400105c4  neg     r8d
0x1400105c7  sbb     r9d, r9d
0x1400105ca  not     r9d
0x1400105cd  and     r9d, ecx
0x1400105d0  mov     [r10+8], r9d
0x1400105d4  and     eax, 0FFFFC01Fh
0x1400105d9  xor     r9d, r9d
0x1400105dc  mov     r8d, 4000h
0x1400105e2  cmp     r11d, ecx
0x1400105e5  cmovz   r9d, r8d
0x1400105e9  mov     r8d, eax
0x1400105ec  btr     r8d, 0Eh
0x1400105f1  mov     eax, r9d
0x1400105f4  or      eax, r8d
0x1400105f7  mov     r8d, eax
0x1400105fa  shr     r8d, 5
0x1400105fe  and     r8d, 1FFh
0x140010605  lea     r9d, [r8+1]
0x140010609  cmp     r9d, 1FFh
0x140010610  ja      short loc_140010617
0x140010612  cmp     r9d, r8d
0x140010615  jnb     short loc_140010622
0x140010617  mov     r9d, ebx
0x14001061a  mov     [r10+8], r11d
0x14001061e  mov     [r10+4], r8d
0x140010622  shl     r9d, 5
0x140010626  xor     r9d, eax
0x140010629  and     r9d, 3FE0h
0x140010630  xor     r9d, eax
0x140010633  mov     eax, edx
0x140010635  lock cmpxchg [rsi], r9d
0x14001063a  jz      short loc_140010643
0x14001063c  mov     edx, eax
0x14001063e  jmp     loc_140010595
0x140010643  not     edx
0x140010645  and     edx, ebx
0x140010647  mov     [r10], edx
0x14001064a  mov     dword ptr [r10+10h], 0
0x140010652  mov     rax, r10
0x140010655  pop     rdi
0x140010656  pop     rsi
0x140010657  pop     rbp
0x140010658  pop     rbx
0x140010659  retn
```
