# CBackgroundCopyFileExt::SetProperty(_DeliveryOptimizationFileProperty,tagVARIANT const *)

- ea: `0x18000e410`
- end: `0x18000e9a0`
- name: `?SetProperty@CBackgroundCopyFileExt@@UEAAJW4_DeliveryOptimizationFileProperty@@PEBUtagVARIANT@@@Z`
- size: `1424`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x18000bd54`
- `0x18000e410`
- `0x18000e9a8`
- `0x18000ecf0`
- `0x18000ef98`
- `0x18001cc3c`
- `0x180084164`
- `0x18008624c`
- `0x1800a98f8`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e65b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e65b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e61c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e61c`

## string_xrefs

- `0x18000e451`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e47e`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e4c3`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e5c6`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e699`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e78b`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e897`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`
- `0x18000e95b`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalFile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBackgroundCopyFileExt::SetProperty(__int64 a1, int a2, unsigned __int16 *a3)
{
  __int64 v4; // rbx
  __int64 result; // rax
  int v6; // ecx
  const char *v7; // r9
  IUnknown *v8; // rsi
  __m128i si128; // xmm1
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rcx
  int v12; // r12d
  volatile signed __int32 *v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int128 *v17; // rax
  __int128 *v18; // r8
  unsigned __int64 v19; // r9
  __int64 v20; // r10
  __int128 *v21; // rax
  __int128 *v22; // rcx
  __int128 *v23; // rdx
  int v24; // eax
  unsigned int v25; // esi
  volatile signed __int32 *v26; // rdi
  volatile signed __int32 *v27; // rdi
  int v28; // eax
  unsigned int v29; // esi
  volatile signed __int32 *v30; // rdi
  int v31; // eax
  unsigned int v32; // ebx
  int v33[4]; // [rsp+20h] [rbp-98h] BYREF
  __int128 v34; // [rsp+30h] [rbp-88h] BYREF
  __int64 v35; // [rsp+40h] [rbp-78h]
  unsigned __int64 v36; // [rsp+48h] [rbp-70h]
  __m128i v37; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v4 = a2;
  if ( (unsigned __int64)a2 >= 7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
      (const char *)0x80D02011LL,
      v33[0]);
    return 2161123345LL;
  }
  if ( a2 == 5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
      (const char *)0x80070057LL,
      v33[0]);
    return 2147942487LL;
  }
  try
  {
    if ( a2 == 3 )
    {
      if ( a3 )
      {
        v6 = *a3;
        if ( v6 != 13 && *a3 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDA,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
            (const char *)0x80070057LL,
            v33[0]);
          return 2147942487LL;
        }
      }
      else
      {
        v6 = 0;
      }
      if ( v6 == 13 )
        v8 = (IUnknown *)*((_QWORD *)a3 + 1);
      else
        v8 = 0;
      si128 = 0;
      *(_OWORD *)v33 = 0;
      if ( v8 )
      {
        v10 = (volatile signed __int32 *)operator new(0x20u);
        v37.m128i_i64[0] = (__int64)v10;
        *((_DWORD *)v10 + 2) = 1;
        *((_DWORD *)v10 + 3) = 1;
        *(_QWORD *)v10 = &std::_Ref_count_obj2<CDownloadStream>::`vftable';
        CDownloadStream::CDownloadStream((CDownloadStream *)(v10 + 4), v8);
        *(_QWORD *)v33 = v10 + 4;
        *(_QWORD *)&v33[2] = v10;
        si128 = _mm_load_si128((const __m128i *)v33);
      }
      else
      {
        v10 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      }
      v11 = *(_QWORD *)(a1 + 24);
      if ( v10 )
        _InterlockedIncrement(v10 + 2);
      v37 = si128;
      v12 = CBackgroundCopyFile::SetDownloadSinkStreamInterface(v11, &v37);
      v13 = (volatile signed __int32 *)v37.m128i_i64[1];
      if ( v37.m128i_i64[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v37.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE1,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
          (const char *)(unsigned int)v12,
          v33[0]);
        if ( v10 )
        {
          if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          }
        }
        return (unsigned int)v12;
      }
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 48));
      if ( *(IUnknown **)(a1 + 40) != v8 )
      {
        if ( v8 )
          ((void (__fastcall *)(IUnknown *))v8->lpVtbl->AddRef)(v8);
        v14 = *(_QWORD *)(a1 + 40);
        *(_QWORD *)(a1 + 40) = v8;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 48));
      if ( !v10 )
        return 0;
