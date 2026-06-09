# HTTP_LOG_HANDLER::GetCustomLogValues(IHttpContext *,LOGGING *,EXTENDED_LOG_DATA * *)

- ea: `0x180003510`
- end: `0x1800038ef`
- name: `?GetCustomLogValues@HTTP_LOG_HANDLER@@QEAAJPEAVIHttpContext@@PEAVLOGGING@@PEAPEAVEXTENDED_LOG_DATA@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(HTTP_LOG_HANDLER *__hidden this, struct IHttpContext *, struct LOGGING *, struct EXTENDED_LOG_DATA **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180001080`

## callees

- `0x1800025b0`
- `0x1800025f0`
- `0x180003510`
- `0x1800055a4`
- `0x180005720`
- `0x180006010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180003801`
- `msvcrt!wcsncpy_s` at `0x180003801`
- `msvcrt!_strupr` at `0x18000367d`
- `msvcrt!_strupr` at `0x18000367d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003862`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003862`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000389e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000389e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800038b6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800038b6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800038c0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800038c0`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003674`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003691`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000370b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003674`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003691`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000370b`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800035df`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800035df`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003560`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003560`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000356a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000356a`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800035ca`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800035ca`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003622`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003639`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003780`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003622`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003639`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003780`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x18000362f`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x18000362f`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180003646`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180003646`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800036e8`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180003745`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800036e8`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180003745`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18000376c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18000376c`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x180003739`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x180003739`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_HANDLER::GetCustomLogValues(
        HTTP_LOG_HANDLER *this,
        struct IHttpContext *a2,
        struct LOGGING *a3,
        struct EXTENDED_LOG_DATA **a4)
{
  unsigned int v4; // r14d
  int v5; // edi
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rdx
  _DWORD *v11; // rbx
  const unsigned __int16 *Str; // r12
  const unsigned __int16 *v13; // rax
  int v14; // ecx
  int v15; // ecx
  char *v16; // rax
  __int64 (__fastcall *v17)(struct IHttpContext *, char *, wchar_t **, int *); // rbx
  char *v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // rax
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64, char *, __int16 *); // rbx
  __int64 v23; // rdi
  char *v24; // rax
  const char *v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // ecx
  bool v29; // sf
  unsigned int v30; // edi
  wchar_t *v31; // rax
  unsigned __int16 *v32; // rbx
  _QWORD *v33; // rcx
  __int16 v35; // [rsp+30h] [rbp-89h] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-81h] BYREF
  int v37; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v38; // [rsp+44h] [rbp-75h]
  unsigned int v39; // [rsp+48h] [rbp-71h]
  unsigned int v40; // [rsp+4Ch] [rbp-6Dh]
  __int64 v41; // [rsp+50h] [rbp-69h]
  struct EXTENDED_LOG_DATA **v42; // [rsp+58h] [rbp-61h]
  _BYTE v43[56]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v44[56]; // [rsp+98h] [rbp-21h] BYREF

  v4 = 0;
  v42 = a4;
  *a4 = 0;
  v5 = 0;
  v37 = 0;
  Source = 0;
  v35 = 0;
  STRU::STRU((STRU *)v43);
  STRA::STRA((STRA *)v44);
  if ( !*((_DWORD *)a3 + 28) )
    goto LABEL_39;
  v8 = operator new(0x68u);
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_39;
  }
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v8[4] = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 16);
  *v8 = &EXTENDED_LOG_DATA::`vftable';
  *((_DWORD *)v8 + 6) = 1145854021;
  MULTISZ::MULTISZ((MULTISZ *)(v8 + 5));
  v8[2] = v8 + 1;
  v8[1] = v8 + 1;
  MULTISZ::Reset((MULTISZ *)(v8 + 5));
  *((_DWORD *)v8 + 24) = GetTickCount();
  v10 = *((_QWORD *)a3 + 13);
  v39 = *((_DWORD *)a3 + 24);
  v40 = *((_DWORD *)a3 + 23);
  v38 = 0;
  v41 = v10;
  while ( v4 < *((_DWORD *)a3 + 28) )
  {
    v11 = (_DWORD *)(v10 + 176LL * v4);
    Str = STRU::QueryStr((STRU *)v11);
    STRA::Reset((STRA *)v44);
    v13 = STRU::QueryStr((STRU *)(v11 + 28));
    v5 = STRA::AppendW((STRA *)v44, v13);
    if ( v5 < 0 )
      goto LABEL_34;
    v14 = v11[42];
    if ( !v14 )
    {
      STRU::Reset((STRU *)v43);
      v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v22 = *(__int64 (__fastcall **)(__int64, char *, __int16 *))(*(_QWORD *)v21 + 24LL);
LABEL_15:
      v23 = v21;
      v24 = STRA::QueryStr((STRA *)v44);
      v25 = (const char *)v22(v23, v24, &v35);
      if ( v25 && v35 )
        v26 = STRU::AppendA((STRU *)v43, v25);
      else
        v26 = STRU::Append((STRU *)v43, 0x2Du);
      v5 = v26;
      if ( v26 < 0 )
        goto LABEL_34;
      v20 = STRU::QueryStr((STRU *)v43);
      Source = v20;
      goto LABEL_22;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      STRU::Reset((STRU *)v43);
      v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
      v22 = *(__int64 (__fastcall **)(__int64, char *, __int16 *))(*(_QWORD *)v21 + 72LL);
      goto LABEL_15;
    }
    if ( v15 == 1 )
    {
      v16 = STRA::QueryStr((STRA *)v44);
      _strupr(v16);
      v17 = *(__int64 (__fastcall **)(struct IHttpContext *, char *, wchar_t **, int *))(*(_QWORD *)a2 + 128LL);
      v18 = STRA::QueryStr((STRA *)v44);
      v19 = v17(a2, v18, &Source, &v37);
      v5 = v19;
      if ( v19 == -2147023483 || !v37 )
      {
        v20 = L"-";
        Source = (wchar_t *)L"-";
        goto LABEL_22;
      }
      if ( v19 < 0 )
        goto LABEL_34;
    }
    v20 = Source;
LABEL_22:
    v27 = -1;
    do
      ++v27;
    while ( v20[v27] );
    v28 = 2 * v27;
    v38 += v28;
    if ( v38 <= v40 )
    {
      if ( v28 <= v39 )
      {
        v5 = EXTENDED_LOG_DATA::AddNameValue((EXTENDED_LOG_DATA *)v8, Str, v20);
      }
      else
      {
        v30 = v39 + 1;
        v31 = (wchar_t *)operator new(saturated_mul(v39 + 1, 2u));
        v32 = v31;
        if ( !v31 )
        {
          v5 = -2147024882;
LABEL_34:
          (*(void (__fastcall **)(_QWORD *, __int64))*v8)(v8, 1);
          goto LABEL_39;
        }
        wcsncpy_s(v31, v30, Source, (unsigned __int64)v39 >> 1);
        v5 = EXTENDED_LOG_DATA::AddNameValue((EXTENDED_LOG_DATA *)v8, Str, v32);
        operator delete(v32);
      }
      v29 = v5 < 0;
    }
    else
    {
      Source = (wchar_t *)L"-";
      v5 = EXTENDED_LOG_DATA::AddNameValue((EXTENDED_LOG_DATA *)v8, Str, L"-");
      v29 = v5 < 0;
    }
    if ( v29 )
      goto LABEL_34;
    v10 = v41;
    ++v4;
  }
  EnterCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
  v33 = (_QWORD *)qword_18000B730;
  if ( *(struct _LIST_ENTRY **)qword_18000B730 != &HTTP_LOG_HANDLER::sm_LogDataListHead )
    __fastfail(3u);
  v8[2] = qword_18000B730;
  v8[1] = &HTTP_LOG_HANDLER::sm_LogDataListHead;
  *v33 = v8 + 1;
  qword_18000B730 = (__int64)(v8 + 1);
  LeaveCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
  *v42 = (struct EXTENDED_LOG_DATA *)v8;
