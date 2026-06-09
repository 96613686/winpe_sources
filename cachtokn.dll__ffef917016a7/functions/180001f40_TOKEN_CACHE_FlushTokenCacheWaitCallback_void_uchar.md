# TOKEN_CACHE::FlushTokenCacheWaitCallback(void *,uchar)

- ea: `0x180001f40`
- end: `0x180001fd0`
- name: `?FlushTokenCacheWaitCallback@TOKEN_CACHE@@SAXPEAXE@Z`
- size: `144`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180001f40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180001fc4`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180001fc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f85`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f85`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001fa9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001fa9`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180001f9f`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180001f9f`

## string_xrefs

- `0x180001f73`: `FlushTokenCache`

## pseudocode

```c
void __fastcall TOKEN_CACHE::FlushTokenCacheWaitCallback(void *a1)
{
  HKEY v2; // rcx
  DWORD v3; // [rsp+40h] [rbp+8h] BYREF
  int v4; // [rsp+50h] [rbp+18h] BYREF
  DWORD v5; // [rsp+58h] [rbp+20h] BYREF

  v4 = 0;
  v3 = 0;
  v2 = (HKEY)*((_QWORD *)a1 + 10);
  v5 = 4;
  if ( !RegQueryValueExW(v2, L"FlushTokenCache", 0, &v3, (LPBYTE)&v4, &v5) && v3 == 4 && v4 )
    CLKRHashTable::Clear((CLKRHashTable *)a1);
  ResetEvent(*((HANDLE *)a1 + 11));
  RegNotifyChangeKeyValue(*((HKEY *)a1 + 10), 1, 4u, *((HANDLE *)a1 + 11), 1);
}

```

## disassembly

```asm
0x180001f40  mov     r11, rsp
0x180001f43  push    rbx
0x180001f44  sub     rsp, 30h
0x180001f48  lea     rax, [r11+20h]
0x180001f4c  mov     [rsp+38h+arg_10], 0
0x180001f54  mov     [r11-10h], rax
0x180001f58  lea     r9, [r11+8]; lpType
0x180001f5c  lea     rax, [r11+18h]
0x180001f60  mov     [rsp+38h+arg_0], 0
0x180001f68  mov     rbx, rcx
0x180001f6b  mov     [r11-18h], rax
0x180001f6f  mov     rcx, [rcx+50h]; hKey
0x180001f73  lea     rdx, ValueName; "FlushTokenCache"
0x180001f7a  xor     r8d, r8d; lpReserved
0x180001f7d  mov     [rsp+38h+arg_18], 4
0x180001f85  call    cs:__imp_RegQueryValueExW
0x180001f8b  test    eax, eax
0x180001f8d  jnz     short loc_180001FA5
0x180001f8f  cmp     [rsp+38h+arg_0], 4
0x180001f94  jnz     short loc_180001FA5
0x180001f96  cmp     [rsp+38h+arg_10], eax
0x180001f9a  jbe     short loc_180001FA5
0x180001f9c  mov     rcx, rbx
0x180001f9f  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180001fa5  mov     rcx, [rbx+58h]; hEvent
0x180001fa9  call    cs:__imp_ResetEvent
0x180001faf  mov     r9, [rbx+58h]; hEvent
0x180001fb3  mov     edx, 1; bWatchSubtree
0x180001fb8  mov     rcx, [rbx+50h]; hKey
0x180001fbc  mov     [rsp+38h+fAsynchronous], edx; fAsynchronous
0x180001fc0  lea     r8d, [rdx+3]; dwNotifyFilter
0x180001fc4  call    cs:__imp_RegNotifyChangeKeyValue
0x180001fca  add     rsp, 30h
0x180001fce  pop     rbx
0x180001fcf  retn
```
