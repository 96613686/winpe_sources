# OE_DPA_DeletePtr

- ea: `0x1800100d0`
- end: `0x18001019c`
- name: `OE_DPA_DeletePtr`
- size: `204`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ec10`
- `0x18000ed10`
- `0x180013060`
- `0x1800229f8`
- `0x1800245dc`
- `0x1800365b0`
- `0x18003817c`
- `0x1800c7d68`
- `0x1800c8a80`

## callees

- `0x1800100d0`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x18001011a`
- `KERNEL32!RtlMoveMemory` at `0x18001011a`
- `KERNEL32!GetProcessHeap` at `0x180010138`
- `KERNEL32!GetProcessHeap` at `0x180010168`
- `KERNEL32!GetProcessHeap` at `0x180010138`
- `KERNEL32!GetProcessHeap` at `0x180010168`
- `KERNEL32!HeapFree` at `0x180010176`
- `KERNEL32!HeapFree` at `0x180010176`
- `KERNEL32!HeapReAlloc` at `0x180010152`
- `KERNEL32!HeapReAlloc` at `0x180010152`

## pseudocode

```c
__int64 __fastcall OE_DPA_DeletePtr(unsigned int *a1, unsigned int a2)
{
  unsigned int v3; // r8d
  __int64 v4; // r9
  __int64 *v5; // rcx
  __int64 v6; // r14
  unsigned int v7; // esi
  unsigned int v8; // ebp
  void *v9; // rbx
  HANDLE v10; // rax
  LPVOID v11; // rax
  HANDLE ProcessHeap; // rax

  if ( !a1 )
    return 0;
  v3 = *a1;
  if ( a2 >= *a1 )
    return 0;
  v4 = *((_QWORD *)a1 + 1);
  v5 = (__int64 *)(v4 + 8LL * a2);
  v6 = *v5;
  if ( a2 < v3 - 1 )
    RtlMoveMemory(v5, v4 + 8LL * (a2 + 1), 8 * (v3 - a2) - 8);
  --*a1;
  v7 = a1[4];
  v8 = a1[5];
  if ( v7 - *a1 > v8 )
  {
    v9 = (void *)*((_QWORD *)a1 + 1);
    if ( v7 <= v8 )
    {
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        *((_QWORD *)a1 + 1) = 0;
      }
    }
    else
    {
      v10 = GetProcessHeap();
      v11 = HeapReAlloc(v10, 8u, v9, 8LL * (v7 - v8));
      if ( v11 )
        *((_QWORD *)a1 + 1) = v11;
    }
    a1[4] -= a1[5];
  }
  return v6;
}

```

## disassembly

```asm
0x1800100d0  push    rbx
0x1800100d2  push    rbp
0x1800100d3  push    rsi
0x1800100d4  push    rdi
0x1800100d5  push    r14
0x1800100d7  sub     rsp, 20h
0x1800100db  mov     rdi, rcx
0x1800100de  test    rcx, rcx
0x1800100e1  jz      loc_18001018F
0x1800100e7  mov     r8d, [rcx]
0x1800100ea  cmp     edx, r8d
0x1800100ed  jnb     loc_18001018F
0x1800100f3  mov     r9, [rcx+8]
0x1800100f7  mov     eax, edx
0x1800100f9  lea     rcx, [r9+rax*8]
0x1800100fd  mov     r14, [rcx]
0x180010100  lea     eax, [r8-1]
0x180010104  cmp     edx, eax
0x180010106  jnb     short loc_180010120
0x180010108  sub     r8d, edx
0x18001010b  lea     eax, [rdx+1]
0x18001010e  lea     rdx, [r9+rax*8]
0x180010112  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[r8*8]
0x18001011a  call    cs:__imp_RtlMoveMemory
0x180010120  dec     dword ptr [rdi]
0x180010122  mov     esi, [rdi+10h]
0x180010125  mov     eax, esi
0x180010127  sub     eax, [rdi]
0x180010129  mov     ebp, [rdi+14h]
0x18001012c  cmp     eax, ebp
0x18001012e  jbe     short loc_18001018A
0x180010130  mov     rbx, [rdi+8]
0x180010134  cmp     esi, ebp
0x180010136  jbe     short loc_180010163
0x180010138  call    cs:__imp_GetProcessHeap
0x18001013e  sub     esi, ebp
0x180010140  mov     r8, rbx; lpMem
0x180010143  mov     r9d, esi
0x180010146  mov     edx, 8; dwFlags
0x18001014b  shl     r9, 3; dwBytes
0x18001014f  mov     rcx, rax; hHeap
0x180010152  call    cs:__imp_HeapReAlloc
0x180010158  test    rax, rax
0x18001015b  jz      short loc_180010184
0x18001015d  mov     [rdi+8], rax
0x180010161  jmp     short loc_180010184
0x180010163  test    rbx, rbx
0x180010166  jz      short loc_180010184
0x180010168  call    cs:__imp_GetProcessHeap
0x18001016e  mov     r8, rbx; lpMem
0x180010171  xor     edx, edx; dwFlags
0x180010173  mov     rcx, rax; hHeap
0x180010176  call    cs:__imp_HeapFree
0x18001017c  mov     qword ptr [rdi+8], 0
0x180010184  mov     ecx, [rdi+14h]
0x180010187  sub     [rdi+10h], ecx
0x18001018a  mov     rax, r14
0x18001018d  jmp     short loc_180010191
0x18001018f  xor     eax, eax
0x180010191  add     rsp, 20h
0x180010195  pop     r14
0x180010197  pop     rdi
0x180010198  pop     rsi
0x180010199  pop     rbp
0x18001019a  pop     rbx
0x18001019b  retn
```
