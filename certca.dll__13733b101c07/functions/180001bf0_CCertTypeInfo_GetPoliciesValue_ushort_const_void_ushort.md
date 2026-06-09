# CCertTypeInfo::_GetPoliciesValue(ushort const *,void *,ushort * *)

- ea: `0x180001bf0`
- end: `0x180002270`
- name: `?_GetPoliciesValue@CCertTypeInfo@@IEAAJPEBGPEAXPEAPEAG@Z`
- size: `1664`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, const unsigned __int16 *, struct ldap *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800025a0`

## callees

- `0x180001920`
- `0x180001bf0`
- `0x180002ef0`
- `0x180004c30`
- `0x180008610`
- `0x180013a86`
- `0x18002c24c`
- `0x180032380`

## import_xrefs

- `msvcrt!wcschr` at `0x180001ee0`
- `msvcrt!wcschr` at `0x180001ee0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001e4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001e91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001fd0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001e4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001e91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001fd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000218c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002248`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000218c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002248`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002143`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001fb9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002010`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001fb9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002010`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001c88`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001cd3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001d10`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001d4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001d8a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001dc4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001c88`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001cd3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001d10`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001d4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001d8a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001dc4`
- `CRYPT32!CryptEncodeObject` at `0x18000205d`
- `CRYPT32!CryptEncodeObject` at `0x180002139`
- `CRYPT32!CryptEncodeObject` at `0x18000205d`
- `CRYPT32!CryptEncodeObject` at `0x180002139`

## string_xrefs

