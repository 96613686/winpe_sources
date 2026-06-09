# UpdateInternalStatsOnFlush

- ea: `0x180030128`
- end: `0x18003016a`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000f4fc`
- `0x180030088`

## callees

- `0x180030128`

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
0x180030128  test    edx, edx
0x18003012a  jz      short locret_180030169
0x18003012c  lea     r8, [rcx+118h]
0x180030133  cmp     [rcx+128h], edx
0x180030139  ja      short loc_180030143
0x18003013b  mov     rax, [r8]
0x18003013e  test    rax, rax
0x180030141  jnz     short loc_18003014C
0x180030143  mov     rax, [r8]
0x180030146  mov     [rcx+128h], edx
0x18003014c  cmp     [rcx+124h], edx
0x180030152  jnb     short loc_18003015A
0x180030154  mov     [rcx+124h], edx
0x18003015a  inc     rax
0x18003015d  mov     [r8], rax
0x180030160  mov     eax, edx
0x180030162  add     [rcx+110h], rax
0x180030169  retn
```
