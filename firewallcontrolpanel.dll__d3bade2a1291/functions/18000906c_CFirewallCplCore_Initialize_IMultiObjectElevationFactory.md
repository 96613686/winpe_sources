# CFirewallCplCore::Initialize(IMultiObjectElevationFactory *)

- ea: `0x18000906c`
- end: `0x180009180`
- name: `?Initialize@CFirewallCplCore@@QEAAJPEAUIMultiObjectElevationFactory@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(CFirewallCplCore *this, IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f2c0`

## callees

- `0x18000906c`
- `0x180009b30`
- `0x18001c384`
- `0x18001d570`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18000913a`
- `SHCORE!IUnknown_Set` at `0x18000913a`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180009164`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180009164`
- `DUI70!??0Proxy@DirectUI@@QEAA@XZ` at `0x18000909b`
- `DUI70!??0Proxy@DirectUI@@QEAA@XZ` at `0x18000909b`

## pseudocode

```c
__int64 __fastcall CFirewallCplCore::Initialize(CFirewallCplCore *this, IUnknown *a2)
{
  DirectUI::Proxy *v4; // rax
  unsigned __int64 v5; // rdx
  DirectUI::Proxy *v6; // rbx
  CFwProfileMgr *v7; // rax
  CFwProfileMgr *v8; // r8
  int v9; // ebx

  v4 = (DirectUI::Proxy *)DirectUI::HAllocAndZero((DirectUI *)0x28, (unsigned __int64)a2);
  v6 = v4;
  if ( v4 )
  {
    DirectUI::Proxy::Proxy(v4);
    *((_QWORD *)v6 + 2) = &CRefObject::`vftable';
    *((_DWORD *)v6 + 6) = 1;
    *(_QWORD *)v6 = &CFwCplProxy::`vftable'{for `DirectUI::Proxy'};
    *((_QWORD *)v6 + 2) = &CFwCplProxy::`vftable'{for `CRefObject'};
    *((_QWORD *)v6 + 4) = 0;
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 10) = v6;
  if ( v6
    && ((v7 = (CFwProfileMgr *)DirectUI::HAllocAndZero((DirectUI *)0xE0, v5)) == 0
      ? (v8 = 0)
      : (v8 = CFwProfileMgr::CFwProfileMgr(v7)),
        (*((_QWORD *)this + 5) = v8) != 0) )
  {
    v9 = CFwProfileMgr::Initialize(
           v8,
           (struct IFwChangeListener *)(((unsigned __int64)this + 8)
                                      & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
    if ( v9 >= 0 && !*((_QWORD *)this + 9) && a2 )
      IUnknown_Set((IUnknown **)this + 9, a2);
  }
  else
  {
    v9 = -2147024882;
  }
  *((_QWORD *)this + 11) = SHCreateWorkerWindowW(CFirewallCplCore::NotifierWndProc, 0, 0, 0, 0, this);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000906c  mov     [rsp+arg_8], rbx
0x180009071  mov     [rsp+arg_10], rsi
0x180009076  push    rdi
0x180009077  sub     rsp, 30h
0x18000907b  mov     rsi, rdx
0x18000907e  mov     rdi, rcx
0x180009081  mov     ecx, 28h ; '('; this
0x180009086  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000908b  mov     rbx, rax
0x18000908e  mov     [rsp+38h+arg_0], rax
0x180009093  test    rax, rax
0x180009096  jz      short loc_1800090D2
0x180009098  mov     rcx, rax
0x18000909b  call    cs:__imp_??0Proxy@DirectUI@@QEAA@XZ; DirectUI::Proxy::Proxy(void)
0x1800090a1  lea     rax, ??_7CRefObject@@6B@; const CRefObject::`vftable'
0x1800090a8  mov     [rbx+10h], rax
0x1800090ac  mov     dword ptr [rbx+18h], 1
0x1800090b3  lea     rax, ??_7CFwCplProxy@@6BProxy@DirectUI@@@; const CFwCplProxy::`vftable'{for `DirectUI::Proxy'}
0x1800090ba  mov     [rbx], rax
0x1800090bd  lea     rax, ??_7CFwCplProxy@@6BCRefObject@@@; const CFwCplProxy::`vftable'{for `CRefObject'}
0x1800090c4  mov     [rbx+10h], rax
0x1800090c8  mov     qword ptr [rbx+20h], 0
0x1800090d0  jmp     short loc_1800090D4
0x1800090d2  xor     ebx, ebx
0x1800090d4  mov     [rdi+50h], rbx
0x1800090d8  test    rbx, rbx
0x1800090db  jz      short loc_180009142
0x1800090dd  mov     ecx, 0E0h; this
0x1800090e2  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800090e7  mov     [rsp+38h+arg_0], rax
0x1800090ec  test    rax, rax
0x1800090ef  jz      short loc_1800090FE
0x1800090f1  mov     rcx, rax; this
0x1800090f4  call    ??0CFwProfileMgr@@QEAA@XZ; CFwProfileMgr::CFwProfileMgr(void)
0x1800090f9  mov     r8, rax
0x1800090fc  jmp     short loc_180009101
0x1800090fe  xor     r8d, r8d
0x180009101  mov     [rdi+28h], r8
0x180009105  test    r8, r8
0x180009108  jz      short loc_180009142
0x18000910a  mov     rax, rdi
0x18000910d  lea     rcx, [rdi+8]
0x180009111  neg     rax
0x180009114  sbb     rdx, rdx
0x180009117  and     rdx, rcx; struct IFwChangeListener *
0x18000911a  mov     rcx, r8; this
0x18000911d  call    ?Initialize@CFwProfileMgr@@QEAAJPEAUIFwChangeListener@@@Z; CFwProfileMgr::Initialize(IFwChangeListener *)
0x180009122  mov     ebx, eax
0x180009124  test    eax, eax
0x180009126  js      short loc_180009147
0x180009128  lea     rcx, [rdi+48h]; ppunk
0x18000912c  cmp     qword ptr [rcx], 0
0x180009130  jnz     short loc_180009147
0x180009132  test    rsi, rsi
0x180009135  jz      short loc_180009147
0x180009137  mov     rdx, rsi; punk
0x18000913a  call    cs:__imp_IUnknown_Set
0x180009140  jmp     short loc_180009147
0x180009142  mov     ebx, 8007000Eh
0x180009147  mov     [rsp+38h+var_10], rdi
0x18000914c  mov     [rsp+38h+var_18], 0
0x180009155  xor     r9d, r9d
0x180009158  xor     r8d, r8d
0x18000915b  xor     edx, edx
0x18000915d  lea     rcx, ?NotifierWndProc@CFirewallCplCore@@SA_JPEAUHWND__@@I_K_J@Z; CFirewallCplCore::NotifierWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180009164  call    cs:__imp_SHCreateWorkerWindowW
0x18000916a  mov     [rdi+58h], rax
0x18000916e  mov     eax, ebx
0x180009170  mov     rbx, [rsp+38h+arg_8]
0x180009175  mov     rsi, [rsp+38h+arg_10]
0x18000917a  add     rsp, 30h
0x18000917e  pop     rdi
0x18000917f  retn
```
