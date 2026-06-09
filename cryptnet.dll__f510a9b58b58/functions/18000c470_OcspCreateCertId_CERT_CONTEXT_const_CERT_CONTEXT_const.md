# OcspCreateCertId(_CERT_CONTEXT const *,_CERT_CONTEXT const *)

- ea: `0x18000c470`
- end: `0x18000c60d`
- name: `?OcspCreateCertId@@YAPEAU_OCSP_CERT_ID@@PEBU_CERT_CONTEXT@@0@Z`
- size: `413`
- prototype: `struct _OCSP_CERT_ID *__fastcall(const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800101e0`
- `0x18001e524`

## callees

- `0x18000a990`
- `0x18000c470`
- `0x180026552`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d8`
- `CRYPT32!CryptHashCertificate` at `0x18000c56e`
- `CRYPT32!CryptHashCertificate` at `0x18000c5bc`
- `CRYPT32!CryptHashCertificate` at `0x18000c56e`
- `CRYPT32!CryptHashCertificate` at `0x18000c5bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c4a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c4a0`

## pseudocode

```c
struct _OCSP_CERT_ID *__fastcall OcspCreateCertId(const struct _CERT_CONTEXT *a1, const struct _CERT_CONTEXT *a2)
{
  DWORD cbData; // eax
  char *v5; // rax
  char *v6; // rdi
  const char *v8; // rdx
  _BYTE *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r9
  _BYTE *v12; // rax
  DWORD v13; // edx
  char *v14; // r10

