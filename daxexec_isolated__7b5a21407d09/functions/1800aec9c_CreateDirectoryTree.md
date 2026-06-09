# CreateDirectoryTree

- ea: `0x1800aec9c`
- end: `0x1800aee12`
- name: `CreateDirectoryTree`
- size: `374`
- prototype: `__int64 __fastcall(const WCHAR *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180032218`
- `0x180033100`
- `0x180079238`
- `0x180079ff4`

## callees

- `0x1800aec9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aed6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aed6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aedae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aedae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aedd2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aedd2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aed59`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aed59`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800aecf0`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800aecf0`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800aecc5`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800aecc5`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800aed0e`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800aed0e`

## pseudocode

```c
__int64 __fastcall CreateDirectoryTree(const WCHAR *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  PCWSTR v5; // rcx
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
LABEL_30:
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
          if ( !v6 )
            *ppszRootEnd = 92;
          v5 = ppszRootEnd;
          goto LABEL_30;
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
0x1800aec9c  mov     [rsp-28h+arg_0], rbx
0x1800aeca1  push    rbp
0x1800aeca2  push    rsi
0x1800aeca3  push    rdi
0x1800aeca4  push    r12
0x1800aeca6  push    r14
0x1800aeca8  mov     rbp, rsp
0x1800aecab  sub     rsp, 20h
0x1800aecaf  xor     r14d, r14d
0x1800aecb2  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x1800aecb6  mov     rsi, rdx
0x1800aecb9  mov     [rbp+ppszRootEnd], r14
0x1800aecbd  mov     [rbp+ppszPathOut], r14
0x1800aecc1  lea     edx, [r14+1]; dwFlags
0x1800aecc5  call    cs:__imp_PathAllocCanonicalize
0x1800aeccc  nop     dword ptr [rax+rax+00h]
0x1800aecd1  mov     ebx, eax
0x1800aecd3  test    eax, eax
0x1800aecd5  js      loc_1800AEDA5
0x1800aecdb  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800aecdf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800aece3  inc     rdx
0x1800aece6  cmp     [rcx+rdx*2], r14w
0x1800aeceb  jnz     short loc_1800AECE3
0x1800aeced  inc     rdx; cchPath
0x1800aecf0  call    cs:__imp_PathCchRemoveBackslash
0x1800aecf7  nop     dword ptr [rax+rax+00h]
0x1800aecfc  mov     ebx, eax
0x1800aecfe  test    eax, eax
0x1800aed00  js      loc_1800AEDA5
0x1800aed06  mov     rcx, [rbp+ppszPathOut]; pszPath
0x1800aed0a  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x1800aed0e  call    cs:__imp_PathCchSkipRoot
0x1800aed15  nop     dword ptr [rax+rax+00h]
0x1800aed1a  mov     ebx, eax
0x1800aed1c  test    eax, eax
0x1800aed1e  js      loc_1800AEDA5
0x1800aed24  mov     rcx, [rbp+ppszRootEnd]
0x1800aed28  cmp     r14w, [rcx]
0x1800aed2c  jz      short loc_1800AEDA5
0x1800aed2e  mov     edi, r14d
0x1800aed31  mov     r12d, 5Ch ; '\'
0x1800aed37  cmp     r14w, [rcx]
0x1800aed3b  jnz     short loc_1800AED44
0x1800aed3d  mov     edi, 1
0x1800aed42  jmp     short loc_1800AED52
0x1800aed44  cmp     r12w, [rcx]
0x1800aed48  jnz     loc_1800AEE00
0x1800aed4e  mov     [rcx], r14w
0x1800aed52  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x1800aed56  mov     rdx, rsi; lpSecurityAttributes
0x1800aed59  call    cs:__imp_CreateDirectoryW
0x1800aed60  nop     dword ptr [rax+rax+00h]
0x1800aed65  test    eax, eax
0x1800aed67  jnz     loc_1800AEDF0
0x1800aed6d  call    cs:__imp_GetLastError
0x1800aed74  nop     dword ptr [rax+rax+00h]
0x1800aed79  mov     ebx, eax
0x1800aed7b  test    eax, eax
0x1800aed7d  jle     short loc_1800AED88
0x1800aed7f  movzx   ebx, ax
0x1800aed82  or      ebx, 80070000h
0x1800aed88  cmp     ebx, 800700B7h
0x1800aed8e  jz      short loc_1800AEDCE
0x1800aed90  cmp     ebx, 80070005h
0x1800aed96  jz      short loc_1800AEDCE
0x1800aed98  cmp     ebx, 80070003h
0x1800aed9e  jnz     short loc_1800AEDE7
0x1800aeda0  mov     ebx, 800700B7h
0x1800aeda5  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800aeda9  test    rcx, rcx
0x1800aedac  jz      short loc_1800AEDBA
0x1800aedae  call    cs:__imp_LocalFree
0x1800aedb5  nop     dword ptr [rax+rax+00h]
0x1800aedba  mov     eax, ebx
0x1800aedbc  mov     rbx, [rsp+20h+arg_0]
0x1800aedc1  add     rsp, 20h
0x1800aedc5  pop     r14
0x1800aedc7  pop     r12
0x1800aedc9  pop     rdi
0x1800aedca  pop     rsi
0x1800aedcb  pop     rbp
0x1800aedcc  retn
0x1800aedce  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800aedd2  call    cs:__imp_GetFileAttributesW
0x1800aedd9  nop     dword ptr [rax+rax+00h]
0x1800aedde  cmp     eax, 0FFFFFFFFh
0x1800aede1  jz      short loc_1800AEDED
0x1800aede3  test    al, 10h
0x1800aede5  jnz     short loc_1800AEDED
0x1800aede7  test    ebx, ebx
0x1800aede9  js      short loc_1800AEDA5
0x1800aedeb  jmp     short loc_1800AEDF0
0x1800aeded  mov     ebx, r14d
0x1800aedf0  test    edi, edi
0x1800aedf2  jnz     short loc_1800AEDFC
0x1800aedf4  mov     rax, [rbp+ppszRootEnd]
0x1800aedf8  mov     [rax], r12w
0x1800aedfc  mov     rcx, [rbp+ppszRootEnd]
0x1800aee00  add     rcx, 2
0x1800aee04  mov     [rbp+ppszRootEnd], rcx
0x1800aee08  test    edi, edi
0x1800aee0a  jz      loc_1800AED37
0x1800aee10  jmp     short loc_1800AEDA5
```
