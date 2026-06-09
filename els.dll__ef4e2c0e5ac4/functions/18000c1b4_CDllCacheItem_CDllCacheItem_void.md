# CDllCacheItem::~CDllCacheItem(void)

- ea: `0x18000c1b4`
- end: `0x18000c204`
- name: `??1CDllCacheItem@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CDllCacheItem *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c270`

## callees

- `0x18000c1b4`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000c1d3`
- `KERNEL32!FreeLibrary` at `0x18000c1d3`

## pseudocode

```c
void __fastcall CDllCacheItem::~CDllCacheItem(CDllCacheItem *this)
{
  HMODULE v2; // rcx

  *(_QWORD *)this = &CDllCacheItem::`vftable';
  v2 = (HMODULE)*((_QWORD *)this + 69);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 69) = 0;
  }
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CDLink::`vftable';
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18000c1b4  push    rbx
0x18000c1b6  sub     rsp, 20h
0x18000c1ba  lea     rax, ??_7CDllCacheItem@@6B@; const CDllCacheItem::`vftable'
0x18000c1c1  mov     rbx, rcx
0x18000c1c4  mov     [rcx], rax
0x18000c1c7  mov     rcx, [rcx+228h]; hLibModule
0x18000c1ce  test    rcx, rcx
0x18000c1d1  jz      short loc_18000C1E4
0x18000c1d3  call    cs:__imp_FreeLibrary
0x18000c1d9  mov     qword ptr [rbx+228h], 0
0x18000c1e4  lea     rax, ??_7CDLink@@6B@; const CDLink::`vftable'
0x18000c1eb  mov     qword ptr [rbx+8], 0
0x18000c1f3  mov     [rbx], rax
0x18000c1f6  mov     qword ptr [rbx+10h], 0
0x18000c1fe  add     rsp, 20h
0x18000c202  pop     rbx
0x18000c203  retn
```
