# DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>> * *)

- ea: `0x180017360`
- end: `0x1800173fa`
- name: `?Create@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001774c`

## callees

- `0x18000766c`
- `0x18000f00c`
- `0x180017360`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x1800173c8`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x1800173c8`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017390`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017390`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(
           v7,
           (HINSTANCE)&_ImageBase,
           L"CFrameModule",
           0,
           (const struct DirectUI::PropertyInfo *const *)&off_18001C640,
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
0x180017360  mov     [rsp+arg_0], rbx
0x180017365  mov     [rsp+arg_8], rsi
0x18001736a  push    rdi
0x18001736b  sub     rsp, 30h
0x18001736f  mov     rsi, [rsp+38h+arg_28]
0x180017374  mov     ecx, 10h; this
0x180017379  mov     qword ptr [rsi], 0
0x180017380  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180017385  mov     rbx, rax
0x180017388  test    rax, rax
0x18001738b  jz      short loc_1800173E3
0x18001738d  mov     rcx, rax
0x180017390  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180017396  lea     rax, ??_7?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::`vftable'
0x18001739d  mov     [rsp+38h+var_10], 1
0x1800173a5  mov     [rbx], rax
0x1800173a8  lea     r8, aCframemodule; "CFrameModule"
0x1800173af  lea     rax, off_18001C640
0x1800173b6  xor     r9d, r9d
0x1800173b9  lea     rdx, __ImageBase
0x1800173c0  mov     [rsp+38h+var_18], rax
0x1800173c5  mov     rcx, rbx
0x1800173c8  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x1800173ce  mov     edi, eax
0x1800173d0  test    eax, eax
0x1800173d2  js      short loc_1800173D9
0x1800173d4  mov     [rsi], rbx
0x1800173d7  jmp     short loc_1800173E8
0x1800173d9  mov     rcx, rbx; this
0x1800173dc  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x1800173e1  jmp     short loc_1800173E8
0x1800173e3  mov     edi, 8007000Eh
0x1800173e8  mov     rbx, [rsp+38h+arg_0]
0x1800173ed  mov     eax, edi
0x1800173ef  mov     rsi, [rsp+38h+arg_8]
0x1800173f4  add     rsp, 30h
0x1800173f8  pop     rdi
0x1800173f9  retn
```
