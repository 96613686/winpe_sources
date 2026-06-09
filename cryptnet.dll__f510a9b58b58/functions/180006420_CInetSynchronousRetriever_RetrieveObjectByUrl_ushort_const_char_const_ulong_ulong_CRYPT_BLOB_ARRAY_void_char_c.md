# CInetSynchronousRetriever::RetrieveObjectByUrl(ushort const *,char const *,ulong,ulong,_CRYPT_BLOB_ARRAY *,void (**)(char const *,_CRYPT_BLOB_ARRAY *,void *),void * *,void *,_CRYPT_CREDENTIALS *,_CRYPT_RETRIEVE_AUX_INFO *)

- ea: `0x180006420`
- end: `0x18000662e`
- name: `?RetrieveObjectByUrl@CInetSynchronousRetriever@@UEAAHPEBGPEBDKKPEAU_CRYPT_BLOB_ARRAY@@PEAP6AX12PEAX@ZPEAPEAX3PEAU_CRYPT_CREDENTIALS@@PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(CInetSynchronousRetriever *this, unsigned __int16 *, const char *, int, unsigned int, struct _CRYPT_BLOB_ARRAY *, void (**)(const char *, struct _CRYPT_BLOB_ARRAY *, void *), void **, void *, struct _CRYPT_CREDENTIALS *, struct _CRYPT_RETRIEVE_AUX_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x180006420`
- `0x180006640`
- `0x180006710`
- `0x180006d40`
- `0x180019220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006504`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006611`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006504`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000649f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000649f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065f9`
- `CRYPT32!I_CertDiagControl` at `0x1800064e6`
- `CRYPT32!I_CertDiagControl` at `0x1800064e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064fc`
- `WINHTTP!WinHttpCloseHandle` at `0x180006609`
- `WINHTTP!WinHttpCloseHandle` at `0x180006609`
- `WINHTTP!WinHttpSetOption` at `0x1800065a0`
- `WINHTTP!WinHttpSetOption` at `0x1800065a0`
- `WINHTTP!WinHttpOpen` at `0x18000656f`
- `WINHTTP!WinHttpOpen` at `0x18000656f`

## string_xrefs

- `0x1800064c2`: `ReadFromCache`
- `0x180006453`: `\Microsoft\CryptnetUrlCache\`
- `0x18000661e`: `Call_WinHttpOpen`

## pseudocode

```c
__int64 __fastcall CInetSynchronousRetriever::RetrieveObjectByUrl(
        CInetSynchronousRetriever *this,
        unsigned __int16 *a2,
        const char *a3,
        int a4,
        unsigned int a5,
        struct _CRYPT_BLOB_ARRAY *a6,
        void (**a7)(const char *, struct _CRYPT_BLOB_ARRAY *, void *),
        void **a8,
        void *a9,
        struct _CRYPT_CREDENTIALS *a10,
        struct _CRYPT_RETRIEVE_AUX_INFO *a11)
{
  void *v11; // rbp
  void *LowIntegrityUserPath; // rbx
  void *Token; // rax
  void *v16; // rsi
  DWORD v17; // edi
  __int64 CryptBlobArray; // rax
  DWORD LastError; // eax
  DWORD v20; // edi
  struct _CRYPT_BLOB_ARRAY *v22; // rdx
  void *v23; // rax
  void *v24; // rsi
  DWORD v25; // edi
  unsigned int v26; // ebx
  const wchar_t *v27; // [rsp+40h] [rbp-48h] BYREF
  DWORD v28; // [rsp+48h] [rbp-40h]
  int v29; // [rsp+4Ch] [rbp-3Ch]
  __int128 v30; // [rsp+50h] [rbp-38h]
  __int128 v31; // [rsp+60h] [rbp-28h]
  int Buffer; // [rsp+A8h] [rbp+20h] BYREF

