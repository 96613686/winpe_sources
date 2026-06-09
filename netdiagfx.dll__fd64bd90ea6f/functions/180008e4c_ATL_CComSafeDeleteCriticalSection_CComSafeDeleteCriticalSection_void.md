# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180008e4c`
- end: `0x180008e65`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008c34`
- `0x1800167c0`
- `0x18001680c`

## callees

- `0x180008e4c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008e5a`
- `KERNEL32!DeleteCriticalSection` at `0x180008e5a`

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
0x180008e4c  sub     rsp, 28h
0x180008e50  cmp     byte ptr [rcx+28h], 0
0x180008e54  jz      short loc_180008E60
0x180008e56  mov     byte ptr [rcx+28h], 0
0x180008e5a  call    cs:__imp_DeleteCriticalSection
0x180008e60  add     rsp, 28h
0x180008e64  retn
```