- `0x180001c61`: `msPKI-Template-Schema-Version`
- `0x180001d63`: `msPKI-Template-Schema-Version`
- `0x180001ca9`: `msPKI-Template-Minor-Revision`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_GetPoliciesValue(
        CCertTypeInfo *this,
        const unsigned __int16 *a2,
        struct ldap *a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // r14d
  HLOCAL v7; // r12
  unsigned int Property; // edi
  __int64 v10; // r13
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  size_t v13; // rdi
  HLOCAL v14; // rax
  unsigned int *v15; // rbx
  wchar_t *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  CCertTypeInfo *v19; // rcx
  int PolicyQualifiers; // eax
  unsigned int v21; // eax
  int v22; // ebx
  CHAR *v23; // rax
  unsigned int *v24; // rdx
  int v25; // eax
  const char *v26; // rcx
  signed int LastError; // eax
  bool v28; // cc
  unsigned int v29; // r14d
  int v30; // ecx
  unsigned __int16 *v31; // rsi
  __int64 v32; // r15
  unsigned int *v33; // rsi
  __int64 i; // rbx
  DWORD pcbEncoded; // [rsp+40h] [rbp-40h] BYREF
  void *Src; // [rsp+48h] [rbp-38h] BYREF
  unsigned int *v37; // [rsp+50h] [rbp-30h]
  HLOCAL hMem; // [rsp+58h] [rbp-28h]
  HLOCAL v39; // [rsp+60h] [rbp-20h] BYREF
  BYTE *v40; // [rsp+68h] [rbp-18h]
  __int128 pvStructInfo; // [rsp+70h] [rbp-10h] BYREF

  v4 = 0;
  Src = 0;
  v39 = 0;
  v7 = 0;
  pvStructInfo = 0;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !a2 )
  {
    Property = -2147467261;
    goto LABEL_82;
  }
  if ( *((_DWORD *)this + 22) || !(unsigned int)IsV2Property(a2) )
  {
    Property = 0;
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Template-Minor-Revision", -1) == 2 )
    {
      LODWORD(Src) = *((_DWORD *)this + 16);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-RA-Signature", -1) == 2 )
    {
      LODWORD(Src) = *((_DWORD *)this + 21);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Minimal-Key-Size", -1) == 2 )
    {
      LODWORD(Src) = *((_DWORD *)this + 20);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Template-Schema-Version", -1) == 2 )
    {
      LODWORD(Src) = *((_DWORD *)this + 22);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"revision", -1) == 2 )
    {
      LODWORD(Src) = *((_DWORD *)this + 36);
    }
    else
    {
      Property = CCertTypeInfo::GetProperty(this, a2, (unsigned __int16 ***)&Src);
    }
    if ( Property )
      goto LABEL_82;
LABEL_21:
    if ( !Src )
      goto LABEL_80;
    LODWORD(v10) = 0;
    if ( !*(_QWORD *)Src )
      goto LABEL_80;
    do
      v10 = (unsigned int)(v10 + 1);
    while ( *((_QWORD *)Src + v10) );
    if ( !(_DWORD)v10 )
    {
LABEL_80:
      Property = 0;
      goto LABEL_82;
    }
    v11 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v11 < (unsigned int)v10 )
    {
      Property = -2147024362;
      CSPrintErrorLineFileData2(0, 0x18AA0328u, -2147024362, 0);
      goto LABEL_82;
    }
    v12 = 8 * v11;
    if ( v12 > 0xFFFFFFFF )
    {
      Property = -2147024362;
      CSPrintErrorLineFileData2(0, 0x18AD0328u, -2147024362, 0);
      goto LABEL_82;
    }
    v13 = (unsigned int)v12;
    v14 = LocalAlloc(0x40u, (unsigned int)v12);
    hMem = v14;
    if ( !v14 )
    {
      Property = -2147024882;
      goto LABEL_82;
    }
    memcpy_0(v14, Src, v13);
    pvStructInfo = 0;
    v37 = (unsigned int *)LocalAlloc(0x40u, 24 * v10);
    v15 = v37;
    if ( !v37 )
    {
      Property = -2147024882;
      LocalFree(hMem);
      goto LABEL_82;
    }
    Property = 0;
    v40 = 0;
    while ( 2 )
    {
      v16 = wcschr(*((const wchar_t **)hMem + v4), 0x3Bu);
      if ( v16 )
        *v16 = 0;
      v17 = -1;
      while ( aMspkiCertifica[v17 + 1] == a2[v17 + 1] )
      {
        v17 += 2;
        if ( v17 == 25 )
        {
          v18 = I_CAOIDGetProperty(*((const unsigned __int16 **)hMem + v4), 2u, &v39, a3);
          v7 = v39;
          if ( !v18 && v39 )
          {
            PolicyQualifiers = CCertTypeInfo::_GetPolicyQualifiers(
                                 v19,
                                 (unsigned __int16 *)v39,
                                 &v15[6 * v4 + 2],
                                 (struct _CERT_POLICY_QUALIFIER_INFO **)&v15[6 * v4 + 4]);
            Property = PolicyQualifiers;
            if ( PolicyQualifiers )
            {
              CSPrintErrorLineFileData2(0, 0x18DB0328u, PolicyQualifiers, 0);
              v29 = 0;
              goto LABEL_69;
            }
            if ( v7 )
              LocalFree(v7);
            v7 = 0;
            v39 = 0;
          }
          break;
        }
        if ( aMspkiCertifica[v17] != a2[v17] )
          break;
      }
      v21 = WideCharToMultiByte(0, 0, *((LPCWCH *)hMem + v4), -1, 0, 0, 0, 0);
      v22 = v21;
      if ( !v21 )
      {
        v15 = v37;
        Property = -2147418113;
        v29 = 0;
        goto LABEL_69;
      }
      v23 = (CHAR *)LocalAlloc(0x40u, v21);
      v24 = v37;
      *(_QWORD *)&v37[6 * v4] = v23;
      if ( !v23 )
      {
        Property = -2147024882;
        v29 = 0;
        v15 = v24;
        goto LABEL_69;
      }
      v25 = WideCharToMultiByte(0, 0, *((LPCWCH *)hMem + v4), -1, v23, v22, 0, 0);
      v15 = v37;
      if ( !v25 )
      {
        Property = -2147418113;
        v29 = 0;
        goto LABEL_69;
      }
      if ( ++v4 < (unsigned int)v10 )
        continue;
      break;
    }
    LODWORD(pvStructInfo) = v10;
    *((_QWORD *)&pvStructInfo + 1) = v37;
    pcbEncoded = 0;
    if ( CryptEncodeObject(1u, "2.5.29.32", &pvStructInfo, 0, &pcbEncoded) )
    {
      v40 = (BYTE *)CertAllocStringByteLen(v26, pcbEncoded);
      v31 = (unsigned __int16 *)v40;
      if ( !v40 )
      {
        Property = -2147024882;
        goto LABEL_68;
      }
      if ( CryptEncodeObject(1u, "2.5.29.32", &pvStructInfo, v40, &pcbEncoded) )
      {
        *a4 = v31;
        v40 = 0;
        goto LABEL_68;
      }
      LastError = GetLastError();
      Property = LastError;
      v28 = LastError < 1;
      if ( LastError == 1 )
      {
LABEL_51:
        CSPrintErrorLineFileData2(L"S_FALSE == hr", 0x65F01CAu, 1, 0);
LABEL_68:
        v29 = 0;
LABEL_69:
        v32 = 0;
        do
        {
          v33 = &v15[6 * v32];
          LocalFree(*(HLOCAL *)v33);
          if ( *((_QWORD *)v33 + 2) )
          {
            for ( i = 0; (unsigned int)i < v33[2]; i = (unsigned int)(i + 1) )
              LocalFree(*(HLOCAL *)(*((_QWORD *)v33 + 2) + 24 * i + 16));
            LocalFree(*((HLOCAL *)v33 + 2));
            v15 = v37;
          }
          ++v29;
          ++v32;
        }
        while ( v29 < (unsigned int)v10 );
        LocalFree(v15);
        if ( v40 )
          LocalFree(v40 - 4);
        LocalFree(hMem);
        goto LABEL_82;
      }
    }
    else
    {
      LastError = GetLastError();
      Property = LastError;
      v28 = LastError < 1;
      if ( LastError == 1 )
        goto LABEL_51;
    }
    if ( !v28 )
    {
      if ( LastError > 0 )
        Property = (unsigned __int16)LastError | 0x80070000;
      v30 = Property;
      if ( !(_WORD)Property )
        v30 = -2147418113;
      Property = v30;
    }
    goto LABEL_68;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"msPKI-Template-Schema-Version", -1) == 2 )
  {
    LODWORD(Src) = 1;
    goto LABEL_21;
  }
  Property = -2147023728;
