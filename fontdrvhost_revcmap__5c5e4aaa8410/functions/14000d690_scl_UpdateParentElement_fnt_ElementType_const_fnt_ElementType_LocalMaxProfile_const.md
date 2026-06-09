# scl_UpdateParentElement(fnt_ElementType const *,fnt_ElementType *,LocalMaxProfile const *)

- ea: `0x14000d690`
- end: `0x14000d74b`
- name: `?scl_UpdateParentElement@@YAHPEBUfnt_ElementType@@PEAU1@PEBULocalMaxProfile@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(const struct fnt_ElementType *, struct fnt_ElementType *, const struct LocalMaxProfile *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000d128`

## callees

- `0x14000d690`

## pseudocode

```c
__int64 __fastcall scl_UpdateParentElement(
        const struct fnt_ElementType *a1,
        struct fnt_ElementType *a2,
        const struct LocalMaxProfile *a3)
{
  __int64 v3; // r10
  __int16 v4; // r9
  unsigned __int16 v5; // ax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int16 v9; // r11
  __int16 v10; // bx

  v3 = *((__int16 *)a2 + 40);
  v4 = *((_WORD *)a1 + 40) + v3;
  if ( v4 < (__int16)v3 || v4 < 0 )
    return 5123;
  v5 = *((_WORD *)a3 + 6);
  if ( *((_WORD *)a3 + 4) >= v5 )
    v5 = *((_WORD *)a3 + 4);
  if ( v4 > (int)v5 )
    return 5123;
  if ( !(_WORD)v3 )
  {
LABEL_7:
    *((_WORD *)a2 + 40) = v4;
    return 0;
  }
  v7 = *((_QWORD *)a2 + 8);
  v8 = *((__int16 *)a2 + 40);
  v9 = *(_WORD *)(v7 + 2 * v3 - 2) + 1;
  v10 = *(_WORD *)(v7 + 2LL * v4 - 2) + v9;
  if ( v10 >= v9 && v10 >= 0 )
  {
    while ( (__int16)v3 < v4 )
    {
      LOWORD(v3) = v3 + 1;
      *(_WORD *)(*((_QWORD *)a2 + 7) + 2 * v8) += v9;
      *(_WORD *)(*((_QWORD *)a2 + 8) + 2 * v8++) += v9;
    }
    goto LABEL_7;
  }
  return 5121;
}

```

## disassembly

```asm
0x14000d690  mov     [rsp+arg_0], rbx
0x14000d695  mov     [rsp+arg_8], rdi
0x14000d69a  movsx   r10, word ptr [rdx+50h]
0x14000d69f  movzx   r9d, r10w
0x14000d6a3  add     r9w, [rcx+50h]
0x14000d6a8  cmp     r9w, r10w
0x14000d6ac  jl      loc_14000D744
0x14000d6b2  test    r9w, r9w
0x14000d6b6  js      loc_14000D744
0x14000d6bc  movzx   eax, word ptr [r8+0Ch]
0x14000d6c1  cmp     [r8+8], ax
0x14000d6c6  movsx   rbx, r9w
0x14000d6ca  cmovnb  ax, [r8+8]
0x14000d6d0  movzx   eax, ax
0x14000d6d3  cmp     ebx, eax
0x14000d6d5  jg      short loc_14000D744
0x14000d6d7  test    r10w, r10w
0x14000d6db  jnz     short loc_14000D6EF
0x14000d6dd  mov     [rdx+50h], r9w
0x14000d6e2  xor     eax, eax
0x14000d6e4  mov     rbx, [rsp+arg_0]
0x14000d6e9  mov     rdi, [rsp+arg_8]
0x14000d6ee  retn
0x14000d6ef  mov     rcx, [rdx+40h]
0x14000d6f3  mov     rax, rbx
0x14000d6f6  mov     edi, 1
0x14000d6fb  mov     r8, r10
0x14000d6fe  movzx   r11d, word ptr [rcx+r10*2-2]
0x14000d704  add     r11w, di
0x14000d708  movzx   ebx, r11w
0x14000d70c  add     bx, [rcx+rax*2-2]
0x14000d711  cmp     bx, r11w
0x14000d715  jl      short loc_14000D71C
0x14000d717  test    bx, bx
0x14000d71a  jns     short loc_14000D73C
0x14000d71c  mov     eax, 1401h
0x14000d721  jmp     short loc_14000D6E4
0x14000d723  mov     rax, [rdx+38h]
0x14000d727  add     r10w, di
0x14000d72b  add     [rax+r8*2], r11w
0x14000d730  mov     rax, [rdx+40h]
0x14000d734  add     [rax+r8*2], r11w
0x14000d739  add     r8, rdi
0x14000d73c  cmp     r10w, r9w
0x14000d740  jl      short loc_14000D723
0x14000d742  jmp     short loc_14000D6DD
0x14000d744  mov     eax, 1403h
0x14000d749  jmp     short loc_14000D6E4
```
