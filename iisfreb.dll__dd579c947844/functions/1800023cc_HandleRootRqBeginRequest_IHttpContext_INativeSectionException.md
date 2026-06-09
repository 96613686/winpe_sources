# HandleRootRqBeginRequest(IHttpContext *,INativeSectionException * *)

- ea: `0x1800023cc`
- end: `0x180002790`
- name: `?HandleRootRqBeginRequest@@YAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003440`

## callees

- `0x180001f1c`
- `0x1800023cc`
- `0x180003570`
- `0x180004440`
- `0x180005210`
- `0x1800053a4`
- `0x180005980`
- `0x18000a4dc`
- `0x18000a6d8`
- `0x18000ac52`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800025a5`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800025a5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002602`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000266e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002602`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000266e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002431`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002431`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000251e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000251e`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800025d0`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800025d0`
- `iisutil!PuDbgPrint` at `0x180002648`
- `iisutil!PuDbgPrint` at `0x180002648`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180002588`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180002588`

## string_xrefs

- `0x18000263c`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_module.cxx`

## pseudocode

```c
__int64 __fastcall HandleRootRqBeginRequest(struct IHttpContext *a1, struct INativeSectionException **a2)
{
  int ParsedMetadata; // edi
  __int64 v5; // rax
  __int64 (__fastcall ***v6)(_QWORD, void *); // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  FREB_LOG_NT_EVENT_TABLE *v10; // rcx
  int v11; // esi
  __int64 v12; // r15
  __int64 v13; // rbx
  __int64 v14; // r12
  unsigned int v15; // r15d
  const char *v16; // rax
  int v17; // esi
  int v18; // esi
  int v19; // ebx
  const char *v20; // rax
  __int64 v21; // r8
  struct IHttpTraceContext *v22; // rax
  signed int v24; // eax
  void *v25; // rax
  void *v26; // rsi
  void *v27; // rsi
  __int64 v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-CCh] BYREF
  struct FREB_META_STORED_CONTEXT *v31[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v32[32]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-98h]
  unsigned int v34; // [rsp+70h] [rbp-90h]
  unsigned int v35; // [rsp+78h] [rbp-88h]
  _BYTE v36[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v39[128]; // [rsp+C0h] [rbp-40h] BYREF

  v31[0] = 0;
  v29 = 0;
  ParsedMetadata = 0;
  memset_0(v39, 0, sizeof(v39));
  STRU::STRU((STRU *)v36, v39, 0x80u);
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 240LL))(a1);
  v6 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5);
  v7 = (**v6)(v6, g_pModuleContext);
  v8 = v7;
  if ( !v7 )
    goto LABEL_22;
  v9 = *(_QWORD *)(v7 + 72);
  if ( !v9 || !*(_DWORD *)(v9 + 12) )
    goto LABEL_22;
  *(_DWORD *)(v8 + 232) = 1;
  ParsedMetadata = FREB_META_STORED_CONTEXT::GetParsedMetadata(
                     a1,
                     v31,
                     (enum FREB_FAILURE_POINT *)&v29,
                     (struct STRU *)v36,
                     a2);
  if ( ParsedMetadata < 0 )
  {
    v11 = v29;
    if ( v29 )
    {
      if ( v38 )
      {
        v12 = *(_QWORD *)(v8 + 48);
        if ( v12 )
        {
          v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 24LL))(*(_QWORD *)(v8 + 48));
          v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
          LOWORD(v29) = 0;
          v15 = 0;
          v31[0] = 0;
          v30 = 0;
          STRU::STRU((STRU *)v32);
          v16 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v13 + 16LL))(
                                v13,
                                23,
                                &v29);
          v17 = v11 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              if ( v18 == 1 )
                v15 = 12836;
            }
            else
            {
              v15 = 12835;
            }
          }
          else
          {
            v15 = 12834;
          }
          if ( (int)LANG_STRING::GetString(
                      (LANG_STRING *)FREB_REQUEST_CONTEXT::sm_pLangString,
                      v16,
                      (unsigned __int16)v29,
                      v15,
                      (const unsigned __int16 **)v31,
                      &v30) >= 0
            && (int)STRU::Resize((STRU *)v32, 2 * (v30 + v38) + 2) >= 0 )
          {
            v19 = StringCchPrintfW(v33, (unsigned __int64)v34 >> 1, (const unsigned __int16 *)v31[0], v37);
            STRU::SyncWithBuffer((STRU *)v32);
            if ( v19 >= 0 )
              (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v14 + 192LL))(
                v14,
                v33,
                v35,
                1);
          }
          STRU::~STRU((STRU *)v32);
        }
      }
    }
    FREB_LOG_NT_EVENT_TABLE::LogEventInvalidFrebSection(v10, *a2, ParsedMetadata);
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_22;
    v20 = "Failed to handle trace event (GetParsedMetadata()) hr=0x%x";
    v21 = 1160;
    goto LABEL_21;
  }
  v24 = FREB_REQUEST_CONTEXT::InitializeInstance((FREB_REQUEST_CONTEXT *)v8, v31[0], 0);
  ParsedMetadata = v24;
  if ( v24 < 0 )
  {
    *(_OWORD *)v31 = 0;
    FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008F2, 2u, (const unsigned __int16 **const)v31, v24);
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_22;
    v20 = "Failed to handle trace event (freb request context initialize) hr=0x%x";
    v21 = 1184;
