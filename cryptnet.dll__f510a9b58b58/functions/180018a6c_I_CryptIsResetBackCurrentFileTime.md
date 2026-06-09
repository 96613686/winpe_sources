# I_CryptIsResetBackCurrentFileTime

- ea: `0x180018a6c`
- end: `0x180018a9d`
- name: `I_CryptIsResetBackCurrentFileTime`
- size: `49`
- prototype: `_BOOL8 __fastcall(_QWORD *, unsigned int, const FILETIME *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008f80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018a89`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018a89`

## pseudocode

```c
_BOOL8 __fastcall I_CryptIsResetBackCurrentFileTime(_QWORD *a1, unsigned int a2, const FILETIME *a3)
{
  FILETIME FileTime2; // [rsp+30h] [rbp+8h] BYREF

  FileTime2 = (FILETIME)(*a1 + 10000000LL * a2);
  return CompareFileTime(a3, &FileTime2) > 0;
}

```

## disassembly

```asm
0x180018a6c  sub     rsp, 28h
0x180018a70  mov     eax, edx
0x180018a72  imul    rdx, rax, 989680h
0x180018a79  add     rdx, [rcx]
0x180018a7c  mov     rcx, r8; lpFileTime1
0x180018a7f  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], rdx
0x180018a84  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x180018a89  call    cs:__imp_CompareFileTime
0x180018a8f  xor     ecx, ecx
0x180018a91  test    eax, eax
0x180018a93  setnle  cl
0x180018a96  mov     eax, ecx
0x180018a98  add     rsp, 28h
0x180018a9c  retn
```
