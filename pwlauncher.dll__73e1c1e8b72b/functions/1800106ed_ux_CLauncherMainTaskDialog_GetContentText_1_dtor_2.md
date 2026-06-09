# _ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor$2

- ea: `0x1800106ed`
- end: `0x180010713`
- name: `_ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor$2`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800098ec`
- `0x1800106ed`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::GetContentText_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(*(_QWORD **)(a2 + 120));
  }
  return result;
}

```

## disassembly

```asm
0x1800106ed  push    rbp
0x1800106ef  sub     rsp, 20h
0x1800106f3  mov     rbp, rdx
0x1800106f6  mov     eax, [rbp+30h]
0x1800106f9  and     eax, 1
0x1800106fc  test    eax, eax
0x1800106fe  jz      short loc_18001070D
0x180010700  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x180010704  mov     rcx, [rbp+78h]
0x180010708  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001070d  add     rsp, 20h
0x180010711  pop     rbp
0x180010712  retn
```
