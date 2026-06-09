# DiagCreatePath(ushort *)

- ea: `0x18013a9a8`
- end: `0x18013aa2b`
- name: `?DiagCreatePath@@YAJPEAG@Z`
- size: `131`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180139cd0`

## callees

- `0x18013a9a8`

## import_xrefs

- `msvcrt!wcschr` at `0x18013a9c8`
- `msvcrt!wcschr` at `0x18013a9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a9f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a9f4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18013a9e0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18013a9e0`

## pseudocode

```c
__int64 __fastcall DiagCreatePath(LPCWSTR lpPathName)
{
  WCHAR *v2; // rbx
  wchar_t *v3; // rax
  unsigned int v4; // ecx
  signed int LastError; // eax

  v2 = (WCHAR *)(lpPathName + 3);
  while ( 1 )
  {
    v3 = wcschr(v2 + 1, 0x5Cu);
    v4 = 0;
    v2 = v3;
    if ( !v3 )
      break;
    *v3 = 0;
    if ( CreateDirectoryW(lpPathName, 0) || !GetLastError() )
    {
      *v2 = 92;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      *v2 = 92;
      if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147024713 )
        return v4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18013a9a8  push    rbx
0x18013a9aa  push    rbp
0x18013a9ab  push    rsi
0x18013a9ac  push    rdi
0x18013a9ad  sub     rsp, 28h
0x18013a9b1  mov     rdi, rcx
0x18013a9b4  lea     rbx, [rcx+6]
0x18013a9b8  mov     esi, 5Ch ; '\'
0x18013a9bd  mov     ebp, 80000000h
0x18013a9c2  mov     edx, esi; Ch
0x18013a9c4  lea     rcx, [rbx+2]; Str
0x18013a9c8  call    cs:__imp_wcschr
0x18013a9ce  xor     ecx, ecx
0x18013a9d0  mov     rbx, rax
0x18013a9d3  test    rax, rax
0x18013a9d6  jz      short loc_18013AA1B
0x18013a9d8  mov     [rax], cx
0x18013a9db  xor     edx, edx; lpSecurityAttributes
0x18013a9dd  mov     rcx, rdi; lpPathName
0x18013a9e0  call    cs:__imp_CreateDirectoryW
0x18013a9e6  test    eax, eax
0x18013a9e8  jnz     short loc_18013AA26
0x18013a9ea  call    cs:__imp_GetLastError
0x18013a9f0  test    eax, eax
0x18013a9f2  jz      short loc_18013AA26
0x18013a9f4  call    cs:__imp_GetLastError
0x18013a9fa  mov     ecx, eax
0x18013a9fc  test    eax, eax
0x18013a9fe  jle     short loc_18013AA09
0x18013aa00  movzx   ecx, ax
0x18013aa03  or      ecx, 80070000h
0x18013aa09  lea     eax, [rcx+rbp]
0x18013aa0c  mov     [rbx], si
0x18013aa0f  test    ebp, eax
0x18013aa11  jnz     short loc_18013A9C2
0x18013aa13  cmp     ecx, 800700B7h
0x18013aa19  jz      short loc_18013A9C2
0x18013aa1b  mov     eax, ecx
0x18013aa1d  add     rsp, 28h
0x18013aa21  pop     rdi
0x18013aa22  pop     rsi
0x18013aa23  pop     rbp
0x18013aa24  pop     rbx
0x18013aa25  retn
0x18013aa26  mov     [rbx], si
0x18013aa29  jmp     short loc_18013A9C2
```
