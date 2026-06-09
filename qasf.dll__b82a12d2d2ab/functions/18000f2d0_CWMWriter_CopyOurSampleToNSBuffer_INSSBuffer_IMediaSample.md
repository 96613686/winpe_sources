# CWMWriter::CopyOurSampleToNSBuffer(INSSBuffer *,IMediaSample *)

- ea: `0x18000f2d0`
- end: `0x18000f3b5`
- name: `?CopyOurSampleToNSBuffer@CWMWriter@@IEAAJPEAUINSSBuffer@@PEAUIMediaSample@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct INSSBuffer *, struct IMediaSample *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010dfc`

## callees

- `0x180001460`
- `0x18000f2d0`
- `0x18001e5c5`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::CopyOurSampleToNSBuffer(CWMWriter *this, struct INSSBuffer *a2, struct IMediaSample *a3)
{
  struct IMediaSampleVtbl *lpVtbl; // rax
  int v6; // eax
  struct INSSBufferVtbl *v7; // rcx
  size_t v8; // rbp
  int v9; // edi
  void *Src; // [rsp+20h] [rbp-38h] BYREF
  void *v12; // [rsp+28h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  lpVtbl = a3->lpVtbl;
  Src = 0;
  v12 = 0;
  v6 = ((__int64 (__fastcall *)(struct IMediaSample *))lpVtbl->GetActualDataLength)(a3);
  v7 = a2->lpVtbl;
  v8 = v6;
  v13 = 0;
  v9 = ((__int64 (__fastcall *)(struct INSSBuffer *, void **, unsigned int *))v7->GetBufferAndLength)(a2, &v12, &v13);
  if ( v9 >= 0 )
  {
    if ( v13 >= (unsigned int)v8 )
    {
      ((void (__fastcall *)(struct IMediaSample *, void **))a3->lpVtbl->GetPointer)(a3, &Src);
      memcpy_0(v12, Src, v8);
      ((void (__fastcall *)(struct INSSBuffer *, _QWORD))a2->lpVtbl->SetLength)(a2, (unsigned int)v8);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f2d0  mov     [rsp+arg_0], rbx
0x18000f2d5  push    rbp
0x18000f2d6  push    rsi
0x18000f2d7  push    rdi
0x18000f2d8  sub     rsp, 40h
0x18000f2dc  mov     rax, cs:__security_cookie
0x18000f2e3  xor     rax, rsp
0x18000f2e6  mov     [rsp+58h+var_20], rax
0x18000f2eb  mov     rbx, r8
0x18000f2ee  mov     rsi, rdx
0x18000f2f1  test    rdx, rdx
0x18000f2f4  jz      loc_18000F396
0x18000f2fa  test    rbx, rbx
0x18000f2fd  jz      loc_18000F396
0x18000f303  mov     rax, [r8]
0x18000f306  mov     rcx, rbx
0x18000f309  mov     [rsp+58h+Src], 0
0x18000f312  mov     [rsp+58h+var_30], 0
0x18000f31b  mov     rax, [rax+58h]
0x18000f31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f324  mov     rcx, [rsi]
0x18000f327  lea     r8, [rsp+58h+var_28]
0x18000f32c  movsxd  rbp, eax
0x18000f32f  lea     rdx, [rsp+58h+var_30]
0x18000f334  mov     [rsp+58h+var_28], 0
0x18000f33c  mov     rax, [rcx+38h]
0x18000f340  mov     rcx, rsi
0x18000f343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f348  mov     edi, eax
0x18000f34a  test    eax, eax
0x18000f34c  js      short loc_18000F392
0x18000f34e  cmp     [rsp+58h+var_28], ebp
0x18000f352  jnb     short loc_18000F35B
0x18000f354  mov     edi, 8000FFFFh
0x18000f359  jmp     short loc_18000F392
0x18000f35b  mov     rax, [rbx]
0x18000f35e  lea     rdx, [rsp+58h+Src]
0x18000f363  mov     rcx, rbx
0x18000f366  mov     rax, [rax+18h]
0x18000f36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f36f  mov     rdx, [rsp+58h+Src]; Src
0x18000f374  mov     r8, rbp; Size
0x18000f377  mov     rcx, [rsp+58h+var_30]; void *
0x18000f37c  call    memcpy_0
0x18000f381  mov     rax, [rsi]
0x18000f384  mov     edx, ebp
0x18000f386  mov     rcx, rsi
0x18000f389  mov     rax, [rax+20h]
0x18000f38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f392  mov     eax, edi
0x18000f394  jmp     short loc_18000F39B
0x18000f396  mov     eax, 80004003h
0x18000f39b  mov     rcx, [rsp+58h+var_20]
0x18000f3a0  xor     rcx, rsp; StackCookie
0x18000f3a3  call    __security_check_cookie
0x18000f3a8  mov     rbx, [rsp+58h+arg_0]
0x18000f3ad  add     rsp, 40h
0x18000f3b1  pop     rdi
0x18000f3b2  pop     rsi
0x18000f3b3  pop     rbp
0x18000f3b4  retn
```
