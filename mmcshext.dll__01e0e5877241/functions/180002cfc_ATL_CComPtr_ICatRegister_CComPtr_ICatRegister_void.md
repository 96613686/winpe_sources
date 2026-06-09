# ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(void)

- ea: `0x180002cfc`
- end: `0x180002d1a`
- name: `??1?$CComPtr@UICatRegister@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aad0`

## callees

- `0x180002cfc`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(__int64 *a1)
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
0x180002cfc  sub     rsp, 28h
0x180002d00  mov     rcx, [rcx]
0x180002d03  test    rcx, rcx
0x180002d06  jz      short loc_180002D15
0x180002d08  mov     rax, [rcx]
0x180002d0b  mov     rax, [rax+10h]
0x180002d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d14  nop
0x180002d15  add     rsp, 28h
0x180002d19  retn
```
