# DrFile::GetCurrentQueryDirCacheEntry(_FILE_INFORMATION_CLASS)

- ea: `0x1400168f0`
- end: `0x14001696b`
- name: `?GetCurrentQueryDirCacheEntry@DrFile@@QEAAPEAUtagRDPDR_QUERYDIR_CACHE_ENTRY@@W4_FILE_INFORMATION_CLASS@@@Z`
- size: `123`
- prototype: `struct tagRDPDR_QUERYDIR_CACHE_ENTRY *__fastcall(DrFile *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400131e0`
- `0x1400152a0`

## callees

- `0x14000327c`
- `0x1400168f0`
- `0x140016974`

## pseudocode

```c
struct tagRDPDR_QUERYDIR_CACHE_ENTRY *__fastcall DrFile::GetCurrentQueryDirCacheEntry(DrFile *this, unsigned int a2)
{
  QueryDirCache *v3; // rcx

  switch ( a2 )
  {
    case 1u:
      v3 = (DrFile *)((char *)this + 56);
      return QueryDirCache::NextCacheEntry(v3);
    case 2u:
      v3 = (DrFile *)((char *)this + 96);
      return QueryDirCache::NextCacheEntry(v3);
    case 3u:
      v3 = (DrFile *)((char *)this + 136);
      return QueryDirCache::NextCacheEntry(v3);
    case 0xCu:
      v3 = (DrFile *)((char *)this + 176);
      return QueryDirCache::NextCacheEntry(v3);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, a2);
  return 0;
}

```

## disassembly

```asm
0x1400168f0  sub     rsp, 28h
0x1400168f4  mov     r8d, edx
0x1400168f7  mov     r9d, edx
0x1400168fa  sub     r8d, 1
0x1400168fe  jz      short loc_14001695C
0x140016900  sub     r8d, 1
0x140016904  jz      short loc_140016956
0x140016906  sub     r8d, 1
0x14001690a  jz      short loc_14001694D
0x14001690c  cmp     r8d, 9
0x140016910  jz      short loc_140016944
0x140016912  mov     rcx, cs:WPP_GLOBAL_Control
0x140016919  lea     rax, WPP_GLOBAL_Control
0x140016920  cmp     rcx, rax
0x140016923  jz      short loc_140016940
0x140016925  cmp     byte ptr [rcx+29h], 2
0x140016929  jb      short loc_140016940
0x14001692b  mov     rcx, [rcx+18h]
0x14001692f  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016936  mov     edx, 13h
0x14001693b  call    WPP_SF_d
0x140016940  xor     eax, eax
0x140016942  jmp     short loc_140016965
0x140016944  add     rcx, 0B0h
0x14001694b  jmp     short loc_140016960
0x14001694d  add     rcx, 88h
0x140016954  jmp     short loc_140016960
0x140016956  add     rcx, 60h ; '`'
0x14001695a  jmp     short loc_140016960
0x14001695c  add     rcx, 38h ; '8'; this
0x140016960  call    ?NextCacheEntry@QueryDirCache@@QEAAPEAUtagRDPDR_QUERYDIR_CACHE_ENTRY@@XZ; QueryDirCache::NextCacheEntry(void)
0x140016965  add     rsp, 28h
0x140016969  retn
```
