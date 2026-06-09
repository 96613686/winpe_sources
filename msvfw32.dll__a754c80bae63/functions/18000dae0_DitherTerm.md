# DitherTerm

- ea: `0x18000dae0`
- end: `0x18000db75`
- name: `DitherTerm`
- size: `149`
- prototype: `__int64 __fastcall(LPCVOID pMem)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008400`
- `0x18000a860`
- `0x18000d7c0`

## callees

- `0x18000dae0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000db19`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000db57`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000db19`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000db57`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db26`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db60`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db26`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000db60`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000db2f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000db69`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000db2f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000db69`

## pseudocode

```c
void __fastcall DitherTerm(LPCVOID pMem)
{
  int v2; // eax
  HGLOBAL v3; // rax
  HGLOBAL v4; // rax
  HGLOBAL v5; // rax
  HGLOBAL v6; // rax

  if ( pMem == glpDitherTable )
  {
    v2 = giDitherTableUsage;
    if ( giDitherTableUsage )
    {
      --giDitherTableUsage;
      if ( v2 - 1 <= 0 )
      {
        if ( glpDitherTable )
        {
          v3 = GlobalHandle(glpDitherTable);
          GlobalUnlock(v3);
          v4 = GlobalHandle(glpDitherTable);
          GlobalFree(v4);
          glpDitherTable = 0;
        }
      }
    }
  }
  else if ( pMem )
  {
    v5 = GlobalHandle(pMem);
    GlobalUnlock(v5);
    v6 = GlobalHandle(pMem);
    GlobalFree(v6);
  }
}

```

## disassembly

```asm
0x18000dae0  push    rbx
0x18000dae2  sub     rsp, 20h
0x18000dae6  mov     rbx, rcx
0x18000dae9  mov     rcx, cs:glpDitherTable; pMem
0x18000daf0  cmp     rbx, rcx
0x18000daf3  jnz     short loc_18000DB46
0x18000daf5  mov     eax, cs:giDitherTableUsage
0x18000dafb  test    eax, eax
0x18000dafd  jz      short loc_18000DB6F
0x18000daff  dec     eax
0x18000db01  mov     cs:giDitherTableUsage, eax
0x18000db07  test    eax, eax
0x18000db09  jg      short loc_18000DB6F
0x18000db0b  test    rcx, rcx
0x18000db0e  jz      short loc_18000DB6F
0x18000db10  call    cs:__imp_GlobalHandle
0x18000db16  mov     rcx, rax; hMem
0x18000db19  call    cs:__imp_GlobalUnlock
0x18000db1f  mov     rcx, cs:glpDitherTable; pMem
0x18000db26  call    cs:__imp_GlobalHandle
0x18000db2c  mov     rcx, rax; hMem
0x18000db2f  call    cs:__imp_GlobalFree
0x18000db35  mov     cs:glpDitherTable, 0
0x18000db40  add     rsp, 20h
0x18000db44  pop     rbx
0x18000db45  retn
0x18000db46  test    rbx, rbx
0x18000db49  jz      short loc_18000DB6F
0x18000db4b  mov     rcx, rbx; pMem
0x18000db4e  call    cs:__imp_GlobalHandle
0x18000db54  mov     rcx, rax; hMem
0x18000db57  call    cs:__imp_GlobalUnlock
0x18000db5d  mov     rcx, rbx; pMem
0x18000db60  call    cs:__imp_GlobalHandle
0x18000db66  mov     rcx, rax; hMem
0x18000db69  call    cs:__imp_GlobalFree
0x18000db6f  add     rsp, 20h
0x18000db73  pop     rbx
0x18000db74  retn
```
