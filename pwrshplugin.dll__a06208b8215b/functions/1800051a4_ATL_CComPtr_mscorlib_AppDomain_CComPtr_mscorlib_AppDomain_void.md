# ATL::CComPtr<mscorlib::_AppDomain>::~CComPtr<mscorlib::_AppDomain>(void)

- ea: `0x1800051a4`
- end: `0x1800051c2`
- name: `??1?$CComPtr@U_AppDomain@mscorlib@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009b2f`
- `0x180009e52`
- `0x180009e7e`
- `0x180009e90`
- `0x180009ea2`
- `0x180009eea`

## callees

- `0x1800051a4`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<mscorlib::_AppDomain>::~CComPtr<mscorlib::_AppDomain>(__int64 *a1)
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
0x1800051a4  sub     rsp, 28h
0x1800051a8  mov     rcx, [rcx]
0x1800051ab  test    rcx, rcx
0x1800051ae  jz      short loc_1800051BD
0x1800051b0  mov     rax, [rcx]
0x1800051b3  mov     rax, [rax+10h]
0x1800051b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051bc  nop
0x1800051bd  add     rsp, 28h
0x1800051c1  retn
```
