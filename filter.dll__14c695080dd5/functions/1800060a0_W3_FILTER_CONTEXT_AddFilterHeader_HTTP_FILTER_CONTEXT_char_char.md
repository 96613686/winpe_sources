# W3_FILTER_CONTEXT::AddFilterHeader(_HTTP_FILTER_CONTEXT *,char *,char *)

- ea: `0x1800060a0`
- end: `0x180006375`
- name: `?AddFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z`
- size: `725`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, char *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180004b80`
- `0x1800060a0`
- `0x180007930`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `msvcrt!strchr` at `0x1800061d8`
- `msvcrt!strchr` at `0x1800061f9`
- `msvcrt!strchr` at `0x1800061d8`
- `msvcrt!strchr` at `0x1800061f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000617b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006352`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000617b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006352`
- `iisutil!?SetLen@STRA@@QEAA_NK@Z` at `0x18000622a`
- `iisutil!?SetLen@STRA@@QEAA_NK@Z` at `0x18000622a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800061ca`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800061eb`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000620c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006294`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800062a2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800061ca`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800061eb`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000620c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006294`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800062a2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000625a`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000625a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180006287`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180006287`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006186`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006191`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006328`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006333`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000635d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006368`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006186`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006191`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006328`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006333`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000635d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006368`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800060da`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800060f3`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800060da`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800060f3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000615e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000615e`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::AddFilterHeader(struct _HTTP_FILTER_CONTEXT *a1, char *a2, char *a3)
{
  _QWORD *ServerContext; // rax
  __int64 v7; // r15
  __int64 v8; // r12
  const char *v9; // rdx
  signed int v10; // ecx
  const char *Str; // rax
  char *v13; // rax
  const char *v14; // rax
  char *v15; // rax
  char *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 (__fastcall *v20)(__int64, char *, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *v22; // rbx
  char *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  struct IHttpTraceContext *v26; // rax
  const struct _GUID *v27; // rdx
  _BYTE v28[56]; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v29[56]; // [rsp+68h] [rbp-180h] BYREF
  char v30[128]; // [rsp+A0h] [rbp-148h] BYREF
  char v31[128]; // [rsp+120h] [rbp-C8h] BYREF

  STRA::STRA((STRA *)v29, v30, 0x80u);
  STRA::STRA((STRA *)v28, v31, 0x80u);
  if ( !a1 || (ServerContext = a1->ServerContext) == 0 || !a2 || !a3 )
  {
    SetLastError(0x57u);
    STRA::~STRA((STRA *)v28);
    STRA::~STRA((STRA *)v29);
    return 0;
  }
  v7 = ServerContext[3];
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  v9 = a3;
  if ( !*a3 )
    v9 = " ";
  v10 = STRA::Copy((STRA *)v28, v9);
  if ( v10 < 0 )
    goto LABEL_8;
  Str = STRA::QueryStr((STRA *)v28);
  v13 = strchr(Str, 13);
  if ( v13 )
    *v13 = 0;
  v14 = STRA::QueryStr((STRA *)v28);
  v15 = strchr(v14, 10);
  if ( v15 )
    *v15 = 0;
  v16 = STRA::QueryStr((STRA *)v28);
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( v16[v18] );
  STRA::SetLen((STRA *)v28, v18);
  do
    ++v17;
  while ( a2[v17] );
  if ( (unsigned int)v17 <= 1 || (v19 = (unsigned int)(v17 - 1), a2[v19] != 58) )
  {
    LOWORD(v10) = 87;
    goto LABEL_9;
  }
  v10 = STRA::Copy((STRA *)v29, a2, v19);
  if ( v10 < 0
    || (v20 = *(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, _DWORD))(*(_QWORD *)v8 + 40LL),
        CCH = STRA::QueryCCH((STRA *)v28),
        v22 = STRA::QueryStr((STRA *)v28),
        v23 = STRA::QueryStr((STRA *)v29),
        v10 = v20(v8, v23, v22, CCH, 0),
        v10 < 0) )
  {
LABEL_8:
    if ( (v10 & 0x1FFF0000) != 0x70000 )
    {
LABEL_10:
      SetLastError(v10);
      STRA::~STRA((STRA *)v28);
      STRA::~STRA((STRA *)v29);
      return 0;
    }
LABEL_9:
    v10 = (unsigned __int16)v10;
    goto LABEL_10;
  }
  v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 272LL))(v7);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v24, v25, 4) )
  {
    v26 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 272LL))(v7);
    IISFilterEvents::FILTER_ADD_REQ_HEADER::RaiseEvent(v26, v27, a2, a3);
  }
  STRA::~STRA((STRA *)v28);
  STRA::~STRA((STRA *)v29);
  return 1;
}

