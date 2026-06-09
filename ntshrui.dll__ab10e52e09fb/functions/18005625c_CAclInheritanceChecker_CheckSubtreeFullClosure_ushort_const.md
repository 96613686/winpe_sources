# CAclInheritanceChecker::CheckSubtreeFullClosure(ushort const *)

- ea: `0x18005625c`
- end: `0x1800563bf`
- name: `?CheckSubtreeFullClosure@CAclInheritanceChecker@@QEAAJPEBG@Z`
- size: `355`
- prototype: `__int64 __fastcall(CAclInheritanceChecker *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005625c`
- `0x180056ce4`

## callees

- `0x1800098dc`
- `0x1800194cc`
- `0x18001bf88`
- `0x18001d1dc`
- `0x18005625c`
- `0x180056f7c`
- `0x1800572bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18005628e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180056324`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18005628e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180056324`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180056392`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180056392`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180056381`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180056381`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800562cf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800562cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAclInheritanceChecker::CheckSubtreeFullClosure(
        CAclInheritanceChecker *this,
        const unsigned __int16 *a2)
{
  void *v4; // rcx
  HRESULT Error; // edi
  LPWIN32_FIND_DATAW v6; // rbx
  HANDLE FirstFileW; // rsi
  const WCHAR *v8; // rcx
  CAclInheritanceChecker *v9; // rcx
  HRESULT v10; // eax
  LPWIN32_FIND_DATAW lpFindFileData; // [rsp+20h] [rbp-10h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-8h] BYREF
  bool v14; // [rsp+70h] [rbp+40h] BYREF
  PCWSTR pszPathIn; // [rsp+78h] [rbp+48h] BYREF

  ppszPathOut = 0;
  Error = PathAllocCombine(a2, L"*", 0, &ppszPathOut);
  if ( Error >= 0 )
  {
    lpFindFileData = 0;
    Error = CTCoAllocPolicy::Alloc(v4, 1u, 0x250u, (void **)&lpFindFileData);
    if ( Error >= 0 )
    {
      v6 = lpFindFileData;
      FirstFileW = FindFirstFileW(ppszPathOut, lpFindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        Error = 0;
        do
        {
LABEL_7:
          if ( (v6->dwFileAttributes & 0x10) != 0 )
          {
            if ( (v6->dwFileAttributes & 0x400) == 0 && !(unsigned int)PathIsDotOrDotDotW(v6->cFileName) )
            {
              pszPathIn = 0;
              Error = PathAllocCombine(a2, v8, 0, (PWSTR *)&pszPathIn);
              if ( Error >= 0 )
              {
                v14 = 0;
                if ( CAclInheritanceChecker::IsFolderAclNotFullyInherit(v9, pszPathIn, &v14) >= 0 && v14 )
                  v10 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR))(**(_QWORD **)this + 40LL))(
                          *(_QWORD *)this,
                          pszPathIn);
                else
                  v10 = CAclInheritanceChecker::CheckSubtreeFullClosure(this, pszPathIn);
                Error = v10;
              }
              CLocalMemPtr<void>::~CLocalMemPtr<void>(&pszPathIn);
            }
            if ( Error < 0 )
              break;
          }
        }
        while ( FindNextFileW(FirstFileW, v6) );
        FindClose(FirstFileW);
        goto LABEL_20;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_7;
    }
LABEL_20:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpFindFileData);
  }
  CLocalMemPtr<void>::~CLocalMemPtr<void>(&ppszPathOut);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005625c  mov     [rsp-28h+arg_0], rbx
0x180056261  push    rbp
0x180056262  push    rsi
0x180056263  push    rdi
0x180056264  push    r14
0x180056266  push    r15
0x180056268  mov     rbp, rsp
0x18005626b  sub     rsp, 30h
0x18005626f  mov     r15, rdx
0x180056272  mov     r14, rcx
0x180056275  mov     [rbp+ppszPathOut], 0
0x18005627d  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180056281  xor     r8d, r8d; dwFlags
0x180056284  lea     rdx, pszMore; "*"
0x18005628b  mov     rcx, r15; pszPathIn
0x18005628e  call    cs:__imp_PathAllocCombine
0x180056294  mov     edi, eax
0x180056296  test    eax, eax
0x180056298  js      loc_1800563A3
0x18005629e  mov     [rbp+lpFindFileData], 0
0x1800562a6  lea     r9, [rbp+lpFindFileData]; void **
0x1800562aa  mov     edx, 1; unsigned int
0x1800562af  mov     r8d, 250h; unsigned __int64
0x1800562b5  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800562ba  mov     edi, eax
0x1800562bc  test    eax, eax
0x1800562be  js      loc_180056399
0x1800562c4  mov     rbx, [rbp+lpFindFileData]
0x1800562c8  mov     rdx, rbx; lpFindFileData
0x1800562cb  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800562cf  call    cs:__imp_FindFirstFileW
0x1800562d5  mov     rsi, rax
0x1800562d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800562dc  jnz     short loc_1800562EF
0x1800562de  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800562e3  mov     edi, eax
0x1800562e5  test    eax, eax
0x1800562e7  js      loc_180056399
0x1800562ed  jmp     short loc_1800562F1
0x1800562ef  xor     edi, edi
0x1800562f1  test    byte ptr [rbx], 10h
0x1800562f4  jz      loc_18005637B
0x1800562fa  test    dword ptr [rbx], 400h
0x180056300  jnz     short loc_180056377
0x180056302  lea     rcx, [rbx+2Ch]; unsigned __int16 *
0x180056306  call    ?PathIsDotOrDotDotW@@YAHPEBG@Z; PathIsDotOrDotDotW(ushort const *)
0x18005630b  test    eax, eax
0x18005630d  jnz     short loc_180056377
0x18005630f  mov     [rbp+pszPathIn], 0
0x180056317  lea     r9, [rbp+pszPathIn]; ppszPathOut
0x18005631b  xor     r8d, r8d; dwFlags
0x18005631e  mov     rdx, rcx; pszMore
0x180056321  mov     rcx, r15; pszPathIn
0x180056324  call    cs:__imp_PathAllocCombine
0x18005632a  mov     edi, eax
0x18005632c  test    eax, eax
0x18005632e  js      short loc_18005636E
0x180056330  mov     [rbp+arg_10], 0
0x180056334  lea     r8, [rbp+arg_10]; bool *
0x180056338  mov     rdx, [rbp+pszPathIn]; unsigned __int16 *
0x18005633c  call    ?IsFolderAclNotFullyInherit@CAclInheritanceChecker@@QEAAJPEBGPEA_N@Z; CAclInheritanceChecker::IsFolderAclNotFullyInherit(ushort const *,bool *)
0x180056341  test    eax, eax
0x180056343  js      short loc_180056360
0x180056345  cmp     [rbp+arg_10], 0
0x180056349  jz      short loc_180056360
0x18005634b  mov     rcx, [r14]
0x18005634e  mov     rax, [rcx]
0x180056351  mov     rdx, [rbp+pszPathIn]
0x180056355  mov     rax, [rax+28h]
0x180056359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005635e  jmp     short loc_18005636C
0x180056360  mov     rdx, [rbp+pszPathIn]; unsigned __int16 *
0x180056364  mov     rcx, r14; this
0x180056367  call    ?CheckSubtreeFullClosure@CAclInheritanceChecker@@QEAAJPEBG@Z; CAclInheritanceChecker::CheckSubtreeFullClosure(ushort const *)
0x18005636c  mov     edi, eax
0x18005636e  lea     rcx, [rbp+pszPathIn]
0x180056372  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x180056377  test    edi, edi
0x180056379  js      short loc_18005638F
0x18005637b  mov     rdx, rbx; lpFindFileData
0x18005637e  mov     rcx, rsi; hFindFile
0x180056381  call    cs:__imp_FindNextFileW
0x180056387  test    eax, eax
0x180056389  jnz     loc_1800562F1
0x18005638f  mov     rcx, rsi; hFindFile
0x180056392  call    cs:__imp_FindClose
0x180056398  nop
0x180056399  lea     rcx, [rbp+lpFindFileData]
0x18005639d  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800563a2  nop
0x1800563a3  lea     rcx, [rbp+ppszPathOut]
0x1800563a7  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x1800563ac  mov     eax, edi
0x1800563ae  mov     rbx, [rsp+30h+arg_0]
0x1800563b3  add     rsp, 30h
0x1800563b7  pop     r15
0x1800563b9  pop     r14
0x1800563bb  pop     rdi
0x1800563bc  pop     rsi
0x1800563bd  pop     rbp
0x1800563be  retn
```
