# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002378`
- end: `0x1800027b8`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(int, int, struct IHttpContext *, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001b00`
- `0x180001ce0`

## callees

- `0x180001008`
- `0x180002378`
- `0x180002844`
- `0x180002e38`
- `0x180003060`
- `0x180004010`

## import_xrefs

- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x18000244b`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x18000244b`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, int a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  int v6; // r15d
  __int64 v7; // rax
  __int64 v8; // rdi
  _QWORD *v9; // rbx
  int v10; // r14d
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r14
  URL_LOGGING *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r15d
  __int64 v20; // rax
  __int64 v21; // rax
  struct INativeSectionException *v23; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+48h] BYREF

  v24 = a2;
  v23 = 0;
  v25 = 0;
  if ( a1 != 1024 || a5 || ((*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 112LL))(a3) & 0x21) != 0 )
    return 0;
  v6 = -2147467259;
  v7 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a3)(a3);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v9 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v8)(v8, g_pLoggingModuleContext);
  if ( v9 )
  {
LABEL_14:
    if ( !v9[2] )
      return 0;
    v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    v16 = (URL_LOGGING *)(**(__int64 (__fastcall ***)(__int64, void *))v15)(v15, g_pLoggingModuleContext);
    if ( !v16 )
    {
      v16 = (URL_LOGGING *)operator new(0x10u);
      if ( !v16 )
        return 0;
      *((_DWORD *)v16 + 2) = 0;
      *(_QWORD *)v16 = &URL_LOGGING::`vftable';
      if ( (int)URL_LOGGING::Initialize(v16, a3, &v23) < 0 )
      {
        v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 80LL))(v17);
        if ( v23 )
          (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v23)(
            v23,
            &IID_IAppHostConfigException,
            &v25);
        v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v18 + 24LL))(
          v18,
          500,
          "Internal Server Error",
          19,
          v6,
          v25,
          0);
        if ( v25 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          v25 = 0;
        }
        if ( v23 )
        {
          (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v23 + 16LL))(v23);
          v23 = 0;
        }
        (**(void (__fastcall ***)(URL_LOGGING *))v16)(v16);
        goto LABEL_34;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, URL_LOGGING *, void *))(*(_QWORD *)v15 + 8LL))(
              v15,
              v16,
              g_pLoggingModuleContext);
      if ( v19 < 0 )
      {
        (**(void (__fastcall ***)(URL_LOGGING *))v16)(v16);
        if ( v19 != -2147024811 )
          return 0;
        v16 = (URL_LOGGING *)(**(__int64 (__fastcall ***)(__int64, void *))v15)(v15, g_pLoggingModuleContext);
      }
    }
    if ( *((_DWORD *)v16 + 3) )
      return 0;
    v20 = *(_QWORD *)a3;
    LOWORD(v24) = 0;
    v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v20 + 32))(a3);
    (*(void (__fastcall **)(__int64, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v21 + 184LL))(
      v21,
      &v24,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0);
    if ( *((_DWORD *)v16 + 2) == 1 )
    {
      if ( (unsigned __int16)v24 > 0x18Fu )
        return 0;
    }
    else if ( *((_DWORD *)v16 + 2) == 2 && (unsigned __int16)v24 < 0x190u )
    {
      return 0;
    }
LABEL_34:
    LOGGING::DoWork((LOGGING *)v9, a3);
    return 0;
  }
  v9 = operator new(0x50u);
  if ( !v9 )
    return 0;
  *((_DWORD *)v9 + 2) = 1195855692;
  *v9 = &LOGGING::`vftable';
  v9[2] = 0;
  MULTISZA::MULTISZA((MULTISZA *)(v9 + 3));
  if ( g_fDoCentralBinaryLogging || (v10 = LOGGING::ActivateLogging((LOGGING *)v9, a3), v10 >= 0) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, void *))(*(_QWORD *)v8 + 8LL))(v8, v9, g_pLoggingModuleContext);
    if ( v6 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *))*v9)(v9);
      if ( v6 != -2147024811 )
        return 0;
      v9 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v8)(v8, g_pLoggingModuleContext);
      v6 = 0;
    }
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  if ( *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) + 8) < 0x190u )
  {
    v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 80LL))(v12);
    v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v13 + 24LL))(
      v13,
      500,
      "Internal Server Error",
      0,
      v10,
      0,
      0);
  }
  (*(void (__fastcall **)(_QWORD *))*v9)(v9);
  return 0;
}

```

## disassembly

