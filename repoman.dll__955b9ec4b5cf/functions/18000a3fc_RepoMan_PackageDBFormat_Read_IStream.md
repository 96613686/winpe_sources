# RepoMan::PackageDBFormat::Read(IStream *)

- ea: `0x18000a3fc`
- end: `0x18000ac0e`
- name: `?Read@PackageDBFormat@RepoMan@@QEAAXPEAUIStream@@@Z`
- size: `2066`
- prototype: `void __fastcall(RepoMan::PackageDBFormat *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x18000ac38`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180009fc0`
- `0x18000a3fc`
- `0x1800136dc`
- `0x180013b14`
- `0x180015674`
- `0x18001580c`
- `0x180015890`
- `0x1800158fc`
- `0x18001c48c`
- `0x1800248a4`
- `0x180024d50`
- `0x180024d6c`
- `0x180024de8`
- `0x180025f18`
- `0x18002c00c`
- `0x18002e6b8`
- `0x180038ac8`
- `0x18003b998`
- `0x18018aed8`
- `0x180198f88`
- `0x180199088`
- `0x18019a840`
- `0x18019f7a0`
- `0x18019f800`
- `0x1801a02e0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000aa31`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000aae9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000aa31`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000aae9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000aa2a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000aadf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000aa2a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000aadf`

## string_xrefs

- `0x18000a434`: `PackageDBFormat.Read`
- `0x18000ab5b`: `Entire object wasn't read!`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall RepoMan::PackageDBFormat::Read(RepoMan::PackageDBFormat *this, struct IStream *a2)
{
  unsigned int v4; // eax
  const char *v5; // r9
  unsigned int v6; // eax
  const char *v7; // r9
  char *v8; // r15
  __int64 *v9; // rdi
  unsigned int v10; // eax
  const char *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r13
  __int64 v14; // rdx
  char *v15; // rdi
  size_t v16; // rdi
  unsigned __int8 *v17; // r12
  __int64 v18; // rbx
  unsigned __int8 *v19; // r15
  unsigned __int16 v20; // di
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  size_t v24; // r8
  bool v25; // di
  unsigned int v26; // eax
  const char *v27; // r9
  __int64 *v28; // rdi
  __int64 v29; // rdx
  unsigned int v30; // eax
  const char *v31; // r9
  _BYTE *v32; // rcx
  _BYTE *v33; // rax
  unsigned int v34; // eax
  const char *v35; // r9
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int *v42; // rdi
  char *v43; // r14
  __int64 v44; // rcx
  void *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  char *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B8h] BYREF
  void *v57[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+60h] [rbp-A0h]
  __int128 v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h]
  _QWORD v61[17]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v62[13]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v63[4]; // [rsp+170h] [rbp+70h] BYREF
  void *Block[2]; // [rsp+190h] [rbp+90h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]
  _BYTE v66[40]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v67; // [rsp+1D8h] [rbp+D8h]

  RepoMan::Tracer::Tracer(v66, 1, "PackageDBFormat.Read");
  v4 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v4, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v5);
  v63[0] = (__int64)a2;
  v6 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(
         a2,
         *((_QWORD *)this + 9),
         0,
         0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v6, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v7);
  v8 = (char *)this + 48;
  v9 = RepoMan::StreamBase<>::Read((__int64 *)v57, (__int64)a2, *((_QWORD *)this + 7) - *((_QWORD *)this + 6));
  if ( (__int64 *)((char *)this + 48) != v9 )
  {
    std::vector<unsigned char>::_Tidy((char *)this + 48);
    *(_QWORD *)v8 = *v9;
    *((_QWORD *)this + 7) = v9[1];
    *((_QWORD *)this + 8) = v9[2];
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
  }
  std::vector<unsigned char>::_Tidy(v57);
  LODWORD(v53) = 0;
  v10 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, __int64 *))a2->lpVtbl->Read)(
          a2,
          (char *)this + 40,
          2,
          &v53);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v10, 218, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v11);
  if ( !(_DWORD)v53 )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      219,
      (unsigned int)"src\\repoman\\src\\inc\\StreamBase.hpp",
      (unsigned int)"Entire object wasn't read!",
      -1941503469,
      8);
  ___for_each__01V_lambda_1___1__Read___SerializableObject_UFieldNBytes_Meta_RepoMan__UField2Bytes_23_UField4Bytes_23_U423_U523_U523_U523_U423_U423_U523_U523_U523__Meta_RepoMan__QEAAXPEAUIStream___Z_AEAPEAU6____TypeList_UFieldNBytes_Meta_RepoMan__UField2Bytes_23_UField4Bytes_23_U423_U523_U523_U523_U423_U423_U523_U523_U523__Meta_RepoMan__QEAAXAEBV_lambda_1___1__Read___SerializableObject_UFieldNBytes_Meta_RepoMan__UField2Bytes_23_UField4Bytes_23_U423_U523_U523_U523_U423_U423_U523_U523_U523__12_QEAAXPEAUIStream___Z_AEAPEAU6__Z(
    (__int64)this,
    v12,
    v63);
  *(_OWORD *)v57 = 0;
  v13 = 0;
  v58 = 0;
  v14 = *((_QWORD *)this + 7) - *(_QWORD *)v8;
  v15 = 0;
  v63[0] = 0;
  if ( v14 )
  {
    std::vector<unsigned char>::_Buy_nonzero(v57, v14);
    v16 = *((_QWORD *)this + 7) - *(_QWORD *)v8;
    v17 = (unsigned __int8 *)v57[0];
    memmove(v57[0], *(const void **)v8, v16);
    v15 = (char *)&v17[v16];
    v63[0] = (__int64)v15;
    v57[1] = v15;
    v13 = v58;
  }
  else
  {
    v17 = (unsigned __int8 *)v57[0];
  }
  std::ostringstream::ostringstream(v61);
  if ( v17 != (unsigned __int8 *)v15 )
  {
    v18 = v63[0];
    v19 = v17;
    do
    {
      v20 = *v19;
      *(_DWORD *)((char *)&v61[3] + *(int *)(v61[0] + 4LL)) = *(_DWORD *)((_BYTE *)&v61[3] + *(int *)(v61[0] + 4LL))
                                                            & 0xFFFFF1FF
                                                            | 0x800;
      *((_BYTE *)&v61[11] + *(int *)(v61[0] + 4LL)) = 48;
      v21 = std::setw(v63, 2);
      (*(void (__fastcall **)(char *, _QWORD))v21)((char *)v61 + *(int *)(v61[0] + 4LL), *(_QWORD *)(v21 + 8));
      v22 = std::ostream::operator<<(v61, v20);
      std::operator<<<std::char_traits<char>>(v22, (__int64)" ");
      ++v19;
    }
    while ( v19 != (unsigned __int8 *)v18 );
    v8 = (char *)this + 48;
  }
  v23 = RepoMan::PackageDBFormat::PREAMBLE(v63);
  v24 = *(_QWORD *)(v23 + 8) - *(_QWORD *)v23;
  v25 = v24 == *((_QWORD *)v8 + 1) - *(_QWORD *)v8 && memcmp(*(const void **)v23, *(const void **)v8, v24) == 0;
  std::vector<unsigned char>::_Tidy(v63);
  if ( !v25 )
  {
    v50 = std::ostringstream::str(v61, Block);
    v51 = std::operator+<char>(v63, "unexpected preamble : ", v50);
    v52 = std::string::c_str(v51);
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      138,
      (unsigned int)"src\\repoman\\src\\inc\\PackageDBFormat.hpp",
      v52,
      -1941503423,
      8);
  }
  if ( *((unsigned __int16 *)this + 20) != *((_QWORD *)v8 + 1) - *(_QWORD *)v8 + 36LL )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      139,
      (unsigned int)"src\\repoman\\src\\inc\\PackageDBFormat.hpp",
      (unsigned int)"unexpected header size",
      -1941503423,
      8);
  if ( *((_BYTE *)this + 12) > 1u )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      80,
      (unsigned int)"src\\repoman\\src\\inc\\PackageDBFormat.hpp",
      (unsigned int)"unknown or unsupported hash algorithm id.",
      -1941503422,
      8);
  if ( `RepoMan::PackageDBFormat::HashSize'::`2'::hashSizes[*((unsigned __int8 *)this + 12)] != *((unsigned __int16 *)this
                                                                                                + 8) )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      140,
      (unsigned int)"src\\repoman\\src\\inc\\PackageDBFormat.hpp",
      (unsigned int)"invalid hash digest size",
      -1941503421,
      8);
  v26 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(
          a2,
          *((unsigned int *)this + 5),
          0,
          0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v26, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v27);
  v28 = RepoMan::StreamBase<>::Read(v63, (__int64)a2, *((unsigned __int16 *)this + 8));
  if ( (__int64 *)((char *)this + 192) != v28 )
  {
    std::vector<unsigned char>::_Tidy((char *)this + 192);
    *((_QWORD *)this + 24) = *v28;
    *((_QWORD *)this + 25) = v28[1];
    *((_QWORD *)this + 26) = v28[2];
    *v28 = 0;
    v28[1] = 0;
    v28[2] = 0;
  }
  std::vector<unsigned char>::_Tidy(v63);
  v29 = *((unsigned int *)this + 9);
  *((_QWORD *)this + 19) = v29;
  *((_QWORD *)this + 20) = v29 + *((unsigned __int16 *)this + 16);
  v30 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, v29, 0, 0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v30, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v31);
  *((_QWORD *)this + 17) = 0;
  v32 = (char *)this + 120;
  if ( *((_QWORD *)this + 18) > 0xFu )
    v32 = (_BYTE *)*((_QWORD *)this + 15);
  *v32 = 0;
  *((_QWORD *)this + 13) = 0;
  v33 = (char *)this + 88;
  if ( *((_QWORD *)this + 14) > 0xFu )
    v33 = (_BYTE *)*((_QWORD *)this + 11);
  *v33 = 0;
  v63[0] = (__int64)a2;
  v34 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(
          a2,
          *((_QWORD *)this + 19),
          0,
          0);
  RepoMan::RaiseExceptionIfFailed((RepoMan *)v34, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v35);
  `RepoMan::Meta::SerializableObject<RepoMan::Meta::FieldString,RepoMan::Meta::FieldString>::Read'::`2'::_lambda_1_::operator()<RepoMan::Meta::FieldString>(
    v36,
    (_QWORD *)this + 15,
    v37,
    v63);
  `RepoMan::Meta::SerializableObject<RepoMan::Meta::FieldString,RepoMan::Meta::FieldString>::Read'::`2'::_lambda_1_::operator()<RepoMan::Meta::FieldString>(
    v38,
    (_QWORD *)this + 11,
    v39,
    v63);
  RepoMan::Logger::CreateValue((unsigned int)v63, 1, 1, (_DWORD)this + 120, 0);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 48LL))(v67, v63);
  RepoMan::Logger::CreateValue((unsigned int)&v53, 1, 2, (_DWORD)this + 88, 0);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 48LL))(v67, &v53);
  v40 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  }
  v41 = v63[0];
  if ( v63[0] )
  {
    v63[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
  }
  v63[0] = (__int64)a2;
  if ( a2 )
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  RepoMan::ComPtr<IStream>::Make<RepoMan::SubStream,unsigned int &,unsigned int &,RepoMan::ComPtr<IStream>>(
    &v56,
    (char *)this + 28,
    (char *)this + 24,
    v63);
  if ( a2 )
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->Release)(a2);
  v42 = (unsigned int *)((char *)this + 8);
  RepoMan::ComPtr<IStream>::Make<RepoMan::InflateStream,RepoMan::ComPtr<IStream> &,unsigned int &>(
    &v55,
    &v56,
    (char *)this + 8);
  RepoMan::ComPtr<IStream>::Make<RepoMan::ValidatedStream,RepoMan::ComPtr<IStream> &,std::vector<unsigned char>>(
    &v54,
    &v55,
    (char *)this + 192);
  RepoMan::StreamBase<>::Read((__int64 *)&v59, v54, *((unsigned int *)this + 2));
  v43 = (char *)this + 168;
  if ( v43 != (char *)&v59 )
  {
    std::vector<unsigned char>::_Tidy(v43);
    *(_OWORD *)v43 = v59;
    *((_QWORD *)v43 + 2) = v60;
    v59 = 0;
    v60 = 0;
  }
  std::vector<unsigned char>::_Tidy(&v59);
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(Block[0]) = *(_DWORD *)"bytes";
  WORD2(Block[0]) = (unsigned __int8)aBytes[4];
  RepoMan::Logger::CreateValue((unsigned int)v63, 3, 11, (unsigned int)Block, *v42);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 48LL))(v67, v63);
  v44 = v63[0];
  if ( v63[0] )
  {
    v63[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
  }
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v45 = Block[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v45 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v45 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v45);
  }
  v46 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  std::ostringstream::~ostringstream(v62);
  v62[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v62);
  if ( v17 )
  {
    v49 = (char *)v17;
    if ( (unsigned __int64)(v13 - (_QWORD)v17) >= 0x1000 )
    {
      v17 = (unsigned __int8 *)*((_QWORD *)v17 - 1);
      if ( (unsigned __int64)(v49 - (char *)v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v66);
}

```

## disassembly

```asm
0x18000a3fc  mov     [rsp-8+arg_10], rbx
0x18000a401  push    rbp
0x18000a402  push    rsi
0x18000a403  push    rdi
0x18000a404  push    r12
0x18000a406  push    r13
0x18000a408  push    r14
0x18000a40a  push    r15
0x18000a40c  lea     rbp, [rsp-0F0h]
0x18000a414  sub     rsp, 1F0h
0x18000a41b  mov     rax, cs:__security_cookie
0x18000a422  xor     rax, rsp
0x18000a425  mov     [rbp+120h+var_40], rax
0x18000a42c  mov     rsi, rdx
0x18000a42f  mov     r14, rcx
0x18000a432  xor     ebx, ebx
0x18000a434  lea     r8, aPackagedbforma_0; "PackageDBFormat.Read"
0x18000a43b  lea     edx, [rbx+1]
0x18000a43e  lea     rcx, [rbp+120h+var_70]
0x18000a445  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x18000a44a  nop
0x18000a44b  mov     rax, [rsi]
0x18000a44e  xor     r9d, r9d
0x18000a451  xor     r8d, r8d
0x18000a454  mov     edx, ebx
0x18000a456  mov     rcx, rsi
0x18000a459  mov     rax, [rax+28h]
0x18000a45d  call    cs:__guard_dispatch_icall_fptr
0x18000a463  mov     ecx, eax; this
0x18000a465  lea     r12, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000a46c  mov     r8, r12; int
0x18000a46f  mov     edi, 169h
0x18000a474  mov     edx, edi; int
0x18000a476  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000a47b  mov     [rbp+120h+var_B0], rsi
0x18000a47f  mov     rax, [rsi]
0x18000a482  xor     r9d, r9d
0x18000a485  xor     r8d, r8d
0x18000a488  mov     rdx, [r14+48h]
0x18000a48c  mov     rcx, rsi
0x18000a48f  mov     rax, [rax+28h]
0x18000a493  call    cs:__guard_dispatch_icall_fptr
0x18000a499  mov     ecx, eax; this
0x18000a49b  mov     r8, r12; int
0x18000a49e  mov     edx, edi; int
0x18000a4a0  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000a4a5  nop
0x18000a4a6  lea     r15, [r14+30h]
0x18000a4aa  mov     r8, [r15+8]
0x18000a4ae  sub     r8, [r15]
0x18000a4b1  mov     rdx, rsi
0x18000a4b4  lea     rcx, [rsp+220h+var_1D0]
0x18000a4b9  call    ?Read@?$StreamBase@$$V@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@_K@Z; RepoMan::StreamBase<>::Read(IStream *,unsigned __int64)
0x18000a4be  mov     rdi, rax
0x18000a4c1  cmp     r15, rax
0x18000a4c4  jz      short loc_18000A4EF
0x18000a4c6  mov     rcx, r15
0x18000a4c9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a4ce  mov     rcx, [rdi]
0x18000a4d1  mov     [r15], rcx
0x18000a4d4  mov     rcx, [rdi+8]
0x18000a4d8  mov     [r15+8], rcx
0x18000a4dc  mov     rcx, [rdi+10h]
0x18000a4e0  mov     [r15+10h], rcx
0x18000a4e4  mov     [rdi], rbx
0x18000a4e7  mov     [rdi+8], rbx
0x18000a4eb  mov     [rdi+10h], rbx
0x18000a4ef  lea     rcx, [rsp+220h+var_1D0]
0x18000a4f4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a4f9  nop
0x18000a4fa  mov     dword ptr [rsp+220h+var_1F0], ebx
0x18000a4fe  mov     rax, [rsi]
0x18000a501  lea     rdx, [r14+28h]
0x18000a505  lea     r9, [rsp+220h+var_1F0]
0x18000a50a  mov     r8d, 2
0x18000a510  mov     rcx, rsi
0x18000a513  mov     rax, [rax+18h]
0x18000a517  call    cs:__guard_dispatch_icall_fptr
0x18000a51d  mov     ecx, eax; this
0x18000a51f  mov     r8, r12; int
0x18000a522  mov     edx, 0DAh; int
0x18000a527  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000a52c  cmp     dword ptr [rsp+220h+var_1F0], ebx
0x18000a530  jz      loc_18000AB4D
0x18000a536  lea     r8, [rbp+120h+var_B0]
0x18000a53a  mov     rcx, r14
0x18000a53d  call    ??$for_each@$01V_lambda_1_@?1??Read@?$SerializableObject@UFieldNBytes@Meta@RepoMan@@UField2Bytes@23@UField4Bytes@23@U423@U523@U523@U523@U423@U423@U523@U523@U523@@Meta@RepoMan@@QEAAXPEAUIStream@@@Z@AEAPEAU6@@?$TypeList@UFieldNBytes@Meta@RepoMan@@UField2Bytes@23@UField4Bytes@23@U423@U523@U523@U523@U423@U423@U523@U523@U523@@Meta@RepoMan@@QEAAXAEBV_lambda_1_@?1??Read@?$SerializableObject@UFieldNBytes@Meta@RepoMan@@UField2Bytes@23@UField4Bytes@23@U423@U523@U523@U523@U423@U423@U523@U523@U523@@12@QEAAXPEAUIStream@@@Z@AEAPEAU6@@Z; RepoMan::Meta::TypeList<RepoMan::Meta::FieldNBytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes>::for_each<2,`RepoMan::Meta::SerializableObject<RepoMan::Meta::FieldNBytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes>::Read(IStream *)'::`2'::_lambda_1_,IStream * &>(`RepoMan::Meta::SerializableObject<RepoMan::Meta::FieldNBytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field2Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes>::Read(IStream *)'::`2'::_lambda_1_ const &,IStream * &)
0x18000a542  xorps   xmm0, xmm0
0x18000a545  movdqu  xmmword ptr [rsp+220h+var_1D0], xmm0
0x18000a54b  mov     r13, rbx
0x18000a54e  mov     [rsp+220h+var_1C0], rbx
0x18000a553  mov     rdx, [r15+8]
0x18000a557  sub     rdx, [r15]
0x18000a55a  mov     rdi, rbx
0x18000a55d  mov     [rbp+120h+var_B0], rbx
0x18000a561  jz      short loc_18000A59A
0x18000a563  lea     rcx, [rsp+220h+var_1D0]
0x18000a568  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18000a56d  mov     rdi, [r15+8]
0x18000a571  sub     rdi, [r15]
0x18000a574  mov     r8, rdi; Size
0x18000a577  mov     rdx, [r15]; Src
0x18000a57a  mov     r12, [rsp+220h+var_1D0]
0x18000a57f  mov     rcx, r12; void *
0x18000a582  call    memmove
0x18000a587  add     rdi, r12
0x18000a58a  mov     [rbp+120h+var_B0], rdi
0x18000a58e  mov     [rsp+220h+var_1D0+8], rdi
0x18000a593  mov     r13, [rsp+220h+var_1C0]
0x18000a598  jmp     short loc_18000A59F
0x18000a59a  mov     r12, [rsp+220h+var_1D0]
0x18000a59f  lea     rcx, [rbp+120h+var_1A0]
0x18000a5a3  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18000a5a8  nop
0x18000a5a9  cmp     r12, rdi
0x18000a5ac  jz      loc_18000A636
0x18000a5b2  mov     rbx, [rbp+120h+var_B0]
0x18000a5b6  mov     r15, r12
0x18000a5b9  movzx   edi, byte ptr [r15]
0x18000a5bd  mov     rax, [rbp+120h+var_1A0]
0x18000a5c1  movsxd  rcx, dword ptr [rax+4]
0x18000a5c5  mov     eax, [rbp+rcx+120h+var_188]
0x18000a5c9  and     eax, 0FFFFF9FFh
0x18000a5ce  bts     eax, 0Bh
0x18000a5d2  mov     [rbp+rcx+120h+var_188], eax
0x18000a5d6  mov     rax, [rbp+120h+var_1A0]
0x18000a5da  movsxd  rcx, dword ptr [rax+4]
0x18000a5de  mov     [rbp+rcx+120h+var_148], 30h ; '0'
0x18000a5e3  mov     edx, 2
0x18000a5e8  lea     rcx, [rbp+120h+var_B0]
0x18000a5ec  call    ?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x18000a5f1  mov     rcx, [rbp+120h+var_1A0]
0x18000a5f5  movsxd  rdx, dword ptr [rcx+4]
0x18000a5f9  lea     rcx, [rbp+120h+var_1A0]
0x18000a5fd  add     rcx, rdx
0x18000a600  mov     rdx, [rax+8]
0x18000a604  mov     rax, [rax]
0x18000a607  call    cs:__guard_dispatch_icall_fptr
0x18000a60d  movzx   edx, di
0x18000a610  lea     rcx, [rbp+120h+var_1A0]
0x18000a614  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@F@Z; std::ostream::operator<<(short)
0x18000a619  mov     rcx, rax
0x18000a61c  lea     rdx, asc_1801D0D08; " "
0x18000a623  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000a628  inc     r15
0x18000a62b  cmp     r15, rbx
0x18000a62e  jnz     short loc_18000A5B9
0x18000a630  xor     ebx, ebx
0x18000a632  lea     r15, [r14+30h]
0x18000a636  lea     rcx, [rbp+120h+var_B0]
0x18000a63a  call    ?PREAMBLE@PackageDBFormat@RepoMan@@CA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; RepoMan::PackageDBFormat::PREAMBLE(void)
0x18000a63f  mov     rcx, [rax]; Buf1
0x18000a642  mov     r8, [rax+8]
0x18000a646  sub     r8, rcx; Size
0x18000a649  mov     rax, [r15+8]
0x18000a64d  sub     rax, [r15]
0x18000a650  cmp     r8, rax
0x18000a653  jz      short loc_18000A65A
0x18000a655  mov     dil, bl
0x18000a658  jmp     short loc_18000A668
0x18000a65a  mov     rdx, [r15]; Buf2
0x18000a65d  call    memcmp
0x18000a662  test    eax, eax
0x18000a664  setz    dil
0x18000a668  lea     rcx, [rbp+120h+var_B0]
0x18000a66c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a671  test    dil, dil
0x18000a674  jz      loc_18000AB70
0x18000a67a  mov     rcx, [r15+8]
0x18000a67e  sub     rcx, [r15]
0x18000a681  add     rcx, 24h ; '$'
0x18000a685  movzx   eax, word ptr [r14+28h]
0x18000a68a  cmp     rax, rcx
0x18000a68d  jnz     loc_18000ABC0
0x18000a693  cmp     byte ptr [r14+0Ch], 1
0x18000a698  ja      loc_18000ABE7
0x18000a69e  movzx   ecx, byte ptr [r14+0Ch]
0x18000a6a3  lea     rdx, ?hashSizes@?1??HashSize@PackageDBFormat@RepoMan@@CA_KW4HashAlgorithm@23@@Z@4PA_KA; unsigned __int64 near * `RepoMan::PackageDBFormat::HashSize(RepoMan::PackageDBFormat::HashAlgorithm)'::`2'::hashSizes
0x18000a6aa  movzx   eax, word ptr [r14+10h]
0x18000a6af  cmp     [rdx+rcx*8], rax
0x18000a6b3  jnz     loc_18000AB26
0x18000a6b9  mov     edx, [r14+14h]
0x18000a6bd  mov     rax, [rsi]
0x18000a6c0  xor     r9d, r9d
0x18000a6c3  xor     r8d, r8d
0x18000a6c6  mov     rcx, rsi
0x18000a6c9  mov     rax, [rax+28h]
0x18000a6cd  call    cs:__guard_dispatch_icall_fptr
0x18000a6d3  mov     ecx, eax; this
0x18000a6d5  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000a6dc  mov     edx, 169h; int
0x18000a6e1  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000a6e6  movzx   r8d, word ptr [r14+10h]
0x18000a6eb  mov     rdx, rsi
0x18000a6ee  lea     rcx, [rbp+120h+var_B0]
0x18000a6f2  call    ?Read@?$StreamBase@$$V@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@_K@Z; RepoMan::StreamBase<>::Read(IStream *,unsigned __int64)
0x18000a6f7  mov     rdi, rax
0x18000a6fa  lea     r15, [r14+0C0h]
0x18000a701  cmp     r15, rax
0x18000a704  jz      short loc_18000A72F
0x18000a706  mov     rcx, r15
0x18000a709  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a70e  mov     rcx, [rdi]
0x18000a711  mov     [r15], rcx
0x18000a714  mov     rcx, [rdi+8]
0x18000a718  mov     [r15+8], rcx
0x18000a71c  mov     rcx, [rdi+10h]
0x18000a720  mov     [r15+10h], rcx
0x18000a724  mov     [rdi], rbx
0x18000a727  mov     [rdi+8], rbx
0x18000a72b  mov     [rdi+10h], rbx
0x18000a72f  lea     rcx, [rbp+120h+var_B0]
0x18000a733  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a738  mov     edx, [r14+24h]
0x18000a73c  lea     rdi, [r14+58h]
0x18000a740  mov     [rdi+40h], rdx
0x18000a744  movzx   eax, word ptr [r14+20h]
0x18000a749  add     rax, rdx
0x18000a74c  mov     [r14+0A0h], rax
0x18000a753  mov     rax, [rsi]
0x18000a756  xor     r9d, r9d
0x18000a759  xor     r8d, r8d
0x18000a75c  mov     rcx, rsi
0x18000a75f  mov     rax, [rax+28h]
0x18000a763  call    cs:__guard_dispatch_icall_fptr
0x18000a769  mov     ecx, eax; this
0x18000a76b  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000a772  mov     edx, 169h; int
0x18000a777  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000a77c  mov     [rdi+30h], rbx
0x18000a780  lea     rcx, [rdi+20h]
0x18000a784  cmp     qword ptr [rdi+38h], 0Fh
0x18000a789  jbe     short loc_18000A78F
0x18000a78b  mov     rcx, [rdi+20h]
0x18000a78f  mov     [rcx], bl
0x18000a791  mov     [rdi+10h], rbx
0x18000a795  mov     rax, rdi
0x18000a798  cmp     qword ptr [rdi+18h], 0Fh
0x18000a79d  jbe     short loc_18000A7A2
0x18000a79f  mov     rax, [rdi]
0x18000a7a2  mov     [rax], bl
0x18000a7a4  mov     [rbp+120h+var_B0], rsi
0x18000a7a8  mov     rax, [rsi]
0x18000a7ab  xor     r9d, r9d
0x18000a7ae  xor     r8d, r8d
0x18000a7b1  mov     rdx, [rdi+40h]
0x18000a7b5  mov     rcx, rsi
0x18000a7b8  mov     rax, [rax+28h]
0x18000a7bc  call    cs:__guard_dispatch_icall_fptr
0x18000a7c2  mov     ecx, eax; this
0x18000a7c4  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000a7cb  mov     edx, 169h; int
0x18000a7d0  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000a7d5  lea     r9, [rbp+120h+var_B0]
0x18000a7d9  lea     rdx, [rdi+20h]
0x18000a7dd  call    ??$?RUFieldString@Meta@RepoMan@@@_lambda_1_@?1??Read@?$SerializableObject@UFieldString@Meta@RepoMan@@U123@@Meta@RepoMan@@QEAAXPEAUIStream@@@Z@QEBA?A_PAEAUFieldString@34@_KAEAPEAU5@@Z
0x18000a7e2  lea     r9, [rbp+120h+var_B0]
0x18000a7e6  mov     rdx, rdi
0x18000a7e9  call    ??$?RUFieldString@Meta@RepoMan@@@_lambda_1_@?1??Read@?$SerializableObject@UFieldString@Meta@RepoMan@@U123@@Meta@RepoMan@@QEAAXPEAUIStream@@@Z@QEBA?A_PAEAUFieldString@34@_KAEAPEAU5@@Z
0x18000a7ee  mov     [rsp+220h+Reserved], rbx
0x18000a7f3  lea     r9, [rdi+20h]
0x18000a7f7  mov     edx, 1
0x18000a7fc  mov     r8d, edx
0x18000a7ff  lea     rcx, [rbp+120h+var_B0]
0x18000a803  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18000a808  mov     rcx, [rbp+120h+var_48]
0x18000a80f  mov     rax, [rcx]
0x18000a812  lea     rdx, [rbp+120h+var_B0]
0x18000a816  mov     rax, [rax+30h]
0x18000a81a  call    cs:__guard_dispatch_icall_fptr
0x18000a820  mov     [rsp+220h+Reserved], rbx
0x18000a825  mov     r9, rdi
0x18000a828  mov     edx, 1
0x18000a82d  lea     r8d, [rdx+1]
0x18000a831  lea     rcx, [rsp+220h+var_1F0]
0x18000a836  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18000a83b  mov     rcx, [rbp+120h+var_48]
0x18000a842  mov     rax, [rcx]
0x18000a845  lea     rdx, [rsp+220h+var_1F0]
0x18000a84a  mov     rax, [rax+30h]
0x18000a84e  call    cs:__guard_dispatch_icall_fptr
0x18000a854  nop
0x18000a855  mov     rcx, [rsp+220h+var_1F0]
0x18000a85a  test    rcx, rcx
0x18000a85d  jz      short loc_18000A872
0x18000a85f  mov     [rsp+220h+var_1F0], rbx
0x18000a864  mov     rax, [rcx]
0x18000a867  mov     rax, [rax+8]
0x18000a86b  call    cs:__guard_dispatch_icall_fptr
0x18000a871  nop
0x18000a872  mov     rcx, [rbp+120h+var_B0]
0x18000a876  test    rcx, rcx
0x18000a879  jz      short loc_18000A88D
0x18000a87b  mov     [rbp+120h+var_B0], rbx
0x18000a87f  mov     rax, [rcx]
0x18000a882  mov     rax, [rax+8]
0x18000a886  call    cs:__guard_dispatch_icall_fptr
0x18000a88c  nop
0x18000a88d  mov     [rbp+120h+var_B0], rsi
0x18000a891  test    rsi, rsi
  ... truncated ...
```
