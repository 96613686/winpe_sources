# CASFReader::GetStatistics(_WMReaderStatistics *)

- ea: `0x18000a4e0`
- end: `0x18000a501`
- name: `?GetStatistics@CASFReader@@EEAAJPEAU_WMReaderStatistics@@@Z`
- size: `33`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct _WMReaderStatistics *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a4e0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetStatistics(CASFReader *this, struct _WMReaderStatistics *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 26);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, struct _WMReaderStatistics *))(*(_QWORD *)v2 + 144LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000a4e0  mov     rcx, [rcx+0D0h]
0x18000a4e7  test    rcx, rcx
0x18000a4ea  jnz     short loc_18000A4F2
0x18000a4ec  mov     eax, 80004005h
0x18000a4f1  retn
0x18000a4f2  mov     rax, [rcx]
0x18000a4f5  mov     rax, [rax+90h]
0x18000a4fc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
