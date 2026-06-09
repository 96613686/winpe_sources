# SchemeUpdateCacheResponseInfo

- ea: `0x180001154`
- end: `0x1800012be`
- name: `SchemeUpdateCacheResponseInfo`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180001154`
- `0x180002ca8`
- `0x180003e7c`
- `0x180005900`
- `0x1800063b0`
- `0x1800077b0`
- `0x18000a990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000120f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000120f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000121a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000121a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001200`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001200`

## pseudocode

```c
__int64 __fastcall SchemeUpdateCacheResponseInfo(__int64 a1, __int64 a2, const FILETIME *a3, FILETIME *a4, __int64 a5)
{
  FILETIME *v5; // rbx
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  unsigned __int16 *v9; // r12
  void *v10; // r8
  __int64 v11; // rdi
  unsigned int v12; // r14d
  void *CacheFile; // rax
  void *v14; // rsi
  const FILETIME *v15; // rax
  struct _FILETIME *v16; // r15
  DWORD dwLowDateTime; // eax
  DWORD v18; // r8d
  struct _FILETIME *v19; // rcx
  DWORD nNumberOfBytesToWrite; // [rsp+88h] [rbp+10h] BYREF

  v5 = 0;
  nNumberOfBytesToWrite = 0;
  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  v9 = CryptnetUrlCacheDir;
  if ( !CryptnetUrlCacheDir )
  {
    v14 = 0;
    goto LABEL_21;
  }
  v10 = 0;
  v11 = a5;
  if ( a5 && *(_DWORD *)a5 > 0x30u && *(_QWORD *)(a5 + 48) )
    v10 = *(void **)(a5 + 48);
  v12 = 1;
  CacheFile = (void *)I_UrlCacheCreateCacheFile(CryptnetUrlCacheDir, L"MetaData", v10, 1);
  v14 = CacheFile;
  if ( !CacheFile )
    goto LABEL_21;
  v15 = (const FILETIME *)I_UrlCacheReadAndValidateMetaDataFile(CacheFile, 0, 0, &nNumberOfBytesToWrite, 0);
  v5 = (FILETIME *)v15;
  if ( !v15 )
    goto LABEL_21;
  v16 = (struct _FILETIME *)&v15[2];
  if ( CompareFileTime(v15 + 2, a3) )
  {
    SetLastError(0x456u);
LABEL_21:
    v12 = 0;
    goto LABEL_22;
  }
  GetSystemTimeAsFileTime(v16);
  dwLowDateTime = a4[2].dwLowDateTime;
  if ( dwLowDateTime )
    v5[12].dwLowDateTime = dwLowDateTime;
  if ( a4[1].dwLowDateTime || a4[1].dwHighDateTime )
    v5[11] = a4[1];
  v18 = nNumberOfBytesToWrite;
  *(_OWORD *)&v5[3].dwLowDateTime = 0;
  *(_OWORD *)&v5[5].dwLowDateTime = 0;
  v5[7] = 0;
  v5[3].dwLowDateTime = 40;
  if ( !(unsigned int)I_UrlCacheUpdateMetaData(v14, v5, v18) )
    goto LABEL_21;
  if ( v11 )
  {
    if ( *(_DWORD *)v11 > 8u )
    {
      v19 = *(struct _FILETIME **)(v11 + 8);
      if ( v19 )
        *v19 = *v16;
    }
  }
LABEL_22:
  operator delete(v9);
  operator delete(v5);
  if ( v14 )
    I_UrlCacheCloseHandle(v14);
  return v12;
}

```

## disassembly

