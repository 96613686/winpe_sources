# UpdateInternalStatsOnFlush

- ea: `0x18001e098`
- end: `0x18001e0da`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180018a08`
- `0x180018db4`

## callees

- `0x18001e098`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 280);
    if ( *(_DWORD *)(a1 + 296) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 296) = a2;
    }
    if ( *(_DWORD *)(a1 + 292) < a2 )
      *(_DWORD *)(a1 + 292) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 272) += a2;
  }
}

```

## disassembly

```asm
0x18001e098  test    edx, edx
0x18001e09a  jz      short locret_18001E0D9
0x18001e09c  lea     r8, [rcx+118h]
0x18001e0a3  cmp     [rcx+128h], edx
0x18001e0a9  ja      short loc_18001E0B3
0x18001e0ab  mov     rax, [r8]
0x18001e0ae  test    rax, rax
0x18001e0b1  jnz     short loc_18001E0BC
0x18001e0b3  mov     rax, [r8]
0x18001e0b6  mov     [rcx+128h], edx
0x18001e0bc  cmp     [rcx+124h], edx
0x18001e0c2  jnb     short loc_18001E0CA
0x18001e0c4  mov     [rcx+124h], edx
0x18001e0ca  inc     rax
0x18001e0cd  mov     [r8], rax
0x18001e0d0  mov     eax, edx
0x18001e0d2  add     [rcx+110h], rax
0x18001e0d9  retn
```
