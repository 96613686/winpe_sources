# SchemeDeleteUrlCacheEntry

- ea: `0x18001ff84`
- end: `0x180020073`
- name: `SchemeDeleteUrlCacheEntry`
- size: `239`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e524`

## callees

- `0x180002810`
- `0x180002a90`
- `0x1800063b0`
- `0x18000a990`
- `0x18001ff84`
- `0x180026254`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020019`

## pseudocode

```c
__int64 __fastcall SchemeDeleteUrlCacheEntry(__int64 a1, void *a2)
{
  unsigned int v4; // esi
  unsigned __int16 *CryptnetUrlCacheDir; // rbp
  WCHAR *CacheFileName; // rdi
  const WCHAR *v7; // rax
  WCHAR *v8; // rbx
  _BYTE v10[80]; // [rsp+30h] [rbp-78h] BYREF

  v4 = 0;
  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  if ( CryptnetUrlCacheDir )
  {
    I_UrlCacheGetUrlFileName(a1, v10);
    CacheFileName = (WCHAR *)I_UrlCacheGetCacheFileName(CryptnetUrlCacheDir, L"MetaData", a2, 0);
    v7 = (const WCHAR *)I_UrlCacheGetCacheFileName(CryptnetUrlCacheDir, L"Content", a2, 0);
    v8 = (WCHAR *)v7;
    if ( CacheFileName && v7 && ((unsigned int)I_UrlCacheDeleteFile(v7) || GetLastError() == 2) )
      v4 = I_UrlCacheDeleteFile(CacheFileName);
  }
  else
  {
    CacheFileName = 0;
    v8 = 0;
  }
  operator delete(CryptnetUrlCacheDir);
  operator delete(CacheFileName);
  operator delete(v8);
  return v4;
}

```

## disassembly

```asm
0x18001ff84  mov     [rsp+arg_10], rbx
0x18001ff89  push    rbp
0x18001ff8a  push    rsi
0x18001ff8b  push    rdi
0x18001ff8c  sub     rsp, 90h
0x18001ff93  mov     rax, cs:__security_cookie
0x18001ff9a  xor     rax, rsp
0x18001ff9d  mov     [rsp+0A8h+var_28], rax
0x18001ffa5  mov     rbx, rdx
0x18001ffa8  mov     rdi, rcx
0x18001ffab  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x18001ffb0  xor     esi, esi
0x18001ffb2  mov     rbp, rax
0x18001ffb5  test    rax, rax
0x18001ffb8  jz      short loc_180020030
0x18001ffba  lea     rdx, [rsp+0A8h+var_78]
0x18001ffbf  mov     rcx, rdi
0x18001ffc2  call    I_UrlCacheGetUrlFileName
0x18001ffc7  lea     r9, [rsp+0A8h+var_78]
0x18001ffcc  mov     [rsp+0A8h+var_88], esi; int
0x18001ffd0  mov     r8, rbx; void *
0x18001ffd3  lea     rdx, aMetadata; "MetaData"
0x18001ffda  mov     rcx, rbp; Src
0x18001ffdd  call    I_UrlCacheGetCacheFileName
0x18001ffe2  lea     r9, [rsp+0A8h+var_78]
0x18001ffe7  mov     [rsp+0A8h+var_88], esi; int
0x18001ffeb  mov     r8, rbx; void *
0x18001ffee  lea     rdx, aContent; "Content"
0x18001fff5  mov     rcx, rbp; Src
0x18001fff8  mov     rdi, rax
0x18001fffb  call    I_UrlCacheGetCacheFileName
0x180020000  mov     rbx, rax
0x180020003  test    rdi, rdi
0x180020006  jz      short loc_180020036
0x180020008  test    rax, rax
0x18002000b  jz      short loc_180020036
0x18002000d  mov     rcx, rax; lpFileName
0x180020010  call    I_UrlCacheDeleteFile
0x180020015  test    eax, eax
0x180020017  jnz     short loc_180020024
0x180020019  call    cs:__imp_GetLastError
0x18002001f  cmp     eax, 2
0x180020022  jnz     short loc_180020036
0x180020024  mov     rcx, rdi; lpFileName
0x180020027  call    I_UrlCacheDeleteFile
0x18002002c  mov     esi, eax
0x18002002e  jmp     short loc_180020036
0x180020030  mov     rdi, rsi
0x180020033  mov     rbx, rsi
0x180020036  mov     rcx, rbp; hMem
0x180020039  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002003e  mov     rcx, rdi; hMem
0x180020041  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020046  mov     rcx, rbx; hMem
0x180020049  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002004e  mov     eax, esi
0x180020050  mov     rcx, [rsp+0A8h+var_28]
0x180020058  xor     rcx, rsp; StackCookie
0x18002005b  call    __security_check_cookie
0x180020060  mov     rbx, [rsp+0A8h+arg_10]
0x180020068  add     rsp, 90h
0x18002006f  pop     rdi
0x180020070  pop     rsi
0x180020071  pop     rbp
0x180020072  retn
```
