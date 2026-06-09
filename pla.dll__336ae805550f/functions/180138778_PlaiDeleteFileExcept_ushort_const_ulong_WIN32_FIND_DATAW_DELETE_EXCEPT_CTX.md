# PlaiDeleteFileExcept(ushort const *,ulong,_WIN32_FIND_DATAW *,_DELETE_EXCEPT_CTX *)

- ea: `0x180138778`
- end: `0x18013880a`
- name: `?PlaiDeleteFileExcept@@YAJPEBGKPEAU_WIN32_FIND_DATAW@@PEAU_DELETE_EXCEPT_CTX@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, struct _WIN32_FIND_DATAW *, struct _DELETE_EXCEPT_CTX *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18006f9e8`

## callees

- `0x18002b3a0`
- `0x180138778`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180138798`
- `msvcrt!_wcsicmp` at `0x1801387ae`
- `msvcrt!_wcsicmp` at `0x180138798`
- `msvcrt!_wcsicmp` at `0x1801387ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801387ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801387ca`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801387bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801387bb`

## pseudocode

```c
__int64 __fastcall PlaiDeleteFileExcept(
        LPCWSTR lpFileName,
        __int64 a2,
        struct _WIN32_FIND_DATAW *a3,
        const wchar_t **a4)
{
  const wchar_t *v7; // rdx
  int v8; // r8d
  DWORD LastError; // eax

  if ( *a4 && !_wcsicmp(lpFileName, *a4) )
    return 0;
  v7 = a4[1];
  if ( v7 )
  {
    if ( !_wcsicmp(lpFileName, v7) )
      return 0;
  }
  if ( !DeleteFileW(lpFileName) )
  {
    LastError = GetLastError();
    v8 = PlaiHResultFromWin32(LastError);
    if ( v8 >= 0 )
      goto LABEL_8;
    return 0;
  }
  v8 = 0;
LABEL_8:
  *(_QWORD *)a4[2] -= a3->nFileSizeLow | ((unsigned __int64)a3->nFileSizeHigh << 32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180138778  mov     [rsp+arg_0], rbx
0x18013877d  mov     [rsp+arg_8], rsi
0x180138782  push    rdi
0x180138783  sub     rsp, 20h
0x180138787  mov     rdx, [r9]; String2
0x18013878a  mov     rdi, r9
0x18013878d  mov     rsi, r8
0x180138790  mov     rbx, rcx
0x180138793  test    rdx, rdx
0x180138796  jz      short loc_1801387A2
0x180138798  call    cs:__imp__wcsicmp
0x18013879e  test    eax, eax
0x1801387a0  jz      short loc_1801387F4
0x1801387a2  mov     rdx, [rdi+8]; String2
0x1801387a6  test    rdx, rdx
0x1801387a9  jz      short loc_1801387B8
0x1801387ab  mov     rcx, rbx; String1
0x1801387ae  call    cs:__imp__wcsicmp
0x1801387b4  test    eax, eax
0x1801387b6  jz      short loc_1801387F4
0x1801387b8  mov     rcx, rbx; lpFileName
0x1801387bb  call    cs:__imp_DeleteFileW
0x1801387c1  test    eax, eax
0x1801387c3  jz      short loc_1801387CA
0x1801387c5  xor     r8d, r8d
0x1801387c8  jmp     short loc_1801387DE
0x1801387ca  call    cs:__imp_GetLastError
0x1801387d0  mov     ecx, eax; unsigned int
0x1801387d2  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1801387d7  mov     r8d, eax
0x1801387da  test    eax, eax
0x1801387dc  js      short loc_1801387F4
0x1801387de  mov     ecx, [rsi+1Ch]
0x1801387e1  mov     eax, [rsi+20h]
0x1801387e4  mov     rdx, [rdi+10h]
0x1801387e8  shl     rcx, 20h
0x1801387ec  or      rcx, rax
0x1801387ef  sub     [rdx], rcx
0x1801387f2  jmp     short loc_1801387F7
0x1801387f4  xor     r8d, r8d
0x1801387f7  mov     rbx, [rsp+28h+arg_0]
0x1801387fc  mov     eax, r8d
0x1801387ff  mov     rsi, [rsp+28h+arg_8]
0x180138804  add     rsp, 20h
0x180138808  pop     rdi
0x180138809  retn
```