  v11 = 0;
  if ( (a4 & 2) != 0 )
  {
    LowIntegrityUserPath = 0;
    Token = I_SchemeGetToken();
    v16 = Token;
    if ( Token
      && (LowIntegrityUserPath = (void *)I_CryptGetLowIntegrityUserPath(Token, L"\\Microsoft\\CryptnetUrlCache\\"),
          v17 = GetLastError(),
          CloseHandle(v16),
          SetLastError(v17),
          LowIntegrityUserPath)
      && (CryptBlobArray = I_UrlCacheReadCryptBlobArray(LowIntegrityUserPath)) != 0 )
    {
      LODWORD(v11) = 1;
      v22 = a6;
      a6->cBlob = *(_DWORD *)CryptBlobArray;
      v22->rgBlob = *(PCRYPT_DATA_BLOB *)(CryptBlobArray + 8);
      *a7 = (void (*)(const char *, struct _CRYPT_BLOB_ARRAY *, void *))&SchemeFreeEncodedCryptBlobArray;
      *a8 = (void *)CryptBlobArray;
    }
    else
    {
      LastError = GetLastError();
      v29 = 3;
      if ( !LastError )
        LastError = -2147418113;
      v27 = L"ReadFromCache";
      v28 = LastError;
      v30 = 0;
      v31 = 0;
      I_CertDiagControl(11, &v27, 0);
      if ( !LowIntegrityUserPath )
        return (unsigned int)v11;
    }
    v20 = GetLastError();
    LocalFree(LowIntegrityUserPath);
    SetLastError(v20);
    return (unsigned int)v11;
  }
  v23 = WinHttpOpen(L"Microsoft-CryptoAPI/10.0", 4u, 0, 0, 0);
  v24 = v23;
  if ( v23 )
  {
    Buffer = 0;
    v25 = 0;
    WinHttpSetOption(v23, 0x53u, &Buffer, 4u);
    v11 = v24;
    v26 = InetSendReceiveUrlRequest(v24, a2, a4, (__int64)a10, a6, a7, a8, a11);
    if ( v26 )
    {
LABEL_14:
      WinHttpCloseHandle(v11);
      goto LABEL_15;
    }
  }
  else
  {
    CryptDiagAddActionWithWinHttpLastError(L"Call_WinHttpOpen");
    v26 = 0;
  }
  v25 = GetLastError();
  if ( v11 )
    goto LABEL_14;
LABEL_15:
  SetLastError(v25);
  return v26;
}

