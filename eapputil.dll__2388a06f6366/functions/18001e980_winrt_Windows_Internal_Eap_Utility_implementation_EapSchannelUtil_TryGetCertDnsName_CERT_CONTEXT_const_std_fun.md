# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TryGetCertDnsName(_CERT_CONTEXT const *,std::function<bool (ushort const *)> const &)

- ea: `0x18001e980`
- end: `0x18001ebac`
- name: `?TryGetCertDnsName@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AV?$optional@Uhstring@winrt@@@std@@PEBU_CERT_CONTEXT@@AEBV?$function@$$A6A_NPEBG@Z@9@@Z`
- size: `556`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18001aee0`
- `0x18001f924`

## callees

- `0x1800025a0`
- `0x180002b78`
- `0x180003868`
- `0x180007eac`
- `0x180008274`
- `0x18001e980`
- `0x180023760`
- `0x180033010`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18001e9b8`
- `CRYPT32!CertFindExtension` at `0x18001e9b8`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001ea00`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001ea62`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001ea00`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001ea62`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001eb1b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001eb1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TryGetCertDnsName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  PCERT_EXTENSION Extension; // rsi
  const char *v7; // r9
  DWORD v8; // ebx
  _QWORD *pvStructInfo; // r14
  const char *v10; // rdx
  const char *v11; // r9
  __int64 v12; // rbx
  _WORD *v13; // rsi
  int v14; // ebp
  __int64 v15; // rcx
  _WORD *v16; // rbp
  __int64 v17; // rbx
  struct winrt::impl::shared_hstring_header *v18; // rsi
  __int64 v19; // rbx
  struct winrt::impl::shared_hstring_header *v20; // rbp
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD pcbStructInfo; // [rsp+98h] [rbp+10h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+20h] BYREF

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
        (void *)0x85D,
        (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        v7);
    v8 = pcbStructInfo;
    pvStructInfo = operator new[](pcbStructInfo);
    memset_0(pvStructInfo, 0, v8);
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
        (void *)0x869,
        (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        v11);
    v12 = pvStructInfo[1];
    v13 = 0;
    v14 = *(_DWORD *)pvStructInfo;
    if ( *(_DWORD *)pvStructInfo )
    {
      while ( 1 )
      {
        if ( *(_DWORD *)v12 == 3 )
        {
          v24 = *(_QWORD *)(v12 + 8);
          v15 = *(_QWORD *)(a3 + 56);
          if ( !v15 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 16LL))(v15, &v24) )
          {
            v16 = *(_WORD **)(v12 + 8);
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            if ( (_DWORD)v17 )
            {
              v18 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v17, v10);
              memcpy_s((char *)v18 + 28, 2LL * (unsigned int)v17, v16, 2LL * (unsigned int)v17);
            }
            else
            {
              v18 = 0;
            }
            *(_QWORD *)a1 = v18;
            goto LABEL_18;
          }
          if ( !v13 )
            v13 = *(_WORD **)(v12 + 8);
        }
        if ( !--v14 )
          break;
        v12 += 24;
      }
      if ( v13 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v13[v19] );
        if ( (_DWORD)v19 )
        {
          v20 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v19, v10);
          memcpy_s((char *)v20 + 28, 2LL * (unsigned int)v19, v13, 2LL * (unsigned int)v19);
        }
        else
        {
          v20 = 0;
        }
        *(_QWORD *)a1 = v20;
LABEL_18:
        *(_BYTE *)(a1 + 8) = 1;
        operator delete(pvStructInfo);
        return a1;
      }
    }
    operator delete(pvStructInfo);
  }
  *(_BYTE *)(a1 + 8) = 0;
  return a1;
}