LABEL_21:
    LODWORD(v28) = ParsedMetadata;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_module.cxx",
      v21,
      "HandleRootRqBeginRequest",
      v20,
      v28);
LABEL_22:
    v22 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    EnableWWWServerProvider(v22, 0);
    goto LABEL_23;
  }
  if ( !*(_QWORD *)(v8 + 80) )
    goto LABEL_22;
  FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest((FREB_REQUEST_CONTEXT *)v8, a1);
  v25 = (void *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a1 + 144LL))(a1, 224);
  v26 = v25;
  if ( v25 )
  {
    memset_0(v25, 0, 0x70u);
    *(_QWORD *)(v8 + 264) = v26;
    v27 = (void *)(((unsigned __int64)v26 + 119) & 0xFFFFFFFFFFFFFFF8uLL);
    if ( v27 )
      memset_0(v27, 0, 0x70u);
    else
      v27 = 0;
    *(_QWORD *)(v8 + 248) = v27;
    *(_QWORD *)(v8 + 256) = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a1 + 144LL))(a1, 44);
  }
  FREB_REQUEST_CONTEXT::StartTimeoutMonitorForRequest((FREB_REQUEST_CONTEXT *)v8);
LABEL_23:
  STRU::~STRU((STRU *)v36);
  return (unsigned int)ParsedMetadata;
}

