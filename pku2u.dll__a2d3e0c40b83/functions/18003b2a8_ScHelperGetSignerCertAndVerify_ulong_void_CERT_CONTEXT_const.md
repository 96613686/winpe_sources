# ScHelperGetSignerCertAndVerify(ulong,void *,_CERT_CONTEXT const * *)

- ea: `0x18003b2a8`
- end: `0x18003b416`
- name: `?ScHelperGetSignerCertAndVerify@@YAHKPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(__int64, void *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018ff8`

## callees

- `0x18003b160`
- `0x18003b2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b3d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b3d3`
- `CRYPT32!CertOpenStore` at `0x18003b340`
- `CRYPT32!CertOpenStore` at `0x18003b340`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b3c5`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b3c5`
- `CRYPT32!CertCloseStore` at `0x18003b3e3`
- `CRYPT32!CertCloseStore` at `0x18003b3e3`
- `CRYPT32!CryptMsgControl` at `0x18003b38d`
- `CRYPT32!CryptMsgControl` at `0x18003b38d`
- `CRYPT32!CertGetSubjectCertificateFromStore` at `0x18003b359`
- `CRYPT32!CertGetSubjectCertificateFromStore` at `0x18003b359`
- `CRYPT32!CryptMsgGetParam` at `0x18003b2fd`
- `CRYPT32!CryptMsgGetParam` at `0x18003b2fd`

## pseudocode

