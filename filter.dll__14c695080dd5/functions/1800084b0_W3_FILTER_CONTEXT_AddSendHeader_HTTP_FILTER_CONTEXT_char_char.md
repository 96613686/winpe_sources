# W3_FILTER_CONTEXT::AddSendHeader(_HTTP_FILTER_CONTEXT *,char *,char *)

- ea: `0x1800084b0`
- end: `0x18000870c`
- name: `?AddSendHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z`
- size: `604`
- prototype: `static int(struct _HTTP_FILTER_CONTEXT *, char *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180004b80`
- `0x180007490`
- `0x180007a90`
- `0x1800084b0`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086d0`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000860b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008619`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000860b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008619`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008568`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008568`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800085a0`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800085b6`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800085fe`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800085a0`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800085b6`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800085fe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086a3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086ae`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086db`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086e6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086a3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086ae`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086db`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086e6`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800084ec`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180008505`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800084ec`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180008505`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000858d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000858d`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::AddSendHeader(struct _HTTP_FILTER_CONTEXT *a1, char *a2, char *a3)
{
  _QWORD *ServerContext; // r12
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r12
  int v10; // eax
  const char *v11; // rdx
  __int64 v12; // r14
  __int64 (__fastcall *v13)(__int64, char *, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *Str; // rbx
  char *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  struct IHttpTraceContext *v19; // rax
  const struct _GUID *v20; // rdx
  DWORD v22; // ecx
  _BYTE v23[56]; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v24[56]; // [rsp+68h] [rbp-180h] BYREF
  char v25[128]; // [rsp+A0h] [rbp-148h] BYREF
  char v26[128]; // [rsp+120h] [rbp-C8h] BYREF

  STRA::STRA((STRA *)v24, v25, 0x80u);
  STRA::STRA((STRA *)v23, v26, 0x80u);
  if ( !a1 || (ServerContext = a1->ServerContext) == 0 || !a2 || !a3 )
  {
    v22 = 87;
    goto LABEL_22;
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( (unsigned int)v7 <= 1 )
    goto LABEL_19;
  v8 = (unsigned int)(v7 - 1);
  if ( a2[v8] != 58 )
    goto LABEL_19;
  v9 = ServerContext[3];
  v10 = STRA::Copy((STRA *)v24, a2, v8);
  if ( v10 < 0 )
    goto LABEL_20;
  v11 = a3;
  if ( !*a3 )
    v11 = " ";
  v10 = STRA::Copy((STRA *)v23, v11);
  if ( v10 < 0 )
    goto LABEL_20;
  if ( STRA::QueryCCH((STRA *)v24) > 0xFFFF || STRA::QueryCCH((STRA *)v23) > 0xFFFF )
  {
LABEL_19:
    v10 = -2147024809;
    goto LABEL_20;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
  v13 = *(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, _DWORD))(*(_QWORD *)v12 + 40LL);
  CCH = STRA::QueryCCH((STRA *)v23);
  Str = STRA::QueryStr((STRA *)v23);
  v16 = STRA::QueryStr((STRA *)v24);
  v10 = v13(v12, v16, Str, CCH, 0);
  if ( v10 < 0 )
  {
LABEL_20:
    v22 = WIN32_FROM_HRESULT(v10);
LABEL_22:
    SetLastError(v22);
    STRA::~STRA((STRA *)v23);
    STRA::~STRA((STRA *)v24);
    return 0;
  }
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 272LL))(v9);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v17, v18, 4) )
  {
    v19 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 272LL))(v9);
    IISFilterEvents::FILTER_ADD_RESP_HEADER::RaiseEvent(v19, v20, a2, a3);
  }
  STRA::~STRA((STRA *)v23);
  STRA::~STRA((STRA *)v24);
  return 1;
}

