# DIRLIST_CONFIG::SetupParsedMetadata(IHttpContext *,DIRLIST_CONFIG * *,INativeSectionException * *)

- ea: `0x1800037e8`
- end: `0x1800038f0`
- name: `?SetupParsedMetadata@DIRLIST_CONFIG@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct DIRLIST_CONFIG **, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180002968`

## callees

- `0x180001008`
- `0x180003590`
- `0x1800037e8`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall DIRLIST_CONFIG::SetupParsedMetadata(
        struct IHttpContext *a1,
        struct DIRLIST_CONFIG **a2,
        struct INativeSectionException **a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  DIRLIST_CONFIG *v8; // rbx
  int v9; // edi

  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  v8 = (DIRLIST_CONFIG *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(v7, g_pDirListingModuleContext);
  if ( v8 )
    goto LABEL_2;
  v8 = (DIRLIST_CONFIG *)operator new(0x18u);
  if ( v8 )
  {
    *(_QWORD *)v8 = &DIRLIST_CONFIG::`vftable';
    v9 = DIRLIST_CONFIG::Initialize(v8, a1, a3);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(DIRLIST_CONFIG *))v8)(v8);
      return (unsigned int)v9;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, DIRLIST_CONFIG *, void *))(*(_QWORD *)v7 + 8LL))(
           v7,
           v8,
           g_pDirListingModuleContext);
    if ( v9 >= 0 )
    {
LABEL_10:
      *a2 = v8;
      return (unsigned int)v9;
    }
    (**(void (__fastcall ***)(DIRLIST_CONFIG *))v8)(v8);
    if ( v9 != -2147024811 )
    {
      v8 = 0;
      goto LABEL_10;
    }
    v8 = (DIRLIST_CONFIG *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(v7, g_pDirListingModuleContext);
LABEL_2:
    v9 = 0;
    goto LABEL_10;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800037e8  push    rbx
0x1800037ea  push    rbp
0x1800037eb  push    rsi
0x1800037ec  push    rdi
0x1800037ed  push    r14
0x1800037ef  sub     rsp, 20h
0x1800037f3  mov     rax, [rcx]
0x1800037f6  mov     rbp, r8
0x1800037f9  mov     r14, rdx
0x1800037fc  mov     rdi, rcx
0x1800037ff  mov     rax, [rax+0A0h]
0x180003806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380b  mov     rcx, rax
0x18000380e  mov     r9, [rax]
0x180003811  mov     rax, [r9+18h]
0x180003815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381a  mov     rdx, cs:?g_pDirListingModuleContext@@3PEAXEA; void * g_pDirListingModuleContext
0x180003821  mov     rsi, rax
0x180003824  mov     rcx, [rax]
0x180003827  mov     rax, [rcx]
0x18000382a  mov     rcx, rsi
0x18000382d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003832  mov     rbx, rax
0x180003835  test    rax, rax
0x180003838  jz      short loc_180003841
0x18000383a  xor     edi, edi
0x18000383c  jmp     loc_1800038D9
0x180003841  mov     ecx, 18h; Size
0x180003846  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000384b  mov     rbx, rax
0x18000384e  test    rax, rax
0x180003851  jz      loc_1800038E0
0x180003857  lea     rax, ??_7DIRLIST_CONFIG@@6B@; const DIRLIST_CONFIG::`vftable'
0x18000385e  mov     r8, rbp; struct INativeSectionException **
0x180003861  mov     rdx, rdi; struct IHttpContext *
0x180003864  mov     [rbx], rax
0x180003867  mov     rcx, rbx; this
0x18000386a  call    ?Initialize@DIRLIST_CONFIG@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; DIRLIST_CONFIG::Initialize(IHttpContext *,INativeSectionException * *)
0x18000386f  mov     edi, eax
0x180003871  test    eax, eax
0x180003873  jns     short loc_180003885
0x180003875  mov     rcx, [rbx]
0x180003878  mov     rax, [rcx]
0x18000387b  mov     rcx, rbx
0x18000387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003883  jmp     short loc_1800038DC
0x180003885  mov     rax, [rsi]
0x180003888  mov     rdx, rbx
0x18000388b  mov     r8, cs:?g_pDirListingModuleContext@@3PEAXEA; void * g_pDirListingModuleContext
0x180003892  mov     rcx, rsi
0x180003895  mov     rax, [rax+8]
0x180003899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389e  mov     edi, eax
0x1800038a0  test    eax, eax
0x1800038a2  jns     short loc_1800038D9
0x1800038a4  mov     rcx, [rbx]
0x1800038a7  mov     rax, [rcx]
0x1800038aa  mov     rcx, rbx
0x1800038ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b2  cmp     edi, 80070055h
0x1800038b8  jnz     short loc_1800038D7
0x1800038ba  mov     rax, [rsi]
0x1800038bd  mov     rcx, rsi
0x1800038c0  mov     rdx, cs:?g_pDirListingModuleContext@@3PEAXEA; void * g_pDirListingModuleContext
0x1800038c7  mov     rax, [rax]
0x1800038ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038cf  mov     rbx, rax
0x1800038d2  jmp     loc_18000383A
0x1800038d7  xor     ebx, ebx
0x1800038d9  mov     [r14], rbx
0x1800038dc  mov     eax, edi
0x1800038de  jmp     short loc_1800038E5
0x1800038e0  mov     eax, 80070008h
0x1800038e5  add     rsp, 20h
0x1800038e9  pop     r14
0x1800038eb  pop     rdi
0x1800038ec  pop     rsi
0x1800038ed  pop     rbp
0x1800038ee  pop     rbx
0x1800038ef  retn
```
