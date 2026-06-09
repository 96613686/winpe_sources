# FinalLinksPage::CreateLinks(DirectUI::DUIXmlParser *,bool,ushort const *)

- ea: `0x14001a290`
- end: `0x14001a66a`
- name: `?CreateLinks@FinalLinksPage@@IEAAJPEAVDUIXmlParser@DirectUI@@_NPEBG@Z`
- size: `986`
- prototype: `__int64 __fastcall(FinalLinksPage *this, struct DirectUI::DUIXmlParser *, char, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a6e0`
- `0x14001af10`

## callees

- `0x14000e6bc`
- `0x14001a290`
- `0x140020420`
- `0x140041c54`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001a2dd`
- `KERNEL32!HeapAlloc` at `0x14001a2dd`
- `KERNEL32!HeapFree` at `0x14001a64c`
- `KERNEL32!HeapFree` at `0x14001a64c`
- `KERNEL32!GetProcessHeap` at `0x14001a2c6`
- `KERNEL32!GetProcessHeap` at `0x14001a638`
- `KERNEL32!GetProcessHeap` at `0x14001a2c6`
- `KERNEL32!GetProcessHeap` at `0x14001a638`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a43f`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a592`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a43f`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a592`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a3ca`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a4ba`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a51d`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a604`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a3ca`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a4ba`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a51d`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001a604`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a3a6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a409`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a4f9`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a55c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a3a6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a409`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a4f9`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001a55c`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001a35e`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001a35e`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a496`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a5e3`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a496`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001a5e3`

## string_xrefs

- `0x14001a390`: `linkSpacer`
- `0x14001a4e3`: `linkSpacer`
- `0x14001a3f3`: `commandLink`
- `0x14001a546`: `commandLink`
- `0x14001a2f6`: `FinalLinksPage::CreateLinks`
- `0x14001a61c`: `FinalLinksPage::CreateLinks`

## pseudocode

```c
__int64 __fastcall FinalLinksPage::CreateLinks(
        FinalLinksPage *this,
        struct DirectUI::DUIXmlParser *a2,
        char a3,
        const unsigned __int16 *a4)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // r14
  unsigned int v10; // ebx
  int NamedElement; // eax
  int v12; // r9d
  DirectUI::Element *v13; // rsi
  const unsigned __int16 *v14; // rax
  UINT v15; // eax
  const unsigned __int16 *v16; // rax
  UINT v17; // eax
  HANDLE v18; // rax
  struct DirectUI::Element *v20; // [rsp+30h] [rbp-20h] BYREF
  struct DirectUI::Element *v21; // [rsp+38h] [rbp-18h] BYREF
  struct DirectUI::Element *v22; // [rsp+40h] [rbp-10h] BYREF

  v22 = 0;
  v21 = 0;
  v20 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( v9 )
  {
    v10 = 0;
    if ( (*(unsigned int (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 272LL))(this) )
    {
      NamedElement = WizardPage::GetNamedElement(this, a4, &v22);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 263;
LABEL_37:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::CreateLinks", v12, NamedElement);
        goto LABEL_38;
      }
      v13 = v22;
      NamedElement = DirectUI::Element::RemoveAll(v22);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 266;
        goto LABEL_37;
      }
      if ( a3 )
      {
        NamedElement = DirectUI::DUIXmlParser::CreateElement(a2, L"linkSpacer", 0, 0, 0, &v21);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 274;
          goto LABEL_37;
        }
        NamedElement = DirectUI::Element::Add(v13, v21);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 277;
          goto LABEL_37;
        }
        NamedElement = DirectUI::DUIXmlParser::CreateElement(a2, L"commandLink", 0, 0, 0, &v20);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 283;
          goto LABEL_37;
        }
        v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 288LL))(this);
        NamedElement = DirectUI::Element::SetID(v20, v14);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 286;
          goto LABEL_37;
        }
        v15 = (*(__int64 (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 304LL))(this);
        NamedElement = DwzLoadLocalString(v15, v9, 0x400u);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 289;
          goto LABEL_37;
        }
        NamedElement = DirectUI::Element::SetContentString(v20, v9);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 292;
          goto LABEL_37;
        }
        NamedElement = DirectUI::Element::Add(v13, v20);
        v10 = NamedElement;
        if ( NamedElement < 0 )
        {
          v12 = 295;
          goto LABEL_37;
        }
      }
      NamedElement = DirectUI::DUIXmlParser::CreateElement(a2, L"linkSpacer", 0, 0, 0, &v21);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 302;
        goto LABEL_37;
      }
      NamedElement = DirectUI::Element::Add(v13, v21);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 305;
        goto LABEL_37;
      }
      NamedElement = DirectUI::DUIXmlParser::CreateElement(a2, L"commandLink", 0, 0, 0, &v20);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 311;
        goto LABEL_37;
      }
      v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 296LL))(this);
      NamedElement = DirectUI::Element::SetID(v20, v16);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 314;
        goto LABEL_37;
      }
      v17 = (*(__int64 (__fastcall **)(FinalLinksPage *))(*(_QWORD *)this + 312LL))(this);
      NamedElement = DwzLoadLocalString(v17, v9, 0x400u);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 317;
        goto LABEL_37;
      }
      NamedElement = DirectUI::Element::SetContentString(v20, v9);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 320;
        goto LABEL_37;
      }
      NamedElement = DirectUI::Element::Add(v13, v20);
      v10 = NamedElement;
      if ( NamedElement < 0 )
      {
        v12 = 323;
        goto LABEL_37;
      }
    }
LABEL_38:
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v9);
    return v10;
  }
  v10 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::CreateLinks", 255, -2147024882);
  return v10;
}

```

