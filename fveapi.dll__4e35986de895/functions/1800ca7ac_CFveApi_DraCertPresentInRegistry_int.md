# CFveApi::DraCertPresentInRegistry(int *)

- ea: `0x1800ca7ac`
- end: `0x1800ca8ae`
- name: `?DraCertPresentInRegistry@CFveApi@@SAJPEAH@Z`
- size: `258`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180067130`

## callees

- `0x1800ca7ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca811`
- `CRYPT32!CertCloseStore` at `0x1800ca895`
- `CRYPT32!CertCloseStore` at `0x18012766b`
- `CRYPT32!CertCloseStore` at `0x1800ca895`
- `CRYPT32!CertCloseStore` at `0x18012766b`
- `CRYPT32!CertOpenStore` at `0x1800ca7f8`
- `CRYPT32!CertOpenStore` at `0x1800ca7f8`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800ca83b`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800ca83b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800ca87f`
- `CRYPT32!CertFreeCertificateContext` at `0x180127653`
- `CRYPT32!CertFreeCertificateContext` at `0x1800ca87f`
- `CRYPT32!CertFreeCertificateContext` at `0x180127653`
- `FVECERTS!FveCertCanCertificateBeAdded` at `0x1800ca85c`
- `FVECERTS!FveCertCanCertificateBeAdded` at `0x1800ca85c`

## pseudocode

```c
__int64 __fastcall CFveApi::DraCertPresentInRegistry(int *a1)
{
  unsigned int v2; // edi
  HCERTSTORE v3; // rsi
  const CERT_CONTEXT *v4; // rbx
  signed int LastError; // eax
  PCCERT_CONTEXT v6; // rax

  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v3 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x88000u, L"FVE");
    if ( v3 )
    {
      while ( 1 )
      {
        v6 = CertEnumCertificatesInStore(v3, v4);
        v4 = v6;
        if ( !v6 )
          break;
        if ( (int)FveCertCanCertificateBeAdded(v6, 1) >= 0 )
        {
          *a1 = 1;
          break;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v2 = 0;
      if ( LastError != -2147024894 )
        v2 = LastError;
    }
  }
  else
  {
    v2 = -2147024809;
  }
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( v3 )
    CertCloseStore(v3, 0);
  return v2;
}

```

## disassembly

```asm
0x1800ca7ac  push    rbx
0x1800ca7ae  push    rsi
0x1800ca7af  push    rdi
0x1800ca7b0  push    r14
0x1800ca7b2  sub     rsp, 48h
0x1800ca7b6  mov     r14, rcx
0x1800ca7b9  xor     edi, edi
0x1800ca7bb  xor     esi, esi
0x1800ca7bd  mov     [rsp+68h+var_30], rsi
0x1800ca7c2  xor     ebx, ebx
0x1800ca7c4  mov     [rsp+68h+var_38], rbx
0x1800ca7c9  test    rcx, rcx
0x1800ca7cc  jnz     short loc_1800CA7D8
0x1800ca7ce  mov     edi, 80070057h
0x1800ca7d3  jmp     loc_1800CA877
0x1800ca7d8  mov     dword ptr [rcx], 0
0x1800ca7de  lea     rax, aFve; "FVE"
0x1800ca7e5  mov     [rsp+68h+pvPara], rax; pvPara
0x1800ca7ea  mov     r9d, 88000h; dwFlags
0x1800ca7f0  xor     r8d, r8d; hCryptProv
0x1800ca7f3  xor     edx, edx; dwEncodingType
0x1800ca7f5  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x1800ca7f8  call    cs:__imp_CertOpenStore
0x1800ca7ff  nop     dword ptr [rax+rax+00h]
0x1800ca804  mov     rsi, rax
0x1800ca807  mov     [rsp+68h+var_30], rax
0x1800ca80c  test    rax, rax
0x1800ca80f  jnz     short loc_1800CA835
0x1800ca811  call    cs:__imp_GetLastError
0x1800ca818  nop     dword ptr [rax+rax+00h]
0x1800ca81d  test    eax, eax
0x1800ca81f  jle     short loc_1800CA829
0x1800ca821  movzx   eax, ax
0x1800ca824  or      eax, 80070000h
0x1800ca829  xor     edi, edi
0x1800ca82b  cmp     eax, 80070002h
0x1800ca830  cmovnz  edi, eax
0x1800ca833  jmp     short loc_1800CA877
0x1800ca835  mov     rdx, rbx; pPrevCertContext
0x1800ca838  mov     rcx, rsi; hCertStore
0x1800ca83b  call    cs:__imp_CertEnumCertificatesInStore
0x1800ca842  nop     dword ptr [rax+rax+00h]
0x1800ca847  mov     rbx, rax
0x1800ca84a  mov     [rsp+68h+var_38], rax
0x1800ca84f  test    rax, rax
0x1800ca852  jz      short loc_1800CA877
0x1800ca854  mov     edx, 1
0x1800ca859  mov     rcx, rax
0x1800ca85c  call    cs:__imp_FveCertCanCertificateBeAdded
0x1800ca863  nop     dword ptr [rax+rax+00h]
0x1800ca868  test    eax, eax
0x1800ca86a  js      short loc_1800CA875
0x1800ca86c  mov     dword ptr [r14], 1
0x1800ca873  jmp     short loc_1800CA877
0x1800ca875  jmp     short loc_1800CA835
0x1800ca877  test    rbx, rbx
0x1800ca87a  jz      short loc_1800CA88B
0x1800ca87c  mov     rcx, rbx; pCertContext
0x1800ca87f  call    cs:__imp_CertFreeCertificateContext
0x1800ca886  nop     dword ptr [rax+rax+00h]
0x1800ca88b  test    rsi, rsi
0x1800ca88e  jz      short loc_1800CA8A1
0x1800ca890  xor     edx, edx; dwFlags
0x1800ca892  mov     rcx, rsi; hCertStore
0x1800ca895  call    cs:__imp_CertCloseStore
0x1800ca89c  nop     dword ptr [rax+rax+00h]
0x1800ca8a1  mov     eax, edi
0x1800ca8a3  add     rsp, 48h
0x1800ca8a7  pop     r14
0x1800ca8a9  pop     rdi
0x1800ca8aa  pop     rsi
0x1800ca8ab  pop     rbx
0x1800ca8ac  retn
0x180127641  push    rbp
0x180127643  sub     rsp, 30h
0x180127647  mov     rbp, rdx
0x18012764a  mov     rcx, [rbp+30h]; pCertContext
0x18012764e  test    rcx, rcx
0x180127651  jz      short loc_180127660
0x180127653  call    cs:__imp_CertFreeCertificateContext
0x18012765a  nop     dword ptr [rax+rax+00h]
0x18012765f  nop
0x180127660  mov     rcx, [rbp+38h]; hCertStore
0x180127664  test    rcx, rcx
0x180127667  jz      short loc_180127678
0x180127669  xor     edx, edx; dwFlags
0x18012766b  call    cs:__imp_CertCloseStore
0x180127672  nop     dword ptr [rax+rax+00h]
0x180127677  nop
0x180127678  add     rsp, 30h
0x18012767c  pop     rbp
0x18012767d  retn
```
