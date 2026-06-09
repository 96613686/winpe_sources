# W3_FILTER_CONTEXT::SetSendHeader(_HTTP_FILTER_CONTEXT *,char *,char *)

- ea: `0x1800071c0`
- end: `0x18000747e`
- name: `?SetSendHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z`
- size: `702`
- prototype: `static int(struct _HTTP_FILTER_CONTEXT *, char *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180004b80`
- `0x1800071c0`
- `0x180007490`
- `0x18000bfdc`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000745e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000745e`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800072a2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000734f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000735d`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800072a2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000734f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000735d`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007276`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007276`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800072ed`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007303`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007342`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800072ed`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007303`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007342`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800073ef`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800073fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007444`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000744f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007469`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007474`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800073ef`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800073fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007444`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000744f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007469`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007474`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800071fc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007215`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800071fc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007215`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800072da`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800072da`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::SetSendHeader(struct _HTTP_FILTER_CONTEXT *a1, char *a2, char *a3)
{
  _QWORD *ServerContext; // r15
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r15
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, char *); // rbx
  char *Str; // rax
  __int64 v14; // r14
  __int64 (__fastcall *v15)(__int64, char *, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *v17; // rbx
  char *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  const char *v21; // rbx
  struct IHttpTraceContext *v22; // rax
  const struct _GUID *v23; // rdx
  DWORD v25; // eax
  _BYTE v26[56]; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v27[56]; // [rsp+68h] [rbp-180h] BYREF
  char v28[128]; // [rsp+A0h] [rbp-148h] BYREF
  char v29[128]; // [rsp+120h] [rbp-C8h] BYREF

  STRA::STRA((STRA *)v27, v28, 0x80u);
  STRA::STRA((STRA *)v26, v29, 0x80u);
  if ( !a1 || (ServerContext = a1->ServerContext) == 0 || !a2 )
  {
    SetLastError(0x57u);
    STRA::~STRA((STRA *)v26);
    STRA::~STRA((STRA *)v27);
    return 0;
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( (unsigned int)v7 <= 1 )
    goto LABEL_22;
  v8 = (unsigned int)(v7 - 1);
  if ( a2[v8] != 58 )
    goto LABEL_22;
  v9 = ServerContext[3];
  v10 = STRA::Copy((STRA *)v27, a2, v8);
  if ( v10 < 0 )
    goto LABEL_23;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
  v12 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 56LL);
  Str = STRA::QueryStr((STRA *)v27);
  v10 = v12(v11, Str);
  if ( v10 < 0 )
    goto LABEL_23;
  if ( !a3 || !*a3 )
    goto LABEL_16;
  v10 = STRA::Copy((STRA *)v26, a3);
  if ( v10 < 0 )
  {
LABEL_23:
    v25 = WIN32_FROM_HRESULT(v10);
    SetLastError(v25);
    STRA::~STRA((STRA *)v26);
    STRA::~STRA((STRA *)v27);
    return 0;
  }
  if ( STRA::QueryCCH((STRA *)v27) > 0xFFFF || STRA::QueryCCH((STRA *)v26) > 0xFFFF )
  {
LABEL_22:
    v10 = -2147024809;
    goto LABEL_23;
  }
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
  v15 = *(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, _DWORD))(*(_QWORD *)v14 + 40LL);
  CCH = STRA::QueryCCH((STRA *)v26);
  v17 = STRA::QueryStr((STRA *)v26);
  v18 = STRA::QueryStr((STRA *)v27);
  v10 = v15(v14, v18, v17, CCH, 0);
  if ( v10 < 0 )
    goto LABEL_23;
LABEL_16:
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 272LL))(v9);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v19, v20, 4) )
  {
    v21 = (const char *)&qword_18000EE70;
    if ( a3 )
      v21 = a3;
    v22 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 272LL))(v9);
    IISFilterEvents::FILTER_SET_RESP_HEADER::RaiseEvent(v22, v23, a2, v21);
  }
  STRA::~STRA((STRA *)v26);
  STRA::~STRA((STRA *)v27);
  return 1;
}

```

## disassembly

