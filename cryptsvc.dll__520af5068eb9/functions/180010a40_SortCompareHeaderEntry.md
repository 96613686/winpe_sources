# _SortCompareHeaderEntry

- ea: `0x180010a40`
- end: `0x180010a73`
- name: `_SortCompareHeaderEntry`
- size: `51`
- prototype: `int __fastcall(const void ****, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010a40`
- `0x1800174f0`

## pseudocode

```c
int __fastcall SortCompareHeaderEntry(const void ****a1, __int64 **a2)
{
  const void **v2; // rcx
  __int64 v3; // rdx

  v2 = **a1;
  v3 = **a2;
  if ( *(_DWORD *)v2 != *(_DWORD *)v3 )
    return *(_DWORD *)v2 < *(_DWORD *)v3 ? -1 : 1;
  if ( *(_DWORD *)v2 )
    return memcmp_0(v2[1], *(const void **)(v3 + 8), *(unsigned int *)v2);
  return 0;
}

```

## disassembly

```asm
0x180010a40  mov     rax, [rcx]
0x180010a43  mov     rcx, [rax]
0x180010a46  mov     rax, [rdx]
0x180010a49  mov     rdx, [rax]
0x180010a4c  mov     eax, [rdx]
0x180010a4e  cmp     [rcx], eax
0x180010a50  jnz     short loc_180010A6B
0x180010a52  cmp     dword ptr [rcx], 0
0x180010a55  jnz     short loc_180010A5B
0x180010a57  xor     eax, eax
0x180010a59  jmp     short locret_180010A72
0x180010a5b  mov     r8d, [rcx]; Size
0x180010a5e  mov     rcx, [rcx+8]; Buf1
0x180010a62  mov     rdx, [rdx+8]; Buf2
0x180010a66  jmp     memcmp_0
0x180010a6b  sbb     eax, eax
0x180010a6d  and     eax, 0FFFFFFFEh
0x180010a70  inc     eax
0x180010a72  retn
```
