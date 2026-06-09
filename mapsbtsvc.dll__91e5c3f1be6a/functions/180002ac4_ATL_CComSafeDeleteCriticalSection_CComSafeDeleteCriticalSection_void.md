# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180002ac4`
- end: `0x180002add`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002a60`
- `0x180002aa4`
- `0x180003370`

## callees

- `0x180002ac4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002ad2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002ad2`

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
0x180002ac4  sub     rsp, 28h
0x180002ac8  cmp     byte ptr [rcx+28h], 0
0x180002acc  jz      short loc_180002AD8
0x180002ace  mov     byte ptr [rcx+28h], 0
0x180002ad2  call    cs:__imp_DeleteCriticalSection
0x180002ad8  add     rsp, 28h
0x180002adc  retn
```
