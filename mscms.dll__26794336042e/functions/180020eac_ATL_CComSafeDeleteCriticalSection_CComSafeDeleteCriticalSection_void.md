# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180020eac`
- end: `0x180020ec6`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020e74`
- `0x18002ae98`
- `0x18004bd98`

## callees

- `0x180020eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020eba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020eba`

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
0x180020eac  sub     rsp, 28h
0x180020eb0  cmp     byte ptr [rcx+28h], 0
0x180020eb4  jz      short loc_180020EC1
0x180020eb6  mov     byte ptr [rcx+28h], 0
0x180020eba  call    cs:__imp_DeleteCriticalSection
0x180020ec0  nop
0x180020ec1  add     rsp, 28h
0x180020ec5  retn
```
