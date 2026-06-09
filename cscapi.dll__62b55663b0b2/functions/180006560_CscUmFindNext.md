# CscUmFindNext

- ea: `0x180006560`
- end: `0x180006747`
- name: `CscUmFindNext`
- size: `487`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180001020`
- `0x1800016b0`
- `0x180002080`

## callees

- `0x180002a20`
- `0x180006460`
- `0x180006560`
- `0x180009456`
- `0x180009462`
- `0x180009490`

## pseudocode

```c
__int64 __fastcall CscUmFindNext(__int64 a1, _WORD *a2, _OWORD *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r9
  BOOLEAN v8; // cl
  struct _UNICODE_STRING *v9; // r15
  unsigned int Directory; // ebp
  size_t v11; // r14
  size_t v12; // r8
  unsigned __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-338h]
  __int64 v16; // [rsp+28h] [rbp-330h]
  _DWORD v17[4]; // [rsp+40h] [rbp-318h] BYREF
  _DWORD v18[15]; // [rsp+50h] [rbp-308h] BYREF
  size_t Size; // [rsp+8Ch] [rbp-2CCh]
  char v20; // [rsp+94h] [rbp-2C4h]
  _BYTE v21[24]; // [rsp+96h] [rbp-2C2h] BYREF
  _WORD Src[305]; // [rsp+AEh] [rbp-2AAh] BYREF

  v17[0] = 0;
  if ( !CscUmpLibraryState )
    return 3221225860LL;
  if ( !(unsigned __int8)IsValidCscEnumHandle() || !v6 )
    return (unsigned int)-1073741811;
  v8 = 0;
  if ( *(_BYTE *)(a1 + 32) )
  {
    v8 = 1;
    *(_BYTE *)(a1 + 32) = 0;
  }
  v9 = (struct _UNICODE_STRING *)(a1 + 16);
  if ( !*(_WORD *)(a1 + 16) )
    v9 = 0;
  while ( 1 )
  {
    Directory = CscDriverQueryDirectory(*(void **)(a1 + 8), v17, v18, v7, v15, v16, v9, v8);
    if ( (Directory & 0x80000000) != 0 )
      return Directory;
    v11 = (unsigned int)Size;
    if ( (_DWORD)Size != 2 )
      break;
    if ( Src[0] != 46 )
      goto LABEL_11;
LABEL_16:
    v8 = 0;
  }
  if ( (_DWORD)Size == 4 && Src[0] == 46 && Src[1] == 46 )
    goto LABEL_16;
LABEL_11:
  memset_0(a2, 0, 0x226u);
  if ( (unsigned int)v11 > 0x206 )
    return (unsigned int)-1073741823;
  *a2 = v11;
  memcpy_0(a2 + 2, Src, v11);
  v12 = v20;
  if ( (unsigned __int64)v20 > 0x18 )
    return (unsigned int)-1073741823;
  a2[1] = v20;
  memcpy_0(a2 + 262, v21, v12);
  if ( !a3 )
    return Directory;
  v13 = ((unsigned int)(v11 + 94) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( *(_DWORD *)((char *)v18 + v13) != 1542600881 )
    return (unsigned int)-1073741823;
  *a3 = *(_OWORD *)((char *)&v18[2] + v13);
  a3[1] = *(_OWORD *)((char *)&v18[6] + v13);
  a3[2] = *(_OWORD *)((char *)&v18[10] + v13);
  a3[3] = *(_OWORD *)((char *)&v18[14] + v13);
  a3[4] = *(_OWORD *)&v21[v13 + 2];
  return Directory;
}

