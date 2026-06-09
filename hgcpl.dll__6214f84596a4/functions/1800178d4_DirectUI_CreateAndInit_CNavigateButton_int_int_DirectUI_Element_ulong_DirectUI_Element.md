# DirectUI::CreateAndInit<CNavigateButton,int>(int,DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800178d4`
- end: `0x180017966`
- name: `??$CreateAndInit@VCNavigateButton@@H@DirectUI@@YAJHPEAVElement@0@PEAKPEAPEAV10@@Z`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017c50`

## callees

- `0x18000766c`
- `0x18000f03c`
- `0x1800178d4`

## import_xrefs

- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180017938`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180017938`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001794e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001794e`

## pseudocode

```c
__int64 __fastcall DirectUI::CreateAndInit<CNavigateButton,int>(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  CElementWithSite *v7; // rax
  DirectUI::Element *v8; // rbx
  int v9; // edi

  *a4 = 0;
  v7 = (CElementWithSite *)DirectUI::HAllocAndZero((DirectUI *)0xE0, (unsigned __int64)a2);
  v8 = v7;
  if ( v7 )
  {
    CElementWithSite::CElementWithSite(v7);
    *(_QWORD *)v8 = &CNavigateButton::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v8 + 25) = &CNavigateButton::`vftable'{for `IUnknown'};
    *((_QWORD *)v8 + 26) = &CNavigateButton::`vftable';
    v9 = DirectUI::Element::Initialize(v8, 0, a2, a3);
    if ( v9 < 0 )
      DirectUI::Element::Destroy(v8, 0);
    else
      *a4 = v8;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800178d4  push    rbx
0x1800178d6  push    rbp
0x1800178d7  push    rsi
0x1800178d8  push    rdi
0x1800178d9  sub     rsp, 28h
0x1800178dd  mov     ecx, 0E0h; this
0x1800178e2  mov     qword ptr [r9], 0
0x1800178e9  mov     rsi, r9
0x1800178ec  mov     rdi, r8
0x1800178ef  mov     rbp, rdx
0x1800178f2  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800178f7  mov     rbx, rax
0x1800178fa  test    rax, rax
0x1800178fd  jz      short loc_180017956
0x1800178ff  mov     rcx, rax; this
0x180017902  call    ??0CElementWithSite@@QEAA@XZ; CElementWithSite::CElementWithSite(void)
0x180017907  lea     rax, ??_7CNavigateButton@@6BElement@DirectUI@@@; const CNavigateButton::`vftable'{for `DirectUI::Element'}
0x18001790e  mov     r9, rdi
0x180017911  mov     [rbx], rax
0x180017914  mov     r8, rbp
0x180017917  lea     rax, ??_7CNavigateButton@@6BIUnknown@@@; const CNavigateButton::`vftable'{for `IUnknown'}
0x18001791e  xor     edx, edx
0x180017920  mov     [rbx+0C8h], rax
0x180017927  mov     rcx, rbx
0x18001792a  lea     rax, ??_7CNavigateButton@@6B@; const CNavigateButton::`vftable'
0x180017931  mov     [rbx+0D0h], rax
0x180017938  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18001793e  mov     edi, eax
0x180017940  test    eax, eax
0x180017942  js      short loc_180017949
0x180017944  mov     [rsi], rbx
0x180017947  jmp     short loc_18001795B
0x180017949  xor     edx, edx
0x18001794b  mov     rcx, rbx
0x18001794e  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180017954  jmp     short loc_18001795B
0x180017956  mov     edi, 8007000Eh
0x18001795b  mov     eax, edi
0x18001795d  add     rsp, 28h
0x180017961  pop     rdi
0x180017962  pop     rsi
0x180017963  pop     rbp
0x180017964  pop     rbx
0x180017965  retn
```
