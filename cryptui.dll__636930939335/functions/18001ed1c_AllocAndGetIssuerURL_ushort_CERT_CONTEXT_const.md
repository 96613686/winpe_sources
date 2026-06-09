# AllocAndGetIssuerURL(ushort * *,_CERT_CONTEXT const *)

- ea: `0x18001ed1c`
- end: `0x18001ef12`
- name: `?AllocAndGetIssuerURL@@YAHPEAPEAGPEBU_CERT_CONTEXT@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(unsigned __int16 **, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f2b0`

## callees

- `0x18000590c`
- `0x18001ed1c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001edb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ee82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001edb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ee82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ef08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ef08`
- `CRYPT32!CertFindExtension` at `0x18001ed62`
- `CRYPT32!CertFindExtension` at `0x18001ee39`
- `CRYPT32!CertFindExtension` at `0x18001ed62`
- `CRYPT32!CertFindExtension` at `0x18001ee39`
- `CRYPT32!CryptDecodeObject` at `0x18001eda3`
- `CRYPT32!CryptDecodeObject` at `0x18001ede8`
- `CRYPT32!CryptDecodeObject` at `0x18001ee73`
- `CRYPT32!CryptDecodeObject` at `0x18001eeb4`
- `CRYPT32!CryptDecodeObject` at `0x18001eda3`
- `CRYPT32!CryptDecodeObject` at `0x18001ede8`
- `CRYPT32!CryptDecodeObject` at `0x18001ee73`
- `CRYPT32!CryptDecodeObject` at `0x18001eeb4`

## pseudocode

```c
__int64 __fastcall AllocAndGetIssuerURL(unsigned __int16 **a1, const struct _CERT_CONTEXT *a2)
{
  PCERT_INFO pCertInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v6; // rsi
  unsigned int v7; // ebx
  const unsigned __int16 **pvStructInfo; // rdi
  const unsigned __int16 *v9; // rcx
  PCERT_EXTENSION v10; // rax
  PCERT_EXTENSION v11; // rsi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v14; // rax
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF
  DWORD v16; // [rsp+68h] [rbp+10h] BYREF

  pcbStructInfo = 0;
  pCertInfo = a2->pCertInfo;
  v16 = 0;
  *a1 = 0;
  Extension = CertFindExtension("1.3.6.1.4.1.311.2.1.10", pCertInfo->cExtension, pCertInfo->rgExtension);
  v6 = Extension;
  v7 = 1;
  if ( Extension )
  {
    CryptDecodeObject(1u, (LPCSTR)0x7D0, Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo);
    pvStructInfo = (const unsigned __int16 **)LocalAlloc(0x40u, pcbStructInfo);
    if ( !pvStructInfo )
      return 0;
    if ( !CryptDecodeObject(1u, (LPCSTR)0x7D0, v6->Value.pbData, v6->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
      goto LABEL_16;
    v9 = *pvStructInfo;
    if ( !*pvStructInfo )
      goto LABEL_16;
    if ( *(_DWORD *)v9 == 1 || *(_DWORD *)v9 == 3 )
    {
      v14 = AllocAndCopyWStr(*((const unsigned __int16 **)v9 + 1));
      *a1 = v14;
      if ( v14 )
        goto LABEL_17;
LABEL_16:
      v7 = 0;
      goto LABEL_17;
    }
    LocalFree(pvStructInfo);
  }
  v10 = CertFindExtension("2.5.29.8", a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
  v11 = v10;
  if ( !v10 )
    return 0;
  CryptDecodeObject(1u, "2.5.29.8", v10->Value.pbData, v10->Value.cbData, 0, 0, &v16);
  pvStructInfo = (const unsigned __int16 **)LocalAlloc(0x40u, v16);
  if ( !pvStructInfo )
    return 0;
  if ( !CryptDecodeObject(1u, "2.5.29.8", v11->Value.pbData, v11->Value.cbData, 0, pvStructInfo, &v16) )
    goto LABEL_16;
  if ( *(_DWORD *)pvStructInfo != 7 || (v12 = AllocAndCopyWStr(pvStructInfo[1]), (*a1 = v12) == 0) )
  {
    LocalFree(pvStructInfo);
    return 0;
  }
LABEL_17:
  LocalFree(pvStructInfo);
  return v7;
}

```

## disassembly

