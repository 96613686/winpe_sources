# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180017af8`
- end: `0x180017b11`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001798c`
- `0x1800179d8`
- `0x180017a20`
- `0x180033030`
- `0x180034b60`
- `0x18003664c`
- `0x180036698`
- `0x180037f98`
- `0x180037fe4`

## callees

- `0x180017af8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017b06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017b06`

## pseudocode

```c
void __fastcall ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(
        ATL::CComSafeDeleteCriticalSection *this)
{
  if ( this->m_bInitialized )
  {
    this->m_bInitialized = 0;
    DeleteCriticalSection(&this->m_sec);
  }
}

```

## disassembly

```asm
0x180017af8  sub     rsp, 28h
0x180017afc  cmp     byte ptr [this+28h], 0
0x180017b00  jz      short loc_180017B0C
0x180017b02  mov     byte ptr [this+28h], 0
0x180017b06  call    cs:__imp_DeleteCriticalSection
0x180017b0c  add     rsp, 28h
0x180017b10  retn
```
