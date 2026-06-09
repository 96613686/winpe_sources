# RepoMan::Folder::RemoveDirectoryW(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18018eb0c`
- end: `0x18018f232`
- name: `?RemoveDirectoryW@Folder@RepoMan@@QEBAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1830`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x1800bf1f0`

## callees

- `0x180001504`
- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x18001ac20`
- `0x1800244d0`
- `0x1800273c0`
- `0x18002f940`
- `0x18002f9b0`
- `0x18002fa20`
- `0x18002fb04`
- `0x1800318e0`
- `0x1800dfffc`
- `0x18018b53c`
- `0x18018ea70`
- `0x18018eb0c`
- `0x180190270`
- `0x180190990`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x18018f04b`
- `KERNEL32!RemoveDirectoryW` at `0x18018f04b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018ed7e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018ed7e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018ecc0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018eecf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018ef18`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018f1a8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018ecc0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018eecf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018ef18`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018f1a8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018ecb9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018eec8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018ef11`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018f1a1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018ecb9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018eec8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018ef11`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018f1a1`

## string_xrefs

- `0x18018eb4e`: `Folder.RemoveDirectory`
- `0x18018f0f4`: `removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall RepoMan::Folder::RemoveDirectoryW(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // r12
  __int64 v6; // rcx
  size_t v7; // rcx
  __int64 v8; // rax
  void *v9; // rcx
  __m128i v10; // xmm7
  __int64 v11; // r15
  size_t *i; // rsi
  size_t *v13; // r14
  size_t v14; // rcx
  void *Src; // rax
  _QWORD *v16; // rax
  size_t v17; // rcx
  __int64 v18; // rax
  void *v19; // rcx
  void *v20; // rcx
  __int64 *v21; // rbx
  __m128i v22; // xmm6
  __int64 *v23; // rcx
  __int64 *v24; // rcx
  __int64 *v25; // rdx
  __int64 *v26; // rax
  size_t v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 *v30; // rax
  __int64 *v31; // rax
  __int64 *v32; // rcx
  __int64 v33; // rcx
  void *v34; // rcx
  __int128 v35; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+58h] [rbp-B0h] BYREF
  void *v37[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+78h] [rbp-90h]
  __int128 v39; // [rsp+88h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+98h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-60h]
  void *v42[2]; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v43; // [rsp+C8h] [rbp-40h]
  __int128 v44; // [rsp+D8h] [rbp-30h] BYREF
  __m128i v45; // [rsp+E8h] [rbp-20h]
  _BYTE v46[32]; // [rsp+F8h] [rbp-10h] BYREF
  WCHAR WideCharStr[8]; // [rsp+118h] [rbp+10h] BYREF
  __m128i v48; // [rsp+128h] [rbp+20h]
  _BYTE v49[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v50[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v51[40]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v52; // [rsp+1A0h] [rbp+98h]

  RepoMan::Tracer::Tracer(v51, 1, "Folder.RemoveDirectory");
  v4 = RepoMan::Logger::Message<std::string const &,>(&v35, a2);
  v5 = v52;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 48LL))(v52, v4);
  v6 = v35;
  if ( (_QWORD)v35 )
  {
    *(_QWORD *)&v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v7 = *(_QWORD *)(a1 + 16);
  if ( 0x7FFFFFFFFFFFFFFFLL == v7 )
    std::_Xlen_string();
  std::string::string(v46, v7, "\\", 1u);
  v8 = std::string::append(v46);
  v44 = 0;
  v45 = 0;
  v44 = *(_OWORD *)v8;
  v45 = *(__m128i *)(v8 + 16);
  *(_BYTE *)v8 = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 15;
  *(_QWORD *)&v35 = v37;
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 92;
  sub_180190270(&v44, Block, &v35);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v9 = Block[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v9);
  }
  std::string::_Tidy_deallocate(&v44);
  *(_QWORD *)&v44 = 19937;
  v10 = _mm_load_si128((const __m128i *)&_xmm);
  v45 = v10;
  std::string::_Tidy_deallocate(v46);
  v11 = 0;
  v13 = (size_t *)v37[1];
  for ( i = (size_t *)v37[0]; i != v13; i += 4 )
  {
    v14 = *(_QWORD *)(a2 + 16);
    if ( 0x7FFFFFFFFFFFFFFFLL - v14 < i[2] )
      std::_Xlen_string();
    Src = i;
    if ( i[3] > 0xF )
      Src = (void *)*i;
    std::string::string(v46, v14, Src, i[2]);
    RepoMan::Folder::RemoveFile(a1, v46);
    std::string::_Tidy_deallocate(v46);
    ++v11;
  }
  v36 = 0;
  v16 = malloc(0x40u);
  if ( !v16 )
    std::_Xbad_alloc();
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  *(_QWORD *)&v36 = v16;
  std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(
    &v36,
    &v35,
    a2);
  *(_QWORD *)&v35 = &v36;
  *((_QWORD *)&v35 + 1) = a2;
  v17 = *(_QWORD *)(a1 + 16);
  if ( v17 == 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  std::string::string(v49, v17, "\\", 1u);
  v18 = std::string::append(v49);
  *(_OWORD *)v42 = 0;
  v43 = 0;
  *(_OWORD *)v42 = *(_OWORD *)v18;
  v43 = *(__m128i *)(v18 + 16);
  *(_BYTE *)v18 = 0;
  *(_QWORD *)(v18 + 16) = 0;
  *(_QWORD *)(v18 + 24) = 15;
  v39 = v35;
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 92;
  sub_180190990(v42, Block, &v39);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v19 = Block[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v19 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v19 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v19);
  }
  if ( v43.m128i_i64[1] > 0xFuLL )
  {
    v20 = v42[0];
    if ( (unsigned __int64)(v43.m128i_i64[1] + 1) >= 0x1000 )
    {
      v20 = (void *)*((_QWORD *)v42[0] - 1);
      if ( (unsigned __int64)((char *)v42[0] - (char *)v20 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v20);
  }
  v42[0] = (void *)19937;
  v43 = v10;
  std::string::_Tidy_deallocate(v49);
  v21 = (__int64 *)v36;
  if ( v21 != (__int64 *)*v21 )
  {
    v22 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      if ( !*((_BYTE *)v21 + 25) )
      {
        v23 = (__int64 *)*v21;
        if ( *(_BYTE *)(*v21 + 25) )
        {
          v24 = (__int64 *)v21[1];
          if ( !*((_BYTE *)v24 + 25) )
          {
            v25 = v21;
            do
            {
              if ( v25 != (__int64 *)*v24 )
                break;
              v26 = v24;
              v24 = (__int64 *)v24[1];
              v25 = v26;
            }
            while ( !*((_BYTE *)v24 + 25) );
          }
        }
        else
        {
          do
            v23 = (__int64 *)v23[2];
          while ( !*((_BYTE *)v23 + 25) );
        }
      }
      v27 = *(_QWORD *)(a1 + 16);
      if ( v27 == 0x7FFFFFFFFFFFFFFFLL )
        std::_Xlen_string();
      std::string::string(v50, v27, "\\", 1u);
      v28 = std::string::append(v50);
      *(_OWORD *)Block = 0;
      si128 = 0;
      *(_OWORD *)Block = *(_OWORD *)v28;
      si128 = *(__m128i *)(v28 + 16);
      *(_BYTE *)v28 = 0;
      *(_QWORD *)(v28 + 16) = 0;
      *(_QWORD *)(v28 + 24) = 15;
      v29 = RepoMan::utf8_to_wstring(WideCharStr, (LPCCH)Block);
      if ( *(_QWORD *)(v29 + 24) > 7u )
        v29 = *(_QWORD *)v29;
      RemoveDirectoryW((LPCWSTR)v29);
      std::wstring::_Tidy_deallocate(WideCharStr);
      *(_QWORD *)WideCharStr = 19937;
      v48 = v22;
      std::string::_Tidy_deallocate(Block);
      Block[0] = (void *)19937;
      si128 = v10;
      std::string::_Tidy_deallocate(v50);
      if ( *((_BYTE *)v21 + 25) )
      {
        v21 = (__int64 *)v21[2];
      }
      else
      {
        v30 = (__int64 *)*v21;
        if ( *(_BYTE *)(*v21 + 25) )
        {
          v31 = (__int64 *)v21[1];
          if ( !*((_BYTE *)v31 + 25) )
          {
            v32 = v21;
            do
            {
              if ( v32 != (__int64 *)*v31 )
                break;
              v21 = v31;
              v32 = v31;
              v31 = (__int64 *)v31[1];
            }
            while ( !*((_BYTE *)v31 + 25) );
          }
          if ( !*((_BYTE *)v21 + 25) )
            v21 = v31;
        }
        else
        {
          do
          {
            v21 = v30;
            v30 = (__int64 *)v30[2];
          }
          while ( !*((_BYTE *)v30 + 25) );
        }
      }
    }
    while ( v21 != *(__int64 **)v36 );
  }
  HIWORD(v42[1]) = 0;
  v43 = _mm_load_si128((const __m128i *)&_xmm);
  qmemcpy(v42, "remove", 6);
  *(void **)((char *)v42 + 6) = (void *)(unsigned __int8)aRemoved[6];
  RepoMan::Logger::CreateValue((unsigned int)&v35, 3, 11, (unsigned int)v42, v11);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v5 + 48LL))(v5, &v35);
  v33 = v35;
  if ( (_QWORD)v35 )
  {
    *(_QWORD *)&v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  }
  if ( v43.m128i_i64[1] > 0xFuLL )
  {
    v34 = v42[0];
    if ( (unsigned __int64)(v43.m128i_i64[1] + 1) >= 0x1000 )
    {
      v34 = (void *)*((_QWORD *)v42[0] - 1);
      if ( (unsigned __int64)((char *)v42[0] - (char *)v34 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v34);
  }
  std::_Tree<std::_Tset_traits<RepoMan::Legacy::Descriptor::Package,std::less<RepoMan::Legacy::Descriptor::Package>,std::allocator<RepoMan::Legacy::Descriptor::Package>,0>>::~_Tree<std::_Tset_traits<RepoMan::Legacy::Descriptor::Package,std::less<RepoMan::Legacy::Descriptor::Package>,std::allocator<RepoMan::Legacy::Descriptor::Package>,0>>(&v36);
  std::vector<std::string>::_Tidy(v37);
  *(__m128i *)v37 = _mm_load_si128((const __m128i *)&_xmm);
  v38 = 19937;
  RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v51);
}

