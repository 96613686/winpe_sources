# DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>> * *)

- ea: `0x180017220`
- end: `0x1800172b7`
- name: `?Create@?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001750c`

## callees

- `0x18000766c`
- `0x18000f00c`
- `0x180017220`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017285`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017285`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017250`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017250`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, (HINSTANCE)&_ImageBase, L"CElementWithIUnknown", 0, 0, 0);
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
0x180017220  mov     [rsp+arg_0], rbx
0x180017225  mov     [rsp+arg_8], rsi
0x18001722a  push    rdi
0x18001722b  sub     rsp, 30h
0x18001722f  mov     rsi, [rsp+38h+arg_28]
0x180017234  mov     ecx, 10h; this
0x180017239  mov     qword ptr [rsi], 0
0x180017240  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180017245  mov     rbx, rax
0x180017248  test    rax, rax
0x18001724b  jz      short loc_1800172A0
0x18001724d  mov     rcx, rax
0x180017250  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180017256  lea     rax, ??_7?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::`vftable'
0x18001725d  mov     [rsp+38h+var_10], 0
0x180017265  xor     r9d, r9d
0x180017268  mov     [rbx], rax
0x18001726b  lea     r8, aCelementwithiu; "CElementWithIUnknown"
0x180017272  mov     [rsp+38h+var_18], 0
0x18001727b  lea     rdx, __ImageBase
0x180017282  mov     rcx, rbx
0x180017285  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18001728b  mov     edi, eax
0x18001728d  test    eax, eax
0x18001728f  js      short loc_180017296
0x180017291  mov     [rsi], rbx
0x180017294  jmp     short loc_1800172A5
0x180017296  mov     rcx, rbx; this
0x180017299  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x18001729e  jmp     short loc_1800172A5
0x1800172a0  mov     edi, 8007000Eh
0x1800172a5  mov     rbx, [rsp+38h+arg_0]
0x1800172aa  mov     eax, edi
0x1800172ac  mov     rsi, [rsp+38h+arg_8]
0x1800172b1  add     rsp, 30h
0x1800172b5  pop     rdi
0x1800172b6  retn
```
