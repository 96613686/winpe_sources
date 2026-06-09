# OUTPUT_ENTRY::Initialize(IHttpContext *,IHttpCachePolicy *)

- ea: `0x1800084bc`
- end: `0x180008525`
- name: `?Initialize@OUTPUT_ENTRY@@QEAAJPEAVIHttpContext@@PEAVIHttpCachePolicy@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(OUTPUT_ENTRY *this, struct IHttpContext *, struct IHttpCachePolicy *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004220`

## callees

- `0x18000338c`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall OUTPUT_ENTRY::Initialize(OUTPUT_ENTRY *this, struct IHttpContext *a2, struct IHttpCachePolicy *a3)
{
  char *v6; // rdi
  char *v7; // rbx
  char *v8; // rax

  v6 = (char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a3 + 64LL))(a3);
  v7 = (char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a3 + 48LL))(a3);
  v8 = (char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a3 + 32LL))(a3);
  return OUTPUT_KEY::Initialize((OUTPUT_ENTRY *)((char *)this + 8), a2, v8, v7, v6);
}

```

## disassembly

```asm
0x1800084bc  push    rbx
0x1800084be  push    rbp
0x1800084bf  push    rsi
0x1800084c0  push    rdi
0x1800084c1  push    r14
0x1800084c3  sub     rsp, 30h
0x1800084c7  mov     rax, [r8]
0x1800084ca  mov     rbp, rcx
0x1800084cd  mov     rcx, r8
0x1800084d0  mov     rsi, r8
0x1800084d3  mov     r14, rdx
0x1800084d6  mov     rax, [rax+40h]
0x1800084da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084df  mov     r9, [rsi]
0x1800084e2  mov     rdi, rax
0x1800084e5  mov     rcx, rsi
0x1800084e8  mov     rax, [r9+30h]
0x1800084ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084f1  mov     rcx, [rsi]
0x1800084f4  mov     rbx, rax
0x1800084f7  mov     rax, [rcx+20h]
0x1800084fb  mov     rcx, rsi
0x1800084fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008503  lea     rcx, [rbp+8]; this
0x180008507  mov     [rsp+58h+var_38], rdi; char *
0x18000850c  mov     r9, rbx; char *
0x18000850f  mov     r8, rax; char *
0x180008512  mov     rdx, r14; struct IHttpContext *
0x180008515  call    ?Initialize@OUTPUT_KEY@@QEAAJPEAVIHttpContext@@PEBD11@Z; OUTPUT_KEY::Initialize(IHttpContext *,char const *,char const *,char const *)
0x18000851a  add     rsp, 30h
0x18000851e  pop     r14
0x180008520  pop     rdi
0x180008521  pop     rsi
0x180008522  pop     rbp
0x180008523  pop     rbx
0x180008524  retn
```
