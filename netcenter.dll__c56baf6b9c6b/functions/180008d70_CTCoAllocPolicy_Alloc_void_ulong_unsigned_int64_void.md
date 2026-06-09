# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180008d70`
- end: `0x180008e0b`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d750`
- `0x18000ea5c`
- `0x1800144f0`
- `0x180015a80`
- `0x1800189cc`

## callees

- `0x180002c2c`
- `0x180008d70`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180008db3`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180008db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d8c`

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
0x180008d70  mov     [rsp+arg_8], rbx
0x180008d75  mov     [rsp+arg_10], rsi
0x180008d7a  mov     [rsp+ppMalloc], rcx
0x180008d7f  push    rdi
0x180008d80  sub     rsp, 20h
0x180008d84  mov     rcx, r8; cb
0x180008d87  mov     rdi, r9
0x180008d8a  mov     esi, edx
0x180008d8c  call    cs:__imp_CoTaskMemAlloc
0x180008d92  mov     [rdi], rax
0x180008d95  mov     rbx, rax
0x180008d98  test    rax, rax
0x180008d9b  jz      short loc_180008DF6
0x180008d9d  mov     ecx, 1; dwMemContext
0x180008da2  test    cl, sil
0x180008da5  jz      short loc_180008DF2
0x180008da7  xor     esi, esi
0x180008da9  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180008dae  mov     [rsp+28h+ppMalloc], rsi
0x180008db3  call    cs:__imp_CoGetMalloc
0x180008db9  test    eax, eax
0x180008dbb  js      short loc_180008DE5
0x180008dbd  mov     rcx, [rsp+28h+ppMalloc]
0x180008dc2  mov     rdx, rbx
0x180008dc5  mov     rax, [rcx]
0x180008dc8  mov     rax, [rax+30h]
0x180008dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dd1  mov     rcx, [rsp+28h+ppMalloc]
0x180008dd6  mov     rsi, rax
0x180008dd9  mov     rdx, [rcx]
0x180008ddc  mov     rax, [rdx+10h]
0x180008de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de5  mov     rcx, [rdi]; void *
0x180008de8  mov     r8, rsi; Size
0x180008deb  xor     edx, edx; Val
0x180008ded  call    memset_0
0x180008df2  xor     eax, eax
0x180008df4  jmp     short loc_180008DFB
0x180008df6  mov     eax, 8007000Eh
0x180008dfb  mov     rbx, [rsp+28h+arg_8]
0x180008e00  mov     rsi, [rsp+28h+arg_10]
0x180008e05  add     rsp, 20h
0x180008e09  pop     rdi
0x180008e0a  retn
```
