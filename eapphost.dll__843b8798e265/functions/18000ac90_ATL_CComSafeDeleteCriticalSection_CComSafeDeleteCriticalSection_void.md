# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000ac90`
- end: `0x18000acb0`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ab0c`
- `0x18000eaa4`

## callees

- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ac9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ac9e`

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
0x18000ac90  sub     rsp, 28h
0x18000ac94  cmp     byte ptr [rcx+28h], 0
0x18000ac98  jz      short loc_18000ACAA
0x18000ac9a  mov     byte ptr [rcx+28h], 0
0x18000ac9e  call    cs:__imp_DeleteCriticalSection
0x18000aca5  nop     dword ptr [rax+rax+00h]
0x18000acaa  add     rsp, 28h
0x18000acae  retn
```