  cbData = a1->pCertInfo->SerialNumber.cbData;
  if ( cbData > 0xFFFFFF )
  {
    SetLastError(0x216u);
    return 0;
  }
  else
  {
    v5 = (char *)LocalAlloc(0x40u, cbData + 126);
    v6 = v5;
    if ( v5 )
    {
      v14 = v5 + 72;
      v10 = 2147483646;
      v9 = v5 + 72;
      v8 = "1.3.14.3.2.26";
      v11 = 14;
      do
      {
        if ( !v10 )
          break;
        if ( !*v8 )
          break;
        *v9++ = *v8++;
        --v10;
        --v11;
      }
      while ( v11 );
      v12 = v9 - 1;
      if ( v11 )
        v12 = v9;
      *v12 = 0;
      *((_QWORD *)v6 + 4) = v14 + 14;
      *(_QWORD *)v6 = v14;
      *((_DWORD *)v6 + 6) = 20;
      *((_QWORD *)v6 + 6) = v14 + 34;
      *((_DWORD *)v6 + 10) = 20;
      *((_QWORD *)v6 + 8) = v14 + 54;
      v13 = a1->pCertInfo->SerialNumber.cbData;
      *((_DWORD *)v6 + 14) = v13;
      memcpy_0(v14 + 54, a1->pCertInfo->SerialNumber.pbData, v13);
      if ( CryptHashCertificate(
             0,
             0x8004u,
             0,
             a1->pCertInfo->Issuer.pbData,
             a1->pCertInfo->Issuer.cbData,
             *((BYTE **)v6 + 4),
             (DWORD *)v6 + 6)
        && CryptHashCertificate(
             0,
             0x8004u,
             0,
             a2->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
             a2->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
             *((BYTE **)v6 + 6),
             (DWORD *)v6 + 10) )
      {
        return (struct _OCSP_CERT_ID *)v6;
      }
      else
      {
        operator delete(v6);
        return 0;
      }
    }
    else
    {
      SetLastError(0x8007000E);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000c470  mov     [rsp+arg_18], rbp
0x18000c475  push    r14
0x18000c477  sub     rsp, 40h
0x18000c47b  mov     rax, [rcx+18h]
0x18000c47f  mov     r14, rdx
0x18000c482  mov     rbp, rcx
0x18000c485  mov     eax, [rax+8]
0x18000c488  cmp     eax, 0FFFFFFh
0x18000c48d  ja      loc_18000C5D3
0x18000c493  lea     edx, [rax+7Eh]; uBytes
0x18000c496  mov     [rsp+48h+arg_10], rdi
0x18000c49b  mov     ecx, 40h ; '@'; uFlags
0x18000c4a0  call    cs:__imp_LocalAlloc
0x18000c4a6  mov     rdi, rax
0x18000c4a9  test    rax, rax
0x18000c4ac  jnz     loc_18000C5E5
0x18000c4b2  mov     ecx, 8007000Eh; dwErrCode
0x18000c4b7  call    cs:__imp_SetLastError
0x18000c4bd  mov     rax, rdi
0x18000c4c0  mov     rdi, [rsp+48h+arg_10]
0x18000c4c5  mov     rbp, [rsp+48h+arg_18]
0x18000c4ca  add     rsp, 40h
0x18000c4ce  pop     r14
0x18000c4d0  retn
0x18000c4d1  test    rcx, rcx
0x18000c4d4  jz      short loc_18000C4EF
0x18000c4d6  movzx   eax, byte ptr [rdx]
0x18000c4d9  test    al, al
0x18000c4db  jz      short loc_18000C4EF
0x18000c4dd  mov     [r8], al
0x18000c4e0  inc     rdx
0x18000c4e3  inc     r8
0x18000c4e6  dec     rcx
0x18000c4e9  sub     r9, 1
0x18000c4ed  jnz     short loc_18000C4D1
0x18000c4ef  lea     rax, [r8-1]
0x18000c4f3  test    r9, r9
0x18000c4f6  lea     rbx, [rdi+18h]
0x18000c4fa  cmovnz  rax, r8
0x18000c4fe  lea     rsi, [rdi+28h]
0x18000c502  mov     byte ptr [rax], 0
0x18000c505  lea     rax, [r10+0Eh]
0x18000c509  mov     [rbx+8], rax
0x18000c50d  add     rax, 14h
0x18000c511  mov     [rdi], r10
0x18000c514  mov     dword ptr [rbx], 14h
0x18000c51a  mov     [rsi+8], rax
0x18000c51e  mov     dword ptr [rsi], 14h
0x18000c524  lea     rcx, [rax+14h]; void *
0x18000c528  mov     [rdi+40h], rcx
0x18000c52c  mov     rax, [rbp+18h]
0x18000c530  mov     edx, [rax+8]
0x18000c533  mov     [rdi+38h], edx
0x18000c536  mov     r8d, edx; Size
0x18000c539  mov     rdx, [rbp+18h]
0x18000c53d  mov     rdx, [rdx+10h]; Src
0x18000c541  call    memcpy_0
0x18000c546  mov     r9, [rbp+18h]
0x18000c54a  xor     r8d, r8d; dwFlags
0x18000c54d  mov     rax, [rdi+20h]
0x18000c551  mov     edx, 8004h; Algid
0x18000c556  mov     [rsp+48h+pcbComputedHash], rbx; pcbComputedHash
0x18000c55b  xor     ecx, ecx; hCryptProv
0x18000c55d  mov     [rsp+48h+pbComputedHash], rax; pbComputedHash
0x18000c562  mov     eax, [r9+30h]
0x18000c566  mov     r9, [r9+38h]; pbEncoded
0x18000c56a  mov     [rsp+48h+cbEncoded], eax; cbEncoded
0x18000c56e  call    cs:__imp_CryptHashCertificate
0x18000c574  mov     rbx, [rsp+48h+arg_0]
0x18000c579  test    eax, eax
0x18000c57b  jnz     short loc_18000C591
0x18000c57d  mov     rcx, rdi; hMem
0x18000c580  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c585  mov     rsi, [rsp+48h+arg_8]
0x18000c58a  xor     eax, eax
0x18000c58c  jmp     loc_18000C4C0
0x18000c591  mov     rcx, [rdi+30h]
0x18000c595  xor     r8d, r8d; dwFlags
0x18000c598  mov     r9, [r14+18h]
0x18000c59c  mov     edx, 8004h; Algid
0x18000c5a1  mov     [rsp+48h+pcbComputedHash], rsi; pcbComputedHash
0x18000c5a6  mov     [rsp+48h+pbComputedHash], rcx; pbComputedHash
0x18000c5ab  mov     ecx, [r9+78h]
0x18000c5af  mov     r9, [r9+80h]; pbEncoded
0x18000c5b6  mov     [rsp+48h+cbEncoded], ecx; cbEncoded
0x18000c5ba  xor     ecx, ecx; hCryptProv
0x18000c5bc  call    cs:__imp_CryptHashCertificate
0x18000c5c2  test    eax, eax
0x18000c5c4  jz      short loc_18000C57D
0x18000c5c6  mov     rsi, [rsp+48h+arg_8]
0x18000c5cb  mov     rax, rdi
0x18000c5ce  jmp     loc_18000C4C0
0x18000c5d3  mov     ecx, 216h; dwErrCode
0x18000c5d8  call    cs:__imp_SetLastError
0x18000c5de  xor     eax, eax
0x18000c5e0  jmp     loc_18000C4C5
0x18000c5e5  mov     [rsp+48h+arg_0], rbx
0x18000c5ea  mov     [rsp+48h+arg_8], rsi
0x18000c5ef  lea     r10, [rax+48h]
0x18000c5f3  mov     ecx, 7FFFFFFEh
0x18000c5f8  mov     r8, r10
0x18000c5fb  lea     rdx, a13143226; "1.3.14.3.2.26"
0x18000c602  mov     r9d, 0Eh
0x18000c608  jmp     loc_18000C4D1
```
