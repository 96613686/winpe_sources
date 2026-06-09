# _tlgCreate1Sz_wchar_t

- ea: `0x140001008`
- end: `0x14000103e`
- name: `_tlgCreate1Sz_wchar_t`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f290`
- `0x14000f9b8`

## callees

- `0x140001008`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, const WCHAR *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a2[v2] );
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = &word_1400061B0;
    result = 2;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x140001008  xor     r8d, r8d
0x14000100b  test    rdx, rdx
0x14000100e  jz      short loc_140001027
0x140001010  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001014  inc     rax
0x140001017  cmp     [rdx+rax*2], r8w
0x14000101c  jnz     short loc_140001014
0x14000101e  lea     eax, ds:2[rax*2]
0x140001025  jmp     short loc_140001033
0x140001027  lea     rdx, word_1400061B0
0x14000102e  mov     eax, 2
0x140001033  mov     [rcx], rdx
0x140001036  mov     [rcx+8], eax
0x140001039  mov     [rcx+0Ch], r8d
0x14000103d  retn
```
