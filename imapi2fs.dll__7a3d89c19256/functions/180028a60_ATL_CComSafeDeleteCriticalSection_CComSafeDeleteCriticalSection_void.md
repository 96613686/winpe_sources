# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180028a60`
- end: `0x180028a79`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c12c`
- `0x1800289d4`
- `0x1800289f4`
- `0x180028a2c`
- `0x180028a94`
- `0x18002b638`
- `0x18003aef0`
- `0x18003c3e8`
- `0x18003c428`
- `0x18005459c`

## callees

- `0x180028a60`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180028a6e`
- `KERNEL32!DeleteCriticalSection` at `0x180028a6e`

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
0x180028a60  sub     rsp, 28h
0x180028a64  cmp     byte ptr [rcx+28h], 0
0x180028a68  jz      short loc_180028A74
0x180028a6a  mov     byte ptr [rcx+28h], 0
0x180028a6e  call    cs:__imp_DeleteCriticalSection
0x180028a74  add     rsp, 28h
0x180028a78  retn
```
