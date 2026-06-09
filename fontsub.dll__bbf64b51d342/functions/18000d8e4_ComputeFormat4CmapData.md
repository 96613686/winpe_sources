# ComputeFormat4CmapData

- ea: `0x18000d8e4`
- end: `0x18000db60`
- name: `ComputeFormat4CmapData`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a8dc`
- `0x1800118bc`

## callees

- `0x18000d8e4`
- `0x180014ca0`
- `0x18001a2cc`

## pseudocode

```c
__int64 __fastcall ComputeFormat4CmapData(
        _WORD *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        _WORD *a5,
        __int64 a6,
        unsigned __int16 a7)
{
  _WORD *v7; // r13
  unsigned __int16 v8; // r12
  unsigned __int16 v10; // r10
  __int64 v11; // r14
  __int64 v12; // rbp
  int v13; // r8d
  unsigned __int16 i; // si
  __int64 v15; // rax
  int v16; // ecx
  __int16 v17; // cx
  __int16 v18; // ax
  __int16 v19; // cx
  unsigned __int16 v20; // si
  unsigned __int16 v21; // r14
  unsigned __int16 v22; // r10
  unsigned __int16 v23; // bp
  unsigned __int16 v24; // r8
  unsigned __int16 v25; // dx
  unsigned __int16 v26; // cx
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int16 v29; // si
  __int16 v30; // bx
  __int16 v31; // bx
  __int16 v32; // ax
  unsigned __int16 v33; // di
  __int64 result; // rax
  __int16 v35; // r9

  v7 = a5;
  v8 = 0;
  v10 = 0;
  *a5 = 0;
  if ( a7 )
  {
    do
    {
      v11 = v10;
      while ( v10 < a7 - 1 && *(unsigned __int16 *)(a6 + 4LL * v10) + 1 == *(unsigned __int16 *)(a6 + 4LL * v10 + 4) )
        ++v10;
      v12 = v10;
      v13 = 1;
      ++v10;
      for ( i = v11; i < (unsigned __int16)v12; v13 = v16 )
      {
        if ( !v13 )
          break;
        v15 = i;
        v16 = 0;
        ++i;
        if ( *(unsigned __int16 *)(a6 + 4 * v15 + 2) + 1 == *(unsigned __int16 *)(a6 + 4 * v15 + 6) )
          v16 = v13;
      }
      *(_WORD *)(a2 + 8LL * v8 + 2) = *(_WORD *)(a6 + 4 * v11);
      *(_WORD *)(a2 + 8LL * v8) = *(_WORD *)(a6 + 4 * v12);
      if ( v13 )
      {
        v17 = 0;
        v18 = *(_WORD *)(a6 + 4 * v11 + 2) - *(_WORD *)(a6 + 4 * v11);
      }
      else
      {
        v17 = 1;
        v18 = 0;
      }
      *(_WORD *)(a2 + 8LL * v8 + 4) = v18;
      *(_WORD *)(a2 + 8LL * v8 + 6) = v17;
      v19 = ++v8;
    }
    while ( v10 < a7 );
    v20 = v19;
    v7 = a5;
    if ( v19 )
    {
      v21 = 0;
      v22 = 0;
      do
      {
        v23 = *(_WORD *)(a2 + 8LL * v22 + 2);
        v24 = *(_WORD *)(a2 + 8LL * v22);
        if ( *(_WORD *)(a2 + 8LL * v22 + 6) )
        {
          v25 = *a5;
          *(_WORD *)(a2 + 8LL * v22 + 6) = 2 * (v19 + *a5 - v22 + 1);
          if ( v23 <= v24 )
          {
            v26 = v25;
            do
            {
              v27 = v21;
              ++v25;
              ++v21;
              ++v23;
              *(_WORD *)(a4 + 2LL * v26) = *(_WORD *)(a6 + 4 * v27 + 2);
              v26 = v25;
            }
            while ( v23 <= *(_WORD *)(a2 + 8LL * v22) );
            *a5 = v25;
          }
        }
        else
        {
          *(_WORD *)(a2 + 8LL * v22 + 6) = 0;
          v21 += v24 - v23 + 1;
        }
        ++v22;
        v19 = v20;
      }
      while ( v22 < v20 );
    }
  }
  else
  {
    v20 = 0;
  }
  v28 = v20;
  v29 = v20 + 1;
  *a3 = v29;
  *(_DWORD *)(a2 + 8 * v28 + 4) = 1;
  *(_DWORD *)(a2 + 8 * v28) = -1;
  *a1 = 4;
  a1[2] = 0;
  v30 = v29 * GetGenericSize(&FORMAT4_SEGMENTS_CONTROL);
  v31 = GetGenericSize(&CMAP_FORMAT4_CONTROL) + v30;
  v32 = *v7 + 1;
  a1[3] = 2 * v29;
  a1[1] = 2 * v32 + v31;
  v33 = 1 << (log2ui16(v29) + 1);
  a1[4] = v33;
  result = log2ui16(v33 >> 1);
  a1[6] = v35 - v33;
  a1[5] = result;
  return result;
}

