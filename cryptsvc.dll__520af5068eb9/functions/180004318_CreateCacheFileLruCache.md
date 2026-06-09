# _CreateCacheFileLruCache

- ea: `0x180004318`
- end: `0x18000435b`
- name: `_CreateCacheFileLruCache`
- size: `67`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005700`

## import_xrefs

- `CRYPT32!I_CryptCreateLruCache` at `0x180004350`
- `CRYPT32!I_CryptCreateLruCache` at `0x180004350`

## pseudocode

```c
__int64 __fastcall CreateCacheFileLruCache(__int64 a1)
{
  int v2; // [rsp+20h] [rbp-38h] BYREF
  __int64 v3; // [rsp+24h] [rbp-34h]
  int v4; // [rsp+2Ch] [rbp-2Ch]
  __int64 (__fastcall *v5)(); // [rsp+30h] [rbp-28h]
  __int64 v6; // [rsp+38h] [rbp-20h]
  __int64 v7; // [rsp+40h] [rbp-18h]

  v3 = 0;
  v4 = 0;
  v6 = 0;
  v7 = 127;
  v2 = 3;
  v5 = HashCacheFileEntryLruIdentifier;
  return I_CryptCreateLruCache(&v2, a1 + 104);
}

```

## disassembly

```asm
0x180004318  mov     r11, rsp
0x18000431b  sub     rsp, 58h
0x18000431f  xor     eax, eax
0x180004321  lea     rdx, [rcx+68h]
0x180004325  mov     [r11-34h], rax
0x180004329  lea     rcx, [r11-38h]
0x18000432d  mov     [rsp+58h+var_2C], eax
0x180004331  mov     [r11-20h], rax
0x180004335  lea     rax, _HashCacheFileEntryLruIdentifier
0x18000433c  mov     qword ptr [r11-18h], 7Fh
0x180004344  mov     [rsp+58h+var_38], 3
0x18000434c  mov     [r11-28h], rax
0x180004350  call    cs:__imp_I_CryptCreateLruCache
0x180004356  add     rsp, 58h
0x18000435a  retn
```
