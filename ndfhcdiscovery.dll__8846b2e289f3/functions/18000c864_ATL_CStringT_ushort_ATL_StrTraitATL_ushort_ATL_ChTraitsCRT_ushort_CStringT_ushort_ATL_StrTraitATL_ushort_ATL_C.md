# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x18000c864`
- end: `0x18000c891`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800141b2`
- `0x18001421e`
- `0x1800142ae`
- `0x1800143c8`
- `0x1800143da`

## callees

- `0x18000c864`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1)
{
  volatile signed __int32 *v1; // rdx
  signed __int32 v2; // eax
  bool v3; // cc
  __int64 result; // rax

  v1 = (volatile signed __int32 *)(*a1 - 24LL);
  v2 = _InterlockedExchangeAdd(v1 + 4, 0xFFFFFFFF);
  v3 = v2 <= 1;
  result = (unsigned int)(v2 - 1);
  if ( v3 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  return result;
}

```

## disassembly

```asm
0x18000c864  sub     rsp, 28h
0x18000c868  mov     rdx, [rcx]
0x18000c86b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000c86f  or      eax, 0FFFFFFFFh
0x18000c872  lock xadd [rdx+10h], eax
0x18000c877  sub     eax, 1
0x18000c87a  jg      short loc_18000C88B
0x18000c87c  mov     rcx, [rdx]
0x18000c87f  mov     rax, [rcx]
0x18000c882  mov     rax, [rax+8]
0x18000c886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c88b  add     rsp, 28h
0x18000c88f  retn
```
