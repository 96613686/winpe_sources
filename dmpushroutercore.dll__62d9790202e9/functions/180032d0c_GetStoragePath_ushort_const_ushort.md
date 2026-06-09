# GetStoragePath(ushort const *,ushort * *)

- ea: `0x180032d0c`
- end: `0x180032e34`
- name: `?GetStoragePath@@YAJPEBGPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut)`
- caller_count: `8`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180031a14`
- `0x180031af8`
- `0x180032038`
- `0x1800331d0`
- `0x180033450`
- `0x180033920`
- `0x180033a5c`
- `0x180033f30`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000bab4`
- `0x180032d0c`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180032df9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180032df9`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180032db0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180032dd1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180032db0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180032dd1`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180032d90`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180032d90`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, &word_1800401D0, 0, ppszPathOut);
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
0x180032d0c  mov     [rsp+arg_10], rbx
0x180032d11  push    rbp
0x180032d12  push    rsi
0x180032d13  push    rdi
0x180032d14  sub     rsp, 240h
0x180032d1b  mov     rax, cs:__security_cookie
0x180032d22  xor     rax, rsp
0x180032d25  mov     [rsp+258h+var_28], rax
0x180032d2d  mov     rdi, rdx
0x180032d30  mov     rsi, rcx
0x180032d33  test    rcx, rcx
0x180032d36  jnz     short loc_180032D60
0x180032d38  mov     edx, 132h; void *
0x180032d3d  mov     ebx, 80070057h
0x180032d42  mov     rcx, [rsp+258h]; this
0x180032d4a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180032d51  mov     r9d, ebx; char *
0x180032d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d59  mov     eax, ebx
0x180032d5b  jmp     loc_180032E11
0x180032d60  test    rdi, rdi
0x180032d63  jnz     short loc_180032D6C
0x180032d65  mov     edx, 133h
0x180032d6a  jmp     short loc_180032D3D
0x180032d6c  xor     edx, edx; Val
0x180032d6e  lea     rcx, [rsp+258h+pszPath]; void *
0x180032d73  mov     r8d, 208h; Size
0x180032d79  call    memset_0
0x180032d7e  xor     edx, edx
0x180032d80  lea     r8, [rsp+258h+pszPath]
0x180032d85  mov     ebp, 104h
0x180032d8a  mov     r9d, ebp
0x180032d8d  lea     ecx, [rdx+4]
0x180032d90  call    cs:__imp_GetBasicProfileFolderPath
0x180032d96  mov     ebx, eax
0x180032d98  test    eax, eax
0x180032d9a  jns     short loc_180032DA1
0x180032d9c  lea     edx, [rbp+31h]
0x180032d9f  jmp     short loc_180032D42
0x180032da1  lea     r8, aMicrosoftDmcli; "Microsoft\\DMClient"
0x180032da8  mov     rdx, rbp; cchPath
0x180032dab  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180032db0  call    cs:__imp_PathCchAppend
0x180032db6  mov     ebx, eax
0x180032db8  test    eax, eax
0x180032dba  jns     short loc_180032DC6
0x180032dbc  mov     edx, 137h
0x180032dc1  jmp     loc_180032D42
0x180032dc6  mov     r8, rsi; pszMore
0x180032dc9  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180032dce  mov     rdx, rbp; cchPath
0x180032dd1  call    cs:__imp_PathCchAppend
0x180032dd7  mov     ebx, eax
0x180032dd9  test    eax, eax
0x180032ddb  jns     short loc_180032DE7
0x180032ddd  mov     edx, 139h
0x180032de2  jmp     loc_180032D42
0x180032de7  mov     r9, rdi; ppszPathOut
0x180032dea  lea     rdx, word_1800401D0; pszMore
0x180032df1  xor     r8d, r8d; dwFlags
0x180032df4  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x180032df9  call    cs:__imp_PathAllocCombine
0x180032dff  mov     ebx, eax
0x180032e01  test    eax, eax
0x180032e03  jns     short loc_180032E0F
0x180032e05  mov     edx, 13Ch
0x180032e0a  jmp     loc_180032D42
0x180032e0f  xor     eax, eax
0x180032e11  mov     rcx, [rsp+258h+var_28]
0x180032e19  xor     rcx, rsp; StackCookie
0x180032e1c  call    __security_check_cookie
0x180032e21  mov     rbx, [rsp+258h+arg_10]
0x180032e29  add     rsp, 240h
0x180032e30  pop     rdi
0x180032e31  pop     rsi
0x180032e32  pop     rbp
0x180032e33  retn
```
