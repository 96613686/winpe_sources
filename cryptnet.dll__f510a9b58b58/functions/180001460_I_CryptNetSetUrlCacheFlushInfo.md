# I_CryptNetSetUrlCacheFlushInfo

- ea: `0x180001460`
- end: `0x1800015b4`
- name: `I_CryptNetSetUrlCacheFlushInfo`
- size: `340`
- prototype: `__int64 __fastcall(__int64, const FILETIME *, unsigned __int16 *, _DWORD *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000cfa0`

## callees

- `0x180001460`
- `0x180002c40`
- `0x180002ca8`
- `0x180003e7c`
- `0x180005900`
- `0x1800063b0`
- `0x1800077b0`
- `0x18000a990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000153a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000153a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000159f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000159f`

## pseudocode

```c
__int64 __fastcall I_CryptNetSetUrlCacheFlushInfo(
        __int64 a1,
        const FILETIME *a2,
        unsigned __int16 *a3,
        _DWORD *a4,
        void *a5)
{
  FILETIME *v5; // rbx
  void *v6; // rdi
  unsigned __int16 *v7; // rsi
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  unsigned int v11; // ebp
  void *CacheFile; // rax
  const FILETIME *v13; // rax
  FILETIME v14; // r14
  DWORD v15; // ecx

  v5 = 0;
  v6 = 0;
  v7 = 0;
  CryptnetUrlCacheDir = a3;
  if ( *a4 != 16 )
  {
    v15 = 87;
LABEL_13:
    SetLastError(v15);
LABEL_14:
    v11 = 0;
    goto LABEL_15;
  }
  if ( !a3 )
  {
    CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
    v7 = CryptnetUrlCacheDir;
    if ( !CryptnetUrlCacheDir )
      goto LABEL_14;
  }
  v11 = 1;
  CacheFile = (void *)I_UrlCacheCreateCacheFile(CryptnetUrlCacheDir, L"MetaData", a5, 1);
  v6 = CacheFile;
  if ( !CacheFile )
    goto LABEL_14;
  v13 = (const FILETIME *)I_UrlCacheReadAndValidateMetaDataFile(CacheFile, 0);
  v5 = (FILETIME *)v13;
  if ( !v13 )
    goto LABEL_14;
  if ( a2 && CompareFileTime(v13 + 2, a2) )
  {
    v15 = 1110;
    goto LABEL_13;
  }
  v14 = v5[9];
  I_UrlCacheCopyCbSizeStruct(a4, &v5[8]);
  if ( !v5[9].dwLowDateTime && !v5[9].dwHighDateTime )
    v5[9] = v14;
  if ( v5[8].dwHighDateTime == -1 && LOWORD(v5[10].dwHighDateTime) )
    HIWORD(v5[10].dwHighDateTime) |= 0x8000u;
  if ( !(unsigned int)I_UrlCacheUpdateMetaData(v6, v5, 0) )
    goto LABEL_14;
LABEL_15:
  operator delete(v7);
  operator delete(v5);
  if ( v6 )
    I_UrlCacheCloseHandle(v6);
  return v11;
}

```

## disassembly

