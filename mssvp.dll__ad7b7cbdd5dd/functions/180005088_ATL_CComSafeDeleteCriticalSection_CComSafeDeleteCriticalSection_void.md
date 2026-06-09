# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180005088`
- end: `0x1800050a1`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a69c`

## callees

- `0x180005088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005096`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005096`

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
0x180005088  sub     rsp, 28h
0x18000508c  cmp     byte ptr [rcx+28h], 0
0x180005090  jz      short loc_18000509C
0x180005092  mov     byte ptr [rcx+28h], 0
0x180005096  call    cs:__imp_DeleteCriticalSection
0x18000509c  add     rsp, 28h
0x1800050a0  retn
```
