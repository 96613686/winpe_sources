# __dllonexit

- ea: `0x18002ddb0`
- end: `0x18002de65`
- name: `__dllonexit`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x18001d110`
- `0x18001d5c0`
- `0x18002ddb0`
- `0x18003dc24`
- `0x18003dc34`

## pseudocode

```c
__int64 __fastcall _dllonexit(__int64 a1, void **a2, _QWORD *a3)
{
  __int64 v6; // rcx
  size_t v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rsi

  lockexit();
  v7 = msize(*a2);
  if ( v7 > *a3 - (_QWORD)*a2 )
    goto LABEL_11;
  v8 = 4096;
  if ( v7 < 0x1000 )
    v8 = v7;
  if ( -32 - v8 < v7 )
  {
    v9 = 0;
  }
  else
  {
    v6 = realloc_crt(*a2, v8 + v7);
    v9 = 0;
    if ( v6 )
    {
LABEL_10:
      *a3 = v6 + 8 * ((__int64)(*a3 - (_QWORD)*a2) >> 3);
      *a2 = (void *)v6;
LABEL_11:
      *(_QWORD *)*a3 = a1;
      *a3 += 8LL;
      v9 = a1;
      goto LABEL_12;
    }
  }
  if ( v7 <= 0xFFFFFFFFFFFFFFC0uLL )
  {
    v6 = realloc_crt(*a2, v7 + 32);
    if ( v6 )
      goto LABEL_10;
  }
LABEL_12:
  unlockexit(v6);
  return v9;
}

```

## disassembly

```asm
0x18002ddb0  push    rbx
0x18002ddb2  push    rsi
0x18002ddb3  push    rdi
0x18002ddb4  push    r14
0x18002ddb6  push    r15
0x18002ddb8  sub     rsp, 20h
0x18002ddbc  mov     rbx, r8
0x18002ddbf  mov     r14, rdx
0x18002ddc2  mov     r15, rcx
0x18002ddc5  call    _lockexit
0x18002ddca  nop
0x18002ddcb  mov     rcx, [r14]; Block
0x18002ddce  call    _msize
0x18002ddd3  mov     rdi, rax
0x18002ddd6  mov     r9, [rbx]
0x18002ddd9  sub     r9, [r14]
0x18002dddc  cmp     rax, r9
0x18002dddf  ja      short loc_18002DE44
0x18002dde1  mov     eax, 1000h
0x18002dde6  cmp     rdi, rax
0x18002dde9  cmovb   rax, rdi
0x18002dded  mov     rdx, 0FFFFFFFFFFFFFFE0h
0x18002ddf4  sub     rdx, rax
0x18002ddf7  cmp     rdx, rdi
0x18002ddfa  jb      short loc_18002DE14
0x18002ddfc  lea     rdx, [rax+rdi]; Size
0x18002de00  mov     rcx, [r14]; Block
0x18002de03  call    _realloc_crt
0x18002de08  mov     rcx, rax
0x18002de0b  xor     esi, esi
0x18002de0d  test    rax, rax
0x18002de10  jnz     short loc_18002DE30
0x18002de12  jmp     short loc_18002DE16
0x18002de14  xor     esi, esi
0x18002de16  cmp     rdi, 0FFFFFFFFFFFFFFC0h
0x18002de1a  ja      short loc_18002DE51
0x18002de1c  lea     rdx, [rdi+20h]; Size
0x18002de20  mov     rcx, [r14]; Block
0x18002de23  call    _realloc_crt
0x18002de28  mov     rcx, rax
0x18002de2b  test    rax, rax
0x18002de2e  jz      short loc_18002DE51
0x18002de30  mov     rax, [rbx]
0x18002de33  sub     rax, [r14]
0x18002de36  sar     rax, 3
0x18002de3a  lea     rax, [rcx+rax*8]
0x18002de3e  mov     [rbx], rax
0x18002de41  mov     [r14], rcx
0x18002de44  mov     rax, [rbx]
0x18002de47  mov     [rax], r15
0x18002de4a  add     qword ptr [rbx], 8
0x18002de4e  mov     rsi, r15
0x18002de51  call    _unlockexit
0x18002de56  mov     rax, rsi
0x18002de59  add     rsp, 20h
0x18002de5d  pop     r15
0x18002de5f  pop     r14
0x18002de61  pop     rdi
0x18002de62  pop     rsi
0x18002de63  pop     rbx
0x18002de64  retn
0x18007bcd9  push    rbp
0x18007bcdb  sub     rsp, 20h
0x18007bcdf  mov     rbp, rdx
0x18007bce2  add     rsp, 20h
0x18007bce6  pop     rbp
0x18007bce7  jmp     _unlockexit
```
