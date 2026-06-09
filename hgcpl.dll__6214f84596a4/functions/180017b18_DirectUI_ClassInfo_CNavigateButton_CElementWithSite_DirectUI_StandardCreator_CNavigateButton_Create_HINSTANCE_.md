# DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>> * *)

- ea: `0x180017b18`
- end: `0x180017bb2`
- name: `?Create@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018220`

## callees

- `0x18000766c`
- `0x18000f00c`
- `0x180017b18`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017b80`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180017b80`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017b48`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180017b48`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(
           v7,
           (HINSTANCE)&_ImageBase,
           L"NavigateButton",
           0,
           (const struct DirectUI::PropertyInfo *const *)off_18001C660,
           6u);
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
0x180017b18  mov     [rsp+arg_0], rbx
0x180017b1d  mov     [rsp+arg_8], rsi
0x180017b22  push    rdi
0x180017b23  sub     rsp, 30h
0x180017b27  mov     rsi, [rsp+38h+arg_28]
0x180017b2c  mov     ecx, 10h; this
0x180017b31  mov     qword ptr [rsi], 0
0x180017b38  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180017b3d  mov     rbx, rax
0x180017b40  test    rax, rax
0x180017b43  jz      short loc_180017B9B
0x180017b45  mov     rcx, rax
0x180017b48  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180017b4e  lea     rax, ??_7?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::`vftable'
0x180017b55  mov     [rsp+38h+var_10], 6
0x180017b5d  mov     [rbx], rax
0x180017b60  lea     r8, aNavigatebutton; "NavigateButton"
0x180017b67  lea     rax, off_18001C660
0x180017b6e  xor     r9d, r9d
0x180017b71  lea     rdx, __ImageBase
0x180017b78  mov     [rsp+38h+var_18], rax
0x180017b7d  mov     rcx, rbx
0x180017b80  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180017b86  mov     edi, eax
0x180017b88  test    eax, eax
0x180017b8a  js      short loc_180017B91
0x180017b8c  mov     [rsi], rbx
0x180017b8f  jmp     short loc_180017BA0
0x180017b91  mov     rcx, rbx; this
0x180017b94  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x180017b99  jmp     short loc_180017BA0
0x180017b9b  mov     edi, 8007000Eh
0x180017ba0  mov     rbx, [rsp+38h+arg_0]
0x180017ba5  mov     eax, edi
0x180017ba7  mov     rsi, [rsp+38h+arg_8]
0x180017bac  add     rsp, 30h
0x180017bb0  pop     rdi
0x180017bb1  retn
```
