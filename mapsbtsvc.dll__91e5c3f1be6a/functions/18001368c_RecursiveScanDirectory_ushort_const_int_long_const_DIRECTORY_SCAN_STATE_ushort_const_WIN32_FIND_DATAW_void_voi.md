# RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)

- ea: `0x18001368c`
- end: `0x18001386c`
- name: `?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z`
- size: `480`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, int (__high *const)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b544`
- `0x18001368c`

## callees

- `0x18001368c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ef`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800136fa`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800136fa`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001371c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001378a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001371c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001378a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013807`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013812`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013807`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013812`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800137d9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800137d9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013733`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013733`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800136d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800136d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001383c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001384f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001383c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001384f`

## pseudocode

```c
__int64 __fastcall RecursiveScanDirectory(
        const unsigned __int16 *a1,
        __int64 a2,
        int (__high *const a3)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *),
        void *a4)
{
  struct _WIN32_FIND_DATAW *v6; // rdi
  int v7; // ebx
  HANDLE FirstFileW; // rsi
  BOOL i; // eax
  __int64 v10; // rcx
  int v11; // eax
  signed int LastError; // eax
  PWSTR ppszPathOut; // [rsp+70h] [rbp+40h] BYREF
  PCWSTR pszPathIn; // [rsp+88h] [rbp+58h] BYREF

  pszPathIn = 0;
  ppszPathOut = 0;
  if ( !a1 || !a3 )
  {
    v6 = 0;
    v7 = -2147024809;
    goto LABEL_30;
  }
  v6 = (struct _WIN32_FIND_DATAW *)LocalAlloc(0, 0x250u);
  if ( !v6 )
  {
    v7 = -2147024882;
    goto LABEL_30;
  }
  v7 = PathAllocCanonicalize(a1, 1u, &ppszPathOut);
  if ( v7 >= 0 )
  {
    v7 = PathAllocCombine(ppszPathOut, L"*", 1u, (PWSTR *)&pszPathIn);
    if ( v7 >= 0 )
    {
      FirstFileW = FindFirstFileW(pszPathIn, v6);
      if ( FirstFileW == (HANDLE)-1LL )
        goto LABEL_28;
      for ( i = 1; ; i = FindNextFileW(FirstFileW, v6) )
      {
        if ( !i )
        {
          if ( GetLastError() != 18 )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
            FindClose(FirstFileW);
            goto LABEL_30;
          }
          FindClose(FirstFileW);
LABEL_28:
          v7 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, _QWORD))a3)(
                 1,
                 a1,
                 v6,
                 0);
          goto LABEL_30;
        }
        if ( v6->cFileName[0] != 46 || v6->cFileName[1] && (v6->cFileName[1] != 46 || v6->cFileName[2]) )
          break;
LABEL_22:
        ;
      }
      LocalFree((HLOCAL)pszPathIn);
      pszPathIn = 0;
      v7 = PathAllocCombine(ppszPathOut, v6->cFileName, 1u, (PWSTR *)&pszPathIn);
      if ( v7 < 0 )
        goto LABEL_26;
      if ( (v6->dwFileAttributes & 0x10) != 0 )
      {
        if ( (v6->dwFileAttributes & 0x400) == 0 )
        {
          v11 = RecursiveScanDirectory(pszPathIn, 1, a3, 0);
          goto LABEL_21;
        }
        v10 = 1;
      }
      else
      {
        v10 = 0;
      }
      v11 = ((__int64 (__fastcall *)(__int64, PCWSTR, struct _WIN32_FIND_DATAW *, _QWORD))a3)(v10, pszPathIn, v6, 0);
LABEL_21:
      v7 = v11;
      if ( v11 < 0 )
        goto LABEL_26;
      goto LABEL_22;
    }
  }
LABEL_30:
  LocalFree(ppszPathOut);
  LocalFree((HLOCAL)pszPathIn);
  LocalFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001368c  mov     [rsp-38h+arg_8], rbx
0x180013691  mov     [rsp-38h+pszPathIn], r9
0x180013696  push    rbp
0x180013697  push    rsi
0x180013698  push    rdi
0x180013699  push    r12
0x18001369b  push    r13
0x18001369d  push    r14
0x18001369f  push    r15
0x1800136a1  mov     rbp, rsp
0x1800136a4  sub     rsp, 30h
0x1800136a8  xor     r12d, r12d
0x1800136ab  mov     r14, r8
0x1800136ae  mov     [rbp+pszPathIn], r12
0x1800136b2  mov     r15, rcx
0x1800136b5  mov     [rbp+ppszPathOut], r12
0x1800136b9  test    rcx, rcx
0x1800136bc  jz      loc_180013830
0x1800136c2  test    r8, r8
0x1800136c5  jz      loc_180013830
0x1800136cb  mov     edx, 250h; uBytes
0x1800136d0  xor     ecx, ecx; uFlags
0x1800136d2  call    cs:__imp_LocalAlloc
0x1800136d8  mov     rdi, rax
0x1800136db  test    rax, rax
0x1800136de  jnz     short loc_1800136EA
0x1800136e0  mov     ebx, 8007000Eh
0x1800136e5  jmp     loc_180013838
0x1800136ea  mov     r13d, 1
0x1800136f0  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x1800136f4  mov     edx, r13d; dwFlags
0x1800136f7  mov     rcx, r15; pszPathIn
0x1800136fa  call    cs:__imp_PathAllocCanonicalize
0x180013700  mov     ebx, eax
0x180013702  test    eax, eax
0x180013704  js      loc_180013838
0x18001370a  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18001370e  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x180013712  mov     r8d, r13d; dwFlags
0x180013715  lea     rdx, asc_1800184FC; "*"
0x18001371c  call    cs:__imp_PathAllocCombine
0x180013722  mov     ebx, eax
0x180013724  test    eax, eax
0x180013726  js      loc_180013838
0x18001372c  mov     rcx, [rbp+pszPathIn]; lpFileName
0x180013730  mov     rdx, rdi; lpFindFileData
0x180013733  call    cs:__imp_FindFirstFileW
0x180013739  mov     rsi, rax
0x18001373c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013740  jz      loc_180013818
0x180013746  mov     eax, r13d
0x180013749  test    eax, eax
0x18001374b  jz      loc_1800137E4
0x180013751  cmp     word ptr [rdi+2Ch], 2Eh ; '.'
0x180013756  jnz     short loc_18001376D
0x180013758  cmp     [rdi+2Eh], r12w
0x18001375d  jz      short loc_1800137D3
0x18001375f  cmp     word ptr [rdi+2Eh], 2Eh ; '.'
0x180013764  jnz     short loc_18001376D
0x180013766  cmp     [rdi+30h], r12w
0x18001376b  jz      short loc_1800137D3
0x18001376d  mov     rcx, [rbp+pszPathIn]; hMem
0x180013771  call    cs:__imp_LocalFree
0x180013777  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18001377b  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x18001377f  mov     r8d, r13d; dwFlags
0x180013782  mov     [rbp+pszPathIn], r12
0x180013786  lea     rdx, [rdi+2Ch]; pszMore
0x18001378a  call    cs:__imp_PathAllocCombine
0x180013790  mov     ebx, eax
0x180013792  test    eax, eax
0x180013794  js      short loc_180013804
0x180013796  xor     r9d, r9d; void *
0x180013799  test    byte ptr [rdi], 10h
0x18001379c  jz      short loc_1800137BC
0x18001379e  test    dword ptr [rdi], 400h
0x1800137a4  jz      short loc_1800137AB
0x1800137a6  mov     ecx, r13d
0x1800137a9  jmp     short loc_1800137BE
0x1800137ab  mov     rcx, [rbp+pszPathIn]; unsigned __int16 *
0x1800137af  mov     r8, r14; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x1800137b2  mov     edx, r13d; int
0x1800137b5  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x1800137ba  jmp     short loc_1800137CD
0x1800137bc  xor     ecx, ecx
0x1800137be  mov     rdx, [rbp+pszPathIn]
0x1800137c2  mov     r8, rdi
0x1800137c5  mov     rax, r14
0x1800137c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137cd  mov     ebx, eax
0x1800137cf  test    eax, eax
0x1800137d1  js      short loc_180013804
0x1800137d3  mov     rdx, rdi; lpFindFileData
0x1800137d6  mov     rcx, rsi; hFindFile
0x1800137d9  call    cs:__imp_FindNextFileW
0x1800137df  jmp     loc_180013749
0x1800137e4  call    cs:__imp_GetLastError
0x1800137ea  cmp     eax, 12h
0x1800137ed  jz      short loc_18001380F
0x1800137ef  call    cs:__imp_GetLastError
0x1800137f5  mov     ebx, eax
0x1800137f7  test    eax, eax
0x1800137f9  jle     short loc_180013804
0x1800137fb  movzx   ebx, ax
0x1800137fe  or      ebx, 80070000h
0x180013804  mov     rcx, rsi; hFindFile
0x180013807  call    cs:__imp_FindClose
0x18001380d  jmp     short loc_180013838
0x18001380f  mov     rcx, rsi; hFindFile
0x180013812  call    cs:__imp_FindClose
0x180013818  xor     r9d, r9d
0x18001381b  mov     r8, rdi
0x18001381e  mov     rdx, r15
0x180013821  mov     ecx, r13d
0x180013824  mov     rax, r14
0x180013827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001382c  mov     ebx, eax
0x18001382e  jmp     short loc_180013838
0x180013830  mov     rdi, r12
0x180013833  mov     ebx, 80070057h
0x180013838  mov     rcx, [rbp+ppszPathOut]; hMem
0x18001383c  call    cs:__imp_LocalFree
0x180013842  mov     rcx, [rbp+pszPathIn]; hMem
0x180013846  call    cs:__imp_LocalFree
0x18001384c  mov     rcx, rdi; hMem
0x18001384f  call    cs:__imp_LocalFree
0x180013855  mov     eax, ebx
0x180013857  mov     rbx, [rsp+30h+arg_8]
0x18001385c  add     rsp, 30h
0x180013860  pop     r15
0x180013862  pop     r14
0x180013864  pop     r13
0x180013866  pop     r12
0x180013868  pop     rdi
0x180013869  pop     rsi
0x18001386a  pop     rbp
0x18001386b  retn
```
