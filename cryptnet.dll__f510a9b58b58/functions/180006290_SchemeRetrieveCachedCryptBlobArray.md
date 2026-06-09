# SchemeRetrieveCachedCryptBlobArray

- ea: `0x180006290`
- end: `0x1800063a2`
- name: `SchemeRetrieveCachedCryptBlobArray`
- size: `274`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`
- `0x1800196e0`
- `0x18001a250`

## callees

- `0x180006290`
- `0x180006640`
- `0x180006710`
- `0x180006d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006364`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006351`
- `CRYPT32!I_CertDiagControl` at `0x180006344`
- `CRYPT32!I_CertDiagControl` at `0x180006344`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000635c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000635c`

## string_xrefs

- `0x180006320`: `ReadFromCache`
- `0x1800062b5`: `\Microsoft\CryptnetUrlCache\`

## pseudocode

```c
__int64 __fastcall SchemeRetrieveCachedCryptBlobArray(
        UCHAR *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6)
{
  _WORD *LowIntegrityUserPath; // rbx
  void *Token; // rax
  void *v11; // rsi
  DWORD LastError; // edi
  __int64 v13; // rdx
  _QWORD *CryptBlobArray; // rax
  DWORD v15; // eax
  unsigned int v16; // esi
  DWORD v17; // edi
  const wchar_t *v19; // [rsp+20h] [rbp-68h] BYREF
  DWORD v20; // [rsp+28h] [rbp-60h]
  int v21; // [rsp+2Ch] [rbp-5Ch]
  __int128 v22; // [rsp+30h] [rbp-58h]
  __int128 v23; // [rsp+40h] [rbp-48h]

  LowIntegrityUserPath = 0;
  Token = I_SchemeGetToken();
  v11 = Token;
  if ( Token )
  {
    LowIntegrityUserPath = (_WORD *)I_CryptGetLowIntegrityUserPath(Token, L"\\Microsoft\\CryptnetUrlCache\\");
    LastError = GetLastError();
    CloseHandle(v11);
    SetLastError(LastError);
    if ( LowIntegrityUserPath )
    {
      CryptBlobArray = I_UrlCacheReadCryptBlobArray(LowIntegrityUserPath, v13, a1, a6);
      if ( CryptBlobArray )
      {
        v16 = 1;
        *(_DWORD *)a3 = *(_DWORD *)CryptBlobArray;
        *(_QWORD *)(a3 + 8) = CryptBlobArray[1];
        *a4 = &SchemeFreeEncodedCryptBlobArray;
        *a5 = CryptBlobArray;
LABEL_7:
        v17 = GetLastError();
        LocalFree(LowIntegrityUserPath);
        SetLastError(v17);
        return v16;
      }
    }
  }
  v15 = GetLastError();
  v21 = 3;
  if ( !v15 )
    v15 = -2147418113;
  v19 = L"ReadFromCache";
  v20 = v15;
  v22 = 0;
  v23 = 0;
  I_CertDiagControl(11, &v19, 0);
  v16 = 0;
  if ( LowIntegrityUserPath )
    goto LABEL_7;
  return v16;
}

```

## disassembly

```asm
0x180006290  push    rbx
0x180006292  push    rbp
0x180006293  push    rsi
0x180006294  push    rdi
0x180006295  push    r14
0x180006297  push    r15
0x180006299  sub     rsp, 58h
0x18000629d  mov     r15, r9
0x1800062a0  mov     r14, r8
0x1800062a3  mov     rbp, rcx
0x1800062a6  xor     ebx, ebx
0x1800062a8  call    ?I_SchemeGetToken@@YAPEAXXZ; I_SchemeGetToken(void)
0x1800062ad  mov     rsi, rax
0x1800062b0  test    rax, rax
0x1800062b3  jz      short loc_1800062FD
0x1800062b5  lea     rdx, aMicrosoftCrypt_0; "\\Microsoft\\CryptnetUrlCache\\"
0x1800062bc  mov     rcx, rax
0x1800062bf  call    I_CryptGetLowIntegrityUserPath
0x1800062c4  mov     rbx, rax
0x1800062c7  call    cs:__imp_GetLastError
0x1800062cd  mov     rcx, rsi; hObject
0x1800062d0  mov     edi, eax
0x1800062d2  call    cs:__imp_CloseHandle
0x1800062d8  mov     ecx, edi; dwErrCode
0x1800062da  call    cs:__imp_SetLastError
0x1800062e0  test    rbx, rbx
0x1800062e3  jz      short loc_1800062FD
0x1800062e5  mov     r9, [rsp+88h+arg_28]
0x1800062ed  mov     r8, rbp
0x1800062f0  mov     rcx, rbx; Src
0x1800062f3  call    I_UrlCacheReadCryptBlobArray
0x1800062f8  test    rax, rax
0x1800062fb  jnz     short loc_180006379
0x1800062fd  call    cs:__imp_GetLastError
0x180006303  mov     ecx, 8000FFFFh
0x180006308  mov     [rsp+88h+var_5C], 3
0x180006310  test    eax, eax
0x180006312  lea     rdx, [rsp+88h+var_68]
0x180006317  xorps   xmm0, xmm0
0x18000631a  xorps   xmm1, xmm1
0x18000631d  cmovz   eax, ecx
0x180006320  lea     rcx, aReadfromcache; "ReadFromCache"
0x180006327  mov     [rsp+88h+var_68], rcx
0x18000632c  xor     r8d, r8d
0x18000632f  mov     ecx, 0Bh
0x180006334  mov     [rsp+88h+var_60], eax
0x180006338  movdqu  [rsp+88h+var_58], xmm0
0x18000633e  movdqu  [rsp+88h+var_48], xmm1
0x180006344  call    cs:__imp_I_CertDiagControl
0x18000634a  xor     esi, esi
0x18000634c  test    rbx, rbx
0x18000634f  jz      short loc_18000636A
0x180006351  call    cs:__imp_GetLastError
0x180006357  mov     rcx, rbx; hMem
0x18000635a  mov     edi, eax
0x18000635c  call    cs:__imp_LocalFree
0x180006362  mov     ecx, edi; dwErrCode
0x180006364  call    cs:__imp_SetLastError
0x18000636a  mov     eax, esi
0x18000636c  add     rsp, 58h
0x180006370  pop     r15
0x180006372  pop     r14
0x180006374  pop     rdi
0x180006375  pop     rsi
0x180006376  pop     rbp
0x180006377  pop     rbx
0x180006378  retn
0x180006379  mov     ecx, [rax]
0x18000637b  mov     esi, 1
0x180006380  mov     [r14], ecx
0x180006383  mov     rcx, [rax+8]
0x180006387  mov     [r14+8], rcx
0x18000638b  lea     rcx, SchemeFreeEncodedCryptBlobArray
0x180006392  mov     [r15], rcx
0x180006395  mov     rcx, [rsp+88h+arg_20]
0x18000639d  mov     [rcx], rax
0x1800063a0  jmp     short loc_180006351
```
