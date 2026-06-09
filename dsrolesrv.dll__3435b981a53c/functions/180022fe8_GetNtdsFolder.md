# GetNtdsFolder

- ea: `0x180022fe8`
- end: `0x180023033`
- name: `GetNtdsFolder`
- size: `75`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002303c`
- `0x18002323c`

## callees

- `0x180022ce8`
- `0x180022fe8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180022ffa`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180022ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023004`

## pseudocode

```c
__int64 __fastcall GetNtdsFolder(STRSAFE_LPWSTR pszDest)
{
  unsigned int v2; // ebx
  int v3; // eax

  if ( GetWindowsDirectoryW(pszDest, 0x105u) )
  {
    v2 = 0;
    v3 = AddFilePathName(pszDest);
    if ( v3 < 0 )
      return (unsigned __int16)v3;
  }
  else
  {
    return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x180022fe8  mov     [rsp+arg_0], rbx
0x180022fed  push    rdi
0x180022fee  sub     rsp, 20h
0x180022ff2  mov     edx, 105h; uSize
0x180022ff7  mov     rdi, rcx
0x180022ffa  call    cs:__imp_GetWindowsDirectoryW
0x180023000  test    eax, eax
0x180023002  jnz     short loc_18002300E
0x180023004  call    cs:__imp_GetLastError
0x18002300a  mov     ebx, eax
0x18002300c  jmp     short loc_180023026
0x18002300e  lea     r8, aNtds; "\\NTDS"
0x180023015  mov     rcx, rdi; pszDest
0x180023018  xor     ebx, ebx
0x18002301a  call    AddFilePathName
0x18002301f  test    eax, eax
0x180023021  jns     short loc_180023026
0x180023023  movzx   ebx, ax
0x180023026  mov     eax, ebx
0x180023028  mov     rbx, [rsp+28h+arg_0]
0x18002302d  add     rsp, 20h
0x180023031  pop     rdi
0x180023032  retn
```