```asm
0x18001ed1c  mov     rax, rsp
0x18001ed1f  mov     [rax+18h], rbx
0x18001ed23  mov     [rax+20h], rbp
0x18001ed27  push    rsi
0x18001ed28  push    rdi
0x18001ed29  push    r14
0x18001ed2b  sub     rsp, 40h
0x18001ed2f  mov     rbp, rdx
0x18001ed32  mov     dword ptr [rax+8], 0
0x18001ed39  mov     rdx, [rdx+18h]
0x18001ed3d  mov     r14, rcx
0x18001ed40  mov     dword ptr [rax+10h], 0
0x18001ed47  mov     qword ptr [rcx], 0
0x18001ed4e  lea     rcx, pszObjId; "1.3.6.1.4.1.311.2.1.10"
0x18001ed55  mov     r8, [rdx+0C8h]; rgExtensions
0x18001ed5c  mov     edx, [rdx+0C0h]; cExtensions
0x18001ed62  call    cs:__imp_CertFindExtension
0x18001ed68  mov     rsi, rax
0x18001ed6b  mov     ebx, 1
0x18001ed70  test    rax, rax
0x18001ed73  jz      loc_18001EE1E
0x18001ed79  mov     r9d, [rsi+10h]; cbEncoded
0x18001ed7d  lea     rax, [rsp+58h+arg_0]
0x18001ed82  mov     r8, [rsi+18h]; pbEncoded
0x18001ed86  mov     edx, 7D0h; lpszStructType
0x18001ed8b  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18001ed90  mov     ecx, ebx; dwCertEncodingType
0x18001ed92  mov     [rsp+58h+pvStructInfo], 0; pvStructInfo
0x18001ed9b  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001eda3  call    cs:__imp_CryptDecodeObject
0x18001eda9  mov     edx, [rsp+58h+arg_0]; uBytes
0x18001edad  lea     ecx, [rbx+3Fh]; uFlags
0x18001edb0  call    cs:__imp_LocalAlloc
0x18001edb6  mov     rdi, rax
0x18001edb9  test    rax, rax
0x18001edbc  jz      loc_18001EEDD
0x18001edc2  mov     r9d, [rsi+10h]; cbEncoded
0x18001edc6  lea     rax, [rsp+58h+arg_0]
0x18001edcb  mov     r8, [rsi+18h]; pbEncoded
0x18001edcf  mov     edx, 7D0h; lpszStructType
0x18001edd4  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18001edd9  mov     ecx, ebx; dwCertEncodingType
0x18001eddb  mov     [rsp+58h+pvStructInfo], rdi; pvStructInfo
0x18001ede0  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001ede8  call    cs:__imp_CryptDecodeObject
0x18001edee  test    eax, eax
0x18001edf0  jz      loc_18001EF03
0x18001edf6  mov     rcx, [rdi]
0x18001edf9  test    rcx, rcx
0x18001edfc  jz      loc_18001EF03
0x18001ee02  mov     edx, [rcx]
0x18001ee04  sub     edx, ebx
0x18001ee06  jz      loc_18001EEF2
0x18001ee0c  cmp     edx, 2
0x18001ee0f  jz      loc_18001EEF2
0x18001ee15  mov     rcx, rdi; hMem
0x18001ee18  call    cs:__imp_LocalFree
0x18001ee1e  mov     rdx, [rbp+18h]
0x18001ee22  lea     rbp, a25298; "2.5.29.8"
0x18001ee29  mov     rcx, rbp; pszObjId
0x18001ee2c  mov     r8, [rdx+0C8h]; rgExtensions
0x18001ee33  mov     edx, [rdx+0C0h]; cExtensions
0x18001ee39  call    cs:__imp_CertFindExtension
0x18001ee3f  mov     rsi, rax
0x18001ee42  test    rax, rax
0x18001ee45  jz      loc_18001EEDD
0x18001ee4b  mov     r9d, [rsi+10h]; cbEncoded
0x18001ee4f  lea     rax, [rsp+58h+arg_8]
0x18001ee54  mov     r8, [rsi+18h]; pbEncoded
0x18001ee58  mov     rdx, rbp; lpszStructType
0x18001ee5b  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18001ee60  mov     ecx, ebx; dwCertEncodingType
0x18001ee62  mov     [rsp+58h+pvStructInfo], 0; pvStructInfo
0x18001ee6b  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001ee73  call    cs:__imp_CryptDecodeObject
0x18001ee79  mov     edx, [rsp+58h+arg_8]; uBytes
0x18001ee7d  mov     ecx, 40h ; '@'; uFlags
0x18001ee82  call    cs:__imp_LocalAlloc
0x18001ee88  mov     rdi, rax
0x18001ee8b  test    rax, rax
0x18001ee8e  jz      short loc_18001EEDD
0x18001ee90  mov     r9d, [rsi+10h]; cbEncoded
0x18001ee94  lea     rax, [rsp+58h+arg_8]
0x18001ee99  mov     r8, [rsi+18h]; pbEncoded
0x18001ee9d  mov     rdx, rbp; lpszStructType
0x18001eea0  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18001eea5  mov     ecx, ebx; dwCertEncodingType
0x18001eea7  mov     [rsp+58h+pvStructInfo], rdi; pvStructInfo
0x18001eeac  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001eeb4  call    cs:__imp_CryptDecodeObject
0x18001eeba  test    eax, eax
0x18001eebc  jz      short loc_18001EF03
0x18001eebe  cmp     dword ptr [rdi], 7
0x18001eec1  jnz     short loc_18001EED4
0x18001eec3  mov     rcx, [rdi+8]; Src
0x18001eec7  call    ?AllocAndCopyWStr@@YAPEAGPEBG@Z; AllocAndCopyWStr(ushort const *)
0x18001eecc  mov     [r14], rax
0x18001eecf  test    rax, rax
0x18001eed2  jnz     short loc_18001EF05
0x18001eed4  mov     rcx, rdi; hMem
0x18001eed7  call    cs:__imp_LocalFree
0x18001eedd  xor     eax, eax
0x18001eedf  mov     rbx, [rsp+58h+arg_10]
0x18001eee4  mov     rbp, [rsp+58h+arg_18]
0x18001eee9  add     rsp, 40h
0x18001eeed  pop     r14
0x18001eeef  pop     rdi
0x18001eef0  pop     rsi
0x18001eef1  retn
0x18001eef2  mov     rcx, [rcx+8]; Src
0x18001eef6  call    ?AllocAndCopyWStr@@YAPEAGPEBG@Z; AllocAndCopyWStr(ushort const *)
0x18001eefb  mov     [r14], rax
0x18001eefe  test    rax, rax
0x18001ef01  jnz     short loc_18001EF05
0x18001ef03  xor     ebx, ebx
0x18001ef05  mov     rcx, rdi; hMem
0x18001ef08  call    cs:__imp_LocalFree
0x18001ef0e  mov     eax, ebx
0x18001ef10  jmp     short loc_18001EEDF
```
