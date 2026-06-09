# ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)

- ea: `0x180008ab0`
- end: `0x180008ace`
- name: `??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e11c`
- `0x18000f0f4`
- `0x1800100c4`
- `0x1800126e4`
- `0x180013310`
- `0x180013e14`
- `0x180015370`
- `0x1800154ec`
- `0x180015abc`
- `0x1800161f4`
- `0x180016490`
- `0x180016570`
- `0x18001f84b`
- `0x18001f86f`
- `0x18001f881`
- `0x18001f893`
- `0x18001f9f9`
- `0x18001fe33`
- `0x1800204c2`
- `0x180020552`
- `0x18002072c`
- `0x18002073e`
- `0x180020750`
- `0x1800207ec`
- `0x1800207fe`
- `0x180020810`
- `0x180020822`
- `0x1800208e0`
- `0x180020946`

## callees

- `0x180008ab0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(__int64 *a1)
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
0x180008ab0  sub     rsp, 28h
0x180008ab4  mov     rcx, [rcx]
0x180008ab7  test    rcx, rcx
0x180008aba  jz      short loc_180008AC9
0x180008abc  mov     rax, [rcx]
0x180008abf  mov     rax, [rax+10h]
0x180008ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac8  nop
0x180008ac9  add     rsp, 28h
0x180008acd  retn
```
