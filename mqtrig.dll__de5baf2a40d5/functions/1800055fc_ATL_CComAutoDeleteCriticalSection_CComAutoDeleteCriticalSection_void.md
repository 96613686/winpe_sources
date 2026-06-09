# ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)

- ea: `0x1800055fc`
- end: `0x180005616`
- name: `??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(ATL::CComAutoDeleteCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800055c8`
- `0x18000561c`
- `0x18000a22c`
- `0x18000db44`
- `0x18000db7c`
- `0x1800104f8`

## callees

- `0x1800055fc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000560a`
- `KERNEL32!DeleteCriticalSection` at `0x18000560a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(
        ATL::CComAutoDeleteCriticalSection *this)
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
0x1800055fc  sub     rsp, 28h
0x180005600  cmp     byte ptr [rcx+28h], 0
0x180005604  jz      short loc_180005611
0x180005606  mov     byte ptr [rcx+28h], 0
0x18000560a  call    cs:__imp_DeleteCriticalSection
0x180005610  nop
0x180005611  add     rsp, 28h
0x180005615  retn
```
