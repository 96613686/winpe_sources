# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18002d7f8`
- end: `0x18002d893`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d89c`

## callees

- `0x180002ef8`
- `0x18002d7f8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002d83b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002d83b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d814`

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
0x18002d7f8  mov     [rsp+arg_8], rbx
0x18002d7fd  mov     [rsp+arg_10], rsi
0x18002d802  mov     [rsp+ppMalloc], rcx
0x18002d807  push    rdi
0x18002d808  sub     rsp, 20h
0x18002d80c  mov     rcx, r8; cb
0x18002d80f  mov     rdi, r9
0x18002d812  mov     esi, edx
0x18002d814  call    cs:__imp_CoTaskMemAlloc
0x18002d81a  mov     [rdi], rax
0x18002d81d  mov     rbx, rax
0x18002d820  test    rax, rax
0x18002d823  jz      short loc_18002D87E
0x18002d825  mov     ecx, 1; dwMemContext
0x18002d82a  test    cl, sil
0x18002d82d  jz      short loc_18002D87A
0x18002d82f  xor     esi, esi
0x18002d831  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18002d836  mov     [rsp+28h+ppMalloc], rsi
0x18002d83b  call    cs:__imp_CoGetMalloc
0x18002d841  test    eax, eax
0x18002d843  js      short loc_18002D86D
0x18002d845  mov     rcx, [rsp+28h+ppMalloc]
0x18002d84a  mov     rdx, rbx
0x18002d84d  mov     rax, [rcx]
0x18002d850  mov     rax, [rax+30h]
0x18002d854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d859  mov     rcx, [rsp+28h+ppMalloc]
0x18002d85e  mov     rsi, rax
0x18002d861  mov     rdx, [rcx]
0x18002d864  mov     rax, [rdx+10h]
0x18002d868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d86d  mov     rcx, [rdi]; void *
0x18002d870  mov     r8, rsi; Size
0x18002d873  xor     edx, edx; Val
0x18002d875  call    memset_0
0x18002d87a  xor     eax, eax
0x18002d87c  jmp     short loc_18002D883
0x18002d87e  mov     eax, 8007000Eh
0x18002d883  mov     rbx, [rsp+28h+arg_8]
0x18002d888  mov     rsi, [rsp+28h+arg_10]
0x18002d88d  add     rsp, 20h
0x18002d891  pop     rdi
0x18002d892  retn
```