## disassembly

```asm
0x14001a290  push    rbp
0x14001a292  push    rbx
0x14001a293  push    rsi
0x14001a294  push    rdi
0x14001a295  push    r12
0x14001a297  push    r14
0x14001a299  push    r15
0x14001a29b  mov     rbp, rsp
0x14001a29e  sub     rsp, 50h
0x14001a2a2  mov     rsi, r9
0x14001a2a5  mov     [rbp+var_10], 0
0x14001a2ad  mov     r12b, r8b
0x14001a2b0  mov     [rbp+var_18], 0
0x14001a2b8  mov     r15, rdx
0x14001a2bb  mov     [rbp+var_20], 0
0x14001a2c3  mov     rdi, rcx
0x14001a2c6  call    cs:__imp_GetProcessHeap
0x14001a2cd  nop     dword ptr [rax+rax+00h]
0x14001a2d2  xor     edx, edx; dwFlags
0x14001a2d4  mov     r8d, 800h; dwBytes
0x14001a2da  mov     rcx, rax; hHeap
0x14001a2dd  call    cs:__imp_HeapAlloc
0x14001a2e4  nop     dword ptr [rax+rax+00h]
0x14001a2e9  mov     r14, rax
0x14001a2ec  test    rax, rax
0x14001a2ef  jnz     short loc_14001A31B
0x14001a2f1  mov     ebx, 8007000Eh
0x14001a2f6  lea     r8, aFinallinkspage_5; "FinalLinksPage::CreateLinks"
0x14001a2fd  mov     r9d, 0FFh
0x14001a303  mov     dword ptr [rsp+50h+var_30], ebx
0x14001a307  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001a30e  lea     ecx, [rax+1]; Level
0x14001a311  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001a316  jmp     loc_14001A658
0x14001a31b  mov     rax, [rdi]
0x14001a31e  mov     rcx, rdi
0x14001a321  xor     ebx, ebx
0x14001a323  mov     rax, [rax+110h]
0x14001a32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a32f  test    eax, eax
0x14001a331  jz      loc_14001A638
0x14001a337  lea     r8, [rbp+var_10]; struct DirectUI::Element **
0x14001a33b  mov     rdx, rsi; unsigned __int16 *
0x14001a33e  mov     rcx, rdi; this
0x14001a341  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14001a346  mov     ebx, eax
0x14001a348  test    eax, eax
0x14001a34a  jns     short loc_14001A357
0x14001a34c  mov     r9d, 107h
0x14001a352  jmp     loc_14001A61C
0x14001a357  mov     rsi, [rbp+var_10]
0x14001a35b  mov     rcx, rsi
0x14001a35e  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x14001a365  nop     dword ptr [rax+rax+00h]
0x14001a36a  mov     ebx, eax
0x14001a36c  test    eax, eax
0x14001a36e  jns     short loc_14001A37B
0x14001a370  mov     r9d, 10Ah
0x14001a376  jmp     loc_14001A61C
0x14001a37b  test    r12b, r12b
0x14001a37e  jz      loc_14001A4D7
0x14001a384  lea     rax, [rbp+var_18]
0x14001a388  xor     r9d, r9d
0x14001a38b  mov     [rsp+50h+var_28], rax
0x14001a390  lea     rdx, aLinkspacer; "linkSpacer"
0x14001a397  xor     r8d, r8d
0x14001a39a  mov     [rsp+50h+var_30], 0
0x14001a3a3  mov     rcx, r15
0x14001a3a6  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001a3ad  nop     dword ptr [rax+rax+00h]
0x14001a3b2  mov     ebx, eax
0x14001a3b4  test    eax, eax
0x14001a3b6  jns     short loc_14001A3C3
0x14001a3b8  mov     r9d, 112h
0x14001a3be  jmp     loc_14001A61C
0x14001a3c3  mov     rdx, [rbp+var_18]
0x14001a3c7  mov     rcx, rsi
0x14001a3ca  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001a3d1  nop     dword ptr [rax+rax+00h]
0x14001a3d6  mov     ebx, eax
0x14001a3d8  test    eax, eax
0x14001a3da  jns     short loc_14001A3E7
0x14001a3dc  mov     r9d, 115h
0x14001a3e2  jmp     loc_14001A61C
0x14001a3e7  lea     rax, [rbp+var_20]
0x14001a3eb  xor     r9d, r9d
0x14001a3ee  mov     [rsp+50h+var_28], rax
0x14001a3f3  lea     rdx, aCommandlink; "commandLink"
0x14001a3fa  xor     r8d, r8d
0x14001a3fd  mov     [rsp+50h+var_30], 0
0x14001a406  mov     rcx, r15
0x14001a409  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001a410  nop     dword ptr [rax+rax+00h]
0x14001a415  mov     ebx, eax
0x14001a417  test    eax, eax
0x14001a419  jns     short loc_14001A426
0x14001a41b  mov     r9d, 11Bh
0x14001a421  jmp     loc_14001A61C
0x14001a426  mov     rax, [rdi]
0x14001a429  mov     rcx, rdi
0x14001a42c  mov     rax, [rax+120h]
0x14001a433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a438  mov     rcx, [rbp+var_20]
0x14001a43c  mov     rdx, rax
0x14001a43f  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x14001a446  nop     dword ptr [rax+rax+00h]
0x14001a44b  mov     ebx, eax
0x14001a44d  test    eax, eax
0x14001a44f  jns     short loc_14001A45C
0x14001a451  mov     r9d, 11Eh
0x14001a457  jmp     loc_14001A61C
0x14001a45c  mov     rax, [rdi]
0x14001a45f  mov     rcx, rdi
0x14001a462  mov     rax, [rax+130h]
0x14001a469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a46e  mov     ecx, eax; uID
0x14001a470  mov     r8d, 400h; cchBufferMax
0x14001a476  mov     rdx, r14; lpBuffer
0x14001a479  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001a47e  mov     ebx, eax
0x14001a480  test    eax, eax
0x14001a482  jns     short loc_14001A48F
0x14001a484  mov     r9d, 121h
0x14001a48a  jmp     loc_14001A61C
0x14001a48f  mov     rcx, [rbp+var_20]
0x14001a493  mov     rdx, r14
0x14001a496  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x14001a49d  nop     dword ptr [rax+rax+00h]
0x14001a4a2  mov     ebx, eax
0x14001a4a4  test    eax, eax
0x14001a4a6  jns     short loc_14001A4B3
0x14001a4a8  mov     r9d, 124h
0x14001a4ae  jmp     loc_14001A61C
0x14001a4b3  mov     rdx, [rbp+var_20]
0x14001a4b7  mov     rcx, rsi
0x14001a4ba  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001a4c1  nop     dword ptr [rax+rax+00h]
0x14001a4c6  mov     ebx, eax
0x14001a4c8  test    eax, eax
0x14001a4ca  jns     short loc_14001A4D7
0x14001a4cc  mov     r9d, 127h
0x14001a4d2  jmp     loc_14001A61C
0x14001a4d7  lea     rax, [rbp+var_18]
0x14001a4db  xor     r9d, r9d
0x14001a4de  mov     [rsp+50h+var_28], rax
0x14001a4e3  lea     rdx, aLinkspacer; "linkSpacer"
0x14001a4ea  xor     r8d, r8d
0x14001a4ed  mov     [rsp+50h+var_30], 0
0x14001a4f6  mov     rcx, r15
0x14001a4f9  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001a500  nop     dword ptr [rax+rax+00h]
0x14001a505  mov     ebx, eax
0x14001a507  test    eax, eax
0x14001a509  jns     short loc_14001A516
0x14001a50b  mov     r9d, 12Eh
0x14001a511  jmp     loc_14001A61C
0x14001a516  mov     rdx, [rbp+var_18]
0x14001a51a  mov     rcx, rsi
0x14001a51d  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001a524  nop     dword ptr [rax+rax+00h]
0x14001a529  mov     ebx, eax
0x14001a52b  test    eax, eax
0x14001a52d  jns     short loc_14001A53A
0x14001a52f  mov     r9d, 131h
0x14001a535  jmp     loc_14001A61C
0x14001a53a  lea     rax, [rbp+var_20]
0x14001a53e  xor     r9d, r9d
0x14001a541  mov     [rsp+50h+var_28], rax
0x14001a546  lea     rdx, aCommandlink; "commandLink"
0x14001a54d  xor     r8d, r8d
0x14001a550  mov     [rsp+50h+var_30], 0
0x14001a559  mov     rcx, r15
0x14001a55c  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001a563  nop     dword ptr [rax+rax+00h]
0x14001a568  mov     ebx, eax
0x14001a56a  test    eax, eax
0x14001a56c  jns     short loc_14001A579
0x14001a56e  mov     r9d, 137h
0x14001a574  jmp     loc_14001A61C
0x14001a579  mov     rax, [rdi]
0x14001a57c  mov     rcx, rdi
0x14001a57f  mov     rax, [rax+128h]
0x14001a586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a58b  mov     rcx, [rbp+var_20]
0x14001a58f  mov     rdx, rax
0x14001a592  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x14001a599  nop     dword ptr [rax+rax+00h]
0x14001a59e  mov     ebx, eax
0x14001a5a0  test    eax, eax
0x14001a5a2  jns     short loc_14001A5AC
0x14001a5a4  mov     r9d, 13Ah
0x14001a5aa  jmp     short loc_14001A61C
0x14001a5ac  mov     rax, [rdi]
0x14001a5af  mov     rcx, rdi
0x14001a5b2  mov     rax, [rax+138h]
0x14001a5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5be  mov     ecx, eax; uID
0x14001a5c0  mov     r8d, 400h; cchBufferMax
0x14001a5c6  mov     rdx, r14; lpBuffer
0x14001a5c9  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001a5ce  mov     ebx, eax
0x14001a5d0  test    eax, eax
0x14001a5d2  jns     short loc_14001A5DC
0x14001a5d4  mov     r9d, 13Dh
0x14001a5da  jmp     short loc_14001A61C
0x14001a5dc  mov     rcx, [rbp+var_20]
0x14001a5e0  mov     rdx, r14
0x14001a5e3  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x14001a5ea  nop     dword ptr [rax+rax+00h]
0x14001a5ef  mov     ebx, eax
0x14001a5f1  test    eax, eax
0x14001a5f3  jns     short loc_14001A5FD
0x14001a5f5  mov     r9d, 140h
0x14001a5fb  jmp     short loc_14001A61C
0x14001a5fd  mov     rdx, [rbp+var_20]
0x14001a601  mov     rcx, rsi
0x14001a604  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001a60b  nop     dword ptr [rax+rax+00h]
0x14001a610  mov     ebx, eax
0x14001a612  test    eax, eax
0x14001a614  jns     short loc_14001A638
0x14001a616  mov     r9d, 143h
0x14001a61c  lea     r8, aFinallinkspage_5; "FinalLinksPage::CreateLinks"
0x14001a623  mov     dword ptr [rsp+50h+var_30], eax
0x14001a627  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001a62e  mov     ecx, 1; Level
0x14001a633  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001a638  call    cs:__imp_GetProcessHeap
0x14001a63f  nop     dword ptr [rax+rax+00h]
0x14001a644  mov     r8, r14; lpMem
0x14001a647  xor     edx, edx; dwFlags
0x14001a649  mov     rcx, rax; hHeap
0x14001a64c  call    cs:__imp_HeapFree
0x14001a653  nop     dword ptr [rax+rax+00h]
0x14001a658  mov     eax, ebx
0x14001a65a  add     rsp, 50h
0x14001a65e  pop     r15
0x14001a660  pop     r14
0x14001a662  pop     r12
0x14001a664  pop     rdi
0x14001a665  pop     rsi
0x14001a666  pop     rbx
0x14001a667  pop     rbp
0x14001a668  retn
```
