# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000231c`
- end: `0x1800024ca`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a60`
- `0x180001c00`

## callees

- `0x18000231c`
- `0x180003304`
- `0x1800033c8`
- `0x1800034b0`
- `0x180003530`
- `0x180006010`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800023a0`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800023a0`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000235a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000235a`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rsi
  SSI_REQUEST *v7; // rax
  SSI_REQUEST *v8; // rax
  SSI_REQUEST *v9; // rbx
  __int64 v10; // rax
  int v11; // edx
  __int64 (__fastcall ***v13)(_QWORD, void *); // rax
  __int64 v14; // rax
  int v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  if ( a1 != 128 )
    return 0;
  v6 = a5;
  if ( a5 )
  {
    v13 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
    v9 = (SSI_REQUEST *)(**v13)(v13, s_pSSIModuleContext);
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  else
  {
    v7 = (SSI_REQUEST *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)SSI_REQUEST::sm_pachSsiRequests);
    if ( !v7 )
      goto LABEL_16;
    v8 = SSI_REQUEST::SSI_REQUEST(v7, a3);
    v9 = v8;
    if ( !v8 )
      goto LABEL_16;
    if ( (int)SSI_REQUEST::Initialize(v8) < 0 )
    {
      SSI_REQUEST::~SSI_REQUEST(v9);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)SSI_REQUEST::sm_pachSsiRequests, v9);
LABEL_16:
      v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v14 + 24LL))(
        v14,
        500,
        "Internal Server Error");
      return 2;
    }
    v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
    if ( (*(int (__fastcall **)(__int64, SSI_REQUEST *, void *))(*(_QWORD *)v10 + 8LL))(v10, v9, s_pSSIModuleContext) < 0 )
    {
      (**(void (__fastcall ***)(SSI_REQUEST *))v9)(v9);
      goto LABEL_16;
    }
    v11 = 0;
  }
  if ( SSI_REQUEST::DoWork(v9, v11, &v15) < 0 )
    goto LABEL_16;
  if ( !v15 )
  {
    (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 200LL))(a3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000231c  mov     rax, rsp
0x18000231f  mov     [rax+8], rbx
0x180002323  mov     [rax+18h], rsi
0x180002327  mov     [rax+10h], edx
0x18000232a  push    rdi
0x18000232b  sub     rsp, 40h
0x18000232f  mov     dword ptr [rax+10h], 0
0x180002336  mov     rdi, r8
0x180002339  cmp     ecx, 80h
0x18000233f  jnz     loc_180002410
0x180002345  mov     rsi, [rsp+48h+arg_20]
0x18000234a  test    rsi, rsi
0x18000234d  jnz     loc_180002429
0x180002353  mov     rcx, cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x18000235a  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180002360  test    rax, rax
0x180002363  jz      loc_180002422
0x180002369  mov     rdx, rdi; struct IHttpContext *
0x18000236c  mov     rcx, rax; this
0x18000236f  call    ??0SSI_REQUEST@@AEAA@PEAVIHttpContext@@@Z; SSI_REQUEST::SSI_REQUEST(IHttpContext *)
0x180002374  mov     rbx, rax
0x180002377  test    rax, rax
0x18000237a  jz      loc_180002422
0x180002380  mov     rcx, rax; this
0x180002383  call    ?Initialize@SSI_REQUEST@@AEAAJXZ; SSI_REQUEST::Initialize(void)
0x180002388  mov     esi, eax
0x18000238a  test    eax, eax
0x18000238c  jns     short loc_1800023AB
0x18000238e  mov     rcx, rbx; this
0x180002391  call    ??1SSI_REQUEST@@QEAA@XZ; SSI_REQUEST::~SSI_REQUEST(void)
0x180002396  mov     rcx, cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x18000239d  mov     rdx, rbx
0x1800023a0  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800023a6  jmp     loc_180002478
0x1800023ab  mov     rax, [rdi]
0x1800023ae  mov     rcx, rdi
0x1800023b1  mov     rax, [rax+38h]
0x1800023b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ba  mov     r8, cs:?s_pSSIModuleContext@@3PEAXEA; void * s_pSSIModuleContext
0x1800023c1  mov     r9, rax
0x1800023c4  mov     rdx, rbx
0x1800023c7  mov     rcx, [rax]
0x1800023ca  mov     rax, [rcx+8]
0x1800023ce  mov     rcx, r9
0x1800023d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d6  mov     esi, eax
0x1800023d8  test    eax, eax
0x1800023da  jns     short loc_1800023EF
0x1800023dc  mov     rcx, [rbx]
0x1800023df  mov     rax, [rcx]
0x1800023e2  mov     rcx, rbx
0x1800023e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ea  jmp     loc_180002478
0x1800023ef  xor     edx, edx
0x1800023f1  jmp     short loc_180002461
0x1800023f3  cmp     [rsp+48h+arg_8], 0
0x1800023f8  jnz     loc_1800024C0
0x1800023fe  mov     rax, [rdi]
0x180002401  mov     rcx, rdi
0x180002404  mov     rax, [rax+0C8h]
0x18000240b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002410  xor     eax, eax
0x180002412  mov     rbx, [rsp+48h+arg_0]
0x180002417  mov     rsi, [rsp+48h+arg_10]
0x18000241c  add     rsp, 40h
0x180002420  pop     rdi
0x180002421  retn
0x180002422  mov     esi, 8007000Eh
0x180002427  jmp     short loc_180002478
0x180002429  mov     rax, [r8]
0x18000242c  mov     rcx, rdi
0x18000242f  mov     rax, [rax+38h]
0x180002433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002438  mov     rdx, cs:?s_pSSIModuleContext@@3PEAXEA; void * s_pSSIModuleContext
0x18000243f  mov     rcx, rax
0x180002442  mov     r8, [rax]
0x180002445  mov     rax, [r8]
0x180002448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000244d  mov     rdx, [rsi]
0x180002450  mov     rbx, rax
0x180002453  mov     rcx, rsi
0x180002456  mov     rax, [rdx+8]
0x18000245a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000245f  mov     edx, eax; int
0x180002461  lea     r8, [rsp+48h+arg_8]; int *
0x180002466  mov     rcx, rbx; this
0x180002469  call    ?DoWork@SSI_REQUEST@@QEAAJJPEAH@Z; SSI_REQUEST::DoWork(long,int *)
0x18000246e  mov     esi, eax
0x180002470  test    eax, eax
0x180002472  jns     loc_1800023F3
0x180002478  mov     rax, [rdi]
0x18000247b  mov     rcx, rdi
0x18000247e  mov     rax, [rax+20h]
0x180002482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002487  xor     r9d, r9d
0x18000248a  lea     r8, aInternalServer; "Internal Server Error"
0x180002491  mov     r10, rax
0x180002494  mov     [rsp+48h+var_18], r9d
0x180002499  mov     [rsp+48h+var_20], r9
0x18000249e  mov     edx, 1F4h
0x1800024a3  mov     rcx, [rax]
0x1800024a6  mov     [rsp+48h+var_28], esi
0x1800024aa  mov     rax, [rcx+18h]
0x1800024ae  mov     rcx, r10
0x1800024b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024b6  mov     eax, 2
0x1800024bb  jmp     loc_180002412
0x1800024c0  mov     eax, 1
0x1800024c5  jmp     loc_180002412
```
