# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180019970`
- end: `0x180019c42`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010688`
- `0x18002033c`

## callees

- `0x180019970`

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
0x180019970  push    rbx
0x180019972  push    rbp
0x180019973  push    rsi
0x180019974  push    rdi
0x180019975  xor     eax, eax
0x180019977  xorps   xmm0, xmm0
0x18001997a  mov     r10, rcx
0x18001997d  mov     edi, r9d
0x180019980  mov     r11d, r8d
0x180019983  mov     rsi, rdx
0x180019986  movups  xmmword ptr [rcx], xmm0
0x180019989  mov     [rcx+10h], rax
0x18001998d  mov     ecx, r8d
0x180019990  test    r8d, r8d
0x180019993  jz      loc_180019B6C
0x180019999  sub     ecx, 1
0x18001999c  jz      loc_180019AB3
0x1800199a2  sub     ecx, 1
0x1800199a5  jz      loc_180019A3A
0x1800199ab  sub     ecx, 1
0x1800199ae  jz      loc_180019A3A
0x1800199b4  sub     ecx, 1
0x1800199b7  jz      loc_180019B6C
0x1800199bd  sub     ecx, 1
0x1800199c0  jz      loc_180019AB3
0x1800199c6  sub     ecx, 1
0x1800199c9  jz      short loc_180019A3A
0x1800199cb  cmp     ecx, 1
0x1800199ce  jz      short loc_180019A3A
0x1800199d0  add     r8d, 0FFFFFEC0h
0x1800199d7  lea     ebx, [rax+1]
0x1800199da  cmp     r8d, 40h ; '@'
0x1800199de  jge     short loc_180019A29
0x1800199e0  mov     eax, [rdx+4]
0x1800199e3  lea     ecx, [rbx+0Fh]
0x1800199e6  mov     r9d, r8d
0x1800199e9  shl     r9d, 5
0x1800199ed  test    cl, al
0x1800199ef  jz      short loc_180019A02
0x1800199f1  mov     edx, eax
0x1800199f3  shr     edx, 5
0x1800199f6  and     edx, 3Fh
0x1800199f9  cmp     edx, r8d
0x1800199fc  jnz     short loc_180019A02
0x1800199fe  mov     edx, ebx
0x180019a00  jmp     short loc_180019A04
0x180019a02  xor     edx, edx
0x180019a04  mov     [r10+10h], edx
0x180019a08  mov     edx, r9d
0x180019a0b  xor     edx, eax
0x180019a0d  and     edx, 7E0h
0x180019a13  xor     edx, eax
0x180019a15  or      edx, ecx
0x180019a17  lock cmpxchg [rsi+4], edx
0x180019a1c  jnz     short loc_1800199ED
0x180019a1e  cmp     dword ptr [r10+10h], 0
0x180019a23  jnz     loc_180019C3A
0x180019a29  mov     [r10+8], r11d
0x180019a2d  mov     [r10+4], ebx
0x180019a31  mov     [r10+0Ch], edi
0x180019a35  jmp     loc_180019C3A
0x180019a3a  xor     ecx, ecx
0x180019a3c  sub     r11d, 2
0x180019a40  jz      short loc_180019A68
0x180019a42  sub     r11d, 1
0x180019a46  jz      short loc_180019A61
0x180019a48  sub     r11d, 3
0x180019a4c  jz      short loc_180019A5A
0x180019a4e  cmp     r11d, 1
0x180019a52  jnz     short loc_180019A6D
0x180019a54  lea     ecx, [r11+0Fh]
0x180019a58  jmp     short loc_180019A6D
0x180019a5a  mov     ecx, 4
0x180019a5f  jmp     short loc_180019A6D
0x180019a61  mov     ecx, 8
0x180019a66  jmp     short loc_180019A6D
0x180019a68  mov     ecx, 2
0x180019a6d  mov     edx, [rdx]
0x180019a6f  mov     ebx, 1
0x180019a74  xor     eax, eax
0x180019a76  mov     r8d, ecx
0x180019a79  or      r8d, edx
0x180019a7c  cmp     r8d, edx
0x180019a7f  mov     r9d, r8d
0x180019a82  setz    al
0x180019a85  or      r9d, ebx
0x180019a88  cmp     r8d, edx
0x180019a8b  mov     [r10+10h], eax
0x180019a8f  mov     eax, edx
0x180019a91  cmovz   r9d, r8d
0x180019a95  lock cmpxchg [rsi], r9d
0x180019a9a  jz      short loc_180019AA0
0x180019a9c  mov     edx, eax
0x180019a9e  jmp     short loc_180019A74
0x180019aa0  test    bl, r9b
0x180019aa3  jz      short loc_180019AA9
0x180019aa5  test    bl, dl
0x180019aa7  jz      short loc_180019AAB
0x180019aa9  xor     ebx, ebx
0x180019aab  mov     [r10], ebx
0x180019aae  jmp     loc_180019C3A
0x180019ab3  mov     ecx, [rdx]
0x180019ab5  xor     r9d, r9d
0x180019ab8  cmp     r11d, 5
0x180019abc  mov     ebx, 1
0x180019ac1  setz    r9b
0x180019ac5  mov     eax, ecx
0x180019ac7  mov     dword ptr [r10+4], 0
0x180019acf  or      eax, ebx
0x180019ad1  mov     edx, eax
0x180019ad3  shr     edx, 16h
0x180019ad6  and     edx, ebx
0x180019ad8  cmp     edx, r9d
0x180019adb  jz      short loc_180019B1D
0x180019add  mov     r8d, eax
0x180019ae0  shr     r8d, 0Fh
0x180019ae4  and     r8d, 7Fh
0x180019ae8  jbe     short loc_180019B02
0x180019aea  cmp     r11d, ebx
0x180019aed  mov     [r10+4], r8d
0x180019af1  mov     edx, 5
0x180019af6  cmovnz  edx, ebx
0x180019af9  and     eax, 0FFC07FFFh
0x180019afe  mov     [r10+8], edx
0x180019b02  xor     r8d, r8d
0x180019b05  mov     edx, 400000h
0x180019b0a  cmp     r11d, 5
0x180019b0e  cmovz   r8d, edx
0x180019b12  mov     edx, eax
0x180019b14  btr     edx, 16h
0x180019b18  mov     eax, r8d
0x180019b1b  or      eax, edx
0x180019b1d  mov     edx, eax
0x180019b1f  shr     edx, 0Fh
0x180019b22  and     edx, 7Fh
0x180019b25  lea     r8d, [rdx+1]
0x180019b29  cmp     r8d, 7Fh
0x180019b2d  ja      short loc_180019B34
0x180019b2f  cmp     r8d, edx
0x180019b32  jnb     short loc_180019B3F
0x180019b34  mov     r8d, ebx
0x180019b37  mov     [r10+8], r11d
0x180019b3b  mov     [r10+4], edx
0x180019b3f  shl     r8d, 0Fh
0x180019b43  xor     r8d, eax
0x180019b46  and     r8d, 3F8000h
0x180019b4d  xor     r8d, eax
0x180019b50  mov     eax, ecx
0x180019b52  lock cmpxchg [rsi], r8d
0x180019b57  jz      short loc_180019B60
0x180019b59  mov     ecx, eax
0x180019b5b  jmp     loc_180019AC5
0x180019b60  not     ecx
0x180019b62  and     ecx, ebx
0x180019b64  mov     [r10], ecx
0x180019b67  jmp     loc_180019C32
0x180019b6c  mov     edx, [rdx]
0x180019b6e  xor     ebp, ebp
0x180019b70  lea     ecx, [rbp+4]
0x180019b73  cmp     r11d, ecx
0x180019b76  lea     ebx, [rcx-3]
0x180019b79  setz    bpl
0x180019b7d  mov     eax, edx
0x180019b7f  mov     dword ptr [r10+4], 0
0x180019b87  or      eax, ebx
0x180019b89  mov     r8d, eax
0x180019b8c  shr     r8d, 0Eh
0x180019b90  and     r8d, ebx
0x180019b93  cmp     r8d, ebp
0x180019b96  jz      short loc_180019BDF
0x180019b98  mov     edi, eax
0x180019b9a  shr     edi, 5
0x180019b9d  and     edi, 1FFh
0x180019ba3  jbe     short loc_180019BC1
0x180019ba5  mov     r8d, r11d
0x180019ba8  mov     [r10+4], edi
0x180019bac  neg     r8d
0x180019baf  sbb     r9d, r9d
0x180019bb2  not     r9d
0x180019bb5  and     r9d, ecx
0x180019bb8  mov     [r10+8], r9d
0x180019bbc  and     eax, 0FFFFC01Fh
0x180019bc1  xor     r9d, r9d
0x180019bc4  mov     r8d, 4000h
0x180019bca  cmp     r11d, ecx
0x180019bcd  cmovz   r9d, r8d
0x180019bd1  mov     r8d, eax
0x180019bd4  btr     r8d, 0Eh
0x180019bd9  mov     eax, r9d
0x180019bdc  or      eax, r8d
0x180019bdf  mov     r8d, eax
0x180019be2  shr     r8d, 5
0x180019be6  and     r8d, 1FFh
0x180019bed  lea     r9d, [r8+1]
0x180019bf1  cmp     r9d, 1FFh
0x180019bf8  ja      short loc_180019BFF
0x180019bfa  cmp     r9d, r8d
0x180019bfd  jnb     short loc_180019C0A
0x180019bff  mov     r9d, ebx
0x180019c02  mov     [r10+8], r11d
0x180019c06  mov     [r10+4], r8d
0x180019c0a  shl     r9d, 5
0x180019c0e  xor     r9d, eax
0x180019c11  and     r9d, 3FE0h
0x180019c18  xor     r9d, eax
0x180019c1b  mov     eax, edx
0x180019c1d  lock cmpxchg [rsi], r9d
0x180019c22  jz      short loc_180019C2B
0x180019c24  mov     edx, eax
0x180019c26  jmp     loc_180019B7D
0x180019c2b  not     edx
0x180019c2d  and     edx, ebx
0x180019c2f  mov     [r10], edx
0x180019c32  mov     dword ptr [r10+10h], 0
0x180019c3a  mov     rax, r10
0x180019c3d  pop     rdi
0x180019c3e  pop     rsi
0x180019c3f  pop     rbp
0x180019c40  pop     rbx
0x180019c41  retn
```
