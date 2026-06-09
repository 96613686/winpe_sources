# ATL::CComPtr<IStream>::~CComPtr<IStream>(void)

- ea: `0x180009bd8`
- end: `0x180009bf6`
- name: `??1?$CComPtr@UIStream@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008820`
- `0x180024960`

## callees

- `0x180009bd8`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IStream>::~CComPtr<IStream>(__int64 *a1)
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
0x180009bd8  sub     rsp, 28h
0x180009bdc  mov     rcx, [rcx]
0x180009bdf  test    rcx, rcx
0x180009be2  jz      short loc_180009BF1
0x180009be4  mov     rax, [rcx]
0x180009be7  mov     rax, [rax+10h]
0x180009beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf0  nop
0x180009bf1  add     rsp, 28h
0x180009bf5  retn
```
