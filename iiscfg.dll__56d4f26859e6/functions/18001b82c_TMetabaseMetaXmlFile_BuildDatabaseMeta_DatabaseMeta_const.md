# TMetabaseMetaXmlFile::BuildDatabaseMeta(DatabaseMeta const * &)

- ea: `0x18001b82c`
- end: `0x18001bc82`
- name: `?BuildDatabaseMeta@TMetabaseMetaXmlFile@@AEAAXAEAPEBUDatabaseMeta@@@Z`
- size: `1110`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct DatabaseMeta **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017e84`

## callees

- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001b82c`
- `0x18001d4c0`
- `0x18002e110`
- `0x180030010`

## string_xrefs

- `0x18001bc4e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001bc75`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001bc6e`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TMetabaseMetaXmlFile::BuildDatabaseMeta(TMetabaseMetaXmlFile *this, const struct DatabaseMeta **a2)
{
  unsigned int *v3; // rdi
  __int64 v4; // r15
  unsigned int i; // r13d
  __int64 v6; // rsi
  unsigned int *v7; // r14
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int *v15; // rdx
  unsigned int *v16; // rdx
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int *v27; // rdx
  unsigned int *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // [rsp+88h] [rbp-41h]
  __int64 v32; // [rsp+90h] [rbp-39h]
  _QWORD v33[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v35; // [rsp+D0h] [rbp+7h]
  __int128 v36; // [rsp+E0h] [rbp+17h]

  v33[0] = a2;
  v3 = (unsigned int *)(*((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 32LL));
  v4 = 0;
  for ( i = 0; ; ++i )
  {
    v6 = *((_QWORD *)this + 323);
    if ( i >= *(_DWORD *)(v6 + 36) )
    {
      v33[1] = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v33,
        0,
        *((_QWORD *)this + 325),
        0x80210861,
        3u,
        -1073606445,
        L"MetabaseBaseClass",
        &word_180034198,
        &word_180034198,
        &word_180034198,
        0,
        0,
        0,
        -1,
        -1,
        0,
        0,
        v31,
        v32,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v33,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        1447,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v33);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x5A7u,
        0);
    }
    v7 = (unsigned int *)(v6 + 56);
    if ( *v3 )
    {
      v4 = *v3;
      v8 = (const unsigned __int16 *)(v4 + v6 + *v7);
    }
    else
    {
      v8 = 0;
    }
    if ( !TMetabaseMetaXmlFile::TSizedString::IsEqual((TMetabaseMetaXmlFile *)((char *)this + 552), v8) )
      break;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    if ( *v3 )
    {
      v9 = v4 + v6 + *v7;
      v10 = *(_DWORD *)(v9 - 4) >> 1;
      v4 = 0;
    }
    else
    {
      v4 = 0;
      v9 = 0;
      v10 = 0;
    }
    v11 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v9, v10);
    LODWORD(v34) = v11;
    v12 = v3[1];
    if ( (_DWORD)v12 != *v3 )
    {
      if ( (_DWORD)v12 )
      {
        v13 = *((_QWORD *)this + 323) + v12 + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
        v14 = *(_DWORD *)(v13 - 4) >> 1;
      }
      else
      {
        v13 = 0;
        v14 = 0;
      }
      v11 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(
              this,
              v13,
              v14);
    }
    DWORD1(v34) = v11;
    if ( v3[2] )
      v15 = (unsigned int *)(*((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL) + v3[2]);
    else
      v15 = 0;
    DWORD2(v34) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v15);
    if ( v3[3] )
      v16 = (unsigned int *)(*((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL) + v3[3]);
    else
      v16 = 0;
    HIDWORD(v34) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v16);
    if ( v3[5] )
    {
      v17 = *((_QWORD *)this + 323) + v3[5] + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
      v18 = *(_DWORD *)(v17 - 4) >> 1;
    }
    else
    {
      v17 = 0;
      v18 = 0;
    }
    DWORD1(v35) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
                    this,
                    v17,
                    v18);
    (*(void (__fastcall **)(TMetabaseMetaXmlFile *, __int128 *, __int64))(*(_QWORD *)this + 64LL))(this, &v34, 1);
LABEL_30:
    v3 += 12;
  }
  if ( *v3 )
    v19 = (const unsigned __int16 *)(v4 + v6 + *v7);
  else
    v19 = 0;
  if ( !TMetabaseMetaXmlFile::TSizedString::IsEqual((TMetabaseMetaXmlFile *)((char *)this + 568), v19) )
  {
    v4 = 0;
    goto LABEL_30;
  }
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( *v3 )
  {
    v20 = v4 + v6 + *v7;
    v21 = *(_DWORD *)(v20 - 4) >> 1;
  }
  else
  {
    v20 = 0;
    v21 = 0;
  }
  v22 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v20, v21);
  LODWORD(v34) = v22;
  v23 = v3[1];
  if ( (_DWORD)v23 != *v3 )
  {
    if ( (_DWORD)v23 )
    {
      v26 = *((_QWORD *)this + 323);
      v24 = v23 + v26 + *(unsigned int *)(v26 + 56);
      v25 = *(_DWORD *)(v26 + *(unsigned int *)(v26 + 56) + v3[1] - 4) >> 1;
    }
    else
    {
      v24 = 0;
      v25 = 0;
    }
    v22 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v24, v25);
  }
  DWORD1(v34) = v22;
  if ( v3[2] )
    v27 = (unsigned int *)(*((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL) + v3[2]);
  else
    v27 = 0;
  DWORD2(v34) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v27);
  if ( v3[3] )
    v28 = (unsigned int *)(*((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL) + v3[3]);
  else
    v28 = 0;
  HIDWORD(v34) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v28);
  if ( v3[5] )
  {
    v29 = v3[5] + *((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v30 = *(_DWORD *)(v29 - 4) >> 1;
  }
  else
  {
    v29 = 0;
    v30 = 0;
  }
  DWORD1(v35) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(
                  this,
                  v29,
                  v30);
  (*(void (__fastcall **)(TMetabaseMetaXmlFile *, __int128 *, __int64))(*(_QWORD *)this + 64LL))(this, &v34, 1);
  *(_QWORD *)v33[0] = v3;
}

```

