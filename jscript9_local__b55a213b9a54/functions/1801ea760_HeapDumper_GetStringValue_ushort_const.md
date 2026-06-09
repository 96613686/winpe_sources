# HeapDumper::GetStringValue(ushort const *)

- ea: `0x1801ea760`
- end: `0x1801ea81d`
- name: `?GetStringValue@HeapDumper@@AEAAPEBGPEBG@Z`
- size: `189`
- prototype: `const unsigned __int16 *(HeapDumper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801ea028`

## callees

- `0x1801ea760`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathGetDriveNumberW` at `0x1801ea7b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathGetDriveNumberW` at `0x1801ea7b3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsUNCW` at `0x1801ea7c7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsUNCW` at `0x1801ea7c7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsLFNFileSpecW` at `0x1801ea7da`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsLFNFileSpecW` at `0x1801ea7da`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x1801ea7ed`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x1801ea7ed`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801ea800`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801ea800`

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
  if ( *((_BYTE *)this + 72)
    && (PathGetDriveNumberW(a2) != -1 || PathIsUNCW(a2) || PathIsLFNFileSpecW(a2) && !PathIsFileSpecW(a2)) )
  {
    return PathFindFileNameW(a2);
  }
  return a2;
}

```

## disassembly

```asm
0x1801ea760  mov     rax, rsp
0x1801ea763  mov     [rax+18h], rbx
0x1801ea767  mov     [rax+10h], rdx
0x1801ea76b  mov     [rax+8], rcx
0x1801ea76f  push    rdi
0x1801ea770  sub     rsp, 20h
0x1801ea774  xor     edi, edi
0x1801ea776  mov     rbx, rdx
0x1801ea779  test    rdx, rdx
0x1801ea77c  jnz     short loc_1801EA78A
0x1801ea77e  lea     rax, aNull_1; "(null)"
0x1801ea785  jmp     loc_1801EA811
0x1801ea78a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ea78e  inc     rax
0x1801ea791  cmp     [rbx+rax*2], di
0x1801ea795  jnz     short loc_1801EA78E
0x1801ea797  test    rax, rax
0x1801ea79a  jnz     short loc_1801EA7A5
0x1801ea79c  lea     rax, aEmptyString; "(empty string)"
0x1801ea7a3  jmp     short loc_1801EA811
0x1801ea7a5  mov     rax, [rsp+28h+arg_0]
0x1801ea7aa  cmp     [rax+48h], dil
0x1801ea7ae  jz      short loc_1801EA80E
0x1801ea7b0  mov     rcx, rbx; pszPath
0x1801ea7b3  call    cs:__imp_PathGetDriveNumberW
0x1801ea7ba  nop     dword ptr [rax+rax+00h]
0x1801ea7bf  cmp     eax, 0FFFFFFFFh
0x1801ea7c2  jnz     short loc_1801EA7FD
0x1801ea7c4  mov     rcx, rbx; pszPath
0x1801ea7c7  call    cs:__imp_PathIsUNCW
0x1801ea7ce  nop     dword ptr [rax+rax+00h]
0x1801ea7d3  test    eax, eax
0x1801ea7d5  jnz     short loc_1801EA7FD
0x1801ea7d7  mov     rcx, rbx; pszName
0x1801ea7da  call    cs:__imp_PathIsLFNFileSpecW
0x1801ea7e1  nop     dword ptr [rax+rax+00h]
0x1801ea7e6  test    eax, eax
0x1801ea7e8  jz      short loc_1801EA80E
0x1801ea7ea  mov     rcx, rbx; pszPath
0x1801ea7ed  call    cs:__imp_PathIsFileSpecW
0x1801ea7f4  nop     dword ptr [rax+rax+00h]
0x1801ea7f9  test    eax, eax
0x1801ea7fb  jnz     short loc_1801EA80E
0x1801ea7fd  mov     rcx, rbx; pszPath
0x1801ea800  call    cs:__imp_PathFindFileNameW
0x1801ea807  nop     dword ptr [rax+rax+00h]
0x1801ea80c  jmp     short loc_1801EA811
0x1801ea80e  mov     rax, rbx
0x1801ea811  mov     rbx, [rsp+28h+arg_10]
0x1801ea816  add     rsp, 20h
0x1801ea81a  pop     rdi
0x1801ea81b  retn
```
