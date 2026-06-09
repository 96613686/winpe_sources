# GetInstalledCertHelper

- ea: `0x18006ff4c`
- end: `0x18006ffec`
- name: `GetInstalledCertHelper`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18006fdd8`

## callees

- `0x18006ff4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff9e`
- `CRYPT32!CertOpenStore` at `0x18006ff8d`
- `CRYPT32!CertOpenStore` at `0x18006ff8d`
- `CRYPT32!CertFindCertificateInStore` at `0x18006ffd1`
- `CRYPT32!CertFindCertificateInStore` at `0x18006ffd1`

## pseudocode

```c
signed int __fastcall GetInstalledCertHelper(int a1, int a2, const void *a3, _QWORD *a4, PCCERT_CONTEXT *a5)
{
  DWORD v7; // edx
  const wchar_t *pvPara; // rax
  __int64 v9; // rcx
  HCERTSTORE v10; // rax
  signed int result; // eax
  PCCERT_CONTEXT CertificateInStore; // rax

  if ( a1 )
  {
    v7 = a2 | 0x4000;
    pvPara = L"Root";
    v9 = 10;
  }
  else
  {
    v7 = a2 | 1;
    pvPara = L"MY";
    v9 = 13;
  }
  v10 = CertOpenStore((LPCSTR)v9, 0, 0, v7, pvPara);
  *a4 = v10;
  if ( v10 )
  {
    CertificateInStore = CertFindCertificateInStore(v10, 1u, 0, 0x10000u, a3, *a5);
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
0x18006ff4c  mov     [rsp+arg_0], rbx
0x18006ff51  push    rdi
0x18006ff52  sub     rsp, 30h
0x18006ff56  mov     rdi, r8
0x18006ff59  mov     rbx, r9
0x18006ff5c  xor     r8d, r8d; hCryptProv
0x18006ff5f  test    ecx, ecx
0x18006ff61  jz      short loc_18006FF74
0x18006ff63  bts     edx, 0Eh
0x18006ff67  lea     rax, aRoot; "Root"
0x18006ff6e  lea     ecx, [r8+0Ah]
0x18006ff72  jmp     short loc_18006FF83
0x18006ff74  or      edx, 1
0x18006ff77  lea     rax, aMy; "MY"
0x18006ff7e  mov     ecx, 0Dh; lpszStoreProvider
0x18006ff83  mov     r9d, edx; dwFlags
0x18006ff86  mov     [rsp+38h+pvPara], rax; pvPara
0x18006ff8b  xor     edx, edx; dwEncodingType
0x18006ff8d  call    cs:__imp_CertOpenStore
0x18006ff93  mov     [rbx], rax
0x18006ff96  mov     rcx, rax; hCertStore
0x18006ff99  test    rax, rax
0x18006ff9c  jnz     short loc_18006FFB2
0x18006ff9e  call    cs:__imp_GetLastError
0x18006ffa4  test    eax, eax
0x18006ffa6  jle     short loc_18006FFE1
0x18006ffa8  movzx   eax, ax
0x18006ffab  or      eax, 80070000h
0x18006ffb0  jmp     short loc_18006FFE1
0x18006ffb2  mov     rbx, [rsp+38h+arg_20]
0x18006ffb7  xor     r8d, r8d; dwFindFlags
0x18006ffba  mov     r9d, 10000h; dwFindType
0x18006ffc0  mov     rax, [rbx]
0x18006ffc3  lea     edx, [r8+1]; dwCertEncodingType
0x18006ffc7  mov     [rsp+38h+pPrevCertContext], rax; pPrevCertContext
0x18006ffcc  mov     [rsp+38h+pvPara], rdi; pvFindPara
0x18006ffd1  call    cs:__imp_CertFindCertificateInStore
0x18006ffd7  mov     [rbx], rax
0x18006ffda  test    rax, rax
0x18006ffdd  jz      short loc_18006FF9E
0x18006ffdf  xor     eax, eax
0x18006ffe1  mov     rbx, [rsp+38h+arg_0]
0x18006ffe6  add     rsp, 30h
0x18006ffea  pop     rdi
0x18006ffeb  retn
```
