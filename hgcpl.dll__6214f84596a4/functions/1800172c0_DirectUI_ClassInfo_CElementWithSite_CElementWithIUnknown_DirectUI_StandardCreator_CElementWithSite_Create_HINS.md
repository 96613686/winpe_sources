# DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> * *)

- ea: `0x1800172c0`
- end: `0x180017357`
- name: `?Create@?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017634`

## callees

- `0x18000766c`
- `0x18000f00c`
- `0x1800172c0`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017325`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017325`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x1800172f0`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x1800172f0`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Create(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        DirectUI::ClassInfoBase **a6)
{
  DirectUI::ClassInfoBase *v6; // rax
  DirectUI::ClassInfoBase *v7; // rbx
  int v8; // edi

  *a6 = 0;
  v6 = (DirectUI::ClassInfoBase *)DirectUI::HAllocAndZero((DirectUI *)0x10, a2);
  v7 = v6;
  if ( v6 )
  {
    DirectUI::ClassInfoBase::ClassInfoBase(v6);
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, (HINSTANCE)&_ImageBase, L"CElementWithSite", 0, 0, 0);
    if ( v8 < 0 )
      DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(v7);
    else
      *a6 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800172c0  mov     [rsp+arg_0], rbx
0x1800172c5  mov     [rsp+arg_8], rsi
0x1800172ca  push    rdi
0x1800172cb  sub     rsp, 30h
0x1800172cf  mov     rsi, [rsp+38h+arg_28]
0x1800172d4  mov     ecx, 10h; this
0x1800172d9  mov     qword ptr [rsi], 0
0x1800172e0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800172e5  mov     rbx, rax
0x1800172e8  test    rax, rax
0x1800172eb  jz      short loc_180017340
0x1800172ed  mov     rcx, rax
0x1800172f0  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x1800172f6  lea     rax, ??_7?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::`vftable'
0x1800172fd  mov     [rsp+38h+var_10], 0
0x180017305  xor     r9d, r9d
0x180017308  mov     [rbx], rax
0x18001730b  lea     r8, aCelementwithsi; "CElementWithSite"
0x180017312  mov     [rsp+38h+var_18], 0
0x18001731b  lea     rdx, __ImageBase
0x180017322  mov     rcx, rbx
0x180017325  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18001732b  mov     edi, eax
0x18001732d  test    eax, eax
0x18001732f  js      short loc_180017336
0x180017331  mov     [rsi], rbx
0x180017334  jmp     short loc_180017345
0x180017336  mov     rcx, rbx; this
0x180017339  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x18001733e  jmp     short loc_180017345
0x180017340  mov     edi, 8007000Eh
0x180017345  mov     rbx, [rsp+38h+arg_0]
0x18001734a  mov     eax, edi
0x18001734c  mov     rsi, [rsp+38h+arg_8]
0x180017351  add     rsp, 30h
0x180017355  pop     rdi
0x180017356  retn
```
