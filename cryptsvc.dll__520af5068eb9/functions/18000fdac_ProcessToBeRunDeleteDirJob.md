# ProcessToBeRunDeleteDirJob

- ea: `0x18000fdac`
- end: `0x18000fe3d`
- name: `ProcessToBeRunDeleteDirJob`
- size: `145`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005460`

## callees

- `0x180004998`
- `0x1800068b0`
- `0x18000a660`
- `0x18000fdac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fdbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fdbd`

## pseudocode

```c
__int64 __fastcall ProcessToBeRunDeleteDirJob(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // r11
  __int64 v3; // rcx
  __int64 v4; // r8
  _QWORD *v5; // r11
  __int64 v6; // r11

  v1 = *(_QWORD **)(a1 + 32);
  EnterCriticalSection(&JobsCriticalSection);
  RemoveFromLinkList(&pUrlCacheDirHead, v1, 0);
  while ( 1 )
  {
    v6 = v1[2];
    if ( !v6 )
      break;
    RemoveFromLinkList(*(_QWORD *)(v6 + 40) + 32LL, v6 + 24, 24);
    v3 = *(_QWORD *)(v2 + 16) + 16LL;
    *(_QWORD *)(v2 + 40) = 0;
    RemoveFromLinkList(v3, v2, 0);
    v5[2] = v4;
    PkiFree(v5);
  }
  LeaveCriticalSection(&JobsCriticalSection);
  return FreeUrlCacheDir(v1);
}

```

## disassembly

```asm
0x18000fdac  push    rbx
0x18000fdae  sub     rsp, 20h
0x18000fdb2  mov     rbx, [rcx+20h]
0x18000fdb6  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000fdbd  call    cs:__imp_EnterCriticalSection
0x18000fdc3  xor     r8d, r8d
0x18000fdc6  lea     rcx, ?pUrlCacheDirHead@@3PEAU_CUCS_URL_CACHE_DIR_ENTRY@@EA; _CUCS_URL_CACHE_DIR_ENTRY * pUrlCacheDirHead
0x18000fdcd  mov     rdx, rbx
0x18000fdd0  call    RemoveFromLinkList
0x18000fdd5  jmp     short loc_18000FE15
0x18000fdd7  mov     rcx, [r11+28h]
0x18000fddb  lea     rdx, [r11+18h]
0x18000fddf  add     rcx, 20h ; ' '
0x18000fde3  mov     r8d, 18h
0x18000fde9  call    RemoveFromLinkList
0x18000fdee  mov     rcx, [r11+10h]
0x18000fdf2  xor     r8d, r8d
0x18000fdf5  add     rcx, 10h
0x18000fdf9  mov     qword ptr [r11+28h], 0
0x18000fe01  mov     rdx, r11
0x18000fe04  call    RemoveFromLinkList
0x18000fe09  mov     rcx, r11; hMem
0x18000fe0c  mov     [r11+10h], r8
0x18000fe10  call    PkiFree
0x18000fe15  mov     r11, [rbx+10h]
0x18000fe19  test    r11, r11
0x18000fe1c  jnz     short loc_18000FDD7
0x18000fe1e  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000fe25  call    cs:__imp_LeaveCriticalSection
0x18000fe2b  mov     edx, 1
0x18000fe30  mov     rcx, rbx; hMem
0x18000fe33  add     rsp, 20h
0x18000fe37  pop     rbx
0x18000fe38  jmp     FreeUrlCacheDir
```
