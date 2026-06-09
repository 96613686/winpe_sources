# W3_DEFAULT_DOC_HANDLER::DoWork(IHttpContext *,DEFDOC_META_STORED_CONTEXT *,int,ulong,long)

- ea: `0x180002504`
- end: `0x180002d93`
- name: `?DoWork@W3_DEFAULT_DOC_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVDEFDOC_META_STORED_CONTEXT@@HKJ@Z`
- size: `2191`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002240`

## callees

- `0x180002504`
- `0x1800032a6`
- `0x1800032d0`
- `0x180003360`
- `0x180004010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800029ce`
- `msvcrt!wcschr` at `0x180002bbb`
- `msvcrt!wcschr` at `0x1800029ce`
- `msvcrt!wcschr` at `0x180002bbb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000287d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000288c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000287d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000288c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cc4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cd8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d2a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d4d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d57`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d61`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cc4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002cd8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d2a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d4d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d57`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002d61`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800029e9`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002bd4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002bfa`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800029e9`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002bd4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002bfa`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180002970`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180002970`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000281e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000281e`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x180002807`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x180002807`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800029b6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800029f1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002b86`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800029b6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800029f1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002b86`
- `iisutil!FlipSlashes` at `0x180002a05`
- `iisutil!FlipSlashes` at `0x180002a05`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002574`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800025f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000261d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002574`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800025f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000261d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000272b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000298b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000272b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000298b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800027f9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800027f9`

## string_xrefs

- `0x18000282d`: `Moved Permanently`

## pseudocode

