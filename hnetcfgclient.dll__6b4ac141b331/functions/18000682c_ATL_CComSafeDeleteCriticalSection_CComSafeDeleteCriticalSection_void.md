# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000682c`
- end: `0x180006845`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800066e0`
- `0x180006754`
- `0x1800067c8`
- `0x180006890`
- `0x18000c50c`
- `0x18000c58c`
- `0x18000c5f8`
- `0x18000c664`
- `0x18000c6d0`
- `0x18000c73c`
- `0x18000c7a8`
- `0x18000c814`
- `0x18000c880`
- `0x18000c8d4`
- `0x18000c928`
- `0x18000c97c`
- `0x18000c9d0`
- `0x18000ca38`
- `0x18000ca80`
- `0x18000caf4`
- `0x180018134`
- `0x180025d74`

## callees

- `0x18000682c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000683a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000683a`

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
0x18000682c  sub     rsp, 28h
0x180006830  cmp     byte ptr [rcx+28h], 0
0x180006834  jz      short loc_180006840
0x180006836  mov     byte ptr [rcx+28h], 0
0x18000683a  call    cs:__imp_DeleteCriticalSection
0x180006840  add     rsp, 28h
0x180006844  retn
```