LABEL_72:
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
      return 0;
    }
    if ( a2 == 4 )
    {
      if ( a3 )
      {
        if ( *a3 != 8 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE7,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
            (const char *)0x80070057LL,
            v33[0]);
          return 2147942487LL;
        }
        v15 = *((_QWORD *)a3 + 1);
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(v15 + 2 * v16) );
        v34 = 0;
        v35 = 0;
        v36 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v34);
        v17 = &v34;
        v18 = (__int128 *)v34;
        v19 = v36;
        if ( v36 > 7 )
          v17 = (__int128 *)v34;
        v20 = v35;
        v21 = (__int128 *)((char *)v17 + 2 * v35);
        v22 = &v34;
        if ( v36 > 7 )
          v22 = (__int128 *)v34;
        if ( v22 != v21 )
        {
          do
          {
            if ( *(_WORD *)v22 == 47 )
              *(_WORD *)v22 = 92;
            v22 = (__int128 *)((char *)v22 + 2);
          }
          while ( v22 != v21 );
          v19 = v36;
          v20 = v35;
          v18 = (__int128 *)v34;
        }
        v23 = &v34;
        if ( v19 > 7 )
          v23 = v18;
        WstrToUTF8(&v37, v23, v20);
        *(_OWORD *)v33 = 0;
        std::make_shared<CConfigValue,std::string const &>(v33, &v37);
        v24 = CBackgroundCopyFile::SetProperty(*(CBackgroundCopyFile **)(a1 + 24), 3u, (const char **)v33);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEC,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
            (const char *)(unsigned int)v24,
            v33[0]);
          v26 = *(volatile signed __int32 **)&v33[2];
          if ( *(_QWORD *)&v33[2] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v33[2] + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
              if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
            }
          }
          std::string::~string(&v37);
          std::wstring::~wstring(&v34);
          return v25;
        }
        v27 = *(volatile signed __int32 **)&v33[2];
        if ( *(_QWORD *)&v33[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v33[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
            if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
          }
        }
        std::string::~string(&v37);
        std::wstring::~wstring(&v34);
        return 0;
      }
    }
    else if ( a3 )
    {
      *(_OWORD *)v33 = 0;
      ConfigValueFromVariant(v33, a3);
      v28 = CBackgroundCopyFile::SetProperty(
              *(CBackgroundCopyFile **)(a1 + 24),
              *((_DWORD *)qword_18012A740 + v4),
              (const char **)v33);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
          (const char *)(unsigned int)v28,
          v33[0]);
        v30 = *(volatile signed __int32 **)&v33[2];
        if ( *(_QWORD *)&v33[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v33[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
        return v29;
      }
      v10 = *(volatile signed __int32 **)&v33[2];
      if ( !*(_QWORD *)&v33[2] )
        return 0;
      goto LABEL_72;
    }
    v31 = CBackgroundCopyFile::SetProperty(*(CBackgroundCopyFile **)(a1 + 24), *((_DWORD *)qword_18012A740 + a2), 0);
    v32 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
        (const char *)(unsigned int)v31,
        v33[0]);
      return v32;
    }
    return 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xFA,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalFile.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000e410  push    rbx
