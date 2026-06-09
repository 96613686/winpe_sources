# AslPathToSystemPathBuf

- ea: `0x1408273c4`
- end: `0x140827464`
- name: `AslPathToSystemPathBuf`
- size: `160`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1407369c8`
- `0x140824750`
- `0x140827308`
- `0x140afe014`

## callees

- `0x1402dc448`
- `0x1404a9868`
- `0x1406f4880`
- `0x1408273c4`
- `0x14097d158`

## string_xrefs

- `0x14082740a`: `AslPathToSystemPathBuf`
- `0x140827442`: `AslPathToSystemPathBuf`
- `0x1408273f9`: `Failed to copy string [%x]`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTATUS v6; // ebx

  memset_0(pszDest, 0, 2 * cchDest);
  v6 = RtlStringCchCopyW(pszDest, cchDest, L"\\SystemRoot");
  if ( v6 >= 0 )
  {
    v6 = RtlStringCchCatW(pszDest, cchDest, pszSrc);
    if ( v6 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"AslPathToSystemPathBuf", 1488, (unsigned int)"Failed to cat string [%x]");
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"AslPathToSystemPathBuf", 1471, (unsigned int)"Failed to copy string [%x]");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1408273c4  push    rbx
0x1408273c6  push    rbp
0x1408273c7  push    rsi
0x1408273c8  push    rdi
0x1408273c9  sub     rsp, 38h
0x1408273cd  mov     rbp, r8
0x1408273d0  mov     rdi, rdx
0x1408273d3  lea     r8, [rdx+rdx]; Size
0x1408273d7  mov     rsi, rcx
0x1408273da  xor     edx, edx; Val
0x1408273dc  call    memset_0
0x1408273e1  lea     r8, aSystemroot_4; "\\SystemRoot"
0x1408273e8  mov     rdx, rdi; cchDest
0x1408273eb  mov     rcx, rsi; pszDest
0x1408273ee  call    RtlStringCchCopyW
0x1408273f3  mov     ebx, eax
0x1408273f5  test    eax, eax
0x1408273f7  jns     short loc_14082741D
0x1408273f9  lea     r9, aFailedToCopySt; "Failed to copy string [%x]"
0x140827400  mov     [rsp+58h+var_38], eax
0x140827404  mov     r8d, 5BFh
0x14082740a  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x140827411  mov     ecx, 1
0x140827416  call    AslLogCallPrintf
0x14082741b  jmp     short loc_140827458
0x14082741d  mov     r8, rbp; pszSrc
0x140827420  mov     rdx, rdi; cchDest
0x140827423  mov     rcx, rsi; pszDest
0x140827426  call    RtlStringCchCatW
0x14082742b  mov     ebx, eax
0x14082742d  test    eax, eax
0x14082742f  jns     short loc_140827458
0x140827431  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x140827438  mov     [rsp+58h+var_38], eax
0x14082743c  mov     r8d, 5D0h
0x140827442  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x140827449  mov     ecx, 1
0x14082744e  call    AslLogCallPrintf
0x140827453  mov     ebx, 0C000000Dh
0x140827458  mov     eax, ebx
0x14082745a  add     rsp, 38h
0x14082745e  pop     rdi
0x14082745f  pop     rsi
0x140827460  pop     rbp
0x140827461  pop     rbx
0x140827462  retn
```
