# CCAInfo::GetProperty(ushort const *,ushort * * *)

- ea: `0x18000596c`
- end: `0x180005bd0`
- name: `?GetProperty@CCAInfo@@QEAAJPEBGPEAPEAPEAG@Z`
- size: `612`
- prototype: `__int64 __fastcall(CCAProperty **this, const unsigned __int16 *, unsigned __int16 ***)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000596c`
- `0x18002e4b0`
- `0x1800354fc`
- `0x180035cfc`
- `0x1800362f8`
- `0x1800365a4`

## callees

- `0x180004ba0`
- `0x18000596c`
- `0x180005f00`
- `0x180008400`
- `0x180008610`
- `0x18000d520`
- `0x18000e2e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ade`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005b34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ade`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005b34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ba8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ba8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800059bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800059bc`
- `CRYPT32!CertGetNameStringW` at `0x180005ac4`
- `CRYPT32!CertGetNameStringW` at `0x180005b13`
- `CRYPT32!CertGetNameStringW` at `0x180005ac4`
- `CRYPT32!CertGetNameStringW` at `0x180005b13`

## string_xrefs

- `0x1800059e9`: `certificateTemplates`
- `0x1800059d3`: `supportedCertificateTemplates`

## pseudocode

```c
__int64 __fastcall CCAInfo::GetProperty(CCAProperty **this, const unsigned __int16 *a2, unsigned __int16 ***a3)
{
  __int64 v6; // rbp
  const unsigned __int16 *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int Value; // eax
  int v11; // edx
  unsigned int v12; // ecx
  unsigned __int16 **v13; // rcx
  unsigned __int16 *v14; // rdi
  DWORD NameStringW; // eax
  DWORD v16; // ebx
  WCHAR *v17; // rax
  char *v18; // rax
  unsigned __int16 **v19; // rbx
  __int64 result; // rax
  int Property; // eax
  struct CCAProperty *v22; // [rsp+78h] [rbp+10h] BYREF

  v22 = 0;
  if ( !a2 || !a3 )
  {
    v9 = -2147467261;
    v12 = 101057317;
    v11 = -2147467261;
    goto LABEL_33;
  }
  v6 = -1;
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"machineDNSName", -1) == 2 )
  {
    v7 = L"dNSHostName";
  }
  else if ( (unsigned int)mylstrcmpNLSub(a2, L"supportedCertificateTemplates", -1, 1) )
  {
    v7 = L"signatureAlgorithms";
    if ( (unsigned int)mylstrcmpNLSub(a2, L"signatureAlgs", -1, 1) )
      v7 = a2;
  }
  else
  {
    v7 = L"certificateTemplates";
  }
  v8 = CCAProperty::Find(this[1], v7, &v22);
  v9 = v8;
  if ( !v8 )
  {
    if ( v22 )
    {
      Value = CCAProperty::GetValue(v22, a3);
      v9 = Value;
      if ( Value )
      {
        v11 = Value;
        v12 = 102499109;
LABEL_33:
        CSPrintErrorLineFile(v12, v11);
        return v9;
      }
    }
    else
    {
      *a3 = 0;
    }
    if ( (unsigned int)mylstrcmpNLSub(v7, L"displayName", -1, 1) )
      return v9;
    v13 = *a3;
    if ( *a3 )
    {
      if ( *v13 )
        return v9;
      LocalFree(v13);
      *a3 = 0;
    }
    v14 = 0;
    if ( !*this )
      goto LABEL_28;
    NameStringW = CertGetNameStringW((PCCERT_CONTEXT)*this, 4u, 0, 0, 0, 0);
    v16 = NameStringW;
    if ( !NameStringW )
      goto LABEL_28;
    v17 = (WCHAR *)LocalAlloc(0x40u, 2LL * NameStringW);
    v14 = v17;
    if ( !v17 )
    {
      v11 = -2147024882;
      v12 = 104858405;
      v9 = -2147024882;
      goto LABEL_33;
    }
    if ( CertGetNameStringW((PCCERT_CONTEXT)*this, 4u, 0, 0, v17, v16) )
    {
      do
        ++v6;
      while ( v14[v6] );
      v18 = (char *)LocalAlloc(0x40u, 2 * v6 + 18);
      v19 = (unsigned __int16 **)v18;
      if ( v18 )
      {
        *((_QWORD *)v18 + 1) = 0;
        *(_QWORD *)v18 = v18 + 16;
        StringCchCopyW((unsigned __int16 *)v18 + 8, v6 + 1, v14);
        LocalFree(v14);
        result = 0;
        *a3 = v19;
        return result;
      }
      v9 = -2147024882;
      CSPrintErrorLineFile(0x6510325u, -2147024882);
    }
    else
    {
LABEL_28:
      Property = CCAInfo::GetProperty((CCAInfo *)this, L"cn", a3);
      v9 = Property;
      if ( Property )
        CSPrintErrorLineFile(0x65E0325u, Property);
      if ( !v14 )
        return v9;
    }
    LocalFree(v14);
    return v9;
  }
  CSPrintErrorLineFileData2(v7, 0x6170325u, v8, 0);
  return v9;
}

```

