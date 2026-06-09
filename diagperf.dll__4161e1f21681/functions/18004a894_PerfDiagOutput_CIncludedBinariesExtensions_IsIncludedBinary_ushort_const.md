# PerfDiagOutput::CIncludedBinariesExtensions::IsIncludedBinary(ushort const *)

- ea: `0x18004a894`
- end: `0x18004a914`
- name: `?IsIncludedBinary@CIncludedBinariesExtensions@PerfDiagOutput@@QEAA_NPEBG@Z`
- size: `128`
- prototype: `bool(PerfDiagOutput::CIncludedBinariesExtensions *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004e378`

## callees

- `0x18001769c`
- `0x180017758`
- `0x1800177b4`
- `0x18004a894`
- `0x18004a91c`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18004a8a0`
- `SHLWAPI!PathFindExtensionW` at `0x18004a8a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall PerfDiagOutput::CIncludedBinariesExtensions::IsIncludedBinary(
        PerfDiagOutput::CIncludedBinariesExtensions *this,
        const unsigned __int16 *a2)
{
  LPWSTR ExtensionW; // rdx
  __int64 v4; // rcx
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  ExtensionW = PathFindExtensionW(a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v6,
    ExtensionW);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v6);
  v4 = v6;
  if ( *(_DWORD *)(v6 - 16) )
  {
    if ( (unsigned __int8)std::binary_search<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool (*)(ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &)>(
                            *((_QWORD *)this + 2),
                            *((_QWORD *)this + 3),
                            &v6,
                            PerfDiagOutput::CIgnoredSystemBinariesFilter::Lesser) )
    {
      ATL::CStringData::Release((ATL::CStringData *)(v6 - 24));
      return 1;
    }
    v4 = v6;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 24));
  return 0;
}

```

## disassembly

```asm
0x18004a894  push    rbx
0x18004a896  sub     rsp, 20h
0x18004a89a  mov     rbx, rcx
0x18004a89d  mov     rcx, rdx; pszPath
0x18004a8a0  call    cs:__imp_PathFindExtensionW
0x18004a8a6  mov     rdx, rax
0x18004a8a9  lea     rcx, [rsp+28h+arg_10]
0x18004a8ae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004a8b3  nop
0x18004a8b4  lea     rcx, [rsp+28h+arg_10]
0x18004a8b9  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18004a8be  mov     rcx, [rsp+28h+arg_10]
0x18004a8c3  cmp     dword ptr [rcx-10h], 0
0x18004a8c7  jz      short loc_18004A8FD
0x18004a8c9  lea     r9, ?Lesser@CIgnoredSystemBinariesFilter@PerfDiagOutput@@CA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PerfDiagOutput::CIgnoredSystemBinariesFilter::Lesser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004a8d0  lea     r8, [rsp+28h+arg_10]
0x18004a8d5  mov     rdx, [rbx+18h]
0x18004a8d9  mov     rcx, [rbx+10h]
0x18004a8dd  call    ??$binary_search@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@P6A_NAEBV34@0@Z@std@@YA_NV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@0@0AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@P6A_N11@Z@Z; std::binary_search<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool (*)(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool (*)(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &))
0x18004a8e2  test    al, al
0x18004a8e4  jz      short loc_18004A8F8
0x18004a8e6  mov     rcx, [rsp+28h+arg_10]
0x18004a8eb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004a8ef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004a8f4  mov     al, 1
0x18004a8f6  jmp     short loc_18004A90D
0x18004a8f8  mov     rcx, [rsp+28h+arg_10]
0x18004a8fd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004a901  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004a906  nop
0x18004a907  jmp     short loc_18004A90B
0x18004a909  jmp     short $+2
0x18004a90b  xor     al, al
0x18004a90d  add     rsp, 20h
0x18004a911  pop     rbx
0x18004a912  retn
```
