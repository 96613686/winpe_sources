# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18001af24`
- end: `0x18001afbf`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `155`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a2b0`
- `0x18001b530`

## callees

- `0x1800125c4`
- `0x18001af24`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001af40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001af40`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001af67`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001af67`

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
0x18001af24  mov     [rsp+arg_8], rbx
0x18001af29  mov     [rsp+arg_10], rsi
0x18001af2e  mov     [rsp+ppMalloc], rcx
0x18001af33  push    rdi
0x18001af34  sub     rsp, 20h
0x18001af38  mov     rcx, r8; cb
0x18001af3b  mov     rdi, r9
0x18001af3e  mov     esi, edx
0x18001af40  call    cs:__imp_CoTaskMemAlloc
0x18001af46  mov     [rdi], rax
0x18001af49  mov     rbx, rax
0x18001af4c  test    rax, rax
0x18001af4f  jz      short loc_18001AFAA
0x18001af51  mov     ecx, 1; dwMemContext
0x18001af56  test    cl, sil
0x18001af59  jz      short loc_18001AFA6
0x18001af5b  xor     esi, esi
0x18001af5d  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18001af62  mov     [rsp+28h+ppMalloc], rsi
0x18001af67  call    cs:__imp_CoGetMalloc
0x18001af6d  test    eax, eax
0x18001af6f  js      short loc_18001AF99
0x18001af71  mov     rcx, [rsp+28h+ppMalloc]
0x18001af76  mov     rdx, rbx
0x18001af79  mov     rax, [rcx]
0x18001af7c  mov     rax, [rax+30h]
0x18001af80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af85  mov     rcx, [rsp+28h+ppMalloc]
0x18001af8a  mov     rsi, rax
0x18001af8d  mov     rdx, [rcx]
0x18001af90  mov     rax, [rdx+10h]
0x18001af94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af99  mov     rcx, [rdi]; void *
0x18001af9c  mov     r8, rsi; Size
0x18001af9f  xor     edx, edx; Val
0x18001afa1  call    memset_0
0x18001afa6  xor     eax, eax
0x18001afa8  jmp     short loc_18001AFAF
0x18001afaa  mov     eax, 8007000Eh
0x18001afaf  mov     rbx, [rsp+28h+arg_8]
0x18001afb4  mov     rsi, [rsp+28h+arg_10]
0x18001afb9  add     rsp, 20h
0x18001afbd  pop     rdi
0x18001afbe  retn
```
