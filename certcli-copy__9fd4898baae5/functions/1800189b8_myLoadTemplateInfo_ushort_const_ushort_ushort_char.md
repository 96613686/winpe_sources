# myLoadTemplateInfo(ushort const *,ushort * *,ushort * *,char * *)

- ea: `0x1800189b8`
- end: `0x180018bf2`
- name: `?myLoadTemplateInfo@@YAJPEBGPEAPEAG1PEAPEAD@Z`
- size: `570`
- prototype: `int(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180015e18`
- `0x180017620`

## callees

- `0x1800189b8`
- `0x180020714`
- `0x180020a6c`

## import_xrefs

- `certca!__imp_CAFindCertTypeByName` at `0x180018a08`
- `certca!__imp_CAFindCertTypeByName` at `0x180018a26`
- `certca!__imp_CAFindCertTypeByName` at `0x180018a08`
- `certca!__imp_CAFindCertTypeByName` at `0x180018a26`
- `certca!__imp_CACloseCertType` at `0x180018bd9`
- `certca!__imp_CACloseCertType` at `0x180018bd9`
- `certca!__imp_CAGetCertTypeProperty` at `0x180018a5d`
- `certca!__imp_CAGetCertTypeProperty` at `0x180018adc`
- `certca!__imp_CAGetCertTypeProperty` at `0x180018b4e`
- `certca!__imp_CAGetCertTypeProperty` at `0x180018a5d`
- `certca!__imp_CAGetCertTypeProperty` at `0x180018adc`
- `certca!__imp_CAGetCertTypeProperty` at `0x180018b4e`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180018abf`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180018b31`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180018bcf`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180018abf`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180018b31`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180018bcf`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018aac`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018aac`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018afd`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018b6f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018bb7`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018afd`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018b6f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018bb7`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180018a40`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180018a40`

## string_xrefs

- `0x180018b47`: `msPKI-Cert-Template-OID`
- `0x180018b68`: `msPKI-Cert-Template-OID`

## pseudocode

```c
__int64 __fastcall myLoadTemplateInfo(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        char **a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  int v10; // r8d
  unsigned int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // ecx
  int v14; // edx
  int v15; // eax
  const unsigned __int16 **v16; // rdx
  int v17; // eax
  int v18; // r8d
  const unsigned __int16 **v20; // [rsp+58h] [rbp+38h] BYREF
  __int64 v21; // [rsp+60h] [rbp+40h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v21 = 0;
  v20 = 0;
  v8 = CAFindCertTypeByName(a1, 0, 224, &v21);
  if ( v8 == -2147023728 )
    v8 = CAFindCertTypeByName(a1, 0, 736, &v21);
  if ( v8 )
  {
    CSPrintErrorLineFileData2(a1, 0xC7B019Bu, v8, v8);
    goto LABEL_30;
  }
  v9 = CAGetCertTypeProperty(v21, L"cn", &v20);
  v8 = v9;
  if ( !v9 )
  {
    if ( !v20 || !*v20 )
    {
      v8 = -2147023728;
      v11 = 210108827;
      v10 = -2147023728;
      goto LABEL_29;
    }
    v12 = myDupString(*v20, a2);
    v8 = v12;
    if ( v12 )
    {
      v13 = 210305435;
LABEL_11:
      v14 = v12;
      goto LABEL_12;
    }
    CAFreeCertTypeProperty(v21, v20);
    v20 = 0;
    v15 = CAGetCertTypeProperty(v21, L"dsDisplayName", &v20);
    if ( v15 )
    {
      v20 = 0;
      CSPrintErrorLineFileData(L"dsDisplayName", 0xC92019Bu, v15);
    }
    v16 = v20;
    if ( v20 )
    {
      if ( *v20 )
      {
        v12 = myDupString(*v20, a3);
        v8 = v12;
        if ( v12 )
        {
          v13 = 211354011;
          goto LABEL_11;
        }
        v16 = v20;
      }
      CAFreeCertTypeProperty(v21, v16);
      v20 = 0;
    }
    v17 = CAGetCertTypeProperty(v21, L"msPKI-Cert-Template-OID", &v20);
    if ( v17 )
    {
      v20 = 0;
      CSPrintErrorLineFileData(L"msPKI-Cert-Template-OID", 0xCA3019Bu, v17);
    }
    if ( !v20 || !*v20 || (unsigned int)myConvertWszToSz(a4, *v20, v18) )
    {
      v8 = 0;
      goto LABEL_30;
    }
    v8 = -2147024882;
    v13 = 212468123;
    v14 = -2147024882;
LABEL_12:
    CSPrintErrorLineFile(v13, v14);
    goto LABEL_30;
  }
  v20 = 0;
  v10 = v9;
  v11 = 209781147;
LABEL_29:
  CSPrintErrorLineFileData(L"cn", v11, v10);
LABEL_30:
  if ( v21 )
  {
    if ( v20 )
      CAFreeCertTypeProperty(v21, v20);
    CACloseCertType();
  }
  return v8;
}

```

