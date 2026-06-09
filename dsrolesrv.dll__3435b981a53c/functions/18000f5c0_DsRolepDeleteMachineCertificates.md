# DsRolepDeleteMachineCertificates

- ea: `0x18000f5c0`
- end: `0x18000f715`
- name: `DsRolepDeleteMachineCertificates`
- size: `341`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012460`

## callees

- `0x18000f5c0`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6aa`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f66b`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f66b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000f67f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000f67f`
- `CRYPT32!CertCloseStore` at `0x18000f6d0`
- `CRYPT32!CertCloseStore` at `0x18000f6d0`
- `CRYPT32!CertOpenStore` at `0x18000f632`
- `CRYPT32!CertOpenStore` at `0x18000f632`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18000f69c`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18000f69c`

## string_xrefs

- `0x18000f64b`: `vDC Cloning: CertOpenStore(%ws), status 0x%x\n`
- `0x18000f6b0`: `vDC Cloning: DeleteCertFromStore(%ws), status 0x%x\n`
- `0x18000f6db`: `vDC Cloning: Deleted %d/%d certificates found in %ws store\n`

## pseudocode

```c
__int64 DsRolepDeleteMachineCertificates()
{
  unsigned int v0; // ebp
  unsigned int v1; // r14d
  __int64 v2; // rdi
  unsigned __int64 v3; // rbx
  HCERTSTORE v4; // r15
  DWORD v5; // eax
  __int64 result; // rax
  const CERT_CONTEXT *v7; // rsi
  const CERT_CONTEXT *v8; // rax
  const CERT_CONTEXT *v9; // rax
  DWORD v10; // eax
  DWORD LastError; // eax
  _DWORD v12[2]; // [rsp+30h] [rbp-68h]
  const wchar_t *v13; // [rsp+38h] [rbp-60h]
  int v14; // [rsp+40h] [rbp-58h]
  const wchar_t *v15; // [rsp+48h] [rbp-50h]
  int v16; // [rsp+50h] [rbp-48h]
  const wchar_t *v17; // [rsp+58h] [rbp-40h]

  v12[0] = 0x20000;
  v13 = L"localMachine";
  v0 = 0;
  v14 = 589824;
  v15 = L"localMachineEnterprise";
  v1 = 0;
  v16 = 0x80000;
  v2 = 0;
  v17 = L"localMachineGroupPolicy";
  v3 = 0;
  do
  {
    v4 = CertOpenStore((LPCSTR)0xD, 0, 0, v12[v3 / 4] | 0x4200u, L"my");
    if ( v4 )
    {
      v7 = 0;
      while ( 1 )
      {
        v8 = CertEnumCertificatesInStore(v4, v7);
        v7 = v8;
        if ( !v8 )
          break;
        ++v1;
        v9 = CertDuplicateCertificateContext(v8);
        if ( v9 )
        {
          if ( CertDeleteCertificateFromStore(v9) )
          {
            ++v0;
          }
          else
          {
            LastError = GetLastError();
            DsRolepLogPrintRoutine(1, "vDC Cloning: DeleteCertFromStore(%ws), status 0x%x\n", (&v13)[v3 / 8], LastError);
          }
        }
        else
        {
          v10 = GetLastError();
          DsRolepLogPrintRoutine(1, "vDC Cloning: DupCertContext(%ws), status 0x%x\n", (&v13)[v3 / 8], v10);
        }
      }
      CertCloseStore(v4, 0);
      result = DsRolepLogPrintRoutine(
                 4,
                 "vDC Cloning: Deleted %d/%d certificates found in %ws store\n",
                 v0,
                 v1,
                 (&v13)[v3 / 8]);
    }
    else
    {
      v5 = GetLastError();
      result = DsRolepLogPrintRoutine(4, "vDC Cloning: CertOpenStore(%ws), status 0x%x\n", (&v13)[v3 / 8], v5);
    }
    ++v2;
    v3 += 16LL;
  }
  while ( v2 != 3 );
  return result;
}

```

## disassembly

