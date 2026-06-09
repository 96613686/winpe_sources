# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180029648`
- end: `0x180029661`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180029628`
- `0x1800c1790`

## callees

- `0x180029648`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029656`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029656`

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
0x180029648  sub     rsp, 28h
0x18002964c  cmp     byte ptr [rcx+28h], 0
0x180029650  jz      short loc_18002965C
0x180029652  mov     byte ptr [rcx+28h], 0
0x180029656  call    cs:__imp_DeleteCriticalSection
0x18002965c  add     rsp, 28h
0x180029660  retn
```
