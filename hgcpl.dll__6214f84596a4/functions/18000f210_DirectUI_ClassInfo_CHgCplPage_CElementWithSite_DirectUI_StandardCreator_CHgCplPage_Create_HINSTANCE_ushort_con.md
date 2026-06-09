# DirectUI::ClassInfo<CHgCplPage,CElementWithSite,DirectUI::StandardCreator<CHgCplPage>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CHgCplPage,CElementWithSite,DirectUI::StandardCreator<CHgCplPage>> * *)

- ea: `0x18000f210`
- end: `0x18000f2a7`
- name: `?Create@?$ClassInfo@VCHgCplPage@@VCElementWithSite@@V?$StandardCreator@VCHgCplPage@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f694`

## callees

- `0x18000766c`
- `0x18000f00c`
- `0x18000f210`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000f275`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000f275`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000f240`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000f240`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CHgCplPage,CElementWithSite,DirectUI::StandardCreator<CHgCplPage>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CHgCplPage,CElementWithSite,DirectUI::StandardCreator<CHgCplPage>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, (HINSTANCE)&_ImageBase, L"HgCplPage", 0, 0, 0);
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
0x18000f210  mov     [rsp+arg_0], rbx
0x18000f215  mov     [rsp+arg_8], rsi
0x18000f21a  push    rdi
0x18000f21b  sub     rsp, 30h
0x18000f21f  mov     rsi, [rsp+38h+arg_28]
0x18000f224  mov     ecx, 10h; this
0x18000f229  mov     qword ptr [rsi], 0
0x18000f230  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000f235  mov     rbx, rax
0x18000f238  test    rax, rax
0x18000f23b  jz      short loc_18000F290
0x18000f23d  mov     rcx, rax
0x18000f240  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x18000f246  lea     rax, ??_7?$ClassInfo@VCHgCplPage@@VCElementWithSite@@V?$StandardCreator@VCHgCplPage@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CHgCplPage,CElementWithSite,DirectUI::StandardCreator<CHgCplPage>>::`vftable'
0x18000f24d  mov     [rsp+38h+var_10], 0
0x18000f255  xor     r9d, r9d
0x18000f258  mov     [rbx], rax
0x18000f25b  lea     r8, aHgcplpage; "HgCplPage"
0x18000f262  mov     [rsp+38h+var_18], 0
0x18000f26b  lea     rdx, __ImageBase
0x18000f272  mov     rcx, rbx
0x18000f275  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18000f27b  mov     edi, eax
0x18000f27d  test    eax, eax
0x18000f27f  js      short loc_18000F286
0x18000f281  mov     [rsi], rbx
0x18000f284  jmp     short loc_18000F295
0x18000f286  mov     rcx, rbx; this
0x18000f289  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x18000f28e  jmp     short loc_18000F295
0x18000f290  mov     edi, 8007000Eh
0x18000f295  mov     rbx, [rsp+38h+arg_0]
0x18000f29a  mov     eax, edi
0x18000f29c  mov     rsi, [rsp+38h+arg_8]
0x18000f2a1  add     rsp, 30h
0x18000f2a5  pop     rdi
0x18000f2a6  retn
```
