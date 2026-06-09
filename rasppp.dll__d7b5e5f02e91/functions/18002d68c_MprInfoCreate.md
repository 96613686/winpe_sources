# MprInfoCreate

- ea: `0x18002d68c`
- end: `0x18002d700`
- name: `MprInfoCreate`
- size: `116`
- prototype: `DWORD __stdcall(DWORD dwVersion, LPVOID *lplpNewHeader)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180019098`
- `0x18001928c`
- `0x18001973c`

## callees

- `0x18002d68c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d6a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d6a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d6bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d6bb`

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
0x18002d68c  push    rbx
0x18002d68e  sub     rsp, 20h
0x18002d692  mov     rbx, rdx
0x18002d695  test    rdx, rdx
0x18002d698  jnz     short loc_18002D69F
0x18002d69a  lea     eax, [rdx+57h]
0x18002d69d  jmp     short loc_18002D6F9
0x18002d69f  mov     qword ptr [rdx], 0
0x18002d6a6  call    cs:__imp_GetProcessHeap
0x18002d6ad  nop     dword ptr [rax+rax+00h]
0x18002d6b2  xor     edx, edx; dwFlags
0x18002d6b4  mov     rcx, rax; hHeap
0x18002d6b7  lea     r8d, [rdx+0Ch]; dwBytes
0x18002d6bb  call    cs:__imp_HeapAlloc
0x18002d6c2  nop     dword ptr [rax+rax+00h]
0x18002d6c7  mov     [rbx], rax
0x18002d6ca  test    rax, rax
0x18002d6cd  jnz     short loc_18002D6D6
0x18002d6cf  mov     eax, 8
0x18002d6d4  jmp     short loc_18002D6F9
0x18002d6d6  xor     ecx, ecx
0x18002d6d8  mov     [rax], rcx
0x18002d6db  mov     [rax+8], ecx
0x18002d6de  mov     rax, [rbx]
0x18002d6e1  mov     dword ptr [rax], 1
0x18002d6e7  mov     rax, [rbx]
0x18002d6ea  mov     dword ptr [rax+4], 0Ch
0x18002d6f1  mov     rax, [rbx]
0x18002d6f4  mov     [rax+8], ecx
0x18002d6f7  xor     eax, eax
0x18002d6f9  add     rsp, 20h
0x18002d6fd  pop     rbx
0x18002d6fe  retn
```
