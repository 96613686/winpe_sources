# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800111d4`
- end: `0x1800111ed`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010fb8`
- `0x180011218`

## callees

- `0x1800111d4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800111e2`
- `KERNEL32!DeleteCriticalSection` at `0x1800111e2`

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
0x1800111d4  sub     rsp, 28h
0x1800111d8  cmp     byte ptr [rcx+28h], 0
0x1800111dc  jz      short loc_1800111E8
0x1800111de  mov     byte ptr [rcx+28h], 0
0x1800111e2  call    cs:__imp_DeleteCriticalSection
0x1800111e8  add     rsp, 28h
0x1800111ec  retn
```