## disassembly

```asm
0x18001b82c  mov     [rsp-8+arg_10], rbx
0x18001b831  mov     [rsp-8+arg_18], rsi
0x18001b836  push    rbp
0x18001b837  push    rdi
0x18001b838  push    r13
0x18001b83a  push    r14
0x18001b83c  push    r15
0x18001b83e  lea     rbp, [rsp-37h]
0x18001b843  sub     rsp, 100h
0x18001b84a  mov     rax, cs:__security_cookie
0x18001b851  xor     rax, rsp
0x18001b854  mov     [rbp+57h+var_30], rax
0x18001b858  mov     [rbp+57h+var_70], rdx
0x18001b85c  mov     rbx, rcx
0x18001b85f  mov     rax, [rcx+0A18h]
0x18001b866  mov     edi, [rax+20h]
0x18001b869  add     rdi, rax
0x18001b86c  xor     r15d, r15d
0x18001b86f  mov     r13d, r15d
0x18001b872  mov     rsi, [rbx+0A18h]
0x18001b879  cmp     r13d, [rsi+24h]
0x18001b87d  jnb     loc_18001BBBC
0x18001b883  lea     rcx, [rbx+228h]; this
0x18001b88a  lea     r14, [rsi+38h]
0x18001b88e  cmp     [rdi], r15d
0x18001b891  jnz     short loc_18001B898
0x18001b893  mov     rdx, r15
0x18001b896  jmp     short loc_18001B8A4
0x18001b898  mov     r15d, [rdi]
0x18001b89b  mov     edx, [r14]
0x18001b89e  add     rdx, rsi
0x18001b8a1  add     rdx, r15; unsigned __int16 *
0x18001b8a4  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBG@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *)
0x18001b8a9  test    al, al
0x18001b8ab  jz      loc_18001BA09
0x18001b8b1  xorps   xmm0, xmm0
0x18001b8b4  movups  [rbp+57h+var_60], xmm0
0x18001b8b8  movups  [rbp+57h+var_50], xmm0
0x18001b8bc  movups  [rbp+57h+var_40], xmm0
0x18001b8c0  mov     rax, [rbx]
0x18001b8c3  cmp     dword ptr [rdi], 0
0x18001b8c6  jnz     short loc_18001B8D3
0x18001b8c8  xor     r15d, r15d
0x18001b8cb  mov     edx, r15d
0x18001b8ce  mov     r8d, r15d
0x18001b8d1  jmp     short loc_18001B8ED
0x18001b8d3  mov     edx, [r14]
0x18001b8d6  add     rdx, rsi
0x18001b8d9  add     rdx, r15
0x18001b8dc  mov     ecx, [r14]
0x18001b8df  add     rcx, rsi
0x18001b8e2  mov     r8d, [rcx+r15-4]
0x18001b8e7  shr     r8d, 1
0x18001b8ea  xor     r15d, r15d
0x18001b8ed  mov     rcx, rbx
0x18001b8f0  mov     rax, [rax+28h]
0x18001b8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f9  mov     dword ptr [rbp+57h+var_60], eax
0x18001b8fc  mov     ecx, [rdi+4]
0x18001b8ff  cmp     ecx, [rdi]
0x18001b901  jz      short loc_18001B941
0x18001b903  mov     rax, [rbx]
0x18001b906  test    ecx, ecx
0x18001b908  jnz     short loc_18001B912
0x18001b90a  mov     rdx, r15
0x18001b90d  mov     r8d, r15d
0x18001b910  jmp     short loc_18001B935
0x18001b912  mov     r9, [rbx+0A18h]
0x18001b919  mov     r8, rcx
0x18001b91c  mov     edx, [r9+38h]
0x18001b920  add     rdx, rcx
0x18001b923  add     rdx, r9
0x18001b926  mov     ecx, [r9+38h]
0x18001b92a  add     rcx, r8
0x18001b92d  mov     r8d, [rcx+r9-4]
0x18001b932  shr     r8d, 1
0x18001b935  mov     rcx, rbx
0x18001b938  mov     rax, [rax+28h]
0x18001b93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b941  mov     dword ptr [rbp+57h+var_60+4], eax
0x18001b944  mov     rax, [rbx]
0x18001b947  cmp     [rdi+8], r15d
0x18001b94b  jnz     short loc_18001B952
0x18001b94d  mov     rdx, r15
0x18001b950  jmp     short loc_18001B966
0x18001b952  mov     r8, [rbx+0A18h]
0x18001b959  mov     ecx, [r8+38h]
0x18001b95d  mov     edx, [rdi+8]
0x18001b960  add     rcx, r8
0x18001b963  add     rdx, rcx
0x18001b966  mov     edx, [rdx]
0x18001b968  mov     rcx, rbx
0x18001b96b  mov     rax, [rax+10h]
0x18001b96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b974  mov     dword ptr [rbp+57h+var_60+8], eax
0x18001b977  mov     rax, [rbx]
0x18001b97a  cmp     [rdi+0Ch], r15d
0x18001b97e  jnz     short loc_18001B985
0x18001b980  mov     rdx, r15
0x18001b983  jmp     short loc_18001B999
0x18001b985  mov     r8, [rbx+0A18h]
0x18001b98c  mov     ecx, [r8+38h]
0x18001b990  mov     edx, [rdi+0Ch]
0x18001b993  add     rcx, r8
0x18001b996  add     rdx, rcx
0x18001b999  mov     edx, [rdx]
0x18001b99b  mov     rcx, rbx
0x18001b99e  mov     rax, [rax+10h]
0x18001b9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9a7  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x18001b9aa  mov     rax, [rbx]
0x18001b9ad  cmp     [rdi+14h], r15d
0x18001b9b1  jnz     short loc_18001B9BB
0x18001b9b3  mov     rdx, r15
0x18001b9b6  mov     r8d, r15d
0x18001b9b9  jmp     short loc_18001B9DF
0x18001b9bb  mov     r9, [rbx+0A18h]
0x18001b9c2  mov     r8d, [rdi+14h]
0x18001b9c6  mov     edx, [r9+38h]
0x18001b9ca  add     rdx, r8
0x18001b9cd  add     rdx, r9
0x18001b9d0  mov     ecx, [r9+38h]
0x18001b9d4  add     rcx, r8
0x18001b9d7  mov     r8d, [rcx+r9-4]
0x18001b9dc  shr     r8d, 1
0x18001b9df  mov     rcx, rbx
0x18001b9e2  mov     rax, [rax+28h]
0x18001b9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9eb  mov     dword ptr [rbp+57h+var_50+4], eax
0x18001b9ee  mov     rax, [rbx]
0x18001b9f1  mov     r8d, 1
0x18001b9f7  lea     rdx, [rbp+57h+var_60]
0x18001b9fb  mov     rcx, rbx
0x18001b9fe  mov     rax, [rax+40h]
0x18001ba02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba07  jmp     short loc_18001BA2E
0x18001ba09  lea     rcx, [rbx+238h]; this
0x18001ba10  cmp     dword ptr [rdi], 0
0x18001ba13  jnz     short loc_18001BA19
0x18001ba15  xor     edx, edx
0x18001ba17  jmp     short loc_18001BA22
0x18001ba19  mov     edx, [r14]
0x18001ba1c  add     rdx, rsi
0x18001ba1f  add     rdx, r15; unsigned __int16 *
0x18001ba22  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBG@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *)
0x18001ba27  test    al, al
0x18001ba29  jnz     short loc_18001BA3A
0x18001ba2b  xor     r15d, r15d
0x18001ba2e  inc     r13d
0x18001ba31  add     rdi, 30h ; '0'
0x18001ba35  jmp     loc_18001B872
0x18001ba3a  xorps   xmm0, xmm0
0x18001ba3d  movups  [rbp+57h+var_60], xmm0
0x18001ba41  movups  [rbp+57h+var_50], xmm0
0x18001ba45  movups  [rbp+57h+var_40], xmm0
0x18001ba49  mov     rax, [rbx]
0x18001ba4c  xor     r13d, r13d
0x18001ba4f  cmp     [rdi], r13d
0x18001ba52  jnz     short loc_18001BA5C
0x18001ba54  mov     edx, r13d
0x18001ba57  mov     r8d, r13d
0x18001ba5a  jmp     short loc_18001BA73
0x18001ba5c  mov     edx, [r14]
0x18001ba5f  add     rdx, rsi
0x18001ba62  add     rdx, r15
0x18001ba65  mov     ecx, [r14]
0x18001ba68  add     rcx, rsi
0x18001ba6b  mov     r8d, [rcx+r15-4]
0x18001ba70  shr     r8d, 1
0x18001ba73  mov     rcx, rbx
0x18001ba76  mov     rax, [rax+28h]
0x18001ba7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba7f  mov     dword ptr [rbp+57h+var_60], eax
0x18001ba82  mov     ecx, [rdi+4]
0x18001ba85  cmp     ecx, [rdi]
0x18001ba87  jz      short loc_18001BAC7
0x18001ba89  mov     rax, [rbx]
0x18001ba8c  test    ecx, ecx
0x18001ba8e  jnz     short loc_18001BA98
0x18001ba90  mov     rdx, r13
0x18001ba93  mov     r8d, r13d
0x18001ba96  jmp     short loc_18001BABB
0x18001ba98  mov     r9, [rbx+0A18h]
0x18001ba9f  mov     r8, rcx
0x18001baa2  mov     edx, [r9+38h]
0x18001baa6  add     rdx, r9
0x18001baa9  add     rdx, rcx
0x18001baac  mov     ecx, [r9+38h]
0x18001bab0  add     rcx, r9
0x18001bab3  mov     r8d, [rcx+r8-4]
0x18001bab8  shr     r8d, 1
0x18001babb  mov     rcx, rbx
0x18001babe  mov     rax, [rax+28h]
0x18001bac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bac7  mov     dword ptr [rbp+57h+var_60+4], eax
0x18001baca  mov     rax, [rbx]
0x18001bacd  cmp     [rdi+8], r13d
0x18001bad1  jnz     short loc_18001BAD8
0x18001bad3  mov     rdx, r13
0x18001bad6  jmp     short loc_18001BAEC
0x18001bad8  mov     r8, [rbx+0A18h]
0x18001badf  mov     ecx, [r8+38h]
0x18001bae3  mov     edx, [rdi+8]
0x18001bae6  add     rcx, r8
0x18001bae9  add     rdx, rcx
0x18001baec  mov     edx, [rdx]
0x18001baee  mov     rcx, rbx
0x18001baf1  mov     rax, [rax+10h]
0x18001baf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bafa  mov     dword ptr [rbp+57h+var_60+8], eax
0x18001bafd  mov     rax, [rbx]
0x18001bb00  cmp     [rdi+0Ch], r13d
0x18001bb04  jnz     short loc_18001BB0B
0x18001bb06  mov     rdx, r13
0x18001bb09  jmp     short loc_18001BB1F
0x18001bb0b  mov     r8, [rbx+0A18h]
0x18001bb12  mov     ecx, [r8+38h]
0x18001bb16  mov     edx, [rdi+0Ch]
0x18001bb19  add     rcx, r8
0x18001bb1c  add     rdx, rcx
0x18001bb1f  mov     edx, [rdx]
0x18001bb21  mov     rcx, rbx
0x18001bb24  mov     rax, [rax+10h]
0x18001bb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb2d  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x18001bb30  mov     rax, [rbx]
0x18001bb33  cmp     [rdi+14h], r13d
0x18001bb37  jnz     short loc_18001BB41
0x18001bb39  mov     rdx, r13
0x18001bb3c  mov     r8d, r13d
0x18001bb3f  jmp     short loc_18001BB65
0x18001bb41  mov     r9, [rbx+0A18h]
0x18001bb48  mov     r8d, [rdi+14h]
0x18001bb4c  mov     edx, [r9+38h]
0x18001bb50  add     rdx, r9
0x18001bb53  add     rdx, r8
0x18001bb56  mov     ecx, [r9+38h]
0x18001bb5a  add     rcx, r9
0x18001bb5d  mov     r8d, [rcx+r8-4]
0x18001bb62  shr     r8d, 1
0x18001bb65  mov     rcx, rbx
0x18001bb68  mov     rax, [rax+28h]
0x18001bb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb71  mov     dword ptr [rbp+57h+var_50+4], eax
0x18001bb74  mov     rax, [rbx]
0x18001bb77  mov     r8d, 1
0x18001bb7d  lea     rdx, [rbp+57h+var_60]
0x18001bb81  mov     rcx, rbx
0x18001bb84  mov     rax, [rax+40h]
0x18001bb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb8d  mov     rax, [rbp+57h+var_70]
0x18001bb91  mov     [rax], rdi
0x18001bb94  mov     rcx, [rbp+57h+var_30]
0x18001bb98  xor     rcx, rsp; StackCookie
0x18001bb9b  call    __security_check_cookie
0x18001bba0  lea     r11, [rsp+120h+var_20]
0x18001bba8  mov     rbx, [r11+40h]
0x18001bbac  mov     rsi, [r11+48h]
0x18001bbb0  mov     rsp, r11
0x18001bbb3  pop     r15
0x18001bbb5  pop     r14
0x18001bbb7  pop     r13
0x18001bbb9  pop     rdi
0x18001bbba  pop     rbp
0x18001bbbb  retn
0x18001bbbc  mov     [rbp+57h+var_68], r15
0x18001bbc0  or      eax, 0FFFFFFFFh
0x18001bbc3  mov     [rsp+120h+var_80], eax
0x18001bbca  mov     [rsp+120h+var_88], eax
0x18001bbd1  mov     [rsp+120h+var_A0], r15d
0x18001bbd9  mov     [rsp+120h+var_A8], r15
0x18001bbde  mov     [rsp+120h+var_B0], eax
0x18001bbe2  mov     [rsp+120h+var_B8], eax
0x18001bbe6  mov     [rsp+120h+var_C0], r15d
0x18001bbeb  mov     [rsp+120h+var_C8], r15
0x18001bbf0  mov     [rsp+120h+var_D0], r15d
0x18001bbf5  lea     rax, word_180034198
0x18001bbfc  mov     [rsp+120h+var_D8], rax
0x18001bc01  mov     [rsp+120h+var_E0], rax
0x18001bc06  mov     [rsp+120h+var_E8], rax
0x18001bc0b  lea     rax, aMetabasebasecl; "MetabaseBaseClass"
0x18001bc12  mov     [rsp+120h+var_F0], rax
0x18001bc17  mov     [rsp+120h+var_F8], 0C00210D3h
0x18001bc1f  mov     [rsp+120h+var_100], 3
0x18001bc27  mov     r9d, 80210861h
0x18001bc2d  mov     r8, [rbx+0A28h]
0x18001bc34  xor     edx, edx
0x18001bc36  lea     rcx, [rbp+57h+var_70]
0x18001bc3a  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001bc3f  nop
0x18001bc40  mov     ebx, 5A7h
0x18001bc45  mov     r9d, 400000h; unsigned int
0x18001bc4b  mov     r8d, ebx; unsigned int
0x18001bc4e  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001bc55  lea     rcx, [rbp+57h+var_70]; this
0x18001bc59  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001bc5e  nop
0x18001bc5f  lea     rcx, [rbp+57h+var_70]; this
0x18001bc63  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001bc68  xor     r9d, r9d; unsigned int
  ... truncated ...
```
