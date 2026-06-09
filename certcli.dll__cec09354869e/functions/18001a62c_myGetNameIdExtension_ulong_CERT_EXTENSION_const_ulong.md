# myGetNameIdExtension(ulong,_CERT_EXTENSION const *,ulong *)

- ea: `0x18001a62c`
- end: `0x18001a6dd`
- name: `?myGetNameIdExtension@@YAJKPEBU_CERT_EXTENSION@@PEAK@Z`
- size: `177`
- prototype: `__int64 __fastcall(DWORD cExtensions, CERT_EXTENSION *__attribute__((__org_arrdim(0,0))) rgExtensions, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a5e8`

## callees

- `0x18001a62c`
- `0x180021438`

## import_xrefs

- `CRYPT32!CryptDecodeObject` at `0x18001a6b3`
- `CRYPT32!CryptDecodeObject` at `0x18001a6b3`
- `CRYPT32!CertFindExtension` at `0x18001a658`
- `CRYPT32!CertFindExtension` at `0x18001a658`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001a66f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001a66f`

## pseudocode

```c
__int64 __fastcall myGetNameIdExtension(DWORD cExtensions, CERT_EXTENSION rgExtensions[], unsigned int *a3)
{
  PCERT_EXTENSION Extension; // rax
  unsigned int v5; // ebx
  unsigned int v6; // ecx
  int v7; // edx
  unsigned int pvStructInfo; // [rsp+60h] [rbp+18h] BYREF
  DWORD pcbStructInfo; // [rsp+68h] [rbp+20h] BYREF

  *a3 = -1;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  Extension = CertFindExtension("1.3.6.1.4.1.311.21.1", cExtensions, rgExtensions);
  if ( Extension )
  {
    pcbStructInfo = 4;
    pvStructInfo = 0;
    if ( CryptDecodeObject(
           1u,
           (LPCSTR)0x1B,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0,
           &pvStructInfo,
           &pcbStructInfo) )
    {
      *a3 = pvStructInfo;
      return 0;
    }
    v5 = myHLastError();
    v7 = v5;
    v6 = 557908387;
  }
  else
  {
    v5 = -2147024894;
    v6 = 556990883;
    v7 = -2147024894;
  }
  CSPrintErrorLineFile(v6, v7);
  return v5;
}

```

## disassembly

```asm
0x18001a62c  push    rbx
0x18001a62e  sub     rsp, 40h
0x18001a632  mov     rbx, r8
0x18001a635  mov     dword ptr [r8], 0FFFFFFFFh
0x18001a63c  mov     r8, rdx; rgExtensions
0x18001a63f  mov     [rsp+48h+arg_10], 0
0x18001a647  mov     edx, ecx; cExtensions
0x18001a649  mov     [rsp+48h+arg_18], 0
0x18001a651  lea     rcx, a136141311211; "1.3.6.1.4.1.311.21.1"
0x18001a658  call    cs:__imp_CertFindExtension
0x18001a65e  test    rax, rax
0x18001a661  jnz     short loc_18001A677
0x18001a663  mov     ebx, 80070002h
0x18001a668  mov     ecx, 213301A3h
0x18001a66d  mov     edx, ebx
0x18001a66f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a675  jmp     short loc_18001A6D5
0x18001a677  mov     [rsp+48h+arg_18], 4
0x18001a67f  lea     rcx, [rsp+48h+arg_18]
0x18001a684  mov     [rsp+48h+pcbStructInfo], rcx; pcbStructInfo
0x18001a689  mov     edx, 1Bh; lpszStructType
0x18001a68e  lea     rcx, [rsp+48h+arg_10]
0x18001a693  mov     [rsp+48h+arg_10], 0
0x18001a69b  mov     r9d, [rax+10h]; cbEncoded
0x18001a69f  mov     r8, [rax+18h]; pbEncoded
0x18001a6a3  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x18001a6a8  lea     ecx, [rdx-1Ah]; dwCertEncodingType
0x18001a6ab  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18001a6b3  call    cs:__imp_CryptDecodeObject
0x18001a6b9  test    eax, eax
0x18001a6bb  jnz     short loc_18001A6CD
0x18001a6bd  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a6c2  mov     ebx, eax
0x18001a6c4  mov     edx, eax
0x18001a6c6  mov     ecx, 214101A3h
0x18001a6cb  jmp     short loc_18001A66F
0x18001a6cd  mov     eax, [rsp+48h+arg_10]
0x18001a6d1  mov     [rbx], eax
0x18001a6d3  xor     ebx, ebx
0x18001a6d5  mov     eax, ebx
0x18001a6d7  add     rsp, 40h
0x18001a6db  pop     rbx
0x18001a6dc  retn
```
