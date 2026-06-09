# DsRolepCheckFilePaths

- ea: `0x180003994`
- end: `0x180003a78`
- name: `DsRolepCheckFilePaths`
- size: `228`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH, STRSAFE_PCNZWCH)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a80`
- `0x1800058a0`
- `0x180005e40`
- `0x180006c30`

## callees

- `0x180003994`
- `0x18000e118`
- `0x180020dbc`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800039ce`
- `msvcrt!_wcsnicmp` at `0x1800039e1`
- `msvcrt!_wcsnicmp` at `0x1800039ce`
- `msvcrt!_wcsnicmp` at `0x1800039e1`

## string_xrefs

- `0x180003a4d`: `Database paths subset of sysvol\n`

## pseudocode

```c
__int64 __fastcall DsRolepCheckFilePaths(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH a2, STRSAFE_PCNZWCH a3)
{
  size_t v4; // rbx
  unsigned int v7; // ecx

  v4 = -1;
  do
    ++v4;
  while ( a3[v4] );
  if ( !_wcsnicmp(a3, pszSrc, v4) || !_wcsnicmp(a3, a2, v4) )
  {
    DsRolepLogPrintRoutine(4, "Database paths subset of sysvol\n");
    return 161;
  }
  v7 = DsRolepValidatePath(pszSrc);
  if ( !v7 )
    return 161;
  return v7;
}

```

## disassembly

```asm
0x180003994  mov     [rsp+arg_0], rbx
0x180003999  mov     [rsp+arg_8], rbp
0x18000399e  push    rsi
0x18000399f  push    rdi
0x1800039a0  push    r14
0x1800039a2  sub     rsp, 20h
0x1800039a6  xor     r14d, r14d
0x1800039a9  mov     rdi, r8
0x1800039ac  mov     [rsp+38h+arg_18], r14d
0x1800039b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800039b5  mov     rsi, rdx
0x1800039b8  mov     rbp, rcx
0x1800039bb  inc     rbx
0x1800039be  cmp     [r8+rbx*2], r14w
0x1800039c3  jnz     short loc_1800039BB
0x1800039c5  mov     r8, rbx; MaxCount
0x1800039c8  mov     rdx, rbp; String2
0x1800039cb  mov     rcx, rdi; String1
0x1800039ce  call    cs:__imp__wcsnicmp
0x1800039d4  test    eax, eax
0x1800039d6  jz      short loc_180003A4D
0x1800039d8  mov     r8, rbx; MaxCount
0x1800039db  mov     rdx, rsi; String2
0x1800039de  mov     rcx, rdi; String1
0x1800039e1  call    cs:__imp__wcsnicmp
0x1800039e7  test    eax, eax
0x1800039e9  jz      short loc_180003A4D
0x1800039eb  mov     ebx, 3
0x1800039f0  lea     r8, [rsp+38h+arg_18]
0x1800039f5  mov     edx, ebx
0x1800039f7  mov     rcx, rbp; pszSrc
0x1800039fa  call    DsRolepValidatePath
0x1800039ff  mov     ecx, eax
0x180003a01  test    eax, eax
0x180003a03  jnz     short loc_180003A63
0x180003a05  cmp     [rsp+38h+arg_18], ebx
0x180003a09  jnz     short loc_180003A5E
0x180003a0b  lea     r8, [rsp+38h+arg_18]
0x180003a10  mov     edx, ebx
0x180003a12  mov     rcx, rsi; pszSrc
0x180003a15  call    DsRolepValidatePath
0x180003a1a  mov     ecx, eax
0x180003a1c  test    eax, eax
0x180003a1e  jnz     short loc_180003A63
0x180003a20  cmp     [rsp+38h+arg_18], ebx
0x180003a24  jnz     short loc_180003A5E
0x180003a26  lea     r8, [rsp+38h+arg_18]
0x180003a2b  mov     rcx, rdi; pszSrc
0x180003a2e  lea     edx, [rbx+3]
0x180003a31  call    DsRolepValidatePath
0x180003a36  mov     ecx, eax
0x180003a38  test    eax, eax
0x180003a3a  jnz     short loc_180003A63
0x180003a3c  cmp     [rsp+38h+arg_18], 6
0x180003a41  mov     ecx, 0A1h
0x180003a46  cmovnz  eax, ecx
0x180003a49  mov     ecx, eax
0x180003a4b  jmp     short loc_180003A63
0x180003a4d  lea     rdx, aDatabasePathsS; "Database paths subset of sysvol\n"
0x180003a54  mov     ecx, 4
0x180003a59  call    DsRolepLogPrintRoutine
0x180003a5e  mov     ecx, 0A1h
0x180003a63  mov     rbx, [rsp+38h+arg_0]
0x180003a68  mov     eax, ecx
0x180003a6a  mov     rbp, [rsp+38h+arg_8]
0x180003a6f  add     rsp, 20h
0x180003a73  pop     r14
0x180003a75  pop     rdi
0x180003a76  pop     rsi
0x180003a77  retn
```
