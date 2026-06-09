# OptimalEncoderMoveWindows

- ea: `0x180005b08`
- end: `0x180005be8`
- name: `OptimalEncoderMoveWindows`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x180005b08`
- `0x180006ac9`

## pseudocode

```c
__int16 __fastcall OptimalEncoderMoveWindows(__int64 a1)
{
  __int64 v1; // rdi
  int v3; // esi
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 i; // rdx
  __int16 v7; // ax
  __int64 j; // rdx
  __int16 v9; // ax
  __int16 result; // ax

  v1 = *(_QWORD *)(a1 + 88);
  v3 = *(_DWORD *)(a1 + 32) - 0x8000;
  v4 = v1 + 82412;
  v5 = v1 + 213484;
  memcpy_0((void *)v1, (const void *)(v1 + v3), 0x8000u);
  for ( i = 0; i != 0x10000; ++i )
  {
    v7 = 0;
    if ( *(unsigned __int16 *)(v1 + 2 * i + 344556) - v3 > 0 )
      v7 = *(_WORD *)(v1 + 2 * i + 344556) - v3;
    *(_WORD *)(v1 + 2 * i + 344556) = v7;
  }
  memcpy_0((void *)(v1 + 82412), (const void *)(v4 + 2LL * (*(_DWORD *)(a1 + 32) - 0x8000)), 0x10000u);
  memcpy_0((void *)(v1 + 213484), (const void *)(v5 + 2LL * (*(_DWORD *)(a1 + 32) - 0x8000)), 0x10000u);
  for ( j = 0; j != 0x8000; ++j )
  {
    v9 = 0;
    if ( *(unsigned __int16 *)(v4 + 2 * j) - v3 > 0 )
      v9 = *(_WORD *)(v4 + 2 * j) - v3;
    *(_WORD *)(v4 + 2 * j) = v9;
    result = 0;
    if ( *(unsigned __int16 *)(v5 + 2 * j) - v3 > 0 )
      result = *(_WORD *)(v5 + 2 * j) - v3;
    *(_WORD *)(v5 + 2 * j) = result;
  }
  *(_DWORD *)(a1 + 32) = 0x8000;
  *(_DWORD *)(a1 + 36) = 0x8000;
  return result;
}

```

## disassembly

```asm
0x180005b08  push    rbx
0x180005b0a  push    rbp
0x180005b0b  push    rsi
0x180005b0c  push    rdi
0x180005b0d  push    r12
0x180005b0f  push    r14
0x180005b11  push    r15
0x180005b13  sub     rsp, 20h
0x180005b17  mov     rdi, [rcx+58h]
0x180005b1b  mov     rbx, rcx
0x180005b1e  mov     esi, [rcx+20h]
0x180005b21  mov     ebp, 8000h
0x180005b26  add     esi, 0FFFF8000h
0x180005b2c  mov     r8d, ebp; Size
0x180005b2f  movsxd  rdx, esi
0x180005b32  mov     rcx, rdi; void *
0x180005b35  add     rdx, rdi; Src
0x180005b38  lea     r14, [rdi+141ECh]
0x180005b3f  lea     r15, [rdi+341ECh]
0x180005b46  call    memcpy_0
0x180005b4b  xor     edx, edx
0x180005b4d  mov     r12d, 10000h
0x180005b53  movzx   ecx, word ptr [rdi+rdx*2+541ECh]
0x180005b5b  xor     eax, eax
0x180005b5d  sub     ecx, esi
0x180005b5f  test    ecx, ecx
0x180005b61  cmovg   ax, cx
0x180005b65  mov     [rdi+rdx*2+541ECh], ax
0x180005b6d  inc     rdx
0x180005b70  cmp     rdx, r12
0x180005b73  jnz     short loc_180005B53
0x180005b75  mov     eax, [rbx+20h]
0x180005b78  mov     r8, r12; Size
0x180005b7b  sub     eax, ebp
0x180005b7d  mov     rcx, r14; void *
0x180005b80  cdqe
0x180005b82  lea     rdx, [r14+rax*2]; Src
0x180005b86  call    memcpy_0
0x180005b8b  mov     eax, [rbx+20h]
0x180005b8e  mov     r8, r12; Size
0x180005b91  sub     eax, ebp
0x180005b93  mov     rcx, r15; void *
0x180005b96  cdqe
0x180005b98  lea     rdx, [r15+rax*2]; Src
0x180005b9c  call    memcpy_0
0x180005ba1  xor     edx, edx
0x180005ba3  movzx   ecx, word ptr [r14+rdx*2]
0x180005ba8  xor     eax, eax
0x180005baa  sub     ecx, esi
0x180005bac  test    ecx, ecx
0x180005bae  cmovg   ax, cx
0x180005bb2  mov     [r14+rdx*2], ax
0x180005bb7  xor     eax, eax
0x180005bb9  movzx   ecx, word ptr [r15+rdx*2]
0x180005bbe  sub     ecx, esi
0x180005bc0  test    ecx, ecx
0x180005bc2  cmovg   ax, cx
0x180005bc6  mov     [r15+rdx*2], ax
0x180005bcb  inc     rdx
0x180005bce  cmp     rdx, rbp
0x180005bd1  jnz     short loc_180005BA3
0x180005bd3  mov     [rbx+20h], ebp
0x180005bd6  mov     [rbx+24h], ebp
0x180005bd9  add     rsp, 20h
0x180005bdd  pop     r15
0x180005bdf  pop     r14
0x180005be1  pop     r12
0x180005be3  pop     rdi
0x180005be4  pop     rsi
0x180005be5  pop     rbp
0x180005be6  pop     rbx
0x180005be7  retn
```
