# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18002a270`
- end: `0x18002a54c`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027860`

## callees

- `0x18002a270`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // edx
  signed __int32 i; // ecx
  signed __int32 v8; // r9d
  signed __int32 v9; // eax
  int v10; // edi
  __int64 result; // rax
  signed __int32 v12; // ecx
  BOOL v13; // ebp
  unsigned int v14; // eax
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // r8d
  unsigned int v18; // r9d
  signed __int32 v19; // eax
  signed __int32 v20; // ecx
  BOOL v21; // r9d
  unsigned int v22; // eax
  int v23; // edx
  int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // edx
  signed __int32 v27; // eax
  int v28; // edx
  unsigned __int32 v29; // eax
  int v30; // ecx
  unsigned __int32 v31; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
    case 4:
      v12 = *a2;
      v13 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v14 = v12 | 1;
        if ( (((v12 | 1u) >> 14) & 1) != v13 )
        {
          if ( ((v14 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v14 >> 5) & 0x1FF;
            v15 = 4;
            if ( a3 )
              v15 = 0;
            v14 = v12 & 0xFFFFC01E | 1;
            *(_DWORD *)(a1 + 8) = v15;
          }
          v16 = 0;
          if ( a3 == 4 )
            v16 = 0x4000;
          v14 = v14 & 0xFFFFBFFF | v16;
        }
        v17 = (v14 >> 5) & 0x1FF;
        v18 = v17 + 1;
        if ( v17 + 1 > 0x1FF || v18 < v17 )
        {
          LOWORD(v18) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v17;
        }
        v19 = _InterlockedCompareExchange(
                a2,
                v14 ^ ((unsigned __int16)v14 ^ (unsigned __int16)(32 * v18)) & 0x3FE0,
                v12);
        if ( v12 == v19 )
          break;
        v12 = v19;
      }
      *(_DWORD *)(a1 + 16) = 0;
      *(_DWORD *)a1 = (v12 & 1) == 0;
      result = a1;
      break;
    case 1:
    case 5:
      v20 = *a2;
      v21 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v22 = v20 | 1;
        if ( (((v20 | 1u) >> 22) & 1) != v21 )
        {
          if ( ((v22 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v22 >> 15) & 0x7F;
            v23 = 5;
            if ( a3 != 1 )
              v23 = 1;
            v22 = v20 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v23;
          }
          v24 = 0;
          if ( a3 == 5 )
            v24 = 0x400000;
          v22 = v22 & 0xFFBFFFFF | v24;
        }
        v25 = (v22 >> 15) & 0x7F;
        v26 = v25 + 1;
        if ( v25 + 1 > 0x7F || v26 < v25 )
        {
          v26 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v25;
        }
        v27 = _InterlockedCompareExchange(a2, v22 ^ (v22 ^ (v26 << 15)) & 0x3F8000, v20);
        if ( v20 == v27 )
          break;
        v20 = v27;
      }
      *(_DWORD *)(a1 + 16) = 0;
      result = a1;
      *(_DWORD *)a1 = (v20 & 1) == 0;
      break;
    case 2:
    case 3:
    case 6:
    case 7:
      v6 = 0;
      switch ( a3 )
      {
        case 2:
          v6 = 2;
          break;
        case 3:
          v6 = 8;
          break;
        case 6:
          v6 = 4;
          break;
        case 7:
          v6 = 16;
          break;
      }
      for ( i = *a2; ; i = v9 )
      {
        v8 = i | v6 | 1;
        *(_DWORD *)(a1 + 16) = (i | v6) == i;
        if ( (i | v6) == i )
          v8 = i | v6;
        v9 = _InterlockedCompareExchange(a2, v8, i);
        if ( i == v9 )
          break;
      }
      if ( (v8 & 1) == 0 || (v10 = 1, (i & 1) != 0) )
        v10 = 0;
      *(_DWORD *)a1 = v10;
      result = a1;
      break;
    default:
      v28 = a3 - 320;
      if ( a3 - 320 >= 64 )
        goto LABEL_56;
      v29 = *((_DWORD *)a2 + 1);
      do
      {
        if ( (v29 & 0x10) == 0 || (v30 = 1, ((v29 >> 5) & 0x3F) != v28) )
          v30 = 0;
        *(_DWORD *)(a1 + 16) = v30;
        v31 = v29;
        v29 = _InterlockedCompareExchange(
                a2 + 1,
                v29 ^ ((unsigned __int16)v29 ^ (unsigned __int16)(32 * v28)) & 0x7E0 | 0x10,
                v29);
      }
      while ( v31 != v29 );
      if ( !*(_DWORD *)(a1 + 16) )
      {
LABEL_56:
        *(_DWORD *)(a1 + 8) = a3;
        *(_DWORD *)(a1 + 4) = 1;
        *(_DWORD *)(a1 + 12) = 0;
      }
      result = a1;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18002a270  push    rbx
0x18002a272  push    rbp
0x18002a273  push    rsi
0x18002a274  push    rdi
0x18002a275  xor     eax, eax
0x18002a277  movsxd  r11, r8d
0x18002a27a  xorps   xmm0, xmm0
0x18002a27d  mov     rsi, rdx
0x18002a280  mov     r10, rcx
0x18002a283  movups  xmmword ptr [rcx], xmm0
0x18002a286  mov     [rcx+10h], rax
0x18002a28a  cmp     r11d, 7; switch 8 cases
0x18002a28e  ja      def_18002A2A6; jumptable 000000018002A2A6 default case
0x18002a294  lea     rcx, __ImageBase
0x18002a29b  mov     r8d, ds:(jpt_18002A2A6 - 180000000h)[rcx+r11*4]
0x18002a2a3  add     r8, rcx
0x18002a2a6  jmp     r8; switch jump
0x18002a2a9  xor     ebx, ebx; jumptable 000000018002A2A6 cases 2,3,6,7
0x18002a2ab  mov     edx, ebx
0x18002a2ad  sub     r11d, 2
0x18002a2b1  jz      short loc_18002A2DA
0x18002a2b3  sub     r11d, 1
0x18002a2b7  jz      short loc_18002A2D3
0x18002a2b9  sub     r11d, 3
0x18002a2bd  jz      short loc_18002A2CC
0x18002a2bf  cmp     r11d, 1
0x18002a2c3  jnz     short loc_18002A2DF
0x18002a2c5  mov     edx, 10h
0x18002a2ca  jmp     short loc_18002A2DF
0x18002a2cc  mov     edx, 4
0x18002a2d1  jmp     short loc_18002A2DF
0x18002a2d3  mov     edx, 8
0x18002a2d8  jmp     short loc_18002A2DF
0x18002a2da  mov     edx, 2
0x18002a2df  mov     ecx, [rsi]
0x18002a2e1  mov     eax, ebx
0x18002a2e3  mov     r8d, edx
0x18002a2e6  or      r8d, ecx
0x18002a2e9  cmp     r8d, ecx
0x18002a2ec  mov     r9d, r8d
0x18002a2ef  setz    al
0x18002a2f2  or      r9d, 1
0x18002a2f6  cmp     r8d, ecx
0x18002a2f9  mov     [r10+10h], eax
0x18002a2fd  mov     eax, ecx
0x18002a2ff  cmovz   r9d, r8d
0x18002a303  lock cmpxchg [rsi], r9d
0x18002a308  jz      short loc_18002A30E
0x18002a30a  mov     ecx, eax
0x18002a30c  jmp     short loc_18002A2E1
0x18002a30e  test    r9b, 1
0x18002a312  jz      short loc_18002A31E
0x18002a314  mov     edi, 1
0x18002a319  test    cl, 1
0x18002a31c  jz      short loc_18002A320
0x18002a31e  mov     edi, ebx
0x18002a320  mov     [r10], edi
0x18002a323  mov     rax, r10
0x18002a326  pop     rdi
0x18002a327  pop     rsi
0x18002a328  pop     rbp
0x18002a329  pop     rbx
0x18002a32a  retn
0x18002a32b  mov     ecx, [rdx]; jumptable 000000018002A2A6 cases 0,4
0x18002a32d  xor     ebx, ebx
0x18002a32f  cmp     r11d, 4
0x18002a333  mov     [rsp+20h+arg_0], r14
0x18002a338  mov     ebp, ebx
0x18002a33a  mov     edx, 4
0x18002a33f  setz    bpl
0x18002a343  mov     edi, 1
0x18002a348  mov     r14d, 4000h
0x18002a34e  xchg    ax, ax
0x18002a350  mov     eax, ecx
0x18002a352  mov     [r10+4], ebx
0x18002a356  or      eax, edi
0x18002a358  mov     r8d, eax
0x18002a35b  shr     r8d, 0Eh
0x18002a35f  and     r8d, edi
0x18002a362  cmp     r8d, ebp
0x18002a365  jz      short loc_18002A3A6
0x18002a367  mov     r9d, eax
0x18002a36a  shr     r9d, 5
0x18002a36e  and     r9d, 1FFh
0x18002a375  jbe     short loc_18002A38E
0x18002a377  test    r11d, r11d
0x18002a37a  mov     [r10+4], r9d
0x18002a37e  mov     r8d, edx
0x18002a381  cmovnz  r8d, ebx
0x18002a385  and     eax, 0FFFFC01Fh
0x18002a38a  mov     [r10+8], r8d
0x18002a38e  mov     r8d, eax
0x18002a391  cmp     r11d, edx
0x18002a394  mov     r9d, ebx
0x18002a397  cmovz   r9d, r14d
0x18002a39b  btr     r8d, 0Eh
0x18002a3a0  mov     eax, r9d
0x18002a3a3  or      eax, r8d
0x18002a3a6  mov     r8d, eax
0x18002a3a9  shr     r8d, 5
0x18002a3ad  and     r8d, 1FFh
0x18002a3b4  lea     r9d, [r8+1]
0x18002a3b8  cmp     r9d, 1FFh
0x18002a3bf  ja      short loc_18002A3C6
0x18002a3c1  cmp     r9d, r8d
0x18002a3c4  jnb     short loc_18002A3D1
0x18002a3c6  mov     r9d, edi
0x18002a3c9  mov     [r10+8], r11d
0x18002a3cd  mov     [r10+4], r8d
0x18002a3d1  shl     r9d, 5
0x18002a3d5  xor     r9d, eax
0x18002a3d8  and     r9d, 3FE0h
0x18002a3df  xor     r9d, eax
0x18002a3e2  mov     eax, ecx
0x18002a3e4  lock cmpxchg [rsi], r9d
0x18002a3e9  jz      short loc_18002A3F2
0x18002a3eb  mov     ecx, eax
0x18002a3ed  jmp     loc_18002A350
0x18002a3f2  mov     r14, [rsp+20h+arg_0]
0x18002a3f7  not     ecx
0x18002a3f9  and     ecx, edi
0x18002a3fb  mov     [r10+10h], ebx
0x18002a3ff  mov     [r10], ecx
0x18002a402  mov     rax, r10
0x18002a405  pop     rdi
0x18002a406  pop     rsi
0x18002a407  pop     rbp
0x18002a408  pop     rbx
0x18002a409  retn
0x18002a40a  mov     ecx, [rdx]; jumptable 000000018002A2A6 cases 1,5
0x18002a40c  xor     ebx, ebx
0x18002a40e  cmp     r11d, 5
0x18002a412  mov     r9d, ebx
0x18002a415  mov     edi, 1
0x18002a41a  mov     ebp, 400000h
0x18002a41f  setz    r9b
0x18002a423  mov     eax, ecx
0x18002a425  mov     [r10+4], ebx
0x18002a429  or      eax, edi
0x18002a42b  mov     edx, eax
0x18002a42d  shr     edx, 16h
0x18002a430  and     edx, edi
0x18002a432  cmp     edx, r9d
0x18002a435  jz      short loc_18002A472
0x18002a437  mov     r8d, eax
0x18002a43a  shr     r8d, 0Fh
0x18002a43e  and     r8d, 7Fh
0x18002a442  jbe     short loc_18002A45C
0x18002a444  cmp     r11d, edi
0x18002a447  mov     [r10+4], r8d
0x18002a44b  mov     edx, 5
0x18002a450  cmovnz  edx, edi
0x18002a453  and     eax, 0FFC07FFFh
0x18002a458  mov     [r10+8], edx
0x18002a45c  mov     edx, eax
0x18002a45e  cmp     r11d, 5
0x18002a462  mov     r8d, ebx
0x18002a465  cmovz   r8d, ebp
0x18002a469  btr     edx, 16h
0x18002a46d  mov     eax, r8d
0x18002a470  or      eax, edx
0x18002a472  mov     r8d, eax
0x18002a475  shr     r8d, 0Fh
0x18002a479  and     r8d, 7Fh
0x18002a47d  lea     edx, [r8+1]
0x18002a481  cmp     edx, 7Fh
0x18002a484  ja      short loc_18002A48B
0x18002a486  cmp     edx, r8d
0x18002a489  jnb     short loc_18002A495
0x18002a48b  mov     edx, edi
0x18002a48d  mov     [r10+8], r11d
0x18002a491  mov     [r10+4], r8d
0x18002a495  shl     edx, 0Fh
0x18002a498  xor     edx, eax
0x18002a49a  and     edx, 3F8000h
0x18002a4a0  xor     edx, eax
0x18002a4a2  mov     eax, ecx
0x18002a4a4  lock cmpxchg [rsi], edx
0x18002a4a8  jz      short loc_18002A4B1
0x18002a4aa  mov     ecx, eax
0x18002a4ac  jmp     loc_18002A423
0x18002a4b1  not     ecx
0x18002a4b3  mov     [r10+10h], ebx
0x18002a4b7  and     ecx, edi
0x18002a4b9  mov     rax, r10
0x18002a4bc  mov     [r10], ecx
0x18002a4bf  pop     rdi
0x18002a4c0  pop     rsi
0x18002a4c1  pop     rbp
0x18002a4c2  pop     rbx
0x18002a4c3  retn
0x18002a4c4  lea     edx, [r11-140h]; jumptable 000000018002A2A6 default case
0x18002a4cb  xor     ebx, ebx
0x18002a4cd  mov     edi, 1
0x18002a4d2  cmp     edx, 40h ; '@'
0x18002a4d5  jge     short loc_18002A516
0x18002a4d7  mov     eax, [rsi+4]
0x18002a4da  mov     r8d, edx
0x18002a4dd  shl     r8d, 5
0x18002a4e1  test    al, 10h
0x18002a4e3  jz      short loc_18002A4F3
0x18002a4e5  mov     ecx, eax
0x18002a4e7  shr     ecx, 5
0x18002a4ea  and     ecx, 3Fh
0x18002a4ed  cmp     ecx, edx
0x18002a4ef  mov     ecx, edi
0x18002a4f1  jz      short loc_18002A4F5
0x18002a4f3  mov     ecx, ebx
0x18002a4f5  mov     [r10+10h], ecx
0x18002a4f9  mov     ecx, r8d
0x18002a4fc  xor     ecx, eax
0x18002a4fe  and     ecx, 7E0h
0x18002a504  xor     ecx, eax
0x18002a506  or      ecx, 10h
0x18002a509  lock cmpxchg [rsi+4], ecx
0x18002a50e  jnz     short loc_18002A4E1
0x18002a510  cmp     [r10+10h], ebx
0x18002a514  jnz     short loc_18002A522
0x18002a516  mov     [r10+8], r11d
0x18002a51a  mov     [r10+4], edi
0x18002a51e  mov     [r10+0Ch], ebx
0x18002a522  mov     rax, r10
0x18002a525  pop     rdi
0x18002a526  pop     rsi
0x18002a527  pop     rbp
0x18002a528  pop     rbx
0x18002a529  retn
```
