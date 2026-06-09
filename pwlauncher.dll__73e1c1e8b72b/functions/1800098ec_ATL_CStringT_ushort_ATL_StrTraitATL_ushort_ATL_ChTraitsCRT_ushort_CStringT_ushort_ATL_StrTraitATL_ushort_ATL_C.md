# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x1800098ec`
- end: `0x180009918`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18001060d`
- `0x18001061f`
- `0x180010638`
- `0x1800106a5`
- `0x1800106c9`
- `0x1800106db`
- `0x1800106ed`
- `0x18001072b`
- `0x180010a0e`

## callees

- `0x1800098ec`
- `0x180011010`

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
0x1800098ec  sub     rsp, 28h
0x1800098f0  mov     rdx, [rcx]
0x1800098f3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800098f7  or      eax, 0FFFFFFFFh
0x1800098fa  lock xadd [rdx+10h], eax
0x1800098ff  sub     eax, 1
0x180009902  jg      short loc_180009913
0x180009904  mov     rcx, [rdx]
0x180009907  mov     rax, [rcx]
0x18000990a  mov     rax, [rax+8]
0x18000990e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009913  add     rsp, 28h
0x180009917  retn
```
