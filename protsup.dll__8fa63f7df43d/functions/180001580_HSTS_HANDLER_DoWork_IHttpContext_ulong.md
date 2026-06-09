# HSTS_HANDLER::DoWork(IHttpContext *,ulong)

- ea: `0x180001580`
- end: `0x1800016a7`
- name: `?DoWork@HSTS_HANDLER@@SA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@K@Z`
- size: `295`
- prototype: `__int64 __fastcall(struct IHttpContext *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001290`

## callees

- `0x180001010`
- `0x180001580`
- `0x180001d80`
- `0x180003a5c`
- `0x1800040c8`
- `0x18000413c`
- `0x180004230`
- `0x180005010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001641`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001641`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180002f82`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180002f82`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180002f0a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180002f77`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180002f0a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180002f77`

## string_xrefs

- `0x180002f97`: `Strict-Transport-Security`

## pseudocode

```c
__int64 __fastcall HSTS_HANDLER::DoWork(struct IHttpContext *a1, int a2)
{
  int v4; // esi
  __int64 v5; // rax
  __int64 v6; // rbx
  char *v7; // rdi
  unsigned int v8; // ebx
  __int64 (__fastcall ***v10)(_QWORD); // rax
  unsigned int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ebp
  __int64 v16; // rax
  struct IHttpTraceContext *v17; // rax
  const struct _GUID *v18; // rdx
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, const char *, const char *, _QWORD, int); // rsi
  unsigned __int16 CCH; // ax
  STRA *v22; // rcx
  unsigned __int16 v23; // di
  const char *Str; // rax
  __int64 v25; // rax
  struct IHttpTraceContext *v26; // rax
  const struct _GUID *v27; // rdx
  __int64 v28; // rax
  struct INativeSectionException *v29; // [rsp+40h] [rbp-48h] BYREF
  int v30; // [rsp+90h] [rbp+8h] BYREF
  int v31; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+20h] BYREF

  v30 = 0;
  v31 = 0;
  v4 = 0;
  v32 = 0;
  v29 = 0;
  v5 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a1)(a1);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v7 = (char *)(**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, s_pModuleContext);
  if ( v7 )
    goto LABEL_2;
  v7 = (char *)operator new(0xD0u);
  if ( !v7 )
  {
    v4 = -2147024888;
    goto LABEL_11;
  }
  *((_QWORD *)v7 + 1) = 0;
  *(_QWORD *)v7 = &HSTS_HANDLER::`vftable';
  *((_DWORD *)v7 + 4) = 0;
  STRA::STRA((STRA *)(v7 + 24), v7 + 80, 0x80u);
  v10 = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(struct IHttpContext *))a1)(a1);
  v11 = (**v10)(v10);
  v4 = HSTS_HANDLER::Initialize((HSTS_HANDLER *)v7, v11, &v29);
  if ( v4 < 0 )
  {
LABEL_10:
    (**(void (__fastcall ***)(void *))v7)(v7);
LABEL_11:
    v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) + 536) = 0;
    if ( v29 )
    {
      (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v29)(
        v29,
        &IID_IAppHostConfigException,
        &v32);
      v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v14 + 24LL))(
        v14,
        500,
        "Internal Server Error",
        19,
        v4,
        v32,
        0);
      if ( v32 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        v32 = 0;
      }
      (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    else
    {
      v28 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v28 + 24LL))(
        v28,
        500,
        "Internal Server Error",
        0,
        v4,
        0,
        0);
    }
    return 2;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v6 + 8LL))(v6, v7, s_pModuleContext);
  v4 = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -2147024811 )
    {
      (**(void (__fastcall ***)(void *))v7)(v7);
      v7 = (char *)(**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, s_pModuleContext);
      v4 = 0;
      goto LABEL_2;
    }
    goto LABEL_10;
  }
LABEL_2:
  if ( v4 < 0 )
    goto LABEL_11;
  v8 = 0;
  if ( !*((_DWORD *)v7 + 3) )
    return v8;
  v4 = HSTS_HANDLER::CheckRequestHttps(a1, &v30);
  if ( v4 < 0 )
    goto LABEL_11;
  v15 = a2 - 1;
  if ( v15 )
  {
    if ( v15 == 0x1FFFFFFF && v30 == 1 && STRA::QueryCCH((STRA *)(v7 + 24)) )
    {
      v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v16) )
      {
        v17 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
        IISGeneralEvents::GENERAL_HSTS_HANDLER::RaiseEvent(v17, v18, 1u);
      }
      v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      v20 = *(__int64 (__fastcall **)(__int64, const char *, const char *, _QWORD, int))(*(_QWORD *)v19 + 40LL);
      CCH = STRA::QueryCCH((STRA *)(v7 + 24));
      v22 = (STRA *)(v7 + 24);
      v23 = CCH;
      Str = STRA::QueryStr(v22);
      v4 = v20(v19, "Strict-Transport-Security", Str, v23, 1);
      if ( v4 < 0 )
        goto LABEL_11;
    }
  }
  else
  {
    if ( v30 || *((_DWORD *)v7 + 4) != 1 )
      return v8;
    v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v25) )
    {
      v26 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      IISGeneralEvents::GENERAL_HSTS_HANDLER::RaiseEvent(v26, v27, 0);
    }
    v4 = HSTS_HANDLER::RedirectHttpToHttps(a1, &v31);
    if ( v4 < 0 )
      goto LABEL_11;
    if ( v31 == 1 )
      return 2;
  }
  return v8;
}

```

