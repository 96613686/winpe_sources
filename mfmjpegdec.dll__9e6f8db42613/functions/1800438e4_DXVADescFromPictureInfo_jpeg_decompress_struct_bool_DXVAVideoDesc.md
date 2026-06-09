# DXVADescFromPictureInfo(jpeg_decompress_struct &,bool,DXVAVideoDesc &)

- ea: `0x1800438e4`
- end: `0x180043aac`
- name: `?DXVADescFromPictureInfo@@YAJAEAUjpeg_decompress_struct@@_NAEAUDXVAVideoDesc@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct jpeg_decompress_struct *, char, struct DXVAVideoDesc *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180043e00`
- `0x180043e94`

## callees

- `0x1800438e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DXVADescFromPictureInfo(struct jpeg_decompress_struct *a1, char a2, struct DXVAVideoDesc *a3)
{
  __int64 v4; // r9
  int v6; // ebx
  int v7; // r14d
  int v8; // ebp
  __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  int v12; // edi
  int v13; // r11d
  __int64 v14; // r15
  __int64 v15; // rcx
  __int64 result; // rax
  __int128 v17; // xmm0
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx

  v4 = 0;
  *(_DWORD *)a3 = (*((_DWORD *)a1 + 12) + 15) & 0xFFFFFFF0;
  *((_DWORD *)a3 + 1) = (*((_DWORD *)a1 + 13) + 15) & 0xFFFFFFF0;
  v6 = *((_DWORD *)a1 + 14);
  v7 = 8;
  v8 = 8;
  if ( v6 > 0 )
  {
    do
    {
      if ( a1 == (struct jpeg_decompress_struct *)-408LL )
        break;
      v9 = *((_QWORD *)a1 + v4 + 51);
      v4 = (unsigned int)(v4 + 1);
      v10 = *(_DWORD *)(v9 + 8);
      v11 = *(_DWORD *)(v9 + 12);
      if ( v10 >= v7 )
        v10 = v7;
      v7 = v10;
      if ( v11 >= v8 )
        v11 = v8;
      v8 = v11;
    }
    while ( (int)v4 < v6 );
    if ( !v7 || !v8 )
      return 3222130769LL;
  }
  v12 = 0;
  while ( 1 )
  {
    if ( v6 == LODWORD(qword_18009C530[10 * v12]) && *((_DWORD *)a1 + 70) == HIDWORD(qword_18009C530[10 * v12]) )
    {
      v13 = 0;
      if ( v6 > 0 )
      {
        if ( a1 != (struct jpeg_decompress_struct *)-408LL )
        {
          while ( 1 )
          {
            v14 = *((_QWORD *)a1 + v13 + 51);
            v15 = v13 + 20LL * v12;
            if ( *(_DWORD *)(v14 + 8) / v7 != *((_DWORD *)&qword_18009C530[1] + v15)
              || *(_DWORD *)(v14 + 12) / v8 != *((_DWORD *)&qword_18009C530[3] + v15) )
            {
              break;
            }
            if ( ++v13 >= v6 )
              goto LABEL_18;
          }
        }
        goto LABEL_20;
      }
LABEL_18:
      if ( v13 == v6 && a2 == LOBYTE(qword_18009C530[10 * v12 + 5]) )
        break;
    }
LABEL_20:
    if ( (unsigned int)++v12 >= 7 )
      return 3222130769LL;
  }
  *((_DWORD *)a3 + 2) = HIDWORD(qword_18009C530[10 * v12 + 5]);
  v17 = *(_OWORD *)&qword_18009C530[10 * v12 + 6];
  *((_DWORD *)a3 + 8) = 2;
  *((_DWORD *)a3 + 9) = 2;
  *(_OWORD *)((char *)a3 + 12) = v17;
  v18 = *((_DWORD *)a1 + 15);
  if ( v18 > 8 )
  {
    v24 = v18 - 9;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              v23 = v28 - 1;
              if ( v23 )
              {
LABEL_38:
                if ( (unsigned int)(v23 - 1) >= 2 )
                  goto LABEL_39;
              }
            }
          }
        }
      }
    }
LABEL_40:
    *((_DWORD *)a3 + 7) = 0;
    goto LABEL_41;
  }
  if ( v18 == 8 )
    goto LABEL_40;
  if ( !v18 )
    goto LABEL_39;
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_39;
  v20 = v19 - 1;
  if ( !v20 )
    goto LABEL_40;
  v21 = v20 - 1;
  if ( v21 )
  {
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
        goto LABEL_38;
    }
LABEL_39:
    *((_DWORD *)a3 + 7) = -1;
  }
  else
  {
    *((_DWORD *)a3 + 7) = 5;
  }
LABEL_41:
  *((_DWORD *)a3 + 10) = 30;
  result = 0;
  *((_DWORD *)a3 + 11) = 1;
  return result;
}

```

