# DiagCabDeleteFile(char *,int *,void *)

- ea: `0x180139b40`
- end: `0x180139bde`
- name: `?DiagCabDeleteFile@@YAHPEADPEAHPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(const CHAR *pszFile, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180139b40`

## import_xrefs

- `msvcrt!_errno` at `0x180139bb5`
- `msvcrt!_errno` at `0x180139bb5`
- `msvcrt!_wremove` at `0x180139ba8`
- `msvcrt!_wremove` at `0x180139ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139b96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180139b63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180139b63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180139b52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180139bbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180139b52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180139bbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180139bcd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180139bcd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180139b8c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180139b8c`

## pseudocode

```c
__int64 __fastcall DiagCabDeleteFile(const CHAR *pszFile, int *err, void *pv)
{
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v8; // rdi
  unsigned int v9; // eax
  HANDLE v10; // rax

  v5 = -1;
  ProcessHeap = GetProcessHeap();
  lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v8 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    v9 = MultiByteToWideChar(0xFDE9u, 8u, pszFile, -1, lpWideCharStr, 260);
    if ( v9 )
    {
      if ( v9 < 0x104 )
      {
        v5 = _wremove(v8);
        if ( v5 == -1 )
          *err = *_errno();
      }
    }
    else
    {
      GetLastError();
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x180139b40  push    rbx
0x180139b42  push    rbp
0x180139b43  push    rsi
0x180139b44  push    rdi
0x180139b45  sub     rsp, 38h
0x180139b49  mov     rsi, rdx
0x180139b4c  mov     rbp, rcx
0x180139b4f  or      ebx, 0FFFFFFFFh
0x180139b52  call    cs:__imp_GetProcessHeap
0x180139b58  xor     edx, edx; dwFlags
0x180139b5a  mov     r8d, 208h; dwBytes
0x180139b60  mov     rcx, rax; hHeap
0x180139b63  call    cs:__imp_HeapAlloc
0x180139b69  mov     rdi, rax
0x180139b6c  test    rax, rax
0x180139b6f  jz      short loc_180139BD3
0x180139b71  mov     [rsp+58h+cchWideChar], 104h; cchWideChar
0x180139b79  lea     edx, [rbx+9]; dwFlags
0x180139b7c  or      r9d, ebx; cbMultiByte
0x180139b7f  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x180139b84  mov     r8, rbp; lpMultiByteStr
0x180139b87  mov     ecx, 0FDE9h; CodePage
0x180139b8c  call    cs:__imp_MultiByteToWideChar
0x180139b92  test    eax, eax
0x180139b94  jnz     short loc_180139B9E
0x180139b96  call    cs:__imp_GetLastError
0x180139b9c  jmp     short loc_180139BBF
0x180139b9e  cmp     eax, 104h
0x180139ba3  jnb     short loc_180139BBF
0x180139ba5  mov     rcx, rdi; FileName
0x180139ba8  call    cs:__imp__wremove
0x180139bae  mov     ebx, eax
0x180139bb0  cmp     eax, 0FFFFFFFFh
0x180139bb3  jnz     short loc_180139BBF
0x180139bb5  call    cs:__imp__errno
0x180139bbb  mov     ecx, [rax]
0x180139bbd  mov     [rsi], ecx
0x180139bbf  call    cs:__imp_GetProcessHeap
0x180139bc5  mov     r8, rdi; lpMem
0x180139bc8  xor     edx, edx; dwFlags
0x180139bca  mov     rcx, rax; hHeap
0x180139bcd  call    cs:__imp_HeapFree
0x180139bd3  mov     eax, ebx
0x180139bd5  add     rsp, 38h
0x180139bd9  pop     rdi
0x180139bda  pop     rsi
0x180139bdb  pop     rbp
0x180139bdc  pop     rbx
0x180139bdd  retn
```
