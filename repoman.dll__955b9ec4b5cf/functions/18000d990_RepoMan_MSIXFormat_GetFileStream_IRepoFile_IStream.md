# RepoMan::MSIXFormat::GetFileStream(IRepoFile *,IStream * *)

- ea: `0x18000d990`
- end: `0x18000e0f7`
- name: `?GetFileStream@MSIXFormat@RepoMan@@UEAAJPEAUIRepoFile@@PEAPEAUIStream@@@Z`
- size: `1895`
- prototype: `__int64 __fastcall(RepoMan::MSIXFormat *__hidden this, struct IRepoFile *, struct IStream **)`
- caller_count: `0`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001504`
- `0x180002010`
- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008574`
- `0x18000d5f4`
- `0x18000d990`
- `0x180013b14`
- `0x180016c8c`
- `0x180016cf4`
- `0x180016d5c`
- `0x180016e50`
- `0x18002f9b0`
- `0x180030478`
- `0x180033634`
- `0x18003386c`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18019a840`
- `0x18019f7a0`
- `0x18019f800`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000df1b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000df1b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000dbf3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000dfed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000dbf3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000dfed`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000dbec`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000dfe3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000dbec`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000dfe3`

## string_xrefs

- `0x18000d9d1`: `MSIXFormat.GetFileStream`
- `0x18000e087`: `Missing package reader.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RepoMan::MSIXFormat::GetFileStream(
        RepoMan::MSIXFormat *this,
        struct IRepoFile *a2,
        struct IStream **a3)
{
  _QWORD *v6; // r12
  unsigned int v7; // eax
  const char *v8; // r9
  unsigned int v9; // eax
  const char *v10; // r9
  __int64 v11; // r9
  size_t v12; // rsi
  unsigned int v13; // eax
  const char *v14; // r9
  unsigned int v15; // eax
  const char *v16; // r9
  size_t v17; // r8
  _OWORD *v18; // rdx
  unsigned __int64 v19; // rax
  void *v20; // rcx
  unsigned int v21; // eax
  const char *v22; // r9
  unsigned __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  RepoMan *v26; // rcx
  const char *v27; // r9
  _BYTE *v28; // rax
  _BYTE *v29; // rdi
  size_t v30; // r8
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // xmm2_8
  __int128 *v33; // r13
  char *v34; // r14
  __int64 v35; // rdi
  size_t v36; // rcx
  void *v37; // rax
  RepoMan::MSIXFormat *v38; // rdi
  void *v39; // rdx
  RepoMan *v40; // rcx
  const char *v41; // r9
  unsigned int v42; // eax
  const char *v43; // r9
  __int64 v44; // rcx
  char *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // r8d
  __int64 result; // rax
  int v50; // [rsp+30h] [rbp-138h] BYREF
  unsigned __int64 v51; // [rsp+38h] [rbp-130h] BYREF
  __int64 v52; // [rsp+40h] [rbp-128h] BYREF
  void **v53; // [rsp+48h] [rbp-120h] BYREF
  __int64 v54; // [rsp+50h] [rbp-118h] BYREF
  __int64 v55; // [rsp+58h] [rbp-110h] BYREF
  __int64 v56; // [rsp+60h] [rbp-108h] BYREF
  _BYTE *v57; // [rsp+68h] [rbp-100h] BYREF
  __int64 v58; // [rsp+70h] [rbp-F8h] BYREF
  RepoMan::MSIXFormat *v59; // [rsp+78h] [rbp-F0h]
  struct IStream **v60; // [rsp+80h] [rbp-E8h]
  _BYTE v61[48]; // [rsp+88h] [rbp-E0h] BYREF
  void *Block[2]; // [rsp+B8h] [rbp-B0h] BYREF
  __m128i v63; // [rsp+C8h] [rbp-A0h]
  __int128 v64; // [rsp+D8h] [rbp-90h] BYREF
  __m128i v65; // [rsp+E8h] [rbp-80h]
  _BYTE v66[40]; // [rsp+108h] [rbp-60h] BYREF
  __int64 v67; // [rsp+130h] [rbp-38h]

