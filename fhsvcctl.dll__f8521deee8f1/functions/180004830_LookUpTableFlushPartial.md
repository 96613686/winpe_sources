# LookUpTableFlushPartial

- ea: `0x180004830`
- end: `0x1800048ba`
- name: `LookUpTableFlushPartial`
- size: `138`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040d0`
- `0x180004920`

## callees

- `0x180003fac`
- `0x180004830`

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
0x180004830  push    rbx
0x180004832  push    rbp
0x180004833  push    rsi
0x180004834  push    rdi
0x180004835  sub     rsp, 28h
0x180004839  cmp     dword ptr [rcx+100h], 0
0x180004840  mov     rbx, rcx
0x180004843  jz      short loc_1800048B1
0x180004845  mov     ebp, [rcx+104h]
0x18000484b  xor     edi, edi
0x18000484d  mov     esi, ebp
0x18000484f  mov     eax, esi
0x180004851  cmp     qword ptr [rbx+rax*8], 0
0x180004856  jz      short loc_180004864
0x180004858  mov     edx, esi
0x18000485a  mov     rcx, rbx
0x18000485d  call    FlushLookUpTableBucket
0x180004862  add     edi, eax
0x180004864  inc     esi
0x180004866  and     esi, 1Fh
0x180004869  cmp     esi, ebp
0x18000486b  jz      short loc_180004872
0x18000486d  cmp     edi, 10h
0x180004870  jb      short loc_18000484F
0x180004872  mov     [rbx+104h], esi
0x180004878  test    edi, edi
0x18000487a  jz      short loc_1800048B1
0x18000487c  lea     rax, [rbx+118h]
0x180004883  cmp     [rbx+128h], edi
0x180004889  ja      short loc_180004891
0x18000488b  cmp     qword ptr [rax], 0
0x18000488f  jnz     short loc_180004897
0x180004891  mov     [rbx+128h], edi
0x180004897  cmp     [rbx+124h], edi
0x18000489d  jnb     short loc_1800048A5
0x18000489f  mov     [rbx+124h], edi
0x1800048a5  inc     qword ptr [rax]
0x1800048a8  mov     eax, edi
0x1800048aa  add     [rbx+110h], rax
0x1800048b1  add     rsp, 28h
0x1800048b5  pop     rdi
0x1800048b6  pop     rsi
0x1800048b7  pop     rbp
0x1800048b8  pop     rbx
0x1800048b9  retn
```
