# SchemeHasCacheMetaData

- ea: `0x180019334`
- end: `0x1800193a8`
- name: `SchemeHasCacheMetaData`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005bd0`
- `0x180007cc0`

## callees

- `0x180003e7c`
- `0x180005900`
- `0x1800063b0`
- `0x18000a990`
- `0x180019334`

## pseudocode

```c
_BOOL8 __fastcall SchemeHasCacheMetaData(UCHAR *a1)
{
  HANDLE CacheFile; // rbx
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  unsigned __int16 *v4; // rsi
  BOOL v5; // edi

  CacheFile = 0;
  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  v4 = CryptnetUrlCacheDir;
  v5 = 0;
  if ( CryptnetUrlCacheDir )
  {
    CacheFile = I_UrlCacheCreateCacheFile(CryptnetUrlCacheDir, L"MetaData", 0, a1, 0);
    if ( CacheFile )
      v5 = 1;
  }
  operator delete(v4);
  if ( CacheFile )
    I_UrlCacheCloseHandle(CacheFile);
  return v5;
}

```

## disassembly

```asm
0x180019334  mov     [rsp+arg_0], rbx
0x180019339  mov     [rsp+arg_8], rsi
0x18001933e  push    rdi
0x18001933f  sub     rsp, 30h
0x180019343  mov     rdi, rcx
0x180019346  xor     ebx, ebx
0x180019348  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x18001934d  mov     rsi, rax
0x180019350  test    rax, rax
0x180019353  jnz     short loc_180019376
0x180019355  xor     edi, edi
0x180019357  mov     rcx, rsi; hMem
0x18001935a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001935f  test    rbx, rbx
0x180019362  jnz     short loc_18001939E
0x180019364  mov     rbx, [rsp+38h+arg_0]
0x180019369  mov     eax, edi
0x18001936b  mov     rsi, [rsp+38h+arg_8]
0x180019370  add     rsp, 30h
0x180019374  pop     rdi
0x180019375  retn
0x180019376  mov     r9, rdi
0x180019379  mov     [rsp+38h+var_18], ebx; int
0x18001937d  xor     r8d, r8d; void *
0x180019380  lea     rdx, aMetadata; "MetaData"
0x180019387  mov     rcx, rsi; Src
0x18001938a  call    I_UrlCacheCreateCacheFile
0x18001938f  mov     rbx, rax
0x180019392  test    rax, rax
0x180019395  jz      short loc_180019355
0x180019397  mov     edi, 1
0x18001939c  jmp     short loc_180019357
0x18001939e  mov     rcx, rbx; hObject
0x1800193a1  call    I_UrlCacheCloseHandle
0x1800193a6  jmp     short loc_180019364
```
