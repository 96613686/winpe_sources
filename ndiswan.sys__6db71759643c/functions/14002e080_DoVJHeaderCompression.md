# DoVJHeaderCompression

- ea: `0x14002e080`
- end: `0x14002e206`
- name: `DoVJHeaderCompression`
- size: `390`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140031b80`

## callees

- `0x140016400`
- `0x14002e080`
- `0x14002e99c`

## import_xrefs

- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14002e0e6`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14002e0e6`

## pseudocode

```c
__int64 __fastcall DoVJHeaderCompression(__int64 a1, __int64 a2, void **a3, int *a4, size_t Size)
{
  _DWORD *v5; // rdi
  int v8; // eax
  int v10; // r10d
  int v12; // edx
  unsigned int v13; // eax
  void *v14; // r8
  __int64 v15; // rcx
  int v16; // eax
  char v17; // al
  char v18; // r8
  void *v19; // r9
  char *v20; // rsi
  int v21; // r15d
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 result; // rax
  int v27; // ecx
  void *Src; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v30; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int64 v31; // [rsp+90h] [rbp+50h] BYREF

  v5 = (_DWORD *)Size;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v8 = *(_DWORD *)(a2 + 24);
  v10 = *(_DWORD *)Size;
  v12 = *(_DWORD *)(a2 + 16);
  v13 = v8 - *(_DWORD *)Size;
  v14 = *a3;
  v15 = *(_QWORD *)(a2 + 8);
  if ( v13 > 0x80 )
    v13 = 128;
  Src = v14;
  RtlCopyMdlToKernelBuffer(v15, (unsigned int)(v10 + v12), v14, v13, &v31);
  v16 = v31;
  if ( v31 > 0xFFFFFFFF )
  {
    LODWORD(Size) = -1;
    v16 = -1;
  }
  else
  {
    LODWORD(Size) = v31;
  }
  *v5 += v16;
  v17 = sl_compress_tcp(
          (unsigned int)&Src,
          (unsigned int)&Size,
          (unsigned int)&v29,
          (unsigned int)&v30,
          *(_QWORD *)(a1 + 400));
  v18 = v17;
  v19 = Src;
  if ( (*(_DWORD *)(a1 + 68) & 0x1000) != 0 )
    *(_BYTE *)Src |= v17;
  v20 = (char *)*a3;
  v21 = *a4;
  v22 = *(unsigned int *)(a1 + 1652) + ((unsigned __int64)*(unsigned int *)(a1 + 1736) << 32) + v29;
  v23 = *(unsigned int *)(a1 + 1660);
  *(_DWORD *)(a1 + 1652) += v29;
  *(_DWORD *)(a1 + 1736) = HIDWORD(v22);
  v24 = v30 + v23 + ((unsigned __int64)*(unsigned int *)(a1 + 1744) << 32);
  *(_DWORD *)(a1 + 1660) = v30 + v23;
  *(_DWORD *)(a1 + 1744) = HIDWORD(v24);
  if ( v18 == (char)0x80 )
  {
    v25 = (unsigned int)Size;
    memmove(v20, v19, (unsigned int)Size);
    *a3 = &v20[v25];
    *a4 = v21 + v25;
    return 45;
  }
  else
  {
    v27 = Size;
    *a3 = &v20[(unsigned int)Size];
    *a4 = v21 + v27;
    if ( v18 == 64 )
      return 33;
    result = 47;
    if ( v18 != 112 )
      return 33;
  }
  return result;
}

