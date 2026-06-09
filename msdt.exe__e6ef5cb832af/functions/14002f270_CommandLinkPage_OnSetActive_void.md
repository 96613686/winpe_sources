# CommandLinkPage::OnSetActive(void)

- ea: `0x14002f270`
- end: `0x14002f5df`
- name: `?OnSetActive@CommandLinkPage@@MEAA_JXZ`
- size: `879`
- prototype: `__int64 __fastcall(CommandLinkPage *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1400070b0`
- `0x14000e378`
- `0x14000e6bc`
- `0x14000e72c`
- `0x14000e978`
- `0x140010680`
- `0x140010a10`
- `0x140020420`
- `0x140020d58`
- `0x14002ad30`
- `0x14002d660`
- `0x14002f270`
- `0x14002fc60`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14002f2ef`
- `KERNEL32!HeapAlloc` at `0x14002f344`
- `KERNEL32!HeapAlloc` at `0x14002f2ef`
- `KERNEL32!HeapAlloc` at `0x14002f344`
- `KERNEL32!HeapFree` at `0x14002f581`
- `KERNEL32!HeapFree` at `0x14002f5a6`
- `KERNEL32!HeapFree` at `0x14002f581`
- `KERNEL32!HeapFree` at `0x14002f5a6`
- `KERNEL32!GetProcessHeap` at `0x14002f2d8`
- `KERNEL32!GetProcessHeap` at `0x14002f32d`
- `KERNEL32!GetProcessHeap` at `0x14002f56c`
- `KERNEL32!GetProcessHeap` at `0x14002f592`
- `KERNEL32!GetProcessHeap` at `0x14002f2d8`
- `KERNEL32!GetProcessHeap` at `0x14002f32d`
- `KERNEL32!GetProcessHeap` at `0x14002f56c`
- `KERNEL32!GetProcessHeap` at `0x14002f592`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002f5be`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14002f5be`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002f2cb`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14002f2cb`
- `DUI70!?SetNote@CCCommandLink@DirectUI@@QEAAJPEBG@Z` at `0x14002f46c`
- `DUI70!?SetNote@CCCommandLink@DirectUI@@QEAAJPEBG@Z` at `0x14002f46c`

## string_xrefs

- `0x14002f312`: `CommandLinkPage::OnSetActive`
- `0x14002f366`: `CommandLinkPage::OnSetActive`
- `0x14002f39a`: `CommandLinkPage::OnSetActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CommandLinkPage::OnSetActive(CommandLinkPage *this)
{
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  unsigned __int16 *v4; // r14
  __int64 v5; // r15
  const unsigned __int16 *v6; // r13
  int NamedElement; // eax
  const unsigned __int16 **v8; // r12
  WizardPage *v9; // rcx
  BOOL v10; // r8d
  int ButtonImageList; // eax
  unsigned int v12; // eax
  int v13; // r9d
  HANDLE v14; // rax
  HANDLE v15; // rax
  unsigned __int16 *v17; // [rsp+20h] [rbp-58h]
  struct InteractivityChoice *v18; // [rsp+30h] [rbp-48h] BYREF
  HWND v19; // [rsp+38h] [rbp-40h] BYREF
  DirectUI::Element *v20; // [rsp+40h] [rbp-38h]
  unsigned int v21; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int16 *v22[5]; // [rsp+50h] [rbp-28h]
  int v23; // [rsp+C0h] [rbp+48h] BYREF
  int v24; // [rsp+C8h] [rbp+50h] BYREF
  struct DirectUI::Element *v25; // [rsp+D0h] [rbp+58h] BYREF
  LPVOID lpMem; // [rsp+D8h] [rbp+60h]

  v18 = 0;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  v19 = 0;
  v22[0] = L"cl1";
  v22[1] = L"cl2";
  v22[2] = L"cl3";
  v20 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v21 = 0;
  DirectUI::Element::StartDefer(v20, &v21);
  ProcessHeap = GetProcessHeap();
  lpMem = HeapAlloc(ProcessHeap, 0, 0x1800u);
  if ( lpMem )
  {
    v3 = GetProcessHeap();
    v4 = (unsigned __int16 *)HeapAlloc(v3, 0, 0x200u);
    if ( v4 )
    {
      WizardPage::StartRetireBannerTipTest(this, 4);
      InteractivityPage::OnSetActive(this);
      v5 = 0;
      if ( *((_DWORD *)this + 42) )
      {
        do
        {
          v6 = v22[v5];
          NamedElement = WizardPage::GetNamedElement(this, v6, &v25);
          if ( NamedElement < 0 )
          {
            v13 = 2405;
            goto LABEL_34;
          }
          NamedElement = InteractivityPage::GetItem(this, v5, &v18);
          if ( NamedElement < 0 )
          {
            v13 = 2408;
            goto LABEL_34;
          }
          v8 = (const unsigned __int16 **)v18;
          NamedElement = DwzStrTruncate(v4, 0x80u, *(const unsigned __int16 **)v18, &v23);
          if ( NamedElement < 0 )
          {
            v13 = 2415;
            goto LABEL_34;
          }
          v17 = (unsigned __int16 *)v8[1];
          NamedElement = StringCchPrintfW((unsigned __int16 *)lpMem, 0xC00u, L"%s\n\n%s", *v8);
          if ( NamedElement < 0 )
          {
            v13 = 2423;
            goto LABEL_34;
          }
          NamedElement = WizardPage::SetNamedValues(this, v6, v4, *v8, v17, (const unsigned __int16 *)lpMem);
          if ( NamedElement < 0 )
          {
            v13 = 2431;
            goto LABEL_34;
          }
          NamedElement = DwzStrTruncate(v4, 0x100u, v8[1], &v24);
          if ( NamedElement < 0 )
          {
            v13 = 2438;
            goto LABEL_34;
          }
          NamedElement = DirectUI::CCCommandLink::SetNote(v25, v4);
          if ( NamedElement < 0 )
          {
            v13 = 2441;
            goto LABEL_34;
          }
          v10 = v23 || v24;
          NamedElement = WizardPage::EnableTooltip(v9, v25, v10);
          if ( NamedElement < 0 )
          {
            v13 = 2447;
            goto LABEL_34;
          }
          NamedElement = WizardPage::GetNamedHandle(this, v6, &v19);
          if ( NamedElement < 0 )
          {
            v13 = 2450;
            goto LABEL_34;
          }
          ButtonImageList = InteractivityChoice::MakeButtonImageList((InteractivityChoice *)v8, v19);
          if ( ButtonImageList < 0 )
            SdpDebugPrint(
              1u,
              "Dwz IGNORED: %s:%d - hr = 0x%08X\n",
              "CommandLinkPage::OnSetActive",
              2453,
              ButtonImageList);
          v5 = (unsigned int)(v5 + 1);
          v12 = *((_DWORD *)this + 42);
        }
        while ( (unsigned int)v5 < v12 );
        if ( v12 == 2 )
        {
          NamedElement = WizardPage::HideNamedElement(this, L"cl3");
          if ( NamedElement < 0 )
          {
            v13 = 2461;
LABEL_34:
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CommandLinkPage::OnSetActive", v13, NamedElement);
          }
        }
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CommandLinkPage::OnSetActive", 2397, -2147024882);
    }
    v14 = GetProcessHeap();
    HeapFree(v14, 0, lpMem);
    if ( v4 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v4);
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CommandLinkPage::OnSetActive", 2396, -2147024882);
  }
  if ( v21 )
    DirectUI::Element::EndDefer(v20, v21);
  return 0;
}

```

## disassembly

```asm
0x14002f270  push    rbp
0x14002f272  push    rbx
0x14002f273  push    rsi
0x14002f274  push    rdi
0x14002f275  push    r12
0x14002f277  push    r13
0x14002f279  push    r14
0x14002f27b  push    r15
0x14002f27d  mov     rbp, rsp
0x14002f280  sub     rsp, 78h
0x14002f284  mov     rsi, rcx
0x14002f287  xor     edx, edx
0x14002f289  mov     [rbp+var_48], rdx
0x14002f28d  mov     [rbp+arg_10], rdx
0x14002f291  mov     [rbp+arg_0], edx
0x14002f294  mov     [rbp+arg_8], edx
0x14002f297  mov     [rbp+var_40], rdx
0x14002f29b  lea     rax, aCl1; "cl1"
0x14002f2a2  mov     [rbp+var_28], rax
0x14002f2a6  lea     rax, aCl2; "cl2"
0x14002f2ad  mov     [rbp+var_20], rax
0x14002f2b1  lea     rax, aCl3; "cl3"
0x14002f2b8  mov     [rbp+var_18], rax
0x14002f2bc  mov     rcx, [rcx+40h]
0x14002f2c0  mov     [rbp+var_38], rcx
0x14002f2c4  mov     [rbp+var_30], edx
0x14002f2c7  lea     rdx, [rbp+var_30]
0x14002f2cb  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14002f2d2  nop     dword ptr [rax+rax+00h]
0x14002f2d7  nop
0x14002f2d8  call    cs:__imp_GetProcessHeap
0x14002f2df  nop     dword ptr [rax+rax+00h]
0x14002f2e4  mov     rcx, rax; hHeap
0x14002f2e7  xor     edx, edx; dwFlags
0x14002f2e9  mov     r8d, 1800h; dwBytes
0x14002f2ef  call    cs:__imp_HeapAlloc
0x14002f2f6  nop     dword ptr [rax+rax+00h]
0x14002f2fb  mov     [rbp+lpMem], rax
0x14002f2ff  test    rax, rax
0x14002f302  jnz     short loc_14002F32D
0x14002f304  mov     dword ptr [rsp+78h+var_58], 8007000Eh
0x14002f30c  mov     r9d, 95Ch
0x14002f312  lea     r8, aCommandlinkpag_3; "CommandLinkPage::OnSetActive"
0x14002f319  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002f320  lea     ecx, [rax+1]; Level
0x14002f323  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f328  jmp     loc_14002F5B3
0x14002f32d  call    cs:__imp_GetProcessHeap
0x14002f334  nop     dword ptr [rax+rax+00h]
0x14002f339  mov     rcx, rax; hHeap
0x14002f33c  xor     edx, edx; dwFlags
0x14002f33e  mov     r8d, 200h; dwBytes
0x14002f344  call    cs:__imp_HeapAlloc
0x14002f34b  nop     dword ptr [rax+rax+00h]
0x14002f350  mov     r14, rax
0x14002f353  test    rax, rax
0x14002f356  jnz     short loc_14002F375
0x14002f358  mov     dword ptr [rsp+78h+var_58], 8007000Eh
0x14002f360  mov     r9d, 95Dh
0x14002f366  lea     r8, aCommandlinkpag_3; "CommandLinkPage::OnSetActive"
0x14002f36d  lea     ecx, [rax+1]
0x14002f370  jmp     loc_14002F560
0x14002f375  mov     edx, 4
0x14002f37a  mov     rcx, rsi
0x14002f37d  call    ?StartRetireBannerTipTest@WizardPage@@IEAAXW4PageNames@@@Z; WizardPage::StartRetireBannerTipTest(PageNames)
0x14002f382  mov     rcx, rsi; this
0x14002f385  call    ?OnSetActive@InteractivityPage@@MEAA_JXZ; InteractivityPage::OnSetActive(void)
0x14002f38a  xor     r15d, r15d
0x14002f38d  cmp     [rsi+0A8h], r15d
0x14002f394  jbe     loc_14002F56C
0x14002f39a  lea     rdi, aCommandlinkpag_3; "CommandLinkPage::OnSetActive"
0x14002f3a1  lea     ebx, [r15+1]
0x14002f3a5  mov     r13, [rbp+r15*8+var_28]
0x14002f3aa  lea     r8, [rbp+arg_10]; struct DirectUI::Element **
0x14002f3ae  mov     rdx, r13; unsigned __int16 *
0x14002f3b1  mov     rcx, rsi; this
0x14002f3b4  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14002f3b9  test    eax, eax
0x14002f3bb  js      loc_14002F551
0x14002f3c1  lea     r8, [rbp+var_48]; struct InteractivityChoice **
0x14002f3c5  mov     edx, r15d; unsigned int
0x14002f3c8  mov     rcx, rsi; this
0x14002f3cb  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x14002f3d0  test    eax, eax
0x14002f3d2  js      loc_14002F549
0x14002f3d8  lea     r9, [rbp+arg_0]; int *
0x14002f3dc  mov     r12, [rbp+var_48]
0x14002f3e0  mov     r8, [r12]; unsigned __int16 *
0x14002f3e4  mov     edx, 80h; unsigned __int64
0x14002f3e9  mov     rcx, r14; unsigned __int16 *
0x14002f3ec  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x14002f3f1  test    eax, eax
0x14002f3f3  js      loc_14002F541
0x14002f3f9  mov     rax, [r12+8]
0x14002f3fe  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x14002f403  mov     r9, [r12]
0x14002f407  lea     r8, aSS_3; "%s\n\n%s"
0x14002f40e  mov     edx, 0C00h; unsigned __int64
0x14002f413  mov     rcx, [rbp+lpMem]; unsigned __int16 *
0x14002f417  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002f41c  test    eax, eax
0x14002f41e  js      loc_14002F539
0x14002f424  mov     rax, [rbp+lpMem]
0x14002f428  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x14002f42d  mov     r9, [r12]; unsigned __int16 *
0x14002f431  mov     r8, r14; unsigned __int16 *
0x14002f434  mov     rdx, r13; unsigned __int16 *
0x14002f437  mov     rcx, rsi; this
0x14002f43a  call    ?SetNamedValues@WizardPage@@IEAAJPEBG0000@Z; WizardPage::SetNamedValues(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14002f43f  test    eax, eax
0x14002f441  js      loc_14002F531
0x14002f447  lea     r9, [rbp+arg_8]; int *
0x14002f44b  mov     r8, [r12+8]; unsigned __int16 *
0x14002f450  mov     edx, 100h; unsigned __int64
0x14002f455  mov     rcx, r14; unsigned __int16 *
0x14002f458  call    ?DwzStrTruncate@@YAJPEAG_KPEBGPEAH@Z; DwzStrTruncate(ushort *,unsigned __int64,ushort const *,int *)
0x14002f45d  test    eax, eax
0x14002f45f  js      loc_14002F529
0x14002f465  mov     rdx, r14
0x14002f468  mov     rcx, [rbp+arg_10]
0x14002f46c  call    cs:__imp_?SetNote@CCCommandLink@DirectUI@@QEAAJPEBG@Z; DirectUI::CCCommandLink::SetNote(ushort const *)
0x14002f473  nop     dword ptr [rax+rax+00h]
0x14002f478  test    eax, eax
0x14002f47a  js      loc_14002F521
0x14002f480  cmp     [rbp+arg_0], 0
0x14002f484  jnz     short loc_14002F491
0x14002f486  cmp     [rbp+arg_8], 0
0x14002f48a  jnz     short loc_14002F491
0x14002f48c  xor     r8d, r8d
0x14002f48f  jmp     short loc_14002F494
0x14002f491  mov     r8d, ebx; int
0x14002f494  mov     rdx, [rbp+arg_10]; struct DirectUI::Element *
0x14002f498  call    ?EnableTooltip@WizardPage@@IEAAJPEAVElement@DirectUI@@H@Z; WizardPage::EnableTooltip(DirectUI::Element *,int)
0x14002f49d  test    eax, eax
0x14002f49f  js      short loc_14002F519
0x14002f4a1  lea     r8, [rbp+var_40]; HWND *
0x14002f4a5  mov     rdx, r13; unsigned __int16 *
0x14002f4a8  mov     rcx, rsi; this
0x14002f4ab  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002f4b0  test    eax, eax
0x14002f4b2  js      short loc_14002F511
0x14002f4b4  mov     rdx, [rbp+var_40]; HWND
0x14002f4b8  mov     rcx, r12; this
0x14002f4bb  call    ?MakeButtonImageList@InteractivityChoice@@QEAAJPEAUHWND__@@@Z; InteractivityChoice::MakeButtonImageList(HWND__ *)
0x14002f4c0  test    eax, eax
0x14002f4c2  jns     short loc_14002F4DF
0x14002f4c4  mov     dword ptr [rsp+78h+var_58], eax
0x14002f4c8  mov     r9d, 995h
0x14002f4ce  mov     r8, rdi
0x14002f4d1  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14002f4d8  mov     ecx, ebx; Level
0x14002f4da  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f4df  add     r15d, ebx
0x14002f4e2  mov     eax, [rsi+0A8h]
0x14002f4e8  cmp     r15d, eax
0x14002f4eb  jb      loc_14002F3A5
0x14002f4f1  cmp     eax, 2
0x14002f4f4  jnz     short loc_14002F56C
0x14002f4f6  lea     rdx, aCl3; "cl3"
0x14002f4fd  mov     rcx, rsi; this
0x14002f500  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x14002f505  test    eax, eax
0x14002f507  jns     short loc_14002F56C
0x14002f509  mov     r9d, 99Dh
0x14002f50f  jmp     short loc_14002F557
0x14002f511  mov     r9d, 992h
0x14002f517  jmp     short loc_14002F557
0x14002f519  mov     r9d, 98Fh
0x14002f51f  jmp     short loc_14002F557
0x14002f521  mov     r9d, 989h
0x14002f527  jmp     short loc_14002F557
0x14002f529  mov     r9d, 986h
0x14002f52f  jmp     short loc_14002F557
0x14002f531  mov     r9d, 97Fh
0x14002f537  jmp     short loc_14002F557
0x14002f539  mov     r9d, 977h
0x14002f53f  jmp     short loc_14002F557
0x14002f541  mov     r9d, 96Fh
0x14002f547  jmp     short loc_14002F557
0x14002f549  mov     r9d, 968h
0x14002f54f  jmp     short loc_14002F557
0x14002f551  mov     r9d, 965h
0x14002f557  mov     ecx, ebx; Level
0x14002f559  mov     r8, rdi
0x14002f55c  mov     dword ptr [rsp+78h+var_58], eax
0x14002f560  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002f567  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002f56c  call    cs:__imp_GetProcessHeap
0x14002f573  nop     dword ptr [rax+rax+00h]
0x14002f578  mov     rcx, rax; hHeap
0x14002f57b  mov     r8, [rbp+lpMem]; lpMem
0x14002f57f  xor     edx, edx; dwFlags
0x14002f581  call    cs:__imp_HeapFree
0x14002f588  nop     dword ptr [rax+rax+00h]
0x14002f58d  test    r14, r14
0x14002f590  jz      short loc_14002F5B3
0x14002f592  call    cs:__imp_GetProcessHeap
0x14002f599  nop     dword ptr [rax+rax+00h]
0x14002f59e  mov     rcx, rax; hHeap
0x14002f5a1  mov     r8, r14; lpMem
0x14002f5a4  xor     edx, edx; dwFlags
0x14002f5a6  call    cs:__imp_HeapFree
0x14002f5ad  nop     dword ptr [rax+rax+00h]
0x14002f5b2  nop
0x14002f5b3  mov     edx, [rbp+var_30]
0x14002f5b6  test    edx, edx
0x14002f5b8  jz      short loc_14002F5CB
0x14002f5ba  mov     rcx, [rbp+var_38]
0x14002f5be  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14002f5c5  nop     dword ptr [rax+rax+00h]
0x14002f5ca  nop
0x14002f5cb  xor     eax, eax
0x14002f5cd  add     rsp, 78h
0x14002f5d1  pop     r15
0x14002f5d3  pop     r14
0x14002f5d5  pop     r13
0x14002f5d7  pop     r12
0x14002f5d9  pop     rdi
0x14002f5da  pop     rsi
0x14002f5db  pop     rbx
0x14002f5dc  pop     rbp
0x14002f5dd  retn
```
