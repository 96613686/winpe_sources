# CACreateAutoEnrollmentObjectEx

- ea: `0x18002f730`
- end: `0x18002f7f5`
- name: `CACreateAutoEnrollmentObjectEx`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, struct _CMSG_SIGNED_ENCODE_INFO *, LPCSTR lpszStoreProvider, DWORD dwFlags, void *pvPara)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012450`
- `0x18002f350`
- `0x18002f730`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f7d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f7d2`
- `CRYPT32!CertOpenStore` at `0x18002f785`
- `CRYPT32!CertOpenStore` at `0x18002f785`
- `CRYPT32!CertCloseStore` at `0x18002f7e2`
- `CRYPT32!CertCloseStore` at `0x18002f7e2`
- `CRYPT32!CertAddEncodedCTLToStore` at `0x18002f7b4`
- `CRYPT32!CertAddEncodedCTLToStore` at `0x18002f7b4`

## pseudocode

```c
__int64 __fastcall CACreateAutoEnrollmentObjectEx(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct _CMSG_SIGNED_ENCODE_INFO *a4,
        LPCSTR lpszStoreProvider,
        DWORD dwFlags,
        void *pvPara)
{
  void *v7; // rbx
  unsigned int v8; // edi
  HCERTSTORE v9; // rax
  DWORD cbCtlEncoded; // [rsp+30h] [rbp-18h] BYREF
  BYTE *pbCtlEncoded; // [rsp+38h] [rbp-10h] BYREF

  pbCtlEncoded = 0;
  v7 = 0;
  cbCtlEncoded = 0;
  v8 = BuildAutoEnrollmentCTL(a1, a2, a3, a4, &pbCtlEncoded, &cbCtlEncoded);
  if ( !v8 )
  {
    v9 = CertOpenStore(lpszStoreProvider, 0, 0, dwFlags, pvPara);
    v7 = v9;
    if ( !v9 || !CertAddEncodedCTLToStore(v9, 1u, pbCtlEncoded, cbCtlEncoded, 3u, 0) )
      v8 = myHLastError();
  }
  if ( pbCtlEncoded )
    LocalFree(pbCtlEncoded);
  if ( v7 )
    CertCloseStore(v7, 0);
  return v8;
}

```

## disassembly

```asm
0x18002f730  mov     r11, rsp
0x18002f733  mov     [r11+8], rbx
0x18002f737  push    rdi
0x18002f738  sub     rsp, 40h
0x18002f73c  lea     rax, [r11-18h]
0x18002f740  mov     qword ptr [r11-10h], 0
0x18002f748  mov     [r11-20h], rax
0x18002f74c  xor     ebx, ebx
0x18002f74e  lea     rax, [r11-10h]
0x18002f752  mov     [rsp+48h+cbCtlEncoded], 0
0x18002f75a  mov     [r11-28h], rax
0x18002f75e  call    ?BuildAutoEnrollmentCTL@@YAJPEBG0PEAPEAGPEAU_CMSG_SIGNED_ENCODE_INFO@@PEAPEAEPEAK@Z; BuildAutoEnrollmentCTL(ushort const *,ushort const *,ushort * *,_CMSG_SIGNED_ENCODE_INFO *,uchar * *,ulong *)
0x18002f763  mov     edi, eax
0x18002f765  test    eax, eax
0x18002f767  jnz     short loc_18002F7C5
0x18002f769  mov     rax, [rsp+48h+arg_30]
0x18002f771  xor     r8d, r8d; hCryptProv
0x18002f774  mov     r9d, [rsp+48h+dwFlags]; dwFlags
0x18002f779  xor     edx, edx; dwEncodingType
0x18002f77b  mov     rcx, [rsp+48h+lpszStoreProvider]; lpszStoreProvider
0x18002f780  mov     [rsp+48h+pvPara], rax; pvPara
0x18002f785  call    cs:__imp_CertOpenStore
0x18002f78b  mov     rbx, rax
0x18002f78e  test    rax, rax
0x18002f791  jz      short loc_18002F7BE
0x18002f793  mov     r9d, [rsp+48h+cbCtlEncoded]; cbCtlEncoded
0x18002f798  lea     edx, [rdi+1]; dwMsgAndCertEncodingType
0x18002f79b  mov     r8, [rsp+48h+pbCtlEncoded]; pbCtlEncoded
0x18002f7a0  mov     rcx, rax; hCertStore
0x18002f7a3  mov     [rsp+48h+ppCtlContext], 0; ppCtlContext
0x18002f7ac  mov     dword ptr [rsp+48h+pvPara], 3; dwAddDisposition
0x18002f7b4  call    cs:__imp_CertAddEncodedCTLToStore
0x18002f7ba  test    eax, eax
0x18002f7bc  jnz     short loc_18002F7C5
0x18002f7be  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002f7c3  mov     edi, eax
0x18002f7c5  cmp     [rsp+48h+pbCtlEncoded], 0
0x18002f7cb  jz      short loc_18002F7D8
0x18002f7cd  mov     rcx, [rsp+48h+pbCtlEncoded]; hMem
0x18002f7d2  call    cs:__imp_LocalFree
0x18002f7d8  test    rbx, rbx
0x18002f7db  jz      short loc_18002F7E8
0x18002f7dd  xor     edx, edx; dwFlags
0x18002f7df  mov     rcx, rbx; hCertStore
0x18002f7e2  call    cs:__imp_CertCloseStore
0x18002f7e8  mov     rbx, [rsp+48h+arg_0]
0x18002f7ed  mov     eax, edi
0x18002f7ef  add     rsp, 40h
0x18002f7f3  pop     rdi
0x18002f7f4  retn
```
