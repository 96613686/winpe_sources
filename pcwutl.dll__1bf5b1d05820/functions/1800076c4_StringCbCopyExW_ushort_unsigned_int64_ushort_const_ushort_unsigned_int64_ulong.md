# StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x1800076c4`
- end: `0x1800077dc`
- name: `?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `280`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000312c`

## callees

- `0x1800076c4`
- `0x1800191a2`

## pseudocode

```c
__int64 __fastcall StringCbCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v5; // rdi
  char v7; // si
  unsigned int v9; // ebx
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  unsigned __int64 v12; // r8
  unsigned __int16 *v13; // rax
  __int64 v14; // r9
  unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rbp
  __int64 v18; // rdi
  unsigned __int64 v19; // r8

  v5 = a2 >> 1;
  v7 = a2;
  if ( a2 >> 1 )
  {
    if ( v5 <= 0x7FFFFFFF )
    {
      v10 = 2147483646;
      v11 = L"If-None-Match:";
      v12 = v5;
      v13 = a1;
      v14 = 0;
      do
      {
        if ( !v10 )
          break;
        if ( !*v11 )
          break;
        *v13++ = *v11++;
        --v10;
        ++v14;
        --v12;
      }
      while ( v12 );
      v15 = v13 - 1;
      v16 = v14 - 1;
      if ( v12 )
      {
        v15 = v13;
        v16 = v14;
      }
      *v15 = 0;
      v17 = &a1[v16];
      v9 = v12 == 0 ? 0x8007007A : 0;
      v18 = v5 - v16;
      if ( v12 )
      {
        v19 = (v7 & 1) + 2 * v18;
        if ( v19 > 2 )
          memset_0(v17 + 1, 0, v19 - 2);
      }
      if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147024774 )
      {
        if ( a4 )
          *a4 = v17;
        if ( a5 )
          *a5 = (v7 & 1) + 2 * v18;
      }
    }
    else
    {
      v9 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x1800076c4  push    rbx
0x1800076c6  push    rbp
0x1800076c7  push    rsi
0x1800076c8  push    rdi
0x1800076c9  push    r14
0x1800076cb  push    r15
0x1800076cd  sub     rsp, 28h
0x1800076d1  mov     rdi, rdx
0x1800076d4  xor     r15d, r15d
0x1800076d7  shr     rdi, 1
0x1800076da  mov     r14, r9
0x1800076dd  mov     rsi, rdx
0x1800076e0  mov     r10, rcx
0x1800076e3  jz      loc_1800077BF
0x1800076e9  cmp     rdi, 7FFFFFFFh
0x1800076f0  jbe     short loc_1800076FC
0x1800076f2  mov     ebx, 80070057h
0x1800076f7  jmp     loc_1800077C9
0x1800076fc  mov     ecx, 7FFFFFFEh
0x180007701  lea     rdx, aIfNoneMatch; "If-None-Match:"
0x180007708  mov     r8, rdi
0x18000770b  mov     rax, r10
0x18000770e  mov     r9, r15
0x180007711  test    rcx, rcx
0x180007714  jz      short loc_180007738
0x180007716  movzx   r11d, word ptr [rdx]
0x18000771a  test    r11w, r11w
0x18000771e  jz      short loc_180007738
0x180007720  mov     [rax], r11w
0x180007724  add     rdx, 2
0x180007728  add     rax, 2
0x18000772c  dec     rcx
0x18000772f  inc     r9
0x180007732  sub     r8, 1
0x180007736  jnz     short loc_180007711
0x180007738  test    r8, r8
0x18000773b  lea     rcx, [rax-2]
0x18000773f  lea     rdx, [r9-1]
0x180007743  cmovnz  rcx, rax
0x180007747  cmovnz  rdx, r9
0x18000774b  mov     rax, r8
0x18000774e  neg     rax
0x180007751  sbb     ebx, ebx
0x180007753  mov     [rcx], r15w
0x180007757  not     ebx
0x180007759  lea     rbp, [r10+rdx*2]
0x18000775d  and     ebx, 8007007Ah
0x180007763  sub     rdi, rdx
0x180007766  test    r8, r8
0x180007769  jz      short loc_18000778A
0x18000776b  mov     rax, rsi
0x18000776e  and     eax, 1
0x180007771  lea     r8, [rax+rdi*2]
0x180007775  cmp     r8, 2
0x180007779  jbe     short loc_18000778A
0x18000777b  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000777f  lea     rcx, [rbp+2]; void *
0x180007783  xor     edx, edx; Val
0x180007785  call    memset_0
0x18000778a  mov     ecx, 80000000h
0x18000778f  lea     eax, [rbx+rcx]
0x180007792  test    ecx, eax
0x180007794  jnz     short loc_18000779E
0x180007796  cmp     ebx, 8007007Ah
0x18000779c  jnz     short loc_1800077CD
0x18000779e  test    r14, r14
0x1800077a1  jz      short loc_1800077A6
0x1800077a3  mov     [r14], rbp
0x1800077a6  mov     rcx, [rsp+58h+arg_20]
0x1800077ae  test    rcx, rcx
0x1800077b1  jz      short loc_1800077CD
0x1800077b3  and     esi, 1
0x1800077b6  lea     rax, [rsi+rdi*2]
0x1800077ba  mov     [rcx], rax
0x1800077bd  jmp     short loc_1800077CD
0x1800077bf  mov     ebx, 80070057h
0x1800077c4  test    rdi, rdi
0x1800077c7  jz      short loc_1800077CD
0x1800077c9  mov     [rcx], r15w
0x1800077cd  mov     eax, ebx
0x1800077cf  add     rsp, 28h
0x1800077d3  pop     r15
0x1800077d5  pop     r14
0x1800077d7  pop     rdi
0x1800077d8  pop     rsi
0x1800077d9  pop     rbp
0x1800077da  pop     rbx
0x1800077db  retn
```