```c
__int64 __fastcall W3_DEFAULT_DOC_HANDLER::DoWork(__int64 a1, __int64 *a2, __int64 a3, int a4, __int64 a5, int a6)
{
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // r15
  unsigned int v14; // r13d
  int v15; // ebx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  const wchar_t *v25; // r15
  wchar_t *v26; // rax
  int v27; // eax
  __int64 (__fastcall *v28)(struct IHttpServer *, unsigned __int16 *, __int64, __int64, __int64, __int64, int, __int64 *, __int64); // rdi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // r9
  const char *v38; // r8
  __int64 v39; // rdx
  bool v40; // zf
  void (*v41)(void); // rax
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rdi
  __int64 v45; // rax
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h]
  int v49; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v53; // [rsp+78h] [rbp-88h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+90h] [rbp-70h]
  _BYTE v57[32]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *Str; // [rsp+B8h] [rbp-48h]
  unsigned int v59; // [rsp+C8h] [rbp-38h]
  _BYTE v60[32]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v61; // [rsp+F0h] [rbp-10h]
  int v62; // [rsp+100h] [rbp+0h]
  _BYTE v63[32]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v64; // [rsp+128h] [rbp+28h]
  _BYTE v65[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v66[264]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v67[264]; // [rsp+390h] [rbp+290h] BYREF
  char v68[1024]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v69[1024]; // [rsp+9A0h] [rbp+8A0h] BYREF

  v52 = a3;
  v56 = a1;
  memset_0(v66, 0, 0x208u);
  STRU::STRU((STRU *)v65, v66, 0x104u);
  v9 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
  v10 = *a2;
  v11 = v9;
  v55 = v9;
  v12 = (*(__int64 (__fastcall **)(__int64 *))(v10 + 32))(a2);
  v13 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 208))(a2);
  v53 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a2 + 184))(a2, 0);
  memset_0(v69, 0, sizeof(v69));
  STRU::STRU((STRU *)v57, v69, 0x400u);
  memset_0(v67, 0, 0x208u);
  STRU::STRU((STRU *)v60, v67, 0x104u);
  v14 = 0;
  v47 = 0;
  v49 = 0;
  if ( a4 )
  {
    if ( a6 < 0 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12) + 536) = 0;
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
        v12,
        500,
        "Internal Server Error",
        0,
        a6,
        0,
        0);
    }
    (*(void (__fastcall **)(__int64 *))(*a2 + 200))(a2);
    goto LABEL_61;
  }
  v14 = 2;
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 56LL))(v13) & 2) != 0 )
  {
    v15 = -2147024894;
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12) + 536) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
      v12,
      404,
      "Not Found",
      0,
      -2147024894,
      0,
      0);
    goto LABEL_33;
  }
  if ( *(_DWORD *)(a3 + 8) )
  {
    v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a2 + 176))(a2, 0);
    v15 = STRU::Copy((STRU *)v57, v16);
    if ( v15 < 0 )
      goto LABEL_33;
    if ( v59 && Str[v59 - 1] != 47 )
    {
      if ( (unsigned int)(*(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) + 36) - 4) <= 1 )
      {
        STRA::STRA((STRA *)v63, v68, 0x400u);
        v15 = STRA::CopyWToUTF8Escaped((STRA *)v63, (const struct STRU *)v57);
        if ( v15 < 0
          || (v15 = STRA::Append((STRA *)v63, "/"), v15 < 0)
          || ((*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
                v12,
                301,
                "Moved Permanently",
                0,
                0,
                0,
                0),
              v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v12 + 152LL))(
                      v12,
                      v64,
                      0,
                      1),
              v15 < 0) )
        {
          STRA::~STRA((STRA *)v63);
          goto LABEL_33;
        }
        STRA::~STRA((STRA *)v63);
      }
      else
      {
        *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12) + 536) = 0;
        (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
          v12,
          405,
          "Method Not Allowed",
          0,
          -2147024895,
          0,
          0);
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
        *(_QWORD *)(v17 + 224) = "GET, HEAD, OPTIONS, TRACE";
        *(_WORD *)(v17 + 216) = 25;
      }
LABEL_55:
      if ( v49 )
      {
        STRU::~STRU((STRU *)v60);
        STRU::~STRU((STRU *)v57);
        STRU::~STRU((STRU *)v65);
        return 1;
      }
      (*(void (__fastcall **)(__int64 *))(*a2 + 200))(a2);
      v14 = 0;
      goto LABEL_61;
    }
    v18 = *a2;
    v48 = 1;
    v19 = (*(__int64 (__fastcall **)(__int64 *))(v18 + 48))(a2);
    v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
    v51 = 0;
    if ( v54 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 48))(a2);
      v51 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v20 + 80LL))(v20, "SID");
    }
    v21 = *a2;
    v50 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *))(v21 + 160))(a2);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22) )
    {
      v23 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 160))(a2);
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 56LL))(v24);
    }
    v25 = MULTISZ::First((MULTISZ *)(v52 + 16));
    if ( v25 )
    {
      while ( 1 )
      {
        v15 = STRU::Copy((STRU *)v60, v53);
        if ( v15 < 0 )
          break;
        if ( v61[v62 - 1] != 92 )
        {
          v15 = STRU::Append((STRU *)v60, L"\\");
          if ( v15 < 0 )
            break;
        }
        v26 = wcschr(v25, 0x3Fu);
        v27 = v26 ? STRU::Append((STRU *)v60, v25, v26 - v25) : STRU::Append((STRU *)v60, v25);
        v15 = v27;
        if ( v27 < 0 )
          break;
        FlipSlashes(v61);
        v28 = *(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, __int64, __int64, __int64, __int64, int, __int64 *, __int64))(*(_QWORD *)g_pGlobalInfo + 64LL);
        v29 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 272))(a2);
        v30 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 160))(a2);
        v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
        v32 = v28(g_pGlobalInfo, v61, v54, v51, v31, v50, 1, &v47, v29);
        v15 = v32;
        if ( v32 >= 0 )
        {
          v40 = ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 56LL))(v47) & 0x10) == 0;
          v41 = *(void (**)(void))(*(_QWORD *)v47 + 16LL);
          if ( v40 )
          {
            v41();
            v47 = 0;
            v15 = STRU::Append((STRU *)v57, v25);
            if ( v15 < 0 )
              break;
            v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 8LL))(v55);
            if ( *(_WORD *)(v43 + 70) )
            {
              if ( wcschr(Str, 0x3Fu) )
              {
                v15 = STRU::Append((STRU *)v57, L"&", 1u);
                if ( v15 < 0 )
                  break;
                v15 = STRU::Append(
                        (STRU *)v57,
                        (const unsigned __int16 *)(*(_QWORD *)(v43 + 96) + 2LL),
                        (*(unsigned __int16 *)(v43 + 70) >> 1) - 1);
                if ( v15 < 0 )
                  break;
              }
            }
            v44 = v56;
            v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*a2 + 248))(a2, 71, v56 + 8);
            if ( v15 < 0 )
              break;
            v45 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v44 + 8) + 24LL))(*(_QWORD *)(v44 + 8));
            v15 = (*(__int64 (__fastcall **)(__int64, wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v45 + 88LL))(
                    v45,
                    Str,
                    v59,
                    0);
            if ( v15 < 0 )
              break;
            v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, _QWORD, int *))(*a2 + 104))(
                    a2,
                    1,
                    *(_QWORD *)(v44 + 8),
                    (unsigned int)(v48 << 6),
                    0,
                    &v49);
            if ( v15 < 0 )
              break;
            goto LABEL_55;
          }
          v41();
          v47 = 0;
        }
        else if ( (unsigned int)(v32 + 2147024894) > 1 && v32 != -2147024773 )
        {
          break;
        }
        v42 = -1;
        do
          ++v42;
        while ( v25[v42] );
        v25 += v42 + 1;
        if ( !*v25 )
          goto LABEL_62;
        v48 = 0;
      }
LABEL_33:
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12) + 536) = 0;
      if ( v15 >= 0 || (v33 = (unsigned __int16)v15, (v15 & 0x1FFF0000) != 0x70000) )
        v33 = v15;
      v34 = v33 - 5;
      if ( v34 )
      {
        v35 = v34 - 82;
        if ( !v35 )
        {
          v37 = 0;
          v38 = "URL Too Long";
          v39 = 414;
          goto LABEL_60;
        }
        v36 = v35 - 1239;
        if ( v36 && v36 != 5 )
        {
          v37 = 0;
          v38 = "Internal Server Error";
          v39 = 500;
LABEL_60:
          (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
            v12,
            v39,
            v38,
            v37,
            v15,
            0,
            0);
LABEL_61:
          STRU::~STRU((STRU *)v60);
          STRU::~STRU((STRU *)v57);
          STRU::~STRU((STRU *)v65);
          return v14;
        }
      }
      v39 = 401;
      v38 = "Unauthorized";
      v37 = 3;
      goto LABEL_60;
    }
  }
LABEL_62:
  STRU::~STRU((STRU *)v60);
  STRU::~STRU((STRU *)v57);
  STRU::~STRU((STRU *)v65);
  return 0;
}

```

