# FinalElevationPage::CreateElevateLink(DirectUI::DUIXmlParser *)

- ea: `0x14001a03c`
- end: `0x14001a28a`
- name: `?CreateElevateLink@FinalElevationPage@@AEAAJPEAVDUIXmlParser@DirectUI@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(FinalElevationPage *__hidden this, struct DirectUI::DUIXmlParser *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001ae60`

## callees

- `0x14000e6bc`
- `0x14001a03c`
- `0x140020420`
- `0x140041c54`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001a1b6`
- `KERNEL32!HeapAlloc` at `0x14001a1b6`
- `KERNEL32!HeapFree` at `0x14001a273`
- `KERNEL32!HeapFree` at `0x14001a273`
- `KERNEL32!GetProcessHeap` at `0x14001a19f`
- `KERNEL32!GetProcessHeap` at `0x14001a25f`
- `KERNEL32!GetProcessHeap` at `0x14001a19f`
- `KERNEL32!GetProcessHeap` at `0x14001a25f`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a182`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a182`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a119`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a22b`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a119`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a22b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a0f5`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a159`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a0f5`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a159`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001a0b8`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001a0b8`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a207`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a207`

## string_xrefs

- `0x14001a07a`: `elevateLink`
- `0x14001a096`: `FinalElevationPage::CreateElevateLink`
- `0x14001a243`: `FinalElevationPage::CreateElevateLink`
- `0x14001a0df`: `linkSpacer`
- `0x14001a143`: `commandLink`
- `0x14001a17b`: `linkElevate`

## pseudocode

```c
__int64 __fastcall FinalElevationPage::CreateElevateLink(FinalElevationPage *this, struct DirectUI::DUIXmlParser *a2)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  int NamedElement; // eax
  int v7; // r9d
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  unsigned __int16 *v10; // rdi
  int LocalString; // eax
  int v12; // r9d
  HANDLE v13; // rax
  struct DirectUI::Element *v15; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::Element *v16; // [rsp+60h] [rbp+18h] BYREF
  struct DirectUI::Element *v17; // [rsp+68h] [rbp+20h] BYREF

  v2 = *(_QWORD *)this;
  v3 = 0;
  v16 = 0;
  v17 = 0;
  v15 = 0;
  if ( (*(unsigned int (__fastcall **)(FinalElevationPage *))(v2 + 272))(this) )
  {
    NamedElement = WizardPage::GetNamedElement(this, L"elevateLink", &v16);
    v3 = NamedElement;
    if ( NamedElement < 0 )
    {
      v7 = 181;
LABEL_4:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::CreateElevateLink", v7, NamedElement);
      return v3;
    }
    NamedElement = DirectUI::Element::RemoveAll(v16);
    v3 = NamedElement;
    if ( NamedElement < 0 )
    {
      v7 = 184;
      goto LABEL_4;
    }
    NamedElement = DirectUI::DUIXmlParser::CreateElement(a2, L"linkSpacer", 0, 0, 0, &v17);
    v3 = NamedElement;
    if ( NamedElement < 0 )
    {
      v7 = 190;
      goto LABEL_4;
    }
    NamedElement = DirectUI::Element::Add(v16, v17);
    v3 = NamedElement;
    if ( NamedElement < 0 )
    {
      v7 = 193;
      goto LABEL_4;
    }
    NamedElement = DirectUI::DUIXmlParser::CreateElement(a2, L"commandLink", 0, 0, 0, &v15);
    v3 = NamedElement;
    if ( NamedElement < 0 )
    {
      v7 = 199;
      goto LABEL_4;
    }
    NamedElement = DirectUI::Element::SetID(v15, L"linkElevate");
    v3 = NamedElement;
    if ( NamedElement < 0 )
    {
      v7 = 202;
      goto LABEL_4;
    }
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v10 = v9;
    if ( !v9 )
    {
      v3 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::CreateElevateLink", 204, -2147024882);
      return v3;
    }
    LocalString = DwzLoadLocalString(0x283Fu, v9, 0x400u);
    v3 = LocalString;
    if ( LocalString >= 0 )
    {
      LocalString = DirectUI::Element::SetContentString(v15, v10);
      v3 = LocalString;
      if ( LocalString >= 0 )
      {
        LocalString = DirectUI::Element::Add(v16, v15);
        v3 = LocalString;
        if ( LocalString >= 0 )
        {
LABEL_25:
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v10);
          return v3;
        }
        v12 = 212;
      }
      else
      {
        v12 = 209;
      }
    }
    else
    {
      v12 = 206;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::CreateElevateLink", v12, LocalString);
    goto LABEL_25;
  }
  return v3;
}

```

