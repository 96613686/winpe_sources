# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18000daa0`
- end: `0x18000db3b`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d0bc`
- `0x18005bd1c`

## callees

- `0x1800036e4`
- `0x18000daa0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000dae3`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000dae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dabc`

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
0x18000daa0  mov     [rsp+arg_8], rbx
0x18000daa5  mov     [rsp+arg_10], rsi
0x18000daaa  mov     [rsp+ppMalloc], rcx
0x18000daaf  push    rdi
0x18000dab0  sub     rsp, 20h
0x18000dab4  mov     rcx, r8; cb
0x18000dab7  mov     rdi, r9
0x18000daba  mov     esi, edx
0x18000dabc  call    cs:__imp_CoTaskMemAlloc
0x18000dac2  mov     [rdi], rax
0x18000dac5  mov     rbx, rax
0x18000dac8  test    rax, rax
0x18000dacb  jz      short loc_18000DB26
0x18000dacd  mov     ecx, 1; dwMemContext
0x18000dad2  test    cl, sil
0x18000dad5  jz      short loc_18000DB22
0x18000dad7  xor     esi, esi
0x18000dad9  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18000dade  mov     [rsp+28h+ppMalloc], rsi
0x18000dae3  call    cs:__imp_CoGetMalloc
0x18000dae9  test    eax, eax
0x18000daeb  js      short loc_18000DB15
0x18000daed  mov     rcx, [rsp+28h+ppMalloc]
0x18000daf2  mov     rdx, rbx
0x18000daf5  mov     rax, [rcx]
0x18000daf8  mov     rax, [rax+30h]
0x18000dafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db01  mov     rcx, [rsp+28h+ppMalloc]
0x18000db06  mov     rsi, rax
0x18000db09  mov     rdx, [rcx]
0x18000db0c  mov     rax, [rdx+10h]
0x18000db10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db15  mov     rcx, [rdi]; void *
0x18000db18  mov     r8, rsi; Size
0x18000db1b  xor     edx, edx; Val
0x18000db1d  call    memset_0
0x18000db22  xor     eax, eax
0x18000db24  jmp     short loc_18000DB2B
0x18000db26  mov     eax, 8007000Eh
0x18000db2b  mov     rbx, [rsp+28h+arg_8]
0x18000db30  mov     rsi, [rsp+28h+arg_10]
0x18000db35  add     rsp, 20h
0x18000db39  pop     rdi
0x18000db3a  retn
```