```asm
0x180001154  mov     rax, rsp
0x180001157  mov     [rax+10h], edx
0x18000115a  push    rbx
0x18000115b  push    rbp
0x18000115c  push    rsi
0x18000115d  push    rdi
0x18000115e  push    r12
0x180001160  push    r13
0x180001162  push    r14
0x180001164  push    r15
0x180001166  sub     rsp, 38h
0x18000116a  xor     ebx, ebx
0x18000116c  mov     rbp, r9
0x18000116f  mov     [rax+10h], ebx
0x180001172  mov     r13, r8
0x180001175  mov     rsi, rcx
0x180001178  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x18000117d  mov     r12, rax
0x180001180  test    rax, rax
0x180001183  jz      loc_180001288
0x180001189  xor     r8d, r8d
0x18000118c  mov     rdi, [rsp+78h+arg_20]
0x180001194  test    rdi, rdi
0x180001197  jz      short loc_1800011A7
0x180001199  cmp     dword ptr [rdi], 30h ; '0'
0x18000119c  jbe     short loc_1800011A7
0x18000119e  cmp     [rdi+30h], rbx
0x1800011a2  cmovnz  r8, [rdi+30h]; void *
0x1800011a7  mov     r14d, 1
0x1800011ad  lea     rdx, aMetadata; "MetaData"
0x1800011b4  mov     r9, rsi
0x1800011b7  mov     dword ptr [rsp+78h+var_58], r14d; int
0x1800011bc  mov     rcx, r12; Src
0x1800011bf  call    I_UrlCacheCreateCacheFile
0x1800011c4  mov     rsi, rax
0x1800011c7  test    rax, rax
0x1800011ca  jz      loc_18000128A
0x1800011d0  lea     r9, [rsp+78h+nNumberOfBytesToWrite]
0x1800011d8  mov     [rsp+78h+var_58], rbx; __int64
0x1800011dd  xor     r8d, r8d
0x1800011e0  xor     edx, edx
0x1800011e2  mov     rcx, rax; hFile
0x1800011e5  call    I_UrlCacheReadAndValidateMetaDataFile
0x1800011ea  mov     rbx, rax
0x1800011ed  test    rax, rax
0x1800011f0  jz      loc_18000128A
0x1800011f6  lea     r15, [rax+10h]
0x1800011fa  mov     rdx, r13; lpFileTime2
0x1800011fd  mov     rcx, r15; lpFileTime1
0x180001200  call    cs:__imp_CompareFileTime
0x180001206  test    eax, eax
0x180001208  jz      short loc_180001217
0x18000120a  mov     ecx, 456h; dwErrCode
0x18000120f  call    cs:__imp_SetLastError
0x180001215  jmp     short loc_18000128A
0x180001217  mov     rcx, r15; lpSystemTimeAsFileTime
0x18000121a  call    cs:__imp_GetSystemTimeAsFileTime
0x180001220  mov     eax, [rbp+10h]
0x180001223  test    eax, eax
0x180001225  jz      short loc_18000122A
0x180001227  mov     [rbx+60h], eax
0x18000122a  cmp     dword ptr [rbp+8], 0
0x18000122e  jnz     short loc_180001236
0x180001230  cmp     dword ptr [rbp+0Ch], 0
0x180001234  jz      short loc_18000123E
0x180001236  mov     rax, [rbp+8]
0x18000123a  mov     [rbx+58h], rax
0x18000123e  mov     r8d, [rsp+78h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180001246  xorps   xmm0, xmm0
0x180001249  movups  xmmword ptr [rbx+18h], xmm0
0x18000124d  xor     eax, eax
0x18000124f  mov     rdx, rbx; lpBuffer
0x180001252  movups  xmmword ptr [rbx+28h], xmm0
0x180001256  mov     [rbx+38h], rax
0x18000125a  mov     rcx, rsi; hFile
0x18000125d  mov     dword ptr [rbx+18h], 28h ; '('
0x180001264  call    I_UrlCacheUpdateMetaData
0x180001269  test    eax, eax
0x18000126b  jz      short loc_18000128A
0x18000126d  test    rdi, rdi
0x180001270  jz      short loc_18000128D
0x180001272  cmp     dword ptr [rdi], 8
0x180001275  jbe     short loc_18000128D
0x180001277  mov     rcx, [rdi+8]
0x18000127b  test    rcx, rcx
0x18000127e  jz      short loc_18000128D
0x180001280  mov     rax, [r15]
0x180001283  mov     [rcx], rax
0x180001286  jmp     short loc_18000128D
0x180001288  xor     esi, esi
0x18000128a  xor     r14d, r14d
0x18000128d  mov     rcx, r12; hMem
0x180001290  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001295  mov     rcx, rbx; hMem
0x180001298  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000129d  test    rsi, rsi
0x1800012a0  jz      short loc_1800012AA
0x1800012a2  mov     rcx, rsi; hObject
0x1800012a5  call    I_UrlCacheCloseHandle
0x1800012aa  mov     eax, r14d
0x1800012ad  add     rsp, 38h
0x1800012b1  pop     r15
0x1800012b3  pop     r14
0x1800012b5  pop     r13
0x1800012b7  pop     r12
0x1800012b9  pop     rdi
0x1800012ba  pop     rsi
0x1800012bb  pop     rbp
0x1800012bc  pop     rbx
0x1800012bd  retn
```
