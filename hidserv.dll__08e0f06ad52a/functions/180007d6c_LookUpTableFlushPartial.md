# LookUpTableFlushPartial

- ea: `0x180007d6c`
- end: `0x180007df6`
- name: `LookUpTableFlushPartial`
- size: `138`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007620`
- `0x180007e60`

## callees

- `0x1800074f0`
- `0x180007d6c`

## pseudocode

```c
void __fastcall LookUpTableFlushPartial(__int64 a1)
{
  unsigned int v2; // ebp
  unsigned int v3; // edi
  unsigned int v4; // esi
  _QWORD *v5; // rax

  if ( *(_DWORD *)(a1 + 256) )
  {
    v2 = *(_DWORD *)(a1 + 260);
    v3 = 0;
    v4 = v2;
    do
    {
      if ( *(_QWORD *)(a1 + 8LL * v4) )
        v3 += FlushLookUpTableBucket(a1, v4);
      v4 = ((_BYTE)v4 + 1) & 0x1F;
    }
    while ( v4 != v2 && v3 < 0x10 );
    *(_DWORD *)(a1 + 260) = v4;
    if ( v3 )
    {
      v5 = (_QWORD *)(a1 + 280);
      if ( *(_DWORD *)(a1 + 296) > v3 || !*v5 )
        *(_DWORD *)(a1 + 296) = v3;
      if ( *(_DWORD *)(a1 + 292) < v3 )
        *(_DWORD *)(a1 + 292) = v3;
      ++*v5;
      *(_QWORD *)(a1 + 272) += v3;
    }
  }
}

```

## disassembly

```asm
0x180007d6c  push    rbx
0x180007d6e  push    rbp
0x180007d6f  push    rsi
0x180007d70  push    rdi
0x180007d71  sub     rsp, 28h
0x180007d75  cmp     dword ptr [rcx+100h], 0
0x180007d7c  mov     rbx, rcx
0x180007d7f  jz      short loc_180007DED
0x180007d81  mov     ebp, [rcx+104h]
0x180007d87  xor     edi, edi
0x180007d89  mov     esi, ebp
0x180007d8b  mov     eax, esi
0x180007d8d  cmp     qword ptr [rbx+rax*8], 0
0x180007d92  jz      short loc_180007DA0
0x180007d94  mov     edx, esi
0x180007d96  mov     rcx, rbx
0x180007d99  call    FlushLookUpTableBucket
0x180007d9e  add     edi, eax
0x180007da0  inc     esi
0x180007da2  and     esi, 1Fh
0x180007da5  cmp     esi, ebp
0x180007da7  jz      short loc_180007DAE
0x180007da9  cmp     edi, 10h
0x180007dac  jb      short loc_180007D8B
0x180007dae  mov     [rbx+104h], esi
0x180007db4  test    edi, edi
0x180007db6  jz      short loc_180007DED
0x180007db8  lea     rax, [rbx+118h]
0x180007dbf  cmp     [rbx+128h], edi
0x180007dc5  ja      short loc_180007DCD
0x180007dc7  cmp     qword ptr [rax], 0
0x180007dcb  jnz     short loc_180007DD3
0x180007dcd  mov     [rbx+128h], edi
0x180007dd3  cmp     [rbx+124h], edi
0x180007dd9  jnb     short loc_180007DE1
0x180007ddb  mov     [rbx+124h], edi
0x180007de1  inc     qword ptr [rax]
0x180007de4  mov     eax, edi
0x180007de6  add     [rbx+110h], rax
0x180007ded  add     rsp, 28h
0x180007df1  pop     rdi
0x180007df2  pop     rsi
0x180007df3  pop     rbp
0x180007df4  pop     rbx
0x180007df5  retn
```
