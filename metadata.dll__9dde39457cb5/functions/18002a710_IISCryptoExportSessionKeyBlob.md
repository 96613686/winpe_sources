# IISCryptoExportSessionKeyBlob

- ea: `0x18002a710`
- end: `0x18002a9ba`
- name: `IISCryptoExportSessionKeyBlob`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18002a2b4`

## callees

- `0x18002937c`
- `0x180029aa4`
- `0x180029bc8`
- `0x180029c24`
- `0x180029c90`
- `0x180029e24`
- `0x18002a710`

## import_xrefs

- `ADVAPI32!CryptExportKey` at `0x18002a79c`
- `ADVAPI32!CryptExportKey` at `0x18002a847`
- `ADVAPI32!CryptExportKey` at `0x18002a79c`
- `ADVAPI32!CryptExportKey` at `0x18002a847`
- `ADVAPI32!CryptSignHashA` at `0x18002a92f`
- `ADVAPI32!CryptSignHashA` at `0x18002a92f`
- `ADVAPI32!CryptHashData` at `0x18002a8cd`
- `ADVAPI32!CryptHashData` at `0x18002a8cd`
- `ole32!CoTaskMemFree` at `0x18002a990`
- `ole32!CoTaskMemFree` at `0x18002a990`
- `IisRTL!PuDbgPrint` at `0x18002a974`
- `IisRTL!PuDbgPrint` at `0x18002a974`

## string_xrefs

- `0x18002a7c4`: `IISCryptoExportSessionKeyBlob.CryptExportKey (advapi32.dll) failed err=0x%x.\n`
- `0x18002a8a4`: `IISCryptoExportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoExportSessionKeyBlob(struct _IC_BLOB **a1, unsigned __int64 a2, HCRYPTKEY a3, HCRYPTKEY a4)
{
  __int64 result; // rax
  struct _IC_BLOB *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int HashLength; // eax
  struct _IC_BLOB *Blob; // rax
  const BYTE *v14; // r13
  unsigned int v15; // eax
  int Hash; // eax
  unsigned int v17; // eax
  unsigned int LastError; // eax
  DWORD *pdwDataLen; // [rsp+28h] [rbp-20h]
  DWORD *pdwDataLena; // [rsp+28h] [rbp-20h]
  DWORD *pdwDataLenb; // [rsp+28h] [rbp-20h]
  DWORD dwDataLen; // [rsp+30h] [rbp-18h] BYREF
  DWORD pdwSigLen; // [rsp+34h] [rbp-14h] BYREF
  HCRYPTHASH hHash[2]; // [rsp+38h] [rbp-10h] BYREF

  dwDataLen = 0;
  pdwSigLen = 0;
  if ( dword_180048964 )
  {
    hHash[0] = 0;
    v9 = 0;
    if ( CryptExportKey(a3, a4, 1u, 0, 0, &dwDataLen) )
    {
      HashLength = IcpGetHashLength(&pdwSigLen, a2);
      v11 = HashLength;
      if ( HashLength >= 0 )
      {
        Blob = IcpCreateBlob(0x624B6349u, dwDataLen, pdwSigLen);
        v9 = Blob;
        if ( Blob )
        {
          v14 = (const BYTE *)Blob + 16;
          if ( CryptExportKey(a3, a4, 1u, 0, (BYTE *)Blob + 16, &dwDataLen) )
          {
            Hash = IISCryptoCreateHash(hHash, a2);
            v11 = Hash;
            if ( Hash >= 0 )
            {
              if ( !hHash[0] )
              {
                v11 = -2147467259;
LABEL_32:
                CoTaskMemFree(v9);
                return v11;
              }
              if ( CryptHashData(hHash[0], v14, dwDataLen, 0) )
              {
                if ( CryptSignHashA(
                       hHash[0],
                       2u,
                       0,
                       0,
                       (BYTE *)v9 + ((*((_DWORD *)v9 + 2) + 7) & 0xFFFFFFF8) + 16,
                       &pdwSigLen) )
                {
                  IISCryptoDestroyHash(hHash[0]);
                  result = 0;
                  *a1 = v9;
                  return result;
                }
                LastError = IcpGetLastError();
                v11 = LastError;
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  LODWORD(pdwDataLenb) = LastError;
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\crypto\\key.cxx",
                    604,
                    "IISCryptoExportSessionKeyBlob",
                    "IISCryptoExportSessionKeyBlob.CryptSignHash failed err=0x%x.\n",
                    pdwDataLenb);
                }
              }
              else
              {
                v17 = IcpGetLastError();
                v11 = v17;
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  LODWORD(pdwDataLena) = v17;
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\crypto\\key.cxx",
                    589,
                    "IISCryptoExportSessionKeyBlob",
                    "IISCryptoExportSessionKeyBlob.CryptHashData failed err=0x%x.\n",
                    pdwDataLena);
                }
              }
            }
            else if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(pdwDataLena) = Hash;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\key.cxx",
                563,
                "IISCryptoExportSessionKeyBlob",
                "IISCryptoExportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n",
                pdwDataLena);
            }
          }
          else
          {
            v15 = IcpGetLastError();
            v11 = v15;
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(pdwDataLena) = v15;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\key.cxx",
                547,
                "IISCryptoExportSessionKeyBlob",
                "IISCryptoExportSessionKeyBlob.CryptExportKey failed err=0x%x.\n",
                pdwDataLena);
            }
          }
        }
        else
        {
          v11 = -2147024888;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(pdwDataLen) = HashLength;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          513,
          "IISCryptoExportSessionKeyBlob",
          "IISCryptoExportSessionKeyBlob.IcpGetHashLength failed err=0x%x.\n",
          pdwDataLen);
      }
    }
    else
    {
      v10 = IcpGetLastError();
      v11 = v10;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(pdwDataLen) = v10;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          499,
          "IISCryptoExportSessionKeyBlob",
          "IISCryptoExportSessionKeyBlob.CryptExportKey (advapi32.dll) failed err=0x%x.\n",
          pdwDataLen);
      }
    }
    if ( hHash[0] )
      IISCryptoDestroyHash(hHash[0]);
    if ( !v9 )
      return v11;
    goto LABEL_32;
  }
  if ( a2 == 1984918096 && a3 == 1800627539 && a4 == 1801020747 )
    return IISCryptoCreateCleartextBlob(a1, Locale, 1);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18002a710  push    rbp
