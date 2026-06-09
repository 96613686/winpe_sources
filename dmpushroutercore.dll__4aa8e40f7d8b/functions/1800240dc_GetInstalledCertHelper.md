# GetInstalledCertHelper

- ea: `0x1800240dc`
- end: `0x180024165`
- name: `GetInstalledCertHelper`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180023fa0`

## callees

- `0x1800240dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024117`
- `CRYPT32!CertFindCertificateInStore` at `0x18002414a`
- `CRYPT32!CertFindCertificateInStore` at `0x18002414a`
- `CRYPT32!CertOpenStore` at `0x180024106`
- `CRYPT32!CertOpenStore` at `0x180024106`

## pseudocode

```c
signed int __fastcall GetInstalledCertHelper(__int64 a1, int a2, const void *a3, _QWORD *a4, PCCERT_CONTEXT *a5)
{
  HCERTSTORE v7; // rax
  signed int result; // eax
  PCCERT_CONTEXT CertificateInStore; // rax

  v7 = CertOpenStore((LPCSTR)0xD, 0, 0, a2 | 1u, L"MY");
  *a4 = v7;
  if ( v7 )
  {
    CertificateInStore = CertFindCertificateInStore(v7, 1u, 0, 0x10000u, a3, *a5);
    *a5 = CertificateInStore;
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
0x1800240dc  mov     [rsp+arg_0], rbx
0x1800240e1  push    rdi
0x1800240e2  sub     rsp, 30h
0x1800240e6  or      edx, 1
0x1800240e9  lea     rax, aMy; "MY"
0x1800240f0  mov     rbx, r9
0x1800240f3  mov     [rsp+38h+pvPara], rax; pvPara
0x1800240f8  mov     r9d, edx; dwFlags
0x1800240fb  mov     rdi, r8
0x1800240fe  xor     edx, edx; dwEncodingType
0x180024100  xor     r8d, r8d; hCryptProv
0x180024103  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x180024106  call    cs:__imp_CertOpenStore
0x18002410c  mov     [rbx], rax
0x18002410f  mov     rcx, rax; hCertStore
0x180024112  test    rax, rax
0x180024115  jnz     short loc_18002412B
0x180024117  call    cs:__imp_GetLastError
0x18002411d  test    eax, eax
0x18002411f  jle     short loc_18002415A
0x180024121  movzx   eax, ax
0x180024124  or      eax, 80070000h
0x180024129  jmp     short loc_18002415A
0x18002412b  mov     rbx, [rsp+38h+arg_20]
0x180024130  xor     r8d, r8d; dwFindFlags
0x180024133  mov     r9d, 10000h; dwFindType
0x180024139  mov     rax, [rbx]
0x18002413c  lea     edx, [r8+1]; dwCertEncodingType
0x180024140  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x180024145  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x18002414a  call    cs:__imp_CertFindCertificateInStore
0x180024150  mov     [rbx], rax
0x180024153  test    rax, rax
0x180024156  jz      short loc_180024117
0x180024158  xor     eax, eax
0x18002415a  mov     rbx, [rsp+38h+arg_0]
0x18002415f  add     rsp, 30h
0x180024163  pop     rdi
0x180024164  retn
```
