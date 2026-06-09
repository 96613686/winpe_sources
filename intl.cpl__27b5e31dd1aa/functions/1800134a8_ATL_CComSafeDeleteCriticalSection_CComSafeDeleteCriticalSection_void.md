# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800134a8`
- end: `0x1800134c1`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013430`
- `0x18001350c`

## callees

- `0x1800134a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800134b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800134b6`

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
0x1800134a8  sub     rsp, 28h
0x1800134ac  cmp     byte ptr [rcx+28h], 0
0x1800134b0  jz      short loc_1800134BC
0x1800134b2  mov     byte ptr [rcx+28h], 0
0x1800134b6  call    cs:__imp_DeleteCriticalSection
0x1800134bc  add     rsp, 28h
0x1800134c0  retn
```
