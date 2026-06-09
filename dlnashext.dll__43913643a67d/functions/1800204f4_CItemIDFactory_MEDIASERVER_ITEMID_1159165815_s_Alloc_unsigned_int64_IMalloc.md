# CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_Alloc(unsigned __int64,IMalloc *)

- ea: `0x1800204f4`
- end: `0x180020572`
- name: `?s_Alloc@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@CAPEAUCHILDITEMID@1@_KPEAUIMalloc@@@Z`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003cbc`
- `0x180008780`

## callees

- `0x1800125c4`
- `0x1800204f4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020539`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_Alloc(__int64 a1, __int64 a2)
{
  __int16 v2; // si
  _WORD *v3; // rbx
  size_t v4; // rdi
  _WORD *v5; // rax

  v2 = a1;
  if ( a2 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 24LL))(a2, a1);
  v4 = a1 + 8;
  if ( (unsigned __int64)(a1 + 8) > 0x10001 )
    return 0;
  v5 = CoTaskMemAlloc(a1 + 8);
  v3 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, v4);
    v3[2] = v2;
    *v3 = v4 - 2;
  }
  return (__int64)v3;
}

```

## disassembly

```asm
0x1800204f4  mov     [rsp+arg_0], rbx
0x1800204f9  mov     [rsp+arg_8], rsi
0x1800204fe  push    rdi
0x1800204ff  sub     rsp, 20h
0x180020503  mov     r8, rdx
0x180020506  mov     rsi, rcx
0x180020509  test    rdx, rdx
0x18002050c  jz      short loc_180020525
0x18002050e  mov     rax, [rdx]
0x180020511  mov     rdx, rcx
0x180020514  mov     rcx, r8
0x180020517  mov     rax, [rax+18h]
0x18002051b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020520  mov     rbx, rax
0x180020523  jmp     short loc_18002055F
0x180020525  lea     rdi, [rcx+8]
0x180020529  cmp     rdi, 10001h
0x180020530  jbe     short loc_180020536
0x180020532  xor     ebx, ebx
0x180020534  jmp     short loc_18002055F
0x180020536  mov     rcx, rdi; cb
0x180020539  call    cs:__imp_CoTaskMemAlloc
0x18002053f  mov     rbx, rax
0x180020542  test    rax, rax
0x180020545  jz      short loc_18002055F
0x180020547  mov     r8, rdi; Size
0x18002054a  xor     edx, edx; Val
0x18002054c  mov     rcx, rax; void *
0x18002054f  call    memset_0
0x180020554  sub     di, 2
0x180020558  mov     [rbx+4], si
0x18002055c  mov     [rbx], di
0x18002055f  mov     rsi, [rsp+28h+arg_8]
0x180020564  mov     rax, rbx
0x180020567  mov     rbx, [rsp+28h+arg_0]
0x18002056c  add     rsp, 20h
0x180020570  pop     rdi
0x180020571  retn
```
