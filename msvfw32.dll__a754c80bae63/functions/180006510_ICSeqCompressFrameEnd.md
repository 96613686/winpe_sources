# ICSeqCompressFrameEnd

- ea: `0x180006510`
- end: `0x1800065d5`
- name: `ICSeqCompressFrameEnd`
- size: `197`
- prototype: `void __stdcall(PCOMPVARS pc)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003a60`
- `0x180006510`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000657b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800065ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000657b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800065ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006572`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006585`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800065a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800065b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006572`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006585`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800065a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800065b8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000658e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800065c1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000658e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800065c1`

## pseudocode

```c
void __stdcall ICSeqCompressFrameEnd(PCOMPVARS pc)
{
  HIC hic; // rcx
  const void *lpBitsOut; // rcx
  HGLOBAL v4; // rax
  HGLOBAL v5; // rax
  const void *lpBitsPrev; // rcx
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax

  if ( pc && pc->cbSize == 96 && pc->lpBitsOut )
  {
    hic = pc->hic;
    if ( hic )
    {
      ICSendMessage(hic, 0x4009u, 0, 0);
      if ( pc->lpBitsPrev )
        ICSendMessage(pc->hic, 0x400Eu, 0, 0);
    }
    lpBitsOut = pc->lpBitsOut;
    if ( lpBitsOut )
    {
      v4 = GlobalHandle(lpBitsOut);
      GlobalUnlock(v4);
      v5 = GlobalHandle(pc->lpBitsOut);
      GlobalFree(v5);
      pc->lpBitsOut = 0;
    }
    lpBitsPrev = pc->lpBitsPrev;
    if ( lpBitsPrev )
    {
      v7 = GlobalHandle(lpBitsPrev);
      GlobalUnlock(v7);
      v8 = GlobalHandle(pc->lpBitsPrev);
      GlobalFree(v8);
      pc->lpBitsPrev = 0;
    }
  }
}

```

## disassembly

```asm
0x180006510  test    rcx, rcx
0x180006513  jz      locret_1800065D4
0x180006519  push    rbx
0x18000651a  sub     rsp, 20h
0x18000651e  cmp     dword ptr [rcx], 60h ; '`'
0x180006521  mov     rbx, rcx
0x180006524  jnz     loc_1800065CF
0x18000652a  cmp     qword ptr [rcx+28h], 0
0x18000652f  jz      loc_1800065CF
0x180006535  mov     rcx, [rcx+8]; hic
0x180006539  test    rcx, rcx
0x18000653c  jz      short loc_180006569
0x18000653e  xor     r9d, r9d; dw2
0x180006541  xor     r8d, r8d; dw1
0x180006544  mov     edx, 4009h; msg
0x180006549  call    ICSendMessage
0x18000654e  cmp     qword ptr [rbx+30h], 0
0x180006553  jz      short loc_180006569
0x180006555  mov     rcx, [rbx+8]; hic
0x180006559  xor     r9d, r9d; dw2
0x18000655c  xor     r8d, r8d; dw1
0x18000655f  mov     edx, 400Eh; msg
0x180006564  call    ICSendMessage
0x180006569  mov     rcx, [rbx+28h]; pMem
0x18000656d  test    rcx, rcx
0x180006570  jz      short loc_18000659C
0x180006572  call    cs:__imp_GlobalHandle
0x180006578  mov     rcx, rax; hMem
0x18000657b  call    cs:__imp_GlobalUnlock
0x180006581  mov     rcx, [rbx+28h]; pMem
0x180006585  call    cs:__imp_GlobalHandle
0x18000658b  mov     rcx, rax; hMem
0x18000658e  call    cs:__imp_GlobalFree
0x180006594  mov     qword ptr [rbx+28h], 0
0x18000659c  mov     rcx, [rbx+30h]; pMem
0x1800065a0  test    rcx, rcx
0x1800065a3  jz      short loc_1800065CF
0x1800065a5  call    cs:__imp_GlobalHandle
0x1800065ab  mov     rcx, rax; hMem
0x1800065ae  call    cs:__imp_GlobalUnlock
0x1800065b4  mov     rcx, [rbx+30h]; pMem
0x1800065b8  call    cs:__imp_GlobalHandle
0x1800065be  mov     rcx, rax; hMem
0x1800065c1  call    cs:__imp_GlobalFree
0x1800065c7  mov     qword ptr [rbx+30h], 0
0x1800065cf  add     rsp, 20h
0x1800065d3  pop     rbx
0x1800065d4  retn
```
