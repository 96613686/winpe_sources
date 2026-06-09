# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003f5c`
- end: `0x180003f75`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003fc0`

## callees

- `0x180003f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f6a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f6a`

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
0x180003f5c  sub     rsp, 28h
0x180003f60  cmp     byte ptr [rcx+28h], 0
0x180003f64  jz      short loc_180003F70
0x180003f66  mov     byte ptr [rcx+28h], 0
0x180003f6a  call    cs:__imp_DeleteCriticalSection
0x180003f70  add     rsp, 28h
0x180003f74  retn
```