```asm
0x18000f5c0  push    rbx
0x18000f5c2  push    rbp
0x18000f5c3  push    rsi
0x18000f5c4  push    rdi
0x18000f5c5  push    r14
0x18000f5c7  push    r15
0x18000f5c9  sub     rsp, 68h
0x18000f5cd  lea     rax, aLocalmachine; "localMachine"
0x18000f5d4  mov     [rsp+98h+var_68], 20000h
0x18000f5dc  mov     [rsp+98h+var_60], rax
0x18000f5e1  xor     ebp, ebp
0x18000f5e3  lea     rax, aLocalmachineen; "localMachineEnterprise"
0x18000f5ea  mov     [rsp+98h+var_58], 90000h
0x18000f5f2  mov     [rsp+98h+var_50], rax
0x18000f5f7  xor     r14d, r14d
0x18000f5fa  lea     rax, aLocalmachinegr; "localMachineGroupPolicy"
0x18000f601  mov     [rsp+98h+var_48], 80000h
0x18000f609  xor     edi, edi
0x18000f60b  mov     [rsp+98h+var_40], rax
0x18000f610  xor     ebx, ebx
0x18000f612  mov     r9d, [rsp+rbx+98h+var_68]
0x18000f617  lea     rax, aMy; "my"
0x18000f61e  xor     edx, edx; dwEncodingType
0x18000f620  mov     [rsp+98h+pvPara], rax; pvPara
0x18000f625  or      r9d, 4200h; dwFlags
0x18000f62c  xor     r8d, r8d; hCryptProv
0x18000f62f  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18000f632  call    cs:__imp_CertOpenStore
0x18000f638  mov     r15, rax
0x18000f63b  test    rax, rax
0x18000f63e  jnz     short loc_18000F663
0x18000f640  call    cs:__imp_GetLastError
0x18000f646  mov     r8, [rsp+rbx+98h+var_60]
0x18000f64b  lea     rdx, aVdcCloningCert; "vDC Cloning: CertOpenStore(%ws), status"...
0x18000f652  mov     r9d, eax
0x18000f655  lea     ecx, [r15+4]
0x18000f659  call    DsRolepLogPrintRoutine
0x18000f65e  jmp     loc_18000F6F7
0x18000f663  xor     esi, esi
0x18000f665  mov     rdx, rsi; pPrevCertContext
0x18000f668  mov     rcx, r15; hCertStore
0x18000f66b  call    cs:__imp_CertEnumCertificatesInStore
0x18000f671  mov     rsi, rax
0x18000f674  test    rax, rax
0x18000f677  jz      short loc_18000F6CB
0x18000f679  mov     rcx, rax; pCertContext
0x18000f67c  inc     r14d
0x18000f67f  call    cs:__imp_CertDuplicateCertificateContext
0x18000f685  test    rax, rax
0x18000f688  jnz     short loc_18000F699
0x18000f68a  call    cs:__imp_GetLastError
0x18000f690  lea     rdx, aVdcCloningDupc; "vDC Cloning: DupCertContext(%ws), statu"...
0x18000f697  jmp     short loc_18000F6B7
0x18000f699  mov     rcx, rax; pCertContext
0x18000f69c  call    cs:__imp_CertDeleteCertificateFromStore
0x18000f6a2  test    eax, eax
0x18000f6a4  jz      short loc_18000F6AA
0x18000f6a6  inc     ebp
0x18000f6a8  jmp     short loc_18000F665
0x18000f6aa  call    cs:__imp_GetLastError
0x18000f6b0  lea     rdx, aVdcCloningDele_0; "vDC Cloning: DeleteCertFromStore(%ws), "...
0x18000f6b7  mov     r8, [rsp+rbx+98h+var_60]
0x18000f6bc  mov     r9d, eax
0x18000f6bf  mov     ecx, 1
0x18000f6c4  call    DsRolepLogPrintRoutine
0x18000f6c9  jmp     short loc_18000F665
0x18000f6cb  xor     edx, edx; dwFlags
0x18000f6cd  mov     rcx, r15; hCertStore
0x18000f6d0  call    cs:__imp_CertCloseStore
0x18000f6d6  mov     rax, [rsp+rbx+98h+var_60]
0x18000f6db  lea     rdx, aVdcCloningDele; "vDC Cloning: Deleted %d/%d certificates"...
0x18000f6e2  mov     r9d, r14d
0x18000f6e5  mov     [rsp+98h+pvPara], rax
0x18000f6ea  mov     r8d, ebp
0x18000f6ed  mov     ecx, 4
0x18000f6f2  call    DsRolepLogPrintRoutine
0x18000f6f7  inc     rdi
0x18000f6fa  add     rbx, 10h
0x18000f6fe  cmp     rdi, 3
0x18000f702  jnz     loc_18000F612
0x18000f708  add     rsp, 68h
0x18000f70c  pop     r15
0x18000f70e  pop     r14
0x18000f710  pop     rdi
0x18000f711  pop     rsi
0x18000f712  pop     rbp
0x18000f713  pop     rbx
0x18000f714  retn
```
