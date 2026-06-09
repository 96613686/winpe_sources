# W3_ISAPI_HANDLER::InitCoreData(int *,int,ulong,long,int *)

- ea: `0x18000b8f0`
- end: `0x18000bd86`
- name: `?InitCoreData@W3_ISAPI_HANDLER@@QEAAJPEAHHKJ0@Z`
- size: `1174`
- prototype: `__int64 __fastcall(W3_ISAPI_HANDLER *this, int *, int, int, int, struct ISAPI_META_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b3d0`

## callees

- `0x18000b8f0`
- `0x1800107c8`
- `0x180013010`

## import_xrefs

- `msvcrt!strtoul` at `0x18000bb4d`
- `msvcrt!strtoul` at `0x18000bb4d`
- `msvcrt!_errno` at `0x18000bb3b`
- `msvcrt!_errno` at `0x18000bb6b`
- `msvcrt!_errno` at `0x18000bb3b`
- `msvcrt!_errno` at `0x18000bb6b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000bcbd`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000bcbd`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x18000bca6`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x18000bca6`

## string_xrefs

- `0x18000bc16`: `PATH_INFO`
- `0x18000bccb`: `PATH_TRANSLATED`

## pseudocode

```c
__int64 __fastcall W3_ISAPI_HANDLER::InitCoreData(
        W3_ISAPI_HANDLER *this,
        int *a2,
        int a3,
        int a4,
        int a5,
        struct ISAPI_META_CONTEXT *a6)
{
  __int64 v7; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  struct ISAPI_META_CONTEXT *v11; // r14
  __int64 v12; // r15
  int ParsedData; // edi
  unsigned int *v14; // rsi
  struct IHttpContext *v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  struct ISAPI_META_CONTEXT *v18; // rcx
  unsigned int v19; // edx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  const char *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // [rsp+80h] [rbp+40h] BYREF
  int *v44; // [rsp+88h] [rbp+48h] BYREF
  int v45; // [rsp+90h] [rbp+50h] BYREF

  v45 = a3;
  v44 = a2;
  v7 = *((_QWORD *)this + 1);
  LOWORD(v45) = 0;
  LODWORD(v44) = 0;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v11 = a6;
  v12 = v10;
  ParsedData = a5;
  *(_DWORD *)a6 = 0;
  if ( ParsedData != -2147024858 )
  {
    if ( ParsedData < 0 )
      goto LABEL_27;
    if ( !*((_DWORD *)this + 10) )
    {
      *((_DWORD *)this + 12) += a4;
      v14 = (unsigned int *)((char *)this + 44);
      goto LABEL_11;
    }
    v15 = (struct IHttpContext *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 3) = (char *)this + 64;
    a6 = 0;
    ParsedData = ISAPI_META_CONTEXT::GetParsedData(v15, &a6);
    if ( ParsedData < 0 )
      goto LABEL_27;
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 144LL))(v16);
    v18 = a6;
    v14 = (unsigned int *)((char *)this + 44);
    *((_DWORD *)this + 11) = v17;
    v19 = *((_DWORD *)v18 + 2);
    if ( v17 <= v19 )
      v19 = v17;
    else
      *v14 = v19;
    if ( v19 )
      *((_QWORD *)this + 7) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
