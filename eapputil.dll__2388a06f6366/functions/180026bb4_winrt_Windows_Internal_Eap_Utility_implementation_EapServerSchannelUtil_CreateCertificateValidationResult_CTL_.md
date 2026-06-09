# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::CreateCertificateValidationResult(_CTL_USAGE *,_CERT_CHAIN_CONTEXT const *)

- ea: `0x180026bb4`
- end: `0x180026f83`
- name: `?CreateCertificateValidationResult@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AUEapTlsClientCertificateValidationResult@34567@PEAU_CTL_USAGE@@PEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `975`
- prototype: `void *__fastcall(void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18002a008`

## callees

- `0x1800021d0`
- `0x180002cb7`
- `0x180002ce7`
- `0x180007f3c`
- `0x1800083ec`
- `0x1800101c4`
- `0x180010e04`
- `0x180012178`
- `0x18001371c`
- `0x180023760`
- `0x180025a00`
- `0x180025ba8`
- `0x180025c1c`
- `0x180025fc8`
- `0x180026bb4`
- `0x18002de70`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026f28`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026f28`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026ddb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026e0c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026ddb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026e0c`

## pseudocode

```c
void *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::CreateCertificateValidationResult(
        void *a1,
        __int64 a2,
        __int64 a3)
{
  char v6; // al
  unsigned int v7; // esi
  __int64 i; // rbx
  volatile signed __int32 *v9; // rdi
  int v10; // eax
  int v11; // eax
  HANDLE ProcessHeap; // rax
  __int64 v13; // r14
  unsigned int j; // edi
  volatile signed __int32 *v15; // rsi
  int v16; // eax
  int v17; // eax
  HANDLE v18; // rax
  __int64 *View; // r14
  __int64 v20; // rsi
  __int64 *v21; // rdi
  __int64 v22; // rcx
  const CERT_CONTEXT *v23; // rdi
  const char *v24; // r9
  const char *v25; // r9
  __int64 *IBuffer; // r14
  __int64 *v27; // rdi
  __int64 v28; // rcx
  __int64 *v29; // r14
  __int64 *v30; // rdi
  __int64 v31; // rcx
  LPVOID lpMem[2]; // [rsp+20h] [rbp-79h] BYREF
  _OWORD v34[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v35; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v36[2]; // [rsp+58h] [rbp-41h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-31h] BYREF
  _OWORD pvData[2]; // [rsp+6Ch] [rbp-2Dh] BYREF
  DWORD v39; // [rsp+90h] [rbp-9h] BYREF
  _OWORD v40[2]; // [rsp+94h] [rbp-5h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  lpMem[0] = a1;
  if ( !a2 || (v6 = 0, !a3) )
    v6 = 1;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)0x80070057LL,
      (int)lpMem[0]);
  winrt::make_self<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult,>(v36);
  memset(v34, 0, 24);
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v35, v34);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(v34);
  v7 = 0;
  for ( i = v35; v7 < *(_DWORD *)a2; ++v7 )
  {
    winrt::to_hstring<char *,0>(lpMem, *(_QWORD *)(a2 + 8) + 8LL * v7);
    v9 = (volatile signed __int32 *)lpMem[0];
    LODWORD(v34[0]) = 0;
    *(_OWORD *)((char *)v34 + 8) = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)i + 104LL))(i, lpMem[0]);
    if ( v10 < 0 )
      winrt::throw_hresult((unsigned int)v10, v34);
    if ( v9 )
    {
      v11 = _InterlockedDecrement(v9 + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
LABEL_50:
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v9);
      }
      lpMem[0] = 0;
    }
  }
  v13 = *(_QWORD *)(**(_QWORD **)(**(_QWORD **)(a3 + 16) + 16LL) + 32LL);
  if ( v13 )
  {
    for ( j = 0; j < *(_DWORD *)v13; ++j )
    {
      winrt::to_hstring<char *,0>(lpMem, *(_QWORD *)(v13 + 8) + 8LL * j);
      v15 = (volatile signed __int32 *)lpMem[0];
      LODWORD(v34[0]) = 0;
      *(_OWORD *)((char *)v34 + 8) = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)i + 104LL))(i, lpMem[0]);
      if ( v16 < 0 )
        winrt::throw_hresult((unsigned int)v16, v34);
      if ( v15 )
      {
        v17 = _InterlockedDecrement(v15 + 6);
        if ( v17 )
        {
          if ( v17 < 0 )
            goto LABEL_50;
        }
        else
        {
          v18 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v18, 0, (LPVOID)v15);
        }
        lpMem[0] = 0;
      }
    }
  }
  View = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
                      &v35,
                      lpMem);
  v20 = v36[0];
  v21 = (__int64 *)(v36[0] + 24LL);
  if ( (__int64 *)(v36[0] + 24LL) != View )
  {
    if ( *v21 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v36[0] + 24LL);
    v22 = *View;
    *v21 = *View;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  }
  if ( lpMem[0] )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(lpMem);
  v23 = *(const CERT_CONTEXT **)(**(_QWORD **)(**(_QWORD **)(a3 + 16) + 16LL) + 8LL);
  pcbData = 32;
  memset(pvData, 0, sizeof(pvData));
  if ( !CertGetCertificateContextProperty(v23, 3u, pvData, &pcbData) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x274,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      v24);
  v39 = 32;
  memset(v40, 0, sizeof(v40));
  if ( !CertGetCertificateContextProperty(v23, 0x6Bu, v40, &v39) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      v25);
  *(_QWORD *)&v34[0] = pcbData;
  *((_QWORD *)&v34[0] + 1) = pvData;
  IBuffer = winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(lpMem, (unsigned int *)v34);
  v27 = (__int64 *)(v20 + 32);
  if ( (__int64 *)(v20 + 32) != IBuffer )
  {
    if ( *v27 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v20 + 32);
    v28 = *IBuffer;
    *v27 = *IBuffer;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  }
  if ( lpMem[0] )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(lpMem);
  *(_QWORD *)&v34[0] = v39;
  *((_QWORD *)&v34[0] + 1) = v40;
  v29 = winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(lpMem, (unsigned int *)v34);
  v30 = (__int64 *)(v20 + 40);
  if ( (__int64 *)(v20 + 40) != v29 )
  {
    if ( *v30 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v20 + 40);
    v31 = *v29;
    *v30 = *v29;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  }
  if ( lpMem[0] )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(lpMem);
  winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult>::as<winrt::Windows::Internal::Eap::Utility::EapTlsClientCertificateValidationResult>(
    v36,
    a1);
  if ( i )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v35);
  if ( v20 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(v36);
  return a1;
}

```

## disassembly

```asm
0x180026bb4  mov     [rsp-8+arg_18], rbx
0x180026bb9  push    rbp
0x180026bba  push    rsi
0x180026bbb  push    rdi
0x180026bbc  push    r12
0x180026bbe  push    r13
0x180026bc0  push    r14
0x180026bc2  push    r15
0x180026bc4  lea     rbp, [rsp-27h]
0x180026bc9  sub     rsp, 0C0h
0x180026bd0  mov     rax, cs:__security_cookie
0x180026bd7  xor     rax, rsp
0x180026bda  mov     [rbp+57h+var_38], rax
0x180026bde  mov     r13, r8
0x180026be1  mov     r14, rdx
0x180026be4  mov     r15, rcx
0x180026be7  mov     [rbp+57h+lpMem], rcx
0x180026beb  xor     r12d, r12d
0x180026bee  test    rdx, rdx
0x180026bf1  jz      short loc_180026BFB
0x180026bf3  test    r8, r8
0x180026bf6  mov     al, r12b
0x180026bf9  jnz     short loc_180026BFD
0x180026bfb  mov     al, 1
0x180026bfd  mov     rcx, [rbp+5Fh]; this
0x180026c01  test    al, al
0x180026c03  jnz     loc_180026F41
0x180026c09  lea     rcx, [rbp+57h+var_98]
0x180026c0d  call    ??$make_self@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@$$V@winrt@@YA?AU?$com_ptr@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@0@XZ; winrt::make_self<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult,>(void)
0x180026c12  nop
0x180026c13  xorps   xmm0, xmm0
0x180026c16  movdqu  [rbp+57h+var_C0], xmm0
0x180026c1b  mov     [rbp+57h+var_B0], r12
0x180026c1f  lea     rdx, [rbp+57h+var_C0]
0x180026c23  lea     rcx, [rbp+57h+var_A0]
0x180026c27  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x180026c2c  nop
0x180026c2d  lea     rcx, [rbp+57h+var_C0]
0x180026c31  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x180026c36  mov     esi, r12d
0x180026c39  mov     rbx, [rbp+57h+var_A0]
0x180026c3d  cmp     [r14], r12d
0x180026c40  jbe     short loc_180026CBA
0x180026c42  mov     ecx, esi
0x180026c44  mov     rax, [r14+8]
0x180026c48  lea     rdx, [rax+rcx*8]
0x180026c4c  lea     rcx, [rbp+57h+lpMem]
0x180026c50  call    ??$to_hstring@PEAD$0A@@winrt@@YA?AUhstring@0@AEBQEAD@Z; winrt::to_hstring<char *,0>(char * const &)
0x180026c55  nop
0x180026c56  mov     rdi, [rbp+57h+lpMem]
0x180026c5a  mov     dword ptr [rbp+57h+var_C0], r12d
0x180026c5e  xorps   xmm0, xmm0
0x180026c61  movdqu  [rbp+57h+var_C0+8], xmm0
0x180026c66  mov     rax, [rbx]
0x180026c69  mov     rdx, rdi
0x180026c6c  mov     rcx, rbx
0x180026c6f  mov     rax, [rax+68h]
0x180026c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c78  test    eax, eax
0x180026c7a  js      loc_180026F59
0x180026c80  test    rdi, rdi
0x180026c83  jz      short loc_180026CB3
0x180026c85  or      eax, 0FFFFFFFFh
0x180026c88  lock xadd [rdi+18h], eax
0x180026c8d  sub     eax, 1
0x180026c90  jnz     short loc_180026CA7
0x180026c92  nop
0x180026c93  call    WINRT_IMPL_GetProcessHeap
0x180026c98  mov     rcx, rax; hHeap
0x180026c9b  mov     r8, rdi; lpMem
0x180026c9e  xor     edx, edx; dwFlags
0x180026ca0  call    WINRT_IMPL_HeapFree
0x180026ca5  jmp     short loc_180026CAF
0x180026ca7  test    eax, eax
0x180026ca9  js      loc_180026F28
0x180026caf  mov     [rbp+57h+lpMem], r12
0x180026cb3  inc     esi
0x180026cb5  cmp     esi, [r14]
0x180026cb8  jb      short loc_180026C42
0x180026cba  mov     rax, [r13+10h]
0x180026cbe  mov     rcx, [rax]
0x180026cc1  mov     rax, [rcx+10h]
0x180026cc5  mov     rcx, [rax]
0x180026cc8  mov     r14, [rcx+20h]
0x180026ccc  test    r14, r14
0x180026ccf  jz      loc_180026D55
0x180026cd5  mov     edi, r12d
0x180026cd8  cmp     [r14], r12d
0x180026cdb  jbe     short loc_180026D55
0x180026cdd  mov     ecx, edi
0x180026cdf  mov     rax, [r14+8]
0x180026ce3  lea     rdx, [rax+rcx*8]
0x180026ce7  lea     rcx, [rbp+57h+lpMem]
0x180026ceb  call    ??$to_hstring@PEAD$0A@@winrt@@YA?AUhstring@0@AEBQEAD@Z; winrt::to_hstring<char *,0>(char * const &)
0x180026cf0  nop
0x180026cf1  mov     rsi, [rbp+57h+lpMem]
0x180026cf5  mov     dword ptr [rbp+57h+var_C0], r12d
0x180026cf9  xorps   xmm0, xmm0
0x180026cfc  movdqu  [rbp+57h+var_C0+8], xmm0
0x180026d01  mov     rax, [rbx]
0x180026d04  mov     rdx, rsi
0x180026d07  mov     rcx, rbx
0x180026d0a  mov     rax, [rax+68h]
0x180026d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d13  test    eax, eax
0x180026d15  js      loc_180026F77
0x180026d1b  test    rsi, rsi
0x180026d1e  jz      short loc_180026D4E
0x180026d20  or      eax, 0FFFFFFFFh
0x180026d23  lock xadd [rsi+18h], eax
0x180026d28  sub     eax, 1
0x180026d2b  jnz     short loc_180026D42
0x180026d2d  nop
0x180026d2e  call    WINRT_IMPL_GetProcessHeap
0x180026d33  mov     rcx, rax; hHeap
0x180026d36  mov     r8, rsi; lpMem
0x180026d39  xor     edx, edx; dwFlags
0x180026d3b  call    WINRT_IMPL_HeapFree
0x180026d40  jmp     short loc_180026D4A
0x180026d42  test    eax, eax
0x180026d44  js      loc_180026F28
0x180026d4a  mov     [rbp+57h+lpMem], r12
0x180026d4e  inc     edi
0x180026d50  cmp     edi, [r14]
0x180026d53  jb      short loc_180026CDD
0x180026d55  lea     rdx, [rbp+57h+lpMem]
0x180026d59  lea     rcx, [rbp+57h+var_A0]
0x180026d5d  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(void)
0x180026d62  mov     r14, rax
0x180026d65  mov     rsi, [rbp+57h+var_98]
0x180026d69  lea     rdi, [rsi+18h]
0x180026d6d  cmp     rdi, rax
0x180026d70  jz      short loc_180026D96
0x180026d72  cmp     [rdi], r12
0x180026d75  jz      short loc_180026D7F
0x180026d77  mov     rcx, rdi
0x180026d7a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026d7f  mov     rcx, [r14]
0x180026d82  mov     [rdi], rcx
0x180026d85  test    rcx, rcx
0x180026d88  jz      short loc_180026D96
0x180026d8a  mov     rax, [rcx]
0x180026d8d  mov     rax, [rax+8]
0x180026d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d96  cmp     [rbp+57h+lpMem], r12
0x180026d9a  jz      short loc_180026DA5
0x180026d9c  lea     rcx, [rbp+57h+lpMem]
0x180026da0  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026da5  mov     rax, [r13+10h]
0x180026da9  mov     rcx, [rax]
0x180026dac  mov     rax, [rcx+10h]
0x180026db0  mov     rcx, [rax]
0x180026db3  mov     rdi, [rcx+8]
0x180026db7  mov     r14d, 20h ; ' '
0x180026dbd  mov     [rbp+57h+pcbData], r14d
0x180026dc1  xorps   xmm0, xmm0
0x180026dc4  movups  [rbp+57h+pvData], xmm0
0x180026dc8  movups  [rbp+57h+var_74], xmm0
0x180026dcc  lea     r9, [rbp+57h+pcbData]; pcbData
0x180026dd0  lea     r8, [rbp+57h+pvData]; pvData
0x180026dd4  lea     edx, [r14-1Dh]; dwPropId
0x180026dd8  mov     rcx, rdi; pCertContext
0x180026ddb  call    cs:__imp_CertGetCertificateContextProperty
0x180026de1  mov     rcx, [rbp+5Fh]; this
0x180026de5  test    eax, eax
0x180026de7  jz      loc_180026F65
0x180026ded  mov     [rbp+57h+var_60], r14d
0x180026df1  xorps   xmm0, xmm0
0x180026df4  movups  [rbp+57h+var_5C], xmm0
0x180026df8  movups  [rbp+57h+var_4C], xmm0
0x180026dfc  lea     r9, [rbp+57h+var_60]; pcbData
0x180026e00  lea     r8, [rbp+57h+var_5C]; pvData
0x180026e04  mov     edx, 6Bh ; 'k'; dwPropId
0x180026e09  mov     rcx, rdi; pCertContext
0x180026e0c  call    cs:__imp_CertGetCertificateContextProperty
0x180026e12  mov     rcx, [rbp+5Fh]; this
0x180026e16  test    eax, eax
0x180026e18  jz      loc_180026F2F
0x180026e1e  mov     eax, [rbp+57h+pcbData]
0x180026e21  mov     qword ptr [rbp+57h+var_C0], rax
0x180026e25  lea     rax, [rbp+57h+pvData]
0x180026e29  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180026e2d  lea     rdx, [rbp+57h+var_C0]
0x180026e31  lea     rcx, [rbp+57h+lpMem]
0x180026e35  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x180026e3a  mov     r14, rax
0x180026e3d  lea     rdi, [rsi+20h]
0x180026e41  cmp     rdi, rax
0x180026e44  jz      short loc_180026E6A
0x180026e46  cmp     [rdi], r12
0x180026e49  jz      short loc_180026E53
0x180026e4b  mov     rcx, rdi
0x180026e4e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026e53  mov     rcx, [r14]
0x180026e56  mov     [rdi], rcx
0x180026e59  test    rcx, rcx
0x180026e5c  jz      short loc_180026E6A
0x180026e5e  mov     rax, [rcx]
0x180026e61  mov     rax, [rax+8]
0x180026e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e6a  cmp     [rbp+57h+lpMem], r12
0x180026e6e  jz      short loc_180026E79
0x180026e70  lea     rcx, [rbp+57h+lpMem]
0x180026e74  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026e79  mov     eax, [rbp+57h+var_60]
0x180026e7c  mov     qword ptr [rbp+57h+var_C0], rax
0x180026e80  lea     rax, [rbp+57h+var_5C]
0x180026e84  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180026e88  lea     rdx, [rbp+57h+var_C0]
0x180026e8c  lea     rcx, [rbp+57h+lpMem]
0x180026e90  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x180026e95  mov     r14, rax
0x180026e98  lea     rdi, [rsi+28h]
0x180026e9c  cmp     rdi, rax
0x180026e9f  jz      short loc_180026EC5
0x180026ea1  cmp     [rdi], r12
0x180026ea4  jz      short loc_180026EAE
0x180026ea6  mov     rcx, rdi
0x180026ea9  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026eae  mov     rcx, [r14]
0x180026eb1  mov     [rdi], rcx
0x180026eb4  test    rcx, rcx
0x180026eb7  jz      short loc_180026EC5
0x180026eb9  mov     rax, [rcx]
0x180026ebc  mov     rax, [rax+8]
0x180026ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ec5  cmp     [rbp+57h+lpMem], r12
0x180026ec9  jz      short loc_180026ED4
0x180026ecb  lea     rcx, [rbp+57h+lpMem]
0x180026ecf  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026ed4  mov     rdx, r15
0x180026ed7  lea     rcx, [rbp+57h+var_98]
0x180026edb  call    ??$as@UEapTlsClientCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@?$com_ptr@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@QEBA?A_PXZ
0x180026ee0  nop
0x180026ee1  test    rbx, rbx
0x180026ee4  jz      short loc_180026EF0
0x180026ee6  lea     rcx, [rbp+57h+var_A0]
0x180026eea  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180026eef  nop
0x180026ef0  test    rsi, rsi
0x180026ef3  jz      short loc_180026EFE
0x180026ef5  lea     rcx, [rbp+57h+var_98]
0x180026ef9  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180026efe  mov     rax, r15
0x180026f01  mov     rcx, [rbp+57h+var_38]
0x180026f05  xor     rcx, rsp; StackCookie
0x180026f08  call    __security_check_cookie
0x180026f0d  mov     rbx, [rsp+0F0h+arg_18]
0x180026f15  add     rsp, 0C0h
0x180026f1c  pop     r15
0x180026f1e  pop     r14
0x180026f20  pop     r13
0x180026f22  pop     r12
0x180026f24  pop     rdi
0x180026f25  pop     rsi
0x180026f26  pop     rbp
0x180026f27  retn
0x180026f28  call    cs:__imp_abort
0x180026f2f  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026f36  mov     edx, 278h; void *
0x180026f3b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180026f41  mov     r9d, 80070057h; char *
0x180026f47  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026f4e  mov     edx, 25Ah; void *
0x180026f53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026f59  lea     rdx, [rbp+57h+var_C0]
0x180026f5d  mov     ecx, eax
0x180026f5f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180026f65  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180026f6c  mov     edx, 274h; void *
0x180026f71  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180026f77  lea     rdx, [rbp+57h+var_C0]
0x180026f7b  mov     ecx, eax
0x180026f7d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
