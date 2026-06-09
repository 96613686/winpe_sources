# CRLCreateObjectContext

- ea: `0x1800183f0`
- end: `0x180018598`
- name: `CRLCreateObjectContext`
- size: `424`
- prototype: `__int64 __fastcall(__int64, char, __int64, const void **ppvContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800183f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018530`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018516`
- `CRYPT32!I_CertUpdateStore` at `0x1800184c9`
- `CRYPT32!I_CertUpdateStore` at `0x1800184c9`
- `CRYPT32!CryptQueryObject` at `0x18001849f`
- `CRYPT32!CryptQueryObject` at `0x18001857a`
- `CRYPT32!CryptQueryObject` at `0x18001849f`
- `CRYPT32!CryptQueryObject` at `0x18001857a`
- `CRYPT32!CertCloseStore` at `0x1800184d8`
- `CRYPT32!CertCloseStore` at `0x1800184f4`
- `CRYPT32!CertCloseStore` at `0x1800184d8`
- `CRYPT32!CertCloseStore` at `0x1800184f4`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18001853b`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18001853b`
- `CRYPT32!CertOpenStore` at `0x180018422`
- `CRYPT32!CertOpenStore` at `0x180018422`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800184b0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800184b0`

## pseudocode

```c
__int64 __fastcall CRLCreateObjectContext(__int64 a1, char a2, __int64 a3, const void **ppvContext)
{
  unsigned int v4; // ebx
  HCERTSTORE v7; // rbp
  unsigned int updated; // edi
  DWORD LastError; // r12d
  int v10; // esi
  unsigned int v11; // r14d
  _BYTE **v12; // rdx
  const CERT_CONTEXT *v13; // rax
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
          if ( CryptQueryObject(2u, v12, 0x108u, 0xEu, 0, 0, 0, 0, &hCertStore, 0, 0) )
          {
            while ( 1 )
            {
              v13 = CertEnumCertificatesInStore(hCertStore, 0);
              if ( !v13 )
                break;
              CertDeleteCertificateFromStore(v13);
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
          goto LABEL_11;
      }
      if ( v10 < 0 )
      {
        updated = 0;
        SetLastError(LastError);
LABEL_11:
        CertCloseStore(v7, 0);
        return updated;
      }
      *ppvContext = v7;
      return updated;
    }
  }
  else
  {
    return CryptQueryObject(2u, *(const void **)(a3 + 8), 8u, 0xEu, 0, 0, 0, 0, 0, 0, ppvContext);
  }
  return v4;
}

```

## disassembly

