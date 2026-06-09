# CreateAndAddOfflineUrlCacheEntry(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,char const *,ulong)

- ea: `0x180018188`
- end: `0x18001828a`
- name: `?CreateAndAddOfflineUrlCacheEntry@@YAPEAU_OFFLINE_URL_CACHE_ENTRY@@PEAU_CRYPTOAPI_BLOB@@0PEBDK@Z`
- size: `258`
- prototype: `struct _OFFLINE_URL_CACHE_ENTRY *__fastcall(struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *, const char *, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017f70`
- `0x18001802c`

## callees

- `0x180007c00`
- `0x180018188`
- `0x180026552`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018280`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018280`

## pseudocode

```c
struct _OFFLINE_URL_CACHE_ENTRY *__fastcall CreateAndAddOfflineUrlCacheEntry(
        struct _CRYPTOAPI_BLOB *a1,
        struct _CRYPTOAPI_BLOB *a2,
        const char *a3,
        char a4)
{
  DWORD v5; // r10d
  unsigned int v6; // r12d
  DWORD v9; // edx
  char *v10; // rax
  char *v11; // rdi
  DWORD cbData; // eax
  char *v13; // rsi
  BYTE *pbData; // rdx
  __int64 v15; // rbx
  DWORD v16; // eax
  int v17; // ecx
  int v18; // eax
  struct _OFFLINE_URL_CACHE_ENTRY *v19; // rax
  DWORD v21; // ecx
  BYTE *v22; // rdx
  size_t v23; // r8

  v5 = a1->cbData + 64;
  v6 = (unsigned int)a3;
  if ( a1->cbData >= 0xFFFFFFC0 || (v9 = v5 + a2->cbData, v9 < v5) )
  {
    v21 = 534;
    goto LABEL_17;
  }
  v10 = (char *)operator new(v9);
  v11 = v10;
  if ( !v10 )
  {
    v21 = -2147024882;
LABEL_17:
    SetLastError(v21);
    return 0;
  }
  memset_0(v10, 0, 0x40u);
  cbData = a1->cbData;
  v13 = v11 + 64;
  if ( a1->cbData )
  {
    pbData = a1->pbData;
    *((_QWORD *)v11 + 1) = v13;
    *(_DWORD *)v11 = cbData;
    v15 = cbData;
    memcpy_0(v11 + 64, pbData, cbData);
    v13 += v15;
  }
  v16 = a2->cbData;
  if ( a2->cbData )
  {
    v22 = a2->pbData;
    v23 = a2->cbData;
    *((_QWORD *)v11 + 3) = v13;
    *((_DWORD *)v11 + 4) = v16;
    memcpy_0(v13, v22, v23);
  }
  v17 = 0x10000;
  if ( v6 <= 0xFFFF )
    v17 = v6;
  v18 = v17 | 0x20000;
  if ( (a4 & 4) == 0 )
    v18 = v17;
  *((_DWORD *)v11 + 8) = v18;
  v19 = pOfflineUrlCacheHead;
  if ( pOfflineUrlCacheHead )
  {
    *((_QWORD *)pOfflineUrlCacheHead + 7) = v11;
    *((_QWORD *)v11 + 6) = v19;
  }
  pOfflineUrlCacheHead = (struct _OFFLINE_URL_CACHE_ENTRY *)v11;
  return (struct _OFFLINE_URL_CACHE_ENTRY *)v11;
}

```

## disassembly

```asm
0x180018188  push    rbx
0x18001818a  push    rbp
0x18001818b  push    rsi
0x18001818c  push    rdi
0x18001818d  push    r12
0x18001818f  push    r14
0x180018191  push    r15
0x180018193  sub     rsp, 20h
0x180018197  mov     r10d, [rcx]
0x18001819a  mov     ebp, r9d
0x18001819d  add     r10d, 40h ; '@'
0x1800181a1  mov     r12, r8
0x1800181a4  mov     r14, rdx
0x1800181a7  mov     r15, rcx
0x1800181aa  cmp     r10d, 40h ; '@'
0x1800181ae  jb      loc_18001827B
0x1800181b4  mov     edx, [rdx]
0x1800181b6  add     edx, r10d
0x1800181b9  cmp     edx, r10d
0x1800181bc  jb      loc_18001827B
0x1800181c2  mov     ecx, edx; uBytes
0x1800181c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800181c9  mov     rdi, rax
0x1800181cc  test    rax, rax
0x1800181cf  jz      loc_18001825C
0x1800181d5  xor     edx, edx; Val
0x1800181d7  mov     rcx, rax; void *
0x1800181da  lea     r8d, [rdx+40h]; Size
0x1800181de  call    memset_0
0x1800181e3  mov     eax, [r15]
0x1800181e6  lea     rsi, [rdi+40h]
0x1800181ea  test    eax, eax
0x1800181ec  jz      short loc_180018208
0x1800181ee  mov     rdx, [r15+8]; Src
0x1800181f2  mov     r8d, eax; Size
0x1800181f5  mov     rcx, rsi; void *
0x1800181f8  mov     [rdi+8], rsi
0x1800181fc  mov     [rdi], eax
0x1800181fe  mov     ebx, eax
0x180018200  call    memcpy_0
0x180018205  add     rsi, rbx
0x180018208  mov     eax, [r14]
0x18001820b  test    eax, eax
0x18001820d  jnz     short loc_180018263
0x18001820f  cmp     r12d, 0FFFFh
0x180018216  mov     ecx, 10000h
0x18001821b  cmovbe  ecx, r12d
0x18001821f  mov     eax, ecx
0x180018221  bts     eax, 11h
0x180018225  and     bpl, 4
0x180018229  cmovz   eax, ecx
0x18001822c  mov     [rdi+20h], eax
0x18001822f  mov     rax, cs:?pOfflineUrlCacheHead@@3PEAU_OFFLINE_URL_CACHE_ENTRY@@EA; _OFFLINE_URL_CACHE_ENTRY * pOfflineUrlCacheHead
0x180018236  test    rax, rax
0x180018239  jz      short loc_180018243
0x18001823b  mov     [rax+38h], rdi
0x18001823f  mov     [rdi+30h], rax
0x180018243  mov     cs:?pOfflineUrlCacheHead@@3PEAU_OFFLINE_URL_CACHE_ENTRY@@EA, rdi; _OFFLINE_URL_CACHE_ENTRY * pOfflineUrlCacheHead
0x18001824a  mov     rax, rdi
0x18001824d  add     rsp, 20h
0x180018251  pop     r15
0x180018253  pop     r14
0x180018255  pop     r12
0x180018257  pop     rdi
0x180018258  pop     rsi
0x180018259  pop     rbp
0x18001825a  pop     rbx
0x18001825b  retn
0x18001825c  mov     ecx, 8007000Eh
0x180018261  jmp     short loc_180018280
0x180018263  mov     rdx, [r14+8]; Src
0x180018267  mov     r8, rax; Size
0x18001826a  mov     rcx, rsi; void *
0x18001826d  mov     [rdi+18h], rsi
0x180018271  mov     [rdi+10h], eax
0x180018274  call    memcpy_0
0x180018279  jmp     short loc_18001820F
0x18001827b  mov     ecx, 216h; dwErrCode
0x180018280  call    cs:__imp_SetLastError
0x180018286  xor     eax, eax
0x180018288  jmp     short loc_18001824D
```