```

## disassembly

```asm
0x18018eb0c  mov     rax, rsp
0x18018eb0f  mov     [rax+18h], rbx
0x18018eb13  push    rbp
0x18018eb14  push    rsi
0x18018eb15  push    rdi
0x18018eb16  push    r12
0x18018eb18  push    r13
0x18018eb1a  push    r14
0x18018eb1c  push    r15
0x18018eb1e  lea     rbp, [rax-108h]
0x18018eb25  sub     rsp, 1D0h
0x18018eb2c  movaps  xmmword ptr [rax-48h], xmm6
0x18018eb30  movaps  xmmword ptr [rax-58h], xmm7
0x18018eb34  mov     rax, cs:__security_cookie
0x18018eb3b  xor     rax, rsp
0x18018eb3e  mov     [rbp+100h+var_60], rax
0x18018eb45  mov     rbx, rdx
0x18018eb48  mov     rdi, rcx
0x18018eb4b  xor     r13d, r13d
0x18018eb4e  lea     r8, aFolderRemovedi; "Folder.RemoveDirectory"
0x18018eb55  lea     r14d, [r13+1]
0x18018eb59  mov     edx, r14d
0x18018eb5c  lea     rcx, [rbp+100h+var_90]
0x18018eb60  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x18018eb65  nop
0x18018eb66  mov     rdx, rbx
0x18018eb69  lea     rcx, [rsp+200h+var_1C8+8]
0x18018eb6e  call    ??$Message@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::Logger::Message<std::string const &,>(std::string const &)
0x18018eb73  mov     rdx, rax
0x18018eb76  mov     r12, [rbp+100h+var_68]
0x18018eb7d  mov     rcx, [r12]
0x18018eb81  mov     rax, [rcx+30h]
0x18018eb85  mov     rcx, r12
0x18018eb88  call    cs:__guard_dispatch_icall_fptr
0x18018eb8e  nop
0x18018eb8f  mov     rcx, qword ptr [rsp+200h+var_1C8+8]
0x18018eb94  test    rcx, rcx
0x18018eb97  jz      short loc_18018EBAC
0x18018eb99  mov     qword ptr [rsp+200h+var_1C8+8], r13
0x18018eb9e  mov     rax, [rcx]
0x18018eba1  mov     rax, [rax+8]
0x18018eba5  call    cs:__guard_dispatch_icall_fptr
0x18018ebab  nop
0x18018ebac  xorps   xmm0, xmm0
0x18018ebaf  movdqu  xmmword ptr [rsp+200h+var_1A8+8], xmm0
0x18018ebb5  mov     [rsp+200h+var_190], r13
0x18018ebba  mov     rcx, [rdi+10h]
0x18018ebbe  mov     rax, 7FFFFFFFFFFFFFFFh
0x18018ebc8  sub     rax, rcx
0x18018ebcb  cmp     rax, r14
0x18018ebce  jb      loc_18018F21A
0x18018ebd4  mov     r9, rdi
0x18018ebd7  mov     esi, 0Fh
0x18018ebdc  cmp     [rdi+18h], rsi
0x18018ebe0  jbe     short loc_18018EBE5
0x18018ebe2  mov     r9, [rdi]
0x18018ebe5  mov     [rsp+200h+var_1D0], r14; size_t
0x18018ebea  lea     rax, asc_1801DE32C; "\\"
0x18018ebf1  mov     [rsp+200h+Src], rax; Src
0x18018ebf6  mov     [rsp+200h+Reserved], rcx; Size
0x18018ebfb  lea     rcx, [rbp+100h+var_110]; void *
0x18018ebff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18018ec04  nop
0x18018ec05  mov     rdx, rbx
0x18018ec08  cmp     [rbx+18h], rsi
0x18018ec0c  jbe     short loc_18018EC11
0x18018ec0e  mov     rdx, [rbx]
0x18018ec11  mov     r8, [rbx+10h]
0x18018ec15  lea     rcx, [rbp+100h+var_110]; Src
0x18018ec19  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18018ec1e  xorps   xmm0, xmm0
0x18018ec21  movups  [rbp+100h+var_130], xmm0
0x18018ec25  xorps   xmm1, xmm1
0x18018ec28  movdqu  [rbp+100h+var_120], xmm1
0x18018ec2d  movups  xmm0, xmmword ptr [rax]
0x18018ec30  movups  [rbp+100h+var_130], xmm0
0x18018ec34  movups  xmm1, xmmword ptr [rax+10h]
0x18018ec38  movups  [rbp+100h+var_120], xmm1
0x18018ec3c  mov     [rax], r13b
0x18018ec3f  mov     [rax+10h], r13
0x18018ec43  mov     [rax+18h], rsi
0x18018ec47  lea     rax, [rsp+200h+var_1A8+8]
0x18018ec4c  mov     qword ptr [rsp+200h+var_1C8+8], rax
0x18018ec51  xorps   xmm0, xmm0
0x18018ec54  movups  xmmword ptr [rbp+100h+Block], xmm0
0x18018ec58  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000001
0x18018ec60  movdqu  [rbp+100h+var_160], xmm0
0x18018ec65  mov     word ptr [rbp+100h+Block], 5Ch ; '\'
0x18018ec6b  lea     r8, [rsp+200h+var_1C8+8]
0x18018ec70  lea     rdx, [rbp+100h+Block]
0x18018ec74  lea     rcx, [rbp+100h+var_130]
0x18018ec78  call    sub_180190270
0x18018ec7d  nop
0x18018ec7e  mov     rax, qword ptr [rbp+100h+var_160+8]
0x18018ec82  cmp     rax, rsi
0x18018ec85  jbe     short loc_18018ECC7
0x18018ec87  mov     rcx, [rbp+100h+Block]; Block
0x18018ec8b  mov     rdx, rcx
0x18018ec8e  inc     rax
0x18018ec91  cmp     rax, 1000h
0x18018ec97  jb      short loc_18018ECC0
0x18018ec99  mov     rcx, [rcx-8]
0x18018ec9d  sub     rdx, rcx
0x18018eca0  lea     rax, [rdx-8]
0x18018eca4  cmp     rax, 1Fh
0x18018eca8  jbe     short loc_18018ECC0
0x18018ecaa  mov     [rsp+200h+Reserved], r13; Reserved
0x18018ecaf  xor     r9d, r9d; LineNo
0x18018ecb2  xor     r8d, r8d; FileName
0x18018ecb5  xor     edx, edx; FunctionName
0x18018ecb7  xor     ecx, ecx; Expression
0x18018ecb9  call    cs:__imp__invoke_watson
0x18018ecc0  call    cs:__imp_free
0x18018ecc6  nop
0x18018ecc7  lea     rcx, [rbp+100h+var_130]
0x18018eccb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018ecd0  mov     qword ptr [rbp+100h+var_130], 4DE1h
0x18018ecd8  movdqa  xmm7, cs:__xmm@000000000000001f0000000000000000
0x18018ece0  movdqu  [rbp+100h+var_120], xmm7
0x18018ece5  lea     rcx, [rbp+100h+var_110]
0x18018ece9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018ecee  mov     r15, r13
0x18018ecf1  mov     rsi, [rsp+200h+var_1A8+8]
0x18018ecf6  mov     r14, [rsp+200h+var_198]
0x18018ecfb  jmp     short loc_18018ED6B
0x18018ecfd  mov     rcx, [rbx+10h]
0x18018ed01  mov     rdx, [rsi+10h]
0x18018ed05  mov     rax, 7FFFFFFFFFFFFFFFh
0x18018ed0f  sub     rax, rcx
0x18018ed12  cmp     rax, rdx
0x18018ed15  jb      loc_18018F226
0x18018ed1b  mov     r9, rbx
0x18018ed1e  cmp     qword ptr [rbx+18h], 0Fh
0x18018ed23  jbe     short loc_18018ED28
0x18018ed25  mov     r9, [rbx]
0x18018ed28  mov     rax, rsi
0x18018ed2b  cmp     qword ptr [rsi+18h], 0Fh
0x18018ed30  jbe     short loc_18018ED35
0x18018ed32  mov     rax, [rsi]
0x18018ed35  mov     [rsp+200h+var_1D0], rdx; size_t
0x18018ed3a  mov     [rsp+200h+Src], rax; Src
0x18018ed3f  mov     [rsp+200h+Reserved], rcx; Size
0x18018ed44  lea     rcx, [rbp+100h+var_110]; void *
0x18018ed48  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18018ed4d  nop
0x18018ed4e  lea     rdx, [rbp+100h+var_110]
0x18018ed52  mov     rcx, rdi
0x18018ed55  call    ?RemoveFile@Folder@RepoMan@@QEBAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::Folder::RemoveFile(std::string const &)
0x18018ed5a  nop
0x18018ed5b  lea     rcx, [rbp+100h+var_110]
0x18018ed5f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018ed64  inc     r15
0x18018ed67  add     rsi, 20h ; ' '
0x18018ed6b  cmp     rsi, r14
0x18018ed6e  jnz     short loc_18018ECFD
0x18018ed70  xorps   xmm0, xmm0
0x18018ed73  movdqu  [rsp+200h+var_1B8+8], xmm0
0x18018ed79  mov     ecx, 40h ; '@'; Size
0x18018ed7e  call    cs:__imp_malloc
0x18018ed84  test    rax, rax
0x18018ed87  jz      loc_18018F220
0x18018ed8d  mov     [rax], rax
0x18018ed90  mov     [rax+8], rax
0x18018ed94  mov     [rax+10h], rax
0x18018ed98  mov     word ptr [rax+18h], 101h
0x18018ed9e  mov     qword ptr [rsp+200h+var_1B8+8], rax
0x18018eda3  mov     r8, rbx
0x18018eda6  lea     rdx, [rsp+200h+var_1C8+8]
0x18018edab  lea     rcx, [rsp+200h+var_1B8+8]
0x18018edb0  call    ??$_Emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(std::string const &)
0x18018edb5  lea     rax, [rsp+200h+var_1B8+8]
0x18018edba  mov     qword ptr [rsp+200h+var_1C8+8], rax
0x18018edbf  mov     qword ptr [rsp+200h+var_1B8], rbx
0x18018edc4  mov     rcx, [rdi+10h]
0x18018edc8  mov     rax, 7FFFFFFFFFFFFFFFh
0x18018edd2  sub     rax, rcx
0x18018edd5  cmp     rax, 1
0x18018edd9  jb      loc_18018F22C
0x18018eddf  mov     r9, rdi
0x18018ede2  mov     r14d, 0Fh
0x18018ede8  cmp     [rdi+18h], r14
0x18018edec  jbe     short loc_18018EDF1
0x18018edee  mov     r9, [rdi]
0x18018edf1  mov     [rsp+200h+var_1D0], 1; size_t
0x18018edfa  lea     rax, asc_1801DE32C; "\\"
0x18018ee01  mov     [rsp+200h+Src], rax; Src
0x18018ee06  mov     [rsp+200h+Reserved], rcx; Size
0x18018ee0b  lea     rcx, [rbp+100h+var_D0]; void *
0x18018ee0f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18018ee14  nop
0x18018ee15  mov     r8, [rbx+10h]
0x18018ee19  cmp     [rbx+18h], r14
0x18018ee1d  jbe     short loc_18018EE22
0x18018ee1f  mov     rbx, [rbx]
0x18018ee22  mov     rdx, rbx
0x18018ee25  lea     rcx, [rbp+100h+var_D0]; Src
0x18018ee29  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18018ee2e  xorps   xmm0, xmm0
0x18018ee31  movups  xmmword ptr [rbp+100h+var_150], xmm0
0x18018ee35  xorps   xmm1, xmm1
0x18018ee38  movdqu  [rbp+100h+var_140], xmm1
0x18018ee3d  movups  xmm0, xmmword ptr [rax]
0x18018ee40  movups  xmmword ptr [rbp+100h+var_150], xmm0
0x18018ee44  movups  xmm1, xmmword ptr [rax+10h]
0x18018ee48  movups  [rbp+100h+var_140], xmm1
0x18018ee4c  mov     [rax], r13b
0x18018ee4f  mov     [rax+10h], r13
0x18018ee53  mov     [rax+18h], r14
0x18018ee57  movups  xmm0, [rsp+200h+var_1C8+8]
0x18018ee5c  movdqu  [rbp+100h+var_180], xmm0
0x18018ee61  xorps   xmm1, xmm1
0x18018ee64  movups  xmmword ptr [rbp+100h+Block], xmm1
0x18018ee68  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000001
0x18018ee70  movdqu  [rbp+100h+var_160], xmm0
0x18018ee75  mov     word ptr [rbp+100h+Block], 5Ch ; '\'
0x18018ee7b  lea     r8, [rbp+100h+var_180]
0x18018ee7f  lea     rdx, [rbp+100h+Block]
0x18018ee83  lea     rcx, [rbp+100h+var_150]
0x18018ee87  call    sub_180190990
0x18018ee8c  nop
0x18018ee8d  mov     rax, qword ptr [rbp+100h+var_160+8]
0x18018ee91  cmp     rax, r14
0x18018ee94  jbe     short loc_18018EED6
0x18018ee96  mov     rcx, [rbp+100h+Block]; Block
0x18018ee9a  mov     rdx, rcx
0x18018ee9d  inc     rax
0x18018eea0  cmp     rax, 1000h
0x18018eea6  jb      short loc_18018EECF
0x18018eea8  mov     rcx, [rcx-8]
0x18018eeac  sub     rdx, rcx
0x18018eeaf  lea     rax, [rdx-8]
0x18018eeb3  cmp     rax, 1Fh
0x18018eeb7  jbe     short loc_18018EECF
0x18018eeb9  mov     [rsp+200h+Reserved], r13; Reserved
0x18018eebe  xor     r9d, r9d; LineNo
0x18018eec1  xor     r8d, r8d; FileName
0x18018eec4  xor     edx, edx; FunctionName
0x18018eec6  xor     ecx, ecx; Expression
0x18018eec8  call    cs:__imp__invoke_watson
0x18018eecf  call    cs:__imp_free
0x18018eed5  nop
0x18018eed6  mov     rax, qword ptr [rbp+100h+var_140+8]
0x18018eeda  cmp     rax, r14
0x18018eedd  jbe     short loc_18018EF1E
0x18018eedf  mov     rcx, [rbp+100h+var_150]; Block
0x18018eee3  mov     rdx, rcx
0x18018eee6  inc     rax
0x18018eee9  cmp     rax, 1000h
0x18018eeef  jb      short loc_18018EF18
0x18018eef1  mov     rcx, [rcx-8]
0x18018eef5  sub     rdx, rcx
0x18018eef8  lea     rax, [rdx-8]
0x18018eefc  cmp     rax, 1Fh
0x18018ef00  jbe     short loc_18018EF18
0x18018ef02  mov     [rsp+200h+Reserved], r13; Reserved
0x18018ef07  xor     r9d, r9d; LineNo
0x18018ef0a  xor     r8d, r8d; FileName
0x18018ef0d  xor     edx, edx; FunctionName
0x18018ef0f  xor     ecx, ecx; Expression
0x18018ef11  call    cs:__imp__invoke_watson
0x18018ef18  call    cs:__imp_free
0x18018ef1e  mov     esi, 4DE1h
0x18018ef23  mov     [rbp+100h+var_150], rsi
0x18018ef27  movdqu  [rbp+100h+var_140], xmm7
0x18018ef2c  lea     rcx, [rbp+100h+var_D0]
0x18018ef30  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018ef35  mov     rbx, qword ptr [rsp+200h+var_1B8+8]
0x18018ef3a  cmp     rbx, [rbx]
0x18018ef3d  jz      loc_18018F0E0
0x18018ef43  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18018ef4b  mov     rax, rbx
0x18018ef4e  cmp     [rbx+19h], r13b
0x18018ef52  jz      short loc_18018EF5A
0x18018ef54  mov     rax, [rbx+10h]
0x18018ef58  jmp     short loc_18018EFA0
0x18018ef5a  mov     rcx, [rbx]
0x18018ef5d  cmp     [rcx+19h], r13b
0x18018ef61  jz      short loc_18018EF93
0x18018ef63  mov     rcx, [rbx+8]
0x18018ef67  cmp     [rcx+19h], r13b
0x18018ef6b  jnz     short loc_18018EF88
0x18018ef6d  mov     rdx, rbx
0x18018ef70  mov     r8, rcx
0x18018ef73  cmp     rdx, [rcx]
0x18018ef76  jnz     short loc_18018EF88
0x18018ef78  mov     rax, rcx
0x18018ef7b  mov     rcx, [rcx+8]
0x18018ef7f  mov     rdx, rax
0x18018ef82  cmp     [rcx+19h], r13b
0x18018ef86  jz      short loc_18018EF70
0x18018ef88  cmp     [rax+19h], r13b
0x18018ef8c  jnz     short loc_18018EFA0
0x18018ef8e  mov     rax, rcx
0x18018ef91  jmp     short loc_18018EFA0
0x18018ef93  mov     rax, rcx
0x18018ef96  mov     rcx, [rcx+10h]
0x18018ef9a  cmp     [rcx+19h], r13b
0x18018ef9e  jz      short loc_18018EF93
0x18018efa0  lea     rsi, [rax+20h]
0x18018efa4  mov     rcx, [rdi+10h]
  ... truncated ...
```
