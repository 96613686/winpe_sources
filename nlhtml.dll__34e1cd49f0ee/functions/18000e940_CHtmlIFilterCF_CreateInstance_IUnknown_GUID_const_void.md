# CHtmlIFilterCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000e940`
- end: `0x18000e9e8`
- name: `?CreateInstance@CHtmlIFilterCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(CHtmlIFilterCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e940`
- `0x18000ed78`
- `0x180014700`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CHtmlIFilterCF::CreateInstance(
        CHtmlIFilterCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CHtmlIFilter *v6; // rax
  CHtmlIFilter *v7; // rbx
  unsigned int v8; // edi

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v6 = (CHtmlIFilter *)operator new(0x15D8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    v7 = CHtmlIFilter::CHtmlIFilter(v6);
  else
    v7 = 0;
  if ( v7 )
  {
    v8 = (**(__int64 (__fastcall ***)(CHtmlIFilter *, const struct _GUID *, void **))v7)(v7, a3, a4);
    (*(void (__fastcall **)(CHtmlIFilter *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x18000e940  mov     [rsp+arg_0], rbx
0x18000e945  mov     [rsp+arg_8], rsi
0x18000e94a  push    rdi
0x18000e94b  sub     rsp, 20h
0x18000e94f  mov     rdi, r9
0x18000e952  mov     rsi, r8
0x18000e955  test    r9, r9
0x18000e958  jz      short loc_18000E9C9
0x18000e95a  mov     qword ptr [r9], 0
0x18000e961  test    rdx, rdx
0x18000e964  jnz     short loc_18000E9DB
0x18000e966  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e96d  mov     ecx, 15D8h; unsigned __int64
0x18000e972  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e977  mov     [rsp+28h+arg_18], rax
0x18000e97c  test    rax, rax
0x18000e97f  jz      short loc_18000E9D0
0x18000e981  mov     rcx, rax; this
0x18000e984  call    ??0CHtmlIFilter@@QEAA@XZ; CHtmlIFilter::CHtmlIFilter(void)
0x18000e989  mov     rbx, rax
0x18000e98c  test    rbx, rbx
0x18000e98f  jz      short loc_18000E9D4
0x18000e991  mov     rax, [rbx]
0x18000e994  mov     r8, rdi
0x18000e997  mov     rdx, rsi
0x18000e99a  mov     rcx, rbx
0x18000e99d  mov     rax, [rax]
0x18000e9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a5  mov     edi, eax
0x18000e9a7  mov     rax, [rbx]
0x18000e9aa  mov     rcx, rbx
0x18000e9ad  mov     rax, [rax+10h]
0x18000e9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b6  nop
0x18000e9b7  mov     eax, edi
0x18000e9b9  mov     rbx, [rsp+28h+arg_0]
0x18000e9be  mov     rsi, [rsp+28h+arg_8]
0x18000e9c3  add     rsp, 20h
0x18000e9c7  pop     rdi
0x18000e9c8  retn
0x18000e9c9  mov     eax, 80004003h
0x18000e9ce  jmp     short loc_18000E9B9
0x18000e9d0  xor     ebx, ebx
0x18000e9d2  jmp     short loc_18000E98C
0x18000e9d4  mov     edi, 8007000Eh
0x18000e9d9  jmp     short loc_18000E9B7
0x18000e9db  mov     eax, 80040110h
0x18000e9e0  jmp     short loc_18000E9B9
0x18000e9e2  mov     edi, dword ptr [rsp+28h+arg_18]
0x18000e9e6  jmp     short loc_18000E9B7
```
