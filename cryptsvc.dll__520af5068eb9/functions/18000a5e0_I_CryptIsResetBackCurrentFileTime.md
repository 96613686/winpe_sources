# I_CryptIsResetBackCurrentFileTime

- ea: `0x18000a5e0`
- end: `0x18000a611`
- name: `I_CryptIsResetBackCurrentFileTime`
- size: `49`
- prototype: `_BOOL8 __fastcall(_QWORD *, unsigned int, const FILETIME *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a500`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a5fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a5fd`

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
0x18000a5e0  sub     rsp, 28h
0x18000a5e4  mov     eax, edx
0x18000a5e6  imul    rdx, rax, 989680h
0x18000a5ed  add     rdx, [rcx]
0x18000a5f0  mov     rcx, r8; lpFileTime1
0x18000a5f3  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], rdx
0x18000a5f8  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x18000a5fd  call    cs:__imp_CompareFileTime
0x18000a603  xor     ecx, ecx
0x18000a605  test    eax, eax
0x18000a607  setnle  cl
0x18000a60a  mov     eax, ecx
0x18000a60c  add     rsp, 28h
0x18000a610  retn
```
