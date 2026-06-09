# ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)

- ea: `0x180003848`
- end: `0x180003862`
- name: `??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(ATL::CComAutoDeleteCriticalSection *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800033dc`
- `0x180003880`
- `0x18000b128`
- `0x180013630`
- `0x18001a6ec`
- `0x18001cab4`
- `0x18001f0a8`
- `0x18001f514`
- `0x1800201e0`
- `0x180021df0`
- `0x180022974`
- `0x180025668`

## callees

- `0x180003848`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003856`
- `KERNEL32!DeleteCriticalSection` at `0x180003856`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180003848  sub     rsp, 28h
0x18000384c  cmp     byte ptr [rcx+28h], 0
0x180003850  jz      short loc_18000385D
0x180003852  mov     byte ptr [rcx+28h], 0
0x180003856  call    cs:__imp_DeleteCriticalSection
0x18000385c  nop
0x18000385d  add     rsp, 28h
0x180003861  retn
```
