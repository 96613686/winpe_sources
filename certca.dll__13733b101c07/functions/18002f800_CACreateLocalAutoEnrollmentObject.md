# CACreateLocalAutoEnrollmentObject

- ea: `0x18002f800`
- end: `0x18002f8d4`
- name: `CACreateLocalAutoEnrollmentObject`
- size: `212`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, struct _CMSG_SIGNED_ENCODE_INFO *, DWORD)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012450`
- `0x18002f350`
- `0x18002f800`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f8ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f8ac`
- `CRYPT32!CertOpenStore` at `0x18002f85f`
- `CRYPT32!CertOpenStore` at `0x18002f85f`
- `CRYPT32!CertCloseStore` at `0x18002f8bc`
- `CRYPT32!CertCloseStore` at `0x18002f8bc`
- `CRYPT32!CertAddEncodedCTLToStore` at `0x18002f88e`
- `CRYPT32!CertAddEncodedCTLToStore` at `0x18002f88e`

## pseudocode

```c
__int64 __fastcall CACreateLocalAutoEnrollmentObject(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        struct _CMSG_SIGNED_ENCODE_INFO *a3,
        DWORD a4)
{
  void *v5; // rbx
  unsigned int v6; // edi
  HCERTSTORE v7; // rax
  DWORD cbCtlEncoded; // [rsp+30h] [rbp-18h] BYREF
  BYTE *pbCtlEncoded; // [rsp+38h] [rbp-10h] BYREF

  pbCtlEncoded = 0;
  cbCtlEncoded = 0;
  v5 = 0;
  v6 = BuildAutoEnrollmentCTL(a1, 0, a2, a3, &pbCtlEncoded, &cbCtlEncoded);
  if ( !v6 )
  {
    v7 = CertOpenStore((LPCSTR)0xD, 0, 0, a4, L"ACRS");
    v5 = v7;
    if ( !v7 || !CertAddEncodedCTLToStore(v7, 1u, pbCtlEncoded, cbCtlEncoded, 3u, 0) )
      v6 = myHLastError();
  }
  if ( pbCtlEncoded )
    LocalFree(pbCtlEncoded);
  if ( v5 )
    CertCloseStore(v5, 0);
  return v6;
}

```

## disassembly

```asm
0x18002f800  mov     r11, rsp
0x18002f803  mov     [r11+8], rbx
0x18002f807  mov     [r11+10h], rbp
0x18002f80b  push    rdi
0x18002f80c  sub     rsp, 40h
0x18002f810  lea     rax, [r11-18h]
0x18002f814  mov     qword ptr [r11-10h], 0
0x18002f81c  mov     [r11-20h], rax
0x18002f820  mov     ebp, r9d
0x18002f823  mov     r9, r8; struct _CMSG_SIGNED_ENCODE_INFO *
0x18002f826  mov     [rsp+48h+cbCtlEncoded], 0
0x18002f82e  lea     rax, [r11-10h]
0x18002f832  mov     r8, rdx; unsigned __int16 **
0x18002f835  xor     edx, edx; unsigned __int16 *
0x18002f837  mov     [r11-28h], rax
0x18002f83b  xor     ebx, ebx
0x18002f83d  call    ?BuildAutoEnrollmentCTL@@YAJPEBG0PEAPEAGPEAU_CMSG_SIGNED_ENCODE_INFO@@PEAPEAEPEAK@Z; BuildAutoEnrollmentCTL(ushort const *,ushort const *,ushort * *,_CMSG_SIGNED_ENCODE_INFO *,uchar * *,ulong *)
0x18002f842  mov     edi, eax
0x18002f844  test    eax, eax
0x18002f846  jnz     short loc_18002F89F
0x18002f848  lea     rax, aAcrs; "ACRS"
0x18002f84f  mov     r9d, ebp; dwFlags
0x18002f852  xor     r8d, r8d; hCryptProv
0x18002f855  mov     [rsp+48h+pvPara], rax; pvPara
0x18002f85a  xor     edx, edx; dwEncodingType
0x18002f85c  lea     ecx, [rbx+0Dh]; lpszStoreProvider
0x18002f85f  call    cs:__imp_CertOpenStore
0x18002f865  mov     rbx, rax
0x18002f868  test    rax, rax
0x18002f86b  jz      short loc_18002F898
0x18002f86d  mov     r9d, [rsp+48h+cbCtlEncoded]; cbCtlEncoded
0x18002f872  lea     edx, [rdi+1]; dwMsgAndCertEncodingType
0x18002f875  mov     r8, [rsp+48h+pbCtlEncoded]; pbCtlEncoded
0x18002f87a  mov     rcx, rax; hCertStore
0x18002f87d  mov     [rsp+48h+ppCtlContext], 0; ppCtlContext
0x18002f886  mov     dword ptr [rsp+48h+pvPara], 3; dwAddDisposition
0x18002f88e  call    cs:__imp_CertAddEncodedCTLToStore
0x18002f894  test    eax, eax
0x18002f896  jnz     short loc_18002F89F
0x18002f898  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002f89d  mov     edi, eax
0x18002f89f  cmp     [rsp+48h+pbCtlEncoded], 0
0x18002f8a5  jz      short loc_18002F8B2
0x18002f8a7  mov     rcx, [rsp+48h+pbCtlEncoded]; hMem
0x18002f8ac  call    cs:__imp_LocalFree
0x18002f8b2  test    rbx, rbx
0x18002f8b5  jz      short loc_18002F8C2
0x18002f8b7  xor     edx, edx; dwFlags
0x18002f8b9  mov     rcx, rbx; hCertStore
0x18002f8bc  call    cs:__imp_CertCloseStore
0x18002f8c2  mov     rbx, [rsp+48h+arg_0]
0x18002f8c7  mov     eax, edi
0x18002f8c9  mov     rbp, [rsp+48h+arg_8]
0x18002f8ce  add     rsp, 40h
0x18002f8d2  pop     rdi
0x18002f8d3  retn
```
