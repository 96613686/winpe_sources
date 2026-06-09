# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TryGetClientCertificateName(_CERT_CONTEXT const *)

- ea: `0x180029aa4`
- end: `0x180029d4d`
- name: `?TryGetClientCertificateName@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AV?$optional@Uhstring@winrt@@@std@@PEBU_CERT_CONTEXT@@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180029968`

## callees

- `0x1800025a0`
- `0x180002b78`
- `0x180003868`
- `0x180007eac`
- `0x180008274`
- `0x180023760`
- `0x180029aa4`
- `0x180030564`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180029ad1`
- `CRYPT32!CertFindExtension` at `0x180029ad1`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029b2d`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029b97`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029c42`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029cb1`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029b2d`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029b97`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029c42`
- `CRYPT32!CryptDecodeObjectEx` at `0x180029cb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TryGetClientCertificateName(
        __int64 a1,
        __int64 a2)
{
  PCERT_EXTENSION Extension; // rsi
  const char *v5; // r9
  DWORD v6; // ebx
  _QWORD *pvStructInfo; // r14
  const char *v8; // r9
  __int64 v9; // rsi
  int v10; // ebx
  __int64 v11; // r15
  const char *v13; // r9
  DWORD v14; // ebx
  void *v15; // rbp
  const char *v16; // rdx
  const char *v17; // r9
  unsigned int v18; // esi
  struct winrt::impl::shared_hstring_header *v19; // r15
  const void *v20; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD pcbStructInfo; // [rsp+98h] [rbp+10h] BYREF
  DWORD v23; // [rsp+A0h] [rbp+18h] BYREF
  _QWORD *v24; // [rsp+A8h] [rbp+20h]

  Extension = CertFindExtension(
                "2.5.29.17",
                *(_DWORD *)(*(_QWORD *)(a2 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a2 + 24) + 200LL));
  if ( Extension )
  {
    pcbStructInfo = 0;
    if ( !CryptDecodeObjectEx(
            *(_DWORD *)a2,
            (LPCSTR)0xC,
            Extension->Value.pbData,
            Extension->Value.cbData,
            1u,
            0,
            0,
            &pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2FC,
        (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        v5);
    v6 = pcbStructInfo;
    pvStructInfo = operator new[](pcbStructInfo);
    memset_0(pvStructInfo, 0, v6);
    v24 = pvStructInfo;
    if ( !CryptDecodeObjectEx(
            *(_DWORD *)a2,
            (LPCSTR)0xC,
            Extension->Value.pbData,
            Extension->Value.cbData,
            1u,
            0,
            pvStructInfo,
            &pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x308,
        (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        v8);
    v9 = pvStructInfo[1];
    v10 = *(_DWORD *)pvStructInfo;
    if ( *(_DWORD *)pvStructInfo )
    {
      while ( 1 )
      {
        if ( *(_DWORD *)v9 == 1 )
        {
          v11 = *(_QWORD *)(v9 + 8);
          if ( v11 )
          {
            if ( !strcmp_0("1.3.6.1.4.1.311.20.2.3", *(const char **)v11) )
              break;
          }
        }
        v9 += 24;
        if ( !--v10 )
          goto LABEL_10;
      }
      v23 = 0;
      if ( !CryptDecodeObjectEx(
              *(_DWORD *)a2,
              (LPCSTR)0x18,
              *(const BYTE **)(v11 + 16),
              *(_DWORD *)(v11 + 8),
              1u,
              0,
              0,
              &v23) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x31C,
          (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
          v13);
      v14 = v23;
      v15 = operator new[](v23);
      memset_0(v15, 0, v14);
      if ( !CryptDecodeObjectEx(
              *(_DWORD *)a2,
              (LPCSTR)0x18,
              *(const BYTE **)(*(_QWORD *)(v9 + 8) + 16LL),
              *(_DWORD *)(*(_QWORD *)(v9 + 8) + 8LL),
              1u,
              0,
              v15,
              &v23) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x328,
          (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
          v17);
      v18 = *((_DWORD *)v15 + 2) >> 1;
      if ( v18 )
      {
        v20 = (const void *)*((_QWORD *)v15 + 2);
        v19 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v18, v16);
        memcpy_s((char *)v19 + 28, 2LL * v18, v20, 2LL * v18);
      }
      else
      {
        v19 = 0;
      }
      *(_QWORD *)a1 = v19;
      *(_BYTE *)(a1 + 8) = 1;
      operator delete(v15);
    }
    else
    {
LABEL_10:
      *(_BYTE *)(a1 + 8) = 0;
    }
    operator delete(pvStructInfo);
  }
  else
  {
    *(_BYTE *)(a1 + 8) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180029aa4  push    rbx
0x180029aa6  push    rbp
0x180029aa7  push    rsi
0x180029aa8  push    rdi
0x180029aa9  push    r12
0x180029aab  push    r14
0x180029aad  push    r15
0x180029aaf  sub     rsp, 50h
0x180029ab3  mov     r12, rdx
0x180029ab6  mov     rdi, rcx
0x180029ab9  mov     rdx, [rdx+18h]
0x180029abd  mov     r8, [rdx+0C8h]; rgExtensions
0x180029ac4  mov     edx, [rdx+0C0h]; cExtensions
0x180029aca  lea     rcx, a252917; "2.5.29.17"
0x180029ad1  call    cs:__imp_CertFindExtension
0x180029ad7  mov     rsi, rax
0x180029ada  test    rax, rax
0x180029add  jnz     short loc_180029AE7
0x180029adf  mov     [rdi+8], al
0x180029ae2  jmp     loc_180029BED
0x180029ae7  mov     [rsp+88h+arg_8], 0
0x180029af2  lea     rax, [rsp+88h+arg_8]
0x180029afa  mov     [rsp+88h+pcbStructInfo], rax; pcbStructInfo
0x180029aff  mov     [rsp+88h+pvStructInfo], 0; pvStructInfo
0x180029b08  mov     [rsp+88h+pDecodePara], 0; pDecodePara
0x180029b11  mov     ebp, 1
0x180029b16  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x180029b1a  mov     r9d, [rsi+10h]; cbEncoded
0x180029b1e  mov     r8, [rsi+18h]; pbEncoded
0x180029b22  lea     r15d, [rbp+0Bh]
0x180029b26  mov     edx, r15d; lpszStructType
0x180029b29  mov     ecx, [r12]; dwCertEncodingType
0x180029b2d  call    cs:__imp_CryptDecodeObjectEx
0x180029b33  mov     rcx, [rsp+88h]; this
0x180029b3b  test    eax, eax
0x180029b3d  jz      loc_180029D17
0x180029b43  mov     ebx, [rsp+88h+arg_8]
0x180029b4a  mov     ecx, ebx; unsigned __int64
0x180029b4c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029b51  mov     r14, rax
0x180029b54  mov     r8d, ebx; Size
0x180029b57  xor     edx, edx; Val
0x180029b59  mov     rcx, rax; void *
0x180029b5c  call    memset_0
0x180029b61  mov     [rsp+88h+arg_18], r14
0x180029b69  lea     rax, [rsp+88h+arg_8]
0x180029b71  mov     [rsp+88h+pcbStructInfo], rax; pcbStructInfo
0x180029b76  mov     [rsp+88h+pvStructInfo], r14; pvStructInfo
0x180029b7b  mov     [rsp+88h+pDecodePara], 0; pDecodePara
0x180029b84  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x180029b88  mov     r9d, [rsi+10h]; cbEncoded
0x180029b8c  mov     r8, [rsi+18h]; pbEncoded
0x180029b90  mov     edx, r15d; lpszStructType
0x180029b93  mov     ecx, [r12]; dwCertEncodingType
0x180029b97  call    cs:__imp_CryptDecodeObjectEx
0x180029b9d  mov     rcx, [rsp+88h]; this
0x180029ba5  test    eax, eax
0x180029ba7  jz      loc_180029D29
0x180029bad  mov     rsi, [r14+8]
0x180029bb1  mov     ebx, [r14]
0x180029bb4  test    ebx, ebx
0x180029bb6  jz      short loc_180029BE1
0x180029bb8  cmp     [rsi], ebp
0x180029bba  jnz     short loc_180029BD8
0x180029bbc  mov     r15, [rsi+8]
0x180029bc0  test    r15, r15
0x180029bc3  jz      short loc_180029BD8
0x180029bc5  mov     rdx, [r15]; Str2
0x180029bc8  lea     rcx, Str1; "1.3.6.1.4.1.311.20.2.3"
0x180029bcf  call    strcmp_0
0x180029bd4  test    eax, eax
0x180029bd6  jz      short loc_180029BFF
0x180029bd8  add     rsi, 18h
0x180029bdc  add     ebx, 0FFFFFFFFh
0x180029bdf  jnz     short loc_180029BB8
0x180029be1  mov     byte ptr [rdi+8], 0
0x180029be5  mov     rcx, r14; void *
0x180029be8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029bed  mov     rax, rdi
0x180029bf0  add     rsp, 50h
0x180029bf4  pop     r15
0x180029bf6  pop     r14
0x180029bf8  pop     r12
0x180029bfa  pop     rdi
0x180029bfb  pop     rsi
0x180029bfc  pop     rbp
0x180029bfd  pop     rbx
0x180029bfe  retn
0x180029bff  mov     [rsp+88h+arg_10], 0
0x180029c0a  lea     rax, [rsp+88h+arg_10]
0x180029c12  mov     [rsp+88h+pcbStructInfo], rax; pcbStructInfo
0x180029c17  mov     [rsp+88h+pvStructInfo], 0; pvStructInfo
0x180029c20  mov     [rsp+88h+pDecodePara], 0; pDecodePara
0x180029c29  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x180029c2d  mov     r9d, [r15+8]; cbEncoded
0x180029c31  mov     r8, [r15+10h]; pbEncoded
0x180029c35  mov     r15d, 18h
0x180029c3b  mov     edx, r15d; lpszStructType
0x180029c3e  mov     ecx, [r12]; dwCertEncodingType
0x180029c42  call    cs:__imp_CryptDecodeObjectEx
0x180029c48  mov     rcx, [rsp+88h]; this
0x180029c50  test    eax, eax
0x180029c52  jz      loc_180029D3B
0x180029c58  mov     ebx, [rsp+88h+arg_10]
0x180029c5f  mov     ecx, ebx; unsigned __int64
0x180029c61  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029c66  mov     rbp, rax
0x180029c69  mov     r8d, ebx; Size
0x180029c6c  xor     edx, edx; Val
0x180029c6e  mov     rcx, rax; void *
0x180029c71  call    memset_0
0x180029c76  mov     [rsp+88h+var_40], rbp
0x180029c7b  mov     r8, [rsi+8]
0x180029c7f  lea     rax, [rsp+88h+arg_10]
0x180029c87  mov     [rsp+88h+pcbStructInfo], rax; pcbStructInfo
0x180029c8c  mov     [rsp+88h+pvStructInfo], rbp; pvStructInfo
0x180029c91  mov     [rsp+88h+pDecodePara], 0; pDecodePara
0x180029c9a  mov     [rsp+88h+dwFlags], 1; dwFlags
0x180029ca2  mov     r9d, [r8+8]; cbEncoded
0x180029ca6  mov     r8, [r8+10h]; pbEncoded
0x180029caa  mov     edx, r15d; lpszStructType
0x180029cad  mov     ecx, [r12]; dwCertEncodingType
0x180029cb1  call    cs:__imp_CryptDecodeObjectEx
0x180029cb7  mov     rcx, [rsp+88h]; this
0x180029cbf  test    eax, eax
0x180029cc1  jz      short loc_180029D05
0x180029cc3  mov     esi, [rbp+8]
0x180029cc6  shr     esi, 1
0x180029cc8  jnz     short loc_180029CCF
0x180029cca  xor     r15d, r15d
0x180029ccd  jmp     short loc_180029CF1
0x180029ccf  mov     rbx, [rbp+10h]
0x180029cd3  mov     ecx, esi; this
0x180029cd5  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180029cda  mov     r15, rax
0x180029cdd  mov     edx, esi
0x180029cdf  add     rdx, rdx; DestinationSize
0x180029ce2  lea     rcx, [rax+1Ch]; Destination
0x180029ce6  mov     r9, rdx; SourceSize
0x180029ce9  mov     r8, rbx; Source
0x180029cec  call    memcpy_s
0x180029cf1  mov     [rdi], r15
0x180029cf4  mov     byte ptr [rdi+8], 1
0x180029cf8  mov     rcx, rbp; void *
0x180029cfb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029d00  jmp     loc_180029BE5
0x180029d05  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180029d0c  mov     edx, 328h; void *
0x180029d11  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029d17  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180029d1e  mov     edx, 2FCh; void *
0x180029d23  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029d29  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180029d30  mov     edx, 308h; void *
0x180029d35  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029d3b  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180029d42  mov     edx, 31Ch; void *
0x180029d47  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