```asm
0x180001460  mov     [rsp+arg_0], rbx
0x180001465  mov     [rsp+arg_8], rbp
0x18000146a  push    rsi
0x18000146b  push    rdi
0x18000146c  push    r12
0x18000146e  push    r14
0x180001470  push    r15
0x180001472  sub     rsp, 30h
0x180001476  xor     ebx, ebx
0x180001478  xor     edi, edi
0x18000147a  xor     esi, esi
0x18000147c  mov     [rsp+58h+nNumberOfBytesToWrite], ebx
0x180001480  cmp     dword ptr [r9], 10h
0x180001484  mov     r15, r9
0x180001487  mov     rax, r8
0x18000148a  mov     r14, rdx
0x18000148d  mov     r12, rcx
0x180001490  jnz     loc_180001535
0x180001496  test    rax, rax
0x180001499  jz      loc_180001586
0x18000149f  mov     r8, [rsp+58h+arg_20]; void *
0x1800014a7  lea     rdx, aMetadata; "MetaData"
0x1800014ae  mov     ebp, 1
0x1800014b3  mov     r9, r12
0x1800014b6  mov     rcx, rax; Src
0x1800014b9  mov     dword ptr [rsp+58h+var_38], ebp; int
0x1800014bd  call    I_UrlCacheCreateCacheFile
0x1800014c2  mov     rdi, rax
0x1800014c5  test    rax, rax
0x1800014c8  jz      short loc_180001540
0x1800014ca  lea     r9, [rsp+58h+nNumberOfBytesToWrite]
0x1800014cf  mov     [rsp+58h+var_38], rbx; __int64
0x1800014d4  xor     r8d, r8d
0x1800014d7  xor     edx, edx
0x1800014d9  mov     rcx, rax; hFile
0x1800014dc  call    I_UrlCacheReadAndValidateMetaDataFile
0x1800014e1  mov     rbx, rax
0x1800014e4  test    rax, rax
0x1800014e7  jz      short loc_180001540
0x1800014e9  test    r14, r14
0x1800014ec  jnz     loc_180001598
0x1800014f2  lea     rdx, [rbx+40h]
0x1800014f6  mov     rcx, r15
0x1800014f9  mov     r14, [rdx+8]
0x1800014fd  call    I_UrlCacheCopyCbSizeStruct
0x180001502  cmp     dword ptr [rbx+48h], 0
0x180001506  jz      short loc_18000157A
0x180001508  cmp     dword ptr [rbx+44h], 0FFFFFFFFh
0x18000150c  jnz     short loc_18000151F
0x18000150e  xor     eax, eax
0x180001510  cmp     ax, [rbx+54h]
0x180001514  jz      short loc_18000151F
0x180001516  mov     eax, 8000h
0x18000151b  or      [rbx+56h], ax
0x18000151f  mov     r8d, [rsp+58h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180001524  mov     rdx, rbx; lpBuffer
0x180001527  mov     rcx, rdi; hFile
0x18000152a  call    I_UrlCacheUpdateMetaData
0x18000152f  test    eax, eax
0x180001531  jz      short loc_180001540
0x180001533  jmp     short loc_180001542
0x180001535  mov     ecx, 57h ; 'W'; dwErrCode
0x18000153a  call    cs:__imp_SetLastError
0x180001540  xor     ebp, ebp
0x180001542  mov     rcx, rsi; hMem
0x180001545  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000154a  mov     rcx, rbx; hMem
0x18000154d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001552  test    rdi, rdi
0x180001555  jnz     short loc_180001570
0x180001557  mov     rbx, [rsp+58h+arg_0]
0x18000155c  mov     eax, ebp
0x18000155e  mov     rbp, [rsp+58h+arg_8]
0x180001563  add     rsp, 30h
0x180001567  pop     r15
0x180001569  pop     r14
0x18000156b  pop     r12
0x18000156d  pop     rdi
0x18000156e  pop     rsi
0x18000156f  retn
0x180001570  mov     rcx, rdi; hObject
0x180001573  call    I_UrlCacheCloseHandle
0x180001578  jmp     short loc_180001557
0x18000157a  cmp     dword ptr [rbx+4Ch], 0
0x18000157e  jnz     short loc_180001508
0x180001580  mov     [rbx+48h], r14
0x180001584  jmp     short loc_180001508
0x180001586  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x18000158b  mov     rsi, rax
0x18000158e  test    rax, rax
0x180001591  jz      short loc_180001540
0x180001593  jmp     loc_18000149F
0x180001598  lea     rcx, [rax+10h]; lpFileTime1
0x18000159c  mov     rdx, r14; lpFileTime2
0x18000159f  call    cs:__imp_CompareFileTime
0x1800015a5  test    eax, eax
0x1800015a7  jz      loc_1800014F2
0x1800015ad  mov     ecx, 456h
0x1800015b2  jmp     short loc_18000153A
```
