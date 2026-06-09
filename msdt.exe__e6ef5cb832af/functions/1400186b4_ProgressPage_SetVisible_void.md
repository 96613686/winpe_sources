# ProgressPage::SetVisible(void)

- ea: `0x1400186b4`
- end: `0x1400189aa`
- name: `?SetVisible@ProgressPage@@QEAAJXZ`
- size: `758`
- prototype: `__int64 __fastcall(ProgressPage *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140016d90`
- `0x140017ef0`

## callees

- `0x14000e6bc`
- `0x14000e72c`
- `0x1400104bc`
- `0x1400186b4`
- `0x140020420`
- `0x140041c54`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001887a`
- `KERNEL32!HeapAlloc` at `0x14001887a`
- `KERNEL32!HeapFree` at `0x14001896f`
- `KERNEL32!HeapFree` at `0x14001896f`
- `KERNEL32!GetProcessHeap` at `0x140018863`
- `KERNEL32!GetProcessHeap` at `0x14001895b`
- `KERNEL32!GetProcessHeap` at `0x140018863`
- `KERNEL32!GetProcessHeap` at `0x14001895b`
- `USER32!SetWindowLongPtrW` at `0x1400187bd`
- `USER32!SetWindowLongPtrW` at `0x1400187bd`
- `USER32!SendMessageW` at `0x1400187db`
- `USER32!SendMessageW` at `0x1400187db`
- `OLEAUT32!__imp_SysAllocString` at `0x1400188f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400188f3`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x140018812`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x140018812`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140018987`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140018987`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x1400186dc`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x1400186dc`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400186fa`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400186fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProgressPage::SetVisible(const unsigned __int16 **this)
{
  unsigned int v2; // ebx
  int v3; // ebx
  const unsigned __int16 *v4; // rcx
  int NamedHandle; // eax
  int v6; // r9d
  const unsigned __int16 *v7; // rax
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rsi
  int LocalString; // eax
  int v11; // r9d
  int v12; // eax
  HANDLE v13; // rax
  DirectUI::Element *Element; // [rsp+30h] [rbp-10h]
  unsigned int v16; // [rsp+38h] [rbp-8h] BYREF
  HWND hWnd; // [rsp+60h] [rbp+20h] BYREF
  struct DirectUI::Element *v18; // [rsp+68h] [rbp+28h] BYREF

  hWnd = 0;
  v18 = 0;
  Element = DirectUI::TaskPage::GetElement((DirectUI::TaskPage *)this);
  v16 = 0;
  DirectUI::Element::StartDefer(Element, &v16);
  if ( *((_DWORD *)this + 32) )
  {
    v2 = 0;
    goto LABEL_30;
  }
  v3 = *((_DWORD *)Config + 48);
  if ( (*((unsigned int (__fastcall **)(const unsigned __int16 **))*this + 22))(this) == v3 )
  {
    v4 = this[19];
    if ( v4 )
    {
      NamedHandle = (*(__int64 (__fastcall **)(const unsigned __int16 *, HWND, __int64))(*(_QWORD *)v4 + 80LL))(
                      v4,
                      g_HWND,
                      1);
      v2 = NamedHandle;
      if ( NamedHandle < 0 )
      {
        v6 = 1342;
LABEL_7:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::SetVisible", v6, NamedHandle);
        goto LABEL_30;
      }
    }
  }
  NamedHandle = WizardPage::GetNamedHandle((WizardPage *)this, L"progress", &hWnd);
  v2 = NamedHandle;
  if ( NamedHandle < 0 )
  {
    v6 = 1350;
    goto LABEL_7;
  }
  SetWindowLongPtrW(hWnd, -16, 1342177288);
  SendMessageW(hWnd, 0x40Au, 1u, 35);
  NamedHandle = WizardPage::GetNamedElement((WizardPage *)this, L"page", &v18);
  v2 = NamedHandle;
  if ( NamedHandle < 0 )
  {
    v6 = 1363;
    goto LABEL_7;
  }
  NamedHandle = DirectUI::Element::SetVisible(v18, 1);
  v2 = NamedHandle;
  if ( NamedHandle < 0 )
  {
    v6 = 1366;
    goto LABEL_7;
  }
  NamedHandle = WizardPage::GetNamedElement((WizardPage *)this, L"progress", &v18);
  v2 = NamedHandle;
  if ( NamedHandle < 0 )
  {
    v6 = 1369;
    goto LABEL_7;
  }
  v7 = this[18];
  if ( v7 )
  {
    v9 = 0;
    goto LABEL_25;
  }
  ProcessHeap = GetProcessHeap();
  v9 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v9 )
  {
    NamedHandle = -2147024882;
    v2 = -2147024882;
    v6 = 1375;
    goto LABEL_7;
  }
  LocalString = DwzLoadLocalString(*((_DWORD *)Config + 20) != 0 ? 10354 : 354, v9, 0x400u);
  v2 = LocalString;
  if ( LocalString >= 0 )
  {
    v7 = SysAllocString(v9);
    this[18] = v7;
    if ( !v7 )
    {
      LocalString = -2147024882;
      v2 = -2147024882;
      v11 = 1384;
      goto LABEL_21;
    }
LABEL_25:
    v12 = WizardPage::SetHeader((WizardPage *)this, v7);
    v2 = v12;
    if ( v12 >= 0 )
      *((_DWORD *)this + 32) = 1;
    else
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::SetVisible", 1388, v12);
    if ( !v9 )
      goto LABEL_30;
    goto LABEL_29;
  }
  v11 = 1381;