## disassembly

```asm
0x1800189b8  mov     [rsp-28h+arg_0], rbx
0x1800189bd  push    rbp
0x1800189be  push    rsi
0x1800189bf  push    rdi
0x1800189c0  push    r14
0x1800189c2  push    r15
0x1800189c4  mov     rbp, rsp
0x1800189c7  sub     rsp, 20h
0x1800189cb  mov     qword ptr [rdx], 0
0x1800189d2  mov     r15, r9
0x1800189d5  mov     qword ptr [r8], 0
0x1800189dc  mov     r14, r8
0x1800189df  mov     qword ptr [r9], 0
0x1800189e6  mov     rsi, rdx
0x1800189e9  lea     r9, [rbp+arg_10]
0x1800189ed  mov     [rbp+arg_10], 0
0x1800189f5  xor     edx, edx
0x1800189f7  mov     [rbp+arg_8], 0
0x1800189ff  mov     r8d, 0E0h
0x180018a05  mov     rdi, rcx
0x180018a08  call    cs:__imp_CAFindCertTypeByName
0x180018a0e  mov     ebx, eax
0x180018a10  cmp     eax, 80070490h
0x180018a15  jnz     short loc_180018A2E
0x180018a17  lea     r9, [rbp+arg_10]
0x180018a1b  xor     edx, edx
0x180018a1d  mov     r8d, 2E0h
0x180018a23  mov     rcx, rdi
0x180018a26  call    cs:__imp_CAFindCertTypeByName
0x180018a2c  mov     ebx, eax
0x180018a2e  test    ebx, ebx
0x180018a30  jz      short loc_180018A4B
0x180018a32  mov     r9d, ebx
0x180018a35  mov     r8d, ebx
0x180018a38  mov     edx, 0C7B019Bh
0x180018a3d  mov     rcx, rdi
0x180018a40  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180018a46  jmp     loc_180018BBD
0x180018a4b  mov     rcx, [rbp+arg_10]
0x180018a4f  lea     rdi, aCn_0; "cn"
0x180018a56  mov     rdx, rdi
0x180018a59  lea     r8, [rbp+arg_8]
0x180018a5d  call    cs:__imp_CAGetCertTypeProperty
0x180018a63  mov     ebx, eax
0x180018a65  test    eax, eax
0x180018a67  jz      short loc_180018A7E
0x180018a69  mov     [rbp+arg_8], 0
0x180018a71  mov     r8d, eax
0x180018a74  mov     edx, 0C81019Bh
0x180018a79  jmp     loc_180018BB4
0x180018a7e  mov     rax, [rbp+arg_8]
0x180018a82  test    rax, rax
0x180018a85  jz      loc_180018BA7
0x180018a8b  mov     rcx, [rax]; Src
0x180018a8e  test    rcx, rcx
0x180018a91  jz      loc_180018BA7
0x180018a97  mov     rdx, rsi; unsigned __int16 **
0x180018a9a  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x180018a9f  mov     ebx, eax
0x180018aa1  test    eax, eax
0x180018aa3  jz      short loc_180018AB7
0x180018aa5  mov     ecx, 0C89019Bh
0x180018aaa  mov     edx, eax
0x180018aac  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180018ab2  jmp     loc_180018BBD
0x180018ab7  mov     rdx, [rbp+arg_8]
0x180018abb  mov     rcx, [rbp+arg_10]
0x180018abf  call    cs:__imp_CAFreeCertTypeProperty
0x180018ac5  mov     rcx, [rbp+arg_10]
0x180018ac9  lea     r8, [rbp+arg_8]
0x180018acd  lea     rdx, aDsdisplayname; "dsDisplayName"
0x180018ad4  mov     [rbp+arg_8], 0
0x180018adc  call    cs:__imp_CAGetCertTypeProperty
0x180018ae2  test    eax, eax
0x180018ae4  jz      short loc_180018B03
0x180018ae6  mov     r8d, eax
0x180018ae9  mov     [rbp+arg_8], 0
0x180018af1  mov     edx, 0C92019Bh
0x180018af6  lea     rcx, aDsdisplayname; "dsDisplayName"
0x180018afd  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018b03  mov     rdx, [rbp+arg_8]
0x180018b07  test    rdx, rdx
0x180018b0a  jz      short loc_180018B3F
0x180018b0c  mov     rcx, [rdx]; Src
0x180018b0f  test    rcx, rcx
0x180018b12  jz      short loc_180018B2D
0x180018b14  mov     rdx, r14; unsigned __int16 **
0x180018b17  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x180018b1c  mov     ebx, eax
0x180018b1e  test    eax, eax
0x180018b20  jz      short loc_180018B29
0x180018b22  mov     ecx, 0C99019Bh
0x180018b27  jmp     short loc_180018AAA
0x180018b29  mov     rdx, [rbp+arg_8]
0x180018b2d  mov     rcx, [rbp+arg_10]
0x180018b31  call    cs:__imp_CAFreeCertTypeProperty
0x180018b37  mov     [rbp+arg_8], 0
0x180018b3f  mov     rcx, [rbp+arg_10]
0x180018b43  lea     r8, [rbp+arg_8]
0x180018b47  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x180018b4e  call    cs:__imp_CAGetCertTypeProperty
0x180018b54  test    eax, eax
0x180018b56  jz      short loc_180018B75
0x180018b58  mov     r8d, eax
0x180018b5b  mov     [rbp+arg_8], 0
0x180018b63  mov     edx, 0CA3019Bh
0x180018b68  lea     rcx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x180018b6f  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018b75  mov     rdx, [rbp+arg_8]
0x180018b79  test    rdx, rdx
0x180018b7c  jz      short loc_180018BA3
0x180018b7e  mov     rdx, [rdx]; unsigned __int16 *
0x180018b81  test    rdx, rdx
0x180018b84  jz      short loc_180018BA3
0x180018b86  mov     rcx, r15; char **
0x180018b89  call    ?myConvertWszToSz@@YAHPEAPEADPEBGJ@Z; myConvertWszToSz(char * *,ushort const *,long)
0x180018b8e  test    eax, eax
0x180018b90  jnz     short loc_180018BA3
0x180018b92  mov     ebx, 8007000Eh
0x180018b97  mov     ecx, 0CAA019Bh
0x180018b9c  mov     edx, ebx
0x180018b9e  jmp     loc_180018AAC
0x180018ba3  xor     ebx, ebx
0x180018ba5  jmp     short loc_180018BBD
0x180018ba7  mov     ebx, 80070490h
0x180018bac  mov     edx, 0C86019Bh
0x180018bb1  mov     r8d, ebx
0x180018bb4  mov     rcx, rdi
0x180018bb7  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018bbd  mov     rcx, [rbp+arg_10]
0x180018bc1  test    rcx, rcx
0x180018bc4  jz      short loc_180018BDF
0x180018bc6  mov     rdx, [rbp+arg_8]
0x180018bca  test    rdx, rdx
0x180018bcd  jz      short loc_180018BD9
0x180018bcf  call    cs:__imp_CAFreeCertTypeProperty
0x180018bd5  mov     rcx, [rbp+arg_10]
0x180018bd9  call    cs:__imp_CACloseCertType
0x180018bdf  mov     eax, ebx
0x180018be1  mov     rbx, [rsp+20h+arg_0]
0x180018be6  add     rsp, 20h
0x180018bea  pop     r15
0x180018bec  pop     r14
0x180018bee  pop     rdi
0x180018bef  pop     rsi
0x180018bf0  pop     rbp
0x180018bf1  retn
```
