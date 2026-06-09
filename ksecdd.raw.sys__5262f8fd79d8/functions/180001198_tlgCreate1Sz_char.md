# _tlgCreate1Sz_char

- ea: `0x180001198`
- end: `0x1800011c8`
- name: `_tlgCreate1Sz_char`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001023c`

## callees

- `0x180001198`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_char(__int64 a1, _BYTE *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a2[v2] );
    result = (unsigned int)(v2 + 1);
  }
  else
  {
    a2 = &unk_1800169E8;
    result = 1;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180001198  test    rdx, rdx
0x18000119b  jz      short loc_1800011AE
0x18000119d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011a1  inc     rax
0x1800011a4  cmp     byte ptr [rdx+rax], 0
0x1800011a8  jnz     short loc_1800011A1
0x1800011aa  inc     eax
0x1800011ac  jmp     short loc_1800011BA
0x1800011ae  lea     rdx, unk_1800169E8
0x1800011b5  mov     eax, 1
0x1800011ba  mov     [rcx], rdx
0x1800011bd  mov     [rcx+8], eax
0x1800011c0  mov     dword ptr [rcx+0Ch], 0
0x1800011c7  retn
```