```

## disassembly

```asm
0x1800023cc  mov     [rsp-8+arg_10], rbx
0x1800023d1  push    rbp
0x1800023d2  push    rsi
0x1800023d3  push    rdi
0x1800023d4  push    r12
0x1800023d6  push    r13
0x1800023d8  push    r14
0x1800023da  push    r15
0x1800023dc  lea     rbp, [rsp-0D0h]
0x1800023e4  sub     rsp, 1D0h
0x1800023eb  mov     rax, cs:__security_cookie
0x1800023f2  xor     rax, rsp
0x1800023f5  mov     [rbp+100h+var_40], rax
0x1800023fc  xor     r12d, r12d
0x1800023ff  mov     r13, rdx
0x180002402  mov     r14, rcx
0x180002405  mov     [rsp+200h+var_1C8], r12
0x18000240a  xor     edx, edx; Val
0x18000240c  mov     [rsp+200h+var_1D0], r12d
0x180002411  lea     rcx, [rbp+100h+var_140]; void *
0x180002415  mov     r8d, 100h; Size
0x18000241b  mov     edi, r12d
0x18000241e  call    memset_0
0x180002423  mov     r8d, 80h
0x180002429  lea     rdx, [rbp+100h+var_140]
0x18000242d  lea     rcx, [rbp+100h+var_180]
0x180002431  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002437  mov     rax, [r14]
0x18000243a  mov     rcx, r14
0x18000243d  mov     rax, [rax+0F0h]
0x180002444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002449  mov     rcx, rax
0x18000244c  mov     rax, [rax]
0x18000244f  mov     rax, [rax+38h]
0x180002453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002458  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x18000245f  mov     rcx, rax
0x180002462  mov     rax, [rax]
0x180002465  mov     rax, [rax]
0x180002468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000246d  mov     rbx, rax
0x180002470  test    rax, rax
0x180002473  jz      loc_18000264E
0x180002479  mov     rax, [rax+48h]
0x18000247d  test    rax, rax
0x180002480  jz      loc_18000264E
0x180002486  cmp     [rax+0Ch], r12d
0x18000248a  jz      loc_18000264E
0x180002490  lea     r9, [rbp+100h+var_180]; struct STRU *
0x180002494  mov     dword ptr [rbx+0E8h], 1
0x18000249e  lea     r8, [rsp+200h+var_1D0]; enum FREB_FAILURE_POINT *
0x1800024a3  mov     [rsp+200h+var_1E0], r13; struct INativeSectionException **
0x1800024a8  lea     rdx, [rsp+200h+var_1C8]; struct FREB_META_STORED_CONTEXT **
0x1800024ad  mov     rcx, r14; struct IHttpContext *
0x1800024b0  call    ?GetParsedMetadata@FREB_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAW4FREB_FAILURE_POINT@@PEAVSTRU@@PEAPEAVINativeSectionException@@@Z; FREB_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,FREB_META_STORED_CONTEXT * *,FREB_FAILURE_POINT *,STRU *,INativeSectionException * *)
0x1800024b5  mov     edi, eax
0x1800024b7  test    eax, eax
0x1800024b9  jns     loc_1800026A0
0x1800024bf  mov     esi, [rsp+200h+var_1D0]
0x1800024c3  test    esi, esi
0x1800024c5  jz      loc_180002608
0x1800024cb  cmp     [rbp+100h+var_150], r12d
0x1800024cf  jz      loc_180002608
0x1800024d5  mov     r15, [rbx+30h]
0x1800024d9  test    r15, r15
0x1800024dc  jz      loc_180002608
0x1800024e2  mov     rax, [r15]
0x1800024e5  mov     rcx, r15
0x1800024e8  mov     rax, [rax+18h]
0x1800024ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f1  mov     rcx, [r15]
0x1800024f4  mov     rbx, rax
0x1800024f7  mov     rax, [rcx+20h]
0x1800024fb  mov     rcx, r15
0x1800024fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002503  xor     ecx, ecx
0x180002505  mov     r12, rax
0x180002508  mov     word ptr [rsp+200h+var_1D0], cx
0x18000250d  xor     r15d, r15d
0x180002510  mov     [rsp+200h+var_1C8], rcx
0x180002515  mov     [rsp+200h+var_1CC], ecx
0x180002519  lea     rcx, [rsp+200h+var_1B8]
0x18000251e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002524  mov     rcx, [rbx]
0x180002527  lea     r8, [rsp+200h+var_1D0]
0x18000252c  lea     edx, [r15+17h]
0x180002530  mov     rax, [rcx+10h]
0x180002534  mov     rcx, rbx
0x180002537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000253c  sub     esi, 1
0x18000253f  jz      short loc_18000255B
0x180002541  sub     esi, 1
0x180002544  jz      short loc_180002553
0x180002546  cmp     esi, 1
0x180002549  jnz     short loc_180002561
0x18000254b  mov     r15d, 3224h
0x180002551  jmp     short loc_180002561
0x180002553  mov     r15d, 3223h
0x180002559  jmp     short loc_180002561
0x18000255b  mov     r15d, 3222h
0x180002561  movzx   r8d, word ptr [rsp+200h+var_1D0]
0x180002567  lea     rcx, [rsp+200h+var_1CC]
0x18000256c  mov     [rsp+200h+var_1D8], rcx
0x180002571  mov     r9d, r15d
0x180002574  lea     rcx, [rsp+200h+var_1C8]
0x180002579  mov     rdx, rax
0x18000257c  mov     [rsp+200h+var_1E0], rcx
0x180002581  mov     rcx, cs:?sm_pLangString@FREB_REQUEST_CONTEXT@@0PEAVLANG_STRING@@EA; LANG_STRING * FREB_REQUEST_CONTEXT::sm_pLangString
0x180002588  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x18000258e  test    eax, eax
0x180002590  js      short loc_1800025FD
0x180002592  mov     edx, [rbp+100h+var_150]
0x180002595  lea     rcx, [rsp+200h+var_1B8]
0x18000259a  add     edx, [rsp+200h+var_1CC]
0x18000259e  lea     edx, ds:2[rdx*2]
0x1800025a5  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800025ab  test    eax, eax
0x1800025ad  js      short loc_1800025FD
0x1800025af  mov     edx, [rsp+200h+var_190]
0x1800025b3  mov     r9, [rbp+100h+var_160]
0x1800025b7  mov     r8, [rsp+200h+var_1C8]; unsigned __int16 *
0x1800025bc  mov     rcx, [rsp+200h+var_198]; unsigned __int16 *
0x1800025c1  shr     rdx, 1; unsigned __int64
0x1800025c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025c9  lea     rcx, [rsp+200h+var_1B8]
0x1800025ce  mov     ebx, eax
0x1800025d0  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800025d6  test    ebx, ebx
0x1800025d8  js      short loc_1800025FD
0x1800025da  mov     rax, [r12]
0x1800025de  mov     r9d, 1
0x1800025e4  mov     r8d, [rsp+200h+var_188]
0x1800025e9  mov     rcx, r12
0x1800025ec  mov     rdx, [rsp+200h+var_198]
0x1800025f1  mov     rax, [rax+0C0h]
0x1800025f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025fd  lea     rcx, [rsp+200h+var_1B8]
0x180002602  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002608  mov     rdx, [r13+0]; struct INativeSectionException *
0x18000260c  mov     r8d, edi; int
0x18000260f  call    ?LogEventInvalidFrebSection@FREB_LOG_NT_EVENT_TABLE@@QEAAXPEAVINativeSectionException@@J@Z; FREB_LOG_NT_EVENT_TABLE::LogEventInvalidFrebSection(INativeSectionException *,long)
0x180002614  test    byte ptr cs:g_dwDebugFlags, 3
0x18000261b  jz      short loc_18000264E
0x18000261d  lea     rax, aFailedToHandle; "Failed to handle trace event (GetParsed"...
0x180002624  mov     r8d, 488h
0x18000262a  mov     rcx, cs:g_pDebug
0x180002631  lea     r9, aHandlerootrqbe; "HandleRootRqBeginRequest"
0x180002638  mov     dword ptr [rsp+200h+var_1D8], edi
0x18000263c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002643  mov     [rsp+200h+var_1E0], rax
0x180002648  call    cs:__imp_PuDbgPrint
0x18000264e  mov     rax, [r14]
0x180002651  mov     rcx, r14
0x180002654  mov     rax, [rax+110h]
0x18000265b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002660  mov     rcx, rax; struct IHttpTraceContext *
0x180002663  xor     edx, edx; int
0x180002665  call    ?EnableWWWServerProvider@@YAJPEAVIHttpTraceContext@@H@Z; EnableWWWServerProvider(IHttpTraceContext *,int)
0x18000266a  lea     rcx, [rbp+100h+var_180]
0x18000266e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002674  mov     eax, edi
0x180002676  mov     rcx, [rbp+100h+var_40]
0x18000267d  xor     rcx, rsp; StackCookie
0x180002680  call    __security_check_cookie
0x180002685  mov     rbx, [rsp+200h+arg_10]
0x18000268d  add     rsp, 1D0h
0x180002694  pop     r15
0x180002696  pop     r14
0x180002698  pop     r13
0x18000269a  pop     r12
0x18000269c  pop     rdi
0x18000269d  pop     rsi
0x18000269e  pop     rbp
0x18000269f  retn
0x1800026a0  mov     rdx, [rsp+200h+var_1C8]; struct FREB_META_STORED_CONTEXT *
0x1800026a5  xor     r8d, r8d; int
0x1800026a8  mov     rcx, rbx; this
0x1800026ab  call    ?InitializeInstance@FREB_REQUEST_CONTEXT@@QEAAJPEAVFREB_META_STORED_CONTEXT@@H@Z; FREB_REQUEST_CONTEXT::InitializeInstance(FREB_META_STORED_CONTEXT *,int)
0x1800026b0  mov     edi, eax
0x1800026b2  test    eax, eax
0x1800026b4  jns     short loc_1800026F4
0x1800026b6  xorps   xmm0, xmm0
0x1800026b9  lea     r8, [rsp+200h+var_1C8]; unsigned __int16 **
0x1800026be  mov     edx, 2; unsigned __int16
0x1800026c3  mov     r9d, eax; unsigned int
0x1800026c6  mov     ecx, 800008F2h; unsigned int
0x1800026cb  movups  xmmword ptr [rsp+200h+var_1C8], xmm0
0x1800026d0  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800026d5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800026dc  jz      loc_18000264E
0x1800026e2  lea     rax, aFailedToHandle_0; "Failed to handle trace event (freb requ"...
0x1800026e9  mov     r8d, 4A0h
0x1800026ef  jmp     loc_18000262A
0x1800026f4  cmp     [rbx+50h], r12
0x1800026f8  jz      loc_18000264E
0x1800026fe  mov     rdx, r14; struct IHttpContext *
0x180002701  mov     rcx, rbx; this
0x180002704  call    ?SetFrebTraceConfigForRequest@FREB_REQUEST_CONTEXT@@QEAAJPEAVIHttpContext@@@Z; FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest(IHttpContext *)
0x180002709  mov     rax, [r14]
0x18000270c  mov     edx, 0E0h
0x180002711  mov     rcx, r14
0x180002714  mov     rax, [rax+90h]
0x18000271b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002720  mov     rsi, rax
0x180002723  test    rax, rax
0x180002726  jz      short loc_180002783
0x180002728  mov     r15d, 70h ; 'p'
0x18000272e  xor     edx, edx; Val
0x180002730  mov     r8d, r15d; Size
0x180002733  mov     rcx, rax; void *
0x180002736  call    memset_0
0x18000273b  mov     [rbx+108h], rsi
0x180002742  add     rsi, 77h ; 'w'
0x180002746  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18000274a  jz      short loc_18000275B
0x18000274c  mov     r8d, r15d; Size
0x18000274f  xor     edx, edx; Val
0x180002751  mov     rcx, rsi; void *
0x180002754  call    memset_0
0x180002759  jmp     short loc_18000275E
0x18000275b  mov     rsi, r12
0x18000275e  mov     [rbx+0F8h], rsi
0x180002765  mov     edx, 2Ch ; ','
0x18000276a  mov     rax, [r14]
0x18000276d  mov     rcx, r14
0x180002770  mov     rax, [rax+90h]
0x180002777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000277c  mov     [rbx+100h], rax
0x180002783  mov     rcx, rbx; this
0x180002786  call    ?StartTimeoutMonitorForRequest@FREB_REQUEST_CONTEXT@@QEAAXXZ; FREB_REQUEST_CONTEXT::StartTimeoutMonitorForRequest(void)
0x18000278b  jmp     loc_18000266A
```
