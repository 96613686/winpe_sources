# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x1800112a4`
- end: `0x1800113bb`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008278`

## callees

- `0x1800112a4`
- `0x1800133e2`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned int v5; // ebx
  __int64 *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // r9
  __int64 v10; // rbx
  __int64 v11; // r11
  unsigned __int16 *v12; // rcx
  __int64 v13; // rdx
  bool v14; // cf

  if ( !a1 && a2 || a2 > 0x7FFFFFFF )
  {
    v5 = -2147024809;
LABEL_7:
    *a1 = 0;
    return v5;
  }
  if ( a4 < 0x7FFFFFFF )
  {
    v6 = &qword_180017F50;
    if ( a3 )
      v6 = (__int64 *)a3;
    v7 = a4 & -(__int64)(a3 != 0);
    if ( a2 )
    {
      v8 = a2;
      v9 = a1;
      v10 = 0;
      do
      {
        if ( !v7 )
          break;
        if ( !*(_WORD *)v6 )
          break;
        *v9 = *(_WORD *)v6;
        v6 = (__int64 *)((char *)v6 + 2);
        ++v9;
        --v7;
        ++v10;
        --v8;
      }
      while ( v8 );
      v11 = v10 - 1;
      v12 = v9 - 1;
      if ( v8 )
      {
        v11 = v10;
        v12 = v9;
      }
      *v12 = 0;
      v5 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
      {
        v14 = a2 == v11;
        v13 = a2 - v11;
        if ( !v14 && v13 != 1 && (unsigned __int64)(2 * v13) > 2 )
          memset_0(&a1[v11 + 1], 0, 2 * v13 - 2);
      }
    }
    else
    {
      v5 = 0;
      if ( v7 && *(_WORD *)v6 )
        return a1 != 0 ? -2147024774 : -2147024809;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( a2 )
      goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x1800112a4  mov     [rsp+arg_0], rbx
0x1800112a9  push    rdi
0x1800112aa  sub     rsp, 20h
0x1800112ae  xor     edi, edi
0x1800112b0  mov     r10, rcx
0x1800112b3  test    rcx, rcx
0x1800112b6  jnz     short loc_1800112BD
0x1800112b8  test    rdx, rdx
0x1800112bb  jnz     short loc_1800112C7
0x1800112bd  mov     eax, 7FFFFFFFh
0x1800112c2  cmp     rdx, rax
0x1800112c5  jbe     short loc_1800112CE
0x1800112c7  mov     ebx, 80070057h
0x1800112cc  jmp     short loc_1800112E1
0x1800112ce  cmp     r9, rax
0x1800112d1  jb      short loc_1800112E9
0x1800112d3  mov     ebx, 80070057h
0x1800112d8  test    rdx, rdx
0x1800112db  jz      loc_1800113AE
0x1800112e1  mov     [rcx], di
0x1800112e4  jmp     loc_1800113AE
0x1800112e9  test    r8, r8
0x1800112ec  lea     rcx, qword_180017F50
0x1800112f3  cmovnz  rcx, r8
0x1800112f7  neg     r8
0x1800112fa  sbb     rax, rax
0x1800112fd  and     rax, r9
0x180011300  test    rdx, rdx
0x180011303  jnz     short loc_18001132D
0x180011305  mov     ebx, edi
0x180011307  test    rax, rax
0x18001130a  jz      loc_1800113AE
0x180011310  cmp     [rcx], di
0x180011313  jz      loc_1800113AE
0x180011319  neg     r10
0x18001131c  mov     ebx, 80070057h
0x180011321  sbb     eax, eax
0x180011323  and     eax, 23h
0x180011326  add     ebx, eax
0x180011328  jmp     loc_1800113AE
0x18001132d  mov     r8, rdx
0x180011330  mov     r9, r10
0x180011333  mov     rbx, rdi
0x180011336  test    rax, rax
0x180011339  jz      short loc_18001135D
0x18001133b  movzx   r11d, word ptr [rcx]
0x18001133f  test    r11w, r11w
0x180011343  jz      short loc_18001135D
0x180011345  mov     [r9], r11w
0x180011349  add     rcx, 2
0x18001134d  add     r9, 2
0x180011351  dec     rax
0x180011354  inc     rbx
0x180011357  sub     r8, 1
0x18001135b  jnz     short loc_180011336
0x18001135d  test    r8, r8
0x180011360  lea     r11, [rbx-1]
0x180011364  lea     rcx, [r9-2]
0x180011368  mov     rax, r8
0x18001136b  cmovnz  r11, rbx
0x18001136f  cmovnz  rcx, r9
0x180011373  neg     rax
0x180011376  sbb     ebx, ebx
0x180011378  not     ebx
0x18001137a  mov     [rcx], di
0x18001137d  and     ebx, 8007007Ah
0x180011383  test    r8, r8
0x180011386  jz      short loc_1800113AE
0x180011388  sub     rdx, r11
0x18001138b  cmp     rdx, 1
0x18001138f  jbe     short loc_1800113AE
0x180011391  lea     r8, [rdx+rdx]
0x180011395  cmp     r8, 2
0x180011399  jbe     short loc_1800113AE
0x18001139b  add     r10, 2
0x18001139f  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800113a3  xor     edx, edx; Val
0x1800113a5  lea     rcx, [r10+r11*2]; void *
0x1800113a9  call    memset_0
0x1800113ae  mov     eax, ebx
0x1800113b0  mov     rbx, [rsp+28h+arg_0]
0x1800113b5  add     rsp, 20h
0x1800113b9  pop     rdi
0x1800113ba  retn
```
