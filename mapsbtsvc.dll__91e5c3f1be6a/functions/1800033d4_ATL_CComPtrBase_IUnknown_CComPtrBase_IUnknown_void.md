# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x1800033d4`
- end: `0x1800033f2`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800033bc`
- `0x180003730`
- `0x180004940`
- `0x18000b544`
- `0x18000bb70`
- `0x18000c4dc`
- `0x18000cba4`
- `0x18000cd7c`
- `0x18000cfec`
- `0x18000dd10`
- `0x18000eb80`
- `0x18000ecb8`
- `0x18000ee60`
- `0x18000ef18`
- `0x18000f9cc`
- `0x1800108e8`
- `0x18001117c`
- `0x180011ad0`
- `0x18001224c`
- `0x18001240c`

## callees

- `0x1800033d4`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x1800033d4  sub     rsp, 28h
0x1800033d8  mov     rcx, [rcx]
0x1800033db  test    rcx, rcx
0x1800033de  jz      short loc_1800033ED
0x1800033e0  mov     rax, [rcx]
0x1800033e3  mov     rax, [rax+10h]
0x1800033e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ec  nop
0x1800033ed  add     rsp, 28h
0x1800033f1  retn
```