  v60 = a3;
  v59 = this;
  RepoMan::Tracer::Tracer(v66, 1, "MSIXFormat.GetFileStream");
  try
  {
    if ( !a2 || !a3 || *a3 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        753,
        (unsigned int)"src\\repoman\\src\\inc\\PackageFormat.hpp",
        (unsigned int)"invalid parameter",
        -2147024809,
        8);
    if ( !*((_QWORD *)this + 14) )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        754,
        (unsigned int)"src\\repoman\\src\\inc\\PackageFormat.hpp",
        (unsigned int)"Missing package reader.",
        -2147418113,
        8);
    RepoMan::MSIXFormat::GetMSIXSDKLogsOnDemandForScope(v61);
    RepoMan::ComPtr<IAppxPackageReader>::As<IAppxPackageReaderUtf8>((_QWORD *)this + 14, &v58);
    v6 = (_QWORD *)((char *)this + 120);
    if ( *((_QWORD *)this + 15) == *((_QWORD *)this + 16) )
    {
      v52 = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 14) + 48LL))(
             *((_QWORD *)this + 14),
             &v52);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v7, 761, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v8);
      v50 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 32LL))(v52, &v50);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v9, 763, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v10);
      v12 = -1;
      while ( v50 )
      {
        v54 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 24LL))(v52, &v54);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v13, 767, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v14);
        RepoMan::ComPtr<IAppxFile>::As<IAppxFileUtf8>(&v54, &v51);
        v57 = 0;
        v15 = (*(__int64 (__fastcall **)(unsigned __int64, _BYTE **))(*(_QWORD *)v51 + 32LL))(v51, &v57);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v15, 770, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v16);
        v53 = (void **)&v57;
        Z::Z((__int64)&v64, &v53);
        *(_OWORD *)Block = 0;
        v63 = 0;
        v17 = -1;
        do
          ++v17;
        while ( v57[v17] );
        std::string::_Construct<1,char const *>(Block, v57, v17);
        v18 = (_OWORD *)*((_QWORD *)this + 16);
        if ( v18 == *((_OWORD **)this + 17) )
        {
          std::vector<std::string>::_Emplace_reallocate<std::string>((char *)this + 120, v18, Block);
          v19 = v63.m128i_u64[1];
        }
        else
        {
          *v18 = *(_OWORD *)Block;
          v18[1] = v63;
          v19 = 15;
          LOBYTE(Block[0]) = 0;
          *((_QWORD *)this + 16) += 32LL;
        }
        if ( v19 > 0xF )
        {
          v20 = Block[0];
          if ( v19 + 1 >= 0x1000 )
          {
            v20 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v20);
        }
        v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 40LL))(v52, &v50);
        RepoMan::RaiseExceptionIfFailed((RepoMan *)v21, 776, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v22);
        RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)&v64);
        v23 = v51;
        if ( v51 )
        {
          v51 = 0;
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
      }
      LOBYTE(v11) = 0;
      std::_Sort_unchecked<std::string *,std::less<void>>(
        *v6,
        *((_QWORD *)v59 + 16),
        (__int64)(*((_QWORD *)v59 + 16) - *v6) >> 5,
        v11);
      v25 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
    }
    else
    {
      v12 = -1;
    }
    v56 = 0;
    v26 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoFile *, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v56);
    RepoMan::RaiseExceptionIfFailed(v26, 782, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v27);
    v28 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 24LL))(v56);
    v29 = v28;
    if ( *v28 == 92 || *v28 == 47 )
      v29 = v28 + 1;
    *(_OWORD *)Block = 0;
    v63 = 0;
    v30 = -1;
    do
      ++v30;
    while ( v29[v30] );
    std::string::_Construct<1,char const *>(Block, v29, v30);
    RepoMan::Logger::CreateValue((unsigned int)&v51, 1, 9, (unsigned int)Block, 0);
    (*(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v67 + 48LL))(v67, &v51);
    v31 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v31 + 8LL))(v31);
    }
    std::string::_Tidy_deallocate(Block);
    *(_OWORD *)Block = 0;
    v63 = 0;
    do
      ++v12;
    while ( v29[v12] );
    std::string::_Construct<1,char const *>(Block, v29, v12);
    v64 = *(_OWORD *)Block;
    v32 = v63.m128i_i64[0];
    v65 = v63;
    v53 = Block;
    *(_OWORD *)Block = 0;
    v63 = 0u;
    v33 = &v64;
    v34 = (char *)v64;
    v51 = _mm_srli_si128(v65, 8).m128i_u64[0];
    if ( v51 > 0xF )
      v33 = (__int128 *)v64;
    v35 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v32 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    if ( v32 > 0xF )
    {
      if ( (v32 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
      {
        v35 = v32 | 0xF;
        if ( (v32 | 0xF) < 0x16 )
          v35 = 22;
      }
      v36 = v35 + 1;
      if ( v35 == -1 )
      {
        v37 = 0;
      }
      else if ( v36 < 0x1000 )
      {
        v37 = malloc(v36);
        if ( !v37 )
          std::_Xbad_alloc();
      }
      else
      {
        v37 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v36);
      }
      Block[0] = v37;
      v63.m128i_i64[0] = v32;
      v63.m128i_i64[1] = v35;
      memmove(v37, v33, v32 + 1);
    }
    else
    {
      v63.m128i_i64[0] = v32;
      v63.m128i_i64[1] = 15;
      *(_OWORD *)Block = *v33;
    }
    v38 = v59;
    ___find_if_V___Vector_iterator_V___Vector_val_U___Simple_types_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___std___std__V_lambda_2___2__GetFileStream_MSIXFormat_RepoMan__UEAAJPEAUIRepoFile__PEAPEAUIStream___Z__std__YA_AV___Vector_iterator_V___Vector_val_U___Simple_types_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___std___0_V10_V10_V_lambda_2___2__GetFileStream_MSIXFormat_RepoMan__UEAAJPEAUIRepoFile__PEAPEAUIStream___Z__Z(
      &v53,
      *v6,
      *((_QWORD *)v59 + 16),
      Block);
    v39 = v53;
    if ( v53 == *((void ***)v38 + 16) )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        806,
        (unsigned int)"src\\repoman\\src\\inc\\PackageFormat.hpp",
        (unsigned int)"file not in package payload.",
        -1941503375,
        8);
    v55 = 0;
    if ( (unsigned __int64)v53[3] > 0xF )
      v39 = *v53;
    v40 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, void *, __int64 *))(*(_QWORD *)v58 + 24LL))(
                       v58,
                       v39,
                       &v55);
    RepoMan::RaiseExceptionIfFailed(v40, 809, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v41);
    v42 = (*(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v55 + 56LL))(v55, v60);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v42, 810, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v43);
    v44 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    if ( v51 > 0xF )
    {
      v45 = v34;
      if ( v51 + 1 >= 0x1000 )
      {
        v34 = (char *)*((_QWORD *)v34 - 1);
        if ( (unsigned __int64)(v45 - v34 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v34);
    }
    v46 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v61);
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v66);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\inc\\PackageFormat.hpp", (const char *)0x32E, v48);
  }
  return result;
}

