# ICCompressorFree

- ea: `0x180005be0`
- end: `0x180005ce9`
- name: `ICCompressorFree`
- size: `265`
- prototype: `void __stdcall(PCOMPVARS pc)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004590`

## callees

- `0x180002640`
- `0x180005be0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005c22`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005c55`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005c88`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005cbb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005c22`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005c55`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005c88`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005cbb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c19`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c2c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c4c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c5f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c7f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005cb2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005cc5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c19`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c2c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c4c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c5f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c7f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005c92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005cb2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005cc5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c35`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c68`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c9b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005cce`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c35`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c68`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c9b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005cce`

## pseudocode

```c
void __stdcall ICCompressorFree(PCOMPVARS pc)
{
  HIC hic; // rcx
  LPBITMAPINFO lpbiOut; // rcx
  HGLOBAL v4; // rax
  HGLOBAL v5; // rax
  const void *lpBitsOut; // rcx
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax
  const void *lpBitsPrev; // rcx
  HGLOBAL v10; // rax
  HGLOBAL v11; // rax
  const void *lpState; // rcx
  HGLOBAL v13; // rax
  HGLOBAL v14; // rax

  if ( pc && pc->cbSize == 96 )
  {
    hic = pc->hic;
    if ( hic )
    {
      ICClose(hic);
      pc->hic = 0;
    }
    lpbiOut = pc->lpbiOut;
    if ( lpbiOut )
    {
      v4 = GlobalHandle(lpbiOut);
      GlobalUnlock(v4);
      v5 = GlobalHandle(pc->lpbiOut);
      GlobalFree(v5);
      pc->lpbiOut = 0;
    }
    lpBitsOut = pc->lpBitsOut;
    if ( lpBitsOut )
    {
      v7 = GlobalHandle(lpBitsOut);
      GlobalUnlock(v7);
      v8 = GlobalHandle(pc->lpBitsOut);
      GlobalFree(v8);
      pc->lpBitsOut = 0;
    }
    lpBitsPrev = pc->lpBitsPrev;
    if ( lpBitsPrev )
    {
      v10 = GlobalHandle(lpBitsPrev);
      GlobalUnlock(v10);
      v11 = GlobalHandle(pc->lpBitsPrev);
      GlobalFree(v11);
      pc->lpBitsPrev = 0;
    }
    lpState = pc->lpState;
    if ( lpState )
    {
      v13 = GlobalHandle(lpState);
      GlobalUnlock(v13);
      v14 = GlobalHandle(pc->lpState);
      GlobalFree(v14);
      pc->lpState = 0;
    }
    pc->dwFlags = 0;
  }
}

```

## disassembly

```asm
0x180005be0  test    rcx, rcx
0x180005be3  jz      locret_180005CE8
0x180005be9  push    rbx
0x180005bea  sub     rsp, 20h
0x180005bee  cmp     dword ptr [rcx], 60h ; '`'
0x180005bf1  mov     rbx, rcx
0x180005bf4  jnz     loc_180005CE3
0x180005bfa  mov     rcx, [rcx+8]; hic
0x180005bfe  test    rcx, rcx
0x180005c01  jz      short loc_180005C10
0x180005c03  call    ICClose
0x180005c08  mov     qword ptr [rbx+8], 0
0x180005c10  mov     rcx, [rbx+20h]; pMem
0x180005c14  test    rcx, rcx
0x180005c17  jz      short loc_180005C43
0x180005c19  call    cs:__imp_GlobalHandle
0x180005c1f  mov     rcx, rax; hMem
0x180005c22  call    cs:__imp_GlobalUnlock
0x180005c28  mov     rcx, [rbx+20h]; pMem
0x180005c2c  call    cs:__imp_GlobalHandle
0x180005c32  mov     rcx, rax; hMem
0x180005c35  call    cs:__imp_GlobalFree
0x180005c3b  mov     qword ptr [rbx+20h], 0
0x180005c43  mov     rcx, [rbx+28h]; pMem
0x180005c47  test    rcx, rcx
0x180005c4a  jz      short loc_180005C76
0x180005c4c  call    cs:__imp_GlobalHandle
0x180005c52  mov     rcx, rax; hMem
0x180005c55  call    cs:__imp_GlobalUnlock
0x180005c5b  mov     rcx, [rbx+28h]; pMem
0x180005c5f  call    cs:__imp_GlobalHandle
0x180005c65  mov     rcx, rax; hMem
0x180005c68  call    cs:__imp_GlobalFree
0x180005c6e  mov     qword ptr [rbx+28h], 0
0x180005c76  mov     rcx, [rbx+30h]; pMem
0x180005c7a  test    rcx, rcx
0x180005c7d  jz      short loc_180005CA9
0x180005c7f  call    cs:__imp_GlobalHandle
0x180005c85  mov     rcx, rax; hMem
0x180005c88  call    cs:__imp_GlobalUnlock
0x180005c8e  mov     rcx, [rbx+30h]; pMem
0x180005c92  call    cs:__imp_GlobalHandle
0x180005c98  mov     rcx, rax; hMem
0x180005c9b  call    cs:__imp_GlobalFree
0x180005ca1  mov     qword ptr [rbx+30h], 0
0x180005ca9  mov     rcx, [rbx+50h]; pMem
0x180005cad  test    rcx, rcx
0x180005cb0  jz      short loc_180005CDC
0x180005cb2  call    cs:__imp_GlobalHandle
0x180005cb8  mov     rcx, rax; hMem
0x180005cbb  call    cs:__imp_GlobalUnlock
0x180005cc1  mov     rcx, [rbx+50h]; pMem
0x180005cc5  call    cs:__imp_GlobalHandle
0x180005ccb  mov     rcx, rax; hMem
0x180005cce  call    cs:__imp_GlobalFree
0x180005cd4  mov     qword ptr [rbx+50h], 0
0x180005cdc  mov     dword ptr [rbx+4], 0
0x180005ce3  add     rsp, 20h
0x180005ce7  pop     rbx
0x180005ce8  retn
```
