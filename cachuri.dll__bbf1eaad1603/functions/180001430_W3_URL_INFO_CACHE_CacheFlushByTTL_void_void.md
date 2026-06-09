# W3_URL_INFO_CACHE::CacheFlushByTTL(void *,void *)

- ea: `0x180001430`
- end: `0x180001456`
- name: `?CacheFlushByTTL@W3_URL_INFO_CACHE@@CAHPEAX0@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003010`

## pseudocode

```c
__int64 __fastcall W3_URL_INFO_CACHE::CacheFlushByTTL(__int64 *a1, void *a2)
{
  __int64 v2; // rax
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  v4 = 0;
  (*(void (__fastcall **)(__int64 *, unsigned int *))(v2 + 32))(a1, &v4);
  return v4;
}

```

## disassembly

```asm
0x180001430  sub     rsp, 28h
0x180001434  mov     rax, [rcx]
0x180001437  lea     rdx, [rsp+28h+arg_0]
0x18000143c  mov     [rsp+28h+arg_0], 0
0x180001444  mov     rax, [rax+20h]
0x180001448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144d  mov     eax, [rsp+28h+arg_0]
0x180001451  add     rsp, 28h
0x180001455  retn
```
