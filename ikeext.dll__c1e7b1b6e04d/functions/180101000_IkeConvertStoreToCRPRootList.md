# IkeConvertStoreToCRPRootList

- ea: `0x180101000`
- end: `0x18010128e`
- name: `IkeConvertStoreToCRPRootList`
- size: `654`
- prototype: `__int64 __fastcall(int, __int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18010130c`

## callees

- `0x180003c7c`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180101000`
- `0x180101294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801010ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801011c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801010ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801011c3`
- `CRYPT32!CertFreeCertificateContext` at `0x18010123e`
- `CRYPT32!CertFreeCertificateContext` at `0x18010123e`
- `CRYPT32!CertOpenStore` at `0x1801010a0`
- `CRYPT32!CertOpenStore` at `0x1801010a0`
- `CRYPT32!CertCloseStore` at `0x180101249`
- `CRYPT32!CertCloseStore` at `0x180101249`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1801011b9`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1801011b9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1801010d4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1801010ee`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180101137`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1801010d4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1801010ee`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180101137`

## string_xrefs

- `0x1801010bb`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeConvertStoreToCRPRootList(int a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  __int64 v5; // rdi
  __int64 v6; // rsi
  bool v9; // zf
  __int64 v10; // r13
  __int64 v11; // rcx
  const wchar_t *pvPara; // rax
  DWORD v13; // r9d
  unsigned int v14; // ebp
  HCERTSTORE v15; // rax
  void *v16; // r15
  DWORD v17; // eax
  __int64 v18; // rcx
  PCCERT_CONTEXT v19; // rbx
  unsigned int v20; // r14d
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r12
  DWORD LastError; // eax
  __int64 v25; // rcx
  __int64 v28; // [rsp+98h] [rbp+10h] BYREF
  _QWORD *v29; // [rsp+A0h] [rbp+18h]
  unsigned int *v30; // [rsp+A8h] [rbp+20h]

  v30 = a4;
  v29 = a3;
  v5 = 0;
  v6 = 0;
  v28 = 0;
  TraceLogHelper("IkeConvertStoreToCRPRootList", 1);
  v9 = *(_DWORD *)a2 == 1;
  v10 = *(_QWORD *)(a2 + 16);
  v11 = 13;
  *a3 = 0;
  if ( !v9 )
    v11 = 10;
  *a4 = 0;
  pvPara = L"NTAuth";
  v13 = 589825;
  if ( !v9 )
  {
    pvPara = L"Root";
    v13 = 131073;
  }
  if ( (*(_BYTE *)(a2 + 48) & 0x40) == 0 && (!v10 || (*(_BYTE *)(v10 + 48) & 2) == 0) )
  {
    v14 = 0;
    v15 = CertOpenStore((LPCSTR)v11, 0, 0, v13, pvPara);
    v16 = v15;
    if ( v15 )
    {
      v19 = CertEnumCertificatesInStore(v15, 0);
      if ( v19 )
      {
        do
        {
          ++v14;
          v19 = CertEnumCertificatesInStore(v16, v19);
        }
        while ( v19 );
        if ( v14 )
        {
          v20 = 0;
          v21 = WfpMemAlloc(56LL * v14, 8u, &v28);
          v6 = v28;
          v5 = v21;
          if ( !v21 )
          {
            while ( 1 )
            {
              v19 = CertEnumCertificatesInStore(v16, v19);
              if ( !v19 || v20 >= v14 )
                break;
              v23 = 56LL * v20;
              if ( a1 )
              {
                v5 = WfpMemAlloc(0x14u, 8u, (_QWORD *)(v23 + v6 + 8));
                if ( v5 )
                  goto LABEL_26;
                *(_DWORD *)(v23 + v6) = 20;
                if ( !CryptHashPublicKeyInfo(
                        0,
                        0x8004u,
                        0,
                        0x10001u,
                        &v19->pCertInfo->SubjectPublicKeyInfo,
                        *(BYTE **)(v23 + v6 + 8),
                        (DWORD *)(v23 + v6)) )
                {
                  LastError = GetLastError();
                  v5 = WfpReportSysErrorAsWinError(v25, "CryptHashPublicKeyInfo", LastError, 1);
                  goto LABEL_26;
                }
              }
              else
              {
                v5 = WfpBufferCopy(
                       v19->pCertInfo->Subject.pbData,
                       v19->pCertInfo->Subject.cbData,
                       v22,
                       (void **)(v23 + v6 + 8));
                if ( v5 )
                  goto LABEL_26;
                *(_DWORD *)(v23 + v6) = v19->pCertInfo->Subject.cbData;
              }
              if ( v10 )
                *(_DWORD *)(v23 + v6 + 48) = *(_DWORD *)(v10 + 48);
              ++v20;
            }
            *v29 = v6;
            *v30 = v14;
            if ( !v19 )
              goto LABEL_27;
LABEL_26:
            CertFreeCertificateContext(v19);
          }
        }
      }
LABEL_27:
      CertCloseStore(v16, 0);
    }
    else
    {
      v17 = GetLastError();
      v5 = WfpReportSysErrorAsWinError(v18, "CertOpenStore", v17, 1);
    }
    if ( v5 )
      IkeFreeCRPRootList(v6, v14);
  }
  TraceLogHelper("IkeConvertStoreToCRPRootList", 1);
  return IkeReturnError(v5, "IkeConvertStoreToCRPRootList");
}

