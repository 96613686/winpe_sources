# CompareCertificate(__int64,__int64,__int64)

- ea: `0x180007bf0`
- end: `0x180007d53`
- name: `?CompareCertificate@@YAH_J00@Z`
- size: `355`
- prototype: `int(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007bf0`
- `0x180032638`
- `0x180032734`
- `0x18003275c`
- `0x180032970`
- `0x1800329b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007d3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007d3e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007c60`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007c60`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007d1f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007d1f`

## pseudocode

```c
__int64 __fastcall CompareCertificate(const struct _CERT_CONTEXT *a1, const struct _CERT_CONTEXT *a2, int a3)
{
  unsigned int v3; // ebx
  PCNZWCH lpString1; // [rsp+50h] [rbp+20h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp+28h] BYREF

  v3 = 0;
  lpString1 = 0;
  lpString2 = 0;
  if ( !a1 || !a2 )
    goto LABEL_23;
  switch ( (unsigned __int16)a3 )
  {
    case 1u:
      GetCertIssuer(a1, (unsigned __int16 **)&lpString1);
      GetCertIssuer(a2, (unsigned __int16 **)&lpString2);
      goto LABEL_18;
    case 2u:
      GetCertSubject(a1, (unsigned __int16 **)&lpString1);
      GetCertSubject(a2, (unsigned __int16 **)&lpString2);
      goto LABEL_18;
    case 8u:
      GetCertPurpose(a1, (unsigned __int16 **)&lpString1);
      GetCertPurpose(a2, (unsigned __int16 **)&lpString2);
      goto LABEL_18;
    case 0x10u:
      GetCertFriendlyName(a1, (unsigned __int16 **)&lpString1);
      GetCertFriendlyName(a2, (unsigned __int16 **)&lpString2);
      goto LABEL_18;
    case 0x20u:
      if ( !(unsigned int)GetCertLocation(a1, (unsigned __int16 **)&lpString1) )
      {
        lpString1 = 0;
        goto LABEL_23;
      }
      if ( !(unsigned int)GetCertLocation(a2, (unsigned __int16 **)&lpString2) )
      {
        lpString2 = 0;
        goto LABEL_23;
      }
      goto LABEL_18;
  }
  if ( (unsigned __int16)a3 != 4 )
  {
LABEL_18:
    if ( !lpString1 || !lpString2 )
      goto LABEL_23;
    v3 = CompareStringW(0x400u, 1u, lpString1, -1, lpString2, -1) - 2;
    goto LABEL_21;
  }
  v3 = CompareFileTime(&a1->pCertInfo->NotAfter, &a2->pCertInfo->NotAfter);
LABEL_21:
  if ( (a3 & 0x20000) != 0 )
    v3 = -v3;
LABEL_23:
  LocalFree((HLOCAL)lpString1);
  LocalFree((HLOCAL)lpString2);
  return v3;
}

```

## disassembly

