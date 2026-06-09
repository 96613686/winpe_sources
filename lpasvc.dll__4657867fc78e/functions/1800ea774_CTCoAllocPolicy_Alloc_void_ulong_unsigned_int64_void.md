# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800ea774`
- end: `0x1800ea80f`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ea70c`

## callees

- `0x18000ebf4`
- `0x1800ea774`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800ea7b7`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800ea7b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ea790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ea790`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  void *v7; // rbx
  size_t v8; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v8 = 0;
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v7);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(*a4, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ea774  mov     [rsp+arg_8], rbx
0x1800ea779  mov     [rsp+arg_10], rsi
0x1800ea77e  mov     [rsp+ppMalloc], rcx
0x1800ea783  push    rdi
0x1800ea784  sub     rsp, 20h
0x1800ea788  mov     rcx, r8; cb
0x1800ea78b  mov     rdi, r9
0x1800ea78e  mov     esi, edx
0x1800ea790  call    cs:__imp_CoTaskMemAlloc
0x1800ea796  mov     [rdi], rax
0x1800ea799  mov     rbx, rax
0x1800ea79c  test    rax, rax
0x1800ea79f  jz      short loc_1800EA7FA
0x1800ea7a1  mov     ecx, 1; dwMemContext
0x1800ea7a6  test    cl, sil
0x1800ea7a9  jz      short loc_1800EA7F6
0x1800ea7ab  xor     esi, esi
0x1800ea7ad  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800ea7b2  mov     [rsp+28h+ppMalloc], rsi
0x1800ea7b7  call    cs:__imp_CoGetMalloc
0x1800ea7bd  test    eax, eax
0x1800ea7bf  js      short loc_1800EA7E9
0x1800ea7c1  mov     rcx, [rsp+28h+ppMalloc]
0x1800ea7c6  mov     rdx, rbx
0x1800ea7c9  mov     rax, [rcx]
0x1800ea7cc  mov     rax, [rax+30h]
0x1800ea7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea7d5  mov     rcx, [rsp+28h+ppMalloc]
0x1800ea7da  mov     rsi, rax
0x1800ea7dd  mov     rdx, [rcx]
0x1800ea7e0  mov     rax, [rdx+10h]
0x1800ea7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea7e9  mov     rcx, [rdi]; void *
0x1800ea7ec  mov     r8, rsi; Size
0x1800ea7ef  xor     edx, edx; Val
0x1800ea7f1  call    memset_0
0x1800ea7f6  xor     eax, eax
0x1800ea7f8  jmp     short loc_1800EA7FF
0x1800ea7fa  mov     eax, 8007000Eh
0x1800ea7ff  mov     rbx, [rsp+28h+arg_8]
0x1800ea804  mov     rsi, [rsp+28h+arg_10]
0x1800ea809  add     rsp, 20h
0x1800ea80d  pop     rdi
0x1800ea80e  retn
```
