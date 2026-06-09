# DiagCabOpenFile(char *,int,int,int *,void *)

- ea: `0x18013a390`
- end: `0x18013a485`
- name: `?DiagCabOpenFile@@YA_JPEADHHPEAHPEAX@Z`
- size: `245`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode, int *err, void *pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180139c10`

## callees

- `0x18013a390`

## import_xrefs

- `msvcrt!_errno` at `0x18013a455`
- `msvcrt!_errno` at `0x18013a455`
- `msvcrt!_wopen` at `0x18013a448`
- `msvcrt!_wopen` at `0x18013a448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a435`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a3fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a3fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a3ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a45f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a3ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a45f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a46d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a46d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a3cd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a42b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a3cd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a42b`

## pseudocode

```c
INT_PTR __fastcall DiagCabOpenFile(const CHAR *pszFile, int oflag, unsigned int pmode, int *err)
{
  int v4; // esi
  int v9; // eax
  int cchWideChar; // ebp
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v14; // rbx
  HANDLE v15; // rax

  v4 = -1;
  v9 = MultiByteToWideChar(0xFDE9u, 8u, pszFile, -1, 0, 0);
  cchWideChar = v9;
  if ( v9 )
  {
    v11 = 2LL * (v9 + 1);
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, v11);
    v14 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 8u, pszFile, -1, lpWideCharStr, cchWideChar) )
      {
        v4 = _wopen(v14, oflag, pmode);
        if ( v4 == -1 )
          *err = *_errno();
      }
      else
      {
        *err = GetLastError();
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    else
    {
      *err = 14;
    }
  }
  else
  {
    *err = GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x18013a390  push    rbx
0x18013a392  push    rbp
0x18013a393  push    rsi
0x18013a394  push    rdi
0x18013a395  push    r12
0x18013a397  push    r14
0x18013a399  push    r15
0x18013a39b  sub     rsp, 30h
0x18013a39f  or      esi, 0FFFFFFFFh
0x18013a3a2  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x18013a3aa  mov     r14d, r8d
0x18013a3ad  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x18013a3b6  mov     rdi, r9
0x18013a3b9  mov     r15d, edx
0x18013a3bc  mov     r12, rcx
0x18013a3bf  mov     r8, rcx; lpMultiByteStr
0x18013a3c2  lea     edx, [rsi+9]; dwFlags
0x18013a3c5  or      r9d, esi; cbMultiByte
0x18013a3c8  mov     ecx, 0FDE9h; CodePage
0x18013a3cd  call    cs:__imp_MultiByteToWideChar
0x18013a3d3  mov     ebp, eax
0x18013a3d5  test    eax, eax
0x18013a3d7  jnz     short loc_18013A3E6
0x18013a3d9  call    cs:__imp_GetLastError
0x18013a3df  mov     [rdi], eax
0x18013a3e1  jmp     loc_18013A473
0x18013a3e6  inc     eax
0x18013a3e8  movsxd  rbx, eax
0x18013a3eb  add     rbx, rbx
0x18013a3ee  call    cs:__imp_GetProcessHeap
0x18013a3f4  mov     r8, rbx; dwBytes
0x18013a3f7  xor     edx, edx; dwFlags
0x18013a3f9  mov     rcx, rax; hHeap
0x18013a3fc  call    cs:__imp_HeapAlloc
0x18013a402  mov     rbx, rax
0x18013a405  test    rax, rax
0x18013a408  jnz     short loc_18013A412
0x18013a40a  mov     dword ptr [rdi], 0Eh
0x18013a410  jmp     short loc_18013A473
0x18013a412  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18013a416  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x18013a41a  mov     r8, r12; lpMultiByteStr
0x18013a41d  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x18013a422  mov     ecx, 0FDE9h; CodePage
0x18013a427  lea     edx, [r9+9]; dwFlags
0x18013a42b  call    cs:__imp_MultiByteToWideChar
0x18013a431  test    eax, eax
0x18013a433  jnz     short loc_18013A43F
0x18013a435  call    cs:__imp_GetLastError
0x18013a43b  mov     [rdi], eax
0x18013a43d  jmp     short loc_18013A45F
0x18013a43f  mov     r8d, r14d
0x18013a442  mov     edx, r15d; OpenFlag
0x18013a445  mov     rcx, rbx; FileName
0x18013a448  call    cs:__imp__wopen
0x18013a44e  mov     esi, eax
0x18013a450  cmp     eax, 0FFFFFFFFh
0x18013a453  jnz     short loc_18013A45F
0x18013a455  call    cs:__imp__errno
0x18013a45b  mov     ecx, [rax]
0x18013a45d  mov     [rdi], ecx
0x18013a45f  call    cs:__imp_GetProcessHeap
0x18013a465  mov     r8, rbx; lpMem
0x18013a468  xor     edx, edx; dwFlags
0x18013a46a  mov     rcx, rax; hHeap
0x18013a46d  call    cs:__imp_HeapFree
0x18013a473  movsxd  rax, esi
0x18013a476  add     rsp, 30h
0x18013a47a  pop     r15
0x18013a47c  pop     r14
0x18013a47e  pop     r12
0x18013a480  pop     rdi
0x18013a481  pop     rsi
0x18013a482  pop     rbp
0x18013a483  pop     rbx
0x18013a484  retn
```
