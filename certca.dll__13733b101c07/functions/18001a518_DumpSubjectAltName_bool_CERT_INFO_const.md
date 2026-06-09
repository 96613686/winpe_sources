# DumpSubjectAltName(bool,_CERT_INFO const *)

- ea: `0x18001a518`
- end: `0x18001a5d0`
- name: `?DumpSubjectAltName@@YAJ_NPEBU_CERT_INFO@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(char, const struct _CERT_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001af48`

## callees

- `0x180007da0`
- `0x180008400`
- `0x18001a518`
- `0x18001ad64`
- `0x180021e30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a5b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a5b8`
- `CRYPT32!CertFindExtension` at `0x18001a545`
- `CRYPT32!CertFindExtension` at `0x18001a545`

## pseudocode

```c
__int64 __fastcall DumpSubjectAltName(char a1, const struct _CERT_INFO *a2)
{
  CERT_EXTENSION *rgExtension; // r8
  DWORD cExtension; // edx
  HLOCAL v5; // rbx
  PCERT_EXTENSION Extension; // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // edi
  HLOCAL hMem; // [rsp+48h] [rbp+10h] BYREF

  rgExtension = a2->rgExtension;
  cExtension = a2->cExtension;
  v5 = 0;
  hMem = 0;
  Extension = CertFindExtension("2.5.29.17", cExtension, rgExtension);
  if ( !Extension )
    goto LABEL_7;
  v8 = myCryptFormatObject(
         Extension->Value.cbData,
         v7,
         Extension->pszObjId,
         Extension->Value.pbData,
         Extension->Value.cbData,
         (unsigned __int16 **)&hMem);
  v9 = v8;
  if ( !v8 )
  {
    v5 = hMem;
    if ( a1 )
      DbgPrintf(0xFFFFFFFF, "  SubjectAltName: %ws\n", hMem);
    else
      myConsolePrintf(L"  SubjectAltName: %ws\n", hMem);
LABEL_7:
    v9 = 0;
    goto LABEL_8;
  }
  CSPrintErrorLineFile(0x134C01A3u, v8);
  v5 = hMem;
LABEL_8:
  LocalFree(v5);
  return v9;
}

```

## disassembly

```asm
0x18001a518  mov     [rsp+arg_0], rbx
0x18001a51d  mov     [rsp+arg_10], rsi
0x18001a522  push    rdi
0x18001a523  sub     rsp, 30h
0x18001a527  mov     r8, [rdx+0C8h]; rgExtensions
0x18001a52e  mov     sil, cl
0x18001a531  mov     edx, [rdx+0C0h]; cExtensions
0x18001a537  lea     rcx, a252917; "2.5.29.17"
0x18001a53e  xor     ebx, ebx
0x18001a540  mov     [rsp+38h+hMem], rbx
0x18001a545  call    cs:__imp_CertFindExtension
0x18001a54b  test    rax, rax
0x18001a54e  jz      short loc_18001A5B3
0x18001a550  mov     r9, [rax+18h]; unsigned __int8 *
0x18001a554  lea     rcx, [rsp+38h+hMem]
0x18001a559  mov     r8, [rax]; char *
0x18001a55c  mov     [rsp+38h+var_10], rcx; unsigned __int16 **
0x18001a561  mov     ecx, [rax+10h]; unsigned int
0x18001a564  mov     [rsp+38h+var_18], ecx; unsigned int
0x18001a568  call    ?myCryptFormatObject@@YAJKKPEBDPEBEKPEAPEAG@Z; myCryptFormatObject(ulong,ulong,char const *,uchar const *,ulong,ushort * *)
0x18001a56d  mov     edi, eax
0x18001a56f  test    eax, eax
0x18001a571  jz      short loc_18001A586
0x18001a573  mov     edx, eax; int
0x18001a575  mov     ecx, 134C01A3h; unsigned int
0x18001a57a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a57f  mov     rbx, [rsp+38h+hMem]
0x18001a584  jmp     short loc_18001A5B5
0x18001a586  mov     rbx, [rsp+38h+hMem]
0x18001a58b  test    sil, sil
0x18001a58e  jz      short loc_18001A5A4
0x18001a590  mov     r8, rbx
0x18001a593  lea     rdx, aSubjectaltname; "  SubjectAltName: %ws\n"
0x18001a59a  or      ecx, 0FFFFFFFFh; unsigned int
0x18001a59d  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x18001a5a2  jmp     short loc_18001A5B3
0x18001a5a4  mov     rdx, rbx
0x18001a5a7  lea     rcx, aSubjectaltname_0; "  SubjectAltName: %ws\n"
0x18001a5ae  call    ?myConsolePrintf@@YAHPEBGZZ; myConsolePrintf(ushort const *,...)
0x18001a5b3  xor     edi, edi
0x18001a5b5  mov     rcx, rbx; hMem
0x18001a5b8  call    cs:__imp_LocalFree
0x18001a5be  mov     rbx, [rsp+38h+arg_0]
0x18001a5c3  mov     eax, edi
0x18001a5c5  mov     rsi, [rsp+38h+arg_10]
0x18001a5ca  add     rsp, 30h
0x18001a5ce  pop     rdi
0x18001a5cf  retn
```
