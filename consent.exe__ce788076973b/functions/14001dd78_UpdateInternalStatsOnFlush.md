# UpdateInternalStatsOnFlush

- ea: `0x14001dd78`
- end: `0x14001ddba`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001d8c0`
- `0x14001dc38`

## callees

- `0x14001dd78`

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
0x14001dd78  test    edx, edx
0x14001dd7a  jz      short locret_14001DDB9
0x14001dd7c  lea     r8, [rcx+118h]
0x14001dd83  cmp     [rcx+128h], edx
0x14001dd89  ja      short loc_14001DD93
0x14001dd8b  mov     rax, [r8]
0x14001dd8e  test    rax, rax
0x14001dd91  jnz     short loc_14001DD9C
0x14001dd93  mov     rax, [r8]
0x14001dd96  mov     [rcx+128h], edx
0x14001dd9c  cmp     [rcx+124h], edx
0x14001dda2  jnb     short loc_14001DDAA
0x14001dda4  mov     [rcx+124h], edx
0x14001ddaa  inc     rax
0x14001ddad  mov     [r8], rax
0x14001ddb0  mov     eax, edx
0x14001ddb2  add     [rcx+110h], rax
0x14001ddb9  retn
```