LABEL_82:
  if ( Src )
    LocalFree(Src);
  if ( v7 )
    LocalFree(v7);
  return Property;
}

```

## disassembly

```asm
0x180001bf0  mov     [rsp-38h+arg_18], r9
0x180001bf5  mov     [rsp-38h+arg_10], r8
0x180001bfa  push    rbp
0x180001bfb  push    rbx
0x180001bfc  push    rsi
0x180001bfd  push    rdi
0x180001bfe  push    r12
0x180001c00  push    r14
0x180001c02  push    r15
0x180001c04  mov     rbp, rsp
0x180001c07  sub     rsp, 80h
0x180001c0e  xor     r14d, r14d
0x180001c11  xorps   xmm0, xmm0
0x180001c14  mov     [rbp+Src], r14
0x180001c18  mov     r15, r9
0x180001c1b  mov     [rbp+var_20], r14
0x180001c1f  mov     rsi, rdx
0x180001c22  mov     rbx, rcx
0x180001c25  mov     r12d, r14d
0x180001c28  movups  [rbp+pvStructInfo], xmm0
0x180001c2c  test    r9, r9
0x180001c2f  jnz     short loc_180001C3B
0x180001c31  mov     eax, 80004003h
0x180001c36  jmp     loc_18000225E
0x180001c3b  mov     [rsp+80h+arg_0], r13
0x180001c43  mov     [r9], r14
0x180001c46  test    rsi, rsi
0x180001c49  jz      loc_180002232
0x180001c4f  cmp     [rcx+58h], r12d
0x180001c53  jnz     short loc_180001CA9
0x180001c55  mov     rcx, rsi; lpString1
0x180001c58  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180001c5d  test    eax, eax
0x180001c5f  jz      short loc_180001CA9
0x180001c61  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001c68  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001c70  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001c76  mov     [rsp+80h+lpString2], rax; lpString2
0x180001c7b  mov     r8, rsi; lpString1
0x180001c7e  mov     edx, 1; dwCmpFlags
0x180001c83  mov     ecx, 7Fh; Locale
0x180001c88  call    cs:__imp_CompareStringW
0x180001c8e  cmp     eax, 2
0x180001c91  jnz     short loc_180001C9F
0x180001c93  mov     dword ptr [rbp+Src], 1
0x180001c9a  jmp     loc_180001DF3
0x180001c9f  mov     edi, 80070490h
0x180001ca4  jmp     loc_180002237
0x180001ca9  lea     rax, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180001cb0  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001cb8  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001cbe  mov     [rsp+80h+lpString2], rax; lpString2
0x180001cc3  mov     r8, rsi; lpString1
0x180001cc6  mov     edx, 1; dwCmpFlags
0x180001ccb  mov     ecx, 7Fh; Locale
0x180001cd0  mov     edi, r14d
0x180001cd3  call    cs:__imp_CompareStringW
0x180001cd9  cmp     eax, 2
0x180001cdc  jnz     short loc_180001CE9
0x180001cde  mov     eax, [rbx+40h]
0x180001ce1  mov     dword ptr [rbp+Src], eax
0x180001ce4  jmp     loc_180001DEB
0x180001ce9  lea     rax, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180001cf0  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001cf8  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001cfe  mov     [rsp+80h+lpString2], rax; lpString2
0x180001d03  mov     r8, rsi; lpString1
0x180001d06  mov     edx, 1; dwCmpFlags
0x180001d0b  mov     ecx, 7Fh; Locale
0x180001d10  call    cs:__imp_CompareStringW
0x180001d16  cmp     eax, 2
0x180001d19  jnz     short loc_180001D26
0x180001d1b  mov     eax, [rbx+54h]
0x180001d1e  mov     dword ptr [rbp+Src], eax
0x180001d21  jmp     loc_180001DEB
0x180001d26  lea     rax, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180001d2d  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001d35  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001d3b  mov     [rsp+80h+lpString2], rax; lpString2
0x180001d40  mov     r8, rsi; lpString1
0x180001d43  mov     edx, 1; dwCmpFlags
0x180001d48  mov     ecx, 7Fh; Locale
0x180001d4d  call    cs:__imp_CompareStringW
0x180001d53  cmp     eax, 2
0x180001d56  jnz     short loc_180001D63
0x180001d58  mov     eax, [rbx+50h]
0x180001d5b  mov     dword ptr [rbp+Src], eax
0x180001d5e  jmp     loc_180001DEB
0x180001d63  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001d6a  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001d72  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001d78  mov     [rsp+80h+lpString2], rax; lpString2
0x180001d7d  mov     r8, rsi; lpString1
0x180001d80  mov     edx, 1; dwCmpFlags
0x180001d85  mov     ecx, 7Fh; Locale
0x180001d8a  call    cs:__imp_CompareStringW
0x180001d90  cmp     eax, 2
0x180001d93  jnz     short loc_180001D9D
0x180001d95  mov     eax, [rbx+58h]
0x180001d98  mov     dword ptr [rbp+Src], eax
0x180001d9b  jmp     short loc_180001DEB
0x180001d9d  lea     rax, aRevision_0; "revision"
0x180001da4  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001dac  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001db2  mov     [rsp+80h+lpString2], rax; lpString2
0x180001db7  mov     r8, rsi; lpString1
0x180001dba  mov     edx, 1; dwCmpFlags
0x180001dbf  mov     ecx, 7Fh; Locale
0x180001dc4  call    cs:__imp_CompareStringW
0x180001dca  cmp     eax, 2
0x180001dcd  jnz     short loc_180001DDA
0x180001dcf  mov     eax, [rbx+90h]
0x180001dd5  mov     dword ptr [rbp+Src], eax
0x180001dd8  jmp     short loc_180001DEB
0x180001dda  lea     r8, [rbp+Src]; unsigned __int16 ***
0x180001dde  mov     rdx, rsi; unsigned __int16 *
0x180001de1  mov     rcx, rbx; this
0x180001de4  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180001de9  mov     edi, eax
0x180001deb  test    edi, edi
0x180001ded  jnz     loc_180002237
0x180001df3  mov     rcx, [rbp+Src]
0x180001df7  test    rcx, rcx
0x180001dfa  jz      loc_18000222D
0x180001e00  mov     r13d, r14d
0x180001e03  cmp     [rcx], r12
0x180001e06  jz      loc_18000222D
0x180001e0c  nop     dword ptr [rax+00h]
0x180001e10  mov     rax, [rbp+Src]
0x180001e14  inc     r13d
0x180001e17  cmp     [rax+r13*8], r12
0x180001e1b  jnz     short loc_180001E10
0x180001e1d  test    r13d, r13d
0x180001e20  jz      loc_18000222D
0x180001e26  lea     eax, [r13+1]
0x180001e2a  cmp     eax, r13d
0x180001e2d  jb      loc_180002214
0x180001e33  shl     rax, 3
0x180001e37  mov     ecx, 0FFFFFFFFh
0x180001e3c  cmp     rax, rcx
0x180001e3f  ja      loc_1800021FB
0x180001e45  mov     edx, eax; uBytes
0x180001e47  mov     ecx, 40h ; '@'; uFlags
0x180001e4c  mov     edi, eax
0x180001e4e  call    cs:__imp_LocalAlloc
0x180001e54  mov     [rbp+hMem], rax
0x180001e58  test    rax, rax
0x180001e5b  jnz     short loc_180001E67
0x180001e5d  mov     edi, 8007000Eh
0x180001e62  jmp     loc_180002237
0x180001e67  mov     rdx, [rbp+Src]; Src
0x180001e6b  mov     r8, rdi; Size
0x180001e6e  mov     rcx, rax; void *
0x180001e71  call    memcpy_0
0x180001e76  xorps   xmm0, xmm0
0x180001e79  lea     rdx, ds:0[r13*2]
0x180001e81  add     rdx, r13
0x180001e84  mov     ecx, 40h ; '@'; uFlags
0x180001e89  shl     rdx, 3; uBytes
0x180001e8d  movups  [rbp+pvStructInfo], xmm0
0x180001e91  call    cs:__imp_LocalAlloc
0x180001e97  mov     [rbp+var_30], rax
0x180001e9b  mov     rbx, rax
0x180001e9e  test    rax, rax
0x180001ea1  jnz     short loc_180001EB7
0x180001ea3  mov     rcx, [rbp+hMem]; hMem
0x180001ea7  mov     edi, 8007000Eh
0x180001eac  call    cs:__imp_LocalFree
0x180001eb2  jmp     loc_180002237
0x180001eb7  xor     edi, edi
0x180001eb9  mov     [rbp+var_18], r14
0x180001ebd  test    r13d, r13d
0x180001ec0  jz      loc_180002032
0x180001ec6  nop     word ptr [rax+rax+00000000h]
0x180001ed0  mov     rcx, [rbp+hMem]
0x180001ed4  mov     edx, 3Bh ; ';'; Ch
0x180001ed9  mov     r15d, r14d
0x180001edc  mov     rcx, [rcx+r15*8]; Str
0x180001ee0  call    cs:__imp_wcschr
0x180001ee6  test    rax, rax
0x180001ee9  jz      short loc_180001EF0
0x180001eeb  xor     ecx, ecx
0x180001eed  mov     [rax], cx
0x180001ef0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001ef7  lea     rdx, aMspkiCertifica; "msPKI-Certificate-Policy"
0x180001efe  xchg    ax, ax
0x180001f00  movzx   eax, word ptr [rdx+rcx*2+2]
0x180001f05  cmp     ax, [rsi+rcx*2+2]
0x180001f0a  jnz     short loc_180001F84
0x180001f0c  add     rcx, 2
0x180001f10  cmp     rcx, 19h
0x180001f14  jz      short loc_180001F22
0x180001f16  movzx   eax, word ptr [rdx+rcx*2]
0x180001f1a  cmp     ax, [rsi+rcx*2]
0x180001f1e  jz      short loc_180001F00
0x180001f20  jmp     short loc_180001F84
0x180001f22  mov     rax, [rbp+hMem]
0x180001f26  lea     r8, [rbp+var_20]; void *
0x180001f2a  mov     r9, [rbp+arg_10]; struct ldap *
0x180001f2e  mov     edx, 2; unsigned int
0x180001f33  mov     rcx, [rax+r15*8]; unsigned __int16 *
0x180001f37  call    ?I_CAOIDGetProperty@@YAJPEBGKPEAXPEAUldap@@@Z; I_CAOIDGetProperty(ushort const *,ulong,void *,ldap *)
0x180001f3c  mov     r12, [rbp+var_20]
0x180001f40  test    eax, eax
0x180001f42  jnz     short loc_180001F84
0x180001f44  test    r12, r12
0x180001f47  jz      short loc_180001F84
0x180001f49  lea     rax, [r15+r15*2]
0x180001f4d  mov     rdx, r12; unsigned __int16 *
0x180001f50  lea     r9, [rax+2]
0x180001f54  lea     rax, [rax+1]
0x180001f58  lea     r8, [rbx+rax*8]; unsigned int *
0x180001f5c  lea     r9, [rbx+r9*8]; struct _CERT_POLICY_QUALIFIER_INFO **
0x180001f60  call    ?_GetPolicyQualifiers@CCertTypeInfo@@IEAAJPEAGPEAKPEAPEAU_CERT_POLICY_QUALIFIER_INFO@@@Z; CCertTypeInfo::_GetPolicyQualifiers(ushort *,ulong *,_CERT_POLICY_QUALIFIER_INFO * *)
0x180001f65  mov     edi, eax
0x180001f67  test    eax, eax
0x180001f69  jnz     loc_180002094
0x180001f6f  test    r12, r12
0x180001f72  jz      short loc_180001F7D
0x180001f74  mov     rcx, r12; hMem
0x180001f77  call    cs:__imp_LocalFree
0x180001f7d  xor     r12d, r12d
0x180001f80  mov     [rbp+var_20], r12
0x180001f84  mov     rax, [rbp+hMem]
0x180001f88  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180001f8e  mov     [rsp+80h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180001f97  xor     edx, edx; dwFlags
0x180001f99  mov     [rsp+80h+lpDefaultChar], 0; lpDefaultChar
0x180001fa2  xor     ecx, ecx; CodePage
0x180001fa4  mov     [rsp+80h+cchCount2], 0; cbMultiByte
0x180001fac  mov     r8, [rax+r15*8]; lpWideCharStr
0x180001fb0  mov     [rsp+80h+lpString2], 0; lpMultiByteStr
0x180001fb9  call    cs:__imp_WideCharToMultiByte
0x180001fbf  mov     ebx, eax
0x180001fc1  test    eax, eax
0x180001fc3  jz      loc_1800020CB
0x180001fc9  mov     edx, ebx; uBytes
0x180001fcb  mov     ecx, 40h ; '@'; uFlags
0x180001fd0  call    cs:__imp_LocalAlloc
0x180001fd6  mov     rdx, [rbp+var_30]
0x180001fda  lea     rcx, [r15+r15*2]
0x180001fde  mov     [rdx+rcx*8], rax
0x180001fe2  test    rax, rax
0x180001fe5  jz      loc_1800020BB
0x180001feb  xor     ecx, ecx; CodePage
0x180001fed  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180001ff3  mov     [rsp+80h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x180001ff8  xor     edx, edx; dwFlags
0x180001ffa  mov     [rsp+80h+lpDefaultChar], rcx; lpDefaultChar
0x180001fff  mov     [rsp+80h+cchCount2], ebx; cbMultiByte
0x180002003  mov     [rsp+80h+lpString2], rax; lpMultiByteStr
0x180002008  mov     rax, [rbp+hMem]
0x18000200c  mov     r8, [rax+r15*8]; lpWideCharStr
0x180002010  call    cs:__imp_WideCharToMultiByte
0x180002016  mov     rbx, [rbp+var_30]
0x18000201a  test    eax, eax
0x18000201c  jz      loc_1800020AE
0x180002022  inc     r14d
0x180002025  cmp     r14d, r13d
0x180002028  jb      loc_180001ED0
0x18000202e  mov     r15, [rbp+arg_18]
0x180002032  lea     rax, [rbp+pcbEncoded]
0x180002036  mov     dword ptr [rbp+pvStructInfo], r13d
0x18000203a  xor     r9d, r9d; pbEncoded
0x18000203d  mov     [rsp+80h+lpString2], rax; pcbEncoded
0x180002042  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x180002046  mov     qword ptr [rbp+pvStructInfo+8], rbx
0x18000204a  lea     rdx, szStructType; "2.5.29.32"
0x180002051  mov     [rbp+pcbEncoded], 0
0x180002058  mov     ecx, 1; dwCertEncodingType
0x18000205d  call    cs:__imp_CryptEncodeObject
0x180002063  test    eax, eax
0x180002065  jnz     loc_180002102
0x18000206b  call    cs:__imp_GetLastError
0x180002071  mov     edi, eax
0x180002073  cmp     eax, 1
0x180002076  jnz     short loc_1800020DC
0x180002078  xor     r9d, r9d; int
0x18000207b  lea     rcx, aSFalseHr; "S_FALSE == hr"
0x180002082  mov     edx, 65F01CAh; unsigned int
0x180002087  mov     r8d, eax; int
0x18000208a  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000208f  jmp     loc_180002172
0x180002094  xor     r9d, r9d; int
0x180002097  mov     r8d, eax; int
0x18000209a  mov     edx, 18DB0328h; unsigned int
0x18000209f  xor     ecx, ecx; unsigned __int16 *
0x1800020a1  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800020a6  xor     r14d, r14d
0x1800020a9  jmp     loc_18000217A
0x1800020ae  mov     edi, 8000FFFFh
0x1800020b3  xor     r14d, r14d
0x1800020b6  jmp     loc_18000217A
0x1800020bb  mov     edi, 8007000Eh
0x1800020c0  xor     r14d, r14d
0x1800020c3  mov     rbx, rdx
0x1800020c6  jmp     loc_18000217A
0x1800020cb  mov     rbx, [rbp+var_30]
0x1800020cf  mov     edi, 8000FFFFh
0x1800020d4  xor     r14d, r14d
  ... truncated ...
```
