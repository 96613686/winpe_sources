# LsaDbpForestTrustCacheSetInvalid(void)

- ea: `0x180026594`
- end: `0x18002666d`
- name: `?LsaDbpForestTrustCacheSetInvalid@@YAXXZ`
- size: `217`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c400`
- `0x180024e10`
- `0x180026850`
- `0x180026cf0`
- `0x18002a15c`

## callees

- `0x18000fd18`
- `0x18001f5c0`
- `0x18001fbcc`
- `0x180026594`
- `0x180029d94`

## import_xrefs

- `NTDSA!DirNotifyUnRegister` at `0x18002660e`
- `NTDSA!DirNotifyUnRegister` at `0x18002662c`
- `NTDSA!DirNotifyUnRegister` at `0x18002660e`
- `NTDSA!DirNotifyUnRegister` at `0x18002662c`

## pseudocode

```c
void LsaDbpForestTrustCacheSetInvalid(void)
{
  FTCache *v0; // rbx
  char v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 v2; // [rsp+38h] [rbp+10h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  v0 = g_FTCache;
  if ( XrefNotificationHandle || UpnSuffixNotificationHandle )
  {
    v1 = 0;
    if ( (int)LsaDbpDsInitAllocAsNeededEx(50331650, 2, &v1) >= 0 )
    {
      if ( XrefNotificationHandle )
      {
        v2 = 0;
        DirNotifyUnRegister(XrefNotificationHandle, &v2);
      }
      if ( UpnSuffixNotificationHandle )
      {
        v2 = 0;
        DirNotifyUnRegister(UpnSuffixNotificationHandle, &v2);
      }
      LsaDbpDsDeleteAllocAsNeededEx(2, 2u, v1);
    }
    XrefNotificationHandle = 0;
    UpnSuffixNotificationHandle = 0;
  }
  *(_WORD *)((char *)v0 + 1) = 0;
  FTCache::Purge(v0);
}

```

## disassembly

```asm
0x180026594  push    rbx
0x180026596  sub     rsp, 20h
0x18002659a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265a1  test    byte ptr [rcx+1Ch], 8
0x1800265a5  jz      short loc_1800265BC
0x1800265a7  mov     rcx, [rcx+10h]
0x1800265ab  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800265b2  mov     edx, 2Bh ; '+'
0x1800265b7  call    WPP_SF_
0x1800265bc  cmp     cs:?XrefNotificationHandle@@3KA, 0; ulong XrefNotificationHandle
0x1800265c3  mov     rbx, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x1800265ca  jnz     short loc_1800265D9
0x1800265cc  cmp     cs:?UpnSuffixNotificationHandle@@3KA, 0; ulong UpnSuffixNotificationHandle
0x1800265d3  jz      loc_18002665A
0x1800265d9  lea     r8, [rsp+28h+arg_0]
0x1800265de  mov     [rsp+28h+arg_0], 0
0x1800265e3  mov     edx, 2
0x1800265e8  mov     ecx, 3000002h
0x1800265ed  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x1800265f2  test    eax, eax
0x1800265f4  js      short loc_180026646
0x1800265f6  mov     ecx, cs:?XrefNotificationHandle@@3KA; ulong XrefNotificationHandle
0x1800265fc  test    ecx, ecx
0x1800265fe  jz      short loc_180026614
0x180026600  lea     rdx, [rsp+28h+arg_8]
0x180026605  mov     [rsp+28h+arg_8], 0
0x18002660e  call    cs:__imp_DirNotifyUnRegister
0x180026614  mov     ecx, cs:?UpnSuffixNotificationHandle@@3KA; ulong UpnSuffixNotificationHandle
0x18002661a  test    ecx, ecx
0x18002661c  jz      short loc_180026632
0x18002661e  lea     rdx, [rsp+28h+arg_8]
0x180026623  mov     [rsp+28h+arg_8], 0
0x18002662c  call    cs:__imp_DirNotifyUnRegister
0x180026632  mov     r8b, [rsp+28h+arg_0]
0x180026637  mov     edx, 2
0x18002663c  mov     ecx, 3000002h
0x180026641  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x180026646  mov     cs:?XrefNotificationHandle@@3KA, 0; ulong XrefNotificationHandle
0x180026650  mov     cs:?UpnSuffixNotificationHandle@@3KA, 0; ulong UpnSuffixNotificationHandle
0x18002665a  mov     rcx, rbx; this
0x18002665d  mov     word ptr [rbx+1], 0
0x180026663  add     rsp, 20h
0x180026667  pop     rbx
0x180026668  jmp     ?Purge@FTCache@@AEAAXXZ; FTCache::Purge(void)
```
