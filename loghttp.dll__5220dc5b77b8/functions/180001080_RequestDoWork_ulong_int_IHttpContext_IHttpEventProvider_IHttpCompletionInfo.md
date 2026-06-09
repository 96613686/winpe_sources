# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001080`
- end: `0x18000171b`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `1691`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, __int64, __int64)`
- caller_count: `17`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001050`
- `0x180003ba0`
- `0x180003c10`
- `0x180003c70`
- `0x180003ca0`
- `0x180003d10`
- `0x180003d80`
- `0x180003df0`
- `0x180003e60`
- `0x180003ed0`
- `0x180003f40`
- `0x180003fb0`
- `0x180004220`
- `0x180004290`
- `0x180004300`
- `0x180004370`
- `0x180004420`

## callees

- `0x180001080`
- `0x180001730`
- `0x180001cd0`
- `0x1800025b0`
- `0x1800030bc`
- `0x180003318`
- `0x180003510`
- `0x180004b30`
- `0x1800056f2`
- `0x180005720`
- `0x180006010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180001305`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001710`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001305`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001710`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800012c0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800012c0`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800012d3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800012d3`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  __int64 v8; // rax
  __int64 v9; // rdi
  LOGGING *v10; // r14
  __int64 v11; // rax
  __int64 v12; // r15
  URL_LOGGING *v13; // rdi
  __int64 (__fastcall ***v14)(_QWORD, void *); // rax
  __int64 v15; // rdi
  __int64 v17; // rax
  int v18; // r12d
  HTTP_LOG_HANDLER *v19; // rcx
  unsigned int v20; // ebx
  LOGGING *v21; // rax
  LOGGING *v22; // rax
  int v23; // r15d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // r15d
  int v28; // r12d
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // r12d
  __int64 v32; // rax
  __int64 v33; // rax
  int CustomLogString; // eax
  __int64 v35; // rax
  unsigned __int16 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  struct INativeSectionException *v38; // [rsp+70h] [rbp-90h] BYREF
  struct EXTENDED_LOG_DATA *v39; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v40[64]; // [rsp+80h] [rbp-80h] BYREF
  char v41[256]; // [rsp+C0h] [rbp-40h] BYREF

  v38 = 0;
  v37 = 0;
  if ( a5 )
  {
    (**(void (__fastcall ***)(__int64))a5)(a5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
  }
  if ( a1 == 0x20000000 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 48LL))(a4) )
      return 0;
    v8 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a3)(a3);
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v10 = (LOGGING *)(**(__int64 (__fastcall ***)(__int64, void *))v9)(v9, s_pHttpLogModuleContext);
    if ( !v10 )
    {
      v21 = (LOGGING *)operator new(0x80u);
      if ( !v21 )
        return 0;
      v22 = LOGGING::LOGGING(v21);
      v10 = v22;
      if ( !v22 )
        return 0;
      v23 = LOGGING::ActivateLogging(v22, a3);
      if ( v23 < 0 )
      {
        v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        if ( *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24) + 8) < 0x190u )
        {
          v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
          v26 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v26 + 24LL))(
            v26,
            500,
            "Internal Server Error",
            0,
            v23,
            0,
            0);
        }
        (**(void (__fastcall ***)(LOGGING *))v10)(v10);
        return 0;
      }
      v27 = (*(__int64 (__fastcall **)(__int64, LOGGING *, void *))(*(_QWORD *)v9 + 8LL))(
              v9,
              v10,
              s_pHttpLogModuleContext);
      if ( v27 < 0 )
      {
        (**(void (__fastcall ***)(LOGGING *))v10)(v10);
        if ( v27 != -2147024811 )
          return 0;
        v10 = (LOGGING *)(**(__int64 (__fastcall ***)(__int64, void *))v9)(v9, s_pHttpLogModuleContext);
      }
    }
    if ( !*((_DWORD *)v10 + 3) )
      return 0;
    v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
    v13 = (URL_LOGGING *)(**(__int64 (__fastcall ***)(__int64, void *))v12)(v12, s_pHttpLogModuleContext);
    if ( !v13 )
    {
      v13 = (URL_LOGGING *)operator new(0x10u);
      if ( !v13 )
        return 0;
      *((_DWORD *)v13 + 2) = 0;
      *(_QWORD *)v13 = &URL_LOGGING::`vftable';
      v28 = URL_LOGGING::Initialize(v13, a3, &v38);
      if ( v28 < 0 )
      {
        v29 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 80LL))(v29);
        if ( v38 )
          (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v38)(
            v38,
            &IID_IAppHostConfigException,
            &v37);
        v30 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v30 + 24LL))(
          v30,
          500,
          "Internal Server Error",
          19,
          v28,
          v37,
          0);
        if ( v37 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          v37 = 0;
        }
        if ( v38 )
        {
          (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v38 + 16LL))(v38);
          v38 = 0;
        }
        (**(void (__fastcall ***)(URL_LOGGING *))v13)(v13);
