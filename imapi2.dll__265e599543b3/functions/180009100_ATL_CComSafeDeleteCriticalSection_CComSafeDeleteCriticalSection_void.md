# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180009100`
- end: `0x180009119`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e98`
- `0x1800090bc`
- `0x18000e9e4`
- `0x18000ee68`
- `0x18000efcc`
- `0x18000f628`
- `0x1800110c8`
- `0x18001112c`
- `0x180016034`
- `0x180016078`
- `0x1800169d0`
- `0x180016a00`
- `0x180016b58`
- `0x180016b9c`
- `0x180016bfc`
- `0x180024f90`
- `0x180028c8c`
- `0x18002d7c0`
- `0x1800368f0`
- `0x18003c184`
- `0x18003c23c`
- `0x18003c280`
- `0x180042508`
- `0x18004254c`

## callees

- `0x180009100`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000910e`
- `KERNEL32!DeleteCriticalSection` at `0x18000910e`

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
0x180009100  sub     rsp, 28h
0x180009104  cmp     byte ptr [rcx+28h], 0
0x180009108  jz      short loc_180009114
0x18000910a  mov     byte ptr [rcx+28h], 0
0x18000910e  call    cs:__imp_DeleteCriticalSection
0x180009114  add     rsp, 28h
0x180009118  retn
```
