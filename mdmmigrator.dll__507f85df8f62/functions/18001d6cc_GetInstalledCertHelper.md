# GetInstalledCertHelper

- ea: `0x18001d6cc`
- end: `0x18001d755`
- name: `GetInstalledCertHelper`
- size: `137`
- prototype: `signed int __fastcall(__int64, int, const void *, _QWORD *, PCCERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d590`

## callees

- `0x18001d6cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d707`
- `CRYPT32!CertOpenStore` at `0x18001d6f6`
- `CRYPT32!CertOpenStore` at `0x18001d6f6`
- `CRYPT32!CertFindCertificateInStore` at `0x18001d73a`
- `CRYPT32!CertFindCertificateInStore` at `0x18001d73a`

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
0x18001d6cc  mov     [rsp+arg_0], rbx
0x18001d6d1  push    rdi
0x18001d6d2  sub     rsp, 30h
0x18001d6d6  or      edx, 1
0x18001d6d9  lea     rax, aMy; "MY"
0x18001d6e0  mov     rbx, r9
0x18001d6e3  mov     [rsp+38h+pvPara], rax; pvPara
0x18001d6e8  mov     r9d, edx; dwFlags
0x18001d6eb  mov     rdi, r8
0x18001d6ee  xor     edx, edx; dwEncodingType
0x18001d6f0  xor     r8d, r8d; hCryptProv
0x18001d6f3  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18001d6f6  call    cs:__imp_CertOpenStore
0x18001d6fc  mov     [rbx], rax
0x18001d6ff  mov     rcx, rax; hCertStore
0x18001d702  test    rax, rax
0x18001d705  jnz     short loc_18001D71B
0x18001d707  call    cs:__imp_GetLastError
0x18001d70d  test    eax, eax
0x18001d70f  jle     short loc_18001D74A
0x18001d711  movzx   eax, ax
0x18001d714  or      eax, 80070000h
0x18001d719  jmp     short loc_18001D74A
0x18001d71b  mov     rbx, [rsp+38h+arg_20]
0x18001d720  xor     r8d, r8d; dwFindFlags
0x18001d723  mov     r9d, 10000h; dwFindType
0x18001d729  mov     rax, [rbx]
0x18001d72c  lea     edx, [r8+1]; dwCertEncodingType
0x18001d730  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x18001d735  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x18001d73a  call    cs:__imp_CertFindCertificateInStore
0x18001d740  mov     [rbx], rax
0x18001d743  test    rax, rax
0x18001d746  jz      short loc_18001D707
0x18001d748  xor     eax, eax
0x18001d74a  mov     rbx, [rsp+38h+arg_0]
0x18001d74f  add     rsp, 30h
0x18001d753  pop     rdi
0x18001d754  retn
```
