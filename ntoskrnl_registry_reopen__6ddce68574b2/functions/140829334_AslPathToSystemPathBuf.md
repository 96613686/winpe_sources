# AslPathToSystemPathBuf

- ea: `0x140829334`
- end: `0x1408293d4`
- name: `AslPathToSystemPathBuf`
- size: `160`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14073b188`
- `0x1408266c0`
- `0x140829278`
- `0x140b04ab4`

## callees

- `0x140438468`
- `0x1404b8748`
- `0x1406f7380`
- `0x140829334`
- `0x1408c2f88`

## string_xrefs

- `0x14082937a`: `AslPathToSystemPathBuf`
- `0x1408293b2`: `AslPathToSystemPathBuf`
- `0x140829369`: `Failed to copy string [%x]`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  NTSTATUS v10; // [rsp+20h] [rbp-38h]
  NTSTATUS v11; // [rsp+20h] [rbp-38h]

  memset_0(pszDest, 0, 2 * cchDest);
  v6 = RtlStringCchCopyW(pszDest, cchDest, L"\\SystemRoot");
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = RtlStringCchCatW(pszDest, cchDest, pszSrc);
    v7 = v8;
    if ( v8 < 0 )
    {
      v11 = v8;
      AslLogCallPrintf(1, (unsigned int)"AslPathToSystemPathBuf", 1488, (unsigned int)"Failed to cat string [%x]", v11);
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    v10 = v6;
    AslLogCallPrintf(1, (unsigned int)"AslPathToSystemPathBuf", 1471, (unsigned int)"Failed to copy string [%x]", v10);
  }
  return v7;
}

```

## disassembly

```asm
0x140829334  push    rbx
0x140829336  push    rbp
0x140829337  push    rsi
0x140829338  push    rdi
0x140829339  sub     rsp, 38h
0x14082933d  mov     rbp, r8
0x140829340  mov     rdi, rdx
0x140829343  lea     r8, [rdx+rdx]; Size
0x140829347  mov     rsi, rcx
0x14082934a  xor     edx, edx; Val
0x14082934c  call    memset_0
0x140829351  lea     r8, aSystemroot_4; "\\SystemRoot"
0x140829358  mov     rdx, rdi; cchDest
0x14082935b  mov     rcx, rsi; pszDest
0x14082935e  call    RtlStringCchCopyW
0x140829363  mov     ebx, eax
0x140829365  test    eax, eax
0x140829367  jns     short loc_14082938D
0x140829369  lea     r9, aFailedToCopySt; "Failed to copy string [%x]"
0x140829370  mov     [rsp+58h+var_38], eax
0x140829374  mov     r8d, 5BFh
0x14082937a  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x140829381  mov     ecx, 1
0x140829386  call    AslLogCallPrintf
0x14082938b  jmp     short loc_1408293C8
0x14082938d  mov     r8, rbp; pszSrc
0x140829390  mov     rdx, rdi; cchDest
0x140829393  mov     rcx, rsi; pszDest
0x140829396  call    RtlStringCchCatW
0x14082939b  mov     ebx, eax
0x14082939d  test    eax, eax
0x14082939f  jns     short loc_1408293C8
0x1408293a1  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x1408293a8  mov     [rsp+58h+var_38], eax
0x1408293ac  mov     r8d, 5D0h
0x1408293b2  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x1408293b9  mov     ecx, 1
0x1408293be  call    AslLogCallPrintf
0x1408293c3  mov     ebx, 0C000000Dh
0x1408293c8  mov     eax, ebx
0x1408293ca  add     rsp, 38h
0x1408293ce  pop     rdi
0x1408293cf  pop     rsi
0x1408293d0  pop     rbp
0x1408293d1  pop     rbx
0x1408293d2  retn
```