```

## disassembly

```asm
0x1800060a0  push    rbx
0x1800060a2  push    rbp
0x1800060a3  push    r14
0x1800060a5  sub     rsp, 1D0h
0x1800060ac  mov     rax, cs:__security_cookie
0x1800060b3  xor     rax, rsp
0x1800060b6  mov     [rsp+1E8h+var_48], rax
0x1800060be  mov     rbp, r8
0x1800060c1  mov     r14, rdx
0x1800060c4  mov     rbx, rcx
0x1800060c7  lea     rdx, [rsp+1E8h+var_148]
0x1800060cf  mov     r8d, 80h
0x1800060d5  lea     rcx, [rsp+1E8h+var_180]
0x1800060da  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800060e0  mov     r8d, 80h
0x1800060e6  lea     rdx, [rsp+1E8h+var_C8]
0x1800060ee  lea     rcx, [rsp+1E8h+var_1B8]
0x1800060f3  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800060f9  test    rbx, rbx
0x1800060fc  jz      loc_18000634D
0x180006102  mov     rax, [rbx+8]
0x180006106  test    rax, rax
0x180006109  jz      loc_18000634D
0x18000610f  test    r14, r14
0x180006112  jz      loc_18000634D
0x180006118  test    rbp, rbp
0x18000611b  jz      loc_18000634D
0x180006121  mov     [rsp+1E8h+var_30], r12
0x180006129  mov     [rsp+1E8h+var_38], r15
0x180006131  mov     r15, [rax+18h]
0x180006135  mov     rcx, r15
0x180006138  mov     rax, [r15]
0x18000613b  mov     rax, [rax+18h]
0x18000613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006144  cmp     byte ptr [rbp+0], 0
0x180006148  lea     rcx, [rsp+1E8h+var_1B8]
0x18000614d  mov     r12, rax
0x180006150  mov     rdx, rbp
0x180006153  lea     rax, asc_18000EE88; " "
0x18000615a  cmovz   rdx, rax
0x18000615e  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180006164  mov     ecx, eax
0x180006166  test    eax, eax
0x180006168  jns     short loc_1800061C5
0x18000616a  mov     eax, ecx
0x18000616c  and     eax, 1FFF0000h
0x180006171  cmp     eax, 70000h
0x180006176  jnz     short loc_18000617B
0x180006178  movzx   ecx, cx; dwErrCode
0x18000617b  call    cs:__imp_SetLastError
0x180006181  lea     rcx, [rsp+1E8h+var_1B8]
0x180006186  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000618c  lea     rcx, [rsp+1E8h+var_180]
0x180006191  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006197  xor     eax, eax
0x180006199  mov     r12, [rsp+1E8h+var_30]
0x1800061a1  mov     r15, [rsp+1E8h+var_38]
0x1800061a9  mov     rcx, [rsp+1E8h+var_48]
0x1800061b1  xor     rcx, rsp; StackCookie
0x1800061b4  call    __security_check_cookie
0x1800061b9  add     rsp, 1D0h
0x1800061c0  pop     r14
0x1800061c2  pop     rbp
0x1800061c3  pop     rbx
0x1800061c4  retn
0x1800061c5  lea     rcx, [rsp+1E8h+var_1B8]
0x1800061ca  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800061d0  mov     rcx, rax; Str
0x1800061d3  mov     edx, 0Dh; Val
0x1800061d8  call    cs:__imp_strchr
0x1800061de  test    rax, rax
0x1800061e1  jz      short loc_1800061E6
0x1800061e3  mov     byte ptr [rax], 0
0x1800061e6  lea     rcx, [rsp+1E8h+var_1B8]
0x1800061eb  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800061f1  mov     rcx, rax; Str
0x1800061f4  mov     edx, 0Ah; Val
0x1800061f9  call    cs:__imp_strchr
0x1800061ff  test    rax, rax
0x180006202  jz      short loc_180006207
0x180006204  mov     byte ptr [rax], 0
0x180006207  lea     rcx, [rsp+1E8h+var_1B8]
0x18000620c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180006212  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006219  mov     rdx, rbx
0x18000621c  inc     rdx
0x18000621f  cmp     byte ptr [rax+rdx], 0
0x180006223  jnz     short loc_18000621C
0x180006225  lea     rcx, [rsp+1E8h+var_1B8]
0x18000622a  call    cs:__imp_?SetLen@STRA@@QEAA_NK@Z; STRA::SetLen(ulong)
0x180006230  inc     rbx
0x180006233  cmp     byte ptr [r14+rbx], 0
0x180006238  jnz     short loc_180006230
0x18000623a  cmp     ebx, 1
0x18000623d  jbe     loc_180006343
0x180006243  lea     r8d, [rbx-1]
0x180006247  cmp     byte ptr [r8+r14], 3Ah ; ':'
0x18000624c  jnz     loc_180006343
0x180006252  mov     rdx, r14
0x180006255  lea     rcx, [rsp+1E8h+var_180]
0x18000625a  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180006260  mov     ecx, eax
0x180006262  test    eax, eax
0x180006264  js      loc_18000616A
0x18000626a  mov     rax, [r12]
0x18000626e  lea     rcx, [rsp+1E8h+var_1B8]
0x180006273  mov     [rsp+1E8h+var_20], rsi
0x18000627b  mov     [rsp+1E8h+var_28], rdi
0x180006283  mov     rsi, [rax+28h]
0x180006287  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000628d  lea     rcx, [rsp+1E8h+var_1B8]
0x180006292  mov     edi, eax
0x180006294  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000629a  lea     rcx, [rsp+1E8h+var_180]
0x18000629f  mov     rbx, rax
0x1800062a2  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800062a8  movzx   r9d, di
0x1800062ac  mov     [rsp+1E8h+var_1C8], 0
0x1800062b4  mov     rdx, rax
0x1800062b7  mov     r8, rbx
0x1800062ba  mov     rax, rsi
0x1800062bd  mov     rcx, r12
0x1800062c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c5  mov     rdi, [rsp+1E8h+var_28]
0x1800062cd  mov     ecx, eax
0x1800062cf  mov     rsi, [rsp+1E8h+var_20]
0x1800062d7  test    eax, eax
0x1800062d9  js      loc_18000616A
0x1800062df  mov     rax, [r15]
0x1800062e2  mov     rcx, r15
0x1800062e5  mov     rax, [rax+110h]
0x1800062ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f1  mov     r8d, 4
0x1800062f7  mov     rcx, rax
0x1800062fa  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800062ff  test    eax, eax
0x180006301  jz      short loc_180006323
0x180006303  mov     rax, [r15]
0x180006306  mov     rcx, r15
0x180006309  mov     rax, [rax+110h]
0x180006310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006315  mov     rcx, rax; struct IHttpTraceContext *
0x180006318  mov     r9, rbp; char *
0x18000631b  mov     r8, r14; char *
0x18000631e  call    ?RaiseEvent@FILTER_ADD_REQ_HEADER@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2@Z; IISFilterEvents::FILTER_ADD_REQ_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *)
0x180006323  lea     rcx, [rsp+1E8h+var_1B8]
0x180006328  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000632e  lea     rcx, [rsp+1E8h+var_180]
0x180006333  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006339  mov     eax, 1
0x18000633e  jmp     loc_180006199
0x180006343  mov     ecx, 80070057h
0x180006348  jmp     loc_180006178
0x18000634d  mov     ecx, 57h ; 'W'; dwErrCode
0x180006352  call    cs:__imp_SetLastError
0x180006358  lea     rcx, [rsp+1E8h+var_1B8]
0x18000635d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006363  lea     rcx, [rsp+1E8h+var_180]
0x180006368  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000636e  xor     eax, eax
0x180006370  jmp     loc_1800061A9
```
