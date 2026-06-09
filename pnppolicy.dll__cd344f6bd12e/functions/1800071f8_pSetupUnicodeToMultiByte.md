# pSetupUnicodeToMultiByte

- ea: `0x1800071f8`
- end: `0x180007294`
- name: `pSetupUnicodeToMultiByte`
- size: `156`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180006590`
- `0x180006ba4`

## callees

- `0x1800071f8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000726e`
- `KERNEL32!HeapFree` at `0x18000726e`
- `KERNEL32!HeapReAlloc` at `0x180007279`
- `KERNEL32!HeapReAlloc` at `0x180007279`
- `KERNEL32!HeapAlloc` at `0x180007229`
- `KERNEL32!HeapAlloc` at `0x180007229`
- `KERNEL32!WideCharToMultiByte` at `0x180007258`
- `KERNEL32!WideCharToMultiByte` at `0x180007258`

## pseudocode

```c
CHAR *__fastcall pSetupUnicodeToMultiByte(LPCWCH lpWideCharStr)
{
  __int64 v1; // rax
  int v3; // esi
  CHAR *lpMultiByteStr; // rax
  CHAR *v5; // rbx
  unsigned int v7; // eax
  LPVOID v8; // rax

  v1 = -1;
  do
    ++v1;
  while ( lpWideCharStr[v1] );
  v3 = v1 + 1;
  lpMultiByteStr = (CHAR *)HeapAlloc(hHeap, 0, (unsigned int)(2 * (v1 + 1)));
  v5 = lpMultiByteStr;
  if ( !lpMultiByteStr )
    return 0;
  v7 = WideCharToMultiByte(0, 0, lpWideCharStr, v3, lpMultiByteStr, 2 * v3, 0, 0);
  if ( !v7 )
  {
    HeapFree(hHeap, 0, v5);
    return 0;
  }
  v8 = HeapReAlloc(hHeap, 0, v5, v7);
  if ( v8 )
    return (CHAR *)v8;
  return v5;
}

```

## disassembly

```asm
0x1800071f8  push    rbx
0x1800071fa  push    rbp
0x1800071fb  push    rsi
0x1800071fc  push    rdi
0x1800071fd  push    r14
0x1800071ff  sub     rsp, 40h
0x180007203  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007207  mov     rdi, rcx
0x18000720a  xor     r14d, r14d
0x18000720d  inc     rax
0x180007210  cmp     [rcx+rax*2], r14w
0x180007215  jnz     short loc_18000720D
0x180007217  mov     rcx, cs:hHeap; hHeap
0x18000721e  lea     esi, [rax+1]
0x180007221  lea     ebp, [rsi+rsi]
0x180007224  xor     edx, edx; dwFlags
0x180007226  mov     r8d, ebp; dwBytes
0x180007229  call    cs:__imp_HeapAlloc
0x18000722f  mov     rbx, rax
0x180007232  test    rax, rax
0x180007235  jnz     short loc_18000723B
0x180007237  xor     eax, eax
0x180007239  jmp     short loc_180007289
0x18000723b  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180007240  mov     r9d, esi; cchWideChar
0x180007243  mov     [rsp+68h+lpDefaultChar], r14; lpDefaultChar
0x180007248  mov     r8, rdi; lpWideCharStr
0x18000724b  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x18000724f  xor     edx, edx; dwFlags
0x180007251  xor     ecx, ecx; CodePage
0x180007253  mov     [rsp+68h+lpMultiByteStr], rbx; lpMultiByteStr
0x180007258  call    cs:__imp_WideCharToMultiByte
0x18000725e  mov     rcx, cs:hHeap; hHeap
0x180007265  xor     edx, edx; dwFlags
0x180007267  mov     r8, rbx; lpMem
0x18000726a  test    eax, eax
0x18000726c  jnz     short loc_180007276
0x18000726e  call    cs:__imp_HeapFree
0x180007274  jmp     short loc_180007237
0x180007276  mov     r9d, eax; dwBytes
0x180007279  call    cs:__imp_HeapReAlloc
0x18000727f  test    rax, rax
0x180007282  cmovnz  rbx, rax
0x180007286  mov     rax, rbx
0x180007289  add     rsp, 40h
0x18000728d  pop     r14
0x18000728f  pop     rdi
0x180007290  pop     rsi
0x180007291  pop     rbp
0x180007292  pop     rbx
0x180007293  retn
```
