# FindCertBasedOnContainerHelper

- ea: `0x18001c10c`
- end: `0x18001c1b2`
- name: `FindCertBasedOnContainerHelper`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001be08`

## callees

- `0x18001c10c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c152`
- `CRYPT32!CertOpenStore` at `0x18001c13e`
- `CRYPT32!CertOpenStore` at `0x18001c13e`
- `CRYPT32!CertFindCertificateInStore` at `0x18001c18b`
- `CRYPT32!CertFindCertificateInStore` at `0x18001c18b`

## pseudocode

```c
signed int __fastcall FindCertBasedOnContainerHelper(int a1, const void *a2, _QWORD *a3, PCCERT_CONTEXT *a4)
{
  HCERTSTORE v7; // rax
  signed int result; // eax
  PCCERT_CONTEXT CertificateInStore; // rax

  v7 = CertOpenStore((LPCSTR)0xD, 0, 0, a1 | 1u, L"MY");
  *a3 = v7;
  if ( v7 )
  {
    CertificateInStore = CertFindCertificateInStore(v7, 0x10001u, 0, 0x60000u, a2, 0);
    *a4 = CertificateInStore;
    if ( CertificateInStore )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001c10c  mov     [rsp+arg_0], rbx
0x18001c111  mov     [rsp+arg_8], rsi
0x18001c116  push    rdi
0x18001c117  sub     rsp, 30h
0x18001c11b  or      ecx, 1
0x18001c11e  lea     rax, aMy; "MY"
0x18001c125  mov     rsi, rdx
0x18001c128  mov     [rsp+38h+pvPara], rax; pvPara
0x18001c12d  xor     edx, edx; dwEncodingType
0x18001c12f  mov     rdi, r9
0x18001c132  mov     rbx, r8
0x18001c135  mov     r9d, ecx; dwFlags
0x18001c138  xor     r8d, r8d; hCryptProv
0x18001c13b  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18001c13e  call    cs:__imp_CertOpenStore
0x18001c145  nop     dword ptr [rax+rax+00h]
0x18001c14a  mov     [rbx], rax
0x18001c14d  test    rax, rax
0x18001c150  jnz     short loc_18001C16C
0x18001c152  call    cs:__imp_GetLastError
0x18001c159  nop     dword ptr [rax+rax+00h]
0x18001c15e  test    eax, eax
0x18001c160  jle     short loc_18001C1A1
0x18001c162  movzx   eax, ax
0x18001c165  or      eax, 80070000h
0x18001c16a  jmp     short loc_18001C1A1
0x18001c16c  mov     [rsp+38h+pPrevCertContext], 0; pPrevCertContext
0x18001c175  mov     r9d, 60000h; dwFindType
0x18001c17b  xor     r8d, r8d; dwFindFlags
0x18001c17e  mov     [rsp+38h+pvPara], rsi; pvFindPara
0x18001c183  mov     edx, 10001h; dwCertEncodingType
0x18001c188  mov     rcx, rax; hCertStore
0x18001c18b  call    cs:__imp_CertFindCertificateInStore
0x18001c192  nop     dword ptr [rax+rax+00h]
0x18001c197  mov     [rdi], rax
0x18001c19a  test    rax, rax
0x18001c19d  jz      short loc_18001C152
0x18001c19f  xor     eax, eax
0x18001c1a1  mov     rbx, [rsp+38h+arg_0]
0x18001c1a6  mov     rsi, [rsp+38h+arg_8]
0x18001c1ab  add     rsp, 30h
0x18001c1af  pop     rdi
0x18001c1b0  retn
```
