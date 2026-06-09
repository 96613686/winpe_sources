# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180004bb0`
- end: `0x180004c42`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `146`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bde4`

## callees

- `0x180002b60`
- `0x180004bb0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004bca`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180004bea`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180004bea`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax
  void *v6; // rbx
  size_t v7; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v6);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(*a4, 0, v7);
  return 0;
}

```

## disassembly

```asm
0x180004bb0  mov     [rsp+arg_8], rbx
0x180004bb5  mov     [rsp+arg_10], rsi
0x180004bba  mov     [rsp+ppMalloc], rcx
0x180004bbf  push    rdi
0x180004bc0  sub     rsp, 20h
0x180004bc4  mov     rcx, r8; cb
0x180004bc7  mov     rdi, r9
0x180004bca  call    cs:__imp_CoTaskMemAlloc
0x180004bd0  mov     [rdi], rax
0x180004bd3  mov     rbx, rax
0x180004bd6  test    rax, rax
0x180004bd9  jz      short loc_180004C2D
0x180004bdb  xor     esi, esi
0x180004bdd  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180004be2  mov     [rsp+28h+ppMalloc], rsi
0x180004be7  lea     ecx, [rsi+1]; dwMemContext
0x180004bea  call    cs:__imp_CoGetMalloc
0x180004bf0  test    eax, eax
0x180004bf2  js      short loc_180004C1C
0x180004bf4  mov     rcx, [rsp+28h+ppMalloc]
0x180004bf9  mov     rdx, rbx
0x180004bfc  mov     rax, [rcx]
0x180004bff  mov     rax, [rax+30h]
0x180004c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c08  mov     rcx, [rsp+28h+ppMalloc]
0x180004c0d  mov     rsi, rax
0x180004c10  mov     rdx, [rcx]
0x180004c13  mov     rax, [rdx+10h]
0x180004c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1c  mov     rcx, [rdi]; void *
0x180004c1f  mov     r8, rsi; Size
0x180004c22  xor     edx, edx; Val
0x180004c24  call    memset_0
0x180004c29  xor     eax, eax
0x180004c2b  jmp     short loc_180004C32
0x180004c2d  mov     eax, 8007000Eh
0x180004c32  mov     rbx, [rsp+28h+arg_8]
0x180004c37  mov     rsi, [rsp+28h+arg_10]
0x180004c3c  add     rsp, 20h
0x180004c40  pop     rdi
0x180004c41  retn
```
