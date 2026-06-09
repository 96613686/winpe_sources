# UpdateInternalStatsOnFlush

- ea: `0x180018488`
- end: `0x1800184ca`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180017f88`
- `0x180018310`

## callees

- `0x180018488`

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
0x180018488  test    edx, edx
0x18001848a  jz      short locret_1800184C9
0x18001848c  lea     r8, [rcx+118h]
0x180018493  cmp     [rcx+128h], edx
0x180018499  ja      short loc_1800184A3
0x18001849b  mov     rax, [r8]
0x18001849e  test    rax, rax
0x1800184a1  jnz     short loc_1800184AC
0x1800184a3  mov     rax, [r8]
0x1800184a6  mov     [rcx+128h], edx
0x1800184ac  cmp     [rcx+124h], edx
0x1800184b2  jnb     short loc_1800184BA
0x1800184b4  mov     [rcx+124h], edx
0x1800184ba  inc     rax
0x1800184bd  mov     [r8], rax
0x1800184c0  mov     eax, edx
0x1800184c2  add     [rcx+110h], rax
0x1800184c9  retn
```
