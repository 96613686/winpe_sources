# CertificateCreateObjectContext

- ea: `0x180019070`
- end: `0x180019218`
- name: `CertificateCreateObjectContext`
- size: `424`
- prototype: `__int64 __fastcall(__int64, char, __int64, const void **ppvContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180019070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800191b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800191b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019170`
- `CRYPT32!CertEnumCRLsInStore` at `0x180019130`
- `CRYPT32!CertEnumCRLsInStore` at `0x180019130`
- `CRYPT32!I_CertUpdateStore` at `0x18001914d`
- `CRYPT32!I_CertUpdateStore` at `0x18001914d`
- `CRYPT32!CryptQueryObject` at `0x18001911f`
- `CRYPT32!CryptQueryObject` at `0x1800191ef`
- `CRYPT32!CryptQueryObject` at `0x18001911f`
- `CRYPT32!CryptQueryObject` at `0x1800191ef`
- `CRYPT32!CertCloseStore` at `0x18001915c`
- `CRYPT32!CertCloseStore` at `0x18001918a`
- `CRYPT32!CertCloseStore` at `0x18001915c`
- `CRYPT32!CertCloseStore` at `0x18001918a`
- `CRYPT32!CertDeleteCRLFromStore` at `0x18001920d`
- `CRYPT32!CertDeleteCRLFromStore` at `0x18001920d`
- `CRYPT32!CertOpenStore` at `0x1800190a2`
- `CRYPT32!CertOpenStore` at `0x1800190a2`

## pseudocode

```c
__int64 __fastcall CertificateCreateObjectContext(__int64 a1, char a2, __int64 a3, const void **ppvContext)
{
  unsigned int v4; // ebx
  HCERTSTORE v7; // rbp
  unsigned int updated; // edi
  DWORD LastError; // r12d
  int v10; // esi
  unsigned int v11; // r14d
  _BYTE **v12; // rdx
  const CRL_CONTEXT *v13; // rax
  HCERTSTORE hCertStore; // [rsp+60h] [rbp-58h] BYREF

  v4 = 0;
  if ( (a2 & 1) != 0 )
  {
    v7 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
    if ( v7 )
    {
      updated = 1;
      LastError = 0;
      v10 = 0;
      v11 = 0;
      while ( v11 < *(_DWORD *)a3 )
      {
        v12 = (_BYTE **)(*(_QWORD *)(a3 + 8) + 16LL * v11);
        hCertStore = 0;
        if ( *(_DWORD *)v12 && (*(_DWORD *)v12 != 1 || *v12[1]) )
        {
          if ( CryptQueryObject(2u, v12, 0x2102u, 0xEu, 0, 0, 0, 0, &hCertStore, 0, 0) )
          {
            while ( 1 )
            {
              v13 = CertEnumCRLsInStore(hCertStore, 0);
              if ( !v13 )
                break;
              CertDeleteCRLFromStore(v13);
            }
            updated = I_CertUpdateStore(v7, hCertStore, 0, 0);
            CertCloseStore(hCertStore, 0);
            v10 = 1;
          }
          else if ( !v10 )
          {
            v10 = -1;
            LastError = GetLastError();
          }
        }
        ++v11;
        if ( updated != 1 )
          goto LABEL_13;
      }
      if ( v10 < 0 )
      {
        updated = 0;
        SetLastError(LastError);
LABEL_13:
        CertCloseStore(v7, 0);
        return updated;
      }
      *ppvContext = v7;
      return updated;
    }
  }
  else
  {
    return CryptQueryObject(2u, *(const void **)(a3 + 8), 2u, 0xEu, 0, 0, 0, 0, 0, 0, ppvContext);
  }
  return v4;
}

```

## disassembly

