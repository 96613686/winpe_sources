# HeapDumper::GetStringValue(ushort const *)

- ea: `0x180436f78`
- end: `0x180437035`
- name: `?GetStringValue@HeapDumper@@AEAAPEBGPEBG@Z`
- size: `189`
- prototype: `const unsigned __int16 *(HeapDumper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180436840`

## callees

- `0x180436f78`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsLFNFileSpecW` at `0x180436ff2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsLFNFileSpecW` at `0x180436ff2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180436fdf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180436fdf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180437005`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180437005`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180437018`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180437018`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180436fcb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180436fcb`

## pseudocode

```c
const unsigned __int16 *__fastcall HeapDumper::GetStringValue(HeapDumper *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax

  if ( !a2 )
    return L"(null)";
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( !v4 )
    return L"(empty string)";
  if ( *((_BYTE *)this + 84)
    && (PathGetDriveNumberW(a2) != -1 || PathIsUNCW(a2) || PathIsLFNFileSpecW(a2) && !PathIsFileSpecW(a2)) )
  {
    return PathFindFileNameW(a2);
  }
  return a2;
}

```

## disassembly

```asm
0x180436f78  mov     rax, rsp
0x180436f7b  mov     [rax+18h], rbx
0x180436f7f  mov     [rax+10h], rdx
0x180436f83  mov     [rax+8], rcx
0x180436f87  push    rdi
0x180436f88  sub     rsp, 20h
0x180436f8c  xor     edi, edi
0x180436f8e  mov     rbx, rdx
0x180436f91  test    rdx, rdx
0x180436f94  jnz     short loc_180436FA2
0x180436f96  lea     rax, aNull_2; "(null)"
0x180436f9d  jmp     loc_180437029
0x180436fa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180436fa6  inc     rax
0x180436fa9  cmp     [rbx+rax*2], di
0x180436fad  jnz     short loc_180436FA6
0x180436faf  test    rax, rax
0x180436fb2  jnz     short loc_180436FBD
0x180436fb4  lea     rax, aEmptyString; "(empty string)"
0x180436fbb  jmp     short loc_180437029
0x180436fbd  mov     rax, [rsp+28h+arg_0]
0x180436fc2  cmp     [rax+54h], dil
0x180436fc6  jz      short loc_180437026
0x180436fc8  mov     rcx, rbx; pszPath
0x180436fcb  call    cs:__imp_PathGetDriveNumberW
0x180436fd2  nop     dword ptr [rax+rax+00h]
0x180436fd7  cmp     eax, 0FFFFFFFFh
0x180436fda  jnz     short loc_180437015
0x180436fdc  mov     rcx, rbx; pszPath
0x180436fdf  call    cs:__imp_PathIsUNCW
0x180436fe6  nop     dword ptr [rax+rax+00h]
0x180436feb  test    eax, eax
0x180436fed  jnz     short loc_180437015
0x180436fef  mov     rcx, rbx; pszName
0x180436ff2  call    cs:__imp_PathIsLFNFileSpecW
0x180436ff9  nop     dword ptr [rax+rax+00h]
0x180436ffe  test    eax, eax
0x180437000  jz      short loc_180437026
0x180437002  mov     rcx, rbx; pszPath
0x180437005  call    cs:__imp_PathIsFileSpecW
0x18043700c  nop     dword ptr [rax+rax+00h]
0x180437011  test    eax, eax
0x180437013  jnz     short loc_180437026
0x180437015  mov     rcx, rbx; pszPath
0x180437018  call    cs:__imp_PathFindFileNameW
0x18043701f  nop     dword ptr [rax+rax+00h]
0x180437024  jmp     short loc_180437029
0x180437026  mov     rax, rbx
0x180437029  mov     rbx, [rsp+28h+arg_10]
0x18043702e  add     rsp, 20h
0x180437032  pop     rdi
0x180437033  retn
```