LABEL_11:
        v14 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
        if ( (**v14)(v14, s_pHttpLogModuleContext) )
          return 0;
        v15 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(a3, 512);
        if ( !v15 )
          return 0;
        *(_QWORD *)v15 = &HTTP_LOG_HANDLER::`vftable';
        memset_0((void *)(v15 + 152), 0, 0x62u);
        memset_0((void *)(v15 + 250), 0, 0x100u);
        memset_0((void *)(v15 + 12), 0, 0x8Cu);
        *(_DWORD *)(v15 + 8) = 0;
        v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v17 + 8LL))(v17, v15, s_pHttpLogModuleContext);
        v18 = *((_DWORD *)v10 + 29);
        v39 = 0;
        STRA::STRA((STRA *)v40, v41, 0xF5u);
        if ( !v18 )
          goto LABEL_15;
        if ( !*((_DWORD *)v10 + 30) )
          goto LABEL_45;
        CustomLogString = HTTP_LOG_HANDLER::GetCustomLogString(v19, a3, v10, (struct STRA *)v40);
        if ( CustomLogString >= 0 )
        {
LABEL_46:
          v35 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 112LL))(v35, 13);
LABEL_15:
          STRA::QueryStr((LOGGING *)((char *)v10 + 16));
          v20 = HTTP_LOG_HANDLER::DoWork(v15, a3, a4);
          STRA::~STRA((STRA *)v40);
          return v20;
        }
        if ( CustomLogString == -2147024621 )
        {
LABEL_45:
          if ( (int)HTTP_LOG_HANDLER::GetCustomLogValues(v19, a3, v10, &v39) >= 0 )
            goto LABEL_46;
        }
        STRA::~STRA((STRA *)v40);
        return 0;
      }
      v31 = (*(__int64 (__fastcall **)(__int64, URL_LOGGING *, void *))(*(_QWORD *)v12 + 8LL))(
              v12,
              v13,
              s_pHttpLogModuleContext);
      if ( v31 < 0 )
      {
        (**(void (__fastcall ***)(URL_LOGGING *))v13)(v13);
        if ( v31 != -2147024811 )
          return 0;
        v13 = (URL_LOGGING *)(**(__int64 (__fastcall ***)(__int64, void *))v12)(v12, s_pHttpLogModuleContext);
      }
    }
    if ( *((_DWORD *)v13 + 3) )
      return 0;
    v36 = 0;
    if ( *((_DWORD *)v13 + 2) == 1 )
    {
      v33 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v33 + 184LL))(
        v33,
        &v36,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0);
      if ( v36 > 0x18Fu )
        return 0;
    }
    else if ( *((_DWORD *)v13 + 2) == 2 )
    {
      v32 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v32 + 184LL))(
        v32,
        &v36,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0);
      if ( v36 < 0x190u )
        return 0;
    }
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x180001080  push    rbp
0x180001082  push    rbx
0x180001083  push    rsi
0x180001084  push    rdi
0x180001085  push    r13
0x180001087  push    r14
0x180001089  lea     rbp, [rsp-0D8h]
0x180001091  sub     rsp, 1D8h
0x180001098  mov     rax, cs:__security_cookie
0x18000109f  xor     rax, rsp
0x1800010a2  mov     [rbp+100h+var_40], rax
0x1800010a9  mov     r14, [rbp+100h+arg_20]
0x1800010b0  xor     r13d, r13d
0x1800010b3  mov     [rsp+200h+var_190], r13
0x1800010b8  mov     rbx, r9
0x1800010bb  mov     [rsp+200h+var_198], r13
0x1800010c0  mov     rsi, r8
0x1800010c3  mov     edi, ecx
0x1800010c5  test    r14, r14
0x1800010c8  jnz     loc_180001312
0x1800010ce  cmp     edi, 20000000h
0x1800010d4  jnz     loc_180001334
0x1800010da  mov     rax, [rbx]
0x1800010dd  mov     rcx, rbx
0x1800010e0  mov     [rsp+200h+arg_0], r12
0x1800010e8  mov     [rsp+200h+var_30], r15
0x1800010f0  mov     rax, [rax+30h]
0x1800010f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010f9  test    eax, eax
0x1800010fb  jz      loc_180001203
0x180001101  mov     rax, [rsi]
0x180001104  mov     rcx, rsi
0x180001107  mov     rax, [rax]
0x18000110a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000110f  mov     rdx, rax
0x180001112  mov     rcx, [rax]
0x180001115  mov     rax, [rcx+10h]
0x180001119  mov     rcx, rdx
0x18000111c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001121  mov     rdx, cs:?s_pHttpLogModuleContext@@3PEAXEA; void * s_pHttpLogModuleContext
0x180001128  mov     rdi, rax
0x18000112b  mov     rcx, [rax]
0x18000112e  mov     rax, [rcx]
0x180001131  mov     rcx, rdi
0x180001134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001139  mov     r14, rax
0x18000113c  test    rax, rax
0x18000113f  jz      loc_18000133B
0x180001145  cmp     [r14+0Ch], r13d
0x180001149  jz      loc_180001203
0x18000114f  mov     rax, [rsi]
0x180001152  mov     rcx, rsi
0x180001155  mov     rax, [rax+0A0h]
0x18000115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001161  mov     rdx, rax
0x180001164  mov     rcx, [rax]
0x180001167  mov     rax, [rcx+18h]
0x18000116b  mov     rcx, rdx
0x18000116e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001173  mov     rdx, cs:?s_pHttpLogModuleContext@@3PEAXEA; void * s_pHttpLogModuleContext
0x18000117a  mov     r15, rax
0x18000117d  mov     rcx, [rax]
0x180001180  mov     rax, [rcx]
0x180001183  mov     rcx, r15
0x180001186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000118b  mov     rdi, rax
0x18000118e  test    rax, rax
0x180001191  jz      loc_180001477
0x180001197  cmp     [rdi+0Ch], r13d
0x18000119b  jnz     short loc_180001203
0x18000119d  mov     [rsp+200h+var_1A0], r13w
0x1800011a3  mov     ecx, [rdi+8]
0x1800011a6  sub     ecx, 1
0x1800011a9  jz      loc_180001646
0x1800011af  cmp     ecx, 1
0x1800011b2  jz      loc_1800015E4
0x1800011b8  mov     rax, [rsi]
0x1800011bb  mov     rcx, rsi
0x1800011be  mov     rax, [rax+38h]
0x1800011c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011c7  mov     rdx, cs:?s_pHttpLogModuleContext@@3PEAXEA; void * s_pHttpLogModuleContext
0x1800011ce  mov     r8, rax
0x1800011d1  mov     rcx, [rax]
0x1800011d4  mov     rax, [rcx]
0x1800011d7  mov     rcx, r8
0x1800011da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011df  test    rax, rax
0x1800011e2  jnz     short loc_180001203
0x1800011e4  mov     rax, [rsi]
0x1800011e7  mov     edx, 200h
0x1800011ec  mov     rcx, rsi
0x1800011ef  mov     rax, [rax+90h]
0x1800011f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011fb  mov     rdi, rax
0x1800011fe  test    rax, rax
0x180001201  jnz     short loc_180001234
0x180001203  xor     eax, eax
0x180001205  mov     r12, [rsp+200h+arg_0]
0x18000120d  mov     r15, [rsp+200h+var_30]
0x180001215  mov     rcx, [rbp+100h+var_40]
0x18000121c  xor     rcx, rsp; StackCookie
0x18000121f  call    __security_check_cookie
0x180001224  add     rsp, 1D8h
0x18000122b  pop     r14
0x18000122d  pop     r13
0x18000122f  pop     rdi
0x180001230  pop     rsi
0x180001231  pop     rbx
0x180001232  pop     rbp
0x180001233  retn
0x180001234  lea     rax, ??_7HTTP_LOG_HANDLER@@6B@; const HTTP_LOG_HANDLER::`vftable'
0x18000123b  xor     edx, edx; Val
0x18000123d  lea     rcx, [rdi+98h]; void *
0x180001244  mov     [rdi], rax
0x180001247  mov     r8d, 62h ; 'b'; Size
0x18000124d  call    memset_0
0x180001252  lea     rcx, [rdi+0FAh]; void *
0x180001259  xor     edx, edx; Val
0x18000125b  mov     r8d, 100h; Size
0x180001261  call    memset_0
0x180001266  lea     rcx, [rdi+0Ch]; void *
0x18000126a  xor     edx, edx; Val
0x18000126c  mov     r8d, 8Ch; Size
0x180001272  call    memset_0
0x180001277  mov     [rdi+8], r13d
0x18000127b  mov     rcx, rsi
0x18000127e  mov     rax, [rsi]
0x180001281  mov     rax, [rax+38h]
0x180001285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000128a  mov     r8, cs:?s_pHttpLogModuleContext@@3PEAXEA; void * s_pHttpLogModuleContext
0x180001291  mov     r9, rax
0x180001294  mov     rdx, rdi
0x180001297  mov     rcx, [rax]
0x18000129a  mov     rax, [rcx+8]
0x18000129e  mov     rcx, r9
0x1800012a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012a6  mov     r12d, [r14+74h]
0x1800012aa  lea     rdx, [rbp+100h+var_140]
0x1800012ae  mov     r8d, 0F5h
0x1800012b4  mov     [rsp+200h+var_188], r13
0x1800012b9  lea     rcx, [rbp+100h+var_180]
0x1800012bd  mov     r15, r13
0x1800012c0  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800012c6  test    r12d, r12d
0x1800012c9  jnz     loc_1800016A8
0x1800012cf  lea     rcx, [r14+10h]
0x1800012d3  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800012d9  lea     rcx, [rbp+100h+var_180]
0x1800012dd  mov     r8, rbx
0x1800012e0  mov     [rsp+200h+var_1B8], rcx
0x1800012e5  mov     rdx, rsi
0x1800012e8  mov     [rsp+200h+var_1C0], r15
0x1800012ed  mov     rcx, rdi
0x1800012f0  mov     dword ptr [rsp+200h+var_1C8], r12d
0x1800012f5  mov     [rsp+200h+var_1D0], rax
0x1800012fa  call    ?DoWork@HTTP_LOG_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVISendResponseProvider@@HKJPEADHPEAVEXTENDED_LOG_DATA@@PEAVSTRA@@@Z; HTTP_LOG_HANDLER::DoWork(IHttpContext *,ISendResponseProvider *,int,ulong,long,char *,int,EXTENDED_LOG_DATA *,STRA *)
0x1800012ff  lea     rcx, [rbp+100h+var_180]
0x180001303  mov     ebx, eax
0x180001305  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000130b  mov     eax, ebx
0x18000130d  jmp     loc_180001205
0x180001312  mov     rax, [r14]
0x180001315  mov     rcx, r14
0x180001318  mov     rax, [rax]
0x18000131b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001320  mov     rax, [r14]
0x180001323  mov     rcx, r14
0x180001326  mov     rax, [rax+8]
0x18000132a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000132f  jmp     loc_1800010CE
0x180001334  xor     eax, eax
0x180001336  jmp     loc_180001215
0x18000133b  mov     ecx, 80h; Size
0x180001340  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001345  test    rax, rax
0x180001348  jz      loc_180001203
0x18000134e  mov     rcx, rax; this
0x180001351  call    ??0LOGGING@@QEAA@XZ; LOGGING::LOGGING(void)
0x180001356  mov     r14, rax
0x180001359  test    rax, rax
0x18000135c  jz      loc_180001203
0x180001362  mov     r8d, cs:?g_fDoCentralBinaryLogging@@3HA; int
0x180001369  mov     rdx, rsi; struct IHttpContext *
0x18000136c  mov     rcx, rax; this
0x18000136f  call    ?ActivateLogging@LOGGING@@QEAAJPEAVIHttpContext@@H@Z; LOGGING::ActivateLogging(IHttpContext *,int)
0x180001374  mov     r15d, eax
0x180001377  test    eax, eax
0x180001379  jns     loc_18000141B
0x18000137f  mov     rcx, [rsi]
0x180001382  mov     rax, [rcx+20h]
0x180001386  mov     rcx, rsi
0x180001389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000138e  mov     rdx, rax
0x180001391  mov     rcx, [rax]
0x180001394  mov     rax, [rcx+8]
0x180001398  mov     rcx, rdx
0x18000139b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013a0  mov     ecx, 190h
0x1800013a5  cmp     [rax+8], cx
0x1800013a9  jnb     short loc_180001408
0x1800013ab  mov     rax, [rsi]
0x1800013ae  mov     rcx, rsi
0x1800013b1  mov     rax, [rax+20h]
0x1800013b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ba  mov     rcx, rax
0x1800013bd  mov     rdx, [rax]
0x1800013c0  mov     rax, [rdx+50h]
0x1800013c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013c9  mov     rax, [rsi]
0x1800013cc  mov     rcx, rsi
0x1800013cf  mov     rax, [rax+20h]
0x1800013d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d8  mov     r10, rax
0x1800013db  mov     dword ptr [rsp+200h+var_1D0], r13d
0x1800013e0  xor     r9d, r9d
0x1800013e3  mov     [rsp+200h+var_1D8], r13
0x1800013e8  mov     edx, 1F4h
0x1800013ed  mov     dword ptr [rsp+200h+var_1E0], r15d
0x1800013f2  mov     rcx, [rax]
0x1800013f5  lea     r8, aInternalServer; "Internal Server Error"
0x1800013fc  mov     rax, [rcx+18h]
0x180001400  mov     rcx, r10
0x180001403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001408  mov     rax, [r14]
0x18000140b  mov     rcx, r14
0x18000140e  mov     rax, [rax]
0x180001411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001416  jmp     loc_180001203
0x18000141b  mov     rax, [rdi]
0x18000141e  mov     rdx, r14
0x180001421  mov     r8, cs:?s_pHttpLogModuleContext@@3PEAXEA; void * s_pHttpLogModuleContext
0x180001428  mov     rcx, rdi
0x18000142b  mov     rax, [rax+8]
0x18000142f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001434  mov     r15d, eax
0x180001437  test    eax, eax
0x180001439  jns     loc_180001145
0x18000143f  mov     rcx, [r14]
0x180001442  mov     rax, [rcx]
0x180001445  mov     rcx, r14
0x180001448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144d  cmp     r15d, 80070055h
0x180001454  jnz     loc_180001203
0x18000145a  mov     rax, [rdi]
0x18000145d  mov     rcx, rdi
0x180001460  mov     rdx, cs:?s_pHttpLogModuleContext@@3PEAXEA; void * s_pHttpLogModuleContext
0x180001467  mov     rax, [rax]
0x18000146a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146f  mov     r14, rax
0x180001472  jmp     loc_180001145
0x180001477  mov     ecx, 10h; Size
0x18000147c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001481  mov     rdi, rax
0x180001484  test    rax, rax
0x180001487  jz      loc_180001203
0x18000148d  lea     rax, ??_7URL_LOGGING@@6B@; const URL_LOGGING::`vftable'
0x180001494  mov     [rdi+8], r13d
0x180001498  lea     r8, [rsp+200h+var_190]; struct INativeSectionException **
0x18000149d  mov     [rdi], rax
0x1800014a0  mov     rdx, rsi; struct IHttpContext *
0x1800014a3  mov     rcx, rdi; this
0x1800014a6  call    ?Initialize@URL_LOGGING@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; URL_LOGGING::Initialize(IHttpContext *,INativeSectionException * *)
0x1800014ab  mov     r12d, eax
0x1800014ae  test    eax, eax
0x1800014b0  jns     loc_180001588
0x1800014b6  mov     rcx, [rsi]
0x1800014b9  mov     rax, [rcx+20h]
0x1800014bd  mov     rcx, rsi
0x1800014c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014c5  mov     rdx, rax
0x1800014c8  mov     rcx, [rax]
0x1800014cb  mov     rax, [rcx+50h]
0x1800014cf  mov     rcx, rdx
0x1800014d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d7  mov     rcx, [rsp+200h+var_190]
0x1800014dc  test    rcx, rcx
0x1800014df  jz      short loc_1800014F8
0x1800014e1  mov     rax, [rcx]
0x1800014e4  lea     r8, [rsp+200h+var_198]
0x1800014e9  lea     rdx, IID_IAppHostConfigException
0x1800014f0  mov     rax, [rax]
0x1800014f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014f8  mov     rax, [rsi]
0x1800014fb  mov     rcx, rsi
0x1800014fe  mov     rax, [rax+20h]
0x180001502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001507  mov     r10, rax
0x18000150a  mov     dword ptr [rsp+200h+var_1D0], r13d
0x18000150f  mov     edx, 1F4h
0x180001514  lea     r8, aInternalServer; "Internal Server Error"
0x18000151b  mov     r9d, 13h
0x180001521  mov     rcx, [rax]
0x180001524  mov     rax, [rcx+18h]
0x180001528  mov     rcx, [rsp+200h+var_198]
0x18000152d  mov     [rsp+200h+var_1D8], rcx
0x180001532  mov     rcx, r10
0x180001535  mov     dword ptr [rsp+200h+var_1E0], r12d
0x18000153a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000153f  mov     rcx, [rsp+200h+var_198]
0x180001544  test    rcx, rcx
  ... truncated ...
```