## disassembly

```asm
0x180001580  mov     rax, rsp
0x180001583  push    rbx
0x180001584  push    rbp
0x180001585  push    rsi
0x180001586  push    rdi
0x180001587  push    r12
0x180001589  push    r15
0x18000158b  sub     rsp, 58h
0x18000158f  xor     r12d, r12d
0x180001592  mov     ebp, edx
0x180001594  mov     [rax+8], r12d
0x180001598  mov     r15, rcx
0x18000159b  mov     [rax+18h], r12d
0x18000159f  mov     esi, r12d
0x1800015a2  mov     [rax+20h], r12
0x1800015a6  mov     [rax-48h], r12
0x1800015aa  mov     rax, [rcx]
0x1800015ad  mov     rax, [rax]
0x1800015b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015b5  mov     rdx, rax
0x1800015b8  mov     rcx, [rax]
0x1800015bb  mov     rax, [rcx+10h]
0x1800015bf  mov     rcx, rdx
0x1800015c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015c7  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x1800015ce  mov     rbx, rax
0x1800015d1  mov     rcx, [rax]
0x1800015d4  mov     rax, [rcx]
0x1800015d7  mov     rcx, rbx
0x1800015da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015df  mov     rdi, rax
0x1800015e2  test    rax, rax
0x1800015e5  jz      short loc_18000160B
0x1800015e7  test    esi, esi
0x1800015e9  js      loc_180002DEB
0x1800015ef  mov     ebx, r12d
0x1800015f2  cmp     [rdi+0Ch], r12d
0x1800015f6  jnz     loc_180002EC6
0x1800015fc  mov     eax, ebx
0x1800015fe  add     rsp, 58h
0x180001602  pop     r15
0x180001604  pop     r12
0x180001606  pop     rdi
0x180001607  pop     rsi
0x180001608  pop     rbp
0x180001609  pop     rbx
0x18000160a  retn
0x18000160b  mov     ecx, 0D0h; Size
0x180001610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001615  mov     rdi, rax
0x180001618  test    rax, rax
0x18000161b  jz      loc_180002EBC
0x180001621  lea     rax, ??_7HSTS_HANDLER@@6B@; const HSTS_HANDLER::`vftable'
0x180001628  mov     [rdi+8], r12
0x18000162c  lea     rdx, [rdi+50h]
0x180001630  mov     [rdi], rax
0x180001633  lea     rcx, [rdi+18h]
0x180001637  mov     [rdi+10h], r12d
0x18000163b  mov     r8d, 80h
0x180001641  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001647  mov     rax, [r15]
0x18000164a  mov     rcx, r15
0x18000164d  mov     rax, [rax]
0x180001650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001655  mov     rdx, rax
0x180001658  mov     rcx, [rax]
0x18000165b  mov     rax, [rcx]
0x18000165e  mov     rcx, rdx
0x180001661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001666  mov     edx, eax; unsigned int
0x180001668  lea     r8, [rsp+88h+var_48]; struct INativeSectionException **
0x18000166d  mov     rcx, rdi; this
0x180001670  call    ?Initialize@HSTS_HANDLER@@AEAAJKPEAPEAVINativeSectionException@@@Z; HSTS_HANDLER::Initialize(ulong,INativeSectionException * *)
0x180001675  mov     esi, eax
0x180001677  test    eax, eax
0x180001679  js      loc_180002DDD
0x18000167f  mov     rax, [rbx]
0x180001682  mov     rdx, rdi
0x180001685  mov     r8, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x18000168c  mov     rcx, rbx
0x18000168f  mov     rax, [rax+8]
0x180001693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001698  mov     esi, eax
0x18000169a  test    eax, eax
0x18000169c  jns     loc_1800015E7
0x1800016a2  jmp     loc_180002DA8
0x180002da8  cmp     eax, 80070055h
0x180002dad  jnz     short loc_180002DDD
0x180002daf  mov     rax, [rdi]
0x180002db2  mov     rcx, rdi
0x180002db5  mov     rax, [rax]
0x180002db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbd  mov     rax, [rbx]
0x180002dc0  mov     rcx, rbx
0x180002dc3  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002dca  mov     rax, [rax]
0x180002dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd2  mov     rdi, rax
0x180002dd5  mov     esi, r12d
0x180002dd8  jmp     loc_1800015E7
0x180002ddd  mov     rax, [rdi]
0x180002de0  mov     rcx, rdi
0x180002de3  mov     rax, [rax]
0x180002de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002deb  mov     rax, [r15]
0x180002dee  mov     rcx, r15
0x180002df1  mov     rax, [rax+20h]
0x180002df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfa  mov     rdx, rax
0x180002dfd  mov     rcx, [rax]
0x180002e00  mov     rax, [rcx+8]
0x180002e04  mov     rcx, rdx
0x180002e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0c  mov     [rax+218h], r12w
0x180002e14  mov     rcx, [rsp+88h+var_48]
0x180002e19  test    rcx, rcx
0x180002e1c  jz      loc_18000303E
0x180002e22  mov     rax, [rcx]
0x180002e25  lea     r8, [rsp+88h+arg_18]
0x180002e2d  lea     rdx, IID_IAppHostConfigException
0x180002e34  mov     rax, [rax]
0x180002e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3c  mov     rax, [r15]
0x180002e3f  mov     rcx, r15
0x180002e42  mov     rax, [rax+20h]
0x180002e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4b  mov     r10, rax
0x180002e4e  mov     [rsp+88h+var_58], r12d
0x180002e53  mov     edx, 1F4h
0x180002e58  lea     r8, aInternalServer; "Internal Server Error"
0x180002e5f  mov     r9d, 13h
0x180002e65  mov     rcx, [rax]
0x180002e68  mov     rax, [rcx+18h]
0x180002e6c  mov     rcx, [rsp+88h+arg_18]
0x180002e74  mov     [rsp+88h+var_60], rcx
0x180002e79  mov     rcx, r10
0x180002e7c  mov     [rsp+88h+var_68], esi
0x180002e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e85  mov     rcx, [rsp+88h+arg_18]
0x180002e8d  test    rcx, rcx
0x180002e90  jz      short loc_180002EA6
0x180002e92  mov     rax, [rcx]
0x180002e95  mov     rax, [rax+10h]
0x180002e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9e  mov     [rsp+88h+arg_18], r12
0x180002ea6  mov     rcx, [rsp+88h+var_48]
0x180002eab  mov     rax, [rcx]
0x180002eae  mov     rax, [rax+10h]
0x180002eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eb7  jmp     loc_18000307C
0x180002ebc  mov     esi, 80070008h
0x180002ec1  jmp     loc_180002DEB
0x180002ec6  lea     rdx, [rsp+88h+arg_0]; int *
0x180002ece  mov     rcx, r15; struct IHttpContext *
0x180002ed1  call    ?CheckRequestHttps@HSTS_HANDLER@@CAJPEAVIHttpContext@@PEAH@Z; HSTS_HANDLER::CheckRequestHttps(IHttpContext *,int *)
0x180002ed6  mov     esi, eax
0x180002ed8  test    eax, eax
0x180002eda  js      loc_180002DEB
0x180002ee0  sub     ebp, 1
0x180002ee3  jz      loc_180002FBD
0x180002ee9  cmp     ebp, 1FFFFFFFh
0x180002eef  jnz     loc_1800015FC
0x180002ef5  cmp     [rsp+88h+arg_0], 1
0x180002efd  jnz     loc_1800015FC
0x180002f03  lea     rbp, [rdi+18h]
0x180002f07  mov     rcx, rbp
0x180002f0a  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180002f10  test    eax, eax
0x180002f12  jz      loc_1800015FC
0x180002f18  mov     rax, [r15]
0x180002f1b  mov     rcx, r15
0x180002f1e  mov     [rsp+88h+var_38], r14
0x180002f23  mov     rax, [rax+110h]
0x180002f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f2f  mov     rcx, rax
0x180002f32  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180002f37  test    eax, eax
0x180002f39  jz      short loc_180002F5B
0x180002f3b  mov     rax, [r15]
0x180002f3e  mov     rcx, r15
0x180002f41  mov     rax, [rax+110h]
0x180002f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4d  mov     rcx, rax; struct IHttpTraceContext *
0x180002f50  mov     r8d, 1; unsigned int
0x180002f56  call    ?RaiseEvent@GENERAL_HSTS_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISGeneralEvents::GENERAL_HSTS_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x180002f5b  mov     rax, [r15]
0x180002f5e  mov     rcx, r15
0x180002f61  mov     rax, [rax+20h]
0x180002f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6a  mov     rcx, rbp
0x180002f6d  mov     r14, rax
0x180002f70  mov     rdx, [rax]
0x180002f73  mov     rsi, [rdx+28h]
0x180002f77  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180002f7d  mov     rcx, rbp
0x180002f80  mov     edi, eax
0x180002f82  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180002f88  movzx   r9d, di
0x180002f8c  mov     [rsp+88h+var_68], 1
0x180002f94  mov     r8, rax
0x180002f97  lea     rdx, aStrictTranspor; "Strict-Transport-Security"
0x180002f9e  mov     rax, rsi
0x180002fa1  mov     rcx, r14
0x180002fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa9  mov     r14, [rsp+88h+var_38]
0x180002fae  mov     esi, eax
0x180002fb0  test    eax, eax
0x180002fb2  jns     loc_1800015FC
0x180002fb8  jmp     loc_180002DEB
0x180002fbd  cmp     [rsp+88h+arg_0], ebx
0x180002fc4  jnz     loc_1800015FC
0x180002fca  cmp     dword ptr [rdi+10h], 1
0x180002fce  jnz     loc_1800015FC
0x180002fd4  mov     rax, [r15]
0x180002fd7  mov     rcx, r15
0x180002fda  mov     rax, [rax+110h]
0x180002fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe6  mov     rcx, rax
0x180002fe9  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180002fee  test    eax, eax
0x180002ff0  jz      short loc_18000300F
0x180002ff2  mov     rax, [r15]
0x180002ff5  mov     rcx, r15
0x180002ff8  mov     rax, [rax+110h]
0x180002fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003004  mov     rcx, rax; struct IHttpTraceContext *
0x180003007  xor     r8d, r8d; unsigned int
0x18000300a  call    ?RaiseEvent@GENERAL_HSTS_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISGeneralEvents::GENERAL_HSTS_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x18000300f  lea     rdx, [rsp+88h+arg_10]; int *
0x180003017  mov     rcx, r15; struct IHttpContext *
0x18000301a  call    ?RedirectHttpToHttps@HSTS_HANDLER@@CAJPEAVIHttpContext@@PEAH@Z; HSTS_HANDLER::RedirectHttpToHttps(IHttpContext *,int *)
0x18000301f  mov     esi, eax
0x180003021  test    eax, eax
0x180003023  js      loc_180002DEB
0x180003029  cmp     [rsp+88h+arg_10], 1
0x180003031  mov     eax, 2
0x180003036  cmovz   ebx, eax
0x180003039  jmp     loc_1800015FC
0x18000303e  mov     rax, [r15]
0x180003041  mov     rcx, r15
0x180003044  mov     rax, [rax+20h]
0x180003048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304d  mov     r10, rax
0x180003050  mov     [rsp+88h+var_58], r12d
0x180003055  xor     r9d, r9d
0x180003058  mov     [rsp+88h+var_60], r12
0x18000305d  mov     edx, 1F4h
0x180003062  mov     [rsp+88h+var_68], esi
0x180003066  mov     rcx, [rax]
0x180003069  lea     r8, aInternalServer; "Internal Server Error"
0x180003070  mov     rax, [rcx+18h]
0x180003074  mov     rcx, r10
0x180003077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000307c  mov     ebx, 2
0x180003081  jmp     loc_1800015FC
```
