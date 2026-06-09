# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180016e8c`
- end: `0x180016ea5`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016e28`
- `0x180016ef0`

## callees

- `0x180016e8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016e9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016e9a`

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
0x180016e8c  sub     rsp, 28h
0x180016e90  cmp     byte ptr [rcx+28h], 0
0x180016e94  jz      short loc_180016EA0
0x180016e96  mov     byte ptr [rcx+28h], 0
0x180016e9a  call    cs:__imp_DeleteCriticalSection
0x180016ea0  add     rsp, 28h
0x180016ea4  retn
```
