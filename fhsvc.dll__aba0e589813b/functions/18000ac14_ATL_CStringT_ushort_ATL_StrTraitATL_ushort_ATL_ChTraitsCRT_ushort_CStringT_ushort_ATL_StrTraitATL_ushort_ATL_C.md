# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x18000ac14`
- end: `0x18000ac40`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `35`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065c0`
- `0x180009fd0`
- `0x18000a148`
- `0x18000a254`
- `0x18000a360`
- `0x18000aa08`
- `0x18000dca4`
- `0x18000dd60`
- `0x18000df70`
- `0x18000e2f0`
- `0x18000e5d0`
- `0x18000e740`
- `0x18000e8b0`
- `0x18000edc8`
- `0x18000ee2c`
- `0x18000ee74`
- `0x18000ee9c`
- `0x18000efb4`
- `0x18000feb4`
- `0x180010848`
- `0x180010964`
- `0x180011a90`
- `0x180011ab0`
- `0x180011c30`
- `0x180011d4c`
- `0x180011d5e`
- `0x180011d70`
- `0x180011d82`
- `0x180011e6c`
- `0x180011f52`
- `0x180011f7e`
- `0x18001203d`
- `0x1800123dd`
- `0x180012530`
- `0x18001260a`

## callees

- `0x18000ac14`
- `0x180013010`

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
0x18000ac14  sub     rsp, 28h
0x18000ac18  mov     rdx, [rcx]
0x18000ac1b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000ac1f  or      eax, 0FFFFFFFFh
0x18000ac22  lock xadd [rdx+10h], eax
0x18000ac27  sub     eax, 1
0x18000ac2a  jg      short loc_18000AC3B
0x18000ac2c  mov     rcx, [rdx]
0x18000ac2f  mov     rax, [rcx]
0x18000ac32  mov     rax, [rax+8]
0x18000ac36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac3b  add     rsp, 28h
0x18000ac3f  retn
```
