# GetStoragePath(ushort const *,ushort * *)

- ea: `0x1800d3b14`
- end: `0x1800d3c55`
- name: `?GetStoragePath@@YAJPEBGPEAPEAG@Z`
- size: `321`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut)`
- caller_count: `7`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800d3800`
- `0x1800d3880`
- `0x1800d3d74`
- `0x1800d48b4`
- `0x1800d49e4`
- `0x1800d4bf0`
- `0x1800d4e0c`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x1800d3b14`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d3c13`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d3c13`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d3bbe`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d3be5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d3bbe`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d3be5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800d3b98`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800d3b98`

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
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, &Class, 0, ppszPathOut);
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
0x1800d3b14  mov     [rsp+arg_10], rbx
0x1800d3b19  push    rbp
0x1800d3b1a  push    rsi
0x1800d3b1b  push    rdi
0x1800d3b1c  sub     rsp, 240h
0x1800d3b23  mov     rax, cs:__security_cookie
0x1800d3b2a  xor     rax, rsp
0x1800d3b2d  mov     [rsp+258h+var_28], rax
0x1800d3b35  mov     rdi, rdx
0x1800d3b38  mov     rsi, rcx
0x1800d3b3b  test    rcx, rcx
0x1800d3b3e  jnz     short loc_1800D3B68
0x1800d3b40  mov     edx, 132h; void *
0x1800d3b45  mov     ebx, 80070057h
0x1800d3b4a  mov     rcx, [rsp+258h]; this
0x1800d3b52  lea     r8, aOnecoreuapAdmi_107; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800d3b59  mov     r9d, ebx; char *
0x1800d3b5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3b61  mov     eax, ebx
0x1800d3b63  jmp     loc_1800D3C31
0x1800d3b68  test    rdi, rdi
0x1800d3b6b  jnz     short loc_1800D3B74
0x1800d3b6d  mov     edx, 133h
0x1800d3b72  jmp     short loc_1800D3B45
0x1800d3b74  xor     edx, edx; Val
0x1800d3b76  lea     rcx, [rsp+258h+pszPath]; void *
0x1800d3b7b  mov     r8d, 208h; Size
0x1800d3b81  call    memset_0
0x1800d3b86  xor     edx, edx
0x1800d3b88  lea     r8, [rsp+258h+pszPath]
0x1800d3b8d  mov     ebp, 104h
0x1800d3b92  mov     r9d, ebp
0x1800d3b95  lea     ecx, [rdx+4]
0x1800d3b98  call    cs:__imp_GetBasicProfileFolderPath
0x1800d3b9f  nop     dword ptr [rax+rax+00h]
0x1800d3ba4  mov     ebx, eax
0x1800d3ba6  test    eax, eax
0x1800d3ba8  jns     short loc_1800D3BAF
0x1800d3baa  lea     edx, [rbp+31h]
0x1800d3bad  jmp     short loc_1800D3B4A
0x1800d3baf  lea     r8, pszMore; "Microsoft\\DMClient"
0x1800d3bb6  mov     rdx, rbp; cchPath
0x1800d3bb9  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800d3bbe  call    cs:__imp_PathCchAppend
0x1800d3bc5  nop     dword ptr [rax+rax+00h]
0x1800d3bca  mov     ebx, eax
0x1800d3bcc  test    eax, eax
0x1800d3bce  jns     short loc_1800D3BDA
0x1800d3bd0  mov     edx, 137h
0x1800d3bd5  jmp     loc_1800D3B4A
0x1800d3bda  mov     r8, rsi; pszMore
0x1800d3bdd  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800d3be2  mov     rdx, rbp; cchPath
0x1800d3be5  call    cs:__imp_PathCchAppend
0x1800d3bec  nop     dword ptr [rax+rax+00h]
0x1800d3bf1  mov     ebx, eax
0x1800d3bf3  test    eax, eax
0x1800d3bf5  jns     short loc_1800D3C01
0x1800d3bf7  mov     edx, 139h
0x1800d3bfc  jmp     loc_1800D3B4A
0x1800d3c01  mov     r9, rdi; ppszPathOut
0x1800d3c04  lea     rdx, Class; pszMore
0x1800d3c0b  xor     r8d, r8d; dwFlags
0x1800d3c0e  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x1800d3c13  call    cs:__imp_PathAllocCombine
0x1800d3c1a  nop     dword ptr [rax+rax+00h]
0x1800d3c1f  mov     ebx, eax
0x1800d3c21  test    eax, eax
0x1800d3c23  jns     short loc_1800D3C2F
0x1800d3c25  mov     edx, 13Ch
0x1800d3c2a  jmp     loc_1800D3B4A
0x1800d3c2f  xor     eax, eax
0x1800d3c31  mov     rcx, [rsp+258h+var_28]
0x1800d3c39  xor     rcx, rsp; StackCookie
0x1800d3c3c  call    __security_check_cookie
0x1800d3c41  mov     rbx, [rsp+258h+arg_10]
0x1800d3c49  add     rsp, 240h
0x1800d3c50  pop     rdi
0x1800d3c51  pop     rsi
0x1800d3c52  pop     rbp
0x1800d3c53  retn
```
