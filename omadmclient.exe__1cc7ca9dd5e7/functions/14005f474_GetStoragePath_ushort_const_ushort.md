# GetStoragePath(ushort const *,ushort * *)

- ea: `0x14005f474`
- end: `0x14005f5b5`
- name: `?GetStoragePath@@YAJPEBGPEAPEAG@Z`
- size: `321`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14005f3e4`
- `0x14005f750`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x14005f474`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x14005f4f8`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x14005f4f8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14005f573`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14005f573`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14005f51e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14005f545`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14005f51e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14005f545`

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
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, &word_14006E728, 0, ppszPathOut);
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
0x14005f474  mov     [rsp+arg_10], rbx
0x14005f479  push    rbp
0x14005f47a  push    rsi
0x14005f47b  push    rdi
0x14005f47c  sub     rsp, 240h
0x14005f483  mov     rax, cs:__security_cookie
0x14005f48a  xor     rax, rsp
0x14005f48d  mov     [rsp+258h+var_28], rax
0x14005f495  mov     rdi, rdx
0x14005f498  mov     rsi, rcx
0x14005f49b  test    rcx, rcx
0x14005f49e  jnz     short loc_14005F4C8
0x14005f4a0  mov     edx, 132h; void *
0x14005f4a5  mov     ebx, 80070057h
0x14005f4aa  mov     rcx, [rsp+258h]; this
0x14005f4b2  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f4b9  mov     r9d, ebx; char *
0x14005f4bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f4c1  mov     eax, ebx
0x14005f4c3  jmp     loc_14005F591
0x14005f4c8  test    rdi, rdi
0x14005f4cb  jnz     short loc_14005F4D4
0x14005f4cd  mov     edx, 133h
0x14005f4d2  jmp     short loc_14005F4A5
0x14005f4d4  xor     edx, edx; Val
0x14005f4d6  lea     rcx, [rsp+258h+pszPath]; void *
0x14005f4db  mov     r8d, 208h; Size
0x14005f4e1  call    memset_0
0x14005f4e6  xor     edx, edx
0x14005f4e8  lea     r8, [rsp+258h+pszPath]
0x14005f4ed  mov     ebp, 104h
0x14005f4f2  mov     r9d, ebp
0x14005f4f5  lea     ecx, [rdx+4]
0x14005f4f8  call    cs:__imp_GetBasicProfileFolderPath
0x14005f4ff  nop     dword ptr [rax+rax+00h]
0x14005f504  mov     ebx, eax
0x14005f506  test    eax, eax
0x14005f508  jns     short loc_14005F50F
0x14005f50a  lea     edx, [rbp+31h]
0x14005f50d  jmp     short loc_14005F4AA
0x14005f50f  lea     r8, aMicrosoftDmcli; "Microsoft\\DMClient"
0x14005f516  mov     rdx, rbp; cchPath
0x14005f519  lea     rcx, [rsp+258h+pszPath]; pszPath
0x14005f51e  call    cs:__imp_PathCchAppend
0x14005f525  nop     dword ptr [rax+rax+00h]
0x14005f52a  mov     ebx, eax
0x14005f52c  test    eax, eax
0x14005f52e  jns     short loc_14005F53A
0x14005f530  mov     edx, 137h
0x14005f535  jmp     loc_14005F4AA
0x14005f53a  mov     r8, rsi; pszMore
0x14005f53d  lea     rcx, [rsp+258h+pszPath]; pszPath
0x14005f542  mov     rdx, rbp; cchPath
0x14005f545  call    cs:__imp_PathCchAppend
0x14005f54c  nop     dword ptr [rax+rax+00h]
0x14005f551  mov     ebx, eax
0x14005f553  test    eax, eax
0x14005f555  jns     short loc_14005F561
0x14005f557  mov     edx, 139h
0x14005f55c  jmp     loc_14005F4AA
0x14005f561  mov     r9, rdi; ppszPathOut
0x14005f564  lea     rdx, word_14006E728; pszMore
0x14005f56b  xor     r8d, r8d; dwFlags
0x14005f56e  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x14005f573  call    cs:__imp_PathAllocCombine
0x14005f57a  nop     dword ptr [rax+rax+00h]
0x14005f57f  mov     ebx, eax
0x14005f581  test    eax, eax
0x14005f583  jns     short loc_14005F58F
0x14005f585  mov     edx, 13Ch
0x14005f58a  jmp     loc_14005F4AA
0x14005f58f  xor     eax, eax
0x14005f591  mov     rcx, [rsp+258h+var_28]
0x14005f599  xor     rcx, rsp; StackCookie
0x14005f59c  call    __security_check_cookie
0x14005f5a1  mov     rbx, [rsp+258h+arg_10]
0x14005f5a9  add     rsp, 240h
0x14005f5b0  pop     rdi
0x14005f5b1  pop     rsi
0x14005f5b2  pop     rbp
0x14005f5b3  retn
```
