# ATL::CComPtr<INDFHelperClassEnum>::~CComPtr<INDFHelperClassEnum>(void)

- ea: `0x180005588`
- end: `0x1800055a7`
- name: `??1?$CComPtr@UINDFHelperClassEnum@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013d3f`

## callees

- `0x180005588`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<INDFHelperClassEnum>::~CComPtr<INDFHelperClassEnum>(__int64 *a1)
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
0x180005588  sub     rsp, 28h
0x18000558c  mov     rcx, [rcx]
0x18000558f  test    rcx, rcx
0x180005592  jz      short loc_1800055A1
0x180005594  mov     rax, [rcx]
0x180005597  mov     rax, [rax+10h]
0x18000559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a0  nop
0x1800055a1  add     rsp, 28h
0x1800055a5  retn
```
