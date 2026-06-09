# GetCrlReason(_CRL_ENTRY *)

- ea: `0x18001a174`
- end: `0x18001a1dc`
- name: `?GetCrlReason@@YAKPEAU_CRL_ENTRY@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(struct _CRL_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f140`

## callees

- `0x18001a174`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18001a18e`
- `CRYPT32!CertFindExtension` at `0x18001a18e`
- `CRYPT32!CryptDecodeObject` at `0x18001a1cd`
- `CRYPT32!CryptDecodeObject` at `0x18001a1cd`

## pseudocode

```c
__int64 __fastcall GetCrlReason(struct _CRL_ENTRY *a1)
{
  CERT_EXTENSION *rgExtension; // r8
  DWORD cExtension; // edx
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  unsigned int pvStructInfo; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbStructInfo; // [rsp+58h] [rbp+10h] BYREF

  rgExtension = a1->rgExtension;
  cExtension = a1->cExtension;
  pvStructInfo = 0;
  Extension = CertFindExtension("2.5.29.21", cExtension, rgExtension);
  if ( Extension )
  {
    cbData = Extension->Value.cbData;
    pbData = Extension->Value.pbData;
    pcbStructInfo = 4;
    CryptDecodeObject(1u, (LPCSTR)0x1D, pbData, cbData, 0, &pvStructInfo, &pcbStructInfo);
  }
  return pvStructInfo;
}

```

## disassembly

```asm
0x18001a174  sub     rsp, 48h
0x18001a178  mov     r8, [rcx+20h]; rgExtensions
0x18001a17c  mov     edx, [rcx+18h]; cExtensions
0x18001a17f  lea     rcx, a252921; "2.5.29.21"
0x18001a186  mov     [rsp+48h+arg_0], 0
0x18001a18e  call    cs:__imp_CertFindExtension
0x18001a194  test    rax, rax
0x18001a197  jz      short loc_18001A1D3
0x18001a199  mov     r9d, [rax+10h]; cbEncoded
0x18001a19d  lea     rcx, [rsp+48h+arg_8]
0x18001a1a2  mov     r8, [rax+18h]; pbEncoded
0x18001a1a6  mov     edx, 1Dh; lpszStructType
0x18001a1ab  mov     [rsp+48h+pcbStructInfo], rcx; pcbStructInfo
0x18001a1b0  lea     rcx, [rsp+48h+arg_0]
0x18001a1b5  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x18001a1ba  mov     [rsp+48h+arg_8], 4
0x18001a1c2  lea     ecx, [rdx-1Ch]; dwCertEncodingType
0x18001a1c5  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18001a1cd  call    cs:__imp_CryptDecodeObject
0x18001a1d3  mov     eax, [rsp+48h+arg_0]
0x18001a1d7  add     rsp, 48h
0x18001a1db  retn
```
