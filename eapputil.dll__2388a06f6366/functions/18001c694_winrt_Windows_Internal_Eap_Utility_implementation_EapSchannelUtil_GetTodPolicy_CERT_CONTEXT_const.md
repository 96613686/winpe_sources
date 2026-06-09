# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetTodPolicy(_CERT_CONTEXT const *)

- ea: `0x18001c694`
- end: `0x18001c80b`
- name: `?GetTodPolicy@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AW4EapTlsCertificateTodPolicy@34567@PEBU_CERT_CONTEXT@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001eda4`

## callees

- `0x1800025a0`
- `0x180002b78`
- `0x180003868`
- `0x18001c694`
- `0x180023760`
- `0x180030564`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18001c6c1`
- `CRYPT32!CertFindExtension` at `0x18001c6c1`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001c70e`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001c76b`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001c70e`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001c76b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetTodPolicy(__int64 a1)
{
  PCERT_EXTENSION Extension; // rbp
  unsigned int v3; // esi
  const char *v4; // r9
  DWORD v5; // ebx
  _QWORD *pvStructInfo; // rdi
  const char *v7; // r9
  __int64 v8; // rbx
  __int64 v9; // r14
  const char *v10; // rbp
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+68h] [rbp+10h]

  Extension = CertFindExtension(
                "2.5.29.32",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  if ( !Extension )
    return 0;
  pcbStructInfo = 0;
  v3 = 1;
  if ( !CryptDecodeObjectEx(
          *(_DWORD *)a1,
          (LPCSTR)0x10,
          Extension->Value.pbData,
          Extension->Value.cbData,
          1u,
          0,
          0,
          &pcbStructInfo) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7AA,
      (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v4);
  v5 = pcbStructInfo;
  pvStructInfo = operator new[](pcbStructInfo);
  memset_0(pvStructInfo, 0, v5);
  v14 = pvStructInfo;
  if ( !CryptDecodeObjectEx(
          *(_DWORD *)a1,
          (LPCSTR)0x10,
          Extension->Value.pbData,
          Extension->Value.cbData,
          1u,
          0,
          pvStructInfo,
          &pcbStructInfo) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7B6,
      (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      v7);
  if ( !*(_DWORD *)pvStructInfo )
  {
LABEL_9:
    operator delete(pvStructInfo);
    return 0;
  }
  v8 = 0;
  v9 = pvStructInfo[1];
  while ( 1 )
  {
    v10 = *(const char **)(v9 + 24 * v8);
    if ( !strcmp_0(v10, "1.3.6.1.4.1.40808.1.3.1") )
      break;
    if ( !strcmp_0(v10, "1.3.6.1.4.1.40808.1.3.2") )
      goto LABEL_12;
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= *(_DWORD *)pvStructInfo )
      goto LABEL_9;
  }
  v3 = 2;
LABEL_12:
  operator delete(pvStructInfo);
  return v3;
}

```

## disassembly

```asm
0x18001c694  mov     [rsp+arg_10], rbx
0x18001c699  mov     [rsp+arg_18], rbp
0x18001c69e  push    rsi
0x18001c69f  push    rdi
0x18001c6a0  push    r14
0x18001c6a2  sub     rsp, 40h
0x18001c6a6  mov     r14, rcx
0x18001c6a9  mov     rdx, [rcx+18h]
0x18001c6ad  mov     r8, [rdx+0C8h]; rgExtensions
0x18001c6b4  mov     edx, [rdx+0C0h]; cExtensions
0x18001c6ba  lea     rcx, pszObjId; "2.5.29.32"
0x18001c6c1  call    cs:__imp_CertFindExtension
0x18001c6c7  mov     rbp, rax
0x18001c6ca  test    rax, rax
0x18001c6cd  jz      loc_18001C7C1
0x18001c6d3  mov     [rsp+58h+arg_0], 0
0x18001c6db  lea     rax, [rsp+58h+arg_0]
0x18001c6e0  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18001c6e5  mov     [rsp+58h+pvStructInfo], 0; pvStructInfo
0x18001c6ee  mov     [rsp+58h+pDecodePara], 0; pDecodePara
0x18001c6f7  mov     esi, 1
0x18001c6fc  mov     [rsp+58h+dwFlags], esi; dwFlags
0x18001c700  mov     r9d, [rbp+10h]; cbEncoded
0x18001c704  mov     r8, [rbp+18h]; pbEncoded
0x18001c708  lea     edx, [rsi+0Fh]; lpszStructType
0x18001c70b  mov     ecx, [r14]; dwCertEncodingType
0x18001c70e  call    cs:__imp_CryptDecodeObjectEx
0x18001c714  mov     rcx, [rsp+58h]; this
0x18001c719  test    eax, eax
0x18001c71b  jz      loc_18001C7F9
0x18001c721  mov     ebx, [rsp+58h+arg_0]
0x18001c725  mov     ecx, ebx; unsigned __int64
0x18001c727  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c72c  mov     rdi, rax
0x18001c72f  mov     r8d, ebx; Size
0x18001c732  xor     edx, edx; Val
0x18001c734  mov     rcx, rax; void *
0x18001c737  call    memset_0
0x18001c73c  mov     [rsp+58h+arg_8], rdi
0x18001c741  lea     rax, [rsp+58h+arg_0]
0x18001c746  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18001c74b  mov     [rsp+58h+pvStructInfo], rdi; pvStructInfo
0x18001c750  mov     [rsp+58h+pDecodePara], 0; pDecodePara
0x18001c759  mov     [rsp+58h+dwFlags], esi; dwFlags
0x18001c75d  mov     r9d, [rbp+10h]; cbEncoded
0x18001c761  mov     r8, [rbp+18h]; pbEncoded
0x18001c765  lea     edx, [rsi+0Fh]; lpszStructType
0x18001c768  mov     ecx, [r14]; dwCertEncodingType
0x18001c76b  call    cs:__imp_CryptDecodeObjectEx
0x18001c771  mov     rcx, [rsp+58h]; this
0x18001c776  test    eax, eax
0x18001c778  jz      short loc_18001C7E7
0x18001c77a  cmp     dword ptr [rdi], 0
0x18001c77d  jbe     short loc_18001C7B9
0x18001c77f  xor     ebx, ebx
0x18001c781  mov     r14, [rdi+8]
0x18001c785  lea     rcx, [rbx+rbx*2]
0x18001c789  mov     rbp, [r14+rcx*8]
0x18001c78d  lea     rdx, Str2; "1.3.6.1.4.1.40808.1.3.1"
0x18001c794  mov     rcx, rbp; Str1
0x18001c797  call    strcmp_0
0x18001c79c  test    eax, eax
0x18001c79e  jz      short loc_18001C7D6
0x18001c7a0  lea     rdx, a13614140808132; "1.3.6.1.4.1.40808.1.3.2"
0x18001c7a7  mov     rcx, rbp; Str1
0x18001c7aa  call    strcmp_0
0x18001c7af  test    eax, eax
0x18001c7b1  jz      short loc_18001C7DB
0x18001c7b3  add     ebx, esi
0x18001c7b5  cmp     ebx, [rdi]
0x18001c7b7  jb      short loc_18001C785
0x18001c7b9  mov     rcx, rdi; void *
0x18001c7bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c7c1  xor     eax, eax
0x18001c7c3  mov     rbx, [rsp+58h+arg_10]
0x18001c7c8  mov     rbp, [rsp+58h+arg_18]
0x18001c7cd  add     rsp, 40h
0x18001c7d1  pop     r14
0x18001c7d3  pop     rdi
0x18001c7d4  pop     rsi
0x18001c7d5  retn
0x18001c7d6  mov     esi, 2
0x18001c7db  mov     rcx, rdi; void *
0x18001c7de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c7e3  mov     eax, esi
0x18001c7e5  jmp     short loc_18001C7C3
0x18001c7e7  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001c7ee  mov     edx, 7B6h; void *
0x18001c7f3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001c7f9  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001c800  mov     edx, 7AAh; void *
0x18001c805  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
