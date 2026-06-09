# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000bd0c`
- end: `0x18000bd25`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bd50`

## callees

- `0x18000bd0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bd1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bd1a`

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
0x18000bd0c  sub     rsp, 28h
0x18000bd10  cmp     byte ptr [rcx+28h], 0
0x18000bd14  jz      short loc_18000BD20
0x18000bd16  mov     byte ptr [rcx+28h], 0
0x18000bd1a  call    cs:__imp_DeleteCriticalSection
0x18000bd20  add     rsp, 28h
0x18000bd24  retn
```
