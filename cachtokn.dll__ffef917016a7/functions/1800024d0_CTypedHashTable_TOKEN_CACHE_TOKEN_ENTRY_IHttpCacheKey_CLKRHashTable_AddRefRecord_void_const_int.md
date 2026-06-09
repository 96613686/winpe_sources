# CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x1800024d0`
- end: `0x18000250d`
- name: `?_AddRefRecord@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CAXPEBXH@Z`
- size: `61`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024d0`
- `0x180003010`

## pseudocode

```c
void __fastcall CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_AddRefRecord(
        __int64 a1,
        int a2)
{
  if ( a2 == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  else if ( a2 == -1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
}

```

## disassembly

```asm
0x1800024d0  push    rbx
0x1800024d2  sub     rsp, 20h
0x1800024d6  mov     rbx, rcx
0x1800024d9  cmp     edx, 1
0x1800024dc  jnz     short loc_1800024E7
0x1800024de  mov     rax, [rcx]
0x1800024e1  mov     rax, [rax+8]
0x1800024e5  jmp     short loc_180002502
0x1800024e7  cmp     edx, 0FFFFFFFFh
0x1800024ea  jnz     short loc_180002507
0x1800024ec  mov     rax, [rcx]
0x1800024ef  mov     rax, [rax+28h]
0x1800024f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f8  mov     rax, [rbx]
0x1800024fb  mov     rcx, rbx
0x1800024fe  mov     rax, [rax+10h]
0x180002502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002507  add     rsp, 20h
0x18000250b  pop     rbx
0x18000250c  retn
```