```

## disassembly

```asm
0x180101000  mov     rax, rsp
0x180101003  mov     [rax+20h], r9
0x180101007  mov     [rax+18h], r8
0x18010100b  mov     [rax+8], ecx
0x18010100e  push    rbx
0x18010100f  push    rbp
0x180101010  push    rsi
0x180101011  push    rdi
0x180101012  push    r12
0x180101014  push    r13
0x180101016  push    r14
0x180101018  push    r15
0x18010101a  sub     rsp, 48h
0x18010101e  mov     rbx, rdx
0x180101021  lea     rcx, aIkeconvertstor; "IkeConvertStoreToCRPRootList"
0x180101028  xor     edi, edi
0x18010102a  xor     esi, esi
0x18010102c  mov     r12, r9
0x18010102f  mov     [rax+10h], rsi
0x180101033  mov     r14, r8
0x180101036  lea     r13d, [rdi+1]
0x18010103a  mov     edx, r13d
0x18010103d  call    TraceLogHelper
0x180101042  cmp     [rbx], r13d
0x180101045  lea     eax, [rdi+0Ah]
0x180101048  mov     r13, [rbx+10h]
0x18010104c  lea     rdx, aRoot; "Root"
0x180101053  lea     ecx, [rdi+0Dh]
0x180101056  mov     [r14], rsi
0x180101059  cmovnz  ecx, eax; lpszStoreProvider
0x18010105c  mov     [r12], esi
0x180101060  lea     rax, aNtauth; "NTAuth"
0x180101067  mov     r9d, 90001h
0x18010106d  cmovnz  rax, rdx
0x180101071  mov     edx, 20001h
0x180101076  cmovnz  r9d, edx; dwFlags
0x18010107a  test    byte ptr [rbx+30h], 40h
0x18010107e  jnz     loc_18010125E
0x180101084  test    r13, r13
0x180101087  jz      short loc_180101094
0x180101089  test    byte ptr [r13+30h], 2
0x18010108e  jnz     loc_18010125E
0x180101094  xor     r8d, r8d; hCryptProv
0x180101097  mov     [rsp+88h+pvPara], rax; pvPara
0x18010109c  xor     edx, edx; dwEncodingType
0x18010109e  xor     ebp, ebp
0x1801010a0  call    cs:__imp_CertOpenStore
0x1801010a6  mov     r15, rax
0x1801010a9  test    rax, rax
0x1801010ac  jnz     short loc_1801010CF
0x1801010ae  call    cs:__imp_GetLastError
0x1801010b4  mov     r8d, eax
0x1801010b7  lea     r9d, [rbp+1]
0x1801010bb  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x1801010c2  call    WfpReportSysErrorAsWinError
0x1801010c7  mov     rdi, rax
0x1801010ca  jmp     loc_18010124F
0x1801010cf  xor     edx, edx; pPrevCertContext
0x1801010d1  mov     rcx, r15; hCertStore
0x1801010d4  call    cs:__imp_CertEnumCertificatesInStore
0x1801010da  mov     rbx, rax
0x1801010dd  test    rax, rax
0x1801010e0  jz      loc_180101244
0x1801010e6  mov     rdx, rbx; pPrevCertContext
0x1801010e9  mov     rcx, r15; hCertStore
0x1801010ec  inc     ebp
0x1801010ee  call    cs:__imp_CertEnumCertificatesInStore
0x1801010f4  mov     rbx, rax
0x1801010f7  test    rax, rax
0x1801010fa  jnz     short loc_1801010E6
0x1801010fc  test    ebp, ebp
0x1801010fe  jz      loc_180101244
0x180101104  mov     eax, ebp
0x180101106  lea     r8, [rsp+88h+arg_8]
0x18010110e  imul    rcx, rax, 38h ; '8'; dwBytes
0x180101112  lea     edx, [rbx+8]; dwFlags
0x180101115  xor     r14d, r14d
0x180101118  call    WfpMemAlloc
0x18010111d  mov     rsi, [rsp+88h+arg_8]
0x180101125  mov     rdi, rax
0x180101128  test    rax, rax
0x18010112b  jnz     loc_180101244
0x180101131  mov     rdx, rbx; pPrevCertContext
0x180101134  mov     rcx, r15; hCertStore
0x180101137  call    cs:__imp_CertEnumCertificatesInStore
0x18010113d  mov     rbx, rax
0x180101140  test    rax, rax
0x180101143  jz      loc_180101221
0x180101149  cmp     r14d, ebp
0x18010114c  jnb     loc_180101221
0x180101152  mov     eax, r14d
0x180101155  imul    r12, rax, 38h ; '8'
0x180101159  cmp     [rsp+88h+arg_0], 0
0x180101161  jz      short loc_1801011E1
0x180101163  mov     edx, 8; dwFlags
0x180101168  lea     r8, [rsi+8]
0x18010116c  add     r8, r12
0x18010116f  lea     ecx, [rdx+0Ch]; dwBytes
0x180101172  call    WfpMemAlloc
0x180101177  mov     rdi, rax
0x18010117a  test    rax, rax
0x18010117d  jnz     loc_18010123B
0x180101183  lea     rax, [r12+rsi]
0x180101187  mov     r9d, 10001h; dwCertEncodingType
0x18010118d  mov     [rsp+88h+pcbComputedHash], rax; pcbComputedHash
0x180101192  xor     r8d, r8d; dwFlags
0x180101195  mov     dword ptr [rax], 14h
0x18010119b  mov     edx, 8004h; Algid
0x1801011a0  mov     rcx, [rbx+18h]
0x1801011a4  mov     rax, [r12+rsi+8]
0x1801011a9  add     rcx, 60h ; '`'
0x1801011ad  mov     [rsp+88h+pbComputedHash], rax; pbComputedHash
0x1801011b2  mov     [rsp+88h+pvPara], rcx; pInfo
0x1801011b7  xor     ecx, ecx; hCryptProv
0x1801011b9  call    cs:__imp_CryptHashPublicKeyInfo
0x1801011bf  test    eax, eax
0x1801011c1  jnz     short loc_18010120B
0x1801011c3  call    cs:__imp_GetLastError
0x1801011c9  mov     r8d, eax
0x1801011cc  lea     r9d, [rdi+1]
0x1801011d0  lea     rdx, aCrypthashpubli_0; "CryptHashPublicKeyInfo"
0x1801011d7  call    WfpReportSysErrorAsWinError
0x1801011dc  mov     rdi, rax
0x1801011df  jmp     short loc_18010123B
0x1801011e1  mov     rcx, [rbx+18h]
0x1801011e5  lea     r9, [rsi+8]
0x1801011e9  add     r9, r12
0x1801011ec  mov     edx, [rcx+50h]; Size
0x1801011ef  mov     rcx, [rcx+58h]; Src
0x1801011f3  call    WfpBufferCopy
0x1801011f8  mov     rdi, rax
0x1801011fb  test    rax, rax
0x1801011fe  jnz     short loc_18010123B
0x180101200  mov     rax, [rbx+18h]
0x180101204  mov     ecx, [rax+50h]
0x180101207  mov     [r12+rsi], ecx
0x18010120b  test    r13, r13
0x18010120e  jz      short loc_180101219
0x180101210  mov     eax, [r13+30h]
0x180101214  mov     [r12+rsi+30h], eax
0x180101219  inc     r14d
0x18010121c  jmp     loc_180101131
0x180101221  mov     rax, [rsp+88h+arg_10]
0x180101229  mov     [rax], rsi
0x18010122c  mov     rax, [rsp+88h+arg_18]
0x180101234  mov     [rax], ebp
0x180101236  test    rbx, rbx
0x180101239  jz      short loc_180101244
0x18010123b  mov     rcx, rbx; pCertContext
0x18010123e  call    cs:__imp_CertFreeCertificateContext
0x180101244  xor     edx, edx; dwFlags
0x180101246  mov     rcx, r15; hCertStore
0x180101249  call    cs:__imp_CertCloseStore
0x18010124f  test    rdi, rdi
0x180101252  jz      short loc_18010125E
0x180101254  mov     edx, ebp
0x180101256  mov     rcx, rsi
0x180101259  call    IkeFreeCRPRootList
0x18010125e  mov     edx, 1
0x180101263  lea     rcx, aIkeconvertstor; "IkeConvertStoreToCRPRootList"
0x18010126a  call    TraceLogHelper
0x18010126f  lea     rdx, aIkeconvertstor; "IkeConvertStoreToCRPRootList"
0x180101276  mov     rcx, rdi
0x180101279  add     rsp, 48h
0x18010127d  pop     r15
0x18010127f  pop     r14
0x180101281  pop     r13
0x180101283  pop     r12
0x180101285  pop     rdi
0x180101286  pop     rsi
0x180101287  pop     rbp
0x180101288  pop     rbx
0x180101289  jmp     IkeReturnError
```