LABEL_11:
    while ( 1 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 144LL))(v20) || *((_DWORD *)this + 12) >= *v14 )
        break;
      v21 = *((_QWORD *)this + 1);
      *((_DWORD *)this + 10) = 0;
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
      v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int **, struct ISAPI_META_CONTEXT *))(*(_QWORD *)v22 + 128LL))(
              v22,
              *((_QWORD *)this + 7) + *((unsigned int *)this + 12),
              *v14 - *((_DWORD *)this + 12),
              1,
              &v44,
              v11);
      ParsedData = v23;
      if ( v23 == -2147024858 )
      {
        *(_DWORD *)v11 = 0;
        break;
      }
      if ( v23 < 0 )
        goto LABEL_27;
      if ( *(_DWORD *)v11 )
        return 0;
      if ( !(_DWORD)v44 )
        break;
      *((_DWORD *)this + 12) += (_DWORD)v44;
    }
  }
  *(_QWORD *)(*((_QWORD *)this + 3) + 88LL) = *((_QWORD *)this + 7);
  *(_DWORD *)(*((_QWORD *)this + 3) + 80LL) = *((_DWORD *)this + 12);
  **((_DWORD **)this + 3) = *(unsigned __int16 *)(v12 + 32);
  *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = *(unsigned __int16 *)(v12 + 34);
  v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
  if ( (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v25 + 16LL))(v25, 6, &v45) && (_WORD)v45 )
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + 8LL) = -1;
  }
  else
  {
    v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
    v27 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, 11);
    if ( v27 )
    {
      *_errno() = 0;
      *(_DWORD *)(*((_QWORD *)this + 3) + 8LL) = strtoul(v27, 0, 10);
      if ( ((*(_DWORD *)(*((_QWORD *)this + 3) + 8LL) + 1) & 0xFFFFFFFE) == 0 && *_errno() == 34 )
      {
        ParsedData = -2147024362;
        goto LABEL_27;
      }
    }
    else
    {
      *(_DWORD *)(*((_QWORD *)this + 3) + 8LL) = 0;
    }
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 160LL))(*((_QWORD *)this + 1));
  v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v30 = **((_QWORD **)this + 1);
  if ( v29 )
  {
    v31 = (*(__int64 (**)(void))(v30 + 160))();
    v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 56LL))(v32);
  }
  else
  {
    v34 = (*(__int64 (**)(void))(v30 + 48))();
    v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
  }
  *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) = v33;
  *(_QWORD *)(*((_QWORD *)this + 3) + 24LL) = *((_QWORD *)this + 51);
  v35 = *((_QWORD *)this + 1);
  v36 = *((_QWORD *)this + 3);
  v43 = 0;
  ParsedData = (*(__int64 (__fastcall **)(__int64, const char *, __int64, int *))(*(_QWORD *)v35 + 120LL))(
                 v35,
                 "PATH_INFO",
                 v36 + 32,
                 &v43);
  if ( ParsedData >= 0 )
  {
    v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
    *(_QWORD *)(*((_QWORD *)this + 3) + 40LL) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 64LL))(v37);
    v38 = *(_QWORD *)(v12 + 96);
    if ( !v38
      || !*(_WORD *)(v12 + 70)
      || (ParsedData = STRA::CopyWTruncate(
                         (W3_ISAPI_HANDLER *)((char *)this + 160),
                         (const unsigned __int16 *)(v38 + 2),
                         (*(unsigned __int16 *)(v12 + 70) >> 1) - 1),
          ParsedData >= 0) )
    {
      *(_QWORD *)(*((_QWORD *)this + 3) + 48LL) = STRA::QueryStr((W3_ISAPI_HANDLER *)((char *)this + 160));
      ParsedData = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, int *))(**((_QWORD **)this + 1) + 120LL))(
                     *((_QWORD *)this + 1),
                     "PATH_TRANSLATED",
                     *((_QWORD *)this + 3) + 56LL,
                     &v43);
      if ( ParsedData >= 0 )
      {
        v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
        *(_QWORD *)(*((_QWORD *)this + 3) + 64LL) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 16LL))(
                                                      v39,
                                                      12);
        v40 = *((_QWORD *)this + 3);
        if ( !*(_QWORD *)(v40 + 64) )
          *(_QWORD *)(v40 + 64) = word_180016DBA;
        v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
        *(_QWORD *)(*((_QWORD *)this + 3) + 72LL) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 16LL))(
                                                      v41,
                                                      1);
        v42 = *((_QWORD *)this + 3);
        if ( !*(_QWORD *)(v42 + 72) )
          *(_QWORD *)(v42 + 72) = word_180016DBA;
        return (unsigned int)ParsedData;
      }
    }
  }
LABEL_27:
  *((_QWORD *)this + 3) = 0;
  return (unsigned int)ParsedData;
}

