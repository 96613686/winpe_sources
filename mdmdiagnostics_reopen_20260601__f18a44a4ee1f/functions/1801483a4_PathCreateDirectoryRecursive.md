# PathCreateDirectoryRecursive

- ea: `0x1801483a4`
- end: `0x1801484d1`
- name: `PathCreateDirectoryRecursive`
- size: `301`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180148334`
- `0x1801483a4`

## callees

- `0x180147ce0`
- `0x1801483a4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801483e9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18014848d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801483e9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18014848d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801484a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801484a1`

## pseudocode

```c
signed int __fastcall PathCreateDirectoryRecursive(LPCWSTR lpPathName, int a2, unsigned int a3)
{
  signed int result; // eax
  int v6; // r9d
  __int64 v7; // rdi
  int v8; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  if ( !lpPathName || !a2 || a3 >= 0x80 )
    return -2147024809;
  if ( CreateDirectoryW(lpPathName, 0) )
    return 0;
  result = GetLastError();
  if ( result == 183 )
    return 0;
  if ( result != 3 )
  {
LABEL_8:
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringFindChar((_DWORD)lpPathName, 92, a2, v6, (__int64)&v9, (__int64)&v8);
  if ( result < 0 )
    return result;
  if ( !v8 )
    return -2147024893;
  v7 = v9;
  lpPathName[v9] = 0;
  result = PathCreateDirectoryRecursive(lpPathName);
  if ( result >= 0 )
  {
    lpPathName[v7] = 92;
    if ( !CreateDirectoryW(lpPathName, 0) )
    {
      result = GetLastError();
      if ( result != 183 )
        goto LABEL_8;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1801483a4  mov     [rsp+arg_8], rbx
0x1801483a9  push    rsi
0x1801483aa  push    rdi
0x1801483ab  push    r15
0x1801483ad  sub     rsp, 30h
0x1801483b1  mov     [rsp+48h+arg_18], 0
0x1801483b9  mov     esi, r8d
0x1801483bc  mov     [rsp+48h+arg_0], 0
0x1801483c4  mov     edi, edx
0x1801483c6  mov     rbx, rcx
0x1801483c9  test    rcx, rcx
0x1801483cc  jz      loc_1801484BD
0x1801483d2  test    edx, edx
0x1801483d4  jz      loc_1801484BD
0x1801483da  cmp     r8d, 80h
0x1801483e1  jnb     loc_1801484BD
0x1801483e7  xor     edx, edx; lpSecurityAttributes
0x1801483e9  call    cs:__imp_CreateDirectoryW
0x1801483f0  nop     dword ptr [rax+rax+00h]
0x1801483f5  test    eax, eax
0x1801483f7  jz      short loc_180148400
0x1801483f9  xor     eax, eax
0x1801483fb  jmp     loc_1801484C2
0x180148400  call    cs:__imp_GetLastError
0x180148407  nop     dword ptr [rax+rax+00h]
0x18014840c  cmp     eax, 0B7h
0x180148411  jz      short loc_1801483F9
0x180148413  cmp     eax, 3
0x180148416  jz      short loc_18014842D
0x180148418  test    eax, eax
0x18014841a  jle     loc_1801484C2
0x180148420  movzx   eax, ax
0x180148423  or      eax, 80070000h
0x180148428  jmp     loc_1801484C2
0x18014842d  lea     rax, [rsp+48h+arg_0]
0x180148432  mov     r15d, 5Ch ; '\'
0x180148438  mov     [rsp+48h+var_20], rax
0x18014843d  mov     edx, r15d
0x180148440  lea     rax, [rsp+48h+arg_18]
0x180148445  mov     r8d, edi
0x180148448  mov     rcx, rbx
0x18014844b  mov     [rsp+48h+var_28], rax
0x180148450  call    StringFindChar
0x180148455  test    eax, eax
0x180148457  js      short loc_1801484C2
0x180148459  cmp     [rsp+48h+arg_0], 0
0x18014845e  jnz     short loc_180148467
0x180148460  mov     eax, 80070003h
0x180148465  jmp     short loc_1801484C2
0x180148467  mov     edx, [rsp+48h+arg_18]
0x18014846b  lea     r8d, [rsi+1]
0x18014846f  xor     eax, eax
0x180148471  mov     rcx, rbx; lpPathName
0x180148474  mov     edi, edx
0x180148476  mov     [rbx+rdx*2], ax
0x18014847a  call    PathCreateDirectoryRecursive
0x18014847f  test    eax, eax
0x180148481  js      short loc_1801484C2
0x180148483  xor     edx, edx; lpSecurityAttributes
0x180148485  mov     [rbx+rdi*2], r15w
0x18014848a  mov     rcx, rbx; lpPathName
0x18014848d  call    cs:__imp_CreateDirectoryW
0x180148494  nop     dword ptr [rax+rax+00h]
0x180148499  test    eax, eax
0x18014849b  jnz     loc_1801483F9
0x1801484a1  call    cs:__imp_GetLastError
0x1801484a8  nop     dword ptr [rax+rax+00h]
0x1801484ad  cmp     eax, 0B7h
0x1801484b2  jz      loc_1801483F9
0x1801484b8  jmp     loc_180148418
0x1801484bd  mov     eax, 80070057h
0x1801484c2  mov     rbx, [rsp+48h+arg_8]
0x1801484c7  add     rsp, 30h
0x1801484cb  pop     r15
0x1801484cd  pop     rdi
0x1801484ce  pop     rsi
0x1801484cf  retn
```
