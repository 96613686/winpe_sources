# CProviderImpersonation::Create(IDafPrivImpersonationToken *,CProviderImpersonation * *)

- ea: `0x140018f8c`
- end: `0x140018fea`
- name: `?Create@CProviderImpersonation@@SAJPEAUIDafPrivImpersonationToken@@PEAPEAV1@@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct IDafPrivImpersonationToken *, struct CProviderImpersonation **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140017470`
- `0x140017ff0`
- `0x140018880`

## callees

- `0x14000190c`
- `0x140018f8c`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall CProviderImpersonation::Create(
        struct IDafPrivImpersonationToken *a1,
        struct CProviderImpersonation **a2)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rax
  void (*v6)(void); // rax

  v4 = 0;
  try
  {
    v5 = operator new(0x18u);
    *(_QWORD *)v5 = &CProviderImpersonation::`vftable';
    v5[2] = 1;
    *((_QWORD *)v5 + 2) = a1;
    *a2 = (struct CProviderImpersonation *)v5;
    v6 = *(void (**)(void))(*(_QWORD *)a1 + 8LL);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  v5 = operator new(0x18u);
  *(_QWORD *)v5 = &CProviderImpersonation::`vftable';
}

```

## disassembly

```asm
0x140018f8c  mov     [rsp+arg_0], rbx
0x140018f91  mov     [rsp+arg_8], rsi
0x140018f96  push    rdi
0x140018f97  sub     rsp, 20h
0x140018f9b  mov     rsi, rdx
0x140018f9e  mov     rdi, rcx
0x140018fa1  xor     ebx, ebx
0x140018fa3  lea     ecx, [rbx+18h]; Size
0x140018fa6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018fab  lea     rcx, ??_7CProviderImpersonation@@6B@; const CProviderImpersonation::`vftable'
0x140018fb2  mov     [rax], rcx
0x140018fb5  mov     dword ptr [rax+8], 1
0x140018fbc  mov     [rax+10h], rdi
0x140018fc0  mov     [rsi], rax
0x140018fc3  mov     rax, [rdi]
0x140018fc6  mov     rcx, rdi
0x140018fc9  mov     rax, [rax+8]
0x140018fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018fd2  jmp     short loc_140018FD8
0x140018fd4  mov     ebx, [rsp+28h+arg_10]
0x140018fd8  mov     eax, ebx
0x140018fda  mov     rbx, [rsp+28h+arg_0]
0x140018fdf  mov     rsi, [rsp+28h+arg_8]
0x140018fe4  add     rsp, 20h
0x140018fe8  pop     rdi
0x140018fe9  retn
```
