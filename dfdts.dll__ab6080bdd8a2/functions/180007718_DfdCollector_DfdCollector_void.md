# DfdCollector::~DfdCollector(void)

- ea: `0x180007718`
- end: `0x18000774d`
- name: `??1DfdCollector@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(DfdCollector *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002450`
- `0x180008766`

## callees

- `0x180007718`

## import_xrefs

- `ntdll!WinSqmEndSession` at `0x18000772b`
- `ntdll!WinSqmEndSession` at `0x18000772b`
- `ADVAPI32!EventUnregister` at `0x180007741`
- `ADVAPI32!EventUnregister` at `0x180007741`

## pseudocode

```c
void __fastcall DfdCollector::~DfdCollector(DfdCollector *this)
{
  if ( *((_BYTE *)this + 28) )
  {
    WinSqmEndSession(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  if ( *(_QWORD *)this )
    EventUnregister(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180007718  push    rbx
0x18000771a  sub     rsp, 20h
0x18000771e  cmp     byte ptr [rcx+1Ch], 0
0x180007722  mov     rbx, rcx
0x180007725  jz      short loc_180007739
0x180007727  mov     rcx, [rcx+10h]
0x18000772b  call    cs:__imp_WinSqmEndSession
0x180007731  mov     qword ptr [rbx+10h], 0
0x180007739  mov     rcx, [rbx]; RegHandle
0x18000773c  test    rcx, rcx
0x18000773f  jz      short loc_180007747
0x180007741  call    cs:__imp_EventUnregister
0x180007747  add     rsp, 20h
0x18000774b  pop     rbx
0x18000774c  retn
```
