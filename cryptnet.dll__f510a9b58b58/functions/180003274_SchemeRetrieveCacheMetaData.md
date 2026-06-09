# SchemeRetrieveCacheMetaData

- ea: `0x180003274`
- end: `0x18000330c`
- name: `SchemeRetrieveCacheMetaData`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001dde0`
- `0x18001f26c`

## callees

- `0x180003274`
- `0x180003e7c`
- `0x180005900`
- `0x1800063b0`
- `0x1800077b0`
- `0x18000a990`

## pseudocode

```c
_DWORD *__fastcall SchemeRetrieveCacheMetaData(UCHAR *a1, _QWORD *a2, __int64 a3)
{
  _DWORD *v6; // rsi
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  unsigned __int16 *v8; // rdi
  _WORD *v9; // r8
  HANDLE CacheFile; // rax
  void *v11; // rbx

  v6 = 0;
  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  v8 = CryptnetUrlCacheDir;
  if ( CryptnetUrlCacheDir )
  {
    v9 = 0;
    if ( a3 && *(_DWORD *)a3 > 0x30u && *(_QWORD *)(a3 + 48) )
      v9 = *(_WORD **)(a3 + 48);
    CacheFile = I_UrlCacheCreateCacheFile(CryptnetUrlCacheDir, L"MetaData", v9, a1, 0);
    v11 = CacheFile;
    if ( CacheFile )
      v6 = I_UrlCacheReadAndValidateMetaDataFile(CacheFile, 0, 0, 0, a2);
  }
  else
  {
    v11 = 0;
  }
  operator delete(v8);
  if ( v11 )
    I_UrlCacheCloseHandle(v11);
  return v6;
}

```

## disassembly

```asm
0x180003274  push    rbx
0x180003276  push    rbp
0x180003277  push    rsi
0x180003278  push    rdi
0x180003279  push    r14
0x18000327b  sub     rsp, 30h
0x18000327f  mov     rbx, r8
0x180003282  mov     rbp, rdx
0x180003285  mov     r14, rcx
0x180003288  xor     esi, esi
0x18000328a  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x18000328f  mov     rdi, rax
0x180003292  test    rax, rax
0x180003295  jz      short loc_1800032FD
0x180003297  xor     r8d, r8d; void *
0x18000329a  test    rbx, rbx
0x18000329d  jz      short loc_1800032A4
0x18000329f  cmp     dword ptr [rbx], 30h ; '0'
0x1800032a2  ja      short loc_180003301
0x1800032a4  mov     r9, r14
0x1800032a7  mov     dword ptr [rsp+58h+var_38], esi; int
0x1800032ab  lea     rdx, aMetadata; "MetaData"
0x1800032b2  mov     rcx, rdi; Src
0x1800032b5  call    I_UrlCacheCreateCacheFile
0x1800032ba  mov     rbx, rax
0x1800032bd  test    rax, rax
0x1800032c0  jz      short loc_1800032DA
0x1800032c2  xor     r9d, r9d
0x1800032c5  mov     [rsp+58h+var_38], rbp; __int64
0x1800032ca  xor     r8d, r8d
0x1800032cd  xor     edx, edx
0x1800032cf  mov     rcx, rax; hFile
0x1800032d2  call    I_UrlCacheReadAndValidateMetaDataFile
0x1800032d7  mov     rsi, rax
0x1800032da  mov     rcx, rdi; hMem
0x1800032dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800032e2  test    rbx, rbx
0x1800032e5  jz      short loc_1800032EF
0x1800032e7  mov     rcx, rbx; hObject
0x1800032ea  call    I_UrlCacheCloseHandle
0x1800032ef  mov     rax, rsi
0x1800032f2  add     rsp, 30h
0x1800032f6  pop     r14
0x1800032f8  pop     rdi
0x1800032f9  pop     rsi
0x1800032fa  pop     rbp
0x1800032fb  pop     rbx
0x1800032fc  retn
0x1800032fd  xor     ebx, ebx
0x1800032ff  jmp     short loc_1800032DA
0x180003301  cmp     [rbx+30h], rsi
0x180003305  cmovnz  r8, [rbx+30h]
0x18000330a  jmp     short loc_1800032A4
```
