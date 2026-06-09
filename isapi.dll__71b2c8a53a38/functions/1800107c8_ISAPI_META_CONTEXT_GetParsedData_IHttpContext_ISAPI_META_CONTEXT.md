# ISAPI_META_CONTEXT::GetParsedData(IHttpContext *,ISAPI_META_CONTEXT * *)

- ea: `0x1800107c8`
- end: `0x1800108c9`
- name: `?GetParsedData@ISAPI_META_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@@Z`
- size: `257`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct ISAPI_META_CONTEXT **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b3d0`
- `0x18000b8f0`

## callees

- `0x180001020`
- `0x1800107c8`
- `0x1800108d0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_META_CONTEXT::GetParsedData(struct IHttpContext *a1, struct ISAPI_META_CONTEXT **a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  struct ISAPI_META_CONTEXT *v6; // rax
  ISAPI_META_CONTEXT *v8; // rbx
  int v9; // edi

  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
  v6 = (struct ISAPI_META_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v5)(v5, g_pModuleContext);
  if ( v6 )
  {
    *a2 = v6;
    return 0;
  }
  v8 = (ISAPI_META_CONTEXT *)operator new(0x10u);
  if ( !v8 )
    return 2147942408LL;
  *(_QWORD *)v8 = &ISAPI_META_CONTEXT::`vftable';
  v9 = ISAPI_META_CONTEXT::Initialize(v8, a1);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, ISAPI_META_CONTEXT *, void *))(*(_QWORD *)v5 + 8LL))(
           v5,
           v8,
           g_pModuleContext);
    if ( v9 >= 0
      || ((**(void (__fastcall ***)(ISAPI_META_CONTEXT *))v8)(v8), v9 == -2147024811)
      && (v8 = (ISAPI_META_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v5)(v5, g_pModuleContext)) != 0 )
    {
      *a2 = v8;
      return 0;
    }
  }
  else
  {
    (**(void (__fastcall ***)(ISAPI_META_CONTEXT *))v8)(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800107c8  push    rbx
0x1800107ca  push    rsi
0x1800107cb  push    rdi
0x1800107cc  push    r14
0x1800107ce  sub     rsp, 28h
0x1800107d2  mov     rax, [rcx]
0x1800107d5  mov     r14, rdx
0x1800107d8  mov     rdi, rcx
0x1800107db  mov     rax, [rax+0A0h]
0x1800107e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e7  mov     rcx, rax
0x1800107ea  mov     r8, [rax]
0x1800107ed  mov     rax, [r8+18h]
0x1800107f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f6  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800107fd  mov     rsi, rax
0x180010800  mov     rcx, [rax]
0x180010803  mov     rax, [rcx]
0x180010806  mov     rcx, rsi
0x180010809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080e  test    rax, rax
0x180010811  jz      short loc_18001081D
0x180010813  mov     [r14], rax
0x180010816  xor     eax, eax
0x180010818  jmp     loc_1800108BF
0x18001081d  mov     ecx, 10h; Size
0x180010822  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010827  mov     rbx, rax
0x18001082a  test    rax, rax
0x18001082d  jz      loc_1800108BA
0x180010833  lea     rax, ??_7ISAPI_META_CONTEXT@@6B@; const ISAPI_META_CONTEXT::`vftable'
0x18001083a  mov     rdx, rdi; struct IHttpContext *
0x18001083d  mov     rcx, rbx; this
0x180010840  mov     [rbx], rax
0x180010843  call    ?Initialize@ISAPI_META_CONTEXT@@AEAAJPEAVIHttpContext@@@Z; ISAPI_META_CONTEXT::Initialize(IHttpContext *)
0x180010848  mov     edi, eax
0x18001084a  test    eax, eax
0x18001084c  jns     short loc_180010860
0x18001084e  mov     rcx, [rbx]
0x180010851  mov     rax, [rcx]
0x180010854  mov     rcx, rbx
0x180010857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001085c  mov     eax, edi
0x18001085e  jmp     short loc_1800108BF
0x180010860  mov     rax, [rsi]
0x180010863  mov     rdx, rbx
0x180010866  mov     r8, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x18001086d  mov     rcx, rsi
0x180010870  mov     rax, [rax+8]
0x180010874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010879  mov     edi, eax
0x18001087b  test    eax, eax
0x18001087d  jns     short loc_1800108B2
0x18001087f  mov     rcx, [rbx]
0x180010882  mov     rax, [rcx]
0x180010885  mov     rcx, rbx
0x180010888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001088d  cmp     edi, 80070055h
0x180010893  jnz     short loc_18001085C
0x180010895  mov     rcx, [rsi]
0x180010898  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x18001089f  mov     rax, [rcx]
0x1800108a2  mov     rcx, rsi
0x1800108a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108aa  mov     rbx, rax
0x1800108ad  test    rax, rax
0x1800108b0  jz      short loc_18001085C
0x1800108b2  mov     [r14], rbx
0x1800108b5  jmp     loc_180010816
0x1800108ba  mov     eax, 80070008h
0x1800108bf  add     rsp, 28h
0x1800108c3  pop     r14
0x1800108c5  pop     rdi
0x1800108c6  pop     rsi
0x1800108c7  pop     rbx
0x1800108c8  retn
```