```

## disassembly

```asm
0x180006560  mov     r11, rsp
0x180006563  push    rbx
0x180006564  push    rsi
0x180006565  push    rdi
0x180006566  sub     rsp, 340h
0x18000656d  mov     rax, cs:__security_cookie
0x180006574  xor     rax, rsp
0x180006577  mov     [rsp+358h+var_48], rax
0x18000657f  cmp     cs:CscUmpLibraryState, 0
0x180006586  mov     rsi, r8
0x180006589  mov     rbx, rdx
0x18000658c  mov     [rsp+358h+var_318], 0
0x180006594  mov     rdi, rcx
0x180006597  jz      loc_180006727
0x18000659d  mov     [r11-20h], rbp
0x1800065a1  mov     [r11-28h], r12
0x1800065a5  mov     [r11-30h], r14
0x1800065a9  mov     [r11-38h], r15
0x1800065ad  call    IsValidCscEnumHandle
0x1800065b2  test    al, al
0x1800065b4  jz      loc_1800066FE
0x1800065ba  test    rdx, rdx
0x1800065bd  jz      loc_1800066FE
0x1800065c3  xor     cl, cl
0x1800065c5  cmp     [rdi+20h], cl
0x1800065c8  jz      short loc_1800065D0
0x1800065ca  mov     cl, 1
0x1800065cc  mov     byte ptr [rdi+20h], 0
0x1800065d0  lea     r15, [rdi+10h]
0x1800065d4  xor     eax, eax
0x1800065d6  cmp     [r15], ax
0x1800065da  mov     r12d, 2Eh ; '.'
0x1800065e0  cmovz   r15, rax
0x1800065e4  mov     [rsp+358h+var_320], cl
0x1800065e8  lea     r8, [rsp+358h+var_308]
0x1800065ed  mov     rcx, [rdi+8]
0x1800065f1  lea     rdx, [rsp+358h+var_318]
0x1800065f6  mov     [rsp+358h+var_328], r15
0x1800065fb  call    CscDriverQueryDirectory
0x180006600  mov     ebp, eax
0x180006602  test    eax, eax
0x180006604  js      loc_180006703
0x18000660a  mov     r14d, dword ptr [rsp+358h+Size]
0x180006612  cmp     r14d, 2
0x180006616  jnz     short loc_180006646
0x180006618  cmp     r12w, [rsp+358h+Src]
0x180006621  jz      short loc_180006662
0x180006623  xor     edx, edx; Val
0x180006625  mov     r8d, 226h; Size
0x18000662b  mov     rcx, rbx; void *
0x18000662e  call    memset_0
0x180006633  cmp     r14d, 206h
0x18000663a  jbe     short loc_180006669
0x18000663c  mov     ebp, 0C0000001h
0x180006641  jmp     loc_180006703
0x180006646  cmp     r14d, 4
0x18000664a  jnz     short loc_180006623
0x18000664c  cmp     r12w, [rsp+358h+Src]
0x180006655  jnz     short loc_180006623
0x180006657  cmp     r12w, [rsp+358h+var_2A8]
0x180006660  jnz     short loc_180006623
0x180006662  xor     cl, cl
0x180006664  jmp     loc_1800065E4
0x180006669  mov     r8, r14; Size
0x18000666c  mov     [rbx], r14w
0x180006670  lea     rcx, [rbx+4]; void *
0x180006674  lea     rdx, [rsp+358h+Src]; Src
0x18000667c  call    memcpy_0
0x180006681  movsx   rax, [rsp+358h+var_2C4]
0x18000668a  mov     r8, rax; Size
0x18000668d  cmp     rax, 18h
0x180006691  ja      short loc_18000663C
0x180006693  lea     rcx, [rbx+20Ch]; void *
0x18000669a  mov     [rbx+2], ax
0x18000669e  lea     rdx, [rsp+358h+var_2C2]; Src
0x1800066a6  call    memcpy_0
0x1800066ab  test    rsi, rsi
0x1800066ae  jz      short loc_180006703
0x1800066b0  lea     ecx, [r14+5Eh]
0x1800066b4  add     rcx, 7
0x1800066b8  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800066bc  cmp     [rsp+rcx+358h+var_308], 5BF238B1h
0x1800066c4  jnz     loc_18000663C
0x1800066ca  movups  xmm0, [rsp+rcx+358h+var_300]
0x1800066cf  movaps  xmmword ptr [rsi], xmm0
0x1800066d2  movups  xmm1, [rsp+rcx+358h+var_2F0]
0x1800066d7  movaps  xmmword ptr [rsi+10h], xmm1
0x1800066db  movups  xmm0, [rsp+rcx+358h+var_2E0]
0x1800066e0  movaps  xmmword ptr [rsi+20h], xmm0
0x1800066e4  movups  xmm1, xmmword ptr [rsp+rcx+88h]
0x1800066ec  movaps  xmmword ptr [rsi+30h], xmm1
0x1800066f0  movups  xmm0, [rsp+rcx+358h+var_2C0]
0x1800066f8  movaps  xmmword ptr [rsi+40h], xmm0
0x1800066fc  jmp     short loc_180006703
0x1800066fe  mov     ebp, 0C000000Dh
0x180006703  mov     r15, [rsp+358h+var_38]
0x18000670b  mov     eax, ebp
0x18000670d  mov     rbp, [rsp+358h+var_20]
0x180006715  mov     r14, [rsp+358h+var_30]
0x18000671d  mov     r12, [rsp+358h+var_28]
0x180006725  jmp     short loc_18000672C
0x180006727  mov     eax, 0C0000184h
0x18000672c  mov     rcx, [rsp+358h+var_48]
0x180006734  xor     rcx, rsp; StackCookie
0x180006737  call    __security_check_cookie
0x18000673c  add     rsp, 340h
0x180006743  pop     rdi
0x180006744  pop     rsi
0x180006745  pop     rbx
0x180006746  retn
```
