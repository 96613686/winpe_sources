# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180011d6c`
- end: `0x180011d93`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011b00`
- `0x180016948`
- `0x180016ac8`
- `0x1800174b8`
- `0x1800182a8`
- `0x1800185f4`
- `0x1800188bc`
- `0x180018b70`
- `0x180028fdc`
- `0x180029240`
- `0x18002abf0`

## callees

- `0x180011d6c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180011d6c  sub     rsp, 28h
0x180011d70  mov     rdx, rcx
0x180011d73  xor     eax, eax
0x180011d75  mov     rcx, [rcx]
0x180011d78  test    rcx, rcx
0x180011d7b  jz      short loc_180011D8D
0x180011d7d  mov     [rdx], rax
0x180011d80  mov     rax, [rcx]
0x180011d83  mov     rax, [rax+10h]
0x180011d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d8c  nop
0x180011d8d  add     rsp, 28h
0x180011d91  retn
```
