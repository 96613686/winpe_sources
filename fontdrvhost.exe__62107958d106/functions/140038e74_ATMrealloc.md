# ATMrealloc

- ea: `0x140038e74`
- end: `0x140038eea`
- name: `ATMrealloc`
- size: `118`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `21`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140032b84`
- `0x140033274`
- `0x140034688`
- `0x1400350dc`
- `0x140038730`
- `0x1400392dc`
- `0x14003a0e4`
- `0x14003f708`
- `0x14004005c`
- `0x14005be0c`
- `0x14005d97c`
- `0x140066080`
- `0x140072eb0`
- `0x140081760`
- `0x140081780`
- `0x140081930`
- `0x140081a10`
- `0x140081a78`
- `0x140081cb0`
- `0x140082340`
- `0x140082500`

## callees

- `0x140038670`
- `0x140038e74`
- `0x1400392ac`
- `0x1400395a8`
- `0x1400395c8`
- `0x140076ef6`

## pseudocode

```c
_DWORD *__fastcall ATMrealloc(void *Src, unsigned __int64 a2)
{
  unsigned __int64 v4; // r14
  char v5; // al
  __int64 v6; // rdx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  void *v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = Src;
  v4 = ATMmsize((__int64)Src);
  v5 = CountBlock(Src);
  v7 = ATMallocExt(a2, v6, v5 != 0, 1);
  v8 = v7;
  if ( v7 && Src )
  {
    if ( v4 < a2 )
      a2 = v4;
    memmove_0(v7, Src, a2);
    EnhancedFree(&v10);
  }
  return v8;
}

```

## disassembly

```asm
0x140038e74  mov     [rsp+arg_0], rcx
0x140038e79  push    rbx
0x140038e7a  push    rsi
0x140038e7b  push    rdi
0x140038e7c  push    r14
0x140038e7e  sub     rsp, 38h
0x140038e82  mov     rsi, rdx
0x140038e85  mov     rbx, rcx
0x140038e88  call    ATMmsize
0x140038e8d  mov     r14, rax
0x140038e90  mov     rcx, rbx
0x140038e93  call    CountBlock
0x140038e98  mov     r9b, 1
0x140038e9b  mov     rcx, rsi
0x140038e9e  test    al, al
0x140038ea0  jz      short loc_140038ED8
0x140038ea2  mov     r8b, r9b
0x140038ea5  call    ATMallocExt
0x140038eaa  mov     rdi, rax
0x140038ead  test    rax, rax
0x140038eb0  jz      short loc_140038EDD
0x140038eb2  test    rbx, rbx
0x140038eb5  jz      short loc_140038EDD
0x140038eb7  cmp     r14, rsi
0x140038eba  cmovb   rsi, r14
0x140038ebe  mov     r8, rsi; Size
0x140038ec1  mov     rdx, rbx; Src
0x140038ec4  mov     rcx, rax; void *
0x140038ec7  call    memmove_0
0x140038ecc  lea     rcx, [rsp+58h+arg_0]
0x140038ed1  call    EnhancedFree
0x140038ed6  jmp     short loc_140038EDD
0x140038ed8  xor     r8d, r8d
0x140038edb  jmp     short loc_140038EA5
0x140038edd  mov     rax, rdi
0x140038ee0  add     rsp, 38h
0x140038ee4  pop     r14
0x140038ee6  pop     rdi
0x140038ee7  pop     rsi
0x140038ee8  pop     rbx
0x140038ee9  retn
0x140096aae  push    rbp
0x140096ab0  sub     rsp, 30h
0x140096ab4  mov     rbp, rdx
0x140096ab7  add     rsp, 30h
0x140096abb  pop     rbp
0x140096abc  retn
```