```c
__int64 __fastcall ScHelperGetSignerCertAndVerify(__int64 a1, void *a2, const struct _CERT_CONTEXT **a3)
{
  struct _CERT_INFO *Param; // rdi
  const CERT_CONTEXT *v6; // rbx
  void *v7; // r15
  unsigned int v8; // r8d
  unsigned int v9; // esi
  HCERTSTORE v10; // rax
  PCCERT_CONTEXT SubjectCertificateFromStore; // rax
  DWORD LastError; // r14d
  __int128 pvCtrlPara; // [rsp+30h] [rbp-20h] BYREF
  __int128 v15; // [rsp+40h] [rbp-10h]
  int pvData; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+48h] BYREF

  pcbData = 4;
  Param = 0;
  v6 = 0;
  pvData = 0;
  v7 = 0;
  pvCtrlPara = 0;
  v15 = 0;
  if ( !CryptMsgGetParam(a2, 5u, 0, &pvData, &pcbData) )
    goto LABEL_10;
  if ( !pvData )
  {
    SetLastError(0x8009200E);
LABEL_10:
    v9 = 0;
    LastError = GetLastError();
    goto LABEL_11;
  }
  Param = (struct _CERT_INFO *)ScHelperAllocAndMsgGetParam(a2, 7u, v8);
  if ( !Param )
    goto LABEL_10;
  v9 = 1;
  v10 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 1u, a2);
  v7 = v10;
  if ( !v10 )
    goto LABEL_10;
  SubjectCertificateFromStore = CertGetSubjectCertificateFromStore(v10, 0x10001u, Param);
  v6 = SubjectCertificateFromStore;
  if ( !SubjectCertificateFromStore )
    goto LABEL_10;
  LODWORD(pvCtrlPara) = 32;
  *(_QWORD *)&v15 = 0x200000000LL;
  *((_QWORD *)&v15 + 1) = SubjectCertificateFromStore;
  if ( !CryptMsgControl(a2, 0, 0x13u, &pvCtrlPara) )
    goto LABEL_10;
  LastError = 0;
  if ( a3 )
  {
    *a3 = v6;
    v6 = 0;
  }
LABEL_11:
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( Param )
    LocalFree(Param);
  if ( v7 )
    CertCloseStore(v7, 0);
  if ( !v9 && LastError )
    SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x18003b2a8  mov     [rsp-28h+arg_8], rbx
0x18003b2ad  mov     [rsp-28h+arg_10], rsi
0x18003b2b2  mov     [rsp-28h+pvData], ecx
0x18003b2b6  push    rbp
0x18003b2b7  push    rdi
0x18003b2b8  push    r12
0x18003b2ba  push    r14
0x18003b2bc  push    r15
0x18003b2be  mov     rbp, rsp
0x18003b2c1  sub     rsp, 50h
0x18003b2c5  mov     r14, rdx
0x18003b2c8  mov     [rbp+arg_18], 4
0x18003b2cf  xorps   xmm0, xmm0
0x18003b2d2  lea     rax, [rbp+arg_18]
0x18003b2d6  mov     r12, r8
0x18003b2d9  mov     [rsp+50h+pcbData], rax; pcbData
0x18003b2de  xor     edi, edi
0x18003b2e0  lea     r9, [rbp+pvData]; pvData
0x18003b2e4  xor     ebx, ebx
0x18003b2e6  xor     r8d, r8d; dwIndex
0x18003b2e9  mov     rcx, r14; hCryptMsg
0x18003b2ec  mov     [rbp+pvData], ebx
0x18003b2ef  xor     r15d, r15d
0x18003b2f2  lea     edx, [rdi+5]; dwParamType
0x18003b2f5  movups  [rbp+pvCtrlPara], xmm0
0x18003b2f9  movups  [rbp+var_10], xmm0
0x18003b2fd  call    cs:__imp_CryptMsgGetParam
0x18003b303  test    eax, eax
0x18003b305  jz      loc_18003B3B2
0x18003b30b  cmp     [rbp+pvData], ebx
0x18003b30e  jbe     loc_18003B3A7
0x18003b314  lea     edx, [rdi+7]; dwParamType
0x18003b317  mov     rcx, r14; hCryptMsg
0x18003b31a  call    ?ScHelperAllocAndMsgGetParam@@YAPEAXPEAXKK@Z; ScHelperAllocAndMsgGetParam(void *,ulong,ulong)
0x18003b31f  mov     rdi, rax
0x18003b322  test    rax, rax
0x18003b325  jz      loc_18003B3B2
0x18003b32b  lea     esi, [rbx+1]
0x18003b32e  mov     [rsp+50h+pcbData], r14; pvPara
0x18003b333  mov     r9d, esi; dwFlags
0x18003b336  mov     ecx, esi; lpszStoreProvider
0x18003b338  xor     r8d, r8d; hCryptProv
0x18003b33b  mov     edx, 10001h; dwEncodingType
0x18003b340  call    cs:__imp_CertOpenStore
0x18003b346  mov     r15, rax
0x18003b349  test    rax, rax
0x18003b34c  jz      short loc_18003B3B2
0x18003b34e  mov     r8, rdi; pCertId
0x18003b351  mov     edx, 10001h; dwCertEncodingType
0x18003b356  mov     rcx, rax; hCertStore
0x18003b359  call    cs:__imp_CertGetSubjectCertificateFromStore
0x18003b35f  mov     rbx, rax
0x18003b362  test    rax, rax
0x18003b365  jz      short loc_18003B3B2
0x18003b367  lea     r9, [rbp+pvCtrlPara]; pvCtrlPara
0x18003b36b  mov     dword ptr [rbp+pvCtrlPara], 20h ; ' '
0x18003b372  xor     edx, edx; dwFlags
0x18003b374  mov     dword ptr [rbp+var_10], 0
0x18003b37b  lea     r8d, [rsi+12h]; dwCtrlType
0x18003b37f  mov     dword ptr [rbp+var_10+4], 2
0x18003b386  mov     rcx, r14; hCryptMsg
0x18003b389  mov     qword ptr [rbp+var_10+8], rax
0x18003b38d  call    cs:__imp_CryptMsgControl
0x18003b393  test    eax, eax
0x18003b395  jz      short loc_18003B3B2
0x18003b397  xor     r14d, r14d
0x18003b39a  test    r12, r12
0x18003b39d  jz      short loc_18003B3BD
0x18003b39f  mov     [r12], rbx
0x18003b3a3  xor     ebx, ebx
0x18003b3a5  jmp     short loc_18003B3BD
0x18003b3a7  mov     ecx, 8009200Eh; dwErrCode
0x18003b3ac  call    cs:__imp_SetLastError
0x18003b3b2  xor     esi, esi
0x18003b3b4  call    cs:__imp_GetLastError
0x18003b3ba  mov     r14d, eax
0x18003b3bd  test    rbx, rbx
0x18003b3c0  jz      short loc_18003B3CB
0x18003b3c2  mov     rcx, rbx; pCertContext
0x18003b3c5  call    cs:__imp_CertFreeCertificateContext
0x18003b3cb  test    rdi, rdi
0x18003b3ce  jz      short loc_18003B3D9
0x18003b3d0  mov     rcx, rdi; hMem
0x18003b3d3  call    cs:__imp_LocalFree
0x18003b3d9  test    r15, r15
0x18003b3dc  jz      short loc_18003B3E9
0x18003b3de  xor     edx, edx; dwFlags
0x18003b3e0  mov     rcx, r15; hCertStore
0x18003b3e3  call    cs:__imp_CertCloseStore
0x18003b3e9  test    esi, esi
0x18003b3eb  jnz     short loc_18003B3FB
0x18003b3ed  test    r14d, r14d
0x18003b3f0  jz      short loc_18003B3FB
0x18003b3f2  mov     ecx, r14d; dwErrCode
0x18003b3f5  call    cs:__imp_SetLastError
0x18003b3fb  lea     r11, [rsp+50h+var_s0]
0x18003b400  mov     eax, esi
0x18003b402  mov     rbx, [r11+38h]
0x18003b406  mov     rsi, [r11+40h]
0x18003b40a  mov     rsp, r11
0x18003b40d  pop     r15
0x18003b40f  pop     r14
0x18003b411  pop     r12
0x18003b413  pop     rdi
0x18003b414  pop     rbp
0x18003b415  retn
```
