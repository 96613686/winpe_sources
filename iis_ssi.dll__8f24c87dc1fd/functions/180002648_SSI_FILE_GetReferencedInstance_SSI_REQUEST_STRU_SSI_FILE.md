# SSI_FILE::GetReferencedInstance(SSI_REQUEST *,STRU &,SSI_FILE * *)

- ea: `0x180002648`
- end: `0x180002971`
- name: `?GetReferencedInstance@SSI_FILE@@SAJPEAVSSI_REQUEST@@AEAVSTRU@@PEAPEAV1@@Z`
- size: `809`
- prototype: `__int64 __fastcall(struct SSI_REQUEST *, struct STRU *, struct SSI_FILE **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003c24`
- `0x180003fac`
- `0x1800040ec`

## callees

- `0x180001008`
- `0x180002648`
- `0x180002978`
- `0x180006010`

## import_xrefs

- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x180002677`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x180002677`

## pseudocode

```c
__int64 __fastcall SSI_FILE::GetReferencedInstance(struct SSI_REQUEST *a1, struct STRU *a2, struct SSI_FILE **a3)
{
  __int64 v3; // rsi
  __int64 v5; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r12
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // esi
  __int64 (__fastcall ***v18)(_QWORD, void *); // rax
  struct SSI_FILE *v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v26; // [rsp+90h] [rbp+40h] BYREF
  __int64 (__fastcall *v27)(struct IHttpServer *, _QWORD, __int64, _QWORD, __int64, __int64, int, __int64 *, __int64); // [rsp+A8h] [rbp+58h]

  v3 = *((_QWORD *)a1 + 1);
  v5 = 0;
  v26 = 0;
  if ( !STRU::Equals(a2, (struct SSI_REQUEST *)((char *)a1 + 16)) )
    goto LABEL_5;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 208LL))(v3);
  v26 = v7;
  v8 = v7;
  if ( !v7 )
    goto LABEL_6;
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))(v7) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
LABEL_5:
    v8 = v26;
    goto LABEL_6;
  }
  v8 = 0;
  v26 = 0;
LABEL_6:
  if ( !v8 )
  {
    v27 = *(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64, _QWORD, __int64, __int64, int, __int64 *, __int64))(*(_QWORD *)s_pGlobalInfo + 64LL);
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 272LL))(v3);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 160LL))(v3);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 160LL))(v3);
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 56LL))(v12);
    }
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 160LL))(v3);
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
    v17 = v27(s_pGlobalInfo, *((_QWORD *)a2 + 4), v16, 0, v14, v5, 1, &v26, v9);
    if ( v17 < 0 )
      goto LABEL_23;
    v8 = v26;
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 152LL))(v8) )
  {
    v18 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 152LL))(v26);
    v19 = (struct SSI_FILE *)(**v18)(v18, s_pSSIModuleContext);
    if ( v19 )
    {
LABEL_21:
      *a3 = v19;
      return 0;
    }
  }
  v20 = v26;
  v19 = (struct SSI_FILE *)operator new(0x30u);
  if ( !v19 )
  {
    v17 = -2147024882;
    goto LABEL_23;
  }
  *((_QWORD *)v19 + 2) = v20;
  *(_QWORD *)v19 = &SSI_FILE::`vftable';
  *((_QWORD *)v19 + 3) = 0;
  *((_QWORD *)v19 + 4) = 0;
  *((_DWORD *)v19 + 10) = 0;
  *((_DWORD *)v19 + 2) = 1279870547;
  v17 = SSI_FILE::Initialize(v19);
  if ( v17 >= 0 )
  {
    v22 = *((_QWORD *)v19 + 2);
    if ( v22 )
    {
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 152LL))(v22) )
      {
        v23 = *((_QWORD *)v19 + 2);
        *((_DWORD *)v19 + 10) = 1;
        v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 152LL))(v23);
        if ( (*(int (__fastcall **)(__int64, struct SSI_FILE *, void *))(*(_QWORD *)v24 + 8LL))(
               v24,
               v19,
               s_pSSIModuleContext) < 0 )
          *((_DWORD *)v19 + 10) = 0;
      }
    }
    goto LABEL_21;
  }
  v21 = *(_QWORD *)v19;
  *((_QWORD *)v19 + 2) = 0;
  (*(void (__fastcall **)(struct SSI_FILE *, __int64))(v21 + 8))(v19, 1);
