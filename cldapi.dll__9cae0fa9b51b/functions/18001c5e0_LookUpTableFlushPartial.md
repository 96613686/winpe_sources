# LookUpTableFlushPartial

- ea: `0x18001c5e0`
- end: `0x18001c66b`
- name: `LookUpTableFlushPartial`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001be60`
- `0x18001c6f0`

## callees

- `0x18001bd94`
- `0x18001c5e0`

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
0x18001c5e0  push    rbx
0x18001c5e2  push    rbp
0x18001c5e3  push    rsi
0x18001c5e4  push    rdi
0x18001c5e5  sub     rsp, 28h
0x18001c5e9  cmp     dword ptr [rcx+100h], 0
0x18001c5f0  mov     rbx, rcx
0x18001c5f3  jz      short loc_18001C661
0x18001c5f5  mov     ebp, [rcx+104h]
0x18001c5fb  xor     edi, edi
0x18001c5fd  mov     esi, ebp
0x18001c5ff  mov     eax, esi
0x18001c601  cmp     qword ptr [rbx+rax*8], 0
0x18001c606  jz      short loc_18001C614
0x18001c608  mov     edx, esi
0x18001c60a  mov     rcx, rbx
0x18001c60d  call    FlushLookUpTableBucket
0x18001c612  add     edi, eax
0x18001c614  inc     esi
0x18001c616  and     esi, 1Fh
0x18001c619  cmp     esi, ebp
0x18001c61b  jz      short loc_18001C622
0x18001c61d  cmp     edi, 10h
0x18001c620  jb      short loc_18001C5FF
0x18001c622  mov     [rbx+104h], esi
0x18001c628  test    edi, edi
0x18001c62a  jz      short loc_18001C661
0x18001c62c  lea     rax, [rbx+118h]
0x18001c633  cmp     [rbx+128h], edi
0x18001c639  ja      short loc_18001C641
0x18001c63b  cmp     qword ptr [rax], 0
0x18001c63f  jnz     short loc_18001C647
0x18001c641  mov     [rbx+128h], edi
0x18001c647  cmp     [rbx+124h], edi
0x18001c64d  jnb     short loc_18001C655
0x18001c64f  mov     [rbx+124h], edi
0x18001c655  inc     qword ptr [rax]
0x18001c658  mov     eax, edi
0x18001c65a  add     [rbx+110h], rax
0x18001c661  add     rsp, 28h
0x18001c665  pop     rdi
0x18001c666  pop     rsi
0x18001c667  pop     rbp
0x18001c668  pop     rbx
0x18001c669  retn
```