```

## disassembly

```asm
0x180006420  mov     [rsp+arg_0], rbx
0x180006425  mov     [rsp+arg_8], rbp
0x18000642a  push    rsi
0x18000642b  push    rdi
0x18000642c  push    r14
0x18000642e  sub     rsp, 70h
0x180006432  xor     ebp, ebp
0x180006434  mov     ebx, r9d
0x180006437  mov     r14, rdx
0x18000643a  test    r9b, 2
0x18000643e  jz      loc_180006559
0x180006444  mov     ebx, ebp
0x180006446  call    ?I_SchemeGetToken@@YAPEAXXZ; I_SchemeGetToken(void)
0x18000644b  mov     rsi, rax
0x18000644e  test    rax, rax
0x180006451  jz      short loc_18000649F
0x180006453  lea     rdx, aMicrosoftCrypt_0; "\\Microsoft\\CryptnetUrlCache\\"
0x18000645a  mov     rcx, rax
0x18000645d  call    I_CryptGetLowIntegrityUserPath
0x180006462  mov     rbx, rax
0x180006465  call    cs:__imp_GetLastError
0x18000646b  mov     rcx, rsi; hObject
0x18000646e  mov     edi, eax
0x180006470  call    cs:__imp_CloseHandle
0x180006476  mov     ecx, edi; dwErrCode
0x180006478  call    cs:__imp_SetLastError
0x18000647e  test    rbx, rbx
0x180006481  jz      short loc_18000649F
0x180006483  mov     r9, [rsp+88h+arg_50]
0x18000648b  mov     r8, r14
0x18000648e  mov     rcx, rbx; Src
0x180006491  call    I_UrlCacheReadCryptBlobArray
0x180006496  test    rax, rax
0x180006499  jnz     loc_180006521
0x18000649f  call    cs:__imp_GetLastError
0x1800064a5  mov     ecx, 8000FFFFh
0x1800064aa  mov     [rsp+88h+var_3C], 3
0x1800064b2  test    eax, eax
0x1800064b4  lea     rdx, [rsp+88h+var_48]
0x1800064b9  xorps   xmm0, xmm0
0x1800064bc  xorps   xmm1, xmm1
0x1800064bf  cmovz   eax, ecx
0x1800064c2  lea     rcx, aReadfromcache; "ReadFromCache"
0x1800064c9  mov     [rsp+88h+var_48], rcx
0x1800064ce  xor     r8d, r8d
0x1800064d1  mov     ecx, 0Bh
0x1800064d6  mov     [rsp+88h+var_40], eax
0x1800064da  movdqu  [rsp+88h+var_38], xmm0
0x1800064e0  movdqu  [rsp+88h+var_28], xmm1
0x1800064e6  call    cs:__imp_I_CertDiagControl
0x1800064ec  test    rbx, rbx
0x1800064ef  jz      short loc_18000650A
0x1800064f1  call    cs:__imp_GetLastError
0x1800064f7  mov     rcx, rbx; hMem
0x1800064fa  mov     edi, eax
0x1800064fc  call    cs:__imp_LocalFree
0x180006502  mov     ecx, edi; dwErrCode
0x180006504  call    cs:__imp_SetLastError
0x18000650a  mov     eax, ebp
0x18000650c  lea     r11, [rsp+88h+var_18]
0x180006511  mov     rbx, [r11+20h]
0x180006515  mov     rbp, [r11+28h]
0x180006519  mov     rsp, r11
0x18000651c  pop     r14
0x18000651e  pop     rdi
0x18000651f  pop     rsi
0x180006520  retn
0x180006521  mov     ecx, [rax]
0x180006523  mov     ebp, 1
0x180006528  mov     rdx, [rsp+88h+arg_28]
0x180006530  mov     [rdx], ecx
0x180006532  mov     rcx, [rax+8]
0x180006536  mov     [rdx+8], rcx
0x18000653a  lea     rdx, SchemeFreeEncodedCryptBlobArray
0x180006541  mov     rcx, [rsp+88h+arg_30]
0x180006549  mov     [rcx], rdx
0x18000654c  mov     rcx, [rsp+88h+arg_38]
0x180006554  mov     [rcx], rax
0x180006557  jmp     short loc_1800064F1
0x180006559  xor     r9d, r9d; pszProxyBypassW
0x18000655c  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x180006560  xor     r8d, r8d; pszProxyW
0x180006563  lea     rcx, pszAgentW; "Microsoft-CryptoAPI/10.0"
0x18000656a  mov     edx, 4; dwAccessType
0x18000656f  call    cs:__imp_WinHttpOpen
0x180006575  mov     rsi, rax
0x180006578  test    rax, rax
0x18000657b  jz      loc_18000661E
0x180006581  mov     r9d, 4; dwBufferLength
0x180006587  mov     [rsp+88h+Buffer], ebp
0x18000658e  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x180006596  mov     edx, 53h ; 'S'; dwOption
0x18000659b  mov     rcx, rax; hInternet
0x18000659e  mov     edi, ebp
0x1800065a0  call    cs:__imp_WinHttpSetOption
0x1800065a6  mov     rax, [rsp+88h+arg_50]
0x1800065ae  mov     r8d, ebx
0x1800065b1  mov     r9, [rsp+88h+arg_48]
0x1800065b9  mov     rdx, r14
0x1800065bc  mov     [rsp+88h+var_50], rax
0x1800065c1  mov     rcx, rsi
0x1800065c4  mov     rax, [rsp+88h+arg_38]
0x1800065cc  mov     rbp, rsi
0x1800065cf  mov     [rsp+88h+var_58], rax
0x1800065d4  mov     rax, [rsp+88h+arg_30]
0x1800065dc  mov     [rsp+88h+var_60], rax
0x1800065e1  mov     rax, [rsp+88h+arg_28]
0x1800065e9  mov     qword ptr [rsp+88h+dwFlags], rax
0x1800065ee  call    InetSendReceiveUrlRequest
0x1800065f3  mov     ebx, eax
0x1800065f5  test    eax, eax
0x1800065f7  jnz     short loc_180006606
0x1800065f9  call    cs:__imp_GetLastError
0x1800065ff  mov     edi, eax
0x180006601  test    rbp, rbp
0x180006604  jz      short loc_18000660F
0x180006606  mov     rcx, rbp; hInternet
0x180006609  call    cs:__imp_WinHttpCloseHandle
0x18000660f  mov     ecx, edi; dwErrCode
0x180006611  call    cs:__imp_SetLastError
0x180006617  mov     eax, ebx
0x180006619  jmp     loc_18000650C
0x18000661e  lea     rcx, aCallWinhttpope; "Call_WinHttpOpen"
0x180006625  call    CryptDiagAddActionWithWinHttpLastError
0x18000662a  mov     ebx, ebp
0x18000662c  jmp     short loc_1800065F9
```
