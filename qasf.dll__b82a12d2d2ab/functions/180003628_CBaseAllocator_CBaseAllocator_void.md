# CBaseAllocator::~CBaseAllocator(void)

- ea: `0x180003628`
- end: `0x18000366f`
- name: `??1CBaseAllocator@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003790`

## callees

- `0x180003628`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000365c`
- `KERNEL32!DeleteCriticalSection` at `0x18000365c`
- `KERNEL32!CloseHandle` at `0x18000363a`
- `KERNEL32!CloseHandle` at `0x18000363a`

## pseudocode

```c
void __fastcall CBaseAllocator::~CBaseAllocator(CBaseAllocator *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x180003628  push    rbx
0x18000362a  sub     rsp, 20h
0x18000362e  mov     rbx, rcx
0x180003631  mov     rcx, [rcx+58h]; hObject
0x180003635  test    rcx, rcx
0x180003638  jz      short loc_180003640
0x18000363a  call    cs:__imp_CloseHandle
0x180003640  mov     rcx, [rbx+88h]
0x180003647  test    rcx, rcx
0x18000364a  jz      short loc_180003658
0x18000364c  mov     rax, [rcx]
0x18000364f  mov     rax, [rax+10h]
0x180003653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003658  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000365c  call    cs:__imp_DeleteCriticalSection
0x180003662  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003669  add     rsp, 20h
0x18000366d  pop     rbx
0x18000366e  retn
```
