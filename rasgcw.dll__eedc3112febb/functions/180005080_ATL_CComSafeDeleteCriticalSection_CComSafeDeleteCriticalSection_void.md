# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180005080`
- end: `0x180005099`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004114`
- `0x1800046ec`
- `0x1800048ec`
- `0x180004e94`
- `0x18000501c`
- `0x1800050a0`
- `0x1800050c8`
- `0x1800050f0`
- `0x180005114`
- `0x18000513c`
- `0x180005198`
- `0x1800051c0`
- `0x1800051f4`
- `0x18001298c`
- `0x180018bf8`
- `0x180018f48`
- `0x180019cbc`
- `0x18001c228`
- `0x18001ccf4`
- `0x18001ef48`
- `0x18001f844`

## callees

- `0x180005080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000508e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000508e`

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
0x180005080  sub     rsp, 28h
0x180005084  cmp     byte ptr [rcx+28h], 0
0x180005088  jz      short loc_180005094
0x18000508a  mov     byte ptr [rcx+28h], 0
0x18000508e  call    cs:__imp_DeleteCriticalSection
0x180005094  add     rsp, 28h
0x180005098  retn
```