## disassembly

```asm
0x14001a03c  push    rbx
0x14001a03e  push    rbp
0x14001a03f  push    rdi
0x14001a040  sub     rsp, 30h
0x14001a044  mov     rax, [rcx]
0x14001a047  xor     ebx, ebx
0x14001a049  mov     rbp, rdx
0x14001a04c  mov     [rsp+48h+arg_10], rbx
0x14001a051  mov     rdi, rcx
0x14001a054  mov     [rsp+48h+arg_18], rbx
0x14001a059  mov     [rsp+48h+arg_0], rbx
0x14001a05e  mov     rax, [rax+110h]
0x14001a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a06a  test    eax, eax
0x14001a06c  jz      loc_14001A27F
0x14001a072  lea     r8, [rsp+48h+arg_10]; struct DirectUI::Element **
0x14001a077  mov     rcx, rdi; this
0x14001a07a  lea     rdx, aElevatelink; "elevateLink"
0x14001a081  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14001a086  mov     ebx, eax
0x14001a088  test    eax, eax
0x14001a08a  jns     short loc_14001A0B3
0x14001a08c  mov     r9d, 0B5h
0x14001a092  mov     dword ptr [rsp+48h+var_28], eax
0x14001a096  lea     r8, aFinalelevation_3; "FinalElevationPage::CreateElevateLink"
0x14001a09d  mov     ecx, 1; Level
0x14001a0a2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001a0a9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001a0ae  jmp     loc_14001A27F
0x14001a0b3  mov     rcx, [rsp+48h+arg_10]
0x14001a0b8  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x14001a0bf  nop     dword ptr [rax+rax+00h]
0x14001a0c4  mov     ebx, eax
0x14001a0c6  test    eax, eax
0x14001a0c8  jns     short loc_14001A0D2
0x14001a0ca  mov     r9d, 0B8h
0x14001a0d0  jmp     short loc_14001A092
0x14001a0d2  lea     rax, [rsp+48h+arg_18]
0x14001a0d7  xor     r9d, r9d
0x14001a0da  mov     [rsp+48h+var_20], rax
0x14001a0df  lea     rdx, aLinkspacer; "linkSpacer"
0x14001a0e6  xor     r8d, r8d
0x14001a0e9  mov     [rsp+48h+var_28], 0
0x14001a0f2  mov     rcx, rbp
0x14001a0f5  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001a0fc  nop     dword ptr [rax+rax+00h]
0x14001a101  mov     ebx, eax
0x14001a103  test    eax, eax
0x14001a105  jns     short loc_14001A10F
0x14001a107  mov     r9d, 0BEh
0x14001a10d  jmp     short loc_14001A092
0x14001a10f  mov     rdx, [rsp+48h+arg_18]
0x14001a114  mov     rcx, [rsp+48h+arg_10]
0x14001a119  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001a120  nop     dword ptr [rax+rax+00h]
0x14001a125  mov     ebx, eax
0x14001a127  test    eax, eax
0x14001a129  jns     short loc_14001A136
0x14001a12b  mov     r9d, 0C1h
0x14001a131  jmp     loc_14001A092
0x14001a136  lea     rax, [rsp+48h+arg_0]
0x14001a13b  xor     r9d, r9d
0x14001a13e  mov     [rsp+48h+var_20], rax
0x14001a143  lea     rdx, aCommandlink; "commandLink"
0x14001a14a  xor     r8d, r8d
0x14001a14d  mov     [rsp+48h+var_28], 0
0x14001a156  mov     rcx, rbp
0x14001a159  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001a160  nop     dword ptr [rax+rax+00h]
0x14001a165  mov     ebx, eax
0x14001a167  test    eax, eax
0x14001a169  jns     short loc_14001A176
0x14001a16b  mov     r9d, 0C7h
0x14001a171  jmp     loc_14001A092
0x14001a176  mov     rcx, [rsp+48h+arg_0]
0x14001a17b  lea     rdx, aLinkelevate; "linkElevate"
0x14001a182  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x14001a189  nop     dword ptr [rax+rax+00h]
0x14001a18e  mov     ebx, eax
0x14001a190  test    eax, eax
0x14001a192  jns     short loc_14001A19F
0x14001a194  mov     r9d, 0CAh
0x14001a19a  jmp     loc_14001A092
0x14001a19f  call    cs:__imp_GetProcessHeap
0x14001a1a6  nop     dword ptr [rax+rax+00h]
0x14001a1ab  xor     edx, edx; dwFlags
0x14001a1ad  mov     r8d, 800h; dwBytes
0x14001a1b3  mov     rcx, rax; hHeap
0x14001a1b6  call    cs:__imp_HeapAlloc
0x14001a1bd  nop     dword ptr [rax+rax+00h]
0x14001a1c2  mov     rdi, rax
0x14001a1c5  test    rax, rax
0x14001a1c8  jnz     short loc_14001A1DE
0x14001a1ca  mov     ebx, 8007000Eh
0x14001a1cf  mov     r9d, 0CCh
0x14001a1d5  mov     dword ptr [rsp+48h+var_28], ebx
0x14001a1d9  jmp     loc_14001A096
0x14001a1de  mov     r8d, 400h; cchBufferMax
0x14001a1e4  mov     rdx, rdi; lpBuffer
0x14001a1e7  mov     ecx, 283Fh; uID
0x14001a1ec  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001a1f1  mov     ebx, eax
0x14001a1f3  test    eax, eax
0x14001a1f5  jns     short loc_14001A1FF
0x14001a1f7  mov     r9d, 0CEh
0x14001a1fd  jmp     short loc_14001A243
0x14001a1ff  mov     rcx, [rsp+48h+arg_0]
0x14001a204  mov     rdx, rdi
0x14001a207  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x14001a20e  nop     dword ptr [rax+rax+00h]
0x14001a213  mov     ebx, eax
0x14001a215  test    eax, eax
0x14001a217  jns     short loc_14001A221
0x14001a219  mov     r9d, 0D1h
0x14001a21f  jmp     short loc_14001A243
0x14001a221  mov     rdx, [rsp+48h+arg_0]
0x14001a226  mov     rcx, [rsp+48h+arg_10]
0x14001a22b  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001a232  nop     dword ptr [rax+rax+00h]
0x14001a237  mov     ebx, eax
0x14001a239  test    eax, eax
0x14001a23b  jns     short loc_14001A25F
0x14001a23d  mov     r9d, 0D4h
0x14001a243  lea     r8, aFinalelevation_3; "FinalElevationPage::CreateElevateLink"
0x14001a24a  mov     dword ptr [rsp+48h+var_28], eax
0x14001a24e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001a255  mov     ecx, 1; Level
0x14001a25a  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001a25f  call    cs:__imp_GetProcessHeap
0x14001a266  nop     dword ptr [rax+rax+00h]
0x14001a26b  mov     r8, rdi; lpMem
0x14001a26e  xor     edx, edx; dwFlags
0x14001a270  mov     rcx, rax; hHeap
0x14001a273  call    cs:__imp_HeapFree
0x14001a27a  nop     dword ptr [rax+rax+00h]
0x14001a27f  mov     eax, ebx
0x14001a281  add     rsp, 30h
0x14001a285  pop     rdi
0x14001a286  pop     rbp
0x14001a287  pop     rbx
0x14001a288  retn
```
