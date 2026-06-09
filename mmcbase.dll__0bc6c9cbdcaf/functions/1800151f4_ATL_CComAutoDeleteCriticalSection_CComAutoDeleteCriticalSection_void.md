# ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)

- ea: `0x1800151f4`
- end: `0x18001520d`
- name: `??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComAutoDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015220`

## callees

- `0x1800151f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015202`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015202`

## pseudocode

```c
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
0x1800151f4  sub     rsp, 28h
0x1800151f8  cmp     byte ptr [rcx+28h], 0
0x1800151fc  jz      short loc_180015208
0x1800151fe  mov     byte ptr [rcx+28h], 0
0x180015202  call    cs:__imp_DeleteCriticalSection
0x180015208  add     rsp, 28h
0x18001520c  retn
```
