# DestroyCachedProviderArray

- ea: `0x14000aaac`
- end: `0x14000aaf2`
- name: `DestroyCachedProviderArray`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ab4c`

## callees

- `0x14000aaac`
- `0x14000aaf8`

## pseudocode

```c
void __fastcall DestroyCachedProviderArray(__int64 a1, unsigned int *a2)
{
  unsigned int i; // edi

  for ( i = 0; i < *a2; ++i )
    DestroyCachedSslProv((struct CACHED_SSL_PROVIDER *)(a1 + 16LL * i));
  *a2 = 0;
}

```

## disassembly

```asm
0x14000aaac  mov     [rsp+arg_0], rbx
0x14000aab1  mov     [rsp+arg_8], rsi
0x14000aab6  push    rdi
0x14000aab7  sub     rsp, 20h
0x14000aabb  xor     edi, edi
0x14000aabd  mov     rbx, rdx
0x14000aac0  mov     rsi, rcx
0x14000aac3  cmp     [rdx], edi
0x14000aac5  jbe     short loc_14000AADB
0x14000aac7  mov     ecx, edi
0x14000aac9  shl     rcx, 4
0x14000aacd  add     rcx, rsi; struct CACHED_SSL_PROVIDER *
0x14000aad0  call    ?DestroyCachedSslProv@@YAXPEAUCACHED_SSL_PROVIDER@@@Z; DestroyCachedSslProv(CACHED_SSL_PROVIDER *)
0x14000aad5  inc     edi
0x14000aad7  cmp     edi, [rbx]
0x14000aad9  jb      short loc_14000AAC7
0x14000aadb  mov     rsi, [rsp+28h+arg_8]
0x14000aae0  mov     dword ptr [rbx], 0
0x14000aae6  mov     rbx, [rsp+28h+arg_0]
0x14000aaeb  add     rsp, 20h
0x14000aaef  pop     rdi
0x14000aaf0  retn
```