```

## disassembly

```asm
0x18000d990  mov     r11, rsp
0x18000d993  mov     [r11+20h], rbx
0x18000d997  push    rsi
0x18000d998  push    rdi
0x18000d999  push    r12
0x18000d99b  push    r13
0x18000d99d  push    r14
0x18000d99f  sub     rsp, 140h
0x18000d9a6  mov     rax, cs:__security_cookie
0x18000d9ad  xor     rax, rsp
0x18000d9b0  mov     [rsp+168h+var_30], rax
0x18000d9b8  mov     rbx, r8
0x18000d9bb  mov     [rsp+168h+var_E8], rbx
0x18000d9c3  mov     rdi, rdx
0x18000d9c6  mov     r14, rcx
0x18000d9c9  mov     [rsp+168h+var_F0], rcx
0x18000d9ce  xor     r13d, r13d
0x18000d9d1  lea     r8, aMsixformatGetf_0; "MSIXFormat.GetFileStream"
0x18000d9d8  lea     edx, [r13+1]
0x18000d9dc  lea     rcx, [r11-60h]
0x18000d9e0  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x18000d9e5  nop
0x18000d9e6  test    rdi, rdi
0x18000d9e9  jz      loc_18000E0CF
0x18000d9ef  test    rbx, rbx
0x18000d9f2  jz      loc_18000E0CF
0x18000d9f8  cmp     [rbx], r13
0x18000d9fb  jnz     loc_18000E0CF
0x18000da01  lea     rbx, [r14+70h]
0x18000da05  cmp     [rbx], r13
0x18000da08  jz      loc_18000E079
0x18000da0e  lea     rcx, [rsp+168h+var_E0]
0x18000da16  call    ?GetMSIXSDKLogsOnDemandForScope@MSIXFormat@RepoMan@@CA?AVScopeGuard@Meta@2@XZ; RepoMan::MSIXFormat::GetMSIXSDKLogsOnDemandForScope(void)
0x18000da1b  nop
0x18000da1c  lea     rdx, [rsp+168h+var_F8]
0x18000da21  mov     rcx, rbx
0x18000da24  call    ??$As@UIAppxPackageReaderUtf8@@@?$ComPtr@UIAppxPackageReader@@@RepoMan@@QEBA?AV?$ComPtr@UIAppxPackageReaderUtf8@@@1@W4AsPolicy@1@@Z; RepoMan::ComPtr<IAppxPackageReader>::As<IAppxPackageReaderUtf8>(RepoMan::AsPolicy)
0x18000da29  nop
0x18000da2a  lea     r12, [r14+78h]
0x18000da2e  mov     rax, [r12+8]
0x18000da33  cmp     [r12], rax
0x18000da37  jnz     loc_18000DCB2
0x18000da3d  mov     [rsp+168h+var_128], r13
0x18000da42  mov     rcx, [rbx]
0x18000da45  mov     rax, [rcx]
0x18000da48  lea     rdx, [rsp+168h+var_128]
0x18000da4d  mov     rax, [rax+30h]
0x18000da51  call    cs:__guard_dispatch_icall_fptr
0x18000da57  lea     rbx, aSrcRepomanSrcI_7; "src\\repoman\\src\\inc\\PackageFormat.h"...
0x18000da5e  mov     r8, rbx; int
0x18000da61  mov     edx, 2F9h; int
0x18000da66  mov     ecx, eax; this
0x18000da68  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000da6d  mov     [rsp+168h+var_138], r13d
0x18000da72  mov     rcx, [rsp+168h+var_128]
0x18000da77  mov     rax, [rcx]
0x18000da7a  lea     rdx, [rsp+168h+var_138]
0x18000da7f  mov     rax, [rax+20h]
0x18000da83  call    cs:__guard_dispatch_icall_fptr
0x18000da89  mov     r8, rbx; int
0x18000da8c  mov     edx, 2FBh; int
0x18000da91  mov     ecx, eax; this
0x18000da93  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000da98  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000da9c  cmp     [rsp+168h+var_138], r13d
0x18000daa1  jz      loc_18000DC70
0x18000daa7  mov     [rsp+168h+var_118], r13
0x18000daac  mov     rcx, [rsp+168h+var_128]
0x18000dab1  mov     rax, [rcx]
0x18000dab4  lea     rdx, [rsp+168h+var_118]
0x18000dab9  mov     rax, [rax+18h]
0x18000dabd  call    cs:__guard_dispatch_icall_fptr
0x18000dac3  mov     r8, rbx; int
0x18000dac6  mov     edx, 2FFh; int
0x18000dacb  mov     ecx, eax; this
0x18000dacd  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000dad2  lea     rdx, [rsp+168h+var_130]
0x18000dad7  lea     rcx, [rsp+168h+var_118]
0x18000dadc  call    ??$As@UIAppxFileUtf8@@@?$ComPtr@UIAppxFile@@@RepoMan@@QEBA?AV?$ComPtr@UIAppxFileUtf8@@@1@W4AsPolicy@1@@Z; RepoMan::ComPtr<IAppxFile>::As<IAppxFileUtf8>(RepoMan::AsPolicy)
0x18000dae1  nop
0x18000dae2  mov     [rsp+168h+var_100], r13
0x18000dae7  mov     rcx, [rsp+168h+var_130]
0x18000daec  mov     rax, [rcx]
0x18000daef  lea     rdx, [rsp+168h+var_100]
0x18000daf4  mov     rax, [rax+20h]
0x18000daf8  call    cs:__guard_dispatch_icall_fptr
0x18000dafe  mov     ecx, eax; this
0x18000db00  mov     r8, rbx; int
0x18000db03  mov     edx, 302h; int
0x18000db08  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000db0d  lea     rax, [rsp+168h+var_100]
0x18000db12  mov     [rsp+168h+var_120], rax
0x18000db17  lea     rdx, [rsp+168h+var_120]
0x18000db1c  lea     rcx, [rsp+168h+var_90]
0x18000db24  call    ??$?0V_lambda_1_@?O@??GetFileStream@MSIXFormat@RepoMan@@UEAAJPEAUIRepoFile@@PEAPEAUIStream@@@Z@@ScopeGuard@Meta@RepoMan@@QEAA@$$QEAV_lambda_1_@?O@??GetFileStream@MSIXFormat@2@UEAAJPEAUIRepoFile@@PEAPEAUIStream@@@Z@W4Policy@012@@Z; RepoMan::Meta::ScopeGuard::ScopeGuard(`RepoMan::MSIXFormat::GetFileStream(IRepoFile *,IStream * *)'::`14'::_lambda_1_ &&,RepoMan::Meta::ScopeGuard::Policy)
0x18000db29  nop
0x18000db2a  xorps   xmm0, xmm0
0x18000db2d  movups  xmmword ptr [rsp+168h+Block], xmm0
0x18000db35  xorps   xmm1, xmm1
0x18000db38  movdqu  [rsp+168h+var_A0], xmm1
0x18000db41  mov     rdx, [rsp+168h+var_100]
0x18000db46  mov     r8, rsi
0x18000db49  inc     r8
0x18000db4c  cmp     [rdx+r8], r13b
0x18000db50  jnz     short loc_18000DB49
0x18000db52  lea     rcx, [rsp+168h+Block]
0x18000db5a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000db5f  nop
0x18000db60  mov     rdx, [r12+8]
0x18000db65  cmp     rdx, [r12+10h]
0x18000db6a  jz      short loc_18000DB98
0x18000db6c  movups  xmm0, xmmword ptr [rsp+168h+Block]
0x18000db74  movups  xmmword ptr [rdx], xmm0
0x18000db77  movups  xmm1, [rsp+168h+var_A0]
0x18000db7f  movups  xmmword ptr [rdx+10h], xmm1
0x18000db83  mov     eax, 0Fh
0x18000db88  mov     byte ptr [rsp+168h+Block], r13b
0x18000db90  add     qword ptr [r12+8], 20h ; ' '
0x18000db96  jmp     short loc_18000DBB0
0x18000db98  lea     r8, [rsp+168h+Block]
0x18000dba0  mov     rcx, r12
0x18000dba3  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x18000dba8  mov     rax, qword ptr [rsp+168h+var_A0+8]
0x18000dbb0  cmp     rax, 0Fh
0x18000dbb4  jbe     short loc_18000DBF9
0x18000dbb6  mov     rcx, [rsp+168h+Block]; Block
0x18000dbbe  mov     rdx, rcx
0x18000dbc1  inc     rax
0x18000dbc4  cmp     rax, 1000h
0x18000dbca  jb      short loc_18000DBF3
0x18000dbcc  mov     rcx, [rcx-8]
0x18000dbd0  sub     rdx, rcx
0x18000dbd3  lea     rax, [rdx-8]
0x18000dbd7  cmp     rax, 1Fh
0x18000dbdb  jbe     short loc_18000DBF3
0x18000dbdd  mov     [rsp+168h+Reserved], r13; Reserved
0x18000dbe2  xor     r9d, r9d; LineNo
0x18000dbe5  xor     r8d, r8d; FileName
0x18000dbe8  xor     edx, edx; FunctionName
0x18000dbea  xor     ecx, ecx; Expression
0x18000dbec  call    cs:__imp__invoke_watson
0x18000dbf3  call    cs:__imp_free
0x18000dbf9  mov     rcx, [rsp+168h+var_128]
0x18000dbfe  mov     rax, [rcx]
0x18000dc01  lea     rdx, [rsp+168h+var_138]
0x18000dc06  mov     rax, [rax+28h]
0x18000dc0a  call    cs:__guard_dispatch_icall_fptr
0x18000dc10  mov     r8, rbx; int
0x18000dc13  mov     edx, 308h; int
0x18000dc18  mov     ecx, eax; this
0x18000dc1a  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000dc1f  nop
0x18000dc20  lea     rcx, [rsp+168h+var_90]; this
0x18000dc28  call    ??1ScopeGuard@Meta@RepoMan@@QEAA@XZ; RepoMan::Meta::ScopeGuard::~ScopeGuard(void)
0x18000dc2d  nop
0x18000dc2e  mov     rcx, [rsp+168h+var_130]
0x18000dc33  test    rcx, rcx
0x18000dc36  jz      short loc_18000DC4B
0x18000dc38  mov     [rsp+168h+var_130], r13
0x18000dc3d  mov     rax, [rcx]
0x18000dc40  mov     rax, [rax+10h]
0x18000dc44  call    cs:__guard_dispatch_icall_fptr
0x18000dc4a  nop
0x18000dc4b  mov     rcx, [rsp+168h+var_118]
0x18000dc50  test    rcx, rcx
0x18000dc53  jz      loc_18000DA9C
0x18000dc59  mov     [rsp+168h+var_118], r13
0x18000dc5e  mov     rax, [rcx]
0x18000dc61  mov     rax, [rax+10h]
0x18000dc65  call    cs:__guard_dispatch_icall_fptr
0x18000dc6b  jmp     loc_18000DA9C
0x18000dc70  mov     rdx, [rsp+168h+var_F0]
0x18000dc75  mov     rdx, [rdx+80h]
0x18000dc7c  mov     r8, rdx
0x18000dc7f  sub     r8, [r12]
0x18000dc83  sar     r8, 5
0x18000dc87  mov     r9b, r13b
0x18000dc8a  mov     rcx, [r12]
0x18000dc8e  call    ??$_Sort_unchecked@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::string *,std::less<void>>(std::string *,std::string *,__int64,std::less<void>)
0x18000dc93  nop
0x18000dc94  mov     rcx, [rsp+168h+var_128]
0x18000dc99  test    rcx, rcx
0x18000dc9c  jz      short loc_18000DCBD
0x18000dc9e  mov     [rsp+168h+var_128], r13
0x18000dca3  mov     rax, [rcx]
0x18000dca6  mov     rax, [rax+10h]
0x18000dcaa  call    cs:__guard_dispatch_icall_fptr
0x18000dcb0  jmp     short loc_18000DCBD
0x18000dcb2  lea     rbx, aSrcRepomanSrcI_7; "src\\repoman\\src\\inc\\PackageFormat.h"...
0x18000dcb9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000dcbd  mov     [rsp+168h+var_108], r13
0x18000dcc2  mov     rax, [rdi]
0x18000dcc5  lea     rdx, [rsp+168h+var_108]
0x18000dcca  mov     rcx, rdi
0x18000dccd  mov     rax, [rax+30h]
0x18000dcd1  call    cs:__guard_dispatch_icall_fptr
0x18000dcd7  mov     ecx, eax; this
0x18000dcd9  mov     r8, rbx; int
0x18000dcdc  mov     edx, 30Eh; int
0x18000dce1  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000dce6  mov     rcx, [rsp+168h+var_108]
0x18000dceb  mov     rax, [rcx]
0x18000dcee  mov     rax, [rax+18h]
0x18000dcf2  call    cs:__guard_dispatch_icall_fptr
0x18000dcf8  mov     rdi, rax
0x18000dcfb  cmp     byte ptr [rax], 5Ch ; '\'
0x18000dcfe  jz      short loc_18000DD05
0x18000dd00  cmp     byte ptr [rax], 2Fh ; '/'
0x18000dd03  jnz     short loc_18000DD08
0x18000dd05  inc     rdi
0x18000dd08  xorps   xmm0, xmm0
0x18000dd0b  movups  xmmword ptr [rsp+168h+Block], xmm0
0x18000dd13  xorps   xmm1, xmm1
0x18000dd16  movdqu  [rsp+168h+var_A0], xmm1
0x18000dd1f  mov     r8, rsi
0x18000dd22  inc     r8
0x18000dd25  cmp     [rdi+r8], r13b
0x18000dd29  jnz     short loc_18000DD22
0x18000dd2b  mov     rdx, rdi
0x18000dd2e  lea     rcx, [rsp+168h+Block]
0x18000dd36  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000dd3b  nop
0x18000dd3c  mov     [rsp+168h+Reserved], r13
0x18000dd41  lea     r9, [rsp+168h+Block]
0x18000dd49  mov     edx, 1
0x18000dd4e  lea     r8d, [rdx+8]
0x18000dd52  lea     rcx, [rsp+168h+var_130]
0x18000dd57  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18000dd5c  mov     rcx, [rsp+168h+var_38]
0x18000dd64  mov     rax, [rcx]
0x18000dd67  lea     rdx, [rsp+168h+var_130]
0x18000dd6c  mov     rax, [rax+30h]
0x18000dd70  call    cs:__guard_dispatch_icall_fptr
0x18000dd76  nop
0x18000dd77  mov     rcx, [rsp+168h+var_130]
0x18000dd7c  test    rcx, rcx
0x18000dd7f  jz      short loc_18000DD94
0x18000dd81  mov     [rsp+168h+var_130], r13
0x18000dd86  mov     rax, [rcx]
0x18000dd89  mov     rax, [rax+8]
0x18000dd8d  call    cs:__guard_dispatch_icall_fptr
0x18000dd93  nop
0x18000dd94  lea     rcx, [rsp+168h+Block]
0x18000dd9c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000dda1  xorps   xmm0, xmm0
0x18000dda4  movups  xmmword ptr [rsp+168h+Block], xmm0
0x18000ddac  xorps   xmm1, xmm1
0x18000ddaf  movdqu  [rsp+168h+var_A0], xmm1
0x18000ddb8  inc     rsi
0x18000ddbb  cmp     [rdi+rsi], r13b
0x18000ddbf  jnz     short loc_18000DDB8
0x18000ddc1  mov     r8, rsi
0x18000ddc4  mov     rdx, rdi
0x18000ddc7  lea     rcx, [rsp+168h+Block]
0x18000ddcf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000ddd4  nop
0x18000ddd5  movups  xmm1, xmmword ptr [rsp+168h+Block]
0x18000dddd  movups  [rsp+168h+var_90], xmm1
0x18000dde5  movups  xmm2, [rsp+168h+var_A0]
0x18000dded  movups  [rsp+168h+var_80], xmm2
0x18000ddf5  lea     rax, [rsp+168h+Block]
0x18000ddfd  mov     [rsp+168h+var_120], rax
0x18000de02  xorps   xmm0, xmm0
0x18000de05  movups  xmmword ptr [rsp+168h+Block], xmm0
0x18000de0d  mov     qword ptr [rsp+168h+var_A0], r13
0x18000de15  mov     qword ptr [rsp+168h+var_A0+8], r13
0x18000de1d  lea     r13, [rsp+168h+var_90]
0x18000de25  movq    r14, xmm1
0x18000de2a  movdqa  xmm0, xmm2
0x18000de2e  psrldq  xmm0, 8
0x18000de33  movq    rax, xmm0
0x18000de38  mov     [rsp+168h+var_130], rax
0x18000de3d  cmp     rax, 0Fh
0x18000de41  cmova   r13, r14
0x18000de45  mov     rdi, 7FFFFFFFFFFFFFFFh
0x18000de4f  movq    rsi, xmm2
0x18000de54  cmp     rsi, rdi
0x18000de57  ja      loc_18000E0A0
0x18000de5d  cmp     rsi, 0Fh
0x18000de61  ja      short loc_18000DE87
0x18000de63  mov     qword ptr [rsp+168h+var_A0], rsi
0x18000de6b  mov     qword ptr [rsp+168h+var_A0+8], 0Fh
0x18000de77  movups  xmm0, xmmword ptr [r13+0]
0x18000de7c  movdqu  xmmword ptr [rsp+168h+Block], xmm0
0x18000de85  jmp     short loc_18000DED5
0x18000de87  mov     rax, rsi
0x18000de8a  or      rax, 0Fh
0x18000de8e  cmp     rax, rdi
0x18000de91  ja      short loc_18000DEA2
0x18000de93  mov     rdi, rax
0x18000de96  mov     ecx, 16h
0x18000de9b  cmp     rax, rcx
0x18000de9e  cmovb   rdi, rcx
0x18000dea2  lea     rcx, [rdi+1]; Size
0x18000dea6  test    rcx, rcx
0x18000dea9  jnz     short loc_18000DF0B
0x18000deab  xor     eax, eax
0x18000dead  mov     [rsp+168h+Block], rax
0x18000deb5  mov     qword ptr [rsp+168h+var_A0], rsi
0x18000debd  mov     qword ptr [rsp+168h+var_A0+8], rdi
  ... truncated ...
```
