# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000213c`
- end: `0x180002155`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000215c`
- `0x180003f64`
- `0x180006400`
- `0x18000649c`
- `0x180008cb0`
- `0x180008d34`

## callees

- `0x18000213c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000214a`
- `KERNEL32!DeleteCriticalSection` at `0x18000214a`

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
0x18000213c  sub     rsp, 28h
0x180002140  cmp     byte ptr [rcx+28h], 0
0x180002144  jz      short loc_180002150
0x180002146  mov     byte ptr [rcx+28h], 0
0x18000214a  call    cs:__imp_DeleteCriticalSection
0x180002150  add     rsp, 28h
0x180002154  retn
```
