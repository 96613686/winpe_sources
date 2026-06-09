# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001290`
- end: `0x180001572`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `738`
- prototype: `__int64 __fastcall(int, int, struct IHttpContext *, __int64 *, struct INativeSectionException *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001250`
- `0x180001270`
- `0x180003340`
- `0x1800034e0`

## callees

- `0x180001290`
- `0x180001580`
- `0x1800016b0`
- `0x180001d80`
- `0x180003aa4`
- `0x180003f24`
- `0x180005010`

## import_xrefs

- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x1800013e2`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x1800013f2`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180002b49`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180002b5c`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x1800013e2`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x1800013f2`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180002b49`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180002b5c`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014c8`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014d2`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014dc`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014e9`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014c8`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014d2`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014dc`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800014e9`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002d06`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002d06`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001386`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001393`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001481`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001491`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001386`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001393`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001481`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180001491`

## pseudocode

```c
__int64 __fastcall RequestDoWork(
        int a1,
        int a2,
        struct IHttpContext *a3,
        __int64 *a4,
        struct INativeSectionException *a5)
{
  __int64 v8; // r15
  int v9; // ebx
  int v11; // ebx
  __int64 v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, void *); // rax
  __int64 (__fastcall ***v14)(_QWORD, void *); // rbx
  _DWORD *v15; // rsi
  const char *v16; // rbp
  const char *v17; // rbx
  __int64 v18; // r9
  int v19; // r12d
  void (__fastcall *v20)(__int64, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  const char *v21; // rbx
  const char *v22; // r14
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // ecx
  _QWORD *v31; // rax
  void (__fastcall ***v32)(_QWORD); // rbx
  __int64 v33; // rax
  int v34; // esi
  int v35; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v36; // [rsp+B0h] [rbp+18h] BYREF

  v35 = a2;
  a5 = 0;
  v36 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  v9 = a1 - 1;
  if ( !v9 )
    return HSTS_HANDLER::DoWork(a3, 1);
  v11 = v9 - 127;
  if ( !v11 )
  {
    v29 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 24LL))(a3);
    v30 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29) + 36);
    if ( v30 == 3 )
      return OPTIONS_VERB_HANDLER::DoWork(a3);
    if ( v30 == 9 )
    {
      v31 = operator new(0x40u);
      v32 = (void (__fastcall ***)(_QWORD))v31;
      if ( v31 )
      {
        v31[1] = 0;
        v31[2] = 0;
        v31[3] = 0;
        v31[4] = 0;
        v31[5] = 0;
        v31[6] = 0;
        v31[7] = 0;
        *v31 = &TRACE_VERB_HANDLER::`vftable';
        STRA::STRA((STRA *)(v31 + 1));
        v33 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
        v34 = (*(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), void *))(*(_QWORD *)v33 + 8LL))(
                v33,
                v32,
                s_pModuleContext);
        if ( v34 >= 0 )
        {
          return TRACE_VERB_HANDLER::DoWork(v32, a3);
        }
        else
        {
          (**v32)(v32);
          (*(void (__fastcall **)(__int64 *, _QWORD))*a4)(a4, (unsigned int)v34);
          return 2;
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64 *, __int64))*a4)(a4, 2147942408LL);
        return 2;
      }
    }
    return 0;
  }
  if ( v11 != 536870784 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(__int64 *))(*a4 + 8))(a4) )
    return HSTS_HANDLER::DoWork(a3, 0x20000000);
  v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
  v13 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
  v14 = v13;
  if ( v13 )
  {
    v15 = (_DWORD *)(**v13)(v13, s_pModuleContext);
    if ( v15 )
    {
LABEL_8:
      if ( !v15[58] )
      {
        v23 = *a4;
        v24 = (*(__int64 (__fastcall **)(__int64 *))(*a4 + 16))(a4);
        (*(void (__fastcall **)(__int64 *, _QWORD))(v23 + 24))(a4, v24 | 1u);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 96LL))(v8);
      }
      v16 = MULTISZA::First((MULTISZA *)(v15 + 2));
      v17 = MULTISZA::First((MULTISZA *)(v15 + 16));
      if ( v16 )
      {
        while ( v17 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          v19 = (*(__int64 (__fastcall **)(__int64, const char *, const char *))(*(_QWORD *)v8 + 40LL))(v8, v16, v17);
          if ( v19 < 0 )
            goto LABEL_34;
          v16 = MULTISZA::Next((MULTISZA *)(v15 + 2), v16);
          v17 = MULTISZA::Next((MULTISZA *)(v15 + 16), v17);
          if ( !v16 )
            break;
        }
      }
      v20 = *(void (__fastcall **)(__int64, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v8 + 184LL);
      LOWORD(v35) = 0;
      v20(v8, &v35, 0, 0, 0, 0, 0, 0, 0, 0);
      if ( (unsigned int)(unsigned __int16)v35 - 300 < 0x64 )
      {
        v21 = MULTISZA::First((MULTISZA *)(v15 + 30));
        v22 = MULTISZA::First((MULTISZA *)(v15 + 44));
        if ( v21 )
        {
          while ( v22 )
          {
            v25 = -1;
            do
              ++v25;
            while ( v22[v25] );
            v19 = (*(__int64 (__fastcall **)(__int64, const char *, const char *))(*(_QWORD *)v8 + 40LL))(v8, v21, v22);
            if ( v19 < 0 )
              goto LABEL_34;
            v21 = MULTISZA::Next((MULTISZA *)(v15 + 30), v21);
            v22 = MULTISZA::Next((MULTISZA *)(v15 + 44), v22);
            if ( !v21 )
              return HSTS_HANDLER::DoWork(a3, 0x20000000);
          }
        }
      }
      return HSTS_HANDLER::DoWork(a3, 0x20000000);
    }
  }
  v15 = operator new(0xF0u);
  if ( v15 )
  {
    *(_QWORD *)v15 = &PROTOCOL_SUPPORT_META_CONTEXT::`vftable';
    MULTISZA::MULTISZA((MULTISZA *)(v15 + 2));
    MULTISZA::MULTISZA((MULTISZA *)(v15 + 16));
    MULTISZA::MULTISZA((MULTISZA *)(v15 + 30));
    MULTISZA::MULTISZA((MULTISZA *)(v15 + 44));
    v19 = PROTOCOL_SUPPORT_META_CONTEXT::Initialize((PROTOCOL_SUPPORT_META_CONTEXT *)v15, a3, &a5);
    if ( v19 < 0 )
    {
      (**(void (__fastcall ***)(_DWORD *))v15)(v15);
    }
    else
    {
      if ( !v14 )
        goto LABEL_8;
      v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, void *), _DWORD *, void *))(*v14)[1])(
              v14,
              v15,
              s_pModuleContext);
      if ( v19 >= 0 )
        goto LABEL_8;
      (**(void (__fastcall ***)(_DWORD *))v15)(v15);
      if ( v19 == -2147024811 )
      {
        v15 = (_DWORD *)(**v14)(v14, s_pModuleContext);
        goto LABEL_8;
      }
    }
  }
  else
  {
    v19 = -2147024888;
  }
LABEL_34:
  v26 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26) + 536) = 0;
  if ( a5 )
  {
    (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))a5)(
      a5,
      &IID_IAppHostConfigException,
      &v36);
    v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v27 + 24LL))(
      v27,
      500,
      "Internal Server Error",
      19,
      v19,
      v36,
      0);
    if ( v36 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      v36 = 0;
    }
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)a5 + 16LL))(a5);
  }
  else
  {
    v28 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v28 + 24LL))(
      v28,
      500,
      "Internal Server Error",
      0,
      v19,
      0,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180001290  mov     rax, rsp
0x180001293  mov     [rax+10h], edx
0x180001296  push    rbx
0x180001297  push    rdi
0x180001298  push    r13
0x18000129a  push    r14
0x18000129c  push    r15
0x18000129e  sub     rsp, 70h
0x1800012a2  xor     r13d, r13d
0x1800012a5  mov     ebx, ecx
0x1800012a7  mov     [rax+28h], r13
0x1800012ab  mov     rcx, r8
0x1800012ae  mov     [rax+18h], r13
0x1800012b2  mov     r14, r9
0x1800012b5  mov     rax, [r8]
0x1800012b8  mov     rdi, r8
0x1800012bb  mov     rax, [rax+20h]
0x1800012bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012c4  mov     r15, rax
0x1800012c7  sub     ebx, 1
0x1800012ca  jnz     short loc_1800012E6
0x1800012cc  mov     edx, 1
0x1800012d1  mov     rcx, rdi
0x1800012d4  call    ?DoWork@HSTS_HANDLER@@SA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@K@Z; HSTS_HANDLER::DoWork(IHttpContext *,ulong)
0x1800012d9  add     rsp, 70h
0x1800012dd  pop     r15
0x1800012df  pop     r14
0x1800012e1  pop     r13
0x1800012e3  pop     rdi
0x1800012e4  pop     rbx
0x1800012e5  retn
0x1800012e6  mov     [rsp+98h+var_30], rsi
0x1800012eb  mov     [rsp+98h+var_38], r12
0x1800012f0  sub     ebx, 7Fh
0x1800012f3  jz      loc_180002C90
0x1800012f9  cmp     ebx, 1FFFFF80h
0x1800012ff  jnz     loc_180002D65
0x180001305  mov     rcx, [r14]
0x180001308  mov     [rsp+98h+arg_0], rbp
0x180001310  mov     rax, [rcx+8]
0x180001314  mov     rcx, r14
0x180001317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000131c  test    eax, eax
0x18000131e  jz      loc_180001459
0x180001324  mov     rax, [rdi]
0x180001327  mov     rcx, rdi
0x18000132a  mov     rax, [rax+0A0h]
0x180001331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001336  mov     rdx, rax
0x180001339  mov     rcx, [rax]
0x18000133c  mov     rax, [rcx+18h]
0x180001340  mov     rcx, rdx
0x180001343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001348  mov     rbx, rax
0x18000134b  test    rax, rax
0x18000134e  jz      loc_1800014A4
0x180001354  mov     rcx, [rax]
0x180001357  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x18000135e  mov     rax, [rcx]
0x180001361  mov     rcx, rbx
0x180001364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001369  mov     rsi, rax
0x18000136c  test    rax, rax
0x18000136f  jz      loc_1800014A4
0x180001375  cmp     [rsi+0E8h], r13d
0x18000137c  jz      loc_180002AD3
0x180001382  lea     rcx, [rsi+8]
0x180001386  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x18000138c  lea     rcx, [rsi+40h]
0x180001390  mov     rbp, rax
0x180001393  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180001399  mov     rbx, rax
0x18000139c  test    rbp, rbp
0x18000139f  jz      short loc_180001400
0x1800013a1  test    rbx, rbx
0x1800013a4  jz      short loc_180001400
0x1800013a6  mov     rcx, [r15]
0x1800013a9  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800013b0  mov     rax, [rcx+28h]
0x1800013b4  inc     r9
0x1800013b7  cmp     [rbx+r9], r13b
0x1800013bb  jnz     short loc_1800013B4
0x1800013bd  mov     r8, rbx
0x1800013c0  mov     dword ptr [rsp+98h+var_78], r13d
0x1800013c5  mov     rdx, rbp
0x1800013c8  mov     rcx, r15
0x1800013cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d0  mov     r12d, eax
0x1800013d3  test    eax, eax
0x1800013d5  js      loc_180002B75
0x1800013db  mov     rdx, rbp
0x1800013de  lea     rcx, [rsi+8]
0x1800013e2  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x1800013e8  mov     rdx, rbx
0x1800013eb  lea     rcx, [rsi+40h]
0x1800013ef  mov     rbp, rax
0x1800013f2  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x1800013f8  mov     rbx, rax
0x1800013fb  test    rbp, rbp
0x1800013fe  jnz     short loc_1800013A1
0x180001400  mov     rax, [r15]
0x180001403  lea     rdx, [rsp+98h+arg_8]
0x18000140b  mov     [rsp+98h+var_50], r13
0x180001410  xor     r9d, r9d
0x180001413  mov     [rsp+98h+var_58], r13
0x180001418  xor     r8d, r8d
0x18000141b  mov     [rsp+98h+var_60], r13
0x180001420  mov     rcx, r15
0x180001423  mov     rax, [rax+0B8h]
0x18000142a  mov     [rsp+98h+var_68], r13
0x18000142f  mov     [rsp+98h+var_70], r13
0x180001434  mov     word ptr [rsp+98h+arg_8], r13w
0x18000143d  mov     [rsp+98h+var_78], r13
0x180001442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001447  movzx   eax, word ptr [rsp+98h+arg_8]
0x18000144f  sub     eax, 12Ch
0x180001454  cmp     eax, 64h ; 'd'
0x180001457  jb      short loc_18000147D
0x180001459  mov     edx, 20000000h
0x18000145e  mov     rcx, rdi
0x180001461  call    ?DoWork@HSTS_HANDLER@@SA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@K@Z; HSTS_HANDLER::DoWork(IHttpContext *,ulong)
0x180001466  mov     rbp, [rsp+98h+arg_0]
0x18000146e  mov     rsi, [rsp+98h+var_30]
0x180001473  mov     r12, [rsp+98h+var_38]
0x180001478  jmp     loc_1800012D9
0x18000147d  lea     rcx, [rsi+78h]
0x180001481  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180001487  lea     rcx, [rsi+0B0h]
0x18000148e  mov     rbx, rax
0x180001491  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180001497  mov     r14, rax
0x18000149a  test    rbx, rbx
0x18000149d  jz      short loc_180001459
0x18000149f  jmp     loc_180002B08
0x1800014a4  mov     ecx, 0F0h; Size
0x1800014a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800014ae  mov     rsi, rax
0x1800014b1  test    rax, rax
0x1800014b4  jz      loc_180002B6F
0x1800014ba  lea     rax, ??_7PROTOCOL_SUPPORT_META_CONTEXT@@6B@; const PROTOCOL_SUPPORT_META_CONTEXT::`vftable'
0x1800014c1  lea     rcx, [rsi+8]
0x1800014c5  mov     [rsi], rax
0x1800014c8  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800014ce  lea     rcx, [rsi+40h]
0x1800014d2  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800014d8  lea     rcx, [rsi+78h]
0x1800014dc  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800014e2  lea     rcx, [rsi+0B0h]
0x1800014e9  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800014ef  lea     r8, [rsp+98h+arg_20]; struct INativeSectionException **
0x1800014f7  mov     rdx, rdi; struct IHttpContext *
0x1800014fa  mov     rcx, rsi; this
0x1800014fd  call    ?Initialize@PROTOCOL_SUPPORT_META_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; PROTOCOL_SUPPORT_META_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x180001502  mov     r12d, eax
0x180001505  test    eax, eax
0x180001507  js      loc_180002AC0
0x18000150d  test    rbx, rbx
0x180001510  jz      loc_180001375
0x180001516  mov     rax, [rbx]
0x180001519  mov     rdx, rsi
0x18000151c  mov     r8, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180001523  mov     rcx, rbx
0x180001526  mov     rax, [rax+8]
0x18000152a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000152f  mov     r12d, eax
0x180001532  test    eax, eax
0x180001534  jns     loc_180001375
0x18000153a  mov     rax, [rsi]
0x18000153d  mov     rcx, rsi
0x180001540  mov     rax, [rax]
0x180001543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001548  cmp     r12d, 80070055h
0x18000154f  jnz     loc_180002B75
0x180001555  mov     rax, [rbx]
0x180001558  mov     rcx, rbx
0x18000155b  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180001562  mov     rax, [rax]
0x180001565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156a  mov     rsi, rax
0x18000156d  jmp     loc_180001375
0x180002ac0  mov     rcx, [rsi]
0x180002ac3  mov     rax, [rcx]
0x180002ac6  mov     rcx, rsi
0x180002ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ace  jmp     loc_180002B75
0x180002ad3  mov     rbx, [r14]
0x180002ad6  mov     rcx, r14
0x180002ad9  mov     rax, [rbx+10h]
0x180002add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae2  or      eax, 1
0x180002ae5  mov     rcx, r14
0x180002ae8  mov     edx, eax
0x180002aea  mov     rax, [rbx+18h]
0x180002aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af3  mov     rax, [r15]
0x180002af6  mov     rcx, r15
0x180002af9  mov     rax, [rax+60h]
0x180002afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b02  nop
0x180002b03  jmp     loc_180001382
0x180002b08  test    r14, r14
0x180002b0b  jz      loc_180001459
0x180002b11  mov     rcx, [r15]
0x180002b14  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180002b1b  mov     rax, [rcx+28h]
0x180002b1f  inc     r9
0x180002b22  cmp     [r14+r9], r13b
0x180002b26  jnz     short loc_180002B1F
0x180002b28  mov     r8, r14
0x180002b2b  mov     dword ptr [rsp+98h+var_78], r13d
0x180002b30  mov     rdx, rbx
0x180002b33  mov     rcx, r15
0x180002b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3b  mov     r12d, eax
0x180002b3e  test    eax, eax
0x180002b40  js      short loc_180002B75
0x180002b42  mov     rdx, rbx
0x180002b45  lea     rcx, [rsi+78h]
0x180002b49  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x180002b4f  mov     rdx, r14
0x180002b52  lea     rcx, [rsi+0B0h]
0x180002b59  mov     rbx, rax
0x180002b5c  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x180002b62  mov     r14, rax
0x180002b65  test    rbx, rbx
0x180002b68  jnz     short loc_180002B08
0x180002b6a  jmp     loc_180001459
0x180002b6f  mov     r12d, 80070008h
0x180002b75  mov     rax, [rdi]
0x180002b78  mov     rcx, rdi
0x180002b7b  mov     rax, [rax+20h]
0x180002b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b84  mov     rdx, rax
0x180002b87  mov     rcx, [rax]
0x180002b8a  mov     rax, [rcx+8]
0x180002b8e  mov     rcx, rdx
0x180002b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b96  mov     [rax+218h], r13w
0x180002b9e  mov     rcx, [rsp+98h+arg_20]
0x180002ba6  test    rcx, rcx
0x180002ba9  jz      loc_180002C4A
0x180002baf  mov     rax, [rcx]
0x180002bb2  lea     r8, [rsp+98h+arg_10]
0x180002bba  lea     rdx, IID_IAppHostConfigException
0x180002bc1  mov     rax, [rax]
0x180002bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc9  mov     rax, [rdi]
0x180002bcc  mov     rcx, rdi
0x180002bcf  mov     rax, [rax+20h]
0x180002bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd8  mov     r10, rax
0x180002bdb  mov     dword ptr [rsp+98h+var_68], r13d
0x180002be0  mov     edx, 1F4h
0x180002be5  lea     r8, aInternalServer; "Internal Server Error"
0x180002bec  mov     r9d, 13h
0x180002bf2  mov     rcx, [rax]
0x180002bf5  mov     rax, [rcx+18h]
0x180002bf9  mov     rcx, [rsp+98h+arg_10]
0x180002c01  mov     [rsp+98h+var_70], rcx
0x180002c06  mov     rcx, r10
0x180002c09  mov     dword ptr [rsp+98h+var_78], r12d
0x180002c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c13  mov     rcx, [rsp+98h+arg_10]
0x180002c1b  test    rcx, rcx
0x180002c1e  jz      short loc_180002C34
0x180002c20  mov     rax, [rcx]
0x180002c23  mov     rax, [rax+10h]
0x180002c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2c  mov     [rsp+98h+arg_10], r13
0x180002c34  mov     rcx, [rsp+98h+arg_20]
0x180002c3c  mov     rax, [rcx]
0x180002c3f  mov     rax, [rax+10h]
0x180002c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c48  jmp     short loc_180002C89
0x180002c4a  mov     rax, [rdi]
0x180002c4d  mov     rcx, rdi
0x180002c50  mov     rax, [rax+20h]
0x180002c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c59  mov     r10, rax
0x180002c5c  mov     dword ptr [rsp+98h+var_68], r13d
0x180002c61  xor     r9d, r9d
0x180002c64  mov     [rsp+98h+var_70], r13
0x180002c69  mov     edx, 1F4h
0x180002c6e  mov     dword ptr [rsp+98h+var_78], r12d
0x180002c73  mov     rcx, [rax]
0x180002c76  lea     r8, aInternalServer; "Internal Server Error"
0x180002c7d  mov     rax, [rcx+18h]
0x180002c81  mov     rcx, r10
0x180002c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c89  xor     eax, eax
0x180002c8b  jmp     loc_180001466
0x180002c90  mov     rax, [rdi]
0x180002c93  mov     rcx, rdi
0x180002c96  mov     rax, [rax+18h]
0x180002c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c9f  mov     rdx, rax
0x180002ca2  mov     rcx, [rax]
0x180002ca5  mov     rax, [rcx+8]
0x180002ca9  mov     rcx, rdx
0x180002cac  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