```

## disassembly

```asm
0x18001e980  mov     [rsp+arg_0], rbx
0x18001e985  push    rbp
0x18001e986  push    rsi
0x18001e987  push    rdi
0x18001e988  push    r12
0x18001e98a  push    r13
0x18001e98c  push    r14
0x18001e98e  push    r15
0x18001e990  sub     rsp, 50h
0x18001e994  mov     r13, r8
0x18001e997  mov     r15, rdx
0x18001e99a  mov     rdi, rcx
0x18001e99d  xor     r12d, r12d
0x18001e9a0  mov     rdx, [rdx+18h]
0x18001e9a4  mov     r8, [rdx+0C8h]; rgExtensions
0x18001e9ab  mov     edx, [rdx+0C0h]; cExtensions
0x18001e9b1  lea     rcx, a252917; "2.5.29.17"
0x18001e9b8  call    cs:__imp_CertFindExtension
0x18001e9be  mov     rsi, rax
0x18001e9c1  test    rax, rax
0x18001e9c4  jz      loc_18001EB69
0x18001e9ca  mov     [rsp+88h+arg_8], r12d
0x18001e9d2  lea     rax, [rsp+88h+arg_8]
0x18001e9da  mov     [rsp+88h+pcbStructInfo], rax; pcbStructInfo
0x18001e9df  mov     [rsp+88h+pvStructInfo], r12; pvStructInfo
0x18001e9e4  mov     [rsp+88h+pDecodePara], r12; pDecodePara
0x18001e9e9  lea     ebp, [r12+1]
0x18001e9ee  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x18001e9f2  mov     r9d, [rsi+10h]; cbEncoded
0x18001e9f6  mov     r8, [rsi+18h]; pbEncoded
0x18001e9fa  lea     edx, [rbp+0Bh]; lpszStructType
0x18001e9fd  mov     ecx, [r15]; dwCertEncodingType
0x18001ea00  call    cs:__imp_CryptDecodeObjectEx
0x18001ea06  mov     rcx, [rsp+88h]; this
0x18001ea0e  test    eax, eax
0x18001ea10  jz      loc_18001EB9A
0x18001ea16  mov     ebx, [rsp+88h+arg_8]
0x18001ea1d  mov     ecx, ebx; unsigned __int64
0x18001ea1f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ea24  mov     r14, rax
0x18001ea27  mov     r8d, ebx; Size
0x18001ea2a  xor     edx, edx; Val
0x18001ea2c  mov     rcx, rax; void *
0x18001ea2f  call    memset_0
0x18001ea34  mov     [rsp+88h+var_40], r14
0x18001ea39  lea     rax, [rsp+88h+arg_8]
0x18001ea41  mov     [rsp+88h+pcbStructInfo], rax; pcbStructInfo
0x18001ea46  mov     [rsp+88h+pvStructInfo], r14; pvStructInfo
0x18001ea4b  mov     [rsp+88h+pDecodePara], r12; pDecodePara
0x18001ea50  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x18001ea54  mov     r9d, [rsi+10h]; cbEncoded
0x18001ea58  mov     r8, [rsi+18h]; pbEncoded
0x18001ea5c  lea     edx, [rbp+0Bh]; lpszStructType
0x18001ea5f  mov     ecx, [r15]; dwCertEncodingType
0x18001ea62  call    cs:__imp_CryptDecodeObjectEx
0x18001ea68  mov     rcx, [rsp+88h]; this
0x18001ea70  test    eax, eax
0x18001ea72  jz      loc_18001EB88
0x18001ea78  mov     rbx, [r14+8]
0x18001ea7c  mov     esi, r12d
0x18001ea7f  mov     ebp, [r14]
0x18001ea82  test    ebp, ebp
0x18001ea84  jz      loc_18001EB61
0x18001ea8a  cmp     dword ptr [rbx], 3
0x18001ea8d  jnz     short loc_18001EAC5
0x18001ea8f  mov     rax, [rbx+8]
0x18001ea93  mov     [rsp+88h+arg_18], rax
0x18001ea9b  mov     rcx, [r13+38h]
0x18001ea9f  test    rcx, rcx
0x18001eaa2  jz      short loc_18001EB1B
0x18001eaa4  mov     rax, [rcx]
0x18001eaa7  lea     rdx, [rsp+88h+arg_18]
0x18001eaaf  mov     rax, [rax+10h]
0x18001eab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eab8  test    al, al
0x18001eaba  jnz     short loc_18001EAD0
0x18001eabc  test    rsi, rsi
0x18001eabf  jnz     short loc_18001EAC5
0x18001eac1  mov     rsi, [rbx+8]
0x18001eac5  add     ebp, 0FFFFFFFFh
0x18001eac8  jz      short loc_18001EB22
0x18001eaca  add     rbx, 18h
0x18001eace  jmp     short loc_18001EA8A
0x18001ead0  mov     rbp, [rbx+8]
0x18001ead4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ead8  inc     rbx
0x18001eadb  cmp     [rbp+rbx*2+0], r12w
0x18001eae1  jnz     short loc_18001EAD8
0x18001eae3  test    ebx, ebx
0x18001eae5  jnz     short loc_18001EAEC
0x18001eae7  mov     rsi, r12
0x18001eaea  jmp     short loc_18001EB0A
0x18001eaec  mov     ecx, ebx; this
0x18001eaee  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001eaf3  mov     rsi, rax
0x18001eaf6  mov     edx, ebx
0x18001eaf8  add     rdx, rdx; DestinationSize
0x18001eafb  lea     rcx, [rax+1Ch]; Destination
0x18001eaff  mov     r9, rdx; SourceSize
0x18001eb02  mov     r8, rbp; Source
0x18001eb05  call    memcpy_s
0x18001eb0a  mov     [rdi], rsi
0x18001eb0d  mov     byte ptr [rdi+8], 1
0x18001eb11  mov     rcx, r14; void *
0x18001eb14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eb19  jmp     short loc_18001EB6D
0x18001eb1b  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001eb21  int     3; Trap to Debugger
0x18001eb22  test    rsi, rsi
0x18001eb25  jz      short loc_18001EB61
0x18001eb27  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001eb2b  inc     rbx
0x18001eb2e  cmp     [rsi+rbx*2], r12w
0x18001eb33  jnz     short loc_18001EB2B
0x18001eb35  test    ebx, ebx
0x18001eb37  jnz     short loc_18001EB3E
0x18001eb39  mov     rbp, r12
0x18001eb3c  jmp     short loc_18001EB5C
0x18001eb3e  mov     ecx, ebx; this
0x18001eb40  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001eb45  mov     rbp, rax
0x18001eb48  mov     edx, ebx
0x18001eb4a  add     rdx, rdx; DestinationSize
0x18001eb4d  lea     rcx, [rax+1Ch]; Destination
0x18001eb51  mov     r9, rdx; SourceSize
0x18001eb54  mov     r8, rsi; Source
0x18001eb57  call    memcpy_s
0x18001eb5c  mov     [rdi], rbp
0x18001eb5f  jmp     short loc_18001EB0D
0x18001eb61  mov     rcx, r14; void *
0x18001eb64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eb69  mov     [rdi+8], r12b
0x18001eb6d  mov     rax, rdi
0x18001eb70  mov     rbx, [rsp+88h+arg_0]
0x18001eb78  add     rsp, 50h
0x18001eb7c  pop     r15
0x18001eb7e  pop     r14
0x18001eb80  pop     r13
0x18001eb82  pop     r12
0x18001eb84  pop     rdi
0x18001eb85  pop     rsi
0x18001eb86  pop     rbp
0x18001eb87  retn
0x18001eb88  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001eb8f  mov     edx, 869h; void *
0x18001eb94  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001eb9a  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001eba1  mov     edx, 85Dh; void *
0x18001eba6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
