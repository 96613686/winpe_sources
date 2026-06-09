# CompressEnd

- ea: `0x180006760`
- end: `0x1800067b8`
- name: `CompressEnd`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005e00`
- `0x1800064e8`

## callees

- `0x180006760`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000678f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000678f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006786`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006799`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006786`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006799`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800067a2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800067a2`

## pseudocode

```c
__int64 __fastcall CompressEnd(__int64 a1)
{
  const void *v3; // rcx
  HGLOBAL v4; // rax
  HGLOBAL v5; // rax

  if ( !*(_DWORD *)(a1 + 28) )
    return 4294967196LL;
  *(_DWORD *)(a1 + 28) = 0;
  v3 = *(const void **)(a1 + 56);
  if ( v3 )
  {
    v4 = GlobalHandle(v3);
    GlobalUnlock(v4);
    v5 = GlobalHandle(*(LPCVOID *)(a1 + 56));
    GlobalFree(v5);
  }
  *(_QWORD *)(a1 + 56) = 0;
  return 0;
}

```

## disassembly

```asm
0x180006760  push    rbx
0x180006762  sub     rsp, 20h
0x180006766  cmp     dword ptr [rcx+1Ch], 0
0x18000676a  mov     rbx, rcx
0x18000676d  jnz     short loc_180006776
0x18000676f  mov     eax, 0FFFFFF9Ch
0x180006774  jmp     short loc_1800067B2
0x180006776  mov     dword ptr [rcx+1Ch], 0
0x18000677d  mov     rcx, [rcx+38h]; pMem
0x180006781  test    rcx, rcx
0x180006784  jz      short loc_1800067A8
0x180006786  call    cs:__imp_GlobalHandle
0x18000678c  mov     rcx, rax; hMem
0x18000678f  call    cs:__imp_GlobalUnlock
0x180006795  mov     rcx, [rbx+38h]; pMem
0x180006799  call    cs:__imp_GlobalHandle
0x18000679f  mov     rcx, rax; hMem
0x1800067a2  call    cs:__imp_GlobalFree
0x1800067a8  mov     qword ptr [rbx+38h], 0
0x1800067b0  xor     eax, eax
0x1800067b2  add     rsp, 20h
0x1800067b6  pop     rbx
0x1800067b7  retn
```
