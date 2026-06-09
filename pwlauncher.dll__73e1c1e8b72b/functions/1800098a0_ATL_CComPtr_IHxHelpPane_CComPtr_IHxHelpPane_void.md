# ATL::CComPtr<IHxHelpPane>::~CComPtr<IHxHelpPane>(void)

- ea: `0x1800098a0`
- end: `0x1800098be`
- name: `??1?$CComPtr@UIHxHelpPane@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001064a`
- `0x1800109e2`
- `0x180010a44`

## callees

- `0x1800098a0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IHxHelpPane>::~CComPtr<IHxHelpPane>(__int64 *a1)
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
0x1800098a0  sub     rsp, 28h
0x1800098a4  mov     rcx, [rcx]
0x1800098a7  test    rcx, rcx
0x1800098aa  jz      short loc_1800098B9
0x1800098ac  mov     rax, [rcx]
0x1800098af  mov     rax, [rax+10h]
0x1800098b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098b8  nop
0x1800098b9  add     rsp, 28h
0x1800098bd  retn
```
