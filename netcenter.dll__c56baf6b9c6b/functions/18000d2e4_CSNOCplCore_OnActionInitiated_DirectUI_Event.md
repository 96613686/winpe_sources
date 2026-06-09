# CSNOCplCore::OnActionInitiated(DirectUI::Event *)

- ea: `0x18000d2e4`
- end: `0x18000d746`
- name: `?OnActionInitiated@CSNOCplCore@@AEAAXPEAUEvent@DirectUI@@@Z`
- size: `1122`
- prototype: `void __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Event *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180002270`
- `0x180006b70`
- `0x180008f24`
- `0x1800099fc`
- `0x180009aec`
- `0x18000a7f4`
- `0x18000ae44`
- `0x18000d2e4`
- `0x18000db9c`
- `0x18000dd74`
- `0x18000e564`
- `0x1800126b0`
- `0x180013ad4`
- `0x180014218`
- `0x180023010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x18000d6ee`
- `ntdll!WinSqmAddToStream` at `0x18000d6ee`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18000d658`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18000d658`
- `DUI70!StrToID` at `0x18000d38a`
- `DUI70!StrToID` at `0x18000d4de`
- `DUI70!StrToID` at `0x18000d540`
- `DUI70!StrToID` at `0x18000d5ae`
- `DUI70!StrToID` at `0x18000d5fb`
- `DUI70!StrToID` at `0x18000d6a5`
- `DUI70!StrToID` at `0x18000d38a`
- `DUI70!StrToID` at `0x18000d4de`
- `DUI70!StrToID` at `0x18000d540`
- `DUI70!StrToID` at `0x18000d5ae`
- `DUI70!StrToID` at `0x18000d5fb`
- `DUI70!StrToID` at `0x18000d6a5`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000d396`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000d4c5`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000d396`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000d4c5`

## string_xrefs

- `0x18000d4d7`: `createnewbtn`

## pseudocode

```c
void __fastcall CSNOCplCore::OnActionInitiated(struct IUnknown **this, struct DirectUI::Event *a2)
{
  CSNOCplCore *v4; // rcx
  unsigned int v5; // r15d
  int v6; // esi
  unsigned int v7; // r12d
  __int16 v8; // bx
  unsigned __int16 ID; // ax
  unsigned int v10; // ecx
  __int64 v11; // rcx
  const struct _GUID *v12; // rdx
  unsigned __int16 v13; // bx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // edx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rdx
  __int64 v22; // r8
  HRESULT v23; // ebx
  HWND ParentWindow; // rax
  struct IUnknown *v25; // rcx
  struct IShellItem *ppv; // [rsp+30h] [rbp-40h] BYREF
  struct _GUID v27; // [rsp+38h] [rbp-38h] BYREF
  size_t pcchLength[2]; // [rsp+48h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+58h] [rbp-18h] BYREF

  v4 = (CSNOCplCore *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
  LODWORD(ppv) = 0;
  v27 = 0;
  *(_OWORD *)pcchLength = 0;
  CSNOCplCore::GetEventInfo(v4, a2, (unsigned int *)&ppv, &v27, (size_t)pcchLength);
  v5 = 0;
  v6 = 0;
  v7 = 0;
  while ( !v6 )
  {
    v8 = StrToID(*((_QWORD *)&unk_180025CF0 + 2 * (int)v7 + 1));
    ID = DirectUI::Element::GetID(*(DirectUI::Element **)a2);
    v10 = v7;
    if ( ID == v8 )
      v6 = 1;
    else
      v10 = v5;
    ++v7;
    v5 = v10;
    if ( v7 >= 9 )
    {
      if ( !v6 )
      {
        v11 = 1;
        goto LABEL_13;
      }
      break;
    }
  }
  v11 = *((unsigned int *)&unk_180025CF0 + 4 * v5);
LABEL_13:
  _ReportFollowupAction(v11);
  if ( (_DWORD)ppv )
  {
    switch ( (_DWORD)ppv )
    {
      case 2:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        CSNOCplCore::OnLaunchNetConnStatus((CSNOCplCore *)this, &v27);
        goto LABEL_60;
      case 3:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        CSNOCplCore::DisconnectWirelessConnection((CSNOCplCore *)this, v12, &v27);
        goto LABEL_60;
      case 5:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        CSNOCplCore::DisconnectRASConnection((CSNOCplCore *)this, &v27);
        goto LABEL_60;
    }
  }
  v13 = DirectUI::Element::GetID(*(DirectUI::Element **)a2);
  if ( !v13 )
    goto LABEL_60;
  if ( v13 == (unsigned __int16)StrToID(L"createnewbtn") )
  {
    if ( (Microsoft_Windows_Network_and_Sharing_CenterEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v14, (int)&Perf_InvokeUI_SetUpNewNetwork_Start, v15, v16, &v29);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v17 = 0;
LABEL_44:
    CSNOCplCore::OnLaunchRelevantTaskWindow((CSNOCplCore *)this, v17);
    goto LABEL_60;
  }
  if ( v13 == (unsigned __int16)StrToID(L"diagnosebtn") )
  {
    if ( (Microsoft_Windows_Network_and_Sharing_CenterEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v18, (int)&Perf_InvokeUI_FixNetworkProblem_Start, v19, v20, &v29);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v17 = 1;
    goto LABEL_44;
  }
  if ( v13 == (unsigned __int16)StrToID(L"moreinfobtn") )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    CSNOCplCore::OnStartNetprofmDlg((CSNOCplCore *)this, v21, v22);
  }
  else if ( v13 == (unsigned __int16)StrToID(L"networkexplorerbtn") )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    ppv = 0;
    v23 = SHCreateItemInKnownFolder(
            &FOLDERID_NetworkFolder,
            0,
            0,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            (void **)&ppv);
    if ( v23 < 0
      || (v23 = BrowseToItem(this[43], ppv),
          ((void (__fastcall *)(struct IShellItem *))ppv->lpVtbl->Release)(ppv),
          v23 < 0) )
    {
      ParentWindow = CSNOCplCore::GetParentWindow((CSNOCplCore *)this);
      ThrowErrorBox(ParentWindow, v23);
    }
  }
  else if ( v13 == (unsigned __int16)StrToID(L"HomeGroupStatus") )
  {
    v25 = this[44];
    LODWORD(ppv) = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, struct IShellItem **))v25->lpVtbl[1].QueryInterface)(v25, &ppv) >= 0 )
    {
      v29 = 0;
      v29.Size = (unsigned int)ppv;
      LODWORD(v29.Ptr) = 1;
      WinSqmAddToStream(0, 3698, 1, &v29);
    }
  }
LABEL_60:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
}

```

