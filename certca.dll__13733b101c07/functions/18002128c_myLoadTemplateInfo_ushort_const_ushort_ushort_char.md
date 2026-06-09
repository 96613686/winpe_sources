# myLoadTemplateInfo(ushort const *,ushort * *,ushort * *,char * *)

- ea: `0x18002128c`
- end: `0x1800214bd`
- name: `?myLoadTemplateInfo@@YAJPEBGPEAPEAG1PEAPEAD@Z`
- size: `561`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, char **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001ebf8`
- `0x180020378`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000dce0`
- `0x180011130`
- `0x18001255c`
- `0x1800127f0`
- `0x18002128c`
- `0x18002e2a0`
- `0x18002e620`

## string_xrefs

- `0x18002140d`: `msPKI-Cert-Template-OID`
- `0x180021427`: `msPKI-Cert-Template-OID`

## pseudocode

```c
__int64 __fastcall myLoadTemplateInfo(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        char **a4)
{
  const unsigned __int16 *v7; // rsi
  unsigned int v8; // ebx
  CCertTypeInfo *v9; // rdi
  int v10; // r9d
  int v11; // r8d
  unsigned int v12; // edx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // ecx
  int v16; // edx
  int v17; // eax
  int v18; // eax
  unsigned __int16 **v20; // [rsp+78h] [rbp+48h] BYREF
  CCertTypeInfo *v21; // [rsp+80h] [rbp+50h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v21 = 0;
  v20 = 0;
  v7 = a1;
  v8 = CAFindCertTypeByName2((_DWORD)a1, 0, 224, 6, 0, &v21);
  if ( v8 == -2147023728 )
    v8 = CAFindCertTypeByName2((_DWORD)v7, 0, 736, 6, 0, &v21);
  v9 = v21;
  if ( !v8 )
  {
    v7 = L"cn";
    v13 = CAGetCertTypeProperty(v21, L"cn", &v20);
    v8 = v13;
    if ( v13 )
    {
      v20 = 0;
      v11 = v13;
      v12 = 209781147;
LABEL_28:
      v10 = 0;
      goto LABEL_29;
    }
    if ( !v20 || !*v20 )
    {
      v11 = -2147023728;
      v12 = 210108827;
      v8 = -2147023728;
      goto LABEL_28;
    }
    v14 = myDupString(*v20, a2);
    v8 = v14;
    if ( v14 )
    {
      v15 = 210305435;
LABEL_11:
      v16 = v14;
      goto LABEL_12;
    }
    CAFreeCertTypeProperty(v9);
    v20 = 0;
    v17 = CAGetCertTypeProperty(v9, L"dsDisplayName", &v20);
    if ( v17 )
    {
      v20 = 0;
      CSPrintErrorLineFileData2(L"dsDisplayName", 0xC92019Bu, v17, 0);
    }
    if ( v20 )
    {
      if ( *v20 )
      {
        v14 = myDupString(*v20, a3);
        v8 = v14;
        if ( v14 )
        {
          v15 = 211354011;
          goto LABEL_11;
        }
      }
      CAFreeCertTypeProperty(v9);
      v20 = 0;
    }
    v18 = CAGetCertTypeProperty(v9, L"msPKI-Cert-Template-OID", &v20);
    if ( v18 )
    {
      v20 = 0;
      CSPrintErrorLineFileData2(L"msPKI-Cert-Template-OID", 0xCA3019Bu, v18, 0);
    }
    if ( !v20 || !*v20 || (unsigned int)myConvertWszToSz(a4, *v20, -1) )
    {
      v8 = 0;
      goto LABEL_30;
    }
    v8 = -2147024882;
    v15 = 212468123;
    v16 = -2147024882;
LABEL_12:
    CSPrintErrorLineFile(v15, v16);
    goto LABEL_30;
  }
  v10 = v8;
  v11 = v8;
  v12 = 209387931;
LABEL_29:
  CSPrintErrorLineFileData2(v7, v12, v11, v10);
LABEL_30:
  if ( v9 )
  {
    if ( v20 )
      CAFreeCertTypeProperty(v9);
    CACloseCertType(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18002128c  mov     [rsp-38h+arg_0], rbx
0x180021291  push    rbp
0x180021292  push    rsi
0x180021293  push    rdi
0x180021294  push    r12
0x180021296  push    r13
0x180021298  push    r14
0x18002129a  push    r15
0x18002129c  mov     rbp, rsp
0x18002129f  sub     rsp, 30h
0x1800212a3  xor     r13d, r13d
0x1800212a6  lea     rax, [rbp+arg_10]
0x1800212aa  mov     [rdx], r13
0x1800212ad  mov     r12, r9
0x1800212b0  mov     [r8], r13
0x1800212b3  mov     r15, r8
0x1800212b6  mov     r14, rdx
0x1800212b9  mov     [r9], r13
0x1800212bc  mov     [rsp+30h+var_8], rax
0x1800212c1  lea     edi, [r13+6]
0x1800212c5  mov     r9d, edi
0x1800212c8  mov     [rbp+arg_10], r13
0x1800212cc  xor     edx, edx
0x1800212ce  mov     [rbp+arg_8], r13
0x1800212d2  mov     r8d, 0E0h
0x1800212d8  mov     [rsp+30h+var_10], r13d
0x1800212dd  mov     rsi, rcx
0x1800212e0  call    CAFindCertTypeByName2
0x1800212e5  mov     ebx, eax
0x1800212e7  cmp     eax, 80070490h
0x1800212ec  jnz     short loc_180021311
0x1800212ee  lea     rax, [rbp+arg_10]
0x1800212f2  mov     r9d, edi
0x1800212f5  mov     [rsp+30h+var_8], rax
0x1800212fa  xor     edx, edx
0x1800212fc  mov     r8d, 2E0h
0x180021302  mov     [rsp+30h+var_10], r13d
0x180021307  mov     rcx, rsi
0x18002130a  call    CAFindCertTypeByName2
0x18002130f  mov     ebx, eax
0x180021311  mov     rdi, [rbp+arg_10]
0x180021315  test    ebx, ebx
0x180021317  jz      short loc_180021329
0x180021319  mov     r9d, ebx
0x18002131c  mov     r8d, ebx
0x18002131f  mov     edx, 0C7B019Bh
0x180021324  jmp     loc_180021480
0x180021329  lea     rsi, aCn_1; "cn"
0x180021330  mov     rcx, rdi; this
0x180021333  mov     rdx, rsi; unsigned __int16 *
0x180021336  lea     r8, [rbp+arg_8]; unsigned __int16 ***
0x18002133a  call    CAGetCertTypeProperty
0x18002133f  mov     ebx, eax
0x180021341  test    eax, eax
0x180021343  jz      short loc_180021356
0x180021345  mov     [rbp+arg_8], r13
0x180021349  mov     r8d, eax
0x18002134c  mov     edx, 0C81019Bh
0x180021351  jmp     loc_18002147D
0x180021356  mov     rax, [rbp+arg_8]
0x18002135a  test    rax, rax
0x18002135d  jz      loc_18002146F
0x180021363  mov     rcx, [rax]; Src
0x180021366  test    rcx, rcx
0x180021369  jz      loc_18002146F
0x18002136f  mov     rdx, r14; unsigned __int16 **
0x180021372  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x180021377  mov     ebx, eax
0x180021379  test    eax, eax
0x18002137b  jz      short loc_18002138E
0x18002137d  mov     ecx, 0C89019Bh; unsigned int
0x180021382  mov     edx, eax; int
0x180021384  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180021389  jmp     loc_180021488
0x18002138e  mov     rdx, [rbp+arg_8]
0x180021392  mov     rcx, rdi
0x180021395  call    CAFreeCertTypeProperty
0x18002139a  lea     r8, [rbp+arg_8]; unsigned __int16 ***
0x18002139e  mov     [rbp+arg_8], r13
0x1800213a2  lea     rdx, aDsdisplayname; "dsDisplayName"
0x1800213a9  mov     rcx, rdi; this
0x1800213ac  call    CAGetCertTypeProperty
0x1800213b1  test    eax, eax
0x1800213b3  jz      short loc_1800213D0
0x1800213b5  xor     r9d, r9d; int
0x1800213b8  mov     [rbp+arg_8], r13
0x1800213bc  mov     r8d, eax; int
0x1800213bf  lea     rcx, aDsdisplayname; "dsDisplayName"
0x1800213c6  mov     edx, 0C92019Bh; unsigned int
0x1800213cb  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800213d0  mov     rdx, [rbp+arg_8]
0x1800213d4  test    rdx, rdx
0x1800213d7  jz      short loc_180021406
0x1800213d9  mov     rcx, [rdx]; Src
0x1800213dc  test    rcx, rcx
0x1800213df  jz      short loc_1800213FA
0x1800213e1  mov     rdx, r15; unsigned __int16 **
0x1800213e4  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x1800213e9  mov     ebx, eax
0x1800213eb  test    eax, eax
0x1800213ed  jz      short loc_1800213F6
0x1800213ef  mov     ecx, 0C99019Bh
0x1800213f4  jmp     short loc_180021382
0x1800213f6  mov     rdx, [rbp+arg_8]
0x1800213fa  mov     rcx, rdi
0x1800213fd  call    CAFreeCertTypeProperty
0x180021402  mov     [rbp+arg_8], r13
0x180021406  lea     r8, [rbp+arg_8]; unsigned __int16 ***
0x18002140a  mov     rcx, rdi; this
0x18002140d  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x180021414  call    CAGetCertTypeProperty
0x180021419  test    eax, eax
0x18002141b  jz      short loc_180021438
0x18002141d  xor     r9d, r9d; int
0x180021420  mov     [rbp+arg_8], r13
0x180021424  mov     r8d, eax; int
0x180021427  lea     rcx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002142e  mov     edx, 0CA3019Bh; unsigned int
0x180021433  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180021438  mov     rdx, [rbp+arg_8]
0x18002143c  test    rdx, rdx
0x18002143f  jz      short loc_18002146A
0x180021441  mov     rdx, [rdx]; unsigned __int16 *
0x180021444  test    rdx, rdx
0x180021447  jz      short loc_18002146A
0x180021449  or      r8d, 0FFFFFFFFh; int
0x18002144d  mov     rcx, r12; char **
0x180021450  call    ?myConvertWszToSz@@YAHPEAPEADPEBGJ@Z; myConvertWszToSz(char * *,ushort const *,long)
0x180021455  test    eax, eax
0x180021457  jnz     short loc_18002146A
0x180021459  mov     ebx, 8007000Eh
0x18002145e  mov     ecx, 0CAA019Bh
0x180021463  mov     edx, ebx
0x180021465  jmp     loc_180021384
0x18002146a  mov     ebx, r13d
0x18002146d  jmp     short loc_180021488
0x18002146f  mov     r8d, 80070490h; int
0x180021475  mov     edx, 0C86019Bh; unsigned int
0x18002147a  mov     ebx, r8d
0x18002147d  xor     r9d, r9d; int
0x180021480  mov     rcx, rsi; unsigned __int16 *
0x180021483  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180021488  test    rdi, rdi
0x18002148b  jz      short loc_1800214A6
0x18002148d  mov     rdx, [rbp+arg_8]
0x180021491  test    rdx, rdx
0x180021494  jz      short loc_18002149E
0x180021496  mov     rcx, rdi
0x180021499  call    CAFreeCertTypeProperty
0x18002149e  mov     rcx, rdi
0x1800214a1  call    CACloseCertType
0x1800214a6  mov     eax, ebx
0x1800214a8  mov     rbx, [rsp+30h+arg_0]
0x1800214ad  add     rsp, 30h
0x1800214b1  pop     r15
0x1800214b3  pop     r14
0x1800214b5  pop     r13
0x1800214b7  pop     r12
0x1800214b9  pop     rdi
0x1800214ba  pop     rsi
0x1800214bb  pop     rbp
0x1800214bc  retn
```