LABEL_23:
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  *a3 = 0;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180002648  mov     [rsp-38h+arg_8], rbx
0x18000264d  push    rbp
0x18000264e  push    rsi
0x18000264f  push    rdi
0x180002650  push    r12
0x180002652  push    r13
0x180002654  push    r14
0x180002656  push    r15
0x180002658  mov     rbp, rsp
0x18000265b  sub     rsp, 50h
0x18000265f  mov     rsi, [rcx+8]
0x180002663  mov     r13, rdx
0x180002666  lea     rdx, [rcx+10h]
0x18000266a  xor     r15d, r15d
0x18000266d  mov     rcx, r13
0x180002670  mov     [rbp+arg_0], r15
0x180002674  mov     r14, r8
0x180002677  call    cs:__imp_?Equals@STRU@@QEBA_NAEBV1@@Z; STRU::Equals(STRU const &)
0x18000267d  test    al, al
0x18000267f  jz      short loc_1800026C4
0x180002681  mov     rax, [rsi]
0x180002684  mov     rcx, rsi
0x180002687  mov     rax, [rax+0D0h]
0x18000268e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002693  mov     [rbp+arg_0], rax
0x180002697  mov     rcx, rax
0x18000269a  test    rax, rax
0x18000269d  jz      short loc_1800026C8
0x18000269f  mov     rax, [rax]
0x1800026a2  mov     rax, [rax+48h]
0x1800026a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ab  test    rax, rax
0x1800026ae  jz      loc_18000289B
0x1800026b4  mov     rcx, [rbp+arg_0]
0x1800026b8  mov     rax, [rcx]
0x1800026bb  mov     rax, [rax+8]
0x1800026bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c4  mov     rcx, [rbp+arg_0]
0x1800026c8  test    rcx, rcx
0x1800026cb  jnz     loc_1800027ED
0x1800026d1  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800026d8  mov     rdi, r15
0x1800026db  mov     rcx, [rax]
0x1800026de  mov     rax, [rcx+40h]
0x1800026e2  mov     rcx, rsi
0x1800026e5  mov     [rbp+arg_18], rax
0x1800026e9  mov     rax, [rsi]
0x1800026ec  mov     rax, [rax+110h]
0x1800026f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f8  mov     rcx, [rsi]
0x1800026fb  mov     r12, rax
0x1800026fe  mov     rax, [rcx+0A0h]
0x180002705  mov     rcx, rsi
0x180002708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270d  mov     rdx, rax
0x180002710  mov     rcx, [rax]
0x180002713  mov     rax, [rcx+10h]
0x180002717  mov     rcx, rdx
0x18000271a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271f  test    rax, rax
0x180002722  jz      short loc_18000275D
0x180002724  mov     rax, [rsi]
0x180002727  mov     rcx, rsi
0x18000272a  mov     rax, [rax+0A0h]
0x180002731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002736  mov     rdx, rax
0x180002739  mov     rcx, [rax]
0x18000273c  mov     rax, [rcx+10h]
0x180002740  mov     rcx, rdx
0x180002743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002748  mov     rdx, rax
0x18000274b  mov     rcx, [rax]
0x18000274e  mov     rax, [rcx+38h]
0x180002752  mov     rcx, rdx
0x180002755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275a  mov     r15, rax
0x18000275d  mov     rcx, [rsi]
0x180002760  mov     rax, [rcx+0A0h]
0x180002767  mov     rcx, rsi
0x18000276a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276f  mov     rcx, rax
0x180002772  mov     rdx, [rax]
0x180002775  mov     rax, [rdx+8]
0x180002779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000277e  mov     rdx, [rsi]
0x180002781  mov     rbx, rax
0x180002784  mov     rcx, rsi
0x180002787  mov     rax, [rdx+30h]
0x18000278b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002790  mov     rdx, rax
0x180002793  mov     rcx, [rax]
0x180002796  mov     rax, [rcx+20h]
0x18000279a  mov     rcx, rdx
0x18000279d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a2  mov     rdx, [r13+20h]
0x1800027a6  lea     rcx, [rbp+arg_0]
0x1800027aa  mov     [rsp+50h+var_10], r12
0x1800027af  mov     r8, rax
0x1800027b2  mov     rax, [rbp+arg_18]
0x1800027b6  xor     r9d, r9d
0x1800027b9  mov     [rsp+50h+var_18], rcx
0x1800027be  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800027c5  mov     [rsp+50h+var_20], 1
0x1800027cd  mov     [rsp+50h+var_28], r15
0x1800027d2  mov     [rsp+50h+var_30], rbx
0x1800027d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027dc  xor     r15d, r15d
0x1800027df  mov     esi, eax
0x1800027e1  test    eax, eax
0x1800027e3  js      loc_180002911
0x1800027e9  mov     rcx, [rbp+arg_0]
0x1800027ed  mov     rax, [rcx]
0x1800027f0  mov     rax, [rax+98h]
0x1800027f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027fc  test    rax, rax
0x1800027ff  jz      short loc_180002838
0x180002801  mov     rcx, [rbp+arg_0]
0x180002805  mov     rax, [rcx]
0x180002808  mov     rax, [rax+98h]
0x18000280f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002814  mov     rdx, cs:?s_pSSIModuleContext@@3PEAXEA; void * s_pSSIModuleContext
0x18000281b  mov     r8, rax
0x18000281e  mov     rcx, [rax]
0x180002821  mov     rax, [rcx]
0x180002824  mov     rcx, r8
0x180002827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282c  mov     rbx, rax
0x18000282f  test    rax, rax
0x180002832  jnz     loc_180002902
0x180002838  mov     rdi, [rbp+arg_0]
0x18000283c  mov     ecx, 30h ; '0'; Size
0x180002841  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002846  mov     rbx, rax
0x180002849  test    rax, rax
0x18000284c  jz      loc_180002909
0x180002852  lea     rax, ??_7SSI_FILE@@6B@; const SSI_FILE::`vftable'
0x180002859  mov     [rbx+10h], rdi
0x18000285d  mov     [rbx], rax
0x180002860  mov     rcx, rbx; this
0x180002863  mov     [rbx+18h], r15
0x180002867  mov     [rbx+20h], r15
0x18000286b  mov     [rbx+28h], r15d
0x18000286f  mov     dword ptr [rbx+8], 4C494653h
0x180002876  call    ?Initialize@SSI_FILE@@AEAAJXZ; SSI_FILE::Initialize(void)
0x18000287b  mov     esi, eax
0x18000287d  test    eax, eax
0x18000287f  jns     short loc_1800028A7
0x180002881  mov     rax, [rbx]
0x180002884  mov     edx, 1
0x180002889  mov     rcx, rbx
0x18000288c  mov     [rbx+10h], r15
0x180002890  mov     rax, [rax+8]
0x180002894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002899  jmp     short loc_18000290E
0x18000289b  mov     rcx, r15
0x18000289e  mov     [rbp+arg_0], rcx
0x1800028a2  jmp     loc_1800026C8
0x1800028a7  mov     rcx, [rbx+10h]
0x1800028ab  test    rcx, rcx
0x1800028ae  jz      short loc_180002902
0x1800028b0  mov     rax, [rcx]
0x1800028b3  mov     rax, [rax+98h]
0x1800028ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028bf  test    rax, rax
0x1800028c2  jz      short loc_180002902
0x1800028c4  mov     rcx, [rbx+10h]
0x1800028c8  mov     dword ptr [rbx+28h], 1
0x1800028cf  mov     rax, [rcx]
0x1800028d2  mov     rax, [rax+98h]
0x1800028d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028de  mov     r8, cs:?s_pSSIModuleContext@@3PEAXEA; void * s_pSSIModuleContext
0x1800028e5  mov     r9, rax
0x1800028e8  mov     rdx, rbx
0x1800028eb  mov     rcx, [rax]
0x1800028ee  mov     rax, [rcx+8]
0x1800028f2  mov     rcx, r9
0x1800028f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fa  test    eax, eax
0x1800028fc  jns     short loc_180002902
0x1800028fe  mov     [rbx+28h], r15d
0x180002902  mov     [r14], rbx
0x180002905  xor     eax, eax
0x180002907  jmp     short loc_180002959
0x180002909  mov     esi, 8007000Eh
0x18000290e  mov     rdi, r15
0x180002911  mov     rcx, [rbp+arg_0]
0x180002915  test    rcx, rcx
0x180002918  jz      short loc_180002954
0x18000291a  mov     rax, [rcx]
0x18000291d  mov     rax, [rax+10h]
0x180002921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002926  mov     [rbp+arg_0], r15
0x18000292a  test    rdi, rdi
0x18000292d  jz      short loc_180002954
0x18000292f  mov     ebx, [rdi+28h]
0x180002932  mov     rcx, [rdi+10h]
0x180002936  mov     rax, [rcx]
0x180002939  mov     rax, [rax+10h]
0x18000293d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002942  test    ebx, ebx
0x180002944  jnz     short loc_180002954
0x180002946  mov     rax, [rdi]
0x180002949  mov     rcx, rdi
0x18000294c  mov     rax, [rax]
0x18000294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002954  mov     [r14], r15
0x180002957  mov     eax, esi
0x180002959  mov     rbx, [rsp+50h+arg_8]
0x180002961  add     rsp, 50h
0x180002965  pop     r15
0x180002967  pop     r14
0x180002969  pop     r13
0x18000296b  pop     r12
0x18000296d  pop     rdi
0x18000296e  pop     rsi
0x18000296f  pop     rbp
0x180002970  retn
```