```asm
0x180019070  push    rbx
0x180019072  push    rbp
0x180019073  push    rsi
0x180019074  push    rdi
0x180019075  push    r12
0x180019077  push    r13
0x180019079  push    r14
0x18001907b  push    r15
0x18001907d  sub     rsp, 78h
0x180019081  xor     ebx, ebx
0x180019083  mov     r13, r9
0x180019086  mov     r15, r8
0x180019089  test    dl, 1
0x18001908c  jz      loc_1800191BC
0x180019092  xor     r9d, r9d; dwFlags
0x180019095  mov     [rsp+0B8h+pvPara], rbx; pvPara
0x18001909a  xor     r8d, r8d; hCryptProv
0x18001909d  lea     ecx, [rbx+2]; lpszStoreProvider
0x1800190a0  xor     edx, edx; dwEncodingType
0x1800190a2  call    cs:__imp_CertOpenStore
0x1800190a8  mov     rbp, rax
0x1800190ab  test    rax, rax
0x1800190ae  jz      loc_180019192
0x1800190b4  lea     edi, [rbx+1]
0x1800190b7  mov     r12d, ebx
0x1800190ba  mov     esi, ebx
0x1800190bc  mov     r14d, ebx
0x1800190bf  cmp     r14d, [r15]
0x1800190c2  jnb     loc_1800191A5
0x1800190c8  mov     edx, r14d
0x1800190cb  shl     rdx, 4
0x1800190cf  add     rdx, [r15+8]; pvObject
0x1800190d3  mov     [rsp+0B8h+hCertStore], rbx
0x1800190d8  cmp     [rdx], ebx
0x1800190da  jz      loc_180019179
0x1800190e0  cmp     dword ptr [rdx], 1
0x1800190e3  jz      loc_1800191F9
0x1800190e9  mov     [rsp+0B8h+ppvContext], rbx; ppvContext
0x1800190ee  lea     rax, [rsp+0B8h+hCertStore]
0x1800190f3  mov     [rsp+0B8h+phMsg], rbx; phMsg
0x1800190f8  mov     ecx, 2; dwObjectType
0x1800190fd  mov     [rsp+0B8h+phCertStore], rax; phCertStore
0x180019102  mov     r8d, 2102h; dwExpectedContentTypeFlags
0x180019108  mov     [rsp+0B8h+pdwFormatType], rbx; pdwFormatType
0x18001910d  mov     [rsp+0B8h+pdwContentType], rbx; pdwContentType
0x180019112  mov     [rsp+0B8h+pdwMsgAndCertEncodingType], rbx; pdwMsgAndCertEncodingType
0x180019117  lea     r9d, [rcx+0Ch]; dwExpectedFormatTypeFlags
0x18001911b  mov     dword ptr [rsp+0B8h+pvPara], ebx; dwFlags
0x18001911f  call    cs:__imp_CryptQueryObject
0x180019125  test    eax, eax
0x180019127  jz      short loc_180019169
0x180019129  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x18001912e  xor     edx, edx; pPrevCrlContext
0x180019130  call    cs:__imp_CertEnumCRLsInStore
0x180019136  test    rax, rax
0x180019139  jnz     loc_18001920A
0x18001913f  mov     rdx, [rsp+0B8h+hCertStore]
0x180019144  xor     r9d, r9d
0x180019147  xor     r8d, r8d
0x18001914a  mov     rcx, rbp
0x18001914d  call    cs:__imp_I_CertUpdateStore
0x180019153  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x180019158  xor     edx, edx; dwFlags
0x18001915a  mov     edi, eax
0x18001915c  call    cs:__imp_CertCloseStore
0x180019162  mov     esi, 1
0x180019167  jmp     short loc_180019179
0x180019169  test    esi, esi
0x18001916b  jnz     short loc_180019179
0x18001916d  or      esi, 0FFFFFFFFh
0x180019170  call    cs:__imp_GetLastError
0x180019176  mov     r12d, eax
0x180019179  inc     r14d
0x18001917c  cmp     edi, 1
0x18001917f  jz      loc_1800190BF
0x180019185  xor     edx, edx; dwFlags
0x180019187  mov     rcx, rbp; hCertStore
0x18001918a  call    cs:__imp_CertCloseStore
0x180019190  mov     ebx, edi
0x180019192  mov     eax, ebx
0x180019194  add     rsp, 78h
0x180019198  pop     r15
0x18001919a  pop     r14
0x18001919c  pop     r13
0x18001919e  pop     r12
0x1800191a0  pop     rdi
0x1800191a1  pop     rsi
0x1800191a2  pop     rbp
0x1800191a3  pop     rbx
0x1800191a4  retn
0x1800191a5  test    esi, esi
0x1800191a7  js      short loc_1800191AF
0x1800191a9  mov     [r13+0], rbp
0x1800191ad  jmp     short loc_180019190
0x1800191af  mov     ecx, r12d; dwErrCode
0x1800191b2  mov     edi, ebx
0x1800191b4  call    cs:__imp_SetLastError
0x1800191ba  jmp     short loc_180019185
0x1800191bc  mov     rdx, [r15+8]; pvObject
0x1800191c0  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x1800191c6  mov     [rsp+0B8h+ppvContext], r13; ppvContext
0x1800191cb  mov     [rsp+0B8h+phMsg], rbx; phMsg
0x1800191d0  mov     [rsp+0B8h+phCertStore], rbx; phCertStore
0x1800191d5  mov     [rsp+0B8h+pdwFormatType], rbx; pdwFormatType
0x1800191da  lea     r8d, [r9-0Ch]; dwExpectedContentTypeFlags
0x1800191de  mov     [rsp+0B8h+pdwContentType], rbx; pdwContentType
0x1800191e3  mov     ecx, r8d; dwObjectType
0x1800191e6  mov     [rsp+0B8h+pdwMsgAndCertEncodingType], rbx; pdwMsgAndCertEncodingType
0x1800191eb  mov     dword ptr [rsp+0B8h+pvPara], ebx; dwFlags
0x1800191ef  call    cs:__imp_CryptQueryObject
0x1800191f5  mov     ebx, eax
0x1800191f7  jmp     short loc_180019192
0x1800191f9  mov     rax, [rdx+8]
0x1800191fd  cmp     [rax], bl
0x1800191ff  jz      loc_180019179
0x180019205  jmp     loc_1800190E9
0x18001920a  mov     rcx, rax; pCrlContext
0x18001920d  call    cs:__imp_CertDeleteCRLFromStore
0x180019213  jmp     loc_180019129
```
