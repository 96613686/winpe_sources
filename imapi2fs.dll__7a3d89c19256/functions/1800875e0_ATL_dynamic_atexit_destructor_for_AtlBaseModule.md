# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x1800875e0`
- end: `0x18008761e`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800875e0`

## import_xrefs

- `msvcrt!free` at `0x1800875fd`
- `msvcrt!free` at `0x1800875fd`
- `KERNEL32!DeleteCriticalSection` at `0x1800875eb`
- `KERNEL32!DeleteCriticalSection` at `0x1800875eb`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_1800B1EA8);
  if ( qword_1800B1ED0 )
  {
    free(qword_1800B1ED0);
    qword_1800B1ED0 = 0;
  }
  qword_1800B1ED8 = 0;
}

```

## disassembly

```asm
0x1800875e0  sub     rsp, 28h
0x1800875e4  lea     rcx, stru_1800B1EA8; lpCriticalSection
0x1800875eb  call    cs:__imp_DeleteCriticalSection
0x1800875f1  mov     rcx, cs:qword_1800B1ED0; Block
0x1800875f8  test    rcx, rcx
0x1800875fb  jz      short loc_18008760E
0x1800875fd  call    cs:__imp_free
0x180087603  mov     cs:qword_1800B1ED0, 0
0x18008760e  mov     cs:qword_1800B1ED8, 0
0x180087619  add     rsp, 28h
0x18008761d  retn
```