## disassembly

```asm
0x18000d2e4  mov     [rsp-38h+arg_10], rbx
0x18000d2e9  push    rbp
0x18000d2ea  push    rsi
0x18000d2eb  push    rdi
0x18000d2ec  push    r12
0x18000d2ee  push    r13
0x18000d2f0  push    r14
0x18000d2f2  push    r15
0x18000d2f4  mov     rbp, rsp
0x18000d2f7  sub     rsp, 70h
0x18000d2fb  mov     rax, cs:__security_cookie
0x18000d302  xor     rax, rsp
0x18000d305  mov     [rbp+var_8], rax
0x18000d309  mov     r14, rdx
0x18000d30c  mov     rdi, rcx
0x18000d30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d316  lea     rax, WPP_GLOBAL_Control
0x18000d31d  cmp     rcx, rax
0x18000d320  jz      short loc_18000D33D
0x18000d322  test    byte ptr [rcx+1Ch], 8
0x18000d326  jz      short loc_18000D33D
0x18000d328  mov     rcx, [rcx+10h]
0x18000d32c  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d333  mov     edx, 40h ; '@'
0x18000d338  call    WPP_SF_
0x18000d33d  xor     r13d, r13d
0x18000d340  lea     rax, [rbp+pcchLength]
0x18000d344  xorps   xmm0, xmm0
0x18000d347  mov     dword ptr [rbp+var_40], r13d
0x18000d34b  xorps   xmm1, xmm1
0x18000d34e  mov     [rsp+70h+ppv], rax; pcchLength
0x18000d353  lea     r9, [rbp+var_38]; struct _GUID *
0x18000d357  mov     rdx, r14; struct DirectUI::Event *
0x18000d35a  lea     r8, [rbp+var_40]; unsigned int *
0x18000d35e  movups  xmmword ptr [rbp+var_38.Data1], xmm0
0x18000d362  movups  xmmword ptr [rbp+pcchLength], xmm1
0x18000d366  call    ?GetEventInfo@CSNOCplCore@@AEAAXPEAUEvent@DirectUI@@PEAKPEAU_GUID@@2@Z; CSNOCplCore::GetEventInfo(DirectUI::Event *,ulong *,_GUID *,_GUID *)
0x18000d36b  lea     rax, unk_180025CF0
0x18000d372  mov     r15d, r13d
0x18000d375  mov     esi, r13d
0x18000d378  mov     r12d, r13d
0x18000d37b  test    esi, esi
0x18000d37d  jnz     short loc_18000D3CA
0x18000d37f  movsxd  rcx, r12d
0x18000d382  add     rcx, rcx
0x18000d385  mov     rcx, [rax+rcx*8+8]
0x18000d38a  call    cs:__imp_StrToID
0x18000d390  mov     rcx, [r14]
0x18000d393  movzx   ebx, ax
0x18000d396  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18000d39c  lea     edx, [rsi+1]
0x18000d39f  mov     ecx, r12d
0x18000d3a2  cmp     ax, bx
0x18000d3a5  lea     rax, unk_180025CF0
0x18000d3ac  cmovnz  ecx, r15d
0x18000d3b0  cmovz   esi, edx
0x18000d3b3  add     r12d, edx
0x18000d3b6  mov     r15d, ecx
0x18000d3b9  cmp     r12d, 9
0x18000d3bd  jb      short loc_18000D37B
0x18000d3bf  test    esi, esi
0x18000d3c1  jnz     short loc_18000D3CA
0x18000d3c3  mov     r15d, edx
0x18000d3c6  mov     ecx, edx
0x18000d3c8  jmp     short loc_18000D3E0
0x18000d3ca  mov     eax, r15d
0x18000d3cd  lea     rcx, unk_180025CF0
0x18000d3d4  add     rax, rax
0x18000d3d7  mov     r15d, 1
0x18000d3dd  mov     ecx, [rcx+rax*8]
0x18000d3e0  call    ?_ReportFollowupAction@@YAXW4TRACKABLE_CLICK_SITE@@@Z; _ReportFollowupAction(TRACKABLE_CLICK_SITE)
0x18000d3e5  mov     eax, dword ptr [rbp+var_40]
0x18000d3e8  test    eax, eax
0x18000d3ea  jz      loc_18000D4C2
0x18000d3f0  sub     eax, 2
0x18000d3f3  jz      loc_18000D483
0x18000d3f9  sub     eax, 1
0x18000d3fc  jz      short loc_18000D444
0x18000d3fe  cmp     eax, 2
0x18000d401  jnz     loc_18000D4C2
0x18000d407  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d40e  lea     rsi, WPP_GLOBAL_Control
0x18000d415  cmp     rcx, rsi
0x18000d418  jz      short loc_18000D433
0x18000d41a  test    byte ptr [rcx+1Ch], 8
0x18000d41e  jz      short loc_18000D433
0x18000d420  mov     rcx, [rcx+10h]
0x18000d424  lea     edx, [rax+41h]
0x18000d427  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d42e  call    WPP_SF_
0x18000d433  lea     rdx, [rbp+var_38]; struct _GUID *
0x18000d437  mov     rcx, rdi; this
0x18000d43a  call    ?DisconnectRASConnection@CSNOCplCore@@AEAAXAEBU_GUID@@@Z; CSNOCplCore::DisconnectRASConnection(_GUID const &)
0x18000d43f  jmp     loc_18000D6FB
0x18000d444  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d44b  lea     rsi, WPP_GLOBAL_Control
0x18000d452  cmp     rcx, rsi
0x18000d455  jz      short loc_18000D472
0x18000d457  test    byte ptr [rcx+1Ch], 8
0x18000d45b  jz      short loc_18000D472
0x18000d45d  mov     rcx, [rcx+10h]
0x18000d461  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d468  mov     edx, 42h ; 'B'
0x18000d46d  call    WPP_SF_
0x18000d472  lea     r8, [rbp+var_38]; struct _GUID *
0x18000d476  mov     rcx, rdi; this
0x18000d479  call    ?DisconnectWirelessConnection@CSNOCplCore@@AEAAJAEBU_GUID@@0@Z; CSNOCplCore::DisconnectWirelessConnection(_GUID const &,_GUID const &)
0x18000d47e  jmp     loc_18000D6FB
0x18000d483  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d48a  lea     rsi, WPP_GLOBAL_Control
0x18000d491  cmp     rcx, rsi
0x18000d494  jz      short loc_18000D4B1
0x18000d496  test    byte ptr [rcx+1Ch], 8
0x18000d49a  jz      short loc_18000D4B1
0x18000d49c  mov     rcx, [rcx+10h]
0x18000d4a0  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d4a7  mov     edx, 41h ; 'A'
0x18000d4ac  call    WPP_SF_
0x18000d4b1  lea     rdx, [rbp+var_38]; struct _GUID *
0x18000d4b5  mov     rcx, rdi; this
0x18000d4b8  call    ?OnLaunchNetConnStatus@CSNOCplCore@@AEAAXAEBU_GUID@@@Z; CSNOCplCore::OnLaunchNetConnStatus(_GUID const &)
0x18000d4bd  jmp     loc_18000D6FB
0x18000d4c2  mov     rcx, [r14]
0x18000d4c5  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18000d4cb  movzx   ebx, ax
0x18000d4ce  test    ax, ax
0x18000d4d1  jz      loc_18000D6F4
0x18000d4d7  lea     rcx, aCreatenewbtn; "createnewbtn"
0x18000d4de  call    cs:__imp_StrToID
0x18000d4e4  cmp     bx, ax
0x18000d4e7  jnz     short loc_18000D539
0x18000d4e9  test    cs:Microsoft_Windows_Network_and_Sharing_CenterEnableBits, 2
0x18000d4f0  jz      short loc_18000D507
0x18000d4f2  lea     rax, [rbp+var_18]
0x18000d4f6  lea     rdx, Perf_InvokeUI_SetUpNewNetwork_Start; int
0x18000d4fd  mov     [rsp+70h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18000d502  call    McGenEventWrite_EventWriteTransfer
0x18000d507  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d50e  lea     rsi, WPP_GLOBAL_Control
0x18000d515  cmp     rcx, rsi
0x18000d518  jz      short loc_18000D535
0x18000d51a  test    byte ptr [rcx+1Ch], 8
0x18000d51e  jz      short loc_18000D535
0x18000d520  mov     rcx, [rcx+10h]
0x18000d524  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d52b  mov     edx, 44h ; 'D'
0x18000d530  call    WPP_SF_
0x18000d535  xor     edx, edx
0x18000d537  jmp     short loc_18000D59A
0x18000d539  lea     rcx, aDiagnosebtn; "diagnosebtn"
0x18000d540  call    cs:__imp_StrToID
0x18000d546  cmp     bx, ax
0x18000d549  jnz     short loc_18000D5A7
0x18000d54b  test    cs:Microsoft_Windows_Network_and_Sharing_CenterEnableBits, r15b
0x18000d552  jz      short loc_18000D569
0x18000d554  lea     rax, [rbp+var_18]
0x18000d558  lea     rdx, Perf_InvokeUI_FixNetworkProblem_Start; int
0x18000d55f  mov     [rsp+70h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18000d564  call    McGenEventWrite_EventWriteTransfer
0x18000d569  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d570  lea     rsi, WPP_GLOBAL_Control
0x18000d577  cmp     rcx, rsi
0x18000d57a  jz      short loc_18000D597
0x18000d57c  test    byte ptr [rcx+1Ch], 8
0x18000d580  jz      short loc_18000D597
0x18000d582  mov     rcx, [rcx+10h]
0x18000d586  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d58d  mov     edx, 45h ; 'E'
0x18000d592  call    WPP_SF_
0x18000d597  mov     edx, r15d; unsigned int
0x18000d59a  mov     rcx, rdi; this
0x18000d59d  call    ?OnLaunchRelevantTaskWindow@CSNOCplCore@@AEAAXK@Z; CSNOCplCore::OnLaunchRelevantTaskWindow(ulong)
0x18000d5a2  jmp     loc_18000D6FB
0x18000d5a7  lea     rcx, aMoreinfobtn; "moreinfobtn"
0x18000d5ae  call    cs:__imp_StrToID
0x18000d5b4  cmp     bx, ax
0x18000d5b7  jnz     short loc_18000D5F4
0x18000d5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5c0  lea     rsi, WPP_GLOBAL_Control
0x18000d5c7  cmp     rcx, rsi
0x18000d5ca  jz      short loc_18000D5E7
0x18000d5cc  test    byte ptr [rcx+1Ch], 8
0x18000d5d0  jz      short loc_18000D5E7
0x18000d5d2  mov     rcx, [rcx+10h]
0x18000d5d6  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d5dd  mov     edx, 46h ; 'F'
0x18000d5e2  call    WPP_SF_
0x18000d5e7  mov     rcx, rdi; this
0x18000d5ea  call    ?OnStartNetprofmDlg@CSNOCplCore@@AEAAXXZ; CSNOCplCore::OnStartNetprofmDlg(void)
0x18000d5ef  jmp     loc_18000D6FB
0x18000d5f4  lea     rcx, aNetworkexplore; "networkexplorerbtn"
0x18000d5fb  call    cs:__imp_StrToID
0x18000d601  cmp     bx, ax
0x18000d604  jnz     loc_18000D69E
0x18000d60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d611  lea     rsi, WPP_GLOBAL_Control
0x18000d618  cmp     rcx, rsi
0x18000d61b  jz      short loc_18000D638
0x18000d61d  test    byte ptr [rcx+1Ch], 8
0x18000d621  jz      short loc_18000D638
0x18000d623  mov     rcx, [rcx+10h]
0x18000d627  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d62e  mov     edx, 47h ; 'G'
0x18000d633  call    WPP_SF_
0x18000d638  lea     rax, [rbp+var_40]
0x18000d63c  mov     [rbp+var_40], r13
0x18000d640  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000d647  mov     [rsp+70h+ppv], rax; ppv
0x18000d64c  xor     r8d, r8d; pszItem
0x18000d64f  lea     rcx, FOLDERID_NetworkFolder; kfid
0x18000d656  xor     edx, edx; dwKFFlags
0x18000d658  call    cs:__imp_SHCreateItemInKnownFolder
0x18000d65e  mov     ebx, eax
0x18000d660  test    eax, eax
0x18000d662  js      short loc_18000D68A
0x18000d664  mov     rdx, [rbp+var_40]; struct IShellItem *
0x18000d668  mov     rcx, [rdi+158h]; struct IUnknown *
0x18000d66f  call    ?BrowseToItem@@YAJPEAUIUnknown@@PEAUIShellItem@@@Z; BrowseToItem(IUnknown *,IShellItem *)
0x18000d674  mov     rcx, [rbp+var_40]
0x18000d678  mov     ebx, eax
0x18000d67a  mov     rax, [rcx]
0x18000d67d  mov     rax, [rax+10h]
0x18000d681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d686  test    ebx, ebx
0x18000d688  jns     short loc_18000D6FB
0x18000d68a  mov     rcx, rdi; this
0x18000d68d  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x18000d692  mov     rcx, rax; hWnd
0x18000d695  mov     edx, ebx; dwMessageId
0x18000d697  call    ?ThrowErrorBox@@YAXQEAUHWND__@@J@Z; ThrowErrorBox(HWND__ * const,long)
0x18000d69c  jmp     short loc_18000D6FB
0x18000d69e  lea     rcx, aHomegroupstatu; "HomeGroupStatus"
0x18000d6a5  call    cs:__imp_StrToID
0x18000d6ab  cmp     bx, ax
0x18000d6ae  jnz     short loc_18000D6F4
0x18000d6b0  mov     rcx, [rdi+160h]
0x18000d6b7  lea     rdx, [rbp+var_40]
0x18000d6bb  mov     dword ptr [rbp+var_40], r13d
0x18000d6bf  mov     rax, [rcx]
0x18000d6c2  mov     rax, [rax+18h]
0x18000d6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6cb  test    eax, eax
0x18000d6cd  js      short loc_18000D6F4
0x18000d6cf  mov     eax, dword ptr [rbp+var_40]
0x18000d6d2  lea     r9, [rbp+var_18]
0x18000d6d6  xorps   xmm0, xmm0
0x18000d6d9  mov     r8d, r15d
0x18000d6dc  movups  xmmword ptr [rbp+var_18.Ptr], xmm0
0x18000d6e0  mov     edx, 0E72h
0x18000d6e5  mov     [rbp+var_18.Size], eax
0x18000d6e8  xor     ecx, ecx
0x18000d6ea  mov     dword ptr [rbp+var_18.Ptr], r15d
0x18000d6ee  call    cs:__imp_WinSqmAddToStream
0x18000d6f4  lea     rsi, WPP_GLOBAL_Control
0x18000d6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d702  cmp     rcx, rsi
0x18000d705  jz      short loc_18000D722
0x18000d707  test    byte ptr [rcx+1Ch], 8
0x18000d70b  jz      short loc_18000D722
0x18000d70d  mov     rcx, [rcx+10h]
0x18000d711  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d718  mov     edx, 48h ; 'H'
0x18000d71d  call    WPP_SF_
0x18000d722  mov     rcx, [rbp+var_8]
0x18000d726  xor     rcx, rsp; StackCookie
0x18000d729  call    __security_check_cookie
0x18000d72e  mov     rbx, [rsp+70h+arg_10]
0x18000d736  add     rsp, 70h
0x18000d73a  pop     r15
0x18000d73c  pop     r14
0x18000d73e  pop     r13
0x18000d740  pop     r12
0x18000d742  pop     rdi
0x18000d743  pop     rsi
0x18000d744  pop     rbp
0x18000d745  retn
```
