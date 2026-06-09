# AllocAndGetSubjectURL(ushort * *,_CERT_CONTEXT const *)

- ea: `0x18001ef18`
- end: `0x18001f018`
- name: `?AllocAndGetSubjectURL@@YAHPEAPEAGPEBU_CERT_CONTEXT@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(unsigned __int16 **, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f2b0`

## callees

- `0x18000590c`
- `0x18001ef18`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eff9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f006`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eff9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f006`
- `CRYPT32!CertFindExtension` at `0x18001ef4c`
- `CRYPT32!CertFindExtension` at `0x18001ef4c`
- `CRYPT32!CryptDecodeObject` at `0x18001ef8f`
- `CRYPT32!CryptDecodeObject` at `0x18001efd2`
- `CRYPT32!CryptDecodeObject` at `0x18001ef8f`
- `CRYPT32!CryptDecodeObject` at `0x18001efd2`

## pseudocode

```c
__int64 __fastcall AllocAndGetSubjectURL(unsigned __int16 **a1, const struct _CERT_CONTEXT *a2)
{
  PCERT_INFO pCertInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v5; // rsi
  unsigned int v6; // edi
  const unsigned __int16 **pvStructInfo; // rbx
  unsigned __int16 *v8; // rax
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF

  pCertInfo = a2->pCertInfo;
  pcbStructInfo = 0;
  *a1 = 0;
  Extension = CertFindExtension("2.5.29.7", pCertInfo->cExtension, pCertInfo->rgExtension);
  v5 = Extension;
  if ( Extension )
  {
    v6 = 1;
    CryptDecodeObject(1u, "2.5.29.7", Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo);
    pvStructInfo = (const unsigned __int16 **)LocalAlloc(0x40u, pcbStructInfo);
    if ( pvStructInfo )
    {
      if ( !CryptDecodeObject(1u, "2.5.29.7", v5->Value.pbData, v5->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
      {
        v6 = 0;
LABEL_7:
        LocalFree(pvStructInfo);
        return v6;
      }
      if ( *(_DWORD *)pvStructInfo == 7 )
      {
        v8 = AllocAndCopyWStr(pvStructInfo[1]);
        *a1 = v8;
        if ( v8 )
          goto LABEL_7;
      }
      LocalFree(pvStructInfo);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001ef18  push    rbx
0x18001ef1a  push    rsi
0x18001ef1b  push    rdi
0x18001ef1c  push    r14
0x18001ef1e  sub     rsp, 48h
0x18001ef22  mov     rdx, [rdx+18h]
0x18001ef26  mov     r14, rcx
0x18001ef29  mov     [rsp+68h+arg_0], 0
0x18001ef31  mov     qword ptr [rcx], 0
0x18001ef38  lea     rcx, a25297; "2.5.29.7"
0x18001ef3f  mov     r8, [rdx+0C8h]; rgExtensions
0x18001ef46  mov     edx, [rdx+0C0h]; cExtensions
0x18001ef4c  call    cs:__imp_CertFindExtension
0x18001ef52  mov     rsi, rax
0x18001ef55  test    rax, rax
0x18001ef58  jz      loc_18001F00C
0x18001ef5e  mov     r9d, [rsi+10h]; cbEncoded
0x18001ef62  lea     rax, [rsp+68h+arg_0]
0x18001ef67  mov     r8, [rsi+18h]; pbEncoded
0x18001ef6b  lea     rdx, a25297; "2.5.29.7"
0x18001ef72  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x18001ef77  mov     edi, 1
0x18001ef7c  mov     [rsp+68h+pvStructInfo], 0; pvStructInfo
0x18001ef85  mov     ecx, edi; dwCertEncodingType
0x18001ef87  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001ef8f  call    cs:__imp_CryptDecodeObject
0x18001ef95  mov     edx, [rsp+68h+arg_0]; uBytes
0x18001ef99  lea     ecx, [rdi+3Fh]; uFlags
0x18001ef9c  call    cs:__imp_LocalAlloc
0x18001efa2  mov     rbx, rax
0x18001efa5  test    rax, rax
0x18001efa8  jz      short loc_18001F00C
0x18001efaa  mov     r9d, [rsi+10h]; cbEncoded
0x18001efae  lea     rax, [rsp+68h+arg_0]
0x18001efb3  mov     r8, [rsi+18h]; pbEncoded
0x18001efb7  lea     rdx, a25297; "2.5.29.7"
0x18001efbe  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x18001efc3  mov     ecx, edi; dwCertEncodingType
0x18001efc5  mov     [rsp+68h+pvStructInfo], rbx; pvStructInfo
0x18001efca  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001efd2  call    cs:__imp_CryptDecodeObject
0x18001efd8  test    eax, eax
0x18001efda  jnz     short loc_18001EFE0
0x18001efdc  xor     edi, edi
0x18001efde  jmp     short loc_18001EFF6
0x18001efe0  cmp     dword ptr [rbx], 7
0x18001efe3  jnz     short loc_18001F003
0x18001efe5  mov     rcx, [rbx+8]; Src
0x18001efe9  call    ?AllocAndCopyWStr@@YAPEAGPEBG@Z; AllocAndCopyWStr(ushort const *)
0x18001efee  mov     [r14], rax
0x18001eff1  test    rax, rax
0x18001eff4  jz      short loc_18001F003
0x18001eff6  mov     rcx, rbx; hMem
0x18001eff9  call    cs:__imp_LocalFree
0x18001efff  mov     eax, edi
0x18001f001  jmp     short loc_18001F00E
0x18001f003  mov     rcx, rbx; hMem
0x18001f006  call    cs:__imp_LocalFree
0x18001f00c  xor     eax, eax
0x18001f00e  add     rsp, 48h
0x18001f012  pop     r14
0x18001f014  pop     rdi
0x18001f015  pop     rsi
0x18001f016  pop     rbx
0x18001f017  retn
```
