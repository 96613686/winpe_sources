# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000d904`
- end: `0x18000d91d`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800055f0`
- `0x180007ff0`
- `0x18000a688`
- `0x18000d874`
- `0x18000d8c0`
- `0x1800167a4`
- `0x180016808`

## callees

- `0x18000d904`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d912`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d912`

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
0x18000d904  sub     rsp, 28h
0x18000d908  cmp     byte ptr [rcx+28h], 0
0x18000d90c  jz      short loc_18000D918
0x18000d90e  mov     byte ptr [rcx+28h], 0
0x18000d912  call    cs:__imp_DeleteCriticalSection
0x18000d918  add     rsp, 28h
0x18000d91c  retn
```
