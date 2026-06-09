# DecompressEnd

- ea: `0x1800022a4`
- end: `0x1800022db`
- name: `DecompressEnd`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`
- `0x1800021c8`

## callees

- `0x1800022a4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800022be`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800022be`

## pseudocode

```c
__int64 __fastcall DecompressEnd(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 8);
  if ( v2 )
  {
    VirtualFree(v2, 0, 0x8000u);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)(a1 + 4) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800022a4  push    rbx
0x1800022a6  sub     rsp, 20h
0x1800022aa  mov     rbx, rcx
0x1800022ad  mov     rcx, [rcx+8]; lpAddress
0x1800022b1  test    rcx, rcx
0x1800022b4  jz      short loc_1800022CC
0x1800022b6  xor     edx, edx; dwSize
0x1800022b8  mov     r8d, 8000h; dwFreeType
0x1800022be  call    cs:__imp_VirtualFree
0x1800022c4  mov     qword ptr [rbx+8], 0
0x1800022cc  mov     dword ptr [rbx+4], 0
0x1800022d3  xor     eax, eax
0x1800022d5  add     rsp, 20h
0x1800022d9  pop     rbx
0x1800022da  retn
```
