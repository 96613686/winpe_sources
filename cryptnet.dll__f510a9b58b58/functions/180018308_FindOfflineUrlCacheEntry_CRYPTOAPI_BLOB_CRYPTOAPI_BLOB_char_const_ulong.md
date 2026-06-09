# FindOfflineUrlCacheEntry(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,char const *,ulong)

- ea: `0x180018308`
- end: `0x1800183a0`
- name: `?FindOfflineUrlCacheEntry@@YAPEAU_OFFLINE_URL_CACHE_ENTRY@@PEAU_CRYPTOAPI_BLOB@@0PEBDK@Z`
- size: `152`
- prototype: `struct _OFFLINE_URL_CACHE_ENTRY *__fastcall(struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *, const char *, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017ed0`
- `0x180017f70`
- `0x180020140`

## callees

- `0x180018308`
- `0x180026546`

## pseudocode

```c
struct _OFFLINE_URL_CACHE_ENTRY *__fastcall FindOfflineUrlCacheEntry(
        struct _CRYPTOAPI_BLOB *a1,
        struct _CRYPTOAPI_BLOB *a2,
        const char *a3,
        char a4)
{
  size_t cbData; // rdi
  BYTE *pbData; // r14
  int v6; // eax
  size_t v7; // rsi
  BYTE *v8; // r15
  struct _OFFLINE_URL_CACHE_ENTRY *v9; // rbx
  int v10; // ebp

  cbData = a1->cbData;
  pbData = a1->pbData;
  v6 = 0x10000;
  v7 = a2->cbData;
  if ( (unsigned int)a3 <= 0xFFFF )
    v6 = (int)a3;
  v8 = a2->pbData;
  v9 = pOfflineUrlCacheHead;
  v10 = v6 | 0x20000;
  if ( (a4 & 4) == 0 )
    v10 = v6;
  while ( v9 )
  {
    if ( *((_DWORD *)v9 + 8) == v10
      && *(_DWORD *)v9 == (_DWORD)cbData
      && *((_DWORD *)v9 + 4) == (_DWORD)v7
      && (!(_DWORD)v7 || !memcmp_0(*((const void **)v9 + 3), v8, v7))
      && (!(_DWORD)cbData || !memcmp_0(*((const void **)v9 + 1), pbData, cbData)) )
    {
      return v9;
    }
    v9 = (struct _OFFLINE_URL_CACHE_ENTRY *)*((_QWORD *)v9 + 6);
  }
  return 0;
}

```

## disassembly

```asm
0x180018308  push    rbx
0x18001830a  push    rbp
0x18001830b  push    rsi
0x18001830c  push    rdi
0x18001830d  push    r14
0x18001830f  push    r15
0x180018311  sub     rsp, 28h
0x180018315  mov     edi, [rcx]
0x180018317  cmp     r8d, 0FFFFh
0x18001831e  mov     r14, [rcx+8]
0x180018322  mov     eax, 10000h
0x180018327  mov     esi, [rdx]
0x180018329  cmovbe  eax, r8d
0x18001832d  mov     r15, [rdx+8]
0x180018331  mov     ebp, eax
0x180018333  mov     rbx, cs:?pOfflineUrlCacheHead@@3PEAU_OFFLINE_URL_CACHE_ENTRY@@EA; _OFFLINE_URL_CACHE_ENTRY * pOfflineUrlCacheHead
0x18001833a  bts     ebp, 11h
0x18001833e  test    r9b, 4
0x180018342  cmovz   ebp, eax
0x180018345  test    rbx, rbx
0x180018348  jz      short loc_180018391
0x18001834a  cmp     [rbx+20h], ebp
0x18001834d  jnz     short loc_180018353
0x18001834f  cmp     [rbx], edi
0x180018351  jz      short loc_180018359
0x180018353  mov     rbx, [rbx+30h]
0x180018357  jmp     short loc_180018345
0x180018359  cmp     [rbx+10h], esi
0x18001835c  jnz     short loc_180018353
0x18001835e  test    esi, esi
0x180018360  jz      short loc_180018375
0x180018362  mov     rcx, [rbx+18h]; Buf1
0x180018366  mov     r8, rsi; Size
0x180018369  mov     rdx, r15; Buf2
0x18001836c  call    memcmp_0
0x180018371  test    eax, eax
0x180018373  jnz     short loc_180018353
0x180018375  test    edi, edi
0x180018377  jz      short loc_18001838C
0x180018379  mov     rcx, [rbx+8]; Buf1
0x18001837d  mov     r8, rdi; Size
0x180018380  mov     rdx, r14; Buf2
0x180018383  call    memcmp_0
0x180018388  test    eax, eax
0x18001838a  jnz     short loc_180018353
0x18001838c  mov     rax, rbx
0x18001838f  jmp     short loc_180018393
0x180018391  xor     eax, eax
0x180018393  add     rsp, 28h
0x180018397  pop     r15
0x180018399  pop     r14
0x18001839b  pop     rdi
0x18001839c  pop     rsi
0x18001839d  pop     rbp
0x18001839e  pop     rbx
0x18001839f  retn
```
