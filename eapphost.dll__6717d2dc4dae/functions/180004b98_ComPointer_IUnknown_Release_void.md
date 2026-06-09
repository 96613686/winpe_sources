# ComPointer<IUnknown>::Release(void)

- ea: `0x180004b98`
- end: `0x180004bb6`
- name: `?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`
- `0x18000b180`
- `0x180010ba8`
- `0x180010eb4`
- `0x1800115e8`
- `0x180017bac`
- `0x1800372f0`
- `0x180037330`

## callees

- `0x180004b98`
- `0x180038010`

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
0x180004b98  sub     rsp, 28h
0x180004b9c  mov     rcx, [rcx]
0x180004b9f  test    rcx, rcx
0x180004ba2  jz      short loc_180004BB1
0x180004ba4  mov     rax, [rcx]
0x180004ba7  mov     rax, [rax+10h]
0x180004bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb0  nop
0x180004bb1  add     rsp, 28h
0x180004bb5  retn
```
