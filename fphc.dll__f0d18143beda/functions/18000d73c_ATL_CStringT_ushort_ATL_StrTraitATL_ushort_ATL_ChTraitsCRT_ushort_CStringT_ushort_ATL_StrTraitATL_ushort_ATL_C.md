# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x18000d73c`
- end: `0x18000d768`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800119ad`
- `0x180011a1f`
- `0x180011a35`
- `0x180011a61`
- `0x180011a73`
- `0x180011a97`
- `0x180011b01`
- `0x180011b13`
- `0x180011b25`
- `0x180011b94`
- `0x180011ba6`

## callees

- `0x18000d73c`
- `0x180012010`

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
0x18000d73c  sub     rsp, 28h
0x18000d740  mov     rdx, [rcx]
0x18000d743  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000d747  or      eax, 0FFFFFFFFh
0x18000d74a  lock xadd [rdx+10h], eax
0x18000d74f  sub     eax, 1
0x18000d752  jg      short loc_18000D763
0x18000d754  mov     rcx, [rdx]
0x18000d757  mov     rax, [rcx]
0x18000d75a  mov     rax, [rax+8]
0x18000d75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d763  add     rsp, 28h
0x18000d767  retn
```
