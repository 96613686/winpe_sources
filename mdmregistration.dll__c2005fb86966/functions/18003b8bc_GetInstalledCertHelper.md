# GetInstalledCertHelper

- ea: `0x18003b8bc`
- end: `0x18003b958`
- name: `GetInstalledCertHelper`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003b750`

## callees

- `0x18003b8bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8fd`
- `CRYPT32!CertOpenStore` at `0x18003b8e6`
- `CRYPT32!CertOpenStore` at `0x18003b8e6`
- `CRYPT32!CertFindCertificateInStore` at `0x18003b936`
- `CRYPT32!CertFindCertificateInStore` at `0x18003b936`

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
0x18003b8bc  mov     [rsp+arg_0], rbx
0x18003b8c1  push    rdi
0x18003b8c2  sub     rsp, 30h
0x18003b8c6  or      edx, 1
0x18003b8c9  lea     rax, aMy; "MY"
0x18003b8d0  mov     rbx, r9
0x18003b8d3  mov     [rsp+38h+pvPara], rax; pvPara
0x18003b8d8  mov     r9d, edx; dwFlags
0x18003b8db  mov     rdi, r8
0x18003b8de  xor     edx, edx; dwEncodingType
0x18003b8e0  xor     r8d, r8d; hCryptProv
0x18003b8e3  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18003b8e6  call    cs:__imp_CertOpenStore
0x18003b8ed  nop     dword ptr [rax+rax+00h]
0x18003b8f2  mov     [rbx], rax
0x18003b8f5  mov     rcx, rax; hCertStore
0x18003b8f8  test    rax, rax
0x18003b8fb  jnz     short loc_18003B917
0x18003b8fd  call    cs:__imp_GetLastError
0x18003b904  nop     dword ptr [rax+rax+00h]
0x18003b909  test    eax, eax
0x18003b90b  jle     short loc_18003B94C
0x18003b90d  movzx   eax, ax
0x18003b910  or      eax, 80070000h
0x18003b915  jmp     short loc_18003B94C
0x18003b917  mov     rbx, [rsp+38h+arg_20]
0x18003b91c  xor     r8d, r8d; dwFindFlags
0x18003b91f  mov     r9d, 10000h; dwFindType
0x18003b925  mov     rax, [rbx]
0x18003b928  lea     edx, [r8+1]; dwCertEncodingType
0x18003b92c  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x18003b931  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x18003b936  call    cs:__imp_CertFindCertificateInStore
0x18003b93d  nop     dword ptr [rax+rax+00h]
0x18003b942  mov     [rbx], rax
0x18003b945  test    rax, rax
0x18003b948  jz      short loc_18003B8FD
0x18003b94a  xor     eax, eax
0x18003b94c  mov     rbx, [rsp+38h+arg_0]
0x18003b951  add     rsp, 30h
0x18003b955  pop     rdi
0x18003b956  retn
```
