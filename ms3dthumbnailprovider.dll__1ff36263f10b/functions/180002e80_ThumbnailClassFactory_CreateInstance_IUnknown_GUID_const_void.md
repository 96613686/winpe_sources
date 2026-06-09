# ThumbnailClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002e80`
- end: `0x180002f64`
- name: `?CreateInstance@ThumbnailClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(ThumbnailClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f70`

## callees

- `0x180001f14`
- `0x180001f38`
- `0x180002e80`
- `0x180003798`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ThumbnailClassFactory::CreateInstance(
        ThumbnailClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // esi
  Ext3MFThumbnailProvider *v8; // rbx
  Ext3MFThumbnailProvider *v9; // rax
  Ext3MFThumbnailProvider *v10; // rdi

  if ( !a4 )
    return 2147500035LL;
  v7 = -2147221232;
  *a4 = 0;
  if ( !a2 )
  {
    v7 = -2147024882;
    v8 = 0;
    v9 = (Ext3MFThumbnailProvider *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = 0;
    if ( v9 )
    {
      v8 = Ext3MFThumbnailProvider::Ext3MFThumbnailProvider(v9);
      v10 = v8;
    }
    if ( v10 )
    {
      v7 = (**(__int64 (__fastcall ***)(Ext3MFThumbnailProvider *, const struct _GUID *, void **))v8)(v8, a3, a4);
      (*(void (__fastcall **)(Ext3MFThumbnailProvider *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180002e80  mov     [rsp+arg_0], rbx
0x180002e85  mov     [rsp+arg_8], rbp
0x180002e8a  push    rsi
0x180002e8b  push    rdi
0x180002e8c  push    r14
0x180002e8e  sub     rsp, 40h
0x180002e92  mov     r14, r9
0x180002e95  mov     rbp, r8
0x180002e98  mov     [rsp+58h+arg_18], 0
0x180002ea0  test    r9, r9
0x180002ea3  jnz     short loc_180002EAF
0x180002ea5  mov     eax, 80004003h
0x180002eaa  jmp     loc_180002F51
0x180002eaf  mov     esi, 80040110h
0x180002eb4  mov     qword ptr [r9], 0
0x180002ebb  test    rdx, rdx
0x180002ebe  jnz     loc_180002F4F
0x180002ec4  mov     esi, 8007000Eh
0x180002ec9  xor     ebx, ebx
0x180002ecb  mov     [rsp+58h+var_38], rbx
0x180002ed0  mov     [rsp+58h+arg_18], 1
0x180002ed8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002edf  lea     ecx, [rbx+68h]; unsigned __int64
0x180002ee2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002ee7  mov     [rsp+58h+var_30], rax
0x180002eec  mov     [rsp+58h+var_28], rax
0x180002ef1  xor     edi, edi
0x180002ef3  test    rax, rax
0x180002ef6  jz      short loc_180002F12
0x180002ef8  mov     [rsp+58h+var_20], rax
0x180002efd  mov     rcx, rax; this
0x180002f00  call    ??0Ext3MFThumbnailProvider@@QEAA@XZ; Ext3MFThumbnailProvider::Ext3MFThumbnailProvider(void)
0x180002f05  mov     rbx, rax
0x180002f08  mov     [rsp+58h+var_38], rax
0x180002f0d  xor     eax, eax
0x180002f0f  mov     rdi, rbx
0x180002f12  test    rax, rax
0x180002f15  jz      short loc_180002F1F
0x180002f17  mov     rcx, rax; Block
0x180002f1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f1f  test    rdi, rdi
0x180002f22  jz      short loc_180002F3A
0x180002f24  mov     rax, [rbx]
0x180002f27  mov     r8, r14
0x180002f2a  mov     rdx, rbp
0x180002f2d  mov     rcx, rbx
0x180002f30  mov     rax, [rax]
0x180002f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f38  mov     esi, eax
0x180002f3a  test    rdi, rdi
0x180002f3d  jz      short loc_180002F4F
0x180002f3f  mov     rdx, [rdi]
0x180002f42  mov     rcx, rdi
0x180002f45  mov     rax, [rdx+10h]
0x180002f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4e  nop
0x180002f4f  mov     eax, esi
0x180002f51  mov     rbx, [rsp+58h+arg_0]
0x180002f56  mov     rbp, [rsp+58h+arg_8]
0x180002f5b  add     rsp, 40h
0x180002f5f  pop     r14
0x180002f61  pop     rdi
0x180002f62  pop     rsi
0x180002f63  retn
```
