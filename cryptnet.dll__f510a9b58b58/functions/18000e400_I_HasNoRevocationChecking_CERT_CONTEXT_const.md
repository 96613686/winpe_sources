# I_HasNoRevocationChecking(_CERT_CONTEXT const *)

- ea: `0x18000e400`
- end: `0x18000e4a4`
- name: `?I_HasNoRevocationChecking@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `164`
- prototype: `_BOOL8 __fastcall(struct _CERT_CONTEXT *pvPara)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ddb0`

## callees

- `0x18000e400`
- `0x180016500`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18000e42f`
- `CRYPT32!CertFindExtension` at `0x18000e45b`
- `CRYPT32!CertFindExtension` at `0x18000e42f`
- `CRYPT32!CertFindExtension` at `0x18000e45b`

## pseudocode

```c
_BOOL8 __fastcall I_HasNoRevocationChecking(struct _CERT_CONTEXT *pvPara)
{
  PCERT_INFO pCertInfo; // rax
  CERT_EXTENSION *rgExtension; // rdi
  DWORD cExtension; // ebx
  DWORD pcbUrlArray; // [rsp+50h] [rbp+8h] BYREF

  pCertInfo = pvPara->pCertInfo;
  rgExtension = pCertInfo->rgExtension;
  cExtension = pCertInfo->cExtension;
  if ( CertFindExtension("1.3.6.1.5.5.7.48.1.5", cExtension, rgExtension) )
    return 1;
  if ( CertFindExtension("2.5.29.31", cExtension, rgExtension) )
    return 0;
  pcbUrlArray = 0;
  return !CryptGetObjectUrl((LPCSTR)9, pvPara, 0, 0, &pcbUrlArray, 0, 0, 0);
}

```

## disassembly

```asm
0x18000e400  mov     [rsp+arg_8], rbx
0x18000e405  mov     [rsp+arg_10], rsi
0x18000e40a  push    rdi
0x18000e40b  sub     rsp, 40h
0x18000e40f  mov     rax, [rcx+18h]
0x18000e413  mov     rsi, rcx
0x18000e416  lea     rcx, a13615574815; "1.3.6.1.5.5.7.48.1.5"
0x18000e41d  mov     rdi, [rax+0C8h]
0x18000e424  mov     ebx, [rax+0C0h]
0x18000e42a  mov     r8, rdi; rgExtensions
0x18000e42d  mov     edx, ebx; cExtensions
0x18000e42f  call    cs:__imp_CertFindExtension
0x18000e435  test    rax, rax
0x18000e438  jz      short loc_18000E44F
0x18000e43a  mov     eax, 1
0x18000e43f  mov     rbx, [rsp+48h+arg_8]
0x18000e444  mov     rsi, [rsp+48h+arg_10]
0x18000e449  add     rsp, 40h
0x18000e44d  pop     rdi
0x18000e44e  retn
0x18000e44f  mov     r8, rdi; rgExtensions
0x18000e452  lea     rcx, pszObjId; "2.5.29.31"
0x18000e459  mov     edx, ebx; cExtensions
0x18000e45b  call    cs:__imp_CertFindExtension
0x18000e461  test    rax, rax
0x18000e464  jnz     short loc_18000E4A0
0x18000e466  mov     [rsp+48h+pvReserved], rax; pvReserved
0x18000e46b  xor     r9d, r9d; pUrlArray
0x18000e46e  mov     [rsp+48h+pcbUrlInfo], rax; pcbUrlInfo
0x18000e473  xor     r8d, r8d; dwFlags
0x18000e476  mov     [rsp+48h+pUrlInfo], rax; pUrlInfo
0x18000e47b  mov     rdx, rsi; pvPara
0x18000e47e  mov     [rsp+48h+arg_0], eax
0x18000e482  lea     rax, [rsp+48h+arg_0]
0x18000e487  lea     ecx, [r9+9]; pszUrlOid
0x18000e48b  mov     [rsp+48h+pcbUrlArray], rax; pcbUrlArray
0x18000e490  call    CryptGetObjectUrl
0x18000e495  xor     ecx, ecx
0x18000e497  test    eax, eax
0x18000e499  setz    cl
0x18000e49c  mov     eax, ecx
0x18000e49e  jmp     short loc_18000E43F
0x18000e4a0  xor     eax, eax
0x18000e4a2  jmp     short loc_18000E43F
```
