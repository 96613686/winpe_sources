# UpdateInternalStatsOnFlush

- ea: `0x18000b0bc`
- end: `0x18000b0fe`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000af64`

## callees

- `0x18000b0bc`

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
0x18000b0bc  test    edx, edx
0x18000b0be  jz      short locret_18000B0FD
0x18000b0c0  lea     r8, [rcx+118h]
0x18000b0c7  cmp     [rcx+128h], edx
0x18000b0cd  ja      short loc_18000B0D7
0x18000b0cf  mov     rax, [r8]
0x18000b0d2  test    rax, rax
0x18000b0d5  jnz     short loc_18000B0E0
0x18000b0d7  mov     rax, [r8]
0x18000b0da  mov     [rcx+128h], edx
0x18000b0e0  cmp     [rcx+124h], edx
0x18000b0e6  jnb     short loc_18000B0EE
0x18000b0e8  mov     [rcx+124h], edx
0x18000b0ee  inc     rax
0x18000b0f1  mov     [r8], rax
0x18000b0f4  mov     eax, edx
0x18000b0f6  add     [rcx+110h], rax
0x18000b0fd  retn
```