```

## disassembly

```asm
0x1800084b0  push    rbx
0x1800084b2  push    rbp
0x1800084b3  push    r12
0x1800084b5  push    r15
0x1800084b7  sub     rsp, 1C8h
0x1800084be  mov     rax, cs:__security_cookie
0x1800084c5  xor     rax, rsp
0x1800084c8  mov     [rsp+1E8h+var_48], rax
0x1800084d0  mov     r15, r8
0x1800084d3  mov     rbp, rdx
0x1800084d6  mov     rbx, rcx
0x1800084d9  lea     rdx, [rsp+1E8h+var_148]
0x1800084e1  mov     r8d, 80h
0x1800084e7  lea     rcx, [rsp+1E8h+var_180]
0x1800084ec  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800084f2  mov     r8d, 80h
0x1800084f8  lea     rdx, [rsp+1E8h+var_C8]
0x180008500  lea     rcx, [rsp+1E8h+var_1B8]
0x180008505  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000850b  test    rbx, rbx
0x18000850e  jz      loc_1800086CB
0x180008514  mov     r12, [rbx+8]
0x180008518  test    r12, r12
0x18000851b  jz      loc_1800086CB
0x180008521  test    rbp, rbp
0x180008524  jz      loc_1800086CB
0x18000852a  test    r15, r15
0x18000852d  jz      loc_1800086CB
0x180008533  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000853a  inc     rax
0x18000853d  cmp     byte ptr [rax+rbp], 0
0x180008541  jnz     short loc_18000853A
0x180008543  cmp     eax, 1
0x180008546  jbe     loc_1800086BB
0x18000854c  lea     r8d, [rax-1]
0x180008550  cmp     byte ptr [r8+rbp], 3Ah ; ':'
0x180008555  jnz     loc_1800086BB
0x18000855b  mov     r12, [r12+18h]
0x180008560  lea     rcx, [rsp+1E8h+var_180]
0x180008565  mov     rdx, rbp
0x180008568  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000856e  test    eax, eax
0x180008570  js      loc_1800086C0
0x180008576  cmp     byte ptr [r15], 0
0x18000857a  lea     rax, asc_18000EE88; " "
0x180008581  mov     rdx, r15
0x180008584  lea     rcx, [rsp+1E8h+var_1B8]
0x180008589  cmovz   rdx, rax
0x18000858d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180008593  test    eax, eax
0x180008595  js      loc_1800086C0
0x18000859b  lea     rcx, [rsp+1E8h+var_180]
0x1800085a0  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800085a6  cmp     eax, 0FFFFh
0x1800085ab  ja      loc_1800086BB
0x1800085b1  lea     rcx, [rsp+1E8h+var_1B8]
0x1800085b6  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800085bc  cmp     eax, 0FFFFh
0x1800085c1  ja      loc_1800086BB
0x1800085c7  mov     rax, [r12]
0x1800085cb  mov     rcx, r12
0x1800085ce  mov     [rsp+1E8h+var_28], rsi
0x1800085d6  mov     [rsp+1E8h+var_30], rdi
0x1800085de  mov     [rsp+1E8h+var_38], r14
0x1800085e6  mov     rax, [rax+20h]
0x1800085ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ef  mov     r14, rax
0x1800085f2  mov     rcx, [rax]
0x1800085f5  mov     rsi, [rcx+28h]
0x1800085f9  lea     rcx, [rsp+1E8h+var_1B8]
0x1800085fe  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180008604  lea     rcx, [rsp+1E8h+var_1B8]
0x180008609  mov     edi, eax
0x18000860b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180008611  lea     rcx, [rsp+1E8h+var_180]
0x180008616  mov     rbx, rax
0x180008619  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000861f  movzx   r9d, di
0x180008623  mov     [rsp+1E8h+var_1C8], 0
0x18000862b  mov     rdx, rax
0x18000862e  mov     r8, rbx
0x180008631  mov     rax, rsi
0x180008634  mov     rcx, r14
0x180008637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000863c  mov     r14, [rsp+1E8h+var_38]
0x180008644  mov     rdi, [rsp+1E8h+var_30]
0x18000864c  mov     rsi, [rsp+1E8h+var_28]
0x180008654  test    eax, eax
0x180008656  js      short loc_1800086C0
0x180008658  mov     rax, [r12]
0x18000865c  mov     rcx, r12
0x18000865f  mov     rax, [rax+110h]
0x180008666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000866b  mov     r8d, 4
0x180008671  mov     rcx, rax
0x180008674  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180008679  test    eax, eax
0x18000867b  jz      short loc_18000869E
0x18000867d  mov     rax, [r12]
0x180008681  mov     rcx, r12
0x180008684  mov     rax, [rax+110h]
0x18000868b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008690  mov     rcx, rax; struct IHttpTraceContext *
0x180008693  mov     r9, r15; char *
0x180008696  mov     r8, rbp; char *
0x180008699  call    ?RaiseEvent@FILTER_ADD_RESP_HEADER@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2@Z; IISFilterEvents::FILTER_ADD_RESP_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *)
0x18000869e  lea     rcx, [rsp+1E8h+var_1B8]
0x1800086a3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800086a9  lea     rcx, [rsp+1E8h+var_180]
0x1800086ae  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800086b4  mov     eax, 1
0x1800086b9  jmp     short loc_1800086EE
0x1800086bb  mov     eax, 80070057h
0x1800086c0  mov     ecx, eax; int
0x1800086c2  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800086c7  mov     ecx, eax
0x1800086c9  jmp     short loc_1800086D0
0x1800086cb  mov     ecx, 57h ; 'W'; dwErrCode
0x1800086d0  call    cs:__imp_SetLastError
0x1800086d6  lea     rcx, [rsp+1E8h+var_1B8]
0x1800086db  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800086e1  lea     rcx, [rsp+1E8h+var_180]
0x1800086e6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800086ec  xor     eax, eax
0x1800086ee  mov     rcx, [rsp+1E8h+var_48]
0x1800086f6  xor     rcx, rsp; StackCookie
0x1800086f9  call    __security_check_cookie
0x1800086fe  add     rsp, 1C8h
0x180008705  pop     r15
0x180008707  pop     r12
0x180008709  pop     rbp
0x18000870a  pop     rbx
0x18000870b  retn
```
