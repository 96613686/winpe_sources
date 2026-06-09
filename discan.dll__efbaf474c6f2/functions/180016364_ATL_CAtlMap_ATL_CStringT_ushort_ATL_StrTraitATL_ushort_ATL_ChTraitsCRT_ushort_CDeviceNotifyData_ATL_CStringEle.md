# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::RemoveAll(void)

- ea: `0x180016364`
- end: `0x1800163f9`
- name: `?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceNotifyData@@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@PEAVCDeviceNotifyData@@@2@@ATL@@QEAAXXZ`
- size: `149`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180013820`
- `0x18001ac20`

## callees

- `0x180001bc4`
- `0x180014840`
- `0x1800148c0`
- `0x1800153a0`
- `0x180015e3c`
- `0x180016364`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<CDeviceNotifyData *>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdx
  unsigned int v5; // eax
  __int64 result; // rax

  ++*(_DWORD *)(a1 + 48);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
      while ( v3 )
      {
        v4 = v3;
        v3 = *(_QWORD *)(v3 + 16);
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<CDeviceNotifyData *>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  operator delete(*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<CDeviceNotifyData *>>::PickSize(
           a1,
           0);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<CDeviceNotifyData *>>::InitHashTable(
      a1,
      v5,
      0);
  }
  result = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<CDeviceNotifyData *>>::FreePlexes(a1);
  --*(_DWORD *)(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x180016364  mov     [rsp+arg_0], rbx
0x180016369  mov     [rsp+arg_8], rsi
0x18001636e  push    rdi
0x18001636f  sub     rsp, 20h
0x180016373  mov     rbx, rcx
0x180016376  inc     dword ptr [rcx+30h]
0x180016379  cmp     qword ptr [rcx], 0
0x18001637d  jz      short loc_1800163AA
0x18001637f  xor     edi, edi
0x180016381  cmp     [rcx+10h], edi
0x180016384  jbe     short loc_1800163AA
0x180016386  mov     rax, [rbx]
0x180016389  mov     rsi, [rax+rdi*8]
0x18001638d  jmp     short loc_18001639E
0x18001638f  mov     rdx, rsi
0x180016392  mov     rsi, [rsi+10h]
0x180016396  mov     rcx, rbx
0x180016399  call    ?FreeNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceNotifyData@@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@PEAVCDeviceNotifyData@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::FreeNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::CNode *)
0x18001639e  test    rsi, rsi
0x1800163a1  jnz     short loc_18001638F
0x1800163a3  inc     edi
0x1800163a5  cmp     edi, [rbx+10h]
0x1800163a8  jb      short loc_180016386
0x1800163aa  mov     rcx, [rbx]; Block
0x1800163ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800163b2  mov     qword ptr [rbx], 0
0x1800163b9  mov     qword ptr [rbx+8], 0
0x1800163c1  cmp     dword ptr [rbx+30h], 0
0x1800163c5  jnz     short loc_1800163DE
0x1800163c7  xor     edx, edx
0x1800163c9  mov     rcx, rbx
0x1800163cc  call    ?PickSize@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceNotifyData@@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@PEAVCDeviceNotifyData@@@2@@ATL@@AEBAI_K@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::PickSize(unsigned __int64)
0x1800163d1  mov     edx, eax
0x1800163d3  xor     r8d, r8d
0x1800163d6  mov     rcx, rbx
0x1800163d9  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceNotifyData@@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@PEAVCDeviceNotifyData@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::InitHashTable(uint,bool)
0x1800163de  mov     rcx, rbx
0x1800163e1  call    ?FreePlexes@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCDeviceNotifyData@@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@PEAVCDeviceNotifyData@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CDeviceNotifyData *,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<CDeviceNotifyData *>>::FreePlexes(void)
0x1800163e6  dec     dword ptr [rbx+30h]
0x1800163e9  mov     rbx, [rsp+28h+arg_0]
0x1800163ee  mov     rsi, [rsp+28h+arg_8]
0x1800163f3  add     rsp, 20h
0x1800163f7  pop     rdi
0x1800163f8  retn
```