## disassembly

```asm
0x1800438e4  push    rbx
0x1800438e6  push    rbp
0x1800438e7  push    rsi
0x1800438e8  push    rdi
0x1800438e9  push    r12
0x1800438eb  push    r13
0x1800438ed  push    r14
0x1800438ef  push    r15
0x1800438f1  mov     eax, [rcx+30h]
0x1800438f4  mov     r10, rcx
0x1800438f7  add     eax, 0Fh
0x1800438fa  mov     ecx, 0FFFFFFF0h
0x1800438ff  and     eax, ecx
0x180043901  xor     r9d, r9d
0x180043904  mov     [r8], eax
0x180043907  mov     r12b, dl
0x18004390a  mov     eax, [r10+34h]
0x18004390e  add     eax, 0Fh
0x180043911  and     eax, ecx
0x180043913  mov     [r8+4], eax
0x180043917  mov     eax, 8
0x18004391c  mov     ebx, [r10+38h]
0x180043920  mov     r14d, eax
0x180043923  mov     ebp, eax
0x180043925  test    ebx, ebx
0x180043927  jle     short loc_18004396D
0x180043929  lea     r11, [r10+198h]
0x180043930  test    r11, r11
0x180043933  jz      short loc_18004395C
0x180043935  mov     rcx, [r10+r9*8+198h]
0x18004393d  inc     r9d
0x180043940  mov     eax, [rcx+8]
0x180043943  cmp     eax, r14d
0x180043946  mov     edx, [rcx+0Ch]
0x180043949  cmovge  eax, r14d
0x18004394d  cmp     edx, ebp
0x18004394f  mov     r14d, eax
0x180043952  cmovge  edx, ebp
0x180043955  mov     ebp, edx
0x180043957  cmp     r9d, ebx
0x18004395a  jl      short loc_180043930
0x18004395c  test    r14d, r14d
0x18004395f  jz      loc_1800439F3
0x180043965  test    ebp, ebp
0x180043967  jz      loc_1800439F3
0x18004396d  xor     edi, edi
0x18004396f  lea     r13, qword_18009C530
0x180043976  movsxd  rsi, edi
0x180043979  lea     r9, [rsi+rsi*4]
0x18004397d  add     r9, r9
0x180043980  cmp     ebx, [r13+r9*8+0]
0x180043985  jnz     short loc_1800439EC
0x180043987  mov     eax, [r13+r9*8+4]
0x18004398c  cmp     [r10+118h], eax
0x180043993  jnz     short loc_1800439EC
0x180043995  xor     r11d, r11d
0x180043998  test    ebx, ebx
0x18004399a  jle     short loc_1800439E0
0x18004399c  lea     rax, [r10+198h]
0x1800439a3  test    rax, rax
0x1800439a6  jz      short loc_1800439EC
0x1800439a8  movsxd  rdx, r11d
0x1800439ab  lea     rcx, [rsi+rsi*4]
0x1800439af  mov     r15, [r10+rdx*8+198h]
0x1800439b7  lea     rcx, [rdx+rcx*4]
0x1800439bb  mov     eax, [r15+8]
0x1800439bf  cdq
0x1800439c0  idiv    r14d
0x1800439c3  cmp     eax, [r13+rcx*4+8]
0x1800439c8  jnz     short loc_1800439EC
0x1800439ca  mov     eax, [r15+0Ch]
0x1800439ce  cdq
0x1800439cf  idiv    ebp
0x1800439d1  cmp     eax, [r13+rcx*4+18h]
0x1800439d6  jnz     short loc_1800439EC
0x1800439d8  inc     r11d
0x1800439db  cmp     r11d, ebx
0x1800439de  jl      short loc_1800439A8
0x1800439e0  cmp     r11d, ebx
0x1800439e3  jnz     short loc_1800439EC
0x1800439e5  cmp     r12b, [r13+r9*8+28h]
0x1800439ea  jz      short loc_180043A05
0x1800439ec  inc     edi
0x1800439ee  cmp     edi, 7
0x1800439f1  jb      short loc_180043976
0x1800439f3  mov     eax, 0C00DD051h
0x1800439f8  pop     r15
0x1800439fa  pop     r14
0x1800439fc  pop     r13
0x1800439fe  pop     r12
0x180043a00  pop     rdi
0x180043a01  pop     rsi
0x180043a02  pop     rbp
0x180043a03  pop     rbx
0x180043a04  retn
0x180043a05  mov     eax, [r13+r9*8+2Ch]
0x180043a0a  mov     [r8+8], eax
0x180043a0e  mov     eax, 2
0x180043a13  movups  xmm0, xmmword ptr [r13+r9*8+30h]
0x180043a19  mov     [r8+20h], eax
0x180043a1d  mov     [r8+24h], eax
0x180043a21  movdqu  xmmword ptr [r8+0Ch], xmm0
0x180043a27  mov     ecx, [r10+3Ch]
0x180043a2b  cmp     ecx, 8
0x180043a2e  jg      short loc_180043A5B
0x180043a30  jz      short loc_180043A8D
0x180043a32  test    ecx, ecx
0x180043a34  jz      short loc_180043A83
0x180043a36  sub     ecx, 1
0x180043a39  jz      short loc_180043A83
0x180043a3b  sub     ecx, 1
0x180043a3e  jz      short loc_180043A8D
0x180043a40  sub     ecx, 1
0x180043a43  jz      short loc_180043A51
0x180043a45  sub     ecx, 1
0x180043a48  jz      short loc_180043A83
0x180043a4a  sub     ecx, 1
0x180043a4d  jz      short loc_180043A83
0x180043a4f  jmp     short loc_180043A79
0x180043a51  mov     dword ptr [r8+1Ch], 5
0x180043a59  jmp     short loc_180043A95
0x180043a5b  sub     ecx, 9
0x180043a5e  jz      short loc_180043A8D
0x180043a60  sub     ecx, 1
0x180043a63  jz      short loc_180043A8D
0x180043a65  sub     ecx, 1
0x180043a68  jz      short loc_180043A8D
0x180043a6a  sub     ecx, 1
0x180043a6d  jz      short loc_180043A8D
0x180043a6f  sub     ecx, 1
0x180043a72  jz      short loc_180043A8D
0x180043a74  sub     ecx, 1
0x180043a77  jz      short loc_180043A8D
0x180043a79  sub     ecx, 1
0x180043a7c  jz      short loc_180043A8D
0x180043a7e  cmp     ecx, 1
0x180043a81  jz      short loc_180043A8D
0x180043a83  mov     dword ptr [r8+1Ch], 0FFFFFFFFh
0x180043a8b  jmp     short loc_180043A95
0x180043a8d  mov     dword ptr [r8+1Ch], 0
0x180043a95  mov     dword ptr [r8+28h], 1Eh
0x180043a9d  xor     eax, eax
0x180043a9f  mov     dword ptr [r8+2Ch], 1
0x180043aa7  jmp     loc_1800439F8
```
