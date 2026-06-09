# ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>(void)

- ea: `0x18000bd40`
- end: `0x18000bd5e`
- name: `??1?$CComPtr@UIFhTarget@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011a50`
- `0x180011b20`
- `0x180012075`
- `0x180012550`
- `0x180012570`

## callees

- `0x18000bd40`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>(__int64 *a1)
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
0x18000bd40  sub     rsp, 28h
0x18000bd44  mov     rcx, [rcx]
0x18000bd47  test    rcx, rcx
0x18000bd4a  jz      short loc_18000BD59
0x18000bd4c  mov     rax, [rcx]
0x18000bd4f  mov     rax, [rax+10h]
0x18000bd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd58  nop
0x18000bd59  add     rsp, 28h
0x18000bd5d  retn
```
