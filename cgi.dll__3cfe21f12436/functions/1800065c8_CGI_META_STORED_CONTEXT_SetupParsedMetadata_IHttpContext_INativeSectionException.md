# CGI_META_STORED_CONTEXT::SetupParsedMetadata(IHttpContext *,INativeSectionException * *)

- ea: `0x1800065c8`
- end: `0x1800066a2`
- name: `?SetupParsedMetadata@CGI_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000259c`

## callees

- `0x180001008`
- `0x180006368`
- `0x1800065c8`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall CGI_META_STORED_CONTEXT::SetupParsedMetadata(
        struct IHttpContext *a1,
        struct INativeSectionException **a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  CGI_META_STORED_CONTEXT *v6; // rbx
  int v7; // edi
  __int64 result; // rax
  int v9; // edi

  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
  if ( (**(__int64 (__fastcall ***)(__int64, void *))v5)(v5, g_pCgiHandlerContext) )
    return 0;
  v6 = (CGI_META_STORED_CONTEXT *)operator new(0x18u);
  if ( !v6 )
    return 2147942408LL;
  *(_QWORD *)v6 = &CGI_META_STORED_CONTEXT::`vftable';
  v7 = CGI_META_STORED_CONTEXT::Initialize(v6, a1, a2);
  if ( v7 < 0 )
  {
    (**(void (__fastcall ***)(CGI_META_STORED_CONTEXT *))v6)(v6);
    return (unsigned int)v7;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, CGI_META_STORED_CONTEXT *, void *))(*(_QWORD *)v5 + 8LL))(
         v5,
         v6,
         g_pCgiHandlerContext);
  if ( v9 >= 0 )
    return 0;
  (**(void (__fastcall ***)(CGI_META_STORED_CONTEXT *))v6)(v6);
  result = 0;
  if ( v9 != -2147024811 )
    return (unsigned int)v9;
  return result;
}

```

## disassembly

```asm
0x1800065c8  push    rbx
0x1800065ca  push    rbp
0x1800065cb  push    rsi
0x1800065cc  push    rdi
0x1800065cd  sub     rsp, 28h
0x1800065d1  mov     rax, [rcx]
0x1800065d4  mov     rbp, rdx
0x1800065d7  mov     rdi, rcx
0x1800065da  mov     rax, [rax+0A0h]
0x1800065e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e6  mov     rcx, rax
0x1800065e9  mov     r8, [rax]
0x1800065ec  mov     rax, [r8+18h]
0x1800065f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f5  mov     rdx, cs:?g_pCgiHandlerContext@@3PEAXEA; void * g_pCgiHandlerContext
0x1800065fc  mov     rsi, rax
0x1800065ff  mov     rcx, [rax]
0x180006602  mov     rax, [rcx]
0x180006605  mov     rcx, rsi
0x180006608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660d  test    rax, rax
0x180006610  jnz     loc_180006697
0x180006616  lea     ecx, [rax+18h]; Size
0x180006619  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000661e  mov     rbx, rax
0x180006621  test    rax, rax
0x180006624  jz      short loc_180006690
0x180006626  lea     rax, ??_7CGI_META_STORED_CONTEXT@@6B@; const CGI_META_STORED_CONTEXT::`vftable'
0x18000662d  mov     r8, rbp; struct INativeSectionException **
0x180006630  mov     rdx, rdi; struct IHttpContext *
0x180006633  mov     [rbx], rax
0x180006636  mov     rcx, rbx; this
0x180006639  call    ?Initialize@CGI_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; CGI_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x18000663e  mov     edi, eax
0x180006640  test    eax, eax
0x180006642  jns     short loc_180006656
0x180006644  mov     rcx, [rbx]
0x180006647  mov     rax, [rcx]
0x18000664a  mov     rcx, rbx
0x18000664d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006652  mov     eax, edi
0x180006654  jmp     short loc_180006699
0x180006656  mov     rax, [rsi]
0x180006659  mov     rdx, rbx
0x18000665c  mov     r8, cs:?g_pCgiHandlerContext@@3PEAXEA; void * g_pCgiHandlerContext
0x180006663  mov     rcx, rsi
0x180006666  mov     rax, [rax+8]
0x18000666a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000666f  mov     edi, eax
0x180006671  test    eax, eax
0x180006673  jns     short loc_180006697
0x180006675  mov     rcx, [rbx]
0x180006678  mov     rax, [rcx]
0x18000667b  mov     rcx, rbx
0x18000667e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006683  xor     eax, eax
0x180006685  cmp     edi, 80070055h
0x18000668b  cmovnz  eax, edi
0x18000668e  jmp     short loc_180006699
0x180006690  mov     eax, 80070008h
0x180006695  jmp     short loc_180006699
0x180006697  xor     eax, eax
0x180006699  add     rsp, 28h
0x18000669d  pop     rdi
0x18000669e  pop     rsi
0x18000669f  pop     rbp
0x1800066a0  pop     rbx
0x1800066a1  retn
```
