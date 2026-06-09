# ATL::CComPtr<IEnrollEngine>::~CComPtr<IEnrollEngine>(void)

- ea: `0x180005e94`
- end: `0x180005eb3`
- name: `??1?$CComPtr@UIEnrollEngine@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c26`
- `0x180006c38`

## callees

- `0x180005e94`
- `0x180007010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IEnrollEngine>::~CComPtr<IEnrollEngine>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 112LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180005e94  sub     rsp, 28h
0x180005e98  mov     rcx, [rcx]
0x180005e9b  test    rcx, rcx
0x180005e9e  jz      short loc_180005EAD
0x180005ea0  mov     rax, [rcx]
0x180005ea3  mov     rax, [rax+70h]
0x180005ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eac  nop
0x180005ead  add     rsp, 28h
0x180005eb1  retn
```
