# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000a818`
- end: `0x18000a831`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a63c`
- `0x18000e4d0`

## callees

- `0x18000a818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a826`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a826`

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
0x18000a818  sub     rsp, 28h
0x18000a81c  cmp     byte ptr [rcx+28h], 0
0x18000a820  jz      short loc_18000A82C
0x18000a822  mov     byte ptr [rcx+28h], 0
0x18000a826  call    cs:__imp_DeleteCriticalSection
0x18000a82c  add     rsp, 28h
0x18000a830  retn
```
