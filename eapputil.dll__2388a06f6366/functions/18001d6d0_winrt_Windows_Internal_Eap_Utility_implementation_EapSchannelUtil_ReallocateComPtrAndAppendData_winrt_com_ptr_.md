# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReallocateComPtrAndAppendData(winrt::com_ptr<Windows::Storage::Streams::IBuffer> &,gsl::span<uchar const,-1>)

- ea: `0x18001d6d0`
- end: `0x18001dac4`
- name: `?ReallocateComPtrAndAppendData@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CAXAEAU?$com_ptr@UIBuffer@Streams@Storage@Windows@@@7@V?$span@$$CBE$0?0@gsl@@@Z`
- size: `1012`
- prototype: `char *__fastcall(char *, const void *const *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018e1c`
- `0x180019dc4`
- `0x18001c220`

## callees

- `0x180003844`
- `0x180007eac`
- `0x1800101c4`
- `0x180010e04`
- `0x180013a04`
- `0x18001d6d0`
- `0x180024f14`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReallocateComPtrAndAppendData(
        char *a1,
        const void *const *a2)
{
  void *v4; // rdi
  rsize_t v5; // r14
  __int64 (__fastcall ***v6)(_QWORD, __int64 *, void **); // rcx
  int v7; // eax
  unsigned int v8; // r15d
  void *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  void *v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, __int64 *, void **); // rcx
  void *v17; // rbx
  void *v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  char *result; // rax
  void *v23; // r14
  void *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, __int64 *, rsize_t *); // rcx
  rsize_t v29; // rcx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  void **v33; // [rsp+20h] [rbp-48h]
  void *Source; // [rsp+30h] [rbp-38h] BYREF
  void *v35; // [rsp+38h] [rbp-30h] BYREF
  char v36; // [rsp+40h] [rbp-28h] BYREF
  int v37; // [rsp+48h] [rbp-20h] BYREF
  __int128 v38; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  rsize_t SourceSize; // [rsp+B0h] [rbp+48h] BYREF
  void *v41; // [rsp+B8h] [rbp+50h] BYREF
  void *Destination; // [rsp+C0h] [rbp+58h] BYREF
  void *v43; // [rsp+C8h] [rbp+60h] BYREF

  v4 = 0;
  v5 = *(unsigned int *)a2;
  v6 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, void **))a1;
  if ( v6 )
  {
    v41 = 0;
    LODWORD(SourceSize) = 0;
    v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, void **), rsize_t *))(*v6)[7])(
           v6,
           &SourceSize);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x527,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v7,
        (int)v33);
    v8 = v5 + SourceSize;
    if ( v41 )
      winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v41);
    v41 = 0;
    v9 = operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
    if ( v9 )
    {
      v33 = &v41;
      LOBYTE(v11) = SourceSize;
      v12 = Windows::Storage::Streams::MakeCBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup>(v8, v10, v9, v11);
    }
    else
    {
      v12 = -2147024882;
    }
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x529,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v12,
        (int)v33);
    Destination = 0;
    v13 = v41;
    if ( v41 )
    {
      v43 = 0;
      v37 = 0;
      v38 = 0;
      v14 = (**(__int64 (__fastcall ***)(void *, __int64 *, void **))v41)(
              v41,
              winrt::impl::guid_v<Windows::Storage::Streams::IBufferByteAccess>,
              &v43);
      if ( v14 < 0 )
        winrt::throw_hresult((unsigned int)v14, &v37);
      v4 = v43;
      v13 = v43;
    }
    v35 = v4;
    v15 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v13 + 24LL))(v13, &Destination);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52D,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v15,
        (int)v33);
    Source = 0;
    v16 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, void **))a1;
    v43 = 0;
    if ( v16 )
    {
      v37 = 0;
      v38 = 0;
      v19 = (**v16)(v16, winrt::impl::guid_v<Windows::Storage::Streams::IBufferByteAccess>, &v43);
      if ( v19 < 0 )
        winrt::throw_hresult((unsigned int)v19, &v37);
      v17 = v43;
      v18 = v43;
    }
    else
    {
      v17 = 0;
      v18 = 0;
    }
    v20 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v18 + 24LL))(v18, &Source);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x531,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v20,
        (int)v33);
    memcpy_s(Destination, v8, Source, (unsigned int)SourceSize);
    memcpy_s((char *)Destination + (unsigned int)SourceSize, v5, a2[1], v5);
    v21 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v41 + 64LL))(v41, v8);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x536,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v21,
        (int)v33);
    result = &v36;
    if ( a1 != &v36 )
    {
      if ( *(_QWORD *)a1 )
        result = (char *)winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(a1);
      *(_QWORD *)a1 = 0;
    }
    v23 = v41;
    if ( *(void **)a1 != v41 )
    {
      if ( *(_QWORD *)a1 )
        result = (char *)winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(a1);
      *(_QWORD *)a1 = v23;
      if ( v23 )
        result = (char *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 8LL))(v23);
    }
    if ( v17 )
      result = (char *)winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v43);
    if ( v4 )
      result = (char *)winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v35);
    if ( v41 )
      return (char *)winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v41);
  }
  else
  {
    *(_QWORD *)a1 = 0;
    v24 = operator new[](v5, (const struct std::nothrow_t *)std::nothrow);
    if ( v24 )
    {
      LODWORD(v33) = (_DWORD)a1;
      LOBYTE(v26) = SourceSize;
      v27 = Windows::Storage::Streams::MakeCBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup>(
              (unsigned int)v5,
              v25,
              v24,
              v26);
    }
    else
    {
      v27 = -2147024882;
    }
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53D,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v27,
        (int)v33);
    v41 = 0;
    v28 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, rsize_t *))a1;
    SourceSize = 0;
    if ( v28 )
    {
      v37 = 0;
      v38 = 0;
      v30 = (**v28)(v28, winrt::impl::guid_v<Windows::Storage::Streams::IBufferByteAccess>, &SourceSize);
      if ( v30 < 0 )
        winrt::throw_hresult((unsigned int)v30, &v37);
      v29 = SourceSize;
    }
    else
    {
      v29 = 0;
    }
    v31 = (*(__int64 (__fastcall **)(rsize_t, void **))(*(_QWORD *)v29 + 24LL))(v29, &v41);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x540,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v31,
        (int)v33);
    memcpy_s(v41, v5, a2[1], v5);
    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)a1 + 64LL))(*(_QWORD *)a1, (unsigned int)v5);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x542,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v32,
        (int)v33);
    return (char *)winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&SourceSize);
  }
  return result;
}