```asm
0x180007bf0  mov     [rsp-18h+arg_10], rbx
0x180007bf5  push    rbp
0x180007bf6  push    rsi
0x180007bf7  push    rdi
0x180007bf8  mov     rbp, rsp
0x180007bfb  sub     rsp, 30h
0x180007bff  xor     ebx, ebx
0x180007c01  mov     rsi, r8
0x180007c04  mov     [rbp+lpString1], rbx
0x180007c08  mov     rdi, rdx
0x180007c0b  mov     [rbp+arg_8], rbx
0x180007c0f  test    rcx, rcx
0x180007c12  jz      loc_180007D30
0x180007c18  test    rdx, rdx
0x180007c1b  jz      loc_180007D30
0x180007c21  movzx   edx, si
0x180007c24  mov     eax, edx
0x180007c26  sub     eax, 1
0x180007c29  jz      loc_180007CE1
0x180007c2f  sub     eax, 1
0x180007c32  jz      loc_180007CCA
0x180007c38  sub     eax, 6
0x180007c3b  jz      short loc_180007CB3
0x180007c3d  sub     eax, 8
0x180007c40  jz      short loc_180007C9C
0x180007c42  cmp     eax, 10h
0x180007c45  jz      short loc_180007C6D
0x180007c47  cmp     edx, 4
0x180007c4a  jnz     loc_180007CF6
0x180007c50  mov     rdx, [rdi+18h]
0x180007c54  mov     rcx, [rcx+18h]
0x180007c58  add     rdx, 48h ; 'H'; lpFileTime2
0x180007c5c  add     rcx, 48h ; 'H'; lpFileTime1
0x180007c60  call    cs:__imp_CompareFileTime
0x180007c66  mov     ebx, eax
0x180007c68  jmp     loc_180007D28
0x180007c6d  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x180007c71  call    ?GetCertLocation@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertLocation(_CERT_CONTEXT const *,ushort * *)
0x180007c76  test    eax, eax
0x180007c78  jnz     short loc_180007C83
0x180007c7a  mov     [rbp+lpString1], rbx
0x180007c7e  jmp     loc_180007D30
0x180007c83  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180007c87  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180007c8a  call    ?GetCertLocation@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertLocation(_CERT_CONTEXT const *,ushort * *)
0x180007c8f  test    eax, eax
0x180007c91  jnz     short loc_180007CF6
0x180007c93  mov     [rbp+arg_8], rbx
0x180007c97  jmp     loc_180007D30
0x180007c9c  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x180007ca0  call    ?GetCertFriendlyName@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertFriendlyName(_CERT_CONTEXT const *,ushort * *)
0x180007ca5  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180007ca9  mov     rcx, rdi; pCertContext
0x180007cac  call    ?GetCertFriendlyName@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertFriendlyName(_CERT_CONTEXT const *,ushort * *)
0x180007cb1  jmp     short loc_180007CF6
0x180007cb3  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x180007cb7  call    ?GetCertPurpose@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertPurpose(_CERT_CONTEXT const *,ushort * *)
0x180007cbc  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180007cc0  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180007cc3  call    ?GetCertPurpose@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertPurpose(_CERT_CONTEXT const *,ushort * *)
0x180007cc8  jmp     short loc_180007CF6
0x180007cca  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x180007cce  call    ?GetCertSubject@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertSubject(_CERT_CONTEXT const *,ushort * *)
0x180007cd3  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180007cd7  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180007cda  call    ?GetCertSubject@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertSubject(_CERT_CONTEXT const *,ushort * *)
0x180007cdf  jmp     short loc_180007CF6
0x180007ce1  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x180007ce5  call    ?GetCertIssuer@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertIssuer(_CERT_CONTEXT const *,ushort * *)
0x180007cea  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180007cee  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180007cf1  call    ?GetCertIssuer@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertIssuer(_CERT_CONTEXT const *,ushort * *)
0x180007cf6  mov     r8, [rbp+lpString1]; lpString1
0x180007cfa  test    r8, r8
0x180007cfd  jz      short loc_180007D30
0x180007cff  mov     rax, [rbp+arg_8]
0x180007d03  test    rax, rax
0x180007d06  jz      short loc_180007D30
0x180007d08  or      r9d, 0FFFFFFFFh; cchCount1
0x180007d0c  mov     ecx, 400h; Locale
0x180007d11  mov     [rsp+30h+cchCount2], r9d; cchCount2
0x180007d16  mov     [rsp+30h+lpString2], rax; lpString2
0x180007d1b  lea     edx, [r9+2]; dwCmpFlags
0x180007d1f  call    cs:__imp_CompareStringW
0x180007d25  lea     ebx, [rax-2]
0x180007d28  bt      esi, 11h
0x180007d2c  jnb     short loc_180007D30
0x180007d2e  neg     ebx
0x180007d30  mov     rcx, [rbp+lpString1]; hMem
0x180007d34  call    cs:__imp_LocalFree
0x180007d3a  mov     rcx, [rbp+arg_8]; hMem
0x180007d3e  call    cs:__imp_LocalFree
0x180007d44  mov     eax, ebx
0x180007d46  mov     rbx, [rsp+30h+arg_10]
0x180007d4b  add     rsp, 30h
0x180007d4f  pop     rdi
0x180007d50  pop     rsi
0x180007d51  pop     rbp
0x180007d52  retn
```
