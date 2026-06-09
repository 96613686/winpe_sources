# EnumFlushCacheEntryCallback(_CRYPTNET_URL_CACHE_ENTRY const *,ulong,void *,void *)

- ea: `0x18000a500`
- end: `0x18000a5ce`
- name: `?EnumFlushCacheEntryCallback@@YAHPEBU_CRYPTNET_URL_CACHE_ENTRY@@KPEAX1@Z`
- size: `206`
- prototype: `__int64 __fastcall(const struct _CRYPTNET_URL_CACHE_ENTRY *, __int64, void *, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004ac0`
- `0x18000a500`
- `0x18000a5e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a58b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a58b`

## pseudocode

```c
__int64 __fastcall EnumFlushCacheEntryCallback(
        const struct _CRYPTNET_URL_CACHE_ENTRY *a1,
        __int64 a2,
        void *a3,
        char *a4)
{
  __int64 v6; // rbx
  unsigned int v7; // esi
  __int64 v8; // rbx
  FILETIME FileTime1; // [rsp+20h] [rbp-28h] BYREF

  if ( !a4 || !a1 )
    return 0;
  v6 = *((_QWORD *)a1 + 8);
  if ( v6 && *(_DWORD *)v6 >= 0x10u )
  {
    v7 = *(_DWORD *)(v6 + 4);
    if ( !v7 )
      v7 = dword_180020274;
    if ( v7 != -1 )
    {
      v8 = *(_QWORD *)(v6 + 8);
      FileTime1 = 0;
      if ( (unsigned int)I_CryptIsResetBackCurrentFileTime(a4 + 8, 172800, (char *)a1 + 8) )
        v8 = 0;
      FileTime1 = (FILETIME)(v8 + 10000000LL * v7);
      if ( CompareFileTime(&FileTime1, (const FILETIME *)a4 + 1) <= 0 )
        AddFlushCacheEntry(a1, (struct _CUCS_ENUM_URL_CACHE_ARG *)a4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000a500  mov     [rsp+arg_0], rbx
0x18000a505  mov     [rsp+arg_8], rbp
0x18000a50a  push    rsi
0x18000a50b  push    rdi
0x18000a50c  push    r14
0x18000a50e  sub     rsp, 30h
0x18000a512  mov     rbp, r9
0x18000a515  mov     rdi, rcx
0x18000a518  test    r9, r9
0x18000a51b  jz      loc_18000A5CA
0x18000a521  test    rcx, rcx
0x18000a524  jz      loc_18000A5CA
0x18000a52a  mov     rbx, [rcx+40h]
0x18000a52e  test    rbx, rbx
0x18000a531  jz      short loc_18000A595
0x18000a533  cmp     dword ptr [rbx], 10h
0x18000a536  jb      short loc_18000A595
0x18000a538  mov     esi, [rbx+4]
0x18000a53b  test    esi, esi
0x18000a53d  cmovz   esi, cs:dword_180020274
0x18000a544  cmp     esi, 0FFFFFFFFh
0x18000a547  jz      short loc_18000A595
0x18000a549  mov     rbx, [rbx+8]
0x18000a54d  lea     r8, [rcx+8]
0x18000a551  lea     rcx, [r9+8]
0x18000a555  mov     [rsp+48h+arg_18], rbx
0x18000a55a  mov     edx, 2A300h
0x18000a55f  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], 0
0x18000a568  call    I_CryptIsResetBackCurrentFileTime
0x18000a56d  test    eax, eax
0x18000a56f  jnz     short loc_18000A5BA
0x18000a571  mov     eax, esi
0x18000a573  lea     rdx, [rbp+8]; lpFileTime2
0x18000a577  imul    rcx, rax, 989680h
0x18000a57e  add     rcx, rbx
0x18000a581  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rcx
0x18000a586  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x18000a58b  call    cs:__imp_CompareFileTime
0x18000a591  test    eax, eax
0x18000a593  jle     short loc_18000A5AD
0x18000a595  mov     eax, 1
0x18000a59a  mov     rbx, [rsp+48h+arg_0]
0x18000a59f  mov     rbp, [rsp+48h+arg_8]
0x18000a5a4  add     rsp, 30h
0x18000a5a8  pop     r14
0x18000a5aa  pop     rdi
0x18000a5ab  pop     rsi
0x18000a5ac  retn
0x18000a5ad  mov     rdx, rbp; struct _CUCS_ENUM_URL_CACHE_ARG *
0x18000a5b0  mov     rcx, rdi; struct _CRYPTNET_URL_CACHE_ENTRY *
0x18000a5b3  call    ?AddFlushCacheEntry@@YAXPEBU_CRYPTNET_URL_CACHE_ENTRY@@PEAU_CUCS_ENUM_URL_CACHE_ARG@@@Z; AddFlushCacheEntry(_CRYPTNET_URL_CACHE_ENTRY const *,_CUCS_ENUM_URL_CACHE_ARG *)
0x18000a5b8  jmp     short loc_18000A595
0x18000a5ba  mov     [rsp+48h+arg_18], 0
0x18000a5c3  mov     rbx, [rsp+48h+arg_18]
0x18000a5c8  jmp     short loc_18000A571
0x18000a5ca  xor     eax, eax
0x18000a5cc  jmp     short loc_18000A59A
```