```

## disassembly

```asm
0x18001d6d0  push    rbp
0x18001d6d2  push    rbx
0x18001d6d3  push    rsi
0x18001d6d4  push    rdi
0x18001d6d5  push    r12
0x18001d6d7  push    r13
0x18001d6d9  push    r14
0x18001d6db  push    r15
0x18001d6dd  mov     rbp, rsp
0x18001d6e0  sub     rsp, 68h
0x18001d6e4  mov     r12, rdx
0x18001d6e7  mov     rsi, rcx
0x18001d6ea  xor     edi, edi
0x18001d6ec  mov     r14d, [rdx]
0x18001d6ef  mov     rcx, [rcx]
0x18001d6f2  test    rcx, rcx
0x18001d6f5  jz      loc_18001D90D
0x18001d6fb  mov     [rbp+arg_8], rdi
0x18001d6ff  mov     dword ptr [rbp+SourceSize], edi
0x18001d702  mov     rax, [rcx]
0x18001d705  lea     rdx, [rbp+SourceSize]
0x18001d709  mov     rax, [rax+38h]
0x18001d70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d712  mov     rcx, [rbp+40h]; this
0x18001d716  test    eax, eax
0x18001d718  js      loc_18001DA0D
0x18001d71e  mov     r15d, dword ptr [rbp+SourceSize]
0x18001d722  add     r15d, r14d
0x18001d725  cmp     [rbp+arg_8], rdi
0x18001d729  jz      short loc_18001D734
0x18001d72b  lea     rcx, [rbp+arg_8]
0x18001d72f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d734  mov     [rbp+arg_8], rdi
0x18001d738  mov     r13d, r15d
0x18001d73b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d742  mov     ecx, r15d; unsigned __int64
0x18001d745  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d74a  test    rax, rax
0x18001d74d  jnz     short loc_18001D756
0x18001d74f  mov     eax, 8007000Eh
0x18001d754  jmp     short loc_18001D76E
0x18001d756  lea     rcx, [rbp+arg_8]
0x18001d75a  mov     qword ptr [rsp+68h+var_48], rcx; int
0x18001d75f  mov     r9b, byte ptr [rbp+SourceSize]
0x18001d763  mov     r8, rax
0x18001d766  mov     ecx, r15d
0x18001d769  call    ??$MakeCBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@@Streams@Storage@Windows@@YAJIIPEAEVCBuffer_StandardCleanup@012@PEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup>(uint,uint,uchar *,Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::IBuffer * *)
0x18001d76e  mov     rcx, [rbp+40h]; this
0x18001d772  test    eax, eax
0x18001d774  js      loc_18001DA22
0x18001d77a  mov     [rbp+Destination], rdi
0x18001d77e  mov     rcx, [rbp+arg_8]
0x18001d782  test    rcx, rcx
0x18001d785  jz      short loc_18001D7BB
0x18001d787  mov     [rbp+arg_18], rdi
0x18001d78b  mov     [rbp+var_20], edi
0x18001d78e  xorps   xmm0, xmm0
0x18001d791  movdqu  [rbp+var_18], xmm0
0x18001d796  mov     rax, [rcx]
0x18001d799  lea     r8, [rbp+arg_18]
0x18001d79d  lea     rdx, ??$guid_v@UIBufferByteAccess@Streams@Storage@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Storage::Streams::IBufferByteAccess>
0x18001d7a4  mov     rax, [rax]
0x18001d7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ac  test    eax, eax
0x18001d7ae  js      loc_18001DA37
0x18001d7b4  mov     rdi, [rbp+arg_18]
0x18001d7b8  mov     rcx, rdi
0x18001d7bb  mov     [rbp+var_30], rdi
0x18001d7bf  mov     rax, [rcx]
0x18001d7c2  lea     rdx, [rbp+Destination]
0x18001d7c6  mov     rax, [rax+18h]
0x18001d7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7cf  mov     rcx, [rbp+40h]; this
0x18001d7d3  xor     edx, edx
0x18001d7d5  test    eax, eax
0x18001d7d7  js      loc_18001DA43
0x18001d7dd  mov     [rbp+Source], rdx
0x18001d7e1  mov     rcx, [rsi]
0x18001d7e4  mov     [rbp+arg_18], rdx
0x18001d7e8  test    rcx, rcx
0x18001d7eb  jnz     short loc_18001D7F3
0x18001d7ed  mov     ebx, edx
0x18001d7ef  mov     ecx, edx
0x18001d7f1  jmp     short loc_18001D827
0x18001d7f3  mov     [rbp+var_20], edx
0x18001d7f6  xorps   xmm0, xmm0
0x18001d7f9  movdqu  [rbp+var_18], xmm0
0x18001d7fe  mov     rax, [rcx]
0x18001d801  lea     r8, [rbp+arg_18]
0x18001d805  lea     rdx, ??$guid_v@UIBufferByteAccess@Streams@Storage@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Storage::Streams::IBufferByteAccess>
0x18001d80c  mov     rax, [rax]
0x18001d80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d814  test    eax, eax
0x18001d816  js      loc_18001DA58
0x18001d81c  mov     rbx, [rbp+arg_18]
0x18001d820  mov     [rbp+arg_18], rbx
0x18001d824  mov     rcx, rbx
0x18001d827  mov     rax, [rcx]
0x18001d82a  lea     rdx, [rbp+Source]
0x18001d82e  mov     rax, [rax+18h]
0x18001d832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d837  mov     rcx, [rbp+40h]; this
0x18001d83b  test    eax, eax
0x18001d83d  js      loc_18001DA64
0x18001d843  mov     r9d, dword ptr [rbp+SourceSize]; SourceSize
0x18001d847  mov     r8, [rbp+Source]; Source
0x18001d84b  mov     rdx, r13; DestinationSize
0x18001d84e  mov     rcx, [rbp+Destination]; Destination
0x18001d852  call    memcpy_s
0x18001d857  mov     rdx, r14; DestinationSize
0x18001d85a  mov     ecx, dword ptr [rbp+SourceSize]
0x18001d85d  add     rcx, [rbp+Destination]; Destination
0x18001d861  mov     r9, r14; SourceSize
0x18001d864  mov     r8, [r12+8]; Source
0x18001d869  call    memcpy_s
0x18001d86e  mov     rcx, [rbp+arg_8]
0x18001d872  mov     rax, [rcx]
0x18001d875  mov     edx, r15d
0x18001d878  mov     rax, [rax+40h]
0x18001d87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d881  mov     rcx, [rbp+40h]; this
0x18001d885  xor     r15d, r15d
0x18001d888  test    eax, eax
0x18001d88a  js      loc_18001DA79
0x18001d890  lea     rax, [rbp+var_28]
0x18001d894  cmp     rsi, rax
0x18001d897  jz      short loc_18001D8A9
0x18001d899  cmp     [rsi], r15
0x18001d89c  jz      short loc_18001D8A6
0x18001d89e  mov     rcx, rsi
0x18001d8a1  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d8a6  mov     [rsi], r15
0x18001d8a9  mov     r14, [rbp+arg_8]
0x18001d8ad  cmp     [rsi], r14
0x18001d8b0  jz      short loc_18001D8D7
0x18001d8b2  cmp     [rsi], r15
0x18001d8b5  jz      short loc_18001D8BF
0x18001d8b7  mov     rcx, rsi
0x18001d8ba  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d8bf  mov     [rsi], r14
0x18001d8c2  test    r14, r14
0x18001d8c5  jz      short loc_18001D8D7
0x18001d8c7  mov     rax, [r14]
0x18001d8ca  mov     rcx, r14
0x18001d8cd  mov     rax, [rax+8]
0x18001d8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d6  nop
0x18001d8d7  test    rbx, rbx
0x18001d8da  jz      short loc_18001D8E6
0x18001d8dc  lea     rcx, [rbp+arg_18]
0x18001d8e0  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d8e5  nop
0x18001d8e6  test    rdi, rdi
0x18001d8e9  jz      short loc_18001D8F5
0x18001d8eb  lea     rcx, [rbp+var_30]
0x18001d8ef  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d8f4  nop
0x18001d8f5  cmp     [rbp+arg_8], r15
0x18001d8f9  jz      loc_18001D9E7
0x18001d8ff  lea     rcx, [rbp+arg_8]
0x18001d903  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d908  jmp     loc_18001D9E7
0x18001d90d  mov     [rsi], rdi
0x18001d910  mov     rbx, r14
0x18001d913  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d91a  mov     rcx, r14; unsigned __int64
0x18001d91d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d922  test    rax, rax
0x18001d925  jnz     short loc_18001D92E
0x18001d927  mov     eax, 8007000Eh
0x18001d92c  jmp     short loc_18001D942
0x18001d92e  mov     qword ptr [rsp+68h+var_48], rsi; int
0x18001d933  mov     r9b, byte ptr [rbp+SourceSize]
0x18001d937  mov     r8, rax
0x18001d93a  mov     ecx, r14d
0x18001d93d  call    ??$MakeCBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@@Streams@Storage@Windows@@YAJIIPEAEVCBuffer_StandardCleanup@012@PEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup>(uint,uint,uchar *,Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::IBuffer * *)
0x18001d942  mov     rcx, [rbp+40h]; this
0x18001d946  test    eax, eax
0x18001d948  js      loc_18001DA8E
0x18001d94e  mov     [rbp+arg_8], rdi
0x18001d952  mov     rcx, [rsi]
0x18001d955  mov     [rbp+SourceSize], rdi
0x18001d959  test    rcx, rcx
0x18001d95c  jnz     short loc_18001D963
0x18001d95e  mov     rcx, rdi
0x18001d961  jmp     short loc_18001D994
0x18001d963  mov     [rbp+var_20], edi
0x18001d966  xorps   xmm0, xmm0
0x18001d969  movdqu  [rbp+var_18], xmm0
0x18001d96e  mov     rax, [rcx]
0x18001d971  lea     r8, [rbp+SourceSize]
0x18001d975  lea     rdx, ??$guid_v@UIBufferByteAccess@Streams@Storage@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Storage::Streams::IBufferByteAccess>
0x18001d97c  mov     rax, [rax]
0x18001d97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d984  test    eax, eax
0x18001d986  js      loc_18001DAA3
0x18001d98c  mov     rcx, [rbp+SourceSize]
0x18001d990  mov     [rbp+SourceSize], rcx
0x18001d994  mov     rax, [rcx]
0x18001d997  lea     rdx, [rbp+arg_8]
0x18001d99b  mov     rax, [rax+18h]
0x18001d99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9a4  mov     rcx, [rbp+40h]; this
0x18001d9a8  test    eax, eax
0x18001d9aa  js      loc_18001DAAF
0x18001d9b0  mov     r9, rbx; SourceSize
0x18001d9b3  mov     r8, [r12+8]; Source
0x18001d9b8  mov     rdx, rbx; DestinationSize
0x18001d9bb  mov     rcx, [rbp+arg_8]; Destination
0x18001d9bf  call    memcpy_s
0x18001d9c4  mov     rcx, [rsi]
0x18001d9c7  mov     rax, [rcx]
0x18001d9ca  mov     edx, r14d
0x18001d9cd  mov     rax, [rax+40h]
0x18001d9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9d6  mov     rcx, [rbp+40h]; this
0x18001d9da  test    eax, eax
0x18001d9dc  js      short loc_18001D9F8
0x18001d9de  lea     rcx, [rbp+SourceSize]
0x18001d9e2  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d9e7  add     rsp, 68h
0x18001d9eb  pop     r15
0x18001d9ed  pop     r14
0x18001d9ef  pop     r13
0x18001d9f1  pop     r12
0x18001d9f3  pop     rdi
0x18001d9f4  pop     rsi
0x18001d9f5  pop     rbx
0x18001d9f6  pop     rbp
0x18001d9f7  retn
0x18001d9f8  mov     r9d, eax; char *
0x18001d9fb  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da02  mov     edx, 542h; void *
0x18001da07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da0d  mov     r9d, eax; char *
0x18001da10  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da17  mov     edx, 527h; void *
0x18001da1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da22  mov     r9d, eax; char *
0x18001da25  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da2c  mov     edx, 529h; void *
0x18001da31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da37  lea     rdx, [rbp+var_20]
0x18001da3b  mov     ecx, eax
0x18001da3d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001da43  mov     r9d, eax; char *
0x18001da46  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da4d  mov     edx, 52Dh; void *
0x18001da52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da58  lea     rdx, [rbp+var_20]
0x18001da5c  mov     ecx, eax
0x18001da5e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001da64  mov     r9d, eax; char *
0x18001da67  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da6e  mov     edx, 531h; void *
0x18001da73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da79  mov     r9d, eax; char *
0x18001da7c  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da83  mov     edx, 536h; void *
0x18001da88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da8e  mov     r9d, eax; char *
0x18001da91  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001da98  mov     edx, 53Dh; void *
0x18001da9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001daa3  lea     rdx, [rbp+var_20]
0x18001daa7  mov     ecx, eax
0x18001daa9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001daaf  mov     r9d, eax; char *
0x18001dab2  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001dab9  mov     edx, 540h; void *
0x18001dabe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
