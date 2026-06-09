# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180001cbc`
- end: `0x180001cd5`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001be0`
- `0x180001c38`
- `0x180001c9c`

## callees

- `0x180001cbc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180001cca`
- `KERNEL32!DeleteCriticalSection` at `0x180001cca`

## pseudocode

```c
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
0x180001cbc  sub     rsp, 28h
0x180001cc0  cmp     byte ptr [rcx+28h], 0
0x180001cc4  jz      short loc_180001CD0
0x180001cc6  mov     byte ptr [rcx+28h], 0
0x180001cca  call    cs:__imp_DeleteCriticalSection
0x180001cd0  add     rsp, 28h
0x180001cd4  retn
```