```

## disassembly

```asm
0x18000d8e4  mov     rax, rsp
0x18000d8e7  mov     [rax+10h], rbx
0x18000d8eb  mov     [rax+20h], r9
0x18000d8ef  mov     [rax+18h], r8
0x18000d8f3  mov     [rax+8], rcx
0x18000d8f7  push    rbp
0x18000d8f8  push    rsi
0x18000d8f9  push    rdi
0x18000d8fa  push    r12
0x18000d8fc  push    r13
0x18000d8fe  push    r14
0x18000d900  push    r15
0x18000d902  sub     rsp, 20h
0x18000d906  mov     r13, [rsp+58h+arg_20]
0x18000d90e  xor     r12d, r12d
0x18000d911  movzx   r15d, [rsp+58h+arg_30]
0x18000d91a  mov     r11, rdx
0x18000d91d  mov     rbx, [rsp+58h+arg_28]
0x18000d925  mov     r10d, r12d
0x18000d928  mov     [r13+0], r12w
0x18000d92d  lea     edi, [r12+1]
0x18000d932  cmp     r12w, r15w
0x18000d936  jnb     loc_18000DAAD
0x18000d93c  mov     r9d, r15d
0x18000d93f  sub     r9d, edi
0x18000d942  xor     r13d, r13d
0x18000d945  movzx   r14d, r10w
0x18000d949  jmp     short loc_18000D962
0x18000d94b  movzx   eax, r10w
0x18000d94f  movzx   ecx, word ptr [rbx+rax*4]
0x18000d953  movzx   eax, word ptr [rbx+rax*4+4]
0x18000d958  add     ecx, edi
0x18000d95a  cmp     ecx, eax
0x18000d95c  jnz     short loc_18000D96B
0x18000d95e  add     r10w, di
0x18000d962  movzx   eax, r10w
0x18000d966  cmp     eax, r9d
0x18000d969  jl      short loc_18000D94B
0x18000d96b  movzx   ebp, r10w
0x18000d96f  mov     r8d, edi
0x18000d972  add     r10w, di
0x18000d976  movzx   esi, r14w
0x18000d97a  cmp     r14w, bp
0x18000d97e  jnb     short loc_18000D9A8
0x18000d980  test    r8d, r8d
0x18000d983  jz      short loc_18000D9A8
0x18000d985  movzx   eax, si
0x18000d988  mov     ecx, r13d
0x18000d98b  add     si, di
0x18000d98e  movzx   edx, word ptr [rbx+rax*4+2]
0x18000d993  movzx   eax, word ptr [rbx+rax*4+6]
0x18000d998  add     edx, edi
0x18000d99a  cmp     edx, eax
0x18000d99c  cmovz   ecx, r8d
0x18000d9a0  mov     r8d, ecx
0x18000d9a3  cmp     si, bp
0x18000d9a6  jb      short loc_18000D980
0x18000d9a8  movzx   eax, word ptr [rbx+r14*4]
0x18000d9ad  movzx   edx, r12w
0x18000d9b1  mov     [r11+rdx*8+2], ax
0x18000d9b7  movzx   ecx, word ptr [rbx+rbp*4]
0x18000d9bb  mov     [r11+rdx*8], cx
0x18000d9c0  test    r8d, r8d
0x18000d9c3  jz      short loc_18000D9D5
0x18000d9c5  movzx   eax, word ptr [rbx+r14*4+2]
0x18000d9cb  mov     ecx, r13d
0x18000d9ce  sub     ax, [rbx+r14*4]
0x18000d9d3  jmp     short loc_18000D9DB
0x18000d9d5  movzx   ecx, di
0x18000d9d8  mov     eax, r13d
0x18000d9db  mov     [r11+rdx*8+4], ax
0x18000d9e1  mov     [r11+rdx*8+6], cx
0x18000d9e7  lea     ecx, [rdi+r12]
0x18000d9eb  movzx   r12d, cx
0x18000d9ef  cmp     r10w, r15w
0x18000d9f3  jb      loc_18000D945
0x18000d9f9  cmp     r13w, cx
0x18000d9fd  movzx   esi, cx
0x18000da00  mov     r13, [rsp+58h+arg_20]
0x18000da08  jnb     loc_18000DAA8
0x18000da0e  mov     r15, [rsp+58h+arg_18]
0x18000da13  xor     r12d, r12d
0x18000da16  mov     r14d, r12d
0x18000da19  mov     r10d, r12d
0x18000da1c  movzx   r9d, r10w
0x18000da20  movzx   ebp, word ptr [r11+r9*8+2]
0x18000da26  movzx   r8d, word ptr [r11+r9*8]
0x18000da2b  cmp     [r11+r9*8+6], r12w
0x18000da31  jnz     short loc_18000DA47
0x18000da33  sub     r8w, bp
0x18000da37  mov     [r11+r9*8+6], r12w
0x18000da3d  add     r8w, di
0x18000da41  add     r14w, r8w
0x18000da45  jmp     short loc_18000DA95
0x18000da47  movzx   edx, word ptr [r13+0]
0x18000da4c  movzx   eax, dx
0x18000da4f  sub     ax, r10w
0x18000da53  add     ax, cx
0x18000da56  add     ax, di
0x18000da59  add     ax, ax
0x18000da5c  mov     [r11+r9*8+6], ax
0x18000da62  cmp     bp, r8w
0x18000da66  ja      short loc_18000DA95
0x18000da68  movzx   ecx, dx
0x18000da6b  movzx   eax, r14w
0x18000da6f  add     dx, di
0x18000da72  movzx   ecx, cx
0x18000da75  add     r14w, di
0x18000da79  add     bp, di
0x18000da7c  movzx   eax, word ptr [rbx+rax*4+2]
0x18000da81  mov     [r15+rcx*2], ax
0x18000da86  movzx   ecx, dx
0x18000da89  cmp     bp, [r11+r9*8]
0x18000da8e  jbe     short loc_18000DA6B
0x18000da90  mov     [r13+0], dx
0x18000da95  add     r10w, di
0x18000da99  movzx   ecx, si
0x18000da9c  cmp     r10w, si
0x18000daa0  jb      loc_18000DA1C
0x18000daa6  jmp     short loc_18000DAB0
0x18000daa8  xor     r12d, r12d
0x18000daab  jmp     short loc_18000DAB0
0x18000daad  mov     esi, r12d
0x18000dab0  mov     rax, [rsp+58h+arg_10]
0x18000dab5  mov     r14, [rsp+58h+arg_0]
0x18000daba  movzx   ecx, si
0x18000dabd  add     si, di
0x18000dac0  mov     [rax], si
0x18000dac3  mov     [r11+rcx*8+4], edi
0x18000dac8  mov     dword ptr [r11+rcx*8], 0FFFFFFFFh
0x18000dad0  lea     rcx, FORMAT4_SEGMENTS_CONTROL
0x18000dad7  mov     word ptr [r14], 4
0x18000dadd  mov     [r14+4], r12w
0x18000dae2  call    GetGenericSize
0x18000dae7  movzx   ecx, si
0x18000daea  movzx   ebx, ax
0x18000daed  imul    ebx, ecx
0x18000daf0  lea     rcx, CMAP_FORMAT4_CONTROL
0x18000daf7  call    GetGenericSize
0x18000dafc  add     bx, ax
0x18000daff  movzx   r9d, si
0x18000db03  movzx   eax, word ptr [r13+0]
0x18000db08  add     r9w, r9w
0x18000db0c  add     ax, di
0x18000db0f  mov     [r14+6], r9w
0x18000db14  add     ax, ax
0x18000db17  movzx   ecx, si
0x18000db1a  add     bx, ax
0x18000db1d  mov     [r14+2], bx
0x18000db22  call    log2ui16
0x18000db27  lea     ecx, [rdi+rax]
0x18000db2a  shl     di, cl
0x18000db2d  movzx   ecx, di
0x18000db30  mov     [r14+8], di
0x18000db35  shr     cx, 1
0x18000db38  call    log2ui16
0x18000db3d  mov     rbx, [rsp+58h+arg_8]
0x18000db42  sub     r9w, di
0x18000db46  mov     [r14+0Ch], r9w
0x18000db4b  mov     [r14+0Ah], ax
0x18000db50  add     rsp, 20h
0x18000db54  pop     r15
0x18000db56  pop     r14
0x18000db58  pop     r13
0x18000db5a  pop     r12
0x18000db5c  pop     rdi
0x18000db5d  pop     rsi
0x18000db5e  pop     rbp
0x18000db5f  retn
```
