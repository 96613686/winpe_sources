# GetStoragePath(ushort const *,ushort * *)

- ea: `0x180076f44`
- end: `0x18007706c`
- name: `?GetStoragePath@@YAJPEBGPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180076de8`

## callees

- `0x180011938`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180076f44`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180076fe8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180077009`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180076fe8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180077009`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180077031`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180077031`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180076fc8`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180076fc8`

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
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, &wszURI, 0, ppszPathOut);
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
0x180076f44  mov     [rsp+arg_10], rbx
0x180076f49  push    rbp
0x180076f4a  push    rsi
0x180076f4b  push    rdi
0x180076f4c  sub     rsp, 240h
0x180076f53  mov     rax, cs:__security_cookie
0x180076f5a  xor     rax, rsp
0x180076f5d  mov     [rsp+258h+var_28], rax
0x180076f65  mov     rdi, rdx
0x180076f68  mov     rsi, rcx
0x180076f6b  test    rcx, rcx
0x180076f6e  jnz     short loc_180076F98
0x180076f70  mov     edx, 132h; void *
0x180076f75  mov     ebx, 80070057h
0x180076f7a  mov     rcx, [rsp+258h]; this
0x180076f82  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180076f89  mov     r9d, ebx; char *
0x180076f8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076f91  mov     eax, ebx
0x180076f93  jmp     loc_180077049
0x180076f98  test    rdi, rdi
0x180076f9b  jnz     short loc_180076FA4
0x180076f9d  mov     edx, 133h
0x180076fa2  jmp     short loc_180076F75
0x180076fa4  xor     edx, edx; Val
0x180076fa6  lea     rcx, [rsp+258h+pszPath]; void *
0x180076fab  mov     r8d, 208h; Size
0x180076fb1  call    memset_0
0x180076fb6  xor     edx, edx
0x180076fb8  lea     r8, [rsp+258h+pszPath]
0x180076fbd  mov     ebp, 104h
0x180076fc2  mov     r9d, ebp
0x180076fc5  lea     ecx, [rdx+4]
0x180076fc8  call    cs:__imp_GetBasicProfileFolderPath
0x180076fce  mov     ebx, eax
0x180076fd0  test    eax, eax
0x180076fd2  jns     short loc_180076FD9
0x180076fd4  lea     edx, [rbp+31h]
0x180076fd7  jmp     short loc_180076F7A
0x180076fd9  lea     r8, aMicrosoftDmcli; "Microsoft\\DMClient"
0x180076fe0  mov     rdx, rbp; cchPath
0x180076fe3  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180076fe8  call    cs:__imp_PathCchAppend
0x180076fee  mov     ebx, eax
0x180076ff0  test    eax, eax
0x180076ff2  jns     short loc_180076FFE
0x180076ff4  mov     edx, 137h
0x180076ff9  jmp     loc_180076F7A
0x180076ffe  mov     r8, rsi; pszMore
0x180077001  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180077006  mov     rdx, rbp; cchPath
0x180077009  call    cs:__imp_PathCchAppend
0x18007700f  mov     ebx, eax
0x180077011  test    eax, eax
0x180077013  jns     short loc_18007701F
0x180077015  mov     edx, 139h
0x18007701a  jmp     loc_180076F7A
0x18007701f  mov     r9, rdi; ppszPathOut
0x180077022  lea     rdx, wszURI; pszMore
0x180077029  xor     r8d, r8d; dwFlags
0x18007702c  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x180077031  call    cs:__imp_PathAllocCombine
0x180077037  mov     ebx, eax
0x180077039  test    eax, eax
0x18007703b  jns     short loc_180077047
0x18007703d  mov     edx, 13Ch
0x180077042  jmp     loc_180076F7A
0x180077047  xor     eax, eax
0x180077049  mov     rcx, [rsp+258h+var_28]
0x180077051  xor     rcx, rsp; StackCookie
0x180077054  call    __security_check_cookie
0x180077059  mov     rbx, [rsp+258h+arg_10]
0x180077061  add     rsp, 240h
0x180077068  pop     rdi
0x180077069  pop     rsi
0x18007706a  pop     rbp
0x18007706b  retn
```
