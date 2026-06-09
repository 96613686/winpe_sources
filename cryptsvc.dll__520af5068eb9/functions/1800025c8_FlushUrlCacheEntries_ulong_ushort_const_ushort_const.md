# FlushUrlCacheEntries(ulong,ushort * * const,ushort * * const)

- ea: `0x1800025c8`
- end: `0x180002629`
- name: `?FlushUrlCacheEntries@@YAXKQEAPEAG0@Z`
- size: `97`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const, unsigned __int16 **const)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800011f4`
- `0x180003aa0`

## callees

- `0x18000237c`
- `0x1800025c8`
- `0x1800068b0`

## pseudocode

```c
void __fastcall FlushUrlCacheEntries(unsigned int a1, unsigned __int16 **const a2, unsigned __int16 **const a3)
{
  __int64 v3; // rbp

  if ( a1 )
  {
    v3 = 0;
    do
    {
      I_UrlCacheDeleteFile(a3[v3]);
      PkiFree(a3[v3]);
      I_UrlCacheDeleteFile(a2[v3]);
      PkiFree(a2[v3]);
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < a1 );
    PkiFree(a2);
    PkiFree(a3);
  }
}

```

## disassembly

```asm
0x1800025c8  test    ecx, ecx
0x1800025ca  jnz     short loc_1800025CD
0x1800025cc  retn
0x1800025cd  push    rbx
0x1800025ce  push    rbp
0x1800025cf  push    rsi
0x1800025d0  push    rdi
0x1800025d1  push    r14
0x1800025d3  sub     rsp, 20h
0x1800025d7  xor     ebp, ebp
0x1800025d9  mov     rsi, r8
0x1800025dc  mov     r14, rdx
0x1800025df  mov     edi, ecx
0x1800025e1  test    ecx, ecx
0x1800025e3  jz      short loc_18000260F
0x1800025e5  mov     rcx, [rsi+rbp*8]; lpFileName
0x1800025e9  call    I_UrlCacheDeleteFile
0x1800025ee  mov     rcx, [rsi+rbp*8]; hMem
0x1800025f2  call    PkiFree
0x1800025f7  mov     rcx, [r14+rbp*8]; lpFileName
0x1800025fb  call    I_UrlCacheDeleteFile
0x180002600  mov     rcx, [r14+rbp*8]; hMem
0x180002604  call    PkiFree
0x180002609  inc     ebp
0x18000260b  cmp     ebp, edi
0x18000260d  jb      short loc_1800025E5
0x18000260f  mov     rcx, r14; hMem
0x180002612  call    PkiFree
0x180002617  mov     rcx, rsi; hMem
0x18000261a  add     rsp, 20h
0x18000261e  pop     r14
0x180002620  pop     rdi
0x180002621  pop     rsi
0x180002622  pop     rbp
0x180002623  pop     rbx
0x180002624  jmp     PkiFree
```
