# AslEnvGetSysNativeDirPathForGuestBuf

- ea: `0x14073b188`
- end: `0x14073b2b7`
- name: `AslEnvGetSysNativeDirPathForGuestBuf`
- size: `303`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PWSTR pszDest@<rcx>, size_t cchDest@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1408267b0`

## callees

- `0x140438468`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x14073b188`
- `0x140829038`
- `0x140829334`
- `0x1408c2f88`
- `0x140b04ab4`

## string_xrefs

- `0x14073b25b`: `RtlStringCchCopyW failed [%x]`
- `0x14073b203`: `AslPathToSystemPathBuf failed [%x]`
- `0x14073b236`: `AslPathCombine failed [%x]`
- `0x14073b268`: `AslEnvGetSysNativeDirPathForGuestBuf`

## pseudocode

```c
__int64 __fastcall AslEnvGetSysNativeDirPathForGuestBuf(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        _WORD *a3,
        __int16 a4,
        __int16 *a5)
{
  NTSTATUS v9; // ebx
  const char *v10; // r9
  int v11; // r8d
  wchar_t pszSrc[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(pszSrc, 0, sizeof(pszSrc));
  *pszDest = 0;
  if ( a5 && *a5 != a4 )
  {
    v9 = AslPathToSystemPathBuf(pszSrc, 0x40u, L"\\SysNative");
    if ( v9 < 0 )
    {
      v10 = "AslPathToSystemPathBuf failed [%x]";
      v11 = 1847;
LABEL_11:
      AslLogCallPrintf(1, (unsigned int)"AslEnvGetSysNativeDirPathForGuestBuf", v11, (_DWORD)v10);
      return (unsigned int)v9;
    }
    if ( a3 && *a3 )
    {
      v9 = AslPathCombine(pszSrc, a3, pszDest, cchDest);
      if ( v9 < 0 )
      {
        v10 = "AslPathCombine failed [%x]";
        v11 = 1857;
        goto LABEL_11;
      }
    }
    else
    {
      v9 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
      if ( v9 < 0 )
      {
        v10 = "RtlStringCchCopyW failed [%x]";
        v11 = 1865;
        goto LABEL_11;
      }
    }
    return (unsigned int)v9;
  }
  return AslEnvGetSystem32DirPathBuf(pszDest, cchDest, a3, a4, a5);
}

```

## disassembly

```asm
0x14073b188  push    rbx
0x14073b18a  push    rbp
0x14073b18b  push    rsi
0x14073b18c  push    rdi
0x14073b18d  push    r14
0x14073b18f  sub     rsp, 0C0h
0x14073b196  mov     rax, cs:__security_cookie
0x14073b19d  xor     rax, rsp
0x14073b1a0  mov     [rsp+0E8h+var_38], rax
0x14073b1a8  mov     rdi, r8
0x14073b1ab  mov     rbp, rdx
0x14073b1ae  mov     rsi, rcx
0x14073b1b1  xor     edx, edx; Val
0x14073b1b3  mov     r8d, 80h; Size
0x14073b1b9  lea     rcx, [rsp+0E8h+pszSrc]; void *
0x14073b1be  movzx   ebx, r9w
0x14073b1c2  call    memset_0
0x14073b1c7  mov     rax, [rsp+0E8h+arg_20]
0x14073b1cf  xor     r14d, r14d
0x14073b1d2  mov     [rsi], r14w
0x14073b1d6  test    rax, rax
0x14073b1d9  jz      loc_14073B281
0x14073b1df  cmp     [rax], bx
0x14073b1e2  jz      loc_14073B281
0x14073b1e8  lea     r8, aSysnative; "\\SysNative"
0x14073b1ef  lea     edx, [r14+40h]; cchDest
0x14073b1f3  lea     rcx, [rsp+0E8h+pszSrc]; pszDest
0x14073b1f8  call    AslPathToSystemPathBuf
0x14073b1fd  mov     ebx, eax
0x14073b1ff  test    eax, eax
0x14073b201  jns     short loc_14073B212
0x14073b203  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x14073b20a  mov     r8d, 737h
0x14073b210  jmp     short loc_14073B268
0x14073b212  test    rdi, rdi
0x14073b215  jz      short loc_14073B245
0x14073b217  cmp     [rdi], r14w
0x14073b21b  jz      short loc_14073B245
0x14073b21d  mov     r9, rbp
0x14073b220  lea     rcx, [rsp+0E8h+pszSrc]
0x14073b225  mov     r8, rsi
0x14073b228  mov     rdx, rdi
0x14073b22b  call    AslPathCombine
0x14073b230  mov     ebx, eax
0x14073b232  test    eax, eax
0x14073b234  jns     short loc_14073B27D
0x14073b236  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14073b23d  mov     r8d, 741h
0x14073b243  jmp     short loc_14073B268
0x14073b245  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x14073b24a  mov     rdx, rbp; cchDest
0x14073b24d  mov     rcx, rsi; pszDest
0x14073b250  call    RtlStringCchCopyW
0x14073b255  mov     ebx, eax
0x14073b257  test    eax, eax
0x14073b259  jns     short loc_14073B27D
0x14073b25b  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14073b262  mov     r8d, 749h
0x14073b268  lea     rdx, aAslenvgetsysna; "AslEnvGetSysNativeDirPathForGuestBuf"
0x14073b26f  mov     dword ptr [rsp+0E8h+var_C8], eax
0x14073b273  mov     ecx, 1
0x14073b278  call    AslLogCallPrintf
0x14073b27d  mov     eax, ebx
0x14073b27f  jmp     short loc_14073B298
0x14073b281  movzx   r9d, bx
0x14073b285  mov     [rsp+0E8h+var_C8], rax; __int64
0x14073b28a  mov     r8, rdi
0x14073b28d  mov     rdx, rbp; cchDest
0x14073b290  mov     rcx, rsi; pszDest
0x14073b293  call    AslEnvGetSystem32DirPathBuf
0x14073b298  mov     rcx, [rsp+0E8h+var_38]
0x14073b2a0  xor     rcx, rsp; StackCookie
0x14073b2a3  call    __security_check_cookie
0x14073b2a8  add     rsp, 0C0h
0x14073b2af  pop     r14
0x14073b2b1  pop     rdi
0x14073b2b2  pop     rsi
0x14073b2b3  pop     rbp
0x14073b2b4  pop     rbx
0x14073b2b5  retn
```
