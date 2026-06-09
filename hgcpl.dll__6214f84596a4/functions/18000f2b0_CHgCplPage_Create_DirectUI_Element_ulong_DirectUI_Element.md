# CHgCplPage::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000f2b0`
- end: `0x18000f377`
- name: `?Create@CHgCplPage@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z`
- size: `199`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f380`

## callees

- `0x18000766c`
- `0x18000f03c`
- `0x18000f2b0`

## import_xrefs

- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18000f34e`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18000f34e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f364`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f364`

## pseudocode

```c
__int64 __fastcall CHgCplPage::Create(struct DirectUI::Element *a1, unsigned int *a2, struct DirectUI::Element **a3)
{
  int v6; // edi
  CElementWithSite *v7; // rax
  DirectUI::Element *v8; // rbx

  *a3 = 0;
  v6 = -2147024882;
  v7 = (CElementWithSite *)DirectUI::HAllocAndZero((DirectUI *)0x108, (unsigned __int64)a2);
  v8 = v7;
  if ( v7 )
  {
    CElementWithSite::CElementWithSite(v7);
    *((_QWORD *)v8 + 29) = 0;
    *(_QWORD *)v8 = &CHgCplPage::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v8 + 30) = 0;
    *((_QWORD *)v8 + 25) = &CHgCplPage::`vftable'{for `IUnknown'};
    *((_QWORD *)v8 + 31) = 0;
    *((_QWORD *)v8 + 26) = &CHgCplPage::`vftable'{for `CElementWithSite'};
    *((_QWORD *)v8 + 28) = &CHgCplPage::`vftable'{for `IFrameNotificationClient'};
    v6 = DirectUI::Element::Initialize(v8, 0, a1, a2);
    if ( v6 < 0 )
      DirectUI::Element::Destroy(v8, 1);
    else
      *a3 = v8;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000f2b0  push    rbx
0x18000f2b2  push    rbp
0x18000f2b3  push    rsi
0x18000f2b4  push    rdi
0x18000f2b5  push    r14
0x18000f2b7  sub     rsp, 20h
0x18000f2bb  mov     r14, rcx
0x18000f2be  mov     qword ptr [r8], 0
0x18000f2c5  mov     ecx, 108h; this
0x18000f2ca  mov     rsi, r8
0x18000f2cd  mov     rbp, rdx
0x18000f2d0  mov     edi, 8007000Eh
0x18000f2d5  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000f2da  mov     rbx, rax
0x18000f2dd  test    rax, rax
0x18000f2e0  jz      loc_18000F36A
0x18000f2e6  mov     rcx, rax; this
0x18000f2e9  call    ??0CElementWithSite@@QEAA@XZ; CElementWithSite::CElementWithSite(void)
0x18000f2ee  lea     rax, ??_7CHgCplPage@@6BElement@DirectUI@@@; const CHgCplPage::`vftable'{for `DirectUI::Element'}
0x18000f2f5  mov     qword ptr [rbx+0E8h], 0
0x18000f300  mov     [rbx], rax
0x18000f303  mov     r9, rbp
0x18000f306  lea     rax, ??_7CHgCplPage@@6BIUnknown@@@; const CHgCplPage::`vftable'{for `IUnknown'}
0x18000f30d  mov     qword ptr [rbx+0F0h], 0
0x18000f318  mov     [rbx+0C8h], rax
0x18000f31f  mov     r8, r14
0x18000f322  lea     rax, ??_7CHgCplPage@@6BCElementWithSite@@@; const CHgCplPage::`vftable'{for `CElementWithSite'}
0x18000f329  mov     qword ptr [rbx+0F8h], 0
0x18000f334  mov     [rbx+0D0h], rax
0x18000f33b  xor     edx, edx
0x18000f33d  lea     rax, ??_7CHgCplPage@@6BIFrameNotificationClient@@@; const CHgCplPage::`vftable'{for `IFrameNotificationClient'}
0x18000f344  mov     rcx, rbx
0x18000f347  mov     [rbx+0E0h], rax
0x18000f34e  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18000f354  mov     edi, eax
0x18000f356  test    eax, eax
0x18000f358  js      short loc_18000F35F
0x18000f35a  mov     [rsi], rbx
0x18000f35d  jmp     short loc_18000F36A
0x18000f35f  mov     dl, 1
0x18000f361  mov     rcx, rbx
0x18000f364  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000f36a  mov     eax, edi
0x18000f36c  add     rsp, 20h
0x18000f370  pop     r14
0x18000f372  pop     rdi
0x18000f373  pop     rsi
0x18000f374  pop     rbp
0x18000f375  pop     rbx
0x18000f376  retn
```
