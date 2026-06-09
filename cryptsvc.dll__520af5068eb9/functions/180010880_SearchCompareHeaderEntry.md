# _SearchCompareHeaderEntry

- ea: `0x180010880`
- end: `0x1800108ad`
- name: `_SearchCompareHeaderEntry`
- size: `45`
- prototype: `int __fastcall(const void **, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010880`
- `0x1800174f0`

## pseudocode

```c
int __fastcall SearchCompareHeaderEntry(const void **a1, __int64 **a2)
{
  __int64 v2; // rdx

  v2 = **a2;
  if ( *(_DWORD *)a1 != *(_DWORD *)v2 )
    return *(_DWORD *)a1 < *(_DWORD *)v2 ? -1 : 1;
  if ( *(_DWORD *)a1 )
    return memcmp_0(a1[1], *(const void **)(v2 + 8), *(unsigned int *)a1);
  return 0;
}

```

## disassembly

```asm
0x180010880  mov     rax, [rdx]
0x180010883  mov     rdx, [rax]
0x180010886  mov     eax, [rdx]
0x180010888  cmp     [rcx], eax
0x18001088a  jnz     short loc_1800108A5
0x18001088c  cmp     dword ptr [rcx], 0
0x18001088f  jnz     short loc_180010895
0x180010891  xor     eax, eax
0x180010893  jmp     short locret_1800108AC
0x180010895  mov     r8d, [rcx]; Size
0x180010898  mov     rcx, [rcx+8]; Buf1
0x18001089c  mov     rdx, [rdx+8]; Buf2
0x1800108a0  jmp     memcmp_0
0x1800108a5  sbb     eax, eax
0x1800108a7  and     eax, 0FFFFFFFEh
0x1800108aa  inc     eax
0x1800108ac  retn
```