```

## disassembly

```asm
0x18000b8f0  mov     [rsp-38h+arg_10], r8d
0x18000b8f5  mov     [rsp-38h+arg_8], rdx
0x18000b8fa  push    rbp
0x18000b8fb  push    rbx
0x18000b8fc  push    rsi
0x18000b8fd  push    rdi
0x18000b8fe  push    r12
0x18000b900  push    r14
0x18000b902  push    r15
0x18000b904  mov     rbp, rsp
0x18000b907  sub     rsp, 40h
0x18000b90b  mov     rbx, rcx
0x18000b90e  xor     r12d, r12d
0x18000b911  mov     rcx, [rcx+8]
0x18000b915  mov     esi, r9d
0x18000b918  mov     word ptr [rbp+arg_10], r12w
0x18000b91d  mov     dword ptr [rbp+arg_8], r12d
0x18000b921  mov     rax, [rcx]
0x18000b924  mov     rax, [rax+18h]
0x18000b928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b92d  mov     rdx, rax
0x18000b930  mov     rcx, [rax]
0x18000b933  mov     rax, [rcx+8]
0x18000b937  mov     rcx, rdx
0x18000b93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b93f  mov     r14, [rbp+arg_28]
0x18000b943  mov     r15, rax
0x18000b946  mov     edi, [rbp+arg_20]
0x18000b949  mov     [r14], r12d
0x18000b94c  cmp     edi, 80070026h
0x18000b952  jz      loc_18000BA96
0x18000b958  test    edi, edi
0x18000b95a  js      loc_18000BB7B
0x18000b960  cmp     [rbx+28h], r12d
0x18000b964  jnz     short loc_18000B96F
0x18000b966  add     [rbx+30h], esi
0x18000b969  lea     rsi, [rbx+2Ch]
0x18000b96d  jmp     short loc_18000B9E9
0x18000b96f  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000b973  lea     rax, [rbx+40h]
0x18000b977  lea     rdx, [rbp+arg_28]; struct ISAPI_META_CONTEXT **
0x18000b97b  mov     [rbx+18h], rax
0x18000b97f  mov     [rbp+arg_28], r12
0x18000b983  call    ?GetParsedData@ISAPI_META_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@@Z; ISAPI_META_CONTEXT::GetParsedData(IHttpContext *,ISAPI_META_CONTEXT * *)
0x18000b988  mov     edi, eax
0x18000b98a  test    eax, eax
0x18000b98c  js      loc_18000BB7B
0x18000b992  mov     rcx, [rbx+8]
0x18000b996  mov     rax, [rcx]
0x18000b999  mov     rax, [rax+18h]
0x18000b99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a2  mov     rdx, rax
0x18000b9a5  mov     rcx, [rax]
0x18000b9a8  mov     rax, [rcx+90h]
0x18000b9af  mov     rcx, rdx
0x18000b9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9b7  mov     rcx, [rbp+arg_28]
0x18000b9bb  lea     rsi, [rbx+2Ch]
0x18000b9bf  mov     [rsi], eax
0x18000b9c1  mov     edx, [rcx+8]
0x18000b9c4  cmp     eax, edx
0x18000b9c6  jbe     short loc_18000B9CC
0x18000b9c8  mov     [rsi], edx
0x18000b9ca  jmp     short loc_18000B9CE
0x18000b9cc  mov     edx, eax
0x18000b9ce  test    edx, edx
0x18000b9d0  jz      short loc_18000B9E9
0x18000b9d2  mov     rcx, [rbx+8]
0x18000b9d6  mov     rax, [rcx]
0x18000b9d9  mov     rax, [rax+90h]
0x18000b9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e5  mov     [rbx+38h], rax
0x18000b9e9  mov     rcx, [rbx+8]
0x18000b9ed  mov     rax, [rcx]
0x18000b9f0  mov     rax, [rax+18h]
0x18000b9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f9  mov     rdx, rax
0x18000b9fc  mov     rcx, [rax]
0x18000b9ff  mov     rax, [rcx+90h]
0x18000ba06  mov     rcx, rdx
0x18000ba09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba0e  test    eax, eax
0x18000ba10  jz      loc_18000BA96
0x18000ba16  mov     eax, [rsi]
0x18000ba18  cmp     [rbx+30h], eax
0x18000ba1b  jnb     short loc_18000BA96
0x18000ba1d  mov     rcx, [rbx+8]
0x18000ba21  mov     [rbx+28h], r12d
0x18000ba25  mov     rax, [rcx]
0x18000ba28  mov     rax, [rax+18h]
0x18000ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba31  mov     edx, [rbx+30h]
0x18000ba34  mov     r10, rax
0x18000ba37  mov     r8d, [rsi]
0x18000ba3a  mov     r9d, 1
0x18000ba40  sub     r8d, edx
0x18000ba43  mov     [rsp+40h+var_18], r14
0x18000ba48  mov     rcx, [rax]
0x18000ba4b  add     rdx, [rbx+38h]
0x18000ba4f  mov     rax, [rcx+80h]
0x18000ba56  lea     rcx, [rbp+arg_8]
0x18000ba5a  mov     [rsp+40h+var_20], rcx
0x18000ba5f  mov     rcx, r10
0x18000ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba67  mov     edi, eax
0x18000ba69  cmp     eax, 80070026h
0x18000ba6e  jz      short loc_18000BA93
0x18000ba70  test    eax, eax
0x18000ba72  js      loc_18000BB7B
0x18000ba78  cmp     [r14], r12d
0x18000ba7b  jnz     short loc_18000BA8C
0x18000ba7d  mov     eax, dword ptr [rbp+arg_8]
0x18000ba80  test    eax, eax
0x18000ba82  jz      short loc_18000BA96
0x18000ba84  add     [rbx+30h], eax
0x18000ba87  jmp     loc_18000B9E9
0x18000ba8c  xor     eax, eax
0x18000ba8e  jmp     loc_18000BB81
0x18000ba93  mov     [r14], r12d
0x18000ba96  mov     rax, [rbx+38h]
0x18000ba9a  mov     rcx, [rbx+18h]
0x18000ba9e  mov     [rcx+58h], rax
0x18000baa2  mov     rcx, [rbx+18h]
0x18000baa6  mov     eax, [rbx+30h]
0x18000baa9  mov     [rcx+50h], eax
0x18000baac  movzx   ecx, word ptr [r15+20h]
0x18000bab1  mov     rax, [rbx+18h]
0x18000bab5  mov     [rax], ecx
0x18000bab7  mov     rax, [rbx+18h]
0x18000babb  movzx   ecx, word ptr [r15+22h]
0x18000bac0  mov     [rax+4], ecx
0x18000bac3  mov     rcx, [rbx+8]
0x18000bac7  mov     rax, [rcx]
0x18000baca  mov     rax, [rax+18h]
0x18000bace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad3  mov     r9, rax
0x18000bad6  lea     r8, [rbp+arg_10]
0x18000bada  mov     edx, 6
0x18000badf  mov     rcx, [rax]
0x18000bae2  mov     rax, [rcx+10h]
0x18000bae6  mov     rcx, r9
0x18000bae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baee  test    rax, rax
0x18000baf1  jz      short loc_18000BB0A
0x18000baf3  cmp     word ptr [rbp+arg_10], r12w
0x18000baf8  jz      short loc_18000BB0A
0x18000bafa  mov     rax, [rbx+18h]
0x18000bafe  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18000bb05  jmp     loc_18000BB98
0x18000bb0a  mov     rcx, [rbx+8]
0x18000bb0e  mov     rax, [rcx]
0x18000bb11  mov     rax, [rax+18h]
0x18000bb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb1a  mov     r9, rax
0x18000bb1d  xor     r8d, r8d
0x18000bb20  mov     rcx, [rax]
0x18000bb23  lea     edx, [r8+0Bh]
0x18000bb27  mov     rax, [rcx+10h]
0x18000bb2b  mov     rcx, r9
0x18000bb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb33  mov     rdi, rax
0x18000bb36  test    rax, rax
0x18000bb39  jz      short loc_18000BB90
0x18000bb3b  call    cs:__imp__errno
0x18000bb41  xor     edx, edx; EndPtr
0x18000bb43  mov     rcx, rdi; String
0x18000bb46  mov     [rax], r12d
0x18000bb49  lea     r8d, [rdx+0Ah]; Radix
0x18000bb4d  call    cs:__imp_strtoul
0x18000bb53  mov     rcx, [rbx+18h]
0x18000bb57  mov     [rcx+8], eax
0x18000bb5a  mov     rax, [rbx+18h]
0x18000bb5e  mov     ecx, [rax+8]
0x18000bb61  inc     ecx
0x18000bb63  test    ecx, 0FFFFFFFEh
0x18000bb69  jnz     short loc_18000BB98
0x18000bb6b  call    cs:__imp__errno
0x18000bb71  cmp     dword ptr [rax], 22h ; '"'
0x18000bb74  jnz     short loc_18000BB98
0x18000bb76  mov     edi, 80070216h
0x18000bb7b  mov     [rbx+18h], r12
0x18000bb7f  mov     eax, edi
0x18000bb81  add     rsp, 40h
0x18000bb85  pop     r15
0x18000bb87  pop     r14
0x18000bb89  pop     r12
0x18000bb8b  pop     rdi
0x18000bb8c  pop     rsi
0x18000bb8d  pop     rbx
0x18000bb8e  pop     rbp
0x18000bb8f  retn
0x18000bb90  mov     rax, [rbx+18h]
0x18000bb94  mov     [rax+8], r12d
0x18000bb98  mov     rcx, [rbx+8]
0x18000bb9c  mov     rax, [rcx]
0x18000bb9f  mov     rax, [rax+0A0h]
0x18000bba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbab  mov     rdx, rax
0x18000bbae  mov     rcx, [rax]
0x18000bbb1  mov     rax, [rcx+10h]
0x18000bbb5  mov     rcx, rdx
0x18000bbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbbd  mov     rcx, [rbx+8]
0x18000bbc1  mov     rdx, [rcx]
0x18000bbc4  test    rax, rax
0x18000bbc7  jz      short loc_18000BBF3
0x18000bbc9  mov     rax, [rdx+0A0h]
0x18000bbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbd5  mov     rdx, rax
0x18000bbd8  mov     rcx, [rax]
0x18000bbdb  mov     rax, [rcx+10h]
0x18000bbdf  mov     rcx, rdx
0x18000bbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbe7  mov     rdx, rax
0x18000bbea  mov     rcx, [rax]
0x18000bbed  mov     rax, [rcx+38h]
0x18000bbf1  jmp     short loc_18000BC06
0x18000bbf3  mov     rax, [rdx+30h]
0x18000bbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbfc  mov     rdx, rax
0x18000bbff  mov     rcx, [rax]
0x18000bc02  mov     rax, [rcx+20h]
0x18000bc06  mov     rcx, rdx
0x18000bc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc0e  mov     rcx, [rbx+18h]
0x18000bc12  lea     r9, [rbp+arg_0]
0x18000bc16  lea     rdx, aPathInfo; "PATH_INFO"
0x18000bc1d  mov     [rcx+10h], rax
0x18000bc21  mov     rcx, [rbx+18h]
0x18000bc25  mov     rax, [rbx+198h]
0x18000bc2c  mov     [rcx+18h], rax
0x18000bc30  mov     rcx, [rbx+8]
0x18000bc34  mov     r8, [rbx+18h]
0x18000bc38  mov     [rbp+arg_0], r12d
0x18000bc3c  add     r8, 20h ; ' '
0x18000bc40  mov     rax, [rcx]
0x18000bc43  mov     rax, [rax+78h]
0x18000bc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4c  mov     edi, eax
0x18000bc4e  test    eax, eax
0x18000bc50  js      loc_18000BB7B
0x18000bc56  mov     rcx, [rbx+8]
0x18000bc5a  mov     rax, [rcx]
0x18000bc5d  mov     rax, [rax+18h]
0x18000bc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc66  mov     rdx, rax
0x18000bc69  mov     rcx, [rax]
0x18000bc6c  mov     rax, [rcx+40h]
0x18000bc70  mov     rcx, rdx
0x18000bc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc78  mov     rcx, [rbx+18h]
0x18000bc7c  mov     [rcx+28h], rax
0x18000bc80  mov     rdx, [r15+60h]
0x18000bc84  test    rdx, rdx
0x18000bc87  jz      short loc_18000BCB6
0x18000bc89  cmp     [r15+46h], r12w
0x18000bc8e  jz      short loc_18000BCB6
0x18000bc90  movzx   r8d, word ptr [r15+46h]
0x18000bc95  lea     rcx, [rbx+0A0h]
0x18000bc9c  shr     r8d, 1
0x18000bc9f  add     rdx, 2
0x18000bca3  dec     r8d
0x18000bca6  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x18000bcac  mov     edi, eax
0x18000bcae  test    eax, eax
0x18000bcb0  js      loc_18000BB7B
0x18000bcb6  lea     rcx, [rbx+0A0h]
0x18000bcbd  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000bcc3  mov     rcx, [rbx+18h]
0x18000bcc7  lea     r9, [rbp+arg_0]
0x18000bccb  lea     rdx, aPathTranslated; "PATH_TRANSLATED"
0x18000bcd2  mov     [rcx+30h], rax
0x18000bcd6  mov     rcx, [rbx+8]
0x18000bcda  mov     r8, [rbx+18h]
0x18000bcde  add     r8, 38h ; '8'
0x18000bce2  mov     rax, [rcx]
0x18000bce5  mov     rax, [rax+78h]
0x18000bce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcee  mov     edi, eax
0x18000bcf0  test    eax, eax
0x18000bcf2  js      loc_18000BB7B
0x18000bcf8  mov     rcx, [rbx+8]
0x18000bcfc  mov     rax, [rcx]
0x18000bcff  mov     rax, [rax+18h]
0x18000bd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd08  mov     r9, rax
0x18000bd0b  xor     r8d, r8d
0x18000bd0e  mov     rcx, [rax]
0x18000bd11  lea     edx, [r8+0Ch]
0x18000bd15  mov     rax, [rcx+10h]
0x18000bd19  mov     rcx, r9
0x18000bd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd21  mov     rcx, [rbx+18h]
0x18000bd25  lea     rsi, word_180016DBA
0x18000bd2c  mov     [rcx+40h], rax
0x18000bd30  mov     rax, [rbx+18h]
0x18000bd34  cmp     [rax+40h], r12
0x18000bd38  jnz     short loc_18000BD3E
0x18000bd3a  mov     [rax+40h], rsi
0x18000bd3e  mov     rcx, [rbx+8]
  ... truncated ...
```
