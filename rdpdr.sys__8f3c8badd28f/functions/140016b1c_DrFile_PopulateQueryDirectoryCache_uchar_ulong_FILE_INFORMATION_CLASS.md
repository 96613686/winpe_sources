# DrFile::PopulateQueryDirectoryCache(uchar *,ulong,_FILE_INFORMATION_CLASS)

- ea: `0x140016b1c`
- end: `0x140016ba1`
- name: `?PopulateQueryDirectoryCache@DrFile@@QEAAHPEAEKW4_FILE_INFORMATION_CLASS@@@Z`
- size: `133`
- prototype: `int __fastcall(DrFile *this, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400131e0`

## callees

- `0x14000327c`
- `0x1400169f0`
- `0x140016b1c`

## pseudocode

```c
int __fastcall DrFile::PopulateQueryDirectoryCache(DrFile *this, unsigned __int8 *a2, unsigned int a3, unsigned int a4)
{
  QueryDirCache *v7; // rcx

  switch ( a4 )
  {
    case 1u:
      v7 = (DrFile *)((char *)this + 56);
      return QueryDirCache::PopulateCache(v7, a2, a3, *((_DWORD *)this + 13));
    case 2u:
      v7 = (DrFile *)((char *)this + 96);
      return QueryDirCache::PopulateCache(v7, a2, a3, *((_DWORD *)this + 13));
    case 3u:
      v7 = (DrFile *)((char *)this + 136);
      return QueryDirCache::PopulateCache(v7, a2, a3, *((_DWORD *)this + 13));
    case 0xCu:
      v7 = (DrFile *)((char *)this + 176);
      return QueryDirCache::PopulateCache(v7, a2, a3, *((_DWORD *)this + 13));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, a4);
  return 0;
}

```

## disassembly

```asm
0x140016b1c  sub     rsp, 28h
0x140016b20  mov     r11d, r9d
0x140016b23  mov     r9, rcx
0x140016b26  mov     r10d, r11d
0x140016b29  sub     r10d, 1
0x140016b2d  jz      short loc_140016B8E
0x140016b2f  sub     r10d, 1
0x140016b33  jz      short loc_140016B88
0x140016b35  sub     r10d, 1
0x140016b39  jz      short loc_140016B7F
0x140016b3b  cmp     r10d, 9
0x140016b3f  jz      short loc_140016B76
0x140016b41  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b48  lea     rax, WPP_GLOBAL_Control
0x140016b4f  cmp     rcx, rax
0x140016b52  jz      short loc_140016B72
0x140016b54  cmp     byte ptr [rcx+29h], 2
0x140016b58  jb      short loc_140016B72
0x140016b5a  mov     rcx, [rcx+18h]
0x140016b5e  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016b65  mov     edx, 14h
0x140016b6a  mov     r9d, r11d
0x140016b6d  call    WPP_SF_d
0x140016b72  xor     eax, eax
0x140016b74  jmp     short loc_140016B9B
0x140016b76  add     rcx, 0B0h
0x140016b7d  jmp     short loc_140016B92
0x140016b7f  add     rcx, 88h
0x140016b86  jmp     short loc_140016B92
0x140016b88  add     rcx, 60h ; '`'
0x140016b8c  jmp     short loc_140016B92
0x140016b8e  add     rcx, 38h ; '8'; this
0x140016b92  mov     r9d, [r9+34h]; unsigned int
0x140016b96  call    ?PopulateCache@QueryDirCache@@QEAAHPEAEKK@Z; QueryDirCache::PopulateCache(uchar *,ulong,ulong)
0x140016b9b  add     rsp, 28h
0x140016b9f  retn
```
