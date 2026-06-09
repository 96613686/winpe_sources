# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x140004614`
- end: `0x14000462d`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400045d4`
- `0x140004678`

## callees

- `0x140004614`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004622`
- `KERNEL32!DeleteCriticalSection` at `0x140004622`

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
0x140004614  sub     rsp, 28h
0x140004618  cmp     byte ptr [rcx+28h], 0
0x14000461c  jz      short loc_140004628
0x14000461e  mov     byte ptr [rcx+28h], 0
0x140004622  call    cs:__imp_DeleteCriticalSection
0x140004628  add     rsp, 28h
0x14000462c  retn
```
