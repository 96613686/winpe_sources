# TranslateDriverResult

- ea: `0x180007d9c`
- end: `0x180007df0`
- name: `TranslateDriverResult`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d40`
- `0x180004184`

## callees

- `0x180007d9c`
- `0x180007df8`

## pseudocode

```c
__int64 __fastcall TranslateDriverResult(int a1)
{
  int v1; // edx

  v1 = 0;
  if ( dword_18000E080[0] == -1 )
  {
LABEL_4:
    TspLog(2, "TranslateDriverResult: unknown driver result(%x)", a1);
    return 2147483720LL;
  }
  else
  {
    while ( a1 != dword_18000E080[2 * v1] )
    {
      if ( dword_18000E080[2 * ++v1] == -1 )
        goto LABEL_4;
    }
    return (unsigned int)dword_18000E080[2 * v1 + 1];
  }
}

```

## disassembly

```asm
0x180007d9c  sub     rsp, 28h
0x180007da0  xor     edx, edx
0x180007da2  or      r9d, 0FFFFFFFFh
0x180007da6  cmp     cs:dword_18000E080, r9d
0x180007dad  jz      short loc_180007DCA
0x180007daf  lea     r8, dword_18000E080
0x180007db6  movsxd  rax, edx
0x180007db9  cmp     ecx, [r8+rax*8]
0x180007dbd  jz      short loc_180007DE9
0x180007dbf  inc     edx
0x180007dc1  movsxd  rax, edx
0x180007dc4  cmp     [r8+rax*8], r9d
0x180007dc8  jnz     short loc_180007DB6
0x180007dca  mov     r8d, ecx
0x180007dcd  lea     rdx, aTranslatedrive; "TranslateDriverResult: unknown driver r"...
0x180007dd4  mov     ecx, 2
0x180007dd9  call    TspLog
0x180007dde  mov     eax, 80000048h
0x180007de3  add     rsp, 28h
0x180007de7  retn
0x180007de9  mov     eax, [r8+rax*8+4]
0x180007dee  jmp     short loc_180007DE3
```