```asm
0x1800183f0  push    rbx
0x1800183f2  push    rbp
0x1800183f3  push    rsi
0x1800183f4  push    rdi
0x1800183f5  push    r12
0x1800183f7  push    r13
0x1800183f9  push    r14
0x1800183fb  push    r15
0x1800183fd  sub     rsp, 78h
0x180018401  xor     ebx, ebx
0x180018403  mov     r13, r9
0x180018406  mov     r15, r8
0x180018409  test    dl, 1
0x18001840c  jz      loc_180018546
0x180018412  xor     r9d, r9d; dwFlags
0x180018415  mov     [rsp+0B8h+pvPara], rbx; pvPara
0x18001841a  xor     r8d, r8d; hCryptProv
0x18001841d  lea     ecx, [rbx+2]; lpszStoreProvider
0x180018420  xor     edx, edx; dwEncodingType
0x180018422  call    cs:__imp_CertOpenStore
0x180018428  mov     rbp, rax
0x18001842b  test    rax, rax
0x18001842e  jz      loc_1800184FC
0x180018434  lea     edi, [rbx+1]
0x180018437  mov     r12d, ebx
0x18001843a  mov     esi, ebx
0x18001843c  mov     r14d, ebx
0x18001843f  cmp     r14d, [r15]
0x180018442  jnb     loc_180018521
0x180018448  mov     edx, r14d
0x18001844b  shl     rdx, 4
0x18001844f  add     rdx, [r15+8]; pvObject
0x180018453  mov     [rsp+0B8h+hCertStore], rbx
0x180018458  cmp     [rdx], ebx
0x18001845a  jz      loc_1800184E3
0x180018460  cmp     dword ptr [rdx], 1
0x180018463  jz      loc_180018587
0x180018469  mov     [rsp+0B8h+ppvContext], rbx; ppvContext
0x18001846e  lea     rax, [rsp+0B8h+hCertStore]
0x180018473  mov     [rsp+0B8h+phMsg], rbx; phMsg
0x180018478  mov     ecx, 2; dwObjectType
0x18001847d  mov     [rsp+0B8h+phCertStore], rax; phCertStore
0x180018482  mov     r8d, 108h; dwExpectedContentTypeFlags
0x180018488  mov     [rsp+0B8h+pdwFormatType], rbx; pdwFormatType
0x18001848d  mov     [rsp+0B8h+pdwContentType], rbx; pdwContentType
0x180018492  mov     [rsp+0B8h+pdwMsgAndCertEncodingType], rbx; pdwMsgAndCertEncodingType
0x180018497  lea     r9d, [rcx+0Ch]; dwExpectedFormatTypeFlags
0x18001849b  mov     dword ptr [rsp+0B8h+pvPara], ebx; dwFlags
0x18001849f  call    cs:__imp_CryptQueryObject
0x1800184a5  test    eax, eax
0x1800184a7  jz      short loc_18001850F
0x1800184a9  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x1800184ae  xor     edx, edx; pPrevCertContext
0x1800184b0  call    cs:__imp_CertEnumCertificatesInStore
0x1800184b6  test    rax, rax
0x1800184b9  jnz     short loc_180018538
0x1800184bb  mov     rdx, [rsp+0B8h+hCertStore]
0x1800184c0  xor     r9d, r9d
0x1800184c3  xor     r8d, r8d
0x1800184c6  mov     rcx, rbp
0x1800184c9  call    cs:__imp_I_CertUpdateStore
0x1800184cf  mov     rcx, [rsp+0B8h+hCertStore]; hCertStore
0x1800184d4  xor     edx, edx; dwFlags
0x1800184d6  mov     edi, eax
0x1800184d8  call    cs:__imp_CertCloseStore
0x1800184de  mov     esi, 1
0x1800184e3  inc     r14d
0x1800184e6  cmp     edi, 1
0x1800184e9  jz      loc_18001843F
0x1800184ef  xor     edx, edx; dwFlags
0x1800184f1  mov     rcx, rbp; hCertStore
0x1800184f4  call    cs:__imp_CertCloseStore
0x1800184fa  mov     ebx, edi
0x1800184fc  mov     eax, ebx
0x1800184fe  add     rsp, 78h
0x180018502  pop     r15
0x180018504  pop     r14
0x180018506  pop     r13
0x180018508  pop     r12
0x18001850a  pop     rdi
0x18001850b  pop     rsi
0x18001850c  pop     rbp
0x18001850d  pop     rbx
0x18001850e  retn
0x18001850f  test    esi, esi
0x180018511  jnz     short loc_1800184E3
0x180018513  or      esi, 0FFFFFFFFh
0x180018516  call    cs:__imp_GetLastError
0x18001851c  mov     r12d, eax
0x18001851f  jmp     short loc_1800184E3
0x180018521  test    esi, esi
0x180018523  js      short loc_18001852B
0x180018525  mov     [r13+0], rbp
0x180018529  jmp     short loc_1800184FA
0x18001852b  mov     ecx, r12d; dwErrCode
0x18001852e  mov     edi, ebx
0x180018530  call    cs:__imp_SetLastError
0x180018536  jmp     short loc_1800184EF
0x180018538  mov     rcx, rax; pCertContext
0x18001853b  call    cs:__imp_CertDeleteCertificateFromStore
0x180018541  jmp     loc_1800184A9
0x180018546  mov     rdx, [r15+8]; pvObject
0x18001854a  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x180018550  mov     [rsp+0B8h+ppvContext], r13; ppvContext
0x180018555  mov     [rsp+0B8h+phMsg], rbx; phMsg
0x18001855a  mov     [rsp+0B8h+phCertStore], rbx; phCertStore
0x18001855f  mov     [rsp+0B8h+pdwFormatType], rbx; pdwFormatType
0x180018564  lea     r8d, [r9-6]; dwExpectedContentTypeFlags
0x180018568  mov     [rsp+0B8h+pdwContentType], rbx; pdwContentType
0x18001856d  lea     ecx, [r9-0Ch]; dwObjectType
0x180018571  mov     [rsp+0B8h+pdwMsgAndCertEncodingType], rbx; pdwMsgAndCertEncodingType
0x180018576  mov     dword ptr [rsp+0B8h+pvPara], ebx; dwFlags
0x18001857a  call    cs:__imp_CryptQueryObject
0x180018580  mov     ebx, eax
0x180018582  jmp     loc_1800184FC
0x180018587  mov     rax, [rdx+8]
0x18001858b  cmp     [rax], bl
0x18001858d  jz      loc_1800184E3
0x180018593  jmp     loc_180018469
```
