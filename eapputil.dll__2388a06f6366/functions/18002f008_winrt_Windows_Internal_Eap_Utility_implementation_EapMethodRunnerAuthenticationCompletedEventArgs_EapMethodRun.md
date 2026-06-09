# winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::EapMethodRunnerAuthenticationCompletedEventArgs(winrt::Windows::Internal::Eap::Utility::EapAuthenticationStatus,bool,tagEapHostPeerMethodResult const &,std::optional<winrt::Windows::Storage::Streams::IBuffer>)

- ea: `0x18002f008`
- end: `0x18002f56b`
- name: `??0EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA@W4EapAuthenticationStatus@23456@_NAEBUtagEapHostPeerMethodResult@@V?$optional@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@Z`
- size: `1379`
- prototype: `__int64 __fastcall(__int64, int, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000e4c0`

## callees

- `0x180002b1a`
- `0x180002b78`
- `0x1800037dc`
- `0x180003936`
- `0x1800083ec`
- `0x180010df0`
- `0x18001109c`
- `0x180011424`
- `0x18001156c`
- `0x180012178`
- `0x18002de70`
- `0x18002f008`
- `0x18002f574`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f28a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f29d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f311`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f31f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f28a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f29d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f311`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002f31f`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::EapMethodRunnerAuthenticationCompletedEventArgs(
        __int64 a1,
        int a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  __int64 *v7; // rdi
  __int64 *v8; // r12
  __int64 *v9; // r15
  _QWORD *v10; // rsi
  int *v11; // r8
  unsigned int v12; // ecx
  unsigned int v13; // eax
  __int64 v14; // r15
  __int64 v15; // r12
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ebx
  char *v19; // rsi
  __int64 v20; // r8
  char *v21; // rdi
  __int64 v22; // rbx
  unsigned __int8 *v23; // rsi
  char v24; // al
  char v25; // cl
  unsigned __int64 v26; // rsi
  void *v27; // rcx
  __int64 v28; // r12
  unsigned __int64 v29; // r15
  const void *v30; // r12
  size_t v31; // rsi
  void *v32; // rcx
  __int64 v33; // r12
  size_t v34; // r15
  const void *v35; // r12
  _QWORD *v36; // rsi
  __int64 *View; // rbx
  __int64 v38; // rcx
  void *v39; // rcx
  __int64 *v40; // rbx
  __int64 v41; // rcx
  void *v42; // rcx
  __int64 *v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // rcx
  char *v48; // [rsp+20h] [rbp-61h] BYREF
  int v49; // [rsp+28h] [rbp-59h]
  unsigned int v50; // [rsp+2Ch] [rbp-55h]
  unsigned int v51; // [rsp+30h] [rbp-51h]
  __int64 v52; // [rsp+38h] [rbp-49h] BYREF
  size_t Size; // [rsp+40h] [rbp-41h] BYREF
  void *v54; // [rsp+48h] [rbp-39h]
  __int128 v55; // [rsp+50h] [rbp-31h] BYREF
  __int64 v56; // [rsp+60h] [rbp-21h]
  int *v57; // [rsp+68h] [rbp-19h]
  _QWORD v58[2]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v59; // [rsp+80h] [rbp-1h] BYREF
  __int64 v60; // [rsp+88h] [rbp+7h]
  char v61; // [rsp+E8h] [rbp+67h]
  __int64 v63; // [rsp+F8h] [rbp+77h] BYREF

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs,winrt::Windows::Internal::Eap::Utility::IEapMethodRunnerAuthenticationCompletedEventArgs>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs>::`vftable';
  v7 = (__int64 *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_BYTE *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  v8 = (__int64 *)(a1 + 80);
  *(_QWORD *)(a1 + 80) = 0;
  *(_BYTE *)(a1 + 88) = 0;
  v9 = (__int64 *)(a1 + 96);
  *(_QWORD *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 104) = 0;
  v10 = (_QWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 112) = 0;
  v11 = *(int **)(a4 + 40);
  v57 = v11;
  v12 = 0;
  if ( v11 )
    v12 = *v11;
  v51 = v12;
  *(_DWORD *)(a1 + 24) = a2;
  v61 = 0;
  LOBYTE(v63) = 0;
  v55 = 0;
  v56 = 0;
  v13 = 0;
  v50 = 0;
  if ( v12 )
  {
    while ( 1 )
    {
      v14 = 2LL * v13;
      v15 = *((_QWORD *)v11 + 1);
      v16 = *(unsigned int *)(v15 + 16LL * v13 + 4);
      v17 = *(_QWORD *)(v15 + 8 * v14 + 8);
      if ( !v17 && v16 )
        gsl::details::terminate(0);
      v49 = *(_DWORD *)(v15 + 8 * v14);
      v18 = v49;
      v58[0] = v16;
      v58[1] = v17;
      winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(&v52, (unsigned int *)v58);
      v19 = (char *)operator new(0x28u);
      v48 = v19;
      v21 = v19 + 16;
      *((_QWORD *)v19 + 2) = &winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute,winrt::Windows::Internal::Eap::Utility::IEapAttribute>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_QWORD *)v19 + 1) = 1;
      *(_QWORD *)v19 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute>::`vftable';
      *((_QWORD *)v19 + 4) = 0;
      *((_DWORD *)v19 + 6) = v18;
      v22 = v52;
      if ( v19 + 32 != (char *)&v52 )
      {
        *((_QWORD *)v19 + 4) = v52;
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      }
      *(_QWORD *)v19 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute>::`vftable';
      v48 = v19 + 16;
      if ( *((_QWORD *)&v55 + 1) == v56 )
      {
        std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::_Emplace_reallocate<winrt::Windows::Internal::Eap::Utility::EapAttribute const &>(
          &v55,
          *((_QWORD *)&v55 + 1),
          &v48);
        v21 = v48;
      }
      else
      {
        **((_QWORD **)&v55 + 1) = v21;
        if ( v19 != (char *)-16LL )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
        *((_QWORD *)&v55 + 1) += 8LL;
      }
      if ( !*(_BYTE *)(a1 + 40) && v49 == 26 )
        break;
      if ( !*(_BYTE *)(a1 + 56) && v49 == 9003 && *(_DWORD *)(v15 + 8 * v14 + 4) >= 0x40u )
      {
        v36 = (_QWORD *)(a1 + 64);
        if ( (__int64 *)(a1 + 64) != &v52 )
        {
          if ( *v36 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(a1 + 64);
          *v36 = v22;
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
        }
        *(_BYTE *)(a1 + 56) = 1;
      }
LABEL_54:
      if ( v21 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v48);
      if ( v22 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v52);
      v13 = v50 + 1;
      v50 = v13;
      if ( v13 >= v51 )
      {
        v7 = (__int64 *)(a1 + 32);
        v10 = (_QWORD *)(a1 + 112);
        v9 = (__int64 *)(a1 + 96);
        v8 = (__int64 *)(a1 + 80);
        goto LABEL_61;
      }
      v11 = v57;
    }
    v23 = *(unsigned __int8 **)(v15 + 8 * v14 + 8);
    if ( (v23[3] | ((v23[2] | (((*v23 << 8) | v23[1]) << 8)) << 8)) != 0x137 )
      goto LABEL_54;
    if ( a3 )
    {
      v24 = 16;
      v25 = 17;
    }
    else
    {
      v24 = 17;
      v25 = 16;
    }
    if ( v24 == v23[4] )
    {
      LOBYTE(v63) = 1;
      v26 = v23[8];
      LOBYTE(v20) = v26;
      winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::AllocateMasterSessionKeyIfNeeded(
        a1,
        &v59,
        v20);
      if ( !v26 )
        goto LABEL_26;
      v27 = (void *)(v26 + v60);
      if ( !(v26 + v60) )
        goto LABEL_33;
      v28 = *(_QWORD *)(v15 + 8 * v14 + 8);
      v29 = v59 - v26;
      v30 = (const void *)(v28 + 9);
      if ( v30 && v29 >= v26 )
      {
        memcpy_0(v27, v30, (unsigned int)v26);
        goto LABEL_26;
      }
      memset_0(v27, 0, v59 - v26);
      if ( v30 )
      {
        if ( v29 >= v26 )
          goto LABEL_26;
        *(_DWORD *)_o__errno(v27) = 34;
      }
      else
      {
LABEL_33:
        *(_DWORD *)_o__errno(v27) = 22;
      }
      invalid_parameter_noinfo();
LABEL_26:
      if ( !v61 )
        goto LABEL_54;
      goto LABEL_27;
    }
    if ( v25 != v23[4] )
      goto LABEL_26;
    v61 = 1;
    v31 = v23[8];
    LOBYTE(v20) = v31;
    winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::AllocateMasterSessionKeyIfNeeded(
      a1,
      &Size,
      v20);
    if ( v31 )
    {
      v32 = v54;
      if ( !v54 )
        goto LABEL_43;
      v33 = *(_QWORD *)(v15 + 8 * v14 + 8);
      v34 = Size;
      v35 = (const void *)(v33 + 9);
      if ( v35 && Size >= v31 )
      {
        memcpy_0(v54, v35, (unsigned int)v31);
        goto LABEL_27;
      }
      memset_0(v54, 0, Size);
      if ( v35 )
      {
        if ( v34 >= v31 )
          goto LABEL_27;
        *(_DWORD *)_o__errno(v32) = 34;
      }
      else
      {
LABEL_43:
        *(_DWORD *)_o__errno(v32) = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_27:
    if ( (_BYTE)v63 )
      *(_BYTE *)(a1 + 40) = 1;
    goto LABEL_54;
  }
LABEL_61:
  winrt::single_threaded_vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(
    &v63,
    (__int64 *)&v55);
  View = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
                      &v63,
                      &v48);
  if ( v7 != View )
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v7);
    v38 = *View;
    *View = 0;
    *v7 = v38;
  }
  if ( v48 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v48);
  if ( *(_DWORD *)(a4 + 8) )
  {
    *(_BYTE *)(a1 + 72) = 1;
    v39 = *(void **)(a4 + 16);
    if ( !v39 && *(_DWORD *)(a4 + 12) )
      gsl::details::terminate(0);
    Size = *(unsigned int *)(a4 + 12);
    v54 = v39;
    v40 = winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(&v48, (unsigned int *)&Size);
    if ( v8 != v40 )
    {
      if ( *v8 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v8);
      v41 = *v40;
      *v40 = 0;
      *v8 = v41;
    }
    if ( v48 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v48);
  }
  if ( *(_DWORD *)(a4 + 24) )
  {
    *(_BYTE *)(a1 + 88) = 1;
    v42 = *(void **)(a4 + 32);
    if ( !v42 && *(_DWORD *)(a4 + 28) )
      gsl::details::terminate(0);
    Size = *(unsigned int *)(a4 + 28);
    v54 = v42;
    v43 = winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(&v48, (unsigned int *)&Size);
    if ( v9 != v43 )
    {
      if ( *v9 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v9);
      v44 = *v43;
      *v43 = 0;
      *v9 = v44;
    }
    if ( v48 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v48);
  }
  v45 = a5;
  if ( *(_BYTE *)(a5 + 8) )
  {
    *(_BYTE *)(a1 + 104) = 1;
    if ( v10 != (_QWORD *)v45 )
    {
      if ( *v10 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v10);
      v46 = *(_QWORD *)v45;
      *v10 = *(_QWORD *)v45;
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
  if ( v63 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v63);
  std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::~vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>(&v55);
  if ( *(_BYTE *)(v45 + 8) && *(_QWORD *)v45 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v45);
  return a1;
}

```

## disassembly

```asm
0x18002f008  mov     [rsp-8+arg_10], r8b
0x18002f00d  mov     [rsp-8+arg_0], rcx
0x18002f012  push    rbp
0x18002f013  push    rbx
0x18002f014  push    rsi
0x18002f015  push    rdi
0x18002f016  push    r12
0x18002f018  push    r13
0x18002f01a  push    r14
0x18002f01c  push    r15
0x18002f01e  lea     rbp, [rsp-17h]
0x18002f023  sub     rsp, 98h
0x18002f02a  mov     r13, r9
0x18002f02d  mov     r14, rcx
0x18002f030  xor     ebx, ebx
0x18002f032  lea     rax, ??_7?$produce@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunnerAuthenticationCompletedEventArgs@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs,winrt::Windows::Internal::Eap::Utility::IEapMethodRunnerAuthenticationCompletedEventArgs>::`vftable'
0x18002f039  mov     [rcx+10h], rax
0x18002f03d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002f044  mov     qword ptr [rcx+8], 1
0x18002f04c  lea     rax, ??_7?$heap_implements@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs>::`vftable'
0x18002f053  mov     [rcx], rax
0x18002f056  lea     rdi, [rcx+20h]
0x18002f05a  mov     [rdi], rbx
0x18002f05d  mov     [rcx+28h], bl
0x18002f060  mov     [rcx+30h], rbx
0x18002f064  mov     [rcx+38h], bl
0x18002f067  mov     [rcx+40h], rbx
0x18002f06b  mov     [rcx+48h], bl
0x18002f06e  lea     r12, [rcx+50h]
0x18002f072  mov     [r12], rbx
0x18002f076  mov     [rcx+58h], bl
0x18002f079  lea     r15, [rcx+60h]
0x18002f07d  mov     [r15], rbx
0x18002f080  mov     [rcx+68h], bl
0x18002f083  lea     rsi, [rcx+70h]
0x18002f087  mov     [rsi], rbx
0x18002f08a  mov     r8, [r9+28h]
0x18002f08e  mov     [rbp+4Fh+var_68], r8
0x18002f092  test    r8, r8
0x18002f095  mov     ecx, ebx
0x18002f097  jz      short loc_18002F09C
0x18002f099  mov     ecx, [r8]
0x18002f09c  mov     [rbp+4Fh+var_A0], ecx
0x18002f09f  mov     [r14+18h], edx
0x18002f0a3  mov     [rbp+4Fh+arg_8], bl
0x18002f0a6  mov     byte ptr [rbp+4Fh+arg_18], bl
0x18002f0a9  xorps   xmm0, xmm0
0x18002f0ac  movdqu  [rbp+4Fh+var_80], xmm0
0x18002f0b1  mov     [rbp+4Fh+var_70], rbx
0x18002f0b5  mov     eax, ebx
0x18002f0b7  mov     [rbp+4Fh+var_A4], ebx
0x18002f0ba  test    ecx, ecx
0x18002f0bc  jz      loc_18002F3C5
0x18002f0c2  mov     r15d, eax
0x18002f0c5  add     r15, r15
0x18002f0c8  mov     r12, [r8+8]
0x18002f0cc  mov     eax, [r12+r15*8+4]
0x18002f0d1  mov     rcx, [r12+r15*8+8]; this
0x18002f0d6  test    rcx, rcx
0x18002f0d9  jnz     short loc_18002F0E4
0x18002f0db  test    rax, rax
0x18002f0de  jnz     loc_18002F55F
0x18002f0e4  mov     ebx, [r12+r15*8]
0x18002f0e8  mov     [rbp+4Fh+var_A8], ebx
0x18002f0eb  mov     [rbp+4Fh+var_60], rax
0x18002f0ef  mov     [rbp+4Fh+var_58], rcx
0x18002f0f3  lea     rdx, [rbp+4Fh+var_60]
0x18002f0f7  lea     rcx, [rbp+4Fh+var_98]
0x18002f0fb  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x18002f100  nop
0x18002f101  mov     ecx, 28h ; '('; Size
0x18002f106  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f10b  mov     rsi, rax
0x18002f10e  mov     [rbp+4Fh+var_B0], rax
0x18002f112  lea     rdi, [rax+10h]
0x18002f116  lea     rax, ??_7?$produce@UEapAttribute@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapAttribute@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute,winrt::Windows::Internal::Eap::Utility::IEapAttribute>::`vftable'
0x18002f11d  mov     [rdi], rax
0x18002f120  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002f127  mov     qword ptr [rsi+8], 1
0x18002f12f  lea     rax, ??_7?$heap_implements@UEapAttribute@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute>::`vftable'
0x18002f136  mov     [rsi], rax
0x18002f139  lea     rax, [rsi+20h]
0x18002f13d  mov     qword ptr [rax], 0
0x18002f144  mov     [rsi+18h], ebx
0x18002f147  lea     rcx, [rbp+4Fh+var_98]
0x18002f14b  mov     rbx, [rbp+4Fh+var_98]
0x18002f14f  cmp     rax, rcx
0x18002f152  jz      short loc_18002F16B
0x18002f154  mov     [rax], rbx
0x18002f157  test    rbx, rbx
0x18002f15a  jz      short loc_18002F16B
0x18002f15c  mov     rax, [rbx]
0x18002f15f  mov     rcx, rbx
0x18002f162  mov     rax, [rax+8]
0x18002f166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f16b  lea     rax, ??_7?$heap_implements@UEapAttribute@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute>::`vftable'
0x18002f172  mov     [rsi], rax
0x18002f175  mov     [rbp+4Fh+var_B0], rdi
0x18002f179  mov     rdx, qword ptr [rbp+4Fh+var_80+8]
0x18002f17d  cmp     rdx, [rbp+4Fh+var_70]
0x18002f181  jz      short loc_18002F1A1
0x18002f183  mov     [rdx], rdi
0x18002f186  test    rdi, rdi
0x18002f189  jz      short loc_18002F19A
0x18002f18b  mov     rax, [rdi]
0x18002f18e  mov     rcx, rdi
0x18002f191  mov     rax, [rax+8]
0x18002f195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f19a  add     qword ptr [rbp+4Fh+var_80+8], 8
0x18002f19f  jmp     short loc_18002F1B2
0x18002f1a1  lea     r8, [rbp+4Fh+var_B0]
0x18002f1a5  lea     rcx, [rbp+4Fh+var_80]
0x18002f1a9  call    ??$_Emplace_reallocate@AEBUEapAttribute@Utility@Eap@Internal@Windows@winrt@@@?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@AEAAPEAUEapAttribute@Utility@Eap@Internal@Windows@winrt@@QEAU234567@AEBU234567@@Z; std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::_Emplace_reallocate<winrt::Windows::Internal::Eap::Utility::EapAttribute const &>(winrt::Windows::Internal::Eap::Utility::EapAttribute * const,winrt::Windows::Internal::Eap::Utility::EapAttribute const &)
0x18002f1ae  mov     rdi, [rbp+4Fh+var_B0]
0x18002f1b2  mov     eax, [rbp+4Fh+var_A8]
0x18002f1b5  cmp     byte ptr [r14+28h], 0
0x18002f1ba  jnz     loc_18002F335
0x18002f1c0  cmp     eax, 1Ah
0x18002f1c3  jnz     loc_18002F335
0x18002f1c9  mov     rsi, [r12+r15*8+8]
0x18002f1ce  movzx   ecx, byte ptr [rsi+1]
0x18002f1d2  movzx   eax, byte ptr [rsi]
0x18002f1d5  shl     eax, 8
0x18002f1d8  or      ecx, eax
0x18002f1da  shl     ecx, 8
0x18002f1dd  movzx   eax, byte ptr [rsi+2]
0x18002f1e1  or      ecx, eax
0x18002f1e3  shl     ecx, 8
0x18002f1e6  movzx   eax, byte ptr [rsi+3]
0x18002f1ea  or      ecx, eax
0x18002f1ec  cmp     ecx, 137h
0x18002f1f2  jnz     loc_18002F382
0x18002f1f8  cmp     [rbp+4Fh+arg_10], 0
0x18002f1fc  jz      short loc_18002F204
0x18002f1fe  mov     al, 10h
0x18002f200  mov     cl, 11h
0x18002f202  jmp     short loc_18002F208
0x18002f204  mov     al, 11h
0x18002f206  mov     cl, 10h
0x18002f208  cmp     al, [rsi+4]
0x18002f20b  jnz     loc_18002F2AB
0x18002f211  mov     byte ptr [rbp+4Fh+arg_18], 1
0x18002f215  movzx   esi, byte ptr [rsi+8]
0x18002f219  mov     r8b, sil
0x18002f21c  lea     rdx, [rbp+4Fh+var_50]
0x18002f220  mov     rcx, r14
0x18002f223  call    ?AllocateMasterSessionKeyIfNeeded@EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AV?$span@E$0?0@gsl@@E@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::AllocateMasterSessionKeyIfNeeded(uchar)
0x18002f228  test    rsi, rsi
0x18002f22b  jz      short loc_18002F258
0x18002f22d  mov     rcx, [rbp+4Fh+var_48]
0x18002f231  add     rcx, rsi; void *
0x18002f234  jz      short loc_18002F29D
0x18002f236  mov     r12, [r12+r15*8+8]
0x18002f23b  mov     r15, [rbp+4Fh+var_50]
0x18002f23f  sub     r15, rsi
0x18002f242  add     r12, 9
0x18002f246  jz      short loc_18002F276
0x18002f248  cmp     r15, rsi
0x18002f24b  jb      short loc_18002F276
0x18002f24d  mov     r8d, esi; Size
0x18002f250  mov     rdx, r12; Src
0x18002f253  call    memcpy_0
0x18002f258  cmp     [rbp+4Fh+arg_8], 0
0x18002f25c  jz      loc_18002F382
0x18002f262  cmp     byte ptr [rbp+4Fh+arg_18], 0
0x18002f266  jz      loc_18002F382
0x18002f26c  mov     byte ptr [r14+28h], 1
0x18002f271  jmp     loc_18002F382
0x18002f276  mov     r8, r15; Size
0x18002f279  xor     edx, edx; Val
0x18002f27b  call    memset_0
0x18002f280  test    r12, r12
0x18002f283  jz      short loc_18002F29D
0x18002f285  cmp     r15, rsi
0x18002f288  jnb     short loc_18002F258
0x18002f28a  call    cs:__imp__o__errno
0x18002f290  mov     dword ptr [rax], 22h ; '"'
0x18002f296  call    _invalid_parameter_noinfo
0x18002f29b  jmp     short loc_18002F258
0x18002f29d  call    cs:__imp__o__errno
0x18002f2a3  mov     dword ptr [rax], 16h
0x18002f2a9  jmp     short loc_18002F296
0x18002f2ab  cmp     cl, [rsi+4]
0x18002f2ae  jnz     short loc_18002F258
0x18002f2b0  mov     [rbp+4Fh+arg_8], 1
0x18002f2b4  movzx   esi, byte ptr [rsi+8]
0x18002f2b8  mov     r8b, sil
0x18002f2bb  lea     rdx, [rbp+4Fh+Size]
0x18002f2bf  mov     rcx, r14
0x18002f2c2  call    ?AllocateMasterSessionKeyIfNeeded@EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AV?$span@E$0?0@gsl@@E@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::AllocateMasterSessionKeyIfNeeded(uchar)
0x18002f2c7  test    rsi, rsi
0x18002f2ca  jz      short loc_18002F262
0x18002f2cc  mov     rcx, [rbp+4Fh+var_88]; void *
0x18002f2d0  test    rcx, rcx
0x18002f2d3  jz      short loc_18002F31F
0x18002f2d5  mov     r12, [r12+r15*8+8]
0x18002f2da  mov     r15, [rbp+4Fh+Size]
0x18002f2de  add     r12, 9
0x18002f2e2  jz      short loc_18002F2F9
0x18002f2e4  cmp     r15, rsi
0x18002f2e7  jb      short loc_18002F2F9
0x18002f2e9  mov     r8d, esi; Size
0x18002f2ec  mov     rdx, r12; Src
0x18002f2ef  call    memcpy_0
0x18002f2f4  jmp     loc_18002F262
0x18002f2f9  mov     r8, r15; Size
0x18002f2fc  xor     edx, edx; Val
0x18002f2fe  call    memset_0
0x18002f303  test    r12, r12
0x18002f306  jz      short loc_18002F31F
0x18002f308  cmp     r15, rsi
0x18002f30b  jnb     loc_18002F262
0x18002f311  call    cs:__imp__o__errno
0x18002f317  mov     dword ptr [rax], 22h ; '"'
0x18002f31d  jmp     short loc_18002F32B
0x18002f31f  call    cs:__imp__o__errno
0x18002f325  mov     dword ptr [rax], 16h
0x18002f32b  call    _invalid_parameter_noinfo
0x18002f330  jmp     loc_18002F262
0x18002f335  cmp     byte ptr [r14+38h], 0
0x18002f33a  jnz     short loc_18002F382
0x18002f33c  cmp     eax, 232Bh
0x18002f341  jnz     short loc_18002F382
0x18002f343  cmp     dword ptr [r12+r15*8+4], 40h ; '@'
0x18002f349  jb      short loc_18002F382
0x18002f34b  lea     rax, [rbp+4Fh+var_98]
0x18002f34f  lea     rsi, [r14+40h]
0x18002f353  cmp     rsi, rax
0x18002f356  jz      short loc_18002F37D
0x18002f358  cmp     qword ptr [rsi], 0
0x18002f35c  jz      short loc_18002F366
0x18002f35e  mov     rcx, rsi
0x18002f361  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f366  mov     [rsi], rbx
0x18002f369  test    rbx, rbx
0x18002f36c  jz      short loc_18002F37D
0x18002f36e  mov     rax, [rbx]
0x18002f371  mov     rcx, rbx
0x18002f374  mov     rax, [rax+8]
0x18002f378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f37d  mov     byte ptr [r14+38h], 1
0x18002f382  test    rdi, rdi
0x18002f385  jz      short loc_18002F391
0x18002f387  lea     rcx, [rbp+4Fh+var_B0]
0x18002f38b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f390  nop
0x18002f391  test    rbx, rbx
0x18002f394  jz      short loc_18002F39F
0x18002f396  lea     rcx, [rbp+4Fh+var_98]
0x18002f39a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f39f  mov     eax, [rbp+4Fh+var_A4]
0x18002f3a2  inc     eax
0x18002f3a4  mov     [rbp+4Fh+var_A4], eax
0x18002f3a7  cmp     eax, [rbp+4Fh+var_A0]
0x18002f3aa  jnb     short loc_18002F3B5
0x18002f3ac  mov     r8, [rbp+4Fh+var_68]
0x18002f3b0  jmp     loc_18002F0C2
0x18002f3b5  lea     rdi, [r14+20h]
0x18002f3b9  lea     rsi, [r14+70h]
0x18002f3bd  lea     r15, [r14+60h]
0x18002f3c1  lea     r12, [r14+50h]
0x18002f3c5  lea     rdx, [rbp+4Fh+var_80]
0x18002f3c9  lea     rcx, [rbp+4Fh+arg_18]
0x18002f3cd  call    ??$single_threaded_vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute> &&)
0x18002f3d2  nop
0x18002f3d3  lea     rdx, [rbp+4Fh+var_B0]
0x18002f3d7  lea     rcx, [rbp+4Fh+arg_18]
0x18002f3db  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(void)
0x18002f3e0  mov     rbx, rax
0x18002f3e3  cmp     rdi, rax
0x18002f3e6  jz      short loc_18002F403
0x18002f3e8  cmp     qword ptr [rdi], 0
0x18002f3ec  jz      short loc_18002F3F6
0x18002f3ee  mov     rcx, rdi
0x18002f3f1  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f3f6  mov     rcx, [rbx]
0x18002f3f9  mov     qword ptr [rbx], 0
0x18002f400  mov     [rdi], rcx
0x18002f403  xor     edi, edi
0x18002f405  cmp     [rbp+4Fh+var_B0], rdi
0x18002f409  jz      short loc_18002F414
0x18002f40b  lea     rcx, [rbp+4Fh+var_B0]
0x18002f40f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f414  cmp     [r13+8], edi
0x18002f418  jz      short loc_18002F479
0x18002f41a  mov     byte ptr [r14+48h], 1
0x18002f41f  mov     eax, [r13+0Ch]
0x18002f423  mov     rcx, [r13+10h]; this
0x18002f427  test    rcx, rcx
0x18002f42a  jnz     short loc_18002F435
0x18002f42c  test    rax, rax
0x18002f42f  jnz     loc_18002F565
0x18002f435  mov     [rbp+4Fh+Size], rax
0x18002f439  mov     [rbp+4Fh+var_88], rcx
0x18002f43d  lea     rdx, [rbp+4Fh+Size]
0x18002f441  lea     rcx, [rbp+4Fh+var_B0]
0x18002f445  call    ?AllocateIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateIBuffer(gsl::span<uchar,-1>)
0x18002f44a  mov     rbx, rax
0x18002f44d  cmp     r12, rax
0x18002f450  jz      short loc_18002F46A
  ... truncated ...
```
