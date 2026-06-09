# SymCrypt3DesExpandKey

- ea: `0x1800037d0`
- end: `0x180003837`
- name: `SymCrypt3DesExpandKey`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a50`
- `0x180002350`

## callees

- `0x1800037d0`
- `0x180003840`

## pseudocode

```c
__int64 __fastcall SymCrypt3DesExpandKey(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v6; // rsi
  __int64 i; // rdi

  if ( ((a3 - 8) & 0xFFFFFFFFFFFFFFE7uLL) != 0 || a3 == 32 )
    return 32769;
  v6 = 0;
  for ( i = 0; i != 3; ++i )
  {
    SymCryptDesExpandSingleKey(a1 + (i << 7), (_DWORD *)(v6 + a2));
    v6 = (v6 + 8) % a3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800037d0  push    rbx
0x1800037d2  push    rbp
0x1800037d3  push    rsi
0x1800037d4  push    rdi
0x1800037d5  push    r14
0x1800037d7  sub     rsp, 20h
0x1800037db  lea     rax, [r8-8]
0x1800037df  mov     rbx, r8
0x1800037e2  mov     rbp, rdx
0x1800037e5  mov     r14, rcx
0x1800037e8  test    rax, 0FFFFFFFFFFFFFFE7h
0x1800037ee  jnz     short loc_180003826
0x1800037f0  cmp     rbx, 20h ; ' '
0x1800037f4  jz      short loc_180003826
0x1800037f6  xor     esi, esi
0x1800037f8  xor     edi, edi
0x1800037fa  mov     rcx, rdi
0x1800037fd  lea     rdx, [rsi+rbp]
0x180003801  shl     rcx, 7
0x180003805  add     rcx, r14
0x180003808  call    SymCryptDesExpandSingleKey
0x18000380d  lea     rax, [rsi+8]
0x180003811  xor     edx, edx
0x180003813  div     rbx
0x180003816  inc     rdi
0x180003819  mov     rsi, rdx
0x18000381c  cmp     rdi, 3
0x180003820  jnz     short loc_1800037FA
0x180003822  xor     eax, eax
0x180003824  jmp     short loc_18000382B
0x180003826  mov     eax, 8001h
0x18000382b  add     rsp, 20h
0x18000382f  pop     r14
0x180003831  pop     rdi
0x180003832  pop     rsi
0x180003833  pop     rbp
0x180003834  pop     rbx
0x180003835  retn
```