0x18000e412  push    rsi
0x18000e413  push    rdi
0x18000e414  push    r12
0x18000e416  push    r13
0x18000e418  push    r14
0x18000e41a  push    r15
0x18000e41c  sub     rsp, 80h
0x18000e423  mov     rax, cs:__security_cookie
0x18000e42a  xor     rax, rsp
0x18000e42d  mov     [rsp+0B8h+var_48], rax
0x18000e432  mov     r15, rcx
0x18000e435  xor     r13d, r13d
0x18000e438  movsxd  rbx, edx
0x18000e43b  cmp     rbx, 7
0x18000e43f  jb      short loc_18000E469
0x18000e441  mov     rcx, [rsp+0B8h]; this
0x18000e449  mov     ebx, 80D02011h
0x18000e44e  mov     r9d, ebx; char *
0x18000e451  lea     r8, aCW1SSrcDeliver_98; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000e458  mov     edx, 0D5h; void *
0x18000e45d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e462  mov     eax, ebx
0x18000e464  jmp     loc_18000E97F
0x18000e469  cmp     edx, 5
0x18000e46c  jnz     short loc_18000E496
0x18000e46e  mov     rcx, [rsp+0B8h]; this
0x18000e476  mov     ebx, 80070057h
0x18000e47b  mov     r9d, ebx; char *
0x18000e47e  lea     r8, aCW1SSrcDeliver_98; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000e485  mov     edx, 0D6h; void *
0x18000e48a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e48f  mov     eax, ebx
0x18000e491  jmp     loc_18000E97F
0x18000e496  cmp     edx, 3
0x18000e499  jnz     loc_18000E670
0x18000e49f  test    r8, r8
0x18000e4a2  jz      short loc_18000E4DB
0x18000e4a4  movzx   eax, word ptr [r8]
0x18000e4a8  mov     ecx, eax
0x18000e4aa  cmp     eax, 0Dh
0x18000e4ad  jz      short loc_18000E4DE
0x18000e4af  test    eax, eax
0x18000e4b1  jz      short loc_18000E4DE
0x18000e4b3  mov     rcx, [rsp+0B8h]; this
0x18000e4bb  mov     ebx, 80070057h
0x18000e4c0  mov     r9d, ebx; char *
0x18000e4c3  lea     r8, aCW1SSrcDeliver_98; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000e4ca  mov     edx, 0DAh; void *
0x18000e4cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4d4  mov     eax, ebx
0x18000e4d6  jmp     loc_18000E97F
0x18000e4db  mov     ecx, r13d
0x18000e4de  cmp     ecx, 0Dh
0x18000e4e1  jnz     short loc_18000E4E9
0x18000e4e3  mov     rsi, [r8+8]
0x18000e4e7  jmp     short loc_18000E4EC
0x18000e4e9  mov     rsi, r13
0x18000e4ec  xorps   xmm0, xmm0
0x18000e4ef  xorps   xmm1, xmm1
0x18000e4f2  movdqa  xmmword ptr [rsp+0B8h+var_98], xmm1; int
0x18000e4f8  test    rsi, rsi
0x18000e4fb  jz      short loc_18000E549
0x18000e4fd  mov     ecx, 20h ; ' '; Size
0x18000e502  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e507  mov     rdi, rax
0x18000e50a  mov     qword ptr [rsp+0B8h+var_68], rax
0x18000e50f  mov     dword ptr [rax+8], 1
0x18000e516  mov     dword ptr [rax+0Ch], 1
0x18000e51d  lea     rax, ??_7?$_Ref_count_obj2@VCDownloadStream@@@std@@6B@; const std::_Ref_count_obj2<CDownloadStream>::`vftable'
0x18000e524  mov     [rdi], rax
0x18000e527  lea     rbx, [rdi+10h]
0x18000e52b  mov     rdx, rsi; pProxy
0x18000e52e  mov     rcx, rbx; this
0x18000e531  call    ??0CDownloadStream@@QEAA@PEAUIUnknown@@@Z; CDownloadStream::CDownloadStream(IUnknown *)
0x18000e536  nop
0x18000e537  mov     qword ptr [rsp+0B8h+var_98], rbx
0x18000e53c  mov     qword ptr [rsp+0B8h+var_98+8], rdi
0x18000e541  movdqa  xmm1, xmmword ptr [rsp+0B8h+var_98]
0x18000e547  jmp     short loc_18000E553
0x18000e549  psrldq  xmm0, 8
0x18000e54e  movq    rdi, xmm0
0x18000e553  mov     rcx, [r15+18h]
0x18000e557  test    rdi, rdi
0x18000e55a  jz      short loc_18000E560
0x18000e55c  lock inc dword ptr [rdi+8]
0x18000e560  movdqa  [rsp+0B8h+var_68], xmm1
0x18000e566  lea     rdx, [rsp+0B8h+var_68]
0x18000e56b  call    ?SetDownloadSinkStreamInterface@CBackgroundCopyFile@@QEAAJAEBV?$shared_ptr@VIDownloadStream@@@std@@@Z; CBackgroundCopyFile::SetDownloadSinkStreamInterface(std::shared_ptr<IDownloadStream> const &)
0x18000e570  mov     r12d, eax
0x18000e573  mov     r14, qword ptr [rsp+0B8h+var_68+8]
0x18000e578  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e57c  test    r14, r14
0x18000e57f  jz      short loc_18000E5B6
0x18000e581  mov     eax, ebx
0x18000e583  lock xadd [r14+8], eax
0x18000e589  add     eax, ebx
0x18000e58b  jnz     short loc_18000E5B6
0x18000e58d  mov     rax, [r14]
0x18000e590  mov     rcx, r14
0x18000e593  mov     rax, [rax]
0x18000e596  call    _guard_dispatch_icall
0x18000e59b  mov     eax, ebx
0x18000e59d  lock xadd [r14+0Ch], eax
0x18000e5a3  add     eax, ebx
0x18000e5a5  jnz     short loc_18000E5B6
0x18000e5a7  mov     rax, [r14]
0x18000e5aa  mov     rcx, r14
0x18000e5ad  mov     rax, [rax+8]
0x18000e5b1  call    _guard_dispatch_icall
0x18000e5b6  test    r12d, r12d
0x18000e5b9  jns     short loc_18000E618
0x18000e5bb  mov     rcx, [rsp+0B8h]; this
0x18000e5c3  mov     r9d, r12d; char *
0x18000e5c6  lea     r8, aCW1SSrcDeliver_98; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000e5cd  mov     edx, 0E1h; void *
0x18000e5d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5d7  nop
0x18000e5d8  test    rdi, rdi
0x18000e5db  jz      short loc_18000E610
0x18000e5dd  mov     eax, ebx
0x18000e5df  lock xadd [rdi+8], eax
0x18000e5e4  add     eax, ebx
0x18000e5e6  jnz     short loc_18000E610
0x18000e5e8  mov     rax, [rdi]
0x18000e5eb  mov     rcx, rdi
0x18000e5ee  mov     rax, [rax]
0x18000e5f1  call    _guard_dispatch_icall
0x18000e5f6  mov     ecx, ebx
0x18000e5f8  lock xadd [rdi+0Ch], ecx
0x18000e5fd  add     ecx, ebx
0x18000e5ff  jnz     short loc_18000E610
0x18000e601  mov     rcx, [rdi]
0x18000e604  mov     rax, [rcx+8]
0x18000e608  mov     rcx, rdi
0x18000e60b  call    _guard_dispatch_icall
0x18000e610  mov     eax, r12d
0x18000e613  jmp     loc_18000E97F
0x18000e618  lea     rcx, [r15+30h]; SRWLock
0x18000e61c  call    cs:__imp_AcquireSRWLockExclusive
0x18000e622  cmp     [r15+28h], rsi
0x18000e626  jz      short loc_18000E657
0x18000e628  test    rsi, rsi
0x18000e62b  jz      short loc_18000E63D
0x18000e62d  mov     rax, [rsi]
0x18000e630  mov     rcx, rsi
0x18000e633  mov     rax, [rax+8]
0x18000e637  call    _guard_dispatch_icall
0x18000e63c  nop
0x18000e63d  mov     rcx, [r15+28h]
0x18000e641  mov     [r15+28h], rsi
0x18000e645  test    rcx, rcx
0x18000e648  jz      short loc_18000E657
0x18000e64a  mov     rax, [rcx]
0x18000e64d  mov     rax, [rax+10h]
0x18000e651  call    _guard_dispatch_icall
0x18000e656  nop
0x18000e657  lea     rcx, [r15+30h]; SRWLock
0x18000e65b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e661  nop
0x18000e662  test    rdi, rdi
0x18000e665  jz      loc_18000E970
0x18000e66b  jmp     loc_18000E8FF
0x18000e670  cmp     edx, 4
0x18000e673  jnz     loc_18000E84F
0x18000e679  test    r8, r8
0x18000e67c  jz      loc_18000E934
0x18000e682  cmp     word ptr [r8], 8
0x18000e687  jz      short loc_18000E6B1
0x18000e689  mov     rcx, [rsp+0B8h]; this
0x18000e691  mov     ebx, 80070057h
0x18000e696  mov     r9d, ebx; char *
0x18000e699  lea     r8, aCW1SSrcDeliver_98; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000e6a0  mov     edx, 0E7h; void *
0x18000e6a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6aa  mov     eax, ebx
0x18000e6ac  jmp     loc_18000E97F
0x18000e6b1  mov     rdx, [r8+8]
0x18000e6b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e6b9  mov     r8, rbx
0x18000e6bc  inc     r8
0x18000e6bf  cmp     [rdx+r8*2], r13w
0x18000e6c4  jnz     short loc_18000E6BC
0x18000e6c6  xorps   xmm0, xmm0
0x18000e6c9  movups  [rsp+0B8h+var_88], xmm0
0x18000e6ce  mov     [rsp+0B8h+var_78], r13
0x18000e6d3  mov     [rsp+0B8h+var_70], r13
0x18000e6d8  lea     rcx, [rsp+0B8h+var_88]
0x18000e6dd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000e6e2  nop
0x18000e6e3  lea     rax, [rsp+0B8h+var_88]
0x18000e6e8  mov     r8, qword ptr [rsp+0B8h+var_88]
0x18000e6ed  mov     r9, [rsp+0B8h+var_70]
0x18000e6f2  cmp     r9, 7
0x18000e6f6  cmova   rax, r8
0x18000e6fa  mov     r10, [rsp+0B8h+var_78]
0x18000e6ff  lea     rax, [rax+r10*2]
0x18000e703  lea     rcx, [rsp+0B8h+var_88]
0x18000e708  cmova   rcx, r8
0x18000e70c  cmp     rcx, rax
0x18000e70f  jz      short loc_18000E734
0x18000e711  cmp     word ptr [rcx], 2Fh ; '/'
0x18000e715  jnz     short loc_18000E71C
0x18000e717  mov     word ptr [rcx], 5Ch ; '\'
0x18000e71c  add     rcx, 2
0x18000e720  cmp     rcx, rax
0x18000e723  jnz     short loc_18000E711
0x18000e725  mov     r9, [rsp+0B8h+var_70]
0x18000e72a  mov     r10, [rsp+0B8h+var_78]
0x18000e72f  mov     r8, qword ptr [rsp+0B8h+var_88]
0x18000e734  lea     rdx, [rsp+0B8h+var_88]
0x18000e739  cmp     r9, 7
0x18000e73d  cmova   rdx, r8
0x18000e741  mov     r8, r10
0x18000e744  lea     rcx, [rsp+0B8h+var_68]
0x18000e749  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x18000e74e  nop
0x18000e74f  xorps   xmm0, xmm0
0x18000e752  movups  xmmword ptr [rsp+0B8h+var_98], xmm0; int
0x18000e757  lea     rdx, [rsp+0B8h+var_68]
0x18000e75c  lea     rcx, [rsp+0B8h+var_98]
0x18000e761  call    ??$make_shared@VCConfigValue@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$shared_ptr@VCConfigValue@@@0@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_shared<CConfigValue,std::string const &>(std::string const &)
0x18000e766  nop
0x18000e767  lea     r8, [rsp+0B8h+var_98]
0x18000e76c  mov     edx, 3
0x18000e771  mov     rcx, [r15+18h]
0x18000e775  call    ?SetProperty@CBackgroundCopyFile@@QEAAJW4DownloadFileProperty@@PEBV?$shared_ptr@VCConfigValue@@@std@@@Z; CBackgroundCopyFile::SetProperty(DownloadFileProperty,std::shared_ptr<CConfigValue> const *)
0x18000e77a  mov     esi, eax
0x18000e77c  test    eax, eax
0x18000e77e  jns     short loc_18000E7F7
0x18000e780  mov     rcx, [rsp+0B8h]; this
0x18000e788  mov     r9d, eax; char *
0x18000e78b  lea     r8, aCW1SSrcDeliver_98; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000e792  mov     edx, 0ECh; void *
0x18000e797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e79c  nop
0x18000e79d  mov     rdi, qword ptr [rsp+0B8h+var_98+8]
0x18000e7a2  test    rdi, rdi
0x18000e7a5  jz      short loc_18000E7DB
0x18000e7a7  mov     eax, ebx
0x18000e7a9  lock xadd [rdi+8], eax
0x18000e7ae  add     eax, ebx
0x18000e7b0  jnz     short loc_18000E7DB
0x18000e7b2  mov     rax, [rdi]
0x18000e7b5  mov     rcx, rdi
0x18000e7b8  mov     rax, [rax]
0x18000e7bb  call    _guard_dispatch_icall
0x18000e7c0  mov     eax, ebx
0x18000e7c2  lock xadd [rdi+0Ch], eax
0x18000e7c7  add     eax, ebx
0x18000e7c9  jnz     short loc_18000E7DB
0x18000e7cb  mov     rdx, [rdi]
0x18000e7ce  mov     rcx, rdi
0x18000e7d1  mov     rax, [rdx+8]
0x18000e7d5  call    _guard_dispatch_icall
0x18000e7da  nop
0x18000e7db  lea     rcx, [rsp+0B8h+var_68]; void *
0x18000e7e0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000e7e5  nop
0x18000e7e6  lea     rcx, [rsp+0B8h+var_88]
0x18000e7eb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e7f0  mov     eax, esi
0x18000e7f2  jmp     loc_18000E97F
0x18000e7f7  mov     rdi, qword ptr [rsp+0B8h+var_98+8]
0x18000e7fc  test    rdi, rdi
0x18000e7ff  jz      short loc_18000E835
0x18000e801  mov     eax, ebx
0x18000e803  lock xadd [rdi+8], eax
0x18000e808  add     eax, ebx
0x18000e80a  jnz     short loc_18000E835
0x18000e80c  mov     rax, [rdi]
0x18000e80f  mov     rcx, rdi
0x18000e812  mov     rax, [rax]
0x18000e815  call    _guard_dispatch_icall
0x18000e81a  mov     eax, ebx
0x18000e81c  lock xadd [rdi+0Ch], eax
0x18000e821  add     eax, ebx
0x18000e823  jnz     short loc_18000E835
0x18000e825  mov     rax, [rdi]
0x18000e828  mov     rcx, rdi
0x18000e82b  mov     rax, [rax+8]
0x18000e82f  call    _guard_dispatch_icall
0x18000e834  nop
0x18000e835  lea     rcx, [rsp+0B8h+var_68]; void *
0x18000e83a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000e83f  nop
0x18000e840  lea     rcx, [rsp+0B8h+var_88]
0x18000e845  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e84a  jmp     loc_18000E970
0x18000e84f  test    r8, r8
0x18000e852  jz      loc_18000E934
0x18000e858  xorps   xmm0, xmm0
0x18000e85b  movups  xmmword ptr [rsp+0B8h+var_98], xmm0; int
0x18000e860  mov     rdx, r8
0x18000e863  lea     rcx, [rsp+0B8h+var_98]
0x18000e868  call    ?ConfigValueFromVariant@@YA?AV?$shared_ptr@VCConfigValue@@@std@@AEBUtagVARIANT@@@Z; ConfigValueFromVariant(tagVARIANT const &)
0x18000e86d  nop
0x18000e86e  lea     rdx, qword_18012A740
0x18000e875  lea     r8, [rsp+0B8h+var_98]
0x18000e87a  mov     edx, [rdx+rbx*4]
  ... truncated ...
```