```

## disassembly

```asm
0x14002e080  mov     [rsp-38h+arg_18], rbx
0x14002e085  push    rbp
0x14002e086  push    rsi
0x14002e087  push    rdi
0x14002e088  push    r12
0x14002e08a  push    r13
0x14002e08c  push    r14
0x14002e08e  push    r15
0x14002e090  mov     rbp, rsp
0x14002e093  sub     rsp, 40h
0x14002e097  mov     rdi, [rbp+Size]
0x14002e09b  xor     eax, eax
0x14002e09d  mov     [rbp+arg_10], rax
0x14002e0a1  mov     r11, rdx
0x14002e0a4  mov     [rbp+arg_0], eax
0x14002e0a7  mov     r13d, 80h
0x14002e0ad  mov     [rbp+arg_8], eax
0x14002e0b0  mov     r12, r9
0x14002e0b3  mov     eax, [rdx+18h]
0x14002e0b6  mov     r14, r8
0x14002e0b9  mov     r10d, [rdi]
0x14002e0bc  mov     rbx, rcx
0x14002e0bf  mov     edx, [rdx+10h]
0x14002e0c2  sub     eax, r10d
0x14002e0c5  mov     r8, [r8]
0x14002e0c8  cmp     eax, r13d
0x14002e0cb  mov     rcx, [r11+8]
0x14002e0cf  cmova   eax, r13d
0x14002e0d3  mov     [rbp+Src], r8
0x14002e0d7  mov     r9d, eax
0x14002e0da  add     edx, r10d
0x14002e0dd  lea     rax, [rbp+arg_10]
0x14002e0e1  mov     [rsp+40h+var_20], rax
0x14002e0e6  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14002e0ed  nop     dword ptr [rax+rax+00h]
0x14002e0f2  mov     rax, [rbp+arg_10]
0x14002e0f6  mov     ecx, 0FFFFFFFFh
0x14002e0fb  cmp     rax, rcx
0x14002e0fe  ja      short loc_14002E105
0x14002e100  mov     dword ptr [rbp+Size], eax
0x14002e103  jmp     short loc_14002E10A
0x14002e105  mov     dword ptr [rbp+Size], ecx
0x14002e108  mov     eax, ecx
0x14002e10a  add     [rdi], eax
0x14002e10c  lea     r9, [rbp+arg_8]
0x14002e110  mov     rax, [rbx+190h]
0x14002e117  lea     r8, [rbp+arg_0]
0x14002e11b  lea     rdx, [rbp+Size]
0x14002e11f  mov     [rsp+40h+var_20], rax
0x14002e124  lea     rcx, [rbp+Src]
0x14002e128  call    sl_compress_tcp
0x14002e12d  test    dword ptr [rbx+44h], 1000h
0x14002e134  mov     r8b, al
0x14002e137  mov     r9, [rbp+Src]
0x14002e13b  jz      short loc_14002E140
0x14002e13d  or      [r9], al
0x14002e140  mov     eax, [rbx+674h]
0x14002e146  mov     edx, [rbx+6C8h]
0x14002e14c  mov     ecx, [rbp+arg_0]
0x14002e14f  mov     rsi, [r14]
0x14002e152  mov     r15d, [r12]
0x14002e156  shl     rdx, 20h
0x14002e15a  add     rcx, rdx
0x14002e15d  add     rcx, rax
0x14002e160  mov     eax, [rbx+67Ch]
0x14002e166  mov     [rbx+674h], ecx
0x14002e16c  shr     rcx, 20h
0x14002e170  mov     [rbx+6C8h], ecx
0x14002e176  mov     ecx, [rbx+6D0h]
0x14002e17c  shl     rcx, 20h
0x14002e180  add     rcx, rax
0x14002e183  mov     eax, [rbp+arg_8]
0x14002e186  add     rcx, rax
0x14002e189  mov     [rbx+67Ch], ecx
0x14002e18f  shr     rcx, 20h
0x14002e193  mov     [rbx+6D0h], ecx
0x14002e199  cmp     r8b, r13b
0x14002e19c  jnz     short loc_14002E1C5
0x14002e19e  mov     edi, dword ptr [rbp+Size]
0x14002e1a1  mov     rdx, r9; Src
0x14002e1a4  mov     r8d, edi; Size
0x14002e1a7  mov     rcx, rsi; void *
0x14002e1aa  call    memmove
0x14002e1af  lea     rax, [rdi+rsi]
0x14002e1b3  mov     [r14], rax
0x14002e1b6  lea     eax, [r15+rdi]
0x14002e1ba  mov     [r12], eax
0x14002e1be  mov     eax, 2Dh ; '-'
0x14002e1c3  jmp     short loc_14002E1ED
0x14002e1c5  mov     ecx, dword ptr [rbp+Size]
0x14002e1c8  lea     rax, [rsi+rcx]
0x14002e1cc  mov     [r14], rax
0x14002e1cf  lea     eax, [r15+rcx]
0x14002e1d3  mov     [r12], eax
0x14002e1d7  cmp     r8b, 40h ; '@'
0x14002e1db  jz      short loc_14002E1E8
0x14002e1dd  mov     eax, 2Fh ; '/'
0x14002e1e2  cmp     r8b, 70h ; 'p'
0x14002e1e6  jz      short loc_14002E1ED
0x14002e1e8  mov     eax, 21h ; '!'
0x14002e1ed  mov     rbx, [rsp+40h+arg_18]
0x14002e1f5  add     rsp, 40h
0x14002e1f9  pop     r15
0x14002e1fb  pop     r14
0x14002e1fd  pop     r13
0x14002e1ff  pop     r12
0x14002e201  pop     rdi
0x14002e202  pop     rsi
0x14002e203  pop     rbp
0x14002e204  retn
```
