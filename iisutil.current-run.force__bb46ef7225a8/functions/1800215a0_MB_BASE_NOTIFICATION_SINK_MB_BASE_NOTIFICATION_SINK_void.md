# MB_BASE_NOTIFICATION_SINK::~MB_BASE_NOTIFICATION_SINK(void)

- ea: `0x1800215a0`
- end: `0x1800215d0`
- name: `??1MB_BASE_NOTIFICATION_SINK@@UEAA@XZ`
- size: `48`
- prototype: `void __fastcall(MB_BASE_NOTIFICATION_SINK *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800215e0`

## callees

- `0x1800215a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800215bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800215bd`

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
0x1800215a0  push    rbx
0x1800215a2  sub     rsp, 20h
0x1800215a6  cmp     dword ptr [rcx+38h], 0
0x1800215aa  lea     rax, ??_7MB_BASE_NOTIFICATION_SINK@@6B@; const MB_BASE_NOTIFICATION_SINK::`vftable'
0x1800215b1  mov     [rcx], rax
0x1800215b4  mov     rbx, rcx
0x1800215b7  jz      short loc_1800215CA
0x1800215b9  add     rcx, 10h; lpCriticalSection
0x1800215bd  call    cs:__imp_DeleteCriticalSection
0x1800215c3  mov     dword ptr [rbx+38h], 0
0x1800215ca  add     rsp, 20h
0x1800215ce  pop     rbx
0x1800215cf  retn
```
