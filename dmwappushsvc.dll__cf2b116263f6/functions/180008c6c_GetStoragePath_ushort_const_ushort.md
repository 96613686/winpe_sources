# GetStoragePath(ushort const *,ushort * *)

- ea: `0x180008c6c`
- end: `0x180008d94`
- name: `?GetStoragePath@@YAJPEBGPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000a094`
- `0x18000b990`

## callees

- `0x180001a70`
- `0x180002554`
- `0x180008c6c`
- `0x18000af78`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180008d10`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180008d31`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180008d10`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180008d31`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180008d59`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180008d59`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180008cf0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180008cf0`

## pseudocode

```c
__int64 __fastcall GetStoragePath(PCWSTR pszMore, PWSTR *ppszPathOut)
{
  __int64 v4; // rdx
  HRESULT BasicProfileFolderPath; // ebx
  int pszPath[132]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  if ( !pszMore )
  {
    v4 = 306;
LABEL_3:
    BasicProfileFolderPath = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      pszPath[0]);
    return (unsigned int)BasicProfileFolderPath;
  }
  if ( !ppszPathOut )
  {
    v4 = 307;
    goto LABEL_3;
  }
  memset_0(pszPath, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, pszPath, 260);
  if ( BasicProfileFolderPath < 0 )
  {
    v4 = 309;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathCchAppend((PWSTR)pszPath, 0x104u, L"Microsoft\\DMClient");
  if ( BasicProfileFolderPath < 0 )
  {
    v4 = 311;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathCchAppend((PWSTR)pszPath, 0x104u, pszMore);
  if ( BasicProfileFolderPath < 0 )
  {
    v4 = 313;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, &Source, 0, ppszPathOut);
  if ( BasicProfileFolderPath < 0 )
  {
    v4 = 316;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180008c6c  mov     [rsp+arg_10], rbx
0x180008c71  push    rbp
0x180008c72  push    rsi
0x180008c73  push    rdi
0x180008c74  sub     rsp, 240h
0x180008c7b  mov     rax, cs:__security_cookie
0x180008c82  xor     rax, rsp
0x180008c85  mov     [rsp+258h+var_28], rax
0x180008c8d  mov     rdi, rdx
0x180008c90  mov     rsi, rcx
0x180008c93  test    rcx, rcx
0x180008c96  jnz     short loc_180008CC0
0x180008c98  mov     edx, 132h; void *
0x180008c9d  mov     ebx, 80070057h
0x180008ca2  mov     rcx, [rsp+258h]; this
0x180008caa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180008cb1  mov     r9d, ebx; char *
0x180008cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cb9  mov     eax, ebx
0x180008cbb  jmp     loc_180008D71
0x180008cc0  test    rdi, rdi
0x180008cc3  jnz     short loc_180008CCC
0x180008cc5  mov     edx, 133h
0x180008cca  jmp     short loc_180008C9D
0x180008ccc  xor     edx, edx; Val
0x180008cce  lea     rcx, [rsp+258h+pszPath]; void *
0x180008cd3  mov     r8d, 208h; Size
0x180008cd9  call    memset_0
0x180008cde  xor     edx, edx
0x180008ce0  lea     r8, [rsp+258h+pszPath]
0x180008ce5  mov     ebp, 104h
0x180008cea  mov     r9d, ebp
0x180008ced  lea     ecx, [rdx+4]
0x180008cf0  call    cs:__imp_GetBasicProfileFolderPath
0x180008cf6  mov     ebx, eax
0x180008cf8  test    eax, eax
0x180008cfa  jns     short loc_180008D01
0x180008cfc  lea     edx, [rbp+31h]
0x180008cff  jmp     short loc_180008CA2
0x180008d01  lea     r8, pszMore; "Microsoft\\DMClient"
0x180008d08  mov     rdx, rbp; cchPath
0x180008d0b  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180008d10  call    cs:__imp_PathCchAppend
0x180008d16  mov     ebx, eax
0x180008d18  test    eax, eax
0x180008d1a  jns     short loc_180008D26
0x180008d1c  mov     edx, 137h
0x180008d21  jmp     loc_180008CA2
0x180008d26  mov     r8, rsi; pszMore
0x180008d29  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180008d2e  mov     rdx, rbp; cchPath
0x180008d31  call    cs:__imp_PathCchAppend
0x180008d37  mov     ebx, eax
0x180008d39  test    eax, eax
0x180008d3b  jns     short loc_180008D47
0x180008d3d  mov     edx, 139h
0x180008d42  jmp     loc_180008CA2
0x180008d47  mov     r9, rdi; ppszPathOut
0x180008d4a  lea     rdx, Source; pszMore
0x180008d51  xor     r8d, r8d; dwFlags
0x180008d54  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x180008d59  call    cs:__imp_PathAllocCombine
0x180008d5f  mov     ebx, eax
0x180008d61  test    eax, eax
0x180008d63  jns     short loc_180008D6F
0x180008d65  mov     edx, 13Ch
0x180008d6a  jmp     loc_180008CA2
0x180008d6f  xor     eax, eax
0x180008d71  mov     rcx, [rsp+258h+var_28]
0x180008d79  xor     rcx, rsp; StackCookie
0x180008d7c  call    __security_check_cookie
0x180008d81  mov     rbx, [rsp+258h+arg_10]
0x180008d89  add     rsp, 240h
0x180008d90  pop     rdi
0x180008d91  pop     rsi
0x180008d92  pop     rbp
0x180008d93  retn
```
