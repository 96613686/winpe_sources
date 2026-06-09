# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800089c8`
- end: `0x1800089e1`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008904`
- `0x180008a2c`
- `0x18000c8f8`

## callees

- `0x1800089c8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800089d6`
- `KERNEL32!DeleteCriticalSection` at `0x1800089d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(
        ATL::CComSafeDeleteCriticalSection *this)
{
  if ( *((_BYTE *)this + 40) )
  {
    *((_BYTE *)this + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this);
  }
}

```

## disassembly

```asm
0x1800089c8  sub     rsp, 28h
0x1800089cc  cmp     byte ptr [rcx+28h], 0
0x1800089d0  jz      short loc_1800089DC
0x1800089d2  mov     byte ptr [rcx+28h], 0
0x1800089d6  call    cs:__imp_DeleteCriticalSection
0x1800089dc  add     rsp, 28h
0x1800089e0  retn
```
