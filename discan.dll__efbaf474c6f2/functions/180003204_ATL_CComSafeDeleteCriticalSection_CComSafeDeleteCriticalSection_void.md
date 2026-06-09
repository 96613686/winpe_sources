# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003204`
- end: `0x18000321d`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003108`
- `0x180003224`

## callees

- `0x180003204`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003212`
- `KERNEL32!DeleteCriticalSection` at `0x180003212`

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
0x180003204  sub     rsp, 28h
0x180003208  cmp     byte ptr [rcx+28h], 0
0x18000320c  jz      short loc_180003218
0x18000320e  mov     byte ptr [rcx+28h], 0
0x180003212  call    cs:__imp_DeleteCriticalSection
0x180003218  add     rsp, 28h
0x18000321c  retn
```
