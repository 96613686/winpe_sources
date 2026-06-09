# DEFDOC_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,DEFDOC_META_STORED_CONTEXT * *,INativeSectionException * *)

- ea: `0x180002e18`
- end: `0x180002f26`
- name: `?GetParsedMetadata@DEFDOC_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct DEFDOC_META_STORED_CONTEXT **, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002240`

## callees

- `0x180001008`
- `0x180002e18`
- `0x180002f2c`
- `0x180004010`

## import_xrefs

- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002e95`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002e95`

## pseudocode

```c
__int64 __fastcall DEFDOC_META_STORED_CONTEXT::GetParsedMetadata(
        struct IHttpContext *a1,
        struct DEFDOC_META_STORED_CONTEXT **a2,
        struct INativeSectionException **a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  struct DEFDOC_META_STORED_CONTEXT *v8; // rax
  char *v10; // rbx
  int v11; // edi

  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  v8 = (struct DEFDOC_META_STORED_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(
                                              v7,
                                              g_pDefaultDocModuleContext);
  if ( v8 )
  {
    *a2 = v8;
    return 0;
  }
  v10 = (char *)operator new(0x48u);
  if ( v10 )
  {
    *(_QWORD *)v10 = &DEFDOC_META_STORED_CONTEXT::`vftable';
    MULTISZ::MULTISZ((MULTISZ *)(v10 + 16));
    v11 = DEFDOC_META_STORED_CONTEXT::Initialize((DEFDOC_META_STORED_CONTEXT *)v10, a1, a3);
    if ( v11 < 0 )
    {
      (**(void (__fastcall ***)(void *))v10)(v10);
      return (unsigned int)v11;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v7 + 8LL))(
            v7,
            v10,
            g_pDefaultDocModuleContext);
    if ( v11 < 0 )
    {
      (**(void (__fastcall ***)(void *))v10)(v10);
      if ( v11 != -2147024811 )
        return (unsigned int)v11;
      v10 = (char *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(v7, g_pDefaultDocModuleContext);
    }
    *a2 = (struct DEFDOC_META_STORED_CONTEXT *)v10;
    return 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002e18  push    rbx
0x180002e1a  push    rbp
0x180002e1b  push    rsi
0x180002e1c  push    rdi
0x180002e1d  push    r14
0x180002e1f  sub     rsp, 20h
0x180002e23  mov     rax, [rcx]
0x180002e26  mov     rbp, r8
0x180002e29  mov     r14, rdx
0x180002e2c  mov     rdi, rcx
0x180002e2f  mov     rax, [rax+0A0h]
0x180002e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3b  mov     rcx, rax
0x180002e3e  mov     r9, [rax]
0x180002e41  mov     rax, [r9+18h]
0x180002e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4a  mov     rdx, cs:?g_pDefaultDocModuleContext@@3PEAXEA; void * g_pDefaultDocModuleContext
0x180002e51  mov     rsi, rax
0x180002e54  mov     rcx, [rax]
0x180002e57  mov     rax, [rcx]
0x180002e5a  mov     rcx, rsi
0x180002e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e62  test    rax, rax
0x180002e65  jz      short loc_180002E71
0x180002e67  mov     [r14], rax
0x180002e6a  xor     eax, eax
0x180002e6c  jmp     loc_180002F1B
0x180002e71  mov     ecx, 48h ; 'H'; Size
0x180002e76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e7b  mov     rbx, rax
0x180002e7e  test    rax, rax
0x180002e81  jz      loc_180002F16
0x180002e87  lea     rax, ??_7DEFDOC_META_STORED_CONTEXT@@6B@; const DEFDOC_META_STORED_CONTEXT::`vftable'
0x180002e8e  lea     rcx, [rbx+10h]
0x180002e92  mov     [rbx], rax
0x180002e95  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002e9b  mov     r8, rbp; struct INativeSectionException **
0x180002e9e  mov     rdx, rdi; struct IHttpContext *
0x180002ea1  mov     rcx, rbx; this
0x180002ea4  call    ?Initialize@DEFDOC_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; DEFDOC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x180002ea9  mov     edi, eax
0x180002eab  test    eax, eax
0x180002ead  jns     short loc_180002EC1
0x180002eaf  mov     rcx, [rbx]
0x180002eb2  mov     rax, [rcx]
0x180002eb5  mov     rcx, rbx
0x180002eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebd  mov     eax, edi
0x180002ebf  jmp     short loc_180002F1B
0x180002ec1  mov     rax, [rsi]
0x180002ec4  mov     rdx, rbx
0x180002ec7  mov     r8, cs:?g_pDefaultDocModuleContext@@3PEAXEA; void * g_pDefaultDocModuleContext
0x180002ece  mov     rcx, rsi
0x180002ed1  mov     rax, [rax+8]
0x180002ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eda  mov     edi, eax
0x180002edc  test    eax, eax
0x180002ede  jns     short loc_180002F0E
0x180002ee0  mov     rcx, [rbx]
0x180002ee3  mov     rax, [rcx]
0x180002ee6  mov     rcx, rbx
0x180002ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eee  cmp     edi, 80070055h
0x180002ef4  jnz     short loc_180002EBD
0x180002ef6  mov     rax, [rsi]
0x180002ef9  mov     rcx, rsi
0x180002efc  mov     rdx, cs:?g_pDefaultDocModuleContext@@3PEAXEA; void * g_pDefaultDocModuleContext
0x180002f03  mov     rax, [rax]
0x180002f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0b  mov     rbx, rax
0x180002f0e  mov     [r14], rbx
0x180002f11  jmp     loc_180002E6A
0x180002f16  mov     eax, 80070008h
0x180002f1b  add     rsp, 20h
0x180002f1f  pop     r14
0x180002f21  pop     rdi
0x180002f22  pop     rsi
0x180002f23  pop     rbp
0x180002f24  pop     rbx
0x180002f25  retn
```