0x18002a712  push    rbx
0x18002a713  push    rsi
0x18002a714  push    rdi
0x18002a715  push    r12
0x18002a717  push    r13
0x18002a719  push    r14
0x18002a71b  push    r15
0x18002a71d  mov     rbp, rsp
0x18002a720  sub     rsp, 48h
0x18002a724  xor     ebx, ebx
0x18002a726  mov     r14, r9
0x18002a729  cmp     cs:dword_180048964, ebx
0x18002a72f  mov     r15, r8
0x18002a732  mov     rsi, rdx
0x18002a735  mov     [rbp+dwDataLen], ebx
0x18002a738  mov     r12, rcx
0x18002a73b  mov     [rbp+pdwSigLen], ebx
0x18002a73e  jnz     short loc_18002A77A
0x18002a740  cmp     rdx, 764F7250h
0x18002a747  jnz     short loc_18002A770
0x18002a749  cmp     r8, 6B536553h
0x18002a750  jnz     short loc_18002A770
0x18002a752  cmp     r9, 6B59654Bh
0x18002a759  jnz     short loc_18002A770
0x18002a75b  lea     r8d, [rbx+1]
0x18002a75f  lea     rdx, Locale
0x18002a766  call    IISCryptoCreateCleartextBlob
0x18002a76b  jmp     loc_18002A9A9
0x18002a770  mov     eax, 80070057h
0x18002a775  jmp     loc_18002A9A9
0x18002a77a  xor     r9d, r9d; dwFlags
0x18002a77d  mov     [rbp+hHash], rbx
0x18002a781  lea     rax, [rbp+dwDataLen]
0x18002a785  mov     rdx, r14; hExpKey
0x18002a788  mov     [rsp+48h+pdwDataLen], rax; pdwDataLen
0x18002a78d  mov     rcx, r15; hKey
0x18002a790  mov     rdi, rbx
0x18002a793  mov     [rsp+48h+pbData], rbx; pbData
0x18002a798  lea     r8d, [r9+1]; dwBlobType
0x18002a79c  call    cs:__imp_CryptExportKey
0x18002a7a2  test    eax, eax
0x18002a7a4  jnz     short loc_18002A7D0
0x18002a7a6  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002a7ab  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a7b2  mov     ebx, eax
0x18002a7b4  jz      loc_18002A97A
0x18002a7ba  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18002a7be  mov     r8d, 1F3h
0x18002a7c4  lea     rax, aIiscryptoexpor_11; "IISCryptoExportSessionKeyBlob.CryptExpo"...
0x18002a7cb  jmp     loc_18002A95A
0x18002a7d0  mov     rdx, rsi; unsigned __int64
0x18002a7d3  lea     rcx, [rbp+pdwSigLen]; unsigned int *
0x18002a7d7  call    ?IcpGetHashLength@@YAJPEAK_K@Z; IcpGetHashLength(ulong *,unsigned __int64)
0x18002a7dc  mov     ebx, eax
0x18002a7de  test    eax, eax
0x18002a7e0  jns     short loc_18002A805
0x18002a7e2  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a7e9  jz      loc_18002A97A
0x18002a7ef  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18002a7f3  mov     r8d, 201h
0x18002a7f9  lea     rax, aIiscryptoexpor_1; "IISCryptoExportSessionKeyBlob.IcpGetHas"...
0x18002a800  jmp     loc_18002A95A
0x18002a805  mov     r8d, [rbp+pdwSigLen]; unsigned int
0x18002a809  mov     ecx, 624B6349h; unsigned int
0x18002a80e  mov     edx, [rbp+dwDataLen]; unsigned int
0x18002a811  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x18002a816  mov     rdi, rax
0x18002a819  test    rax, rax
0x18002a81c  jnz     short loc_18002A828
0x18002a81e  mov     ebx, 80070008h
0x18002a823  jmp     loc_18002A97A
0x18002a828  lea     r13, [rax+10h]
0x18002a82c  xor     r9d, r9d; dwFlags
0x18002a82f  lea     rax, [rbp+dwDataLen]
0x18002a833  mov     rdx, r14; hExpKey
0x18002a836  mov     [rsp+48h+pdwDataLen], rax; pdwDataLen
0x18002a83b  mov     rcx, r15; hKey
0x18002a83e  mov     [rsp+48h+pbData], r13; pbData
0x18002a843  lea     r8d, [r9+1]; dwBlobType
0x18002a847  call    cs:__imp_CryptExportKey
0x18002a84d  test    eax, eax
0x18002a84f  jnz     short loc_18002A87B
0x18002a851  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002a856  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a85d  mov     ebx, eax
0x18002a85f  jz      loc_18002A97A
0x18002a865  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18002a869  mov     r8d, 223h
0x18002a86f  lea     rax, aIiscryptoexpor; "IISCryptoExportSessionKeyBlob.CryptExpo"...
0x18002a876  jmp     loc_18002A95A
0x18002a87b  mov     rdx, rsi; hProv
0x18002a87e  lea     rcx, [rbp+hHash]; phHash
0x18002a882  call    IISCryptoCreateHash
0x18002a887  mov     ebx, eax
0x18002a889  test    eax, eax
0x18002a88b  jns     short loc_18002A8B0
0x18002a88d  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a894  jz      loc_18002A97A
0x18002a89a  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18002a89e  mov     r8d, 233h
0x18002a8a4  lea     rax, aIiscryptoexpor_9; "IISCryptoExportSessionKeyBlob.IISCrypto"...
0x18002a8ab  jmp     loc_18002A95A
0x18002a8b0  mov     rcx, [rbp+hHash]; hHash
0x18002a8b4  test    rcx, rcx
0x18002a8b7  jnz     short loc_18002A8C3
0x18002a8b9  mov     ebx, 80004005h
0x18002a8be  jmp     loc_18002A98D
0x18002a8c3  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x18002a8c7  xor     r9d, r9d; dwFlags
0x18002a8ca  mov     rdx, r13; pbData
0x18002a8cd  call    cs:__imp_CryptHashData
0x18002a8d3  test    eax, eax
0x18002a8d5  jnz     short loc_18002A8FE
0x18002a8d7  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002a8dc  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a8e3  mov     ebx, eax
0x18002a8e5  jz      loc_18002A97A
0x18002a8eb  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18002a8ef  mov     r8d, 24Dh
0x18002a8f5  lea     rax, aIiscryptoexpor_6; "IISCryptoExportSessionKeyBlob.CryptHash"...
0x18002a8fc  jmp     short loc_18002A95A
0x18002a8fe  mov     eax, [rdi+8]
0x18002a901  mov     ecx, 0FFFFFFF8h
0x18002a906  add     eax, 7
0x18002a909  xor     r9d, r9d; dwFlags
0x18002a90c  and     rax, rcx
0x18002a90f  xor     r8d, r8d; szDescription
0x18002a912  add     rax, 10h
0x18002a916  lea     rcx, [rbp+pdwSigLen]
0x18002a91a  mov     [rsp+48h+pdwDataLen], rcx; pdwSigLen
0x18002a91f  add     rax, rdi
0x18002a922  mov     rcx, [rbp+hHash]; hHash
0x18002a926  lea     edx, [r9+2]; dwKeySpec
0x18002a92a  mov     [rsp+48h+pbData], rax; pbSignature
0x18002a92f  call    cs:__imp_CryptSignHashA
0x18002a935  test    eax, eax
0x18002a937  jnz     short loc_18002A99A
0x18002a939  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002a93e  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a945  mov     ebx, eax
0x18002a947  jz      short loc_18002A97A
0x18002a949  mov     dword ptr [rsp+48h+pdwDataLen], eax
0x18002a94d  mov     r8d, 25Ch
0x18002a953  lea     rax, aIiscryptoexpor_3; "IISCryptoExportSessionKeyBlob.CryptSign"...
0x18002a95a  mov     rcx, cs:g_pDebug
0x18002a961  lea     r9, aIiscryptoexpor_8; "IISCryptoExportSessionKeyBlob"
0x18002a968  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002a96f  mov     [rsp+48h+pbData], rax
0x18002a974  call    cs:__imp_PuDbgPrint
0x18002a97a  mov     rcx, [rbp+hHash]
0x18002a97e  test    rcx, rcx
0x18002a981  jz      short loc_18002A988
0x18002a983  call    IISCryptoDestroyHash
0x18002a988  test    rdi, rdi
0x18002a98b  jz      short loc_18002A996
0x18002a98d  mov     rcx, rdi; pv
0x18002a990  call    cs:__imp_CoTaskMemFree
0x18002a996  mov     eax, ebx
0x18002a998  jmp     short loc_18002A9A9
0x18002a99a  mov     rcx, [rbp+hHash]
0x18002a99e  call    IISCryptoDestroyHash
0x18002a9a3  xor     eax, eax
0x18002a9a5  mov     [r12], rdi
0x18002a9a9  add     rsp, 48h
0x18002a9ad  pop     r15
0x18002a9af  pop     r14
0x18002a9b1  pop     r13
0x18002a9b3  pop     r12
0x18002a9b5  pop     rdi
0x18002a9b6  pop     rsi
0x18002a9b7  pop     rbx
0x18002a9b8  pop     rbp
0x18002a9b9  retn
```
