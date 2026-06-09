# DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>> * *)

- ea: `0x180017a78`
- end: `0x180017b12`
- name: `?Create@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800180f0`

## callees

- `0x18000766c`
- `0x18000f00c`
- `0x180017a78`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017ae0`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017ae0`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017aa8`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017aa8`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(
           v7,
           (HINSTANCE)&_ImageBase,
           L"FocusIndicator",
           0,
           (const struct DirectUI::PropertyInfo *const *)off_18001C658,
           1u);
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
0x180017a78  mov     [rsp+arg_0], rbx
0x180017a7d  mov     [rsp+arg_8], rsi
0x180017a82  push    rdi
0x180017a83  sub     rsp, 30h
0x180017a87  mov     rsi, [rsp+38h+arg_28]
0x180017a8c  mov     ecx, 10h; this
0x180017a91  mov     qword ptr [rsi], 0
0x180017a98  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180017a9d  mov     rbx, rax
0x180017aa0  test    rax, rax
0x180017aa3  jz      short loc_180017AFB
0x180017aa5  mov     rcx, rax
0x180017aa8  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180017aae  lea     rax, ??_7?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::`vftable'
0x180017ab5  mov     [rsp+38h+var_10], 1
0x180017abd  mov     [rbx], rax
0x180017ac0  lea     r8, aFocusindicator; "FocusIndicator"
0x180017ac7  lea     rax, off_18001C658
0x180017ace  xor     r9d, r9d
0x180017ad1  lea     rdx, __ImageBase
0x180017ad8  mov     [rsp+38h+var_18], rax
0x180017add  mov     rcx, rbx
0x180017ae0  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180017ae6  mov     edi, eax
0x180017ae8  test    eax, eax
0x180017aea  js      short loc_180017AF1
0x180017aec  mov     [rsi], rbx
0x180017aef  jmp     short loc_180017B00
0x180017af1  mov     rcx, rbx; this
0x180017af4  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x180017af9  jmp     short loc_180017B00
0x180017afb  mov     edi, 8007000Eh
0x180017b00  mov     rbx, [rsp+38h+arg_0]
0x180017b05  mov     eax, edi
0x180017b07  mov     rsi, [rsp+38h+arg_8]
0x180017b0c  add     rsp, 30h
0x180017b10  pop     rdi
0x180017b11  retn
```
