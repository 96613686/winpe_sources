# FlushCacheDir

- ea: `0x1800011f4`
- end: `0x18000127d`
- name: `FlushCacheDir`
- size: `137`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006aa0`

## callees

- `0x1800011f4`
- `0x1800025c8`
- `0x1800068b0`
- `0x180006db0`
- `0x180007370`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001219`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001219`

## string_xrefs

- `0x18000121f`: `\Microsoft\CryptnetFlushCache\`

## pseudocode

```c
void *__fastcall FlushCacheDir(__int64 a1, __int64 a2)
{
  void *result; // rax
  void *v4; // rbx
  __int128 v5; // [rsp+30h] [rbp-38h] BYREF
  __int128 v6; // [rsp+40h] [rbp-28h]
  __int128 v7; // [rsp+50h] [rbp-18h]

  v5 = 0;
  v6 = 0;
  v7 = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v5 + 1);
  result = (void *)I_CryptGetLowIntegrityUserPath(a2, L"\\Microsoft\\CryptnetFlushCache\\");
  v4 = result;
  if ( result )
  {
    I_UrlCacheEnum(result, (__int64)EnumFlushCacheEntryCallback);
    FlushUrlCacheEntries(v6, *((unsigned __int16 **const *)&v6 + 1), (unsigned __int16 **const)v7);
    return (void *)PkiFree(v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800011f4  mov     rax, rsp
0x1800011f7  mov     [rax+8], rbx
0x1800011fb  push    rdi
0x1800011fc  sub     rsp, 60h
0x180001200  xorps   xmm0, xmm0
0x180001203  mov     rbx, rcx
0x180001206  lea     rcx, [rax-30h]; lpSystemTimeAsFileTime
0x18000120a  mov     rdi, rdx
0x18000120d  movups  xmmword ptr [rax-38h], xmm0
0x180001211  movups  xmmword ptr [rax-28h], xmm0
0x180001215  movups  xmmword ptr [rax-18h], xmm0
0x180001219  call    cs:__imp_GetSystemTimeAsFileTime
0x18000121f  lea     rdx, aMicrosoftCrypt; "\\Microsoft\\CryptnetFlushCache\\"
0x180001226  mov     qword ptr [rsp+68h+var_38], rbx
0x18000122b  mov     rcx, rdi
0x18000122e  call    I_CryptGetLowIntegrityUserPath
0x180001233  mov     rbx, rax
0x180001236  test    rax, rax
0x180001239  jz      short loc_180001272
0x18000123b  lea     rax, ?EnumFlushCacheEntryCallback@@YAHPEBU_CRYPTNET_URL_CACHE_ENTRY@@KPEAX1@Z; EnumFlushCacheEntryCallback(_CRYPTNET_URL_CACHE_ENTRY const *,ulong,void *,void *)
0x180001242  xor     r8d, r8d
0x180001245  lea     r9, [rsp+68h+var_38]
0x18000124a  mov     [rsp+68h+var_48], rax; __int64
0x18000124f  mov     rcx, rbx; Src
0x180001252  call    I_UrlCacheEnum
0x180001257  mov     r8, qword ptr [rsp+68h+var_18]; unsigned __int16 **
0x18000125c  mov     rdx, [rsp+68h+var_20]; unsigned __int16 **
0x180001261  mov     ecx, [rsp+68h+var_28]; unsigned int
0x180001265  call    ?FlushUrlCacheEntries@@YAXKQEAPEAG0@Z; FlushUrlCacheEntries(ulong,ushort * * const,ushort * * const)
0x18000126a  mov     rcx, rbx; hMem
0x18000126d  call    PkiFree
0x180001272  mov     rbx, [rsp+68h+arg_0]
0x180001277  add     rsp, 60h
0x18000127b  pop     rdi
0x18000127c  retn
```
