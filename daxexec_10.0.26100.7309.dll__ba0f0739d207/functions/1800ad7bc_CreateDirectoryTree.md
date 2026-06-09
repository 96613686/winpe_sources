# CreateDirectoryTree

- ea: `0x1800ad7bc`
- end: `0x1800ad932`
- name: `CreateDirectoryTree`
- size: `374`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180030600`
- `0x18003153c`
- `0x1800778a0`
- `0x180078688`

## callees

- `0x1800ad7bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad88d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad88d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad8ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad8ce`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ad8f2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ad8f2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ad879`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ad879`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800ad7e5`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800ad7e5`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800ad810`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800ad810`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800ad82e`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800ad82e`

## pseudocode

```c
__int64 __fastcall CreateDirectoryTree(const WCHAR *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  PCWSTR v5; // rax
  int v6; // edi
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  PCWSTR ppszRootEnd; // [rsp+60h] [rbp+40h] BYREF
  PWSTR ppszPathOut; // [rsp+68h] [rbp+48h] BYREF

  ppszRootEnd = 0;
  ppszPathOut = 0;
  v3 = PathAllocCanonicalize(a1, 1u, &ppszPathOut);
  if ( v3 >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( ppszPathOut[v4] );
    v3 = PathCchRemoveBackslash(ppszPathOut, v4 + 1);
    if ( v3 >= 0 )
    {
      v3 = PathCchSkipRoot(ppszPathOut, &ppszRootEnd);
      if ( v3 >= 0 )
      {
        v5 = ppszRootEnd;
        if ( *ppszRootEnd )
        {
          v6 = 0;
          while ( 1 )
          {
            if ( !*v5 )
            {
              v6 = 1;
              goto LABEL_12;
            }
            if ( *v5 == 92 )
              break;
LABEL_29:
            ppszRootEnd = ++v5;
            if ( v6 )
              goto LABEL_19;
          }
          *v5 = 0;
LABEL_12:
          if ( !CreateDirectoryW(ppszPathOut, a2) )
          {
            LastError = GetLastError();
            v3 = LastError;
            if ( LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
            if ( v3 != -2147024713 && v3 != -2147024891 )
            {
              if ( v3 == -2147024893 )
              {
                v3 = -2147024713;
                goto LABEL_19;
              }
              goto LABEL_24;
            }
            FileAttributesW = GetFileAttributesW(ppszPathOut);
            if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
            {
LABEL_24:
              if ( v3 < 0 )
                goto LABEL_19;
              goto LABEL_27;
            }
            v3 = 0;
          }
LABEL_27:
          v5 = ppszRootEnd;
          if ( !v6 )
          {
            *ppszRootEnd = 92;
            v5 = ppszRootEnd;
          }
          goto LABEL_29;
        }
      }
    }
  }
LABEL_19:
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ad7bc  mov     [rsp-28h+arg_0], rbx
0x1800ad7c1  push    rbp
0x1800ad7c2  push    rsi
0x1800ad7c3  push    rdi
0x1800ad7c4  push    r12
0x1800ad7c6  push    r14
0x1800ad7c8  mov     rbp, rsp
0x1800ad7cb  sub     rsp, 20h
0x1800ad7cf  xor     r14d, r14d
0x1800ad7d2  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x1800ad7d6  mov     rsi, rdx
0x1800ad7d9  mov     [rbp+ppszRootEnd], r14
0x1800ad7dd  mov     [rbp+ppszPathOut], r14
0x1800ad7e1  lea     edx, [r14+1]; dwFlags
0x1800ad7e5  call    cs:__imp_PathAllocCanonicalize
0x1800ad7ec  nop     dword ptr [rax+rax+00h]
0x1800ad7f1  mov     ebx, eax
0x1800ad7f3  test    eax, eax
0x1800ad7f5  js      loc_1800AD8C5
0x1800ad7fb  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800ad7ff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800ad803  inc     rdx
0x1800ad806  cmp     [rcx+rdx*2], r14w
0x1800ad80b  jnz     short loc_1800AD803
0x1800ad80d  inc     rdx; cchPath
0x1800ad810  call    cs:__imp_PathCchRemoveBackslash
0x1800ad817  nop     dword ptr [rax+rax+00h]
0x1800ad81c  mov     ebx, eax
0x1800ad81e  test    eax, eax
0x1800ad820  js      loc_1800AD8C5
0x1800ad826  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800ad82a  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x1800ad82e  call    cs:__imp_PathCchSkipRoot
0x1800ad835  nop     dword ptr [rax+rax+00h]
0x1800ad83a  mov     ebx, eax
0x1800ad83c  test    eax, eax
0x1800ad83e  js      loc_1800AD8C5
0x1800ad844  mov     rax, [rbp+ppszRootEnd]
0x1800ad848  cmp     r14w, [rax]
0x1800ad84c  jz      short loc_1800AD8C5
0x1800ad84e  mov     edi, r14d
0x1800ad851  mov     r12d, 5Ch ; '\'
0x1800ad857  cmp     r14w, [rax]
0x1800ad85b  jnz     short loc_1800AD864
0x1800ad85d  mov     edi, 1
0x1800ad862  jmp     short loc_1800AD872
0x1800ad864  cmp     r12w, [rax]
0x1800ad868  jnz     loc_1800AD920
0x1800ad86e  mov     [rax], r14w
0x1800ad872  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x1800ad876  mov     rdx, rsi; lpSecurityAttributes
0x1800ad879  call    cs:__imp_CreateDirectoryW
0x1800ad880  nop     dword ptr [rax+rax+00h]
0x1800ad885  test    eax, eax
0x1800ad887  jnz     loc_1800AD910
0x1800ad88d  call    cs:__imp_GetLastError
0x1800ad894  nop     dword ptr [rax+rax+00h]
0x1800ad899  mov     ebx, eax
0x1800ad89b  test    eax, eax
0x1800ad89d  jle     short loc_1800AD8A8
0x1800ad89f  movzx   ebx, ax
0x1800ad8a2  or      ebx, 80070000h
0x1800ad8a8  cmp     ebx, 800700B7h
0x1800ad8ae  jz      short loc_1800AD8EE
0x1800ad8b0  cmp     ebx, 80070005h
0x1800ad8b6  jz      short loc_1800AD8EE
0x1800ad8b8  cmp     ebx, 80070003h
0x1800ad8be  jnz     short loc_1800AD907
0x1800ad8c0  mov     ebx, 800700B7h
0x1800ad8c5  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800ad8c9  test    rcx, rcx
0x1800ad8cc  jz      short loc_1800AD8DA
0x1800ad8ce  call    cs:__imp_LocalFree
0x1800ad8d5  nop     dword ptr [rax+rax+00h]
0x1800ad8da  mov     eax, ebx
0x1800ad8dc  mov     rbx, [rsp+20h+arg_0]
0x1800ad8e1  add     rsp, 20h
0x1800ad8e5  pop     r14
0x1800ad8e7  pop     r12
0x1800ad8e9  pop     rdi
0x1800ad8ea  pop     rsi
0x1800ad8eb  pop     rbp
0x1800ad8ec  retn
0x1800ad8ee  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800ad8f2  call    cs:__imp_GetFileAttributesW
0x1800ad8f9  nop     dword ptr [rax+rax+00h]
0x1800ad8fe  cmp     eax, 0FFFFFFFFh
0x1800ad901  jz      short loc_1800AD90D
0x1800ad903  test    al, 10h
0x1800ad905  jnz     short loc_1800AD90D
0x1800ad907  test    ebx, ebx
0x1800ad909  js      short loc_1800AD8C5
0x1800ad90b  jmp     short loc_1800AD910
0x1800ad90d  mov     ebx, r14d
0x1800ad910  mov     rax, [rbp+ppszRootEnd]
0x1800ad914  test    edi, edi
0x1800ad916  jnz     short loc_1800AD920
0x1800ad918  mov     [rax], r12w
0x1800ad91c  mov     rax, [rbp+ppszRootEnd]
0x1800ad920  add     rax, 2
0x1800ad924  mov     [rbp+ppszRootEnd], rax
0x1800ad928  test    edi, edi
0x1800ad92a  jz      loc_1800AD857
0x1800ad930  jmp     short loc_1800AD8C5
```