LABEL_39:
  STRA::~STRA((STRA *)v44);
  STRU::~STRU((STRU *)v43);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003510  mov     [rsp-8+arg_0], rbx
0x180003515  push    rbp
0x180003516  push    rsi
0x180003517  push    rdi
0x180003518  push    r12
0x18000351a  push    r13
0x18000351c  push    r14
0x18000351e  push    r15
0x180003520  lea     rbp, [rsp-27h]
0x180003525  sub     rsp, 0E0h
0x18000352c  mov     rax, cs:__security_cookie
0x180003533  xor     rax, rsp
0x180003536  mov     [rbp+57h+var_40], rax
0x18000353a  xor     r14d, r14d
0x18000353d  mov     [rbp+57h+var_B8], r9
0x180003541  lea     rcx, [rbp+57h+var_B0]
0x180003545  mov     [r9], r14
0x180003548  mov     edi, r14d
0x18000354b  mov     [rbp+57h+var_D0], r14d
0x18000354f  mov     [rsp+110h+Source], r14
0x180003554  mov     r13, r8
0x180003557  mov     [rsp+110h+var_E0], r14w
0x18000355d  mov     r15, rdx
0x180003560  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003566  lea     rcx, [rbp+57h+var_78]
0x18000356a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003570  cmp     [r13+70h], r14d
0x180003574  jz      loc_1800038B2
0x18000357a  lea     ecx, [r14+68h]; Size
0x18000357e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003583  mov     rsi, rax
0x180003586  test    rax, rax
0x180003589  jz      loc_1800038AD
0x18000358f  mov     rax, [r15]
0x180003592  mov     rcx, r15
0x180003595  mov     rax, [rax+18h]
0x180003599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000359e  mov     rcx, rax
0x1800035a1  mov     rax, [rax]
0x1800035a4  mov     rax, [rax+8]
0x1800035a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ad  mov     rcx, [rax+10h]
0x1800035b1  lea     rax, ??_7EXTENDED_LOG_DATA@@6B@; const EXTENDED_LOG_DATA::`vftable'
0x1800035b8  mov     [rsi+20h], rcx
0x1800035bc  lea     rcx, [rsi+28h]
0x1800035c0  mov     [rsi], rax
0x1800035c3  mov     dword ptr [rsi+18h], 444C5845h
0x1800035ca  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800035d0  lea     rax, [rsi+8]
0x1800035d4  lea     rcx, [rsi+28h]
0x1800035d8  mov     [rax+8], rax
0x1800035dc  mov     [rax], rax
0x1800035df  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x1800035e5  call    cs:__imp_GetTickCount
0x1800035eb  mov     [rsi+60h], eax
0x1800035ee  mov     eax, [r13+60h]
0x1800035f2  mov     rdx, [r13+68h]
0x1800035f6  mov     [rbp+57h+var_C8], eax
0x1800035f9  mov     eax, [r13+5Ch]
0x1800035fd  mov     [rbp+57h+var_C4], eax
0x180003600  mov     [rbp+57h+var_CC], r14d
0x180003604  mov     [rbp+57h+var_C0], rdx
0x180003608  cmp     r14d, [r13+70h]
0x18000360c  jnb     loc_18000385B
0x180003612  mov     eax, r14d
0x180003615  imul    rbx, rax, 0B0h
0x18000361c  add     rbx, rdx
0x18000361f  mov     rcx, rbx
0x180003622  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003628  lea     rcx, [rbp+57h+var_78]
0x18000362c  mov     r12, rax
0x18000362f  call    cs:__imp_?Reset@STRA@@QEAAXXZ; STRA::Reset(void)
0x180003635  lea     rcx, [rbx+70h]
0x180003639  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000363f  mov     rdx, rax
0x180003642  lea     rcx, [rbp+57h+var_78]
0x180003646  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x18000364c  mov     edi, eax
0x18000364e  test    eax, eax
0x180003650  js      loc_180003846
0x180003656  mov     ecx, [rbx+0A8h]
0x18000365c  xor     ebx, ebx
0x18000365e  test    ecx, ecx
0x180003660  jz      loc_180003741
0x180003666  sub     ecx, 1
0x180003669  jz      short loc_1800036E4
0x18000366b  cmp     ecx, 1
0x18000366e  jnz     short loc_1800036C6
0x180003670  lea     rcx, [rbp+57h+var_78]
0x180003674  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000367a  mov     rcx, rax; String
0x18000367d  call    cs:__imp__strupr
0x180003683  mov     rax, [r15]
0x180003686  lea     rcx, [rbp+57h+var_78]
0x18000368a  mov     rbx, [rax+80h]
0x180003691  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003697  lea     r9, [rbp+57h+var_D0]
0x18000369b  mov     rcx, r15
0x18000369e  mov     rdx, rax
0x1800036a1  lea     r8, [rsp+110h+Source]
0x1800036a6  mov     rax, rbx
0x1800036a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ae  xor     ebx, ebx
0x1800036b0  mov     edi, eax
0x1800036b2  cmp     eax, 80070585h
0x1800036b7  jz      short loc_1800036D0
0x1800036b9  cmp     [rbp+57h+var_D0], ebx
0x1800036bc  jz      short loc_1800036D0
0x1800036be  test    eax, eax
0x1800036c0  js      loc_180003846
0x1800036c6  mov     rax, [rsp+110h+Source]
0x1800036cb  jmp     loc_18000378B
0x1800036d0  lea     rdx, asc_180007E30; "-"
0x1800036d7  mov     rax, rdx
0x1800036da  mov     [rsp+110h+Source], rdx
0x1800036df  jmp     loc_180003792
0x1800036e4  lea     rcx, [rbp+57h+var_B0]
0x1800036e8  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800036ee  mov     rax, [r15]
0x1800036f1  mov     rcx, r15
0x1800036f4  mov     rax, [rax+20h]
0x1800036f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036fd  mov     rcx, [rax]
0x180003700  mov     rbx, [rcx+48h]
0x180003704  lea     rcx, [rbp+57h+var_78]
0x180003708  mov     rdi, rax
0x18000370b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003711  lea     r8, [rsp+110h+var_E0]
0x180003716  mov     rcx, rdi
0x180003719  mov     rdx, rax
0x18000371c  mov     rax, rbx
0x18000371f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003724  xor     ebx, ebx
0x180003726  test    rax, rax
0x180003729  jz      short loc_180003763
0x18000372b  cmp     [rsp+110h+var_E0], bx
0x180003730  jz      short loc_180003763
0x180003732  mov     rdx, rax
0x180003735  lea     rcx, [rbp+57h+var_B0]
0x180003739  call    cs:__imp_?AppendA@STRU@@QEAAJPEBD@Z; STRU::AppendA(char const *)
0x18000373f  jmp     short loc_180003772
0x180003741  lea     rcx, [rbp+57h+var_B0]
0x180003745  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000374b  mov     rax, [r15]
0x18000374e  mov     rcx, r15
0x180003751  mov     rax, [rax+18h]
0x180003755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375a  mov     rcx, [rax]
0x18000375d  mov     rbx, [rcx+18h]
0x180003761  jmp     short loc_180003704
0x180003763  mov     edx, 2Dh ; '-'
0x180003768  lea     rcx, [rbp+57h+var_B0]
0x18000376c  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180003772  mov     edi, eax
0x180003774  test    eax, eax
0x180003776  js      loc_180003846
0x18000377c  lea     rcx, [rbp+57h+var_B0]
0x180003780  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003786  mov     [rsp+110h+Source], rax
0x18000378b  lea     rdx, asc_180007E30; "-"
0x180003792  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003796  mov     rcx, r8
0x180003799  inc     rcx
0x18000379c  cmp     [rax+rcx*2], bx
0x1800037a0  jnz     short loc_180003799
0x1800037a2  mov     ebx, [rbp+57h+var_CC]
0x1800037a5  add     ecx, ecx
0x1800037a7  add     ebx, ecx
0x1800037a9  mov     [rbp+57h+var_CC], ebx
0x1800037ac  cmp     ebx, [rbp+57h+var_C4]
0x1800037af  jbe     short loc_1800037CA
0x1800037b1  mov     [rsp+110h+Source], rdx
0x1800037b6  mov     r8, rdx; unsigned __int16 *
0x1800037b9  mov     rdx, r12; unsigned __int16 *
0x1800037bc  mov     rcx, rsi; this
0x1800037bf  call    ?AddNameValue@EXTENDED_LOG_DATA@@QEAAJPEBG0@Z; EXTENDED_LOG_DATA::AddNameValue(ushort const *,ushort const *)
0x1800037c4  mov     edi, eax
0x1800037c6  test    eax, eax
0x1800037c8  jmp     short loc_180003833
0x1800037ca  mov     edx, [rbp+57h+var_C8]
0x1800037cd  cmp     ecx, edx
0x1800037cf  jbe     short loc_180003821
0x1800037d1  lea     edi, [rdx+1]
0x1800037d4  mov     eax, 2
0x1800037d9  mul     rdi
0x1800037dc  cmovb   rax, r8
0x1800037e0  mov     rcx, rax; Size
0x1800037e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037e8  mov     rbx, rax
0x1800037eb  test    rax, rax
0x1800037ee  jz      short loc_180003841
0x1800037f0  mov     r9d, [rbp+57h+var_C8]
0x1800037f4  mov     edx, edi; SizeInWords
0x1800037f6  mov     r8, [rsp+110h+Source]; Source
0x1800037fb  mov     rcx, rax; Destination
0x1800037fe  shr     r9, 1; MaxCount
0x180003801  call    cs:__imp_wcsncpy_s
0x180003807  mov     r8, rbx; unsigned __int16 *
0x18000380a  mov     rdx, r12; unsigned __int16 *
0x18000380d  mov     rcx, rsi; this
0x180003810  call    ?AddNameValue@EXTENDED_LOG_DATA@@QEAAJPEBG0@Z; EXTENDED_LOG_DATA::AddNameValue(ushort const *,ushort const *)
0x180003815  mov     rcx, rbx; Block
0x180003818  mov     edi, eax
0x18000381a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000381f  jmp     short loc_180003831
0x180003821  mov     r8, rax; unsigned __int16 *
0x180003824  mov     rdx, r12; unsigned __int16 *
0x180003827  mov     rcx, rsi; this
0x18000382a  call    ?AddNameValue@EXTENDED_LOG_DATA@@QEAAJPEBG0@Z; EXTENDED_LOG_DATA::AddNameValue(ushort const *,ushort const *)
0x18000382f  mov     edi, eax
0x180003831  test    edi, edi
0x180003833  js      short loc_180003846
0x180003835  mov     rdx, [rbp+57h+var_C0]
0x180003839  inc     r14d
0x18000383c  jmp     loc_180003608
0x180003841  mov     edi, 8007000Eh
0x180003846  mov     rax, [rsi]
0x180003849  mov     edx, 1
0x18000384e  mov     rcx, rsi
0x180003851  mov     rax, [rax]
0x180003854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003859  jmp     short loc_1800038B2
0x18000385b  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003862  call    cs:__imp_EnterCriticalSection
0x180003868  mov     rcx, cs:qword_18000B730
0x18000386f  lea     rdx, ?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x180003876  cmp     [rcx], rdx
0x180003879  jz      short loc_180003882
0x18000387b  mov     ecx, 3
0x180003880  int     29h; Win8: RtlFailFast(ecx)
0x180003882  lea     rax, [rsi+8]
0x180003886  mov     [rax+8], rcx
0x18000388a  mov     [rax], rdx
0x18000388d  mov     [rcx], rax
0x180003890  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003897  mov     cs:qword_18000B730, rax
0x18000389e  call    cs:__imp_LeaveCriticalSection
0x1800038a4  mov     rax, [rbp+57h+var_B8]
0x1800038a8  mov     [rax], rsi
0x1800038ab  jmp     short loc_1800038B2
0x1800038ad  mov     edi, 8007000Eh
0x1800038b2  lea     rcx, [rbp+57h+var_78]
0x1800038b6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800038bc  lea     rcx, [rbp+57h+var_B0]
0x1800038c0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800038c6  mov     eax, edi
0x1800038c8  mov     rcx, [rbp+57h+var_40]
0x1800038cc  xor     rcx, rsp; StackCookie
0x1800038cf  call    __security_check_cookie
0x1800038d4  mov     rbx, [rsp+110h+arg_0]
0x1800038dc  add     rsp, 0E0h
0x1800038e3  pop     r15
0x1800038e5  pop     r14
0x1800038e7  pop     r13
0x1800038e9  pop     r12
0x1800038eb  pop     rdi
0x1800038ec  pop     rsi
0x1800038ed  pop     rbp
0x1800038ee  retn
```
