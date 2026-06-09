# CacheClientSideSslProv(CACHED_SSL_PROVIDER *)

- ea: `0x14000a970`
- end: `0x14000a9dd`
- name: `?CacheClientSideSslProv@@YAJPEAUCACHED_SSL_PROVIDER@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct CACHED_SSL_PROVIDER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140002510`

## callees

- `0x14000a970`

## pseudocode

```c
__int64 __fastcall CacheClientSideSslProv(struct CACHED_SSL_PROVIDER *a1)
{
  _QWORD *v1; // r10
  unsigned int v2; // eax
  int *v3; // r9
  unsigned int v4; // r8d

  v1 = &g_rgCachedPagedSslProvs;
  if ( dword_140019528 )
  {
    v2 = g_cCachedPagedSslProvs;
    v3 = (int *)&g_cCachedPagedSslProvs;
  }
  else
  {
    v1 = &unk_140019100;
    v2 = dword_1400190F8;
    v3 = &dword_1400190F8;
  }
  if ( v2 < 0x20 )
  {
    v4 = 0;
    v1[2 * v2] = *(_QWORD *)a1;
    v1[2 * (unsigned int)(*v3)++ + 1] = *((_QWORD *)a1 + 1);
  }
  else
  {
    return (unsigned int)-2146893052;
  }
  return v4;
}

```

## disassembly

```asm
0x14000a970  mov     eax, cs:dword_140019528
0x14000a976  lea     r10, ?g_rgCachedPagedSslProvs@@3PAUCACHED_SSL_PROVIDER@@A; CACHED_SSL_PROVIDER near * g_rgCachedPagedSslProvs
0x14000a97d  test    eax, eax
0x14000a97f  mov     r11, rcx
0x14000a982  lea     rcx, unk_140019100
0x14000a989  cmovz   r10, rcx
0x14000a98d  jz      short loc_14000A99E
0x14000a98f  mov     eax, cs:?g_cCachedPagedSslProvs@@3KA; ulong g_cCachedPagedSslProvs
0x14000a995  lea     r9, ?g_cCachedPagedSslProvs@@3KA; ulong g_cCachedPagedSslProvs
0x14000a99c  jmp     short loc_14000A9AB
0x14000a99e  mov     eax, cs:dword_1400190F8
0x14000a9a4  lea     r9, dword_1400190F8
0x14000a9ab  cmp     eax, 20h ; ' '
0x14000a9ae  jb      short loc_14000A9B8
0x14000a9b0  mov     r8d, 80090304h
0x14000a9b6  jmp     short loc_14000A9D9
0x14000a9b8  mov     rcx, [r11]
0x14000a9bb  xor     r8d, r8d
0x14000a9be  mov     edx, eax
0x14000a9c0  add     rdx, rdx
0x14000a9c3  mov     [r10+rdx*8], rcx
0x14000a9c7  mov     edx, [r9]
0x14000a9ca  mov     rcx, [r11+8]
0x14000a9ce  add     rdx, rdx
0x14000a9d1  mov     [r10+rdx*8+8], rcx
0x14000a9d6  inc     dword ptr [r9]
0x14000a9d9  mov     eax, r8d
0x14000a9dc  retn
```
