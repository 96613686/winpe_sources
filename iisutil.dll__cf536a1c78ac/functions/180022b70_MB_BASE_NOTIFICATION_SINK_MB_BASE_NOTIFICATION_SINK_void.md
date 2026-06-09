# MB_BASE_NOTIFICATION_SINK::~MB_BASE_NOTIFICATION_SINK(void)

- ea: `0x180022b70`
- end: `0x180022ba7`
- name: `??1MB_BASE_NOTIFICATION_SINK@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(MB_BASE_NOTIFICATION_SINK *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022bb0`

## callees

- `0x180022b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b8d`

## pseudocode

```c
void __fastcall MB_BASE_NOTIFICATION_SINK::~MB_BASE_NOTIFICATION_SINK(MB_BASE_NOTIFICATION_SINK *this)
{
  bool v1; // zf

  v1 = *((_DWORD *)this + 14) == 0;
  *(_QWORD *)this = &MB_BASE_NOTIFICATION_SINK::`vftable';
  if ( !v1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    *((_DWORD *)this + 14) = 0;
  }
}

```

## disassembly

```asm
0x180022b70  push    rbx
0x180022b72  sub     rsp, 20h
0x180022b76  cmp     dword ptr [rcx+38h], 0
0x180022b7a  lea     rax, ??_7MB_BASE_NOTIFICATION_SINK@@6B@; const MB_BASE_NOTIFICATION_SINK::`vftable'
0x180022b81  mov     [rcx], rax
0x180022b84  mov     rbx, rcx
0x180022b87  jz      short loc_180022BA0
0x180022b89  add     rcx, 10h; lpCriticalSection
0x180022b8d  call    cs:__imp_DeleteCriticalSection
0x180022b94  nop     dword ptr [rax+rax+00h]
0x180022b99  mov     dword ptr [rbx+38h], 0
0x180022ba0  add     rsp, 20h
0x180022ba4  pop     rbx
0x180022ba5  retn
```