## disassembly

```asm
0x180002504  mov     [rsp-8+arg_18], rbx
0x180002509  push    rbp
0x18000250a  push    rsi
0x18000250b  push    rdi
0x18000250c  push    r12
0x18000250e  push    r13
0x180002510  push    r14
0x180002512  push    r15
0x180002514  lea     rbp, [rsp-10B0h]
0x18000251c  mov     eax, 11B0h
0x180002521  call    _alloca_probe
0x180002526  sub     rsp, rax
0x180002529  mov     rax, cs:__security_cookie
0x180002530  xor     rax, rsp
0x180002533  mov     [rbp+10E0h+var_40], rax
0x18000253a  mov     r12, r8
0x18000253d  mov     [rsp+11E0h+var_1170], r8
0x180002542  mov     r14, rdx
0x180002545  mov     [rbp+10E0h+var_1150], rcx
0x180002549  xor     edx, edx; Val
0x18000254b  lea     rcx, [rbp+10E0h+var_1060]; void *
0x180002552  mov     r8d, 208h; Size
0x180002558  mov     ebx, r9d
0x18000255b  call    memset_0
0x180002560  mov     r13d, 104h
0x180002566  lea     rdx, [rbp+10E0h+var_1060]
0x18000256d  mov     r8d, r13d
0x180002570  lea     rcx, [rbp+10E0h+var_10A0]
0x180002574  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000257a  mov     rax, [r14]
0x18000257d  mov     rcx, r14
0x180002580  mov     rax, [rax+18h]
0x180002584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002589  mov     rcx, [r14]
0x18000258c  mov     rdi, rax
0x18000258f  mov     [rbp+10E0h+var_1158], rax
0x180002593  mov     rax, [rcx+20h]
0x180002597  mov     rcx, r14
0x18000259a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259f  mov     rcx, [r14]
0x1800025a2  mov     rsi, rax
0x1800025a5  mov     rax, [rcx+0D0h]
0x1800025ac  mov     rcx, r14
0x1800025af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b4  mov     rcx, [r14]
0x1800025b7  mov     r15, rax
0x1800025ba  xor     edx, edx
0x1800025bc  mov     rax, [rcx+0B8h]
0x1800025c3  mov     rcx, r14
0x1800025c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025cb  xor     edx, edx; Val
0x1800025cd  mov     [rsp+11E0h+var_1168], rax
0x1800025d2  mov     r8d, 800h; Size
0x1800025d8  lea     rcx, [rbp+10E0h+var_840]; void *
0x1800025df  call    memset_0
0x1800025e4  mov     r8d, 400h
0x1800025ea  lea     rdx, [rbp+10E0h+var_840]
0x1800025f1  lea     rcx, [rbp+10E0h+var_1148]
0x1800025f5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800025fb  xor     edx, edx; Val
0x1800025fd  lea     rcx, [rbp+10E0h+var_E50]; void *
0x180002604  mov     r8d, 208h; Size
0x18000260a  call    memset_0
0x18000260f  mov     r8d, r13d
0x180002612  lea     rdx, [rbp+10E0h+var_E50]
0x180002619  lea     rcx, [rbp+10E0h+var_1110]
0x18000261d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002623  xor     r13d, r13d
0x180002626  mov     [rsp+11E0h+var_1190], r13
0x18000262b  mov     [rsp+11E0h+var_1184], r13d
0x180002630  test    ebx, ebx
0x180002632  jz      short loc_180002698
0x180002634  mov     ebx, [rbp+10E0h+arg_28]
0x18000263a  test    ebx, ebx
0x18000263c  jns     short loc_180002681
0x18000263e  mov     rax, [rsi]
0x180002641  mov     rcx, rsi
0x180002644  mov     rax, [rax+8]
0x180002648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264d  mov     [rsp+11E0h+var_11B0], r13d
0x180002652  lea     r8, aInternalServer; "Internal Server Error"
0x180002659  xor     r9d, r9d
0x18000265c  mov     [rsp+11E0h+var_11B8], r13
0x180002661  mov     edx, 1F4h
0x180002666  mov     dword ptr [rsp+11E0h+var_11C0], ebx
0x18000266a  mov     [rax+218h], r13w
0x180002672  mov     rcx, rsi
0x180002675  mov     rax, [rsi]
0x180002678  mov     rax, [rax+18h]
0x18000267c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002681  mov     rax, [r14]
0x180002684  mov     rcx, r14
0x180002687  mov     rax, [rax+0C8h]
0x18000268e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002693  jmp     loc_180002D26
0x180002698  mov     rax, [r15]
0x18000269b  mov     rcx, r15
0x18000269e  mov     rax, [rax+38h]
0x1800026a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a7  mov     r13d, 2
0x1800026ad  test    r13b, al
0x1800026b0  jz      short loc_180002702
0x1800026b2  mov     rax, [rsi]
0x1800026b5  mov     rcx, rsi
0x1800026b8  mov     ebx, 80070002h
0x1800026bd  mov     rax, [rax+8]
0x1800026c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c6  xor     r15d, r15d
0x1800026c9  lea     r8, aNotFound; "Not Found"
0x1800026d0  mov     [rsp+11E0h+var_11B0], r15d
0x1800026d5  xor     r9d, r9d
0x1800026d8  mov     edx, 194h
0x1800026dd  mov     [rsp+11E0h+var_11B8], r15
0x1800026e2  mov     [rax+218h], r15w
0x1800026ea  mov     rcx, rsi
0x1800026ed  mov     rax, [rsi]
0x1800026f0  mov     dword ptr [rsp+11E0h+var_11C0], ebx
0x1800026f4  mov     rax, [rax+18h]
0x1800026f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026fd  jmp     loc_180002ABA
0x180002702  xor     r15d, r15d
0x180002705  cmp     [r12+8], r15d
0x18000270a  jz      loc_180002D49
0x180002710  mov     rax, [r14]
0x180002713  xor     edx, edx
0x180002715  mov     rcx, r14
0x180002718  mov     rax, [rax+0B0h]
0x18000271f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002724  mov     rdx, rax
0x180002727  lea     rcx, [rbp+10E0h+var_1148]
0x18000272b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002731  mov     ebx, eax
0x180002733  test    eax, eax
0x180002735  js      loc_180002ABA
0x18000273b  mov     eax, [rbp+10E0h+var_1118]
0x18000273e  test    eax, eax
0x180002740  jz      loc_180002897
0x180002746  lea     ecx, [rax-1]
0x180002749  mov     rax, [rbp+10E0h+Str]
0x18000274d  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x180002752  jz      loc_180002897
0x180002758  mov     rax, [rdi]
0x18000275b  mov     rcx, rdi
0x18000275e  mov     rax, [rax+8]
0x180002762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002767  lea     r12d, [r15+1]
0x18000276b  mov     ecx, [rax+24h]
0x18000276e  sub     ecx, 4
0x180002771  cmp     ecx, r12d
0x180002774  jbe     short loc_1800027E8
0x180002776  mov     rax, [rsi]
0x180002779  mov     rcx, rsi
0x18000277c  mov     rax, [rax+8]
0x180002780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002785  mov     [rsp+11E0h+var_11B0], r15d
0x18000278a  lea     r8, aMethodNotAllow; "Method Not Allowed"
0x180002791  xor     r9d, r9d
0x180002794  mov     [rsp+11E0h+var_11B8], r15
0x180002799  mov     edx, 195h
0x18000279e  mov     dword ptr [rsp+11E0h+var_11C0], 80070001h
0x1800027a6  mov     [rax+218h], r15w
0x1800027ae  mov     rcx, rsi
0x1800027b1  mov     rax, [rsi]
0x1800027b4  mov     rax, [rax+18h]
0x1800027b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027bd  mov     rax, [rsi]
0x1800027c0  mov     rcx, rsi
0x1800027c3  mov     rax, [rax+8]
0x1800027c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027cc  lea     rcx, aGetHeadOptions; "GET, HEAD, OPTIONS, TRACE"
0x1800027d3  mov     [rax+0E0h], rcx
0x1800027da  mov     word ptr [rax+0D8h], 19h
0x1800027e3  jmp     loc_180002CA2
0x1800027e8  mov     r8d, 400h
0x1800027ee  lea     rdx, [rbp+10E0h+var_C40]
0x1800027f5  lea     rcx, [rbp+10E0h+var_10D8]
0x1800027f9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800027ff  lea     rdx, [rbp+10E0h+var_1148]
0x180002803  lea     rcx, [rbp+10E0h+var_10D8]
0x180002807  call    cs:__imp_?CopyWToUTF8Escaped@STRA@@QEAAJAEBVSTRU@@@Z; STRA::CopyWToUTF8Escaped(STRU const &)
0x18000280d  mov     ebx, eax
0x18000280f  test    eax, eax
0x180002811  js      short loc_180002888
0x180002813  lea     rdx, asc_180005BE4; "/"
0x18000281a  lea     rcx, [rbp+10E0h+var_10D8]
0x18000281e  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002824  mov     ebx, eax
0x180002826  test    eax, eax
0x180002828  js      short loc_180002888
0x18000282a  mov     rax, [rsi]
0x18000282d  lea     r8, aMovedPermanent; "Moved Permanently"
0x180002834  mov     [rsp+11E0h+var_11B0], r15d
0x180002839  xor     r9d, r9d
0x18000283c  mov     edx, 12Dh
0x180002841  mov     [rsp+11E0h+var_11B8], r15
0x180002846  mov     rcx, rsi
0x180002849  mov     dword ptr [rsp+11E0h+var_11C0], r15d
0x18000284e  mov     rax, [rax+18h]
0x180002852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002857  mov     rax, [rsi]
0x18000285a  mov     r9d, r12d
0x18000285d  mov     rdx, [rbp+10E0h+var_10B8]
0x180002861  xor     r8d, r8d
0x180002864  mov     rcx, rsi
0x180002867  mov     rax, [rax+98h]
0x18000286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002873  lea     rcx, [rbp+10E0h+var_10D8]
0x180002877  mov     ebx, eax
0x180002879  test    eax, eax
0x18000287b  js      short loc_18000288C
0x18000287d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002883  jmp     loc_180002CA2
0x180002888  lea     rcx, [rbp+10E0h+var_10D8]
0x18000288c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002892  jmp     loc_180002ABA
0x180002897  mov     rax, [r14]
0x18000289a  mov     r12d, 1
0x1800028a0  mov     rcx, r14
0x1800028a3  mov     [rsp+11E0h+var_1188], r12d
0x1800028a8  mov     rax, [rax+30h]
0x1800028ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b1  mov     rdx, rax
0x1800028b4  mov     rcx, [rax]
0x1800028b7  mov     rax, [rcx+20h]
0x1800028bb  mov     rcx, rdx
0x1800028be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c3  mov     [rbp+10E0h+var_1160], rax
0x1800028c7  mov     [rsp+11E0h+var_1178], r15
0x1800028cc  test    rax, rax
0x1800028cf  jz      short loc_1800028FE
0x1800028d1  mov     rcx, [r14]
0x1800028d4  mov     rax, [rcx+30h]
0x1800028d8  mov     rcx, r14
0x1800028db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e0  mov     r8, rax
0x1800028e3  lea     rdx, aSid; "SID"
0x1800028ea  mov     rcx, [rax]
0x1800028ed  mov     rax, [rcx+50h]
0x1800028f1  mov     rcx, r8
0x1800028f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f9  mov     [rsp+11E0h+var_1178], rax
0x1800028fe  mov     rcx, [r14]
0x180002901  mov     [rsp+11E0h+var_1180], r15
0x180002906  mov     rax, [rcx+0A0h]
0x18000290d  mov     rcx, r14
0x180002910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002915  mov     rdx, rax
0x180002918  mov     rcx, [rax]
0x18000291b  mov     rax, [rcx+10h]
0x18000291f  mov     rcx, rdx
0x180002922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002927  test    rax, rax
0x18000292a  jz      short loc_180002967
0x18000292c  mov     rax, [r14]
0x18000292f  mov     rcx, r14
0x180002932  mov     rax, [rax+0A0h]
0x180002939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000293e  mov     rdx, rax
0x180002941  mov     rcx, [rax]
0x180002944  mov     rax, [rcx+10h]
0x180002948  mov     rcx, rdx
0x18000294b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002950  mov     rdx, rax
0x180002953  mov     rcx, [rax]
0x180002956  mov     rax, [rcx+38h]
0x18000295a  mov     rcx, rdx
0x18000295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002962  mov     [rsp+11E0h+var_1180], rax
0x180002967  mov     rcx, [rsp+11E0h+var_1170]
0x18000296c  add     rcx, 10h
0x180002970  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180002976  mov     r15, rax
0x180002979  test    rax, rax
0x18000297c  jz      loc_180002D49
0x180002982  mov     rdx, [rsp+11E0h+var_1168]
0x180002987  lea     rcx, [rbp+10E0h+var_1110]
0x18000298b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002991  mov     ebx, eax
0x180002993  test    eax, eax
0x180002995  js      loc_180002AB7
0x18000299b  mov     ecx, [rbp+10E0h+var_10E0]
0x18000299e  mov     rax, [rbp+10E0h+var_10F0]
0x1800029a2  dec     ecx
0x1800029a4  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1800029a9  jz      short loc_1800029C6
0x1800029ab  lea     rdx, asc_180005660; "\\"
0x1800029b2  lea     rcx, [rbp+10E0h+var_1110]
0x1800029b6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800029bc  mov     ebx, eax
0x1800029be  test    eax, eax
0x1800029c0  js      loc_180002AB7
0x1800029c6  mov     edx, 3Fh ; '?'; Ch
0x1800029cb  mov     rcx, r15; Str
0x1800029ce  call    cs:__imp_wcschr
0x1800029d4  mov     rdx, r15
0x1800029d7  lea     rcx, [rbp+10E0h+var_1110]
0x1800029db  test    rax, rax
0x1800029de  jz      short loc_1800029F1
0x1800029e0  sub     rax, r15
0x1800029e3  sar     rax, 1
  ... truncated ...
```