```asm
0x180002378  mov     rax, rsp
0x18000237b  mov     [rax+8], rbx
0x18000237f  mov     [rax+18h], rsi
0x180002383  mov     [rax+20h], r9
0x180002387  mov     [rax+10h], edx
0x18000238a  push    rbp
0x18000238b  push    rdi
0x18000238c  push    r12
0x18000238e  push    r14
0x180002390  push    r15
0x180002392  mov     rbp, rsp
0x180002395  sub     rsp, 70h
0x180002399  xor     r12d, r12d
0x18000239c  mov     rsi, r8
0x18000239f  mov     [rbp+var_10], r12
0x1800023a3  mov     [rbp+arg_18], r12
0x1800023a7  cmp     ecx, 400h
0x1800023ad  jnz     loc_18000279D
0x1800023b3  cmp     [rbp+arg_20], r12
0x1800023b7  jnz     loc_18000279D
0x1800023bd  mov     rax, [r8]
0x1800023c0  mov     rcx, r8
0x1800023c3  mov     rax, [rax+70h]
0x1800023c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023cc  test    al, 21h
0x1800023ce  jnz     loc_18000279D
0x1800023d4  mov     rax, [rsi]
0x1800023d7  mov     rcx, rsi
0x1800023da  mov     r15d, 80004005h
0x1800023e0  mov     rax, [rax]
0x1800023e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e8  mov     rdx, rax
0x1800023eb  mov     rcx, [rax]
0x1800023ee  mov     rax, [rcx+10h]
0x1800023f2  mov     rcx, rdx
0x1800023f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023fa  mov     rdx, cs:?g_pLoggingModuleContext@@3PEAXEA; void * g_pLoggingModuleContext
0x180002401  mov     rdi, rax
0x180002404  mov     rcx, [rax]
0x180002407  mov     rax, [rcx]
0x18000240a  mov     rcx, rdi
0x18000240d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002412  mov     rbx, rax
0x180002415  test    rax, rax
0x180002418  jnz     loc_180002569
0x18000241e  lea     ecx, [rax+50h]; Size
0x180002421  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002426  mov     rbx, rax
0x180002429  test    rax, rax
0x18000242c  jz      loc_18000279D
0x180002432  lea     rax, ??_7LOGGING@@6B@; const LOGGING::`vftable'
0x180002439  mov     dword ptr [rbx+8], 47474F4Ch
0x180002440  lea     rcx, [rbx+18h]
0x180002444  mov     [rbx], rax
0x180002447  mov     [rbx+10h], r12
0x18000244b  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180002451  cmp     cs:?g_fDoCentralBinaryLogging@@3HA, r12d; int g_fDoCentralBinaryLogging
0x180002458  jnz     loc_180002513
0x18000245e  mov     rdx, rsi; struct IHttpContext *
0x180002461  mov     rcx, rbx; this
0x180002464  call    ?ActivateLogging@LOGGING@@QEAAJPEAVIHttpContext@@@Z; LOGGING::ActivateLogging(IHttpContext *)
0x180002469  mov     r14d, eax
0x18000246c  test    eax, eax
0x18000246e  jns     loc_180002513
0x180002474  mov     rcx, [rsi]
0x180002477  mov     rax, [rcx+20h]
0x18000247b  mov     rcx, rsi
0x18000247e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002483  mov     rdx, rax
0x180002486  mov     rcx, [rax]
0x180002489  mov     rax, [rcx+8]
0x18000248d  mov     rcx, rdx
0x180002490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002495  mov     ecx, 190h
0x18000249a  cmp     [rax+8], cx
0x18000249e  jnb     short loc_180002500
0x1800024a0  mov     rax, [rsi]
0x1800024a3  mov     rcx, rsi
0x1800024a6  mov     rax, [rax+20h]
0x1800024aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024af  mov     rdx, rax
0x1800024b2  mov     rcx, [rax]
0x1800024b5  mov     rax, [rcx+50h]
0x1800024b9  mov     rcx, rdx
0x1800024bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c1  mov     rax, [rsi]
0x1800024c4  mov     rcx, rsi
0x1800024c7  mov     rax, [rax+20h]
0x1800024cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d0  mov     r10, rax
0x1800024d3  mov     dword ptr [rsp+70h+var_40], r12d
0x1800024d8  xor     r9d, r9d
0x1800024db  mov     [rsp+70h+var_48], r12
0x1800024e0  mov     edx, 1F4h
0x1800024e5  mov     dword ptr [rsp+70h+var_50], r14d
0x1800024ea  mov     rcx, [rax]
0x1800024ed  lea     r8, aInternalServer; "Internal Server Error"
0x1800024f4  mov     rax, [rcx+18h]
0x1800024f8  mov     rcx, r10
0x1800024fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002500  mov     rax, [rbx]
0x180002503  mov     rcx, rbx
0x180002506  mov     rax, [rax]
0x180002509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000250e  jmp     loc_18000279D
0x180002513  mov     rax, [rdi]
0x180002516  mov     rdx, rbx
0x180002519  mov     r8, cs:?g_pLoggingModuleContext@@3PEAXEA; void * g_pLoggingModuleContext
0x180002520  mov     rcx, rdi
0x180002523  mov     rax, [rax+8]
0x180002527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252c  mov     r15d, eax
0x18000252f  test    eax, eax
0x180002531  jns     short loc_180002569
0x180002533  mov     rcx, [rbx]
0x180002536  mov     rax, [rcx]
0x180002539  mov     rcx, rbx
0x18000253c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002541  cmp     r15d, 80070055h
0x180002548  jnz     loc_18000279D
0x18000254e  mov     rax, [rdi]
0x180002551  mov     rcx, rdi
0x180002554  mov     rdx, cs:?g_pLoggingModuleContext@@3PEAXEA; void * g_pLoggingModuleContext
0x18000255b  mov     rax, [rax]
0x18000255e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002563  mov     rbx, rax
0x180002566  mov     r15d, r12d
0x180002569  cmp     [rbx+10h], r12
0x18000256d  jz      loc_18000279D
0x180002573  mov     rax, [rsi]
0x180002576  mov     rcx, rsi
0x180002579  mov     rax, [rax+0A0h]
0x180002580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002585  mov     rdx, rax
0x180002588  mov     rcx, [rax]
0x18000258b  mov     rax, [rcx+18h]
0x18000258f  mov     rcx, rdx
0x180002592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002597  mov     rdx, cs:?g_pLoggingModuleContext@@3PEAXEA; void * g_pLoggingModuleContext
0x18000259e  mov     r14, rax
0x1800025a1  mov     rcx, [rax]
0x1800025a4  mov     rax, [rcx]
0x1800025a7  mov     rcx, r14
0x1800025aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025af  mov     rdi, rax
0x1800025b2  test    rax, rax
0x1800025b5  jnz     loc_180002712
0x1800025bb  lea     ecx, [rax+10h]; Size
0x1800025be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025c3  mov     rdi, rax
0x1800025c6  test    rax, rax
0x1800025c9  jz      loc_18000279D
0x1800025cf  lea     rax, ??_7URL_LOGGING@@6B@; const URL_LOGGING::`vftable'
0x1800025d6  mov     [rdi+8], r12d
0x1800025da  lea     r8, [rbp+var_10]; struct INativeSectionException **
0x1800025de  mov     [rdi], rax
0x1800025e1  mov     rdx, rsi; struct IHttpContext *
0x1800025e4  mov     rcx, rdi; this
0x1800025e7  call    ?Initialize@URL_LOGGING@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; URL_LOGGING::Initialize(IHttpContext *,INativeSectionException * *)
0x1800025ec  test    eax, eax
0x1800025ee  jns     loc_1800026BF
0x1800025f4  mov     rax, [rsi]
0x1800025f7  mov     rcx, rsi
0x1800025fa  mov     rax, [rax+20h]
0x1800025fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002603  mov     rdx, rax
0x180002606  mov     rcx, [rax]
0x180002609  mov     rax, [rcx+50h]
0x18000260d  mov     rcx, rdx
0x180002610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002615  mov     rcx, [rbp+var_10]
0x180002619  test    rcx, rcx
0x18000261c  jz      short loc_180002634
0x18000261e  mov     rax, [rcx]
0x180002621  lea     r8, [rbp+arg_18]
0x180002625  lea     rdx, IID_IAppHostConfigException
0x18000262c  mov     rax, [rax]
0x18000262f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002634  mov     rax, [rsi]
0x180002637  mov     rcx, rsi
0x18000263a  mov     rax, [rax+20h]
0x18000263e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002643  mov     r10, rax
0x180002646  mov     dword ptr [rsp+70h+var_40], r12d
0x18000264b  mov     edx, 1F4h
0x180002650  lea     r8, aInternalServer; "Internal Server Error"
0x180002657  mov     r9d, 13h
0x18000265d  mov     rcx, [rax]
0x180002660  mov     rax, [rcx+18h]
0x180002664  mov     rcx, [rbp+arg_18]
0x180002668  mov     [rsp+70h+var_48], rcx
0x18000266d  mov     rcx, r10
0x180002670  mov     dword ptr [rsp+70h+var_50], r15d
0x180002675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000267a  mov     rcx, [rbp+arg_18]
0x18000267e  test    rcx, rcx
0x180002681  jz      short loc_180002693
0x180002683  mov     rax, [rcx]
0x180002686  mov     rax, [rax+10h]
0x18000268a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268f  mov     [rbp+arg_18], r12
0x180002693  mov     rcx, [rbp+var_10]
0x180002697  test    rcx, rcx
0x18000269a  jz      short loc_1800026AC
0x18000269c  mov     rax, [rcx]
0x18000269f  mov     rax, [rax+10h]
0x1800026a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a8  mov     [rbp+var_10], r12
0x1800026ac  mov     rax, [rdi]
0x1800026af  mov     rcx, rdi
0x1800026b2  mov     rax, [rax]
0x1800026b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ba  jmp     loc_180002792
0x1800026bf  mov     rax, [r14]
0x1800026c2  mov     rdx, rdi
0x1800026c5  mov     r8, cs:?g_pLoggingModuleContext@@3PEAXEA; void * g_pLoggingModuleContext
0x1800026cc  mov     rcx, r14
0x1800026cf  mov     rax, [rax+8]
0x1800026d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d8  mov     r15d, eax
0x1800026db  test    eax, eax
0x1800026dd  jns     short loc_180002712
0x1800026df  mov     rcx, [rdi]
0x1800026e2  mov     rax, [rcx]
0x1800026e5  mov     rcx, rdi
0x1800026e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ed  cmp     r15d, 80070055h
0x1800026f4  jnz     loc_18000279D
0x1800026fa  mov     rax, [r14]
0x1800026fd  mov     rcx, r14
0x180002700  mov     rdx, cs:?g_pLoggingModuleContext@@3PEAXEA; void * g_pLoggingModuleContext
0x180002707  mov     rax, [rax]
0x18000270a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270f  mov     rdi, rax
0x180002712  cmp     [rdi+0Ch], r12d
0x180002716  jnz     loc_18000279D
0x18000271c  mov     rax, [rsi]
0x18000271f  mov     rcx, rsi
0x180002722  mov     word ptr [rbp+arg_8], r12w
0x180002727  mov     rax, [rax+20h]
0x18000272b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002730  mov     [rsp+70h+var_28], r12
0x180002735  lea     rdx, [rbp+arg_8]
0x180002739  mov     [rsp+70h+var_30], r12
0x18000273e  mov     r10, rax
0x180002741  mov     [rsp+70h+var_38], r12
0x180002746  xor     r9d, r9d
0x180002749  mov     rcx, [rax]
0x18000274c  xor     r8d, r8d
0x18000274f  mov     [rsp+70h+var_40], r12
0x180002754  mov     [rsp+70h+var_48], r12
0x180002759  mov     [rsp+70h+var_50], r12
0x18000275e  mov     rax, [rcx+0B8h]
0x180002765  mov     rcx, r10
0x180002768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276d  mov     ecx, [rdi+8]
0x180002770  sub     ecx, 1
0x180002773  jz      short loc_180002787
0x180002775  cmp     ecx, 1
0x180002778  jnz     short loc_180002792
0x18000277a  mov     ecx, 190h
0x18000277f  cmp     word ptr [rbp+arg_8], cx
0x180002783  jb      short loc_18000279D
0x180002785  jmp     short loc_180002792
0x180002787  mov     eax, 18Fh
0x18000278c  cmp     word ptr [rbp+arg_8], ax
0x180002790  ja      short loc_18000279D
0x180002792  mov     rdx, rsi; struct IHttpContext *
0x180002795  mov     rcx, rbx; this
0x180002798  call    ?DoWork@LOGGING@@QEAAXPEAVIHttpContext@@@Z; LOGGING::DoWork(IHttpContext *)
0x18000279d  lea     r11, [rsp+70h+var_s0]
0x1800027a2  xor     eax, eax
0x1800027a4  mov     rbx, [r11+30h]
0x1800027a8  mov     rsi, [r11+40h]
0x1800027ac  mov     rsp, r11
0x1800027af  pop     r15
0x1800027b1  pop     r14
0x1800027b3  pop     r12
0x1800027b5  pop     rdi
0x1800027b6  pop     rbp
0x1800027b7  retn
```