## disassembly

```asm
0x18000596c  push    rbx
0x18000596e  push    rbp
0x18000596f  push    rsi
0x180005970  push    rdi
0x180005971  push    r14
0x180005973  push    r15
0x180005975  sub     rsp, 38h
0x180005979  xor     r15d, r15d
0x18000597c  mov     rsi, r8
0x18000597f  mov     [rsp+68h+arg_8], r15
0x180005984  mov     rbx, rdx
0x180005987  mov     r14, rcx
0x18000598a  test    rdx, rdx
0x18000598d  jz      loc_180005BB0
0x180005993  test    r8, r8
0x180005996  jz      loc_180005BB0
0x18000599c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800059a0  lea     rax, aMachinednsname; "machineDNSName"
0x1800059a7  mov     r8, rdx; lpString1
0x1800059aa  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x1800059ae  mov     r9d, ebp; cchCount1
0x1800059b1  mov     [rsp+68h+lpString2], rax; lpString2
0x1800059b6  lea     edx, [rbp+2]; dwCmpFlags
0x1800059b9  lea     ecx, [rdx+7Eh]; Locale
0x1800059bc  call    cs:__imp_CompareStringW
0x1800059c2  cmp     eax, 2
0x1800059c5  jnz     short loc_1800059D0
0x1800059c7  lea     rdi, aDnshostname; "dNSHostName"
0x1800059ce  jmp     short loc_180005A14
0x1800059d0  mov     r9b, 1; bool
0x1800059d3  lea     rdx, aSupportedcerti; "supportedCertificateTemplates"
0x1800059da  mov     r8d, ebp; int
0x1800059dd  mov     rcx, rbx; lpString1
0x1800059e0  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800059e5  test    eax, eax
0x1800059e7  jnz     short loc_1800059F2
0x1800059e9  lea     rdi, aCertificatetem; "certificateTemplates"
0x1800059f0  jmp     short loc_180005A14
0x1800059f2  mov     r9b, 1; bool
0x1800059f5  lea     rdx, aSignaturealgs; "signatureAlgs"
0x1800059fc  mov     r8d, ebp; int
0x1800059ff  mov     rcx, rbx; lpString1
0x180005a02  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180005a07  test    eax, eax
0x180005a09  lea     rdi, aSignaturealgor; "signatureAlgorithms"
0x180005a10  cmovnz  rdi, rbx
0x180005a14  mov     rcx, [r14+8]; this
0x180005a18  lea     r8, [rsp+68h+arg_8]; struct CCAProperty **
0x180005a1d  mov     rdx, rdi; unsigned __int16 *
0x180005a20  call    ?Find@CCAProperty@@QEAAJPEBGPEAPEAV1@@Z; CCAProperty::Find(ushort const *,CCAProperty * *)
0x180005a25  mov     ebx, eax
0x180005a27  test    eax, eax
0x180005a29  jz      short loc_180005A43
0x180005a2b  xor     r9d, r9d; int
0x180005a2e  mov     r8d, eax; int
0x180005a31  mov     edx, 6170325h; unsigned int
0x180005a36  mov     rcx, rdi; unsigned __int16 *
0x180005a39  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180005a3e  jmp     loc_180005BC1
0x180005a43  mov     rcx, [rsp+68h+arg_8]; this
0x180005a48  test    rcx, rcx
0x180005a4b  jz      short loc_180005A67
0x180005a4d  mov     rdx, rsi; unsigned __int16 ***
0x180005a50  call    ?GetValue@CCAProperty@@QEAAJPEAPEAPEAG@Z; CCAProperty::GetValue(ushort * * *)
0x180005a55  mov     ebx, eax
0x180005a57  test    eax, eax
0x180005a59  jz      short loc_180005A6A
0x180005a5b  mov     edx, eax
0x180005a5d  mov     ecx, 61C0325h
0x180005a62  jmp     loc_180005BBC
0x180005a67  mov     [rsi], r15
0x180005a6a  mov     r9b, 1; bool
0x180005a6d  lea     rdx, aDisplayname_0; "displayName"
0x180005a74  mov     r8d, ebp; int
0x180005a77  mov     rcx, rdi; lpString1
0x180005a7a  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180005a7f  test    eax, eax
0x180005a81  jnz     loc_180005BC1
0x180005a87  mov     rcx, [rsi]; hMem
0x180005a8a  test    rcx, rcx
0x180005a8d  jz      short loc_180005AA1
0x180005a8f  cmp     [rcx], r15
0x180005a92  jnz     loc_180005BC1
0x180005a98  call    cs:__imp_LocalFree
0x180005a9e  mov     [rsi], r15
0x180005aa1  mov     rcx, [r14]; pCertContext
0x180005aa4  mov     rdi, r15
0x180005aa7  test    rcx, rcx
0x180005aaa  jz      loc_180005B7C
0x180005ab0  xor     r9d, r9d; pvTypePara
0x180005ab3  mov     [rsp+68h+cchCount2], r15d; cchNameString
0x180005ab8  xor     r8d, r8d; dwFlags
0x180005abb  mov     [rsp+68h+lpString2], r15; pszNameString
0x180005ac0  lea     edx, [r9+4]; dwType
0x180005ac4  call    cs:__imp_CertGetNameStringW
0x180005aca  mov     ebx, eax
0x180005acc  test    eax, eax
0x180005ace  jz      loc_180005B7C
0x180005ad4  mov     edx, ebx
0x180005ad6  mov     ecx, 40h ; '@'; uFlags
0x180005adb  add     rdx, rdx; uBytes
0x180005ade  call    cs:__imp_LocalAlloc
0x180005ae4  mov     rdi, rax
0x180005ae7  test    rax, rax
0x180005aea  jnz     short loc_180005AFD
0x180005aec  mov     edx, 8007000Eh
0x180005af1  mov     ecx, 6400325h
0x180005af6  mov     ebx, edx
0x180005af8  jmp     loc_180005BBC
0x180005afd  mov     rcx, [r14]; pCertContext
0x180005b00  xor     r9d, r9d; pvTypePara
0x180005b03  mov     [rsp+68h+cchCount2], ebx; cchNameString
0x180005b07  xor     r8d, r8d; dwFlags
0x180005b0a  mov     [rsp+68h+lpString2], rdi; pszNameString
0x180005b0f  lea     edx, [r9+4]; dwType
0x180005b13  call    cs:__imp_CertGetNameStringW
0x180005b19  test    eax, eax
0x180005b1b  jz      short loc_180005B7C
0x180005b1d  inc     rbp
0x180005b20  cmp     [rdi+rbp*2], r15w
0x180005b25  jnz     short loc_180005B1D
0x180005b27  lea     rdx, ds:12h[rbp*2]; uBytes
0x180005b2f  mov     ecx, 40h ; '@'; uFlags
0x180005b34  call    cs:__imp_LocalAlloc
0x180005b3a  mov     rbx, rax
0x180005b3d  test    rax, rax
0x180005b40  jnz     short loc_180005B55
0x180005b42  mov     edx, 8007000Eh; int
0x180005b47  mov     ecx, 6510325h; unsigned int
0x180005b4c  mov     ebx, edx
0x180005b4e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180005b53  jmp     short loc_180005BA5
0x180005b55  lea     rcx, [rax+10h]; unsigned __int16 *
0x180005b59  mov     [rax+8], r15
0x180005b5d  mov     r8, rdi; unsigned __int16 *
0x180005b60  mov     [rax], rcx
0x180005b63  lea     rdx, [rbp+1]; unsigned __int64
0x180005b67  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005b6c  mov     rcx, rdi; hMem
0x180005b6f  call    cs:__imp_LocalFree
0x180005b75  xor     eax, eax
0x180005b77  mov     [rsi], rbx
0x180005b7a  jmp     short loc_180005BC3
0x180005b7c  mov     r8, rsi; unsigned __int16 ***
0x180005b7f  lea     rdx, aCn_1; "cn"
0x180005b86  mov     rcx, r14; this
0x180005b89  call    ?GetProperty@CCAInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCAInfo::GetProperty(ushort const *,ushort * * *)
0x180005b8e  mov     ebx, eax
0x180005b90  test    eax, eax
0x180005b92  jz      short loc_180005BA0
0x180005b94  mov     edx, eax; int
0x180005b96  mov     ecx, 65E0325h; unsigned int
0x180005b9b  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180005ba0  test    rdi, rdi
0x180005ba3  jz      short loc_180005BC1
0x180005ba5  mov     rcx, rdi; hMem
0x180005ba8  call    cs:__imp_LocalFree
0x180005bae  jmp     short loc_180005BC1
0x180005bb0  mov     ebx, 80004003h
0x180005bb5  mov     ecx, 6060325h; unsigned int
0x180005bba  mov     edx, ebx; int
0x180005bbc  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180005bc1  mov     eax, ebx
0x180005bc3  add     rsp, 38h
0x180005bc7  pop     r15
0x180005bc9  pop     r14
0x180005bcb  pop     rdi
0x180005bcc  pop     rsi
0x180005bcd  pop     rbp
0x180005bce  pop     rbx
0x180005bcf  retn
```
