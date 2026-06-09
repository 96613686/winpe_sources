# QueryDirCache::~QueryDirCache(void)

- ea: `0x14001665c`
- end: `0x1400166ac`
- name: `??1QueryDirCache@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(QueryDirCache *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400037c0`
- `0x14001652c`

## callees

- `0x14000324c`
- `0x14001665c`
- `0x1400167f4`

## pseudocode

```c
void __fastcall QueryDirCache::~QueryDirCache(QueryDirCache *this, __int64 a2, __int64 a3)
{
  *(_QWORD *)this = &QueryDirCache::`vftable';
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids);
  QueryDirCache::CleanupCache(this, a2, a3);
}

```

## disassembly

```asm
0x14001665c  push    rbx
0x14001665e  sub     rsp, 20h
0x140016662  lea     rax, ??_7QueryDirCache@@6B@; const QueryDirCache::`vftable'
0x140016669  mov     rbx, rcx
0x14001666c  mov     [rcx], rax
0x14001666f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016676  lea     rax, WPP_GLOBAL_Control
0x14001667d  cmp     rcx, rax
0x140016680  jz      short loc_14001669D
0x140016682  cmp     byte ptr [rcx+29h], 5
0x140016686  jb      short loc_14001669D
0x140016688  mov     rcx, [rcx+18h]
0x14001668c  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016693  mov     edx, 15h
0x140016698  call    WPP_SF_
0x14001669d  mov     rcx, rbx; this
0x1400166a0  call    ?CleanupCache@QueryDirCache@@QEAAXXZ; QueryDirCache::CleanupCache(void)
0x1400166a5  add     rsp, 20h
0x1400166a9  pop     rbx
0x1400166aa  retn
```
