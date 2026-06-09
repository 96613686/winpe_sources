# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003124`
- end: `0x18000313d`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000309c`
- `0x180003188`
- `0x18000329c`

## callees

- `0x180003124`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003132`
- `KERNEL32!DeleteCriticalSection` at `0x180003132`

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
0x180003124  sub     rsp, 28h
0x180003128  cmp     byte ptr [rcx+28h], 0
0x18000312c  jz      short loc_180003138
0x18000312e  mov     byte ptr [rcx+28h], 0
0x180003132  call    cs:__imp_DeleteCriticalSection
0x180003138  add     rsp, 28h
0x18000313c  retn
```
