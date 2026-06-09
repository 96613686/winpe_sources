# DrFile::CleanupQueryDirCache(_FILE_INFORMATION_CLASS)

- ea: `0x140016870`
- end: `0x1400168e9`
- name: `?CleanupQueryDirCache@DrFile@@QEAAXW4_FILE_INFORMATION_CLASS@@@Z`
- size: `121`
- prototype: `void __fastcall(DrFile *__hidden this, enum _FILE_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014d50`

## callees

- `0x14000327c`
- `0x1400167f4`
- `0x140016870`

## pseudocode

```c
void __fastcall DrFile::CleanupQueryDirCache(DrFile *this, __int64 a2)
{
  __int64 v2; // r8
  QueryDirCache *v3; // rcx

  v2 = (unsigned int)(a2 - 1);
  if ( (_DWORD)a2 == 1 )
  {
    v3 = (DrFile *)((char *)this + 56);
    goto LABEL_12;
  }
  v2 = (unsigned int)(a2 - 2);
  if ( (_DWORD)a2 == 2 )
  {
    v3 = (DrFile *)((char *)this + 96);
    goto LABEL_12;
  }
  v2 = (unsigned int)(a2 - 3);
  if ( (_DWORD)a2 == 3 )
  {
    v3 = (DrFile *)((char *)this + 136);
    goto LABEL_12;
  }
  if ( (_DWORD)a2 == 12 )
  {
    v3 = (DrFile *)((char *)this + 176);
LABEL_12:
    QueryDirCache::CleanupCache(v3, a2, v2);
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, (unsigned int)a2);
}

```

## disassembly

```asm
0x140016870  sub     rsp, 28h
0x140016874  mov     r8d, edx
0x140016877  mov     r9d, edx
0x14001687a  sub     r8d, 1
0x14001687e  jz      short loc_1400168DA
0x140016880  sub     r8d, 1
0x140016884  jz      short loc_1400168D4
0x140016886  sub     r8d, 1
0x14001688a  jz      short loc_1400168CB
0x14001688c  cmp     r8d, 9
0x140016890  jz      short loc_1400168C2
0x140016892  mov     rcx, cs:WPP_GLOBAL_Control
0x140016899  lea     rax, WPP_GLOBAL_Control
0x1400168a0  cmp     rcx, rax
0x1400168a3  jz      short loc_1400168E3
0x1400168a5  cmp     byte ptr [rcx+29h], 2
0x1400168a9  jb      short loc_1400168E3
0x1400168ab  mov     rcx, [rcx+18h]
0x1400168af  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x1400168b6  mov     edx, 12h
0x1400168bb  call    WPP_SF_d
0x1400168c0  jmp     short loc_1400168E3
0x1400168c2  add     rcx, 0B0h
0x1400168c9  jmp     short loc_1400168DE
0x1400168cb  add     rcx, 88h
0x1400168d2  jmp     short loc_1400168DE
0x1400168d4  add     rcx, 60h ; '`'
0x1400168d8  jmp     short loc_1400168DE
0x1400168da  add     rcx, 38h ; '8'; this
0x1400168de  call    ?CleanupCache@QueryDirCache@@QEAAXXZ; QueryDirCache::CleanupCache(void)
0x1400168e3  add     rsp, 28h
0x1400168e7  retn
```
