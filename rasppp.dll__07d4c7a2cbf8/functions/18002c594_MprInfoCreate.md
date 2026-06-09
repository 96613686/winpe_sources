# MprInfoCreate

- ea: `0x18002c594`
- end: `0x18002c5fb`
- name: `MprInfoCreate`
- size: `103`
- prototype: `DWORD __stdcall(DWORD dwVersion, LPVOID *lplpNewHeader)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800187f8`
- `0x1800189d8`
- `0x180018e1c`

## callees

- `0x18002c594`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c5ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c5ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c5bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c5bd`

## pseudocode

```c
DWORD __stdcall MprInfoCreate(DWORD dwVersion, LPVOID *lplpNewHeader)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v5; // rax

  if ( !lplpNewHeader )
    return 87;
  *lplpNewHeader = 0;
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0xCu);
  *lplpNewHeader = v5;
  if ( !v5 )
    return 8;
  *(_QWORD *)v5 = 0;
  v5[2] = 0;
  *(_DWORD *)*lplpNewHeader = 1;
  *((_DWORD *)*lplpNewHeader + 1) = 12;
  *((_DWORD *)*lplpNewHeader + 2) = 0;
  return 0;
}

```

## disassembly

```asm
0x18002c594  push    rbx
0x18002c596  sub     rsp, 20h
0x18002c59a  mov     rbx, rdx
0x18002c59d  test    rdx, rdx
0x18002c5a0  jnz     short loc_18002C5A7
0x18002c5a2  lea     eax, [rdx+57h]
0x18002c5a5  jmp     short loc_18002C5F5
0x18002c5a7  mov     qword ptr [rdx], 0
0x18002c5ae  call    cs:__imp_GetProcessHeap
0x18002c5b4  xor     edx, edx; dwFlags
0x18002c5b6  mov     rcx, rax; hHeap
0x18002c5b9  lea     r8d, [rdx+0Ch]; dwBytes
0x18002c5bd  call    cs:__imp_HeapAlloc
0x18002c5c3  mov     [rbx], rax
0x18002c5c6  test    rax, rax
0x18002c5c9  jnz     short loc_18002C5D2
0x18002c5cb  mov     eax, 8
0x18002c5d0  jmp     short loc_18002C5F5
0x18002c5d2  xor     ecx, ecx
0x18002c5d4  mov     [rax], rcx
0x18002c5d7  mov     [rax+8], ecx
0x18002c5da  mov     rax, [rbx]
0x18002c5dd  mov     dword ptr [rax], 1
0x18002c5e3  mov     rax, [rbx]
0x18002c5e6  mov     dword ptr [rax+4], 0Ch
0x18002c5ed  mov     rax, [rbx]
0x18002c5f0  mov     [rax+8], ecx
0x18002c5f3  xor     eax, eax
0x18002c5f5  add     rsp, 20h
0x18002c5f9  pop     rbx
0x18002c5fa  retn
```
