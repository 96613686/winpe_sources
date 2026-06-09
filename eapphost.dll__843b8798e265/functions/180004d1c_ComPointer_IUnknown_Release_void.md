# ComPointer<IUnknown>::Release(void)

- ea: `0x180004d1c`
- end: `0x180004d3b`
- name: `?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058d0`
- `0x18000b640`
- `0x180011258`
- `0x1800115b4`
- `0x180011d28`
- `0x1800184d4`
- `0x1800386f0`
- `0x180038730`

## callees

- `0x180004d1c`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall ComPointer<IUnknown>::Release(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180004d1c  sub     rsp, 28h
0x180004d20  mov     rcx, [rcx]
0x180004d23  test    rcx, rcx
0x180004d26  jz      short loc_180004D35
0x180004d28  mov     rax, [rcx]
0x180004d2b  mov     rax, [rax+10h]
0x180004d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d34  nop
0x180004d35  add     rsp, 28h
0x180004d39  retn
```