LABEL_21:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ProgressPage::SetVisible", v11, LocalString);
LABEL_29:
  v13 = GetProcessHeap();
  HeapFree(v13, 0, v9);
LABEL_30:
  if ( v16 )
    DirectUI::Element::EndDefer(Element, v16);
  return v2;
}

```

## disassembly

```asm
0x1400186b4  mov     [rsp-18h+arg_10], rbx
0x1400186b9  mov     [rsp-18h+arg_18], rsi
0x1400186be  push    rbp
0x1400186bf  push    rdi
0x1400186c0  push    r15
0x1400186c2  mov     rbp, rsp
0x1400186c5  sub     rsp, 40h
0x1400186c9  mov     rdi, rcx
0x1400186cc  mov     [rbp+hWnd], 0
0x1400186d4  mov     [rbp+arg_8], 0
0x1400186dc  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x1400186e3  nop     dword ptr [rax+rax+00h]
0x1400186e8  mov     [rbp+var_10], rax
0x1400186ec  mov     [rbp+var_8], 0
0x1400186f3  lea     rdx, [rbp+var_8]
0x1400186f7  mov     rcx, rax
0x1400186fa  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140018701  nop     dword ptr [rax+rax+00h]
0x140018706  nop
0x140018707  cmp     dword ptr [rdi+80h], 0
0x14001870e  jz      short loc_140018717
0x140018710  xor     ebx, ebx
0x140018712  jmp     loc_14001897C
0x140018717  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14001871e  mov     ebx, [rax+0C0h]
0x140018724  mov     rax, [rdi]
0x140018727  mov     rcx, rdi
0x14001872a  mov     rax, [rax+0B0h]
0x140018731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018736  mov     r15d, 1
0x14001873c  cmp     eax, ebx
0x14001873e  jnz     short loc_14001878D
0x140018740  mov     rcx, [rdi+98h]
0x140018747  test    rcx, rcx
0x14001874a  jz      short loc_14001878D
0x14001874c  mov     rax, [rcx]
0x14001874f  mov     r8d, r15d
0x140018752  mov     rdx, cs:?g_HWND@@3PEAUHWND__@@EA; HWND__ * g_HWND
0x140018759  mov     rax, [rax+50h]
0x14001875d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018762  mov     ebx, eax
0x140018764  test    eax, eax
0x140018766  jns     short loc_14001878D
0x140018768  mov     r9d, 53Eh
0x14001876e  mov     [rsp+40h+var_20], eax
0x140018772  lea     r8, aProgresspageSe; "ProgressPage::SetVisible"
0x140018779  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140018780  mov     ecx, r15d; Level
0x140018783  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140018788  jmp     loc_14001897C
0x14001878d  lea     r8, [rbp+hWnd]; HWND *
0x140018791  lea     rdx, aProgress; "progress"
0x140018798  mov     rcx, rdi; this
0x14001879b  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x1400187a0  mov     ebx, eax
0x1400187a2  test    eax, eax
0x1400187a4  jns     short loc_1400187AE
0x1400187a6  mov     r9d, 546h
0x1400187ac  jmp     short loc_14001876E
0x1400187ae  mov     edx, 0FFFFFFF0h; nIndex
0x1400187b3  mov     r8d, 50000008h; dwNewLong
0x1400187b9  mov     rcx, [rbp+hWnd]; hWnd
0x1400187bd  call    cs:__imp_SetWindowLongPtrW
0x1400187c4  nop     dword ptr [rax+rax+00h]
0x1400187c9  mov     r9d, 23h ; '#'; lParam
0x1400187cf  mov     r8, r15; wParam
0x1400187d2  mov     edx, 40Ah; Msg
0x1400187d7  mov     rcx, [rbp+hWnd]; hWnd
0x1400187db  call    cs:__imp_SendMessageW
0x1400187e2  nop     dword ptr [rax+rax+00h]
0x1400187e7  lea     r8, [rbp+arg_8]; struct DirectUI::Element **
0x1400187eb  lea     rdx, aPage; "page"
0x1400187f2  mov     rcx, rdi; this
0x1400187f5  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400187fa  mov     ebx, eax
0x1400187fc  test    eax, eax
0x1400187fe  jns     short loc_14001880B
0x140018800  mov     r9d, 553h
0x140018806  jmp     loc_14001876E
0x14001880b  mov     dl, r15b
0x14001880e  mov     rcx, [rbp+arg_8]
0x140018812  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x140018819  nop     dword ptr [rax+rax+00h]
0x14001881e  mov     ebx, eax
0x140018820  test    eax, eax
0x140018822  jns     short loc_14001882F
0x140018824  mov     r9d, 556h
0x14001882a  jmp     loc_14001876E
0x14001882f  lea     r8, [rbp+arg_8]; struct DirectUI::Element **
0x140018833  lea     rdx, aProgress; "progress"
0x14001883a  mov     rcx, rdi; this
0x14001883d  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140018842  mov     ebx, eax
0x140018844  test    eax, eax
0x140018846  jns     short loc_140018853
0x140018848  mov     r9d, 559h
0x14001884e  jmp     loc_14001876E
0x140018853  mov     rax, [rdi+90h]
0x14001885a  test    rax, rax
0x14001885d  jnz     loc_14001891A
0x140018863  call    cs:__imp_GetProcessHeap
0x14001886a  nop     dword ptr [rax+rax+00h]
0x14001886f  mov     rcx, rax; hHeap
0x140018872  xor     edx, edx; dwFlags
0x140018874  mov     r8d, 800h; dwBytes
0x14001887a  call    cs:__imp_HeapAlloc
0x140018881  nop     dword ptr [rax+rax+00h]
0x140018886  mov     rsi, rax
0x140018889  test    rax, rax
0x14001888c  jnz     short loc_1400188A0
0x14001888e  mov     eax, 8007000Eh
0x140018893  mov     ebx, eax
0x140018895  mov     r9d, 55Fh
0x14001889b  jmp     loc_14001876E
0x1400188a0  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400188a7  mov     ecx, [rax+50h]
0x1400188aa  neg     ecx
0x1400188ac  sbb     ecx, ecx
0x1400188ae  and     ecx, 2710h
0x1400188b4  add     ecx, 162h; uID
0x1400188ba  mov     r8d, 400h; cchBufferMax
0x1400188c0  mov     rdx, rsi; lpBuffer
0x1400188c3  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x1400188c8  mov     ebx, eax
0x1400188ca  test    eax, eax
0x1400188cc  jns     short loc_1400188F0
0x1400188ce  mov     r9d, 565h
0x1400188d4  mov     [rsp+40h+var_20], eax
0x1400188d8  lea     r8, aProgresspageSe; "ProgressPage::SetVisible"
0x1400188df  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400188e6  mov     ecx, r15d; Level
0x1400188e9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400188ee  jmp     short loc_14001895B
0x1400188f0  mov     rcx, rsi; psz
0x1400188f3  call    cs:__imp_SysAllocString
0x1400188fa  nop     dword ptr [rax+rax+00h]
0x1400188ff  mov     [rdi+90h], rax
0x140018906  test    rax, rax
0x140018909  jnz     short loc_14001891C
0x14001890b  mov     eax, 8007000Eh
0x140018910  mov     ebx, eax
0x140018912  mov     r9d, 568h
0x140018918  jmp     short loc_1400188D4
0x14001891a  xor     esi, esi
0x14001891c  mov     rdx, rax; unsigned __int16 *
0x14001891f  mov     rcx, rdi; this
0x140018922  call    ?SetHeader@WizardPage@@IEAAJPEBG@Z; WizardPage::SetHeader(ushort const *)
0x140018927  mov     ebx, eax
0x140018929  test    eax, eax
0x14001892b  jns     short loc_14001894F
0x14001892d  mov     [rsp+40h+var_20], eax
0x140018931  mov     r9d, 56Ch
0x140018937  lea     r8, aProgresspageSe; "ProgressPage::SetVisible"
0x14001893e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140018945  mov     ecx, r15d; Level
0x140018948  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001894d  jmp     short loc_140018956
0x14001894f  mov     [rdi+80h], r15d
0x140018956  test    rsi, rsi
0x140018959  jz      short loc_14001897C
0x14001895b  call    cs:__imp_GetProcessHeap
0x140018962  nop     dword ptr [rax+rax+00h]
0x140018967  mov     rcx, rax; hHeap
0x14001896a  mov     r8, rsi; lpMem
0x14001896d  xor     edx, edx; dwFlags
0x14001896f  call    cs:__imp_HeapFree
0x140018976  nop     dword ptr [rax+rax+00h]
0x14001897b  nop
0x14001897c  mov     edx, [rbp+var_8]
0x14001897f  test    edx, edx
0x140018981  jz      short loc_140018994
0x140018983  mov     rcx, [rbp+var_10]
0x140018987  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14001898e  nop     dword ptr [rax+rax+00h]
0x140018993  nop
0x140018994  mov     eax, ebx
0x140018996  mov     rbx, [rsp+40h+arg_10]
0x14001899b  mov     rsi, [rsp+40h+arg_18]
0x1400189a0  add     rsp, 40h
0x1400189a4  pop     r15
0x1400189a6  pop     rdi
0x1400189a7  pop     rbp
0x1400189a8  retn
```
