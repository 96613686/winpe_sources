# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x14000d1b8`
- end: `0x14000d2a0`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `232`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int64@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d094`

## callees

- `0x140001af3`
- `0x14000d1b8`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rax
  unsigned __int16 *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned __int16 *v14; // rcx
  size_t v15; // rbx
  unsigned __int64 v16; // rbx

  v7 = a2;
  v8 = a1;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( a2 <= 0x7FFFFFFF )
  {
    v10 = 2147483646;
    v11 = a1;
    v12 = 0;
    do
    {
      if ( !v10 )
        break;
      if ( !*a3 )
        break;
      *v11++ = *a3++;
      --v10;
      ++v12;
      --a2;
    }
    while ( a2 );
    v13 = v12 - 1;
    if ( a2 )
      v13 = v12;
    v14 = v11 - 1;
    v9 = a2 == 0 ? 0x8007007A : 0;
    if ( a2 )
      v14 = v11;
    *v14 = 0;
    if ( a2 )
    {
      v8 += v13;
      v16 = v7 - v13;
    }
    else
    {
      v15 = 2 * v7;
      memset_0(v8, 0, v15);
      v16 = v15 >> 1;
      if ( v9 != -2147024774 )
        return v9;
    }
    if ( a4 )
      *a4 = v8;
    if ( a5 )
      *a5 = v16;
  }
  else
  {
    v9 = -2147024809;
    *a1 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x14000d1b8  push    rbx
0x14000d1ba  push    rbp
0x14000d1bb  push    rsi
0x14000d1bc  push    rdi
0x14000d1bd  push    r14
0x14000d1bf  sub     rsp, 20h
0x14000d1c3  xor     ebp, ebp
0x14000d1c5  mov     r14, r9
0x14000d1c8  mov     r10, r8
0x14000d1cb  mov     rbx, rdx
0x14000d1ce  mov     rsi, rcx
0x14000d1d1  test    rdx, rdx
0x14000d1d4  jz      loc_14000D285
0x14000d1da  cmp     rdx, 7FFFFFFFh
0x14000d1e1  jbe     short loc_14000D1ED
0x14000d1e3  mov     edi, 80070057h
0x14000d1e8  jmp     loc_14000D28F
0x14000d1ed  mov     eax, 7FFFFFFEh
0x14000d1f2  mov     r8, rsi
0x14000d1f5  mov     rcx, rbp
0x14000d1f8  test    rax, rax
0x14000d1fb  jz      short loc_14000D21F
0x14000d1fd  movzx   r9d, word ptr [r10]
0x14000d201  test    r9w, r9w
0x14000d205  jz      short loc_14000D21F
0x14000d207  mov     [r8], r9w
0x14000d20b  add     r10, 2
0x14000d20f  add     r8, 2
0x14000d213  dec     rax
0x14000d216  inc     rcx
0x14000d219  sub     rdx, 1
0x14000d21d  jnz     short loc_14000D1F8
0x14000d21f  test    rdx, rdx
0x14000d222  lea     r9, [rcx-1]
0x14000d226  mov     rax, rdx
0x14000d229  cmovnz  r9, rcx
0x14000d22d  neg     rax
0x14000d230  lea     rcx, [r8-2]
0x14000d234  sbb     edi, edi
0x14000d236  not     edi
0x14000d238  and     edi, 8007007Ah
0x14000d23e  test    rdx, rdx
0x14000d241  cmovnz  rcx, r8
0x14000d245  mov     [rcx], bp
0x14000d248  jnz     short loc_14000D267
0x14000d24a  add     rbx, rbx
0x14000d24d  xor     edx, edx; Val
0x14000d24f  mov     r8, rbx; Size
0x14000d252  mov     rcx, rsi; void *
0x14000d255  call    memset_0
0x14000d25a  shr     rbx, 1
0x14000d25d  cmp     edi, 8007007Ah
0x14000d263  jnz     short loc_14000D292
0x14000d265  jmp     short loc_14000D26E
0x14000d267  lea     rsi, [rsi+r9*2]
0x14000d26b  sub     rbx, r9
0x14000d26e  test    r14, r14
0x14000d271  jz      short loc_14000D276
0x14000d273  mov     [r14], rsi
0x14000d276  mov     rax, [rsp+48h+arg_20]
0x14000d27b  test    rax, rax
0x14000d27e  jz      short loc_14000D292
0x14000d280  mov     [rax], rbx
0x14000d283  jmp     short loc_14000D292
0x14000d285  mov     edi, 80070057h
0x14000d28a  test    rbx, rbx
0x14000d28d  jz      short loc_14000D292
0x14000d28f  mov     [rcx], bp
0x14000d292  mov     eax, edi
0x14000d294  add     rsp, 20h
0x14000d298  pop     r14
0x14000d29a  pop     rdi
0x14000d29b  pop     rsi
0x14000d29c  pop     rbp
0x14000d29d  pop     rbx
0x14000d29e  retn
```
