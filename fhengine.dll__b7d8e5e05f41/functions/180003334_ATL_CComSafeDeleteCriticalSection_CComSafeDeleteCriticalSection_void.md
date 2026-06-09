# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003334`
- end: `0x18000334d`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003190`
- `0x18000326c`
- `0x180003398`
- `0x1800033d0`
- `0x18000344c`

## callees

- `0x180003334`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003342`
- `KERNEL32!DeleteCriticalSection` at `0x180003342`

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
0x180003334  sub     rsp, 28h
0x180003338  cmp     byte ptr [rcx+28h], 0
0x18000333c  jz      short loc_180003348
0x18000333e  mov     byte ptr [rcx+28h], 0
0x180003342  call    cs:__imp_DeleteCriticalSection
0x180003348  add     rsp, 28h
0x18000334c  retn
```
