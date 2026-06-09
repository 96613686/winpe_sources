# FirstSync::GetStoragePath(ushort const *,ushort * *)

- ea: `0x1800fa920`
- end: `0x1800faa5f`
- name: `?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z`
- size: `319`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PWSTR *ppszPathOut, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18003b3f0`
- `0x1800f9548`
- `0x1800f9760`
- `0x1800f9b94`
- `0x1800f9d20`
- `0x1800fb85c`
- `0x1800fb914`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x1800fa920`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800faa1d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800faa1d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa9c8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa9ef`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa9c8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa9ef`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800fa9a0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800fa9a0`

## pseudocode

```c
__int64 __fastcall FirstSync::GetStoragePath(PCWSTR pszMore, PWSTR *ppszPathOut, unsigned __int16 **a3)
{
  __int64 v5; // rdx
  HRESULT BasicProfileFolderPath; // ebx
  int pszPath[132]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  if ( !pszMore )
  {
    v5 = 93;
LABEL_3:
    BasicProfileFolderPath = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      pszPath[0]);
    return (unsigned int)BasicProfileFolderPath;
  }
  if ( !ppszPathOut )
  {
    v5 = 94;
    goto LABEL_3;
  }
  memset_0(pszPath, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, pszPath, 260);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 97;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathCchAppend((PWSTR)pszPath, 0x104u, L"Microsoft\\DMClient");
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 100;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathCchAppend((PWSTR)pszPath, 0x104u, pszMore);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 103;
    goto LABEL_4;
  }
  BasicProfileFolderPath = PathAllocCombine((PCWSTR)pszPath, L"FirstSync", 0, ppszPathOut);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 105;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800fa920  mov     [rsp+arg_10], rbx
0x1800fa925  push    rbp
0x1800fa926  push    rsi
0x1800fa927  push    rdi
0x1800fa928  sub     rsp, 240h
0x1800fa92f  mov     rax, cs:__security_cookie
0x1800fa936  xor     rax, rsp
0x1800fa939  mov     [rsp+258h+var_28], rax
0x1800fa941  mov     rdi, rdx
0x1800fa944  mov     rsi, rcx
0x1800fa947  test    rcx, rcx
0x1800fa94a  jnz     short loc_1800FA972
0x1800fa94c  lea     edx, [rcx+5Dh]; void *
0x1800fa94f  mov     ebx, 80070057h
0x1800fa954  mov     rcx, [rsp+258h]; this
0x1800fa95c  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fa963  mov     r9d, ebx; char *
0x1800fa966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa96b  mov     eax, ebx
0x1800fa96d  jmp     loc_1800FAA3B
0x1800fa972  test    rdi, rdi
0x1800fa975  jnz     short loc_1800FA97C
0x1800fa977  lea     edx, [rdi+5Eh]
0x1800fa97a  jmp     short loc_1800FA94F
0x1800fa97c  xor     edx, edx; Val
0x1800fa97e  lea     rcx, [rsp+258h+pszPath]; void *
0x1800fa983  mov     r8d, 208h; Size
0x1800fa989  call    memset_0
0x1800fa98e  xor     edx, edx
0x1800fa990  lea     r8, [rsp+258h+pszPath]
0x1800fa995  mov     ebp, 104h
0x1800fa99a  mov     r9d, ebp
0x1800fa99d  lea     ecx, [rdx+4]
0x1800fa9a0  call    cs:__imp_GetBasicProfileFolderPath
0x1800fa9a7  nop     dword ptr [rax+rax+00h]
0x1800fa9ac  mov     ebx, eax
0x1800fa9ae  test    eax, eax
0x1800fa9b0  jns     short loc_1800FA9B9
0x1800fa9b2  mov     edx, 61h ; 'a'
0x1800fa9b7  jmp     short loc_1800FA954
0x1800fa9b9  lea     r8, pszMore; "Microsoft\\DMClient"
0x1800fa9c0  mov     rdx, rbp; cchPath
0x1800fa9c3  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800fa9c8  call    cs:__imp_PathCchAppend
0x1800fa9cf  nop     dword ptr [rax+rax+00h]
0x1800fa9d4  mov     ebx, eax
0x1800fa9d6  test    eax, eax
0x1800fa9d8  jns     short loc_1800FA9E4
0x1800fa9da  mov     edx, 64h ; 'd'
0x1800fa9df  jmp     loc_1800FA954
0x1800fa9e4  mov     r8, rsi; pszMore
0x1800fa9e7  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800fa9ec  mov     rdx, rbp; cchPath
0x1800fa9ef  call    cs:__imp_PathCchAppend
0x1800fa9f6  nop     dword ptr [rax+rax+00h]
0x1800fa9fb  mov     ebx, eax
0x1800fa9fd  test    eax, eax
0x1800fa9ff  jns     short loc_1800FAA0B
0x1800faa01  mov     edx, 67h ; 'g'
0x1800faa06  jmp     loc_1800FA954
0x1800faa0b  mov     r9, rdi; ppszPathOut
0x1800faa0e  lea     rdx, aFirstsync; "FirstSync"
0x1800faa15  xor     r8d, r8d; dwFlags
0x1800faa18  lea     rcx, [rsp+258h+pszPath]; pszPathIn
0x1800faa1d  call    cs:__imp_PathAllocCombine
0x1800faa24  nop     dword ptr [rax+rax+00h]
0x1800faa29  mov     ebx, eax
0x1800faa2b  test    eax, eax
0x1800faa2d  jns     short loc_1800FAA39
0x1800faa2f  mov     edx, 69h ; 'i'
0x1800faa34  jmp     loc_1800FA954
0x1800faa39  xor     eax, eax
0x1800faa3b  mov     rcx, [rsp+258h+var_28]
0x1800faa43  xor     rcx, rsp; StackCookie
0x1800faa46  call    __security_check_cookie
0x1800faa4b  mov     rbx, [rsp+258h+arg_10]
0x1800faa53  add     rsp, 240h
0x1800faa5a  pop     rdi
0x1800faa5b  pop     rsi
0x1800faa5c  pop     rbp
0x1800faa5d  retn
```
