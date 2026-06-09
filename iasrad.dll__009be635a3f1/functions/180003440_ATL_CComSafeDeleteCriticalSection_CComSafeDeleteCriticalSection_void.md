# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003440`
- end: `0x180003459`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ff8`
- `0x18000ae08`
- `0x18000e420`
- `0x18001d70c`

## callees

- `0x180003440`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000344e`
- `KERNEL32!DeleteCriticalSection` at `0x18000344e`

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
0x180003440  sub     rsp, 28h
0x180003444  cmp     byte ptr [rcx+28h], 0
0x180003448  jz      short loc_180003454
0x18000344a  mov     byte ptr [rcx+28h], 0
0x18000344e  call    cs:__imp_DeleteCriticalSection
0x180003454  add     rsp, 28h
0x180003458  retn
```