```asm
0x1800071c0  push    rbx
0x1800071c2  push    rbp
0x1800071c3  push    r12
0x1800071c5  push    r15
0x1800071c7  sub     rsp, 1C8h
0x1800071ce  mov     rax, cs:__security_cookie
0x1800071d5  xor     rax, rsp
0x1800071d8  mov     [rsp+1E8h+var_48], rax
0x1800071e0  mov     r12, r8
0x1800071e3  mov     rbp, rdx
0x1800071e6  mov     rbx, rcx
0x1800071e9  lea     rdx, [rsp+1E8h+var_148]
0x1800071f1  mov     r8d, 80h
0x1800071f7  lea     rcx, [rsp+1E8h+var_180]
0x1800071fc  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180007202  mov     r8d, 80h
0x180007208  lea     rdx, [rsp+1E8h+var_C8]
0x180007210  lea     rcx, [rsp+1E8h+var_1B8]
0x180007215  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000721b  test    rbx, rbx
0x18000721e  jz      loc_180007459
0x180007224  mov     r15, [rbx+8]
0x180007228  test    r15, r15
0x18000722b  jz      loc_180007459
0x180007231  test    rbp, rbp
0x180007234  jz      loc_180007459
0x18000723a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007241  inc     rax
0x180007244  cmp     byte ptr [rax+rbp], 0
0x180007248  jnz     short loc_180007241
0x18000724a  mov     [rsp+1E8h+var_30], rdi
0x180007252  cmp     eax, 1
0x180007255  jbe     loc_18000742B
0x18000725b  lea     r8d, [rax-1]
0x18000725f  cmp     byte ptr [r8+rbp], 3Ah ; ':'
0x180007264  jnz     loc_18000742B
0x18000726a  mov     r15, [r15+18h]
0x18000726e  lea     rcx, [rsp+1E8h+var_180]
0x180007273  mov     rdx, rbp
0x180007276  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000727c  test    eax, eax
0x18000727e  js      loc_180007430
0x180007284  mov     rax, [r15]
0x180007287  mov     rcx, r15
0x18000728a  mov     rax, [rax+20h]
0x18000728e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007293  mov     rdi, rax
0x180007296  mov     rcx, [rax]
0x180007299  mov     rbx, [rcx+38h]
0x18000729d  lea     rcx, [rsp+1E8h+var_180]
0x1800072a2  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800072a8  mov     rdx, rax
0x1800072ab  mov     rcx, rdi
0x1800072ae  mov     rax, rbx
0x1800072b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b6  test    eax, eax
0x1800072b8  js      loc_180007430
0x1800072be  test    r12, r12
0x1800072c1  jz      loc_180007398
0x1800072c7  cmp     byte ptr [r12], 0
0x1800072cc  jz      loc_180007398
0x1800072d2  mov     rdx, r12
0x1800072d5  lea     rcx, [rsp+1E8h+var_1B8]
0x1800072da  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800072e0  test    eax, eax
0x1800072e2  js      loc_180007430
0x1800072e8  lea     rcx, [rsp+1E8h+var_180]
0x1800072ed  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800072f3  cmp     eax, 0FFFFh
0x1800072f8  ja      loc_18000742B
0x1800072fe  lea     rcx, [rsp+1E8h+var_1B8]
0x180007303  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180007309  cmp     eax, 0FFFFh
0x18000730e  ja      loc_18000742B
0x180007314  mov     rax, [r15]
0x180007317  mov     rcx, r15
0x18000731a  mov     [rsp+1E8h+var_28], rsi
0x180007322  mov     [rsp+1E8h+var_38], r14
0x18000732a  mov     rax, [rax+20h]
0x18000732e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007333  mov     r14, rax
0x180007336  mov     rcx, [rax]
0x180007339  mov     rsi, [rcx+28h]
0x18000733d  lea     rcx, [rsp+1E8h+var_1B8]
0x180007342  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180007348  lea     rcx, [rsp+1E8h+var_1B8]
0x18000734d  mov     edi, eax
0x18000734f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007355  lea     rcx, [rsp+1E8h+var_180]
0x18000735a  mov     rbx, rax
0x18000735d  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007363  movzx   r9d, di
0x180007367  mov     [rsp+1E8h+var_1C8], 0
0x18000736f  mov     rdx, rax
0x180007372  mov     r8, rbx
0x180007375  mov     rax, rsi
0x180007378  mov     rcx, r14
0x18000737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007380  mov     r14, [rsp+1E8h+var_38]
0x180007388  mov     rsi, [rsp+1E8h+var_28]
0x180007390  test    eax, eax
0x180007392  js      loc_180007430
0x180007398  mov     rax, [r15]
0x18000739b  mov     rcx, r15
0x18000739e  mov     rax, [rax+110h]
0x1800073a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073aa  mov     r8d, 4
0x1800073b0  mov     rcx, rax
0x1800073b3  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800073b8  test    eax, eax
0x1800073ba  jz      short loc_1800073EA
0x1800073bc  mov     rax, [r15]
0x1800073bf  lea     rbx, qword_18000EE70
0x1800073c6  test    r12, r12
0x1800073c9  mov     rcx, r15
0x1800073cc  cmovnz  rbx, r12
0x1800073d0  mov     rax, [rax+110h]
0x1800073d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073dc  mov     rcx, rax; struct IHttpTraceContext *
0x1800073df  mov     r9, rbx; char *
0x1800073e2  mov     r8, rbp; char *
0x1800073e5  call    ?RaiseEvent@FILTER_SET_RESP_HEADER@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2@Z; IISFilterEvents::FILTER_SET_RESP_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *)
0x1800073ea  lea     rcx, [rsp+1E8h+var_1B8]
0x1800073ef  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800073f5  lea     rcx, [rsp+1E8h+var_180]
0x1800073fa  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007400  mov     eax, 1
0x180007405  mov     rdi, [rsp+1E8h+var_30]
0x18000740d  mov     rcx, [rsp+1E8h+var_48]
0x180007415  xor     rcx, rsp; StackCookie
0x180007418  call    __security_check_cookie
0x18000741d  add     rsp, 1C8h
0x180007424  pop     r15
0x180007426  pop     r12
0x180007428  pop     rbp
0x180007429  pop     rbx
0x18000742a  retn
0x18000742b  mov     eax, 80070057h
0x180007430  mov     ecx, eax; int
0x180007432  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180007437  mov     ecx, eax; dwErrCode
0x180007439  call    cs:__imp_SetLastError
0x18000743f  lea     rcx, [rsp+1E8h+var_1B8]
0x180007444  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000744a  lea     rcx, [rsp+1E8h+var_180]
0x18000744f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007455  xor     eax, eax
0x180007457  jmp     short loc_180007405
0x180007459  mov     ecx, 57h ; 'W'; dwErrCode
0x18000745e  call    cs:__imp_SetLastError
0x180007464  lea     rcx, [rsp+1E8h+var_1B8]
0x180007469  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000746f  lea     rcx, [rsp+1E8h+var_180]
0x180007474  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000747a  xor     eax, eax
0x18000747c  jmp     short loc_18000740D
```
