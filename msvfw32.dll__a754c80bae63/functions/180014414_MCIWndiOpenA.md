# MCIWndiOpenA

- ea: `0x180014414`
- end: `0x1800144a0`
- name: `MCIWndiOpenA`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cc0`

## callees

- `0x1800100e4`
- `0x180013edc`
- `0x180014414`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014485`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014485`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001444f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001444f`

## pseudocode

```c
__int64 __fastcall MCIWndiOpenA(__int64 a1, char a2, LPARAM *a3)
{
  __int64 v6; // r8
  int v7; // r14d
  WCHAR *v8; // rax
  LPARAM *v9; // rdi
  __int64 v11; // rbx

  if ( (unsigned __int64)a3 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return MCIWndiOpen(a1, a2, a3);
  v6 = -1;
  do
    ++v6;
  while ( *((_BYTE *)a3 + v6) );
  v7 = v6 + 1;
  v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * ((int)v6 + 1));
  v9 = (LPARAM *)v8;
  if ( !v8 )
    return -1;
  Imbstowcs(v8, (LPCCH)a3, v7);
  v11 = MCIWndiOpen(a1, a2, v9);
  LocalFree(v9);
  return v11;
}

```

## disassembly

```asm
0x180014414  push    rbx
0x180014416  push    rbp
0x180014417  push    rsi
0x180014418  push    rdi
0x180014419  push    r14
0x18001441b  sub     rsp, 20h
0x18001441f  lea     rax, [r8-1]
0x180014423  mov     rbx, r8
0x180014426  mov     rsi, rdx
0x180014429  mov     rbp, rcx
0x18001442c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014430  ja      short loc_180014490
0x180014432  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014436  inc     r8
0x180014439  cmp     byte ptr [rbx+r8], 0
0x18001443e  jnz     short loc_180014436
0x180014440  lea     r14d, [r8+1]
0x180014444  mov     ecx, 40h ; '@'; uFlags
0x180014449  movsxd  rdx, r14d
0x18001444c  add     rdx, rdx; uBytes
0x18001444f  call    cs:__imp_LocalAlloc
0x180014455  mov     rdi, rax
0x180014458  test    rax, rax
0x18001445b  jnz     short loc_180014463
0x18001445d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014461  jmp     short loc_180014495
0x180014463  mov     r8d, r14d; cchWideChar
0x180014466  mov     rdx, rbx; lpMultiByteStr
0x180014469  mov     rcx, rdi; lpWideCharStr
0x18001446c  call    Imbstowcs
0x180014471  mov     r8, rdi
0x180014474  mov     rdx, rsi
0x180014477  mov     rcx, rbp
0x18001447a  call    MCIWndiOpen
0x18001447f  mov     rcx, rdi; hMem
0x180014482  mov     rbx, rax
0x180014485  call    cs:__imp_LocalFree
0x18001448b  mov     rax, rbx
0x18001448e  jmp     short loc_180014495
0x180014490  call    MCIWndiOpen
0x180014495  add     rsp, 20h
0x180014499  pop     r14
0x18001449b  pop     rdi
0x18001449c  pop     rsi
0x18001449d  pop     rbp
0x18001449e  pop     rbx
0x18001449f  retn
```
