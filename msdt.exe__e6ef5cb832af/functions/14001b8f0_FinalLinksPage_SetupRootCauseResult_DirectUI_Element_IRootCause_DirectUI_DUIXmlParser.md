# FinalLinksPage::SetupRootCauseResult(DirectUI::Element *,IRootCause *,DirectUI::DUIXmlParser *)

- ea: `0x14001b8f0`
- end: `0x14001bbcf`
- name: `?SetupRootCauseResult@FinalLinksPage@@MEAAJPEAVElement@DirectUI@@PEAVIRootCause@@PEAVDUIXmlParser@3@@Z`
- size: `735`
- prototype: `__int64 __fastcall(FinalLinksPage *__hidden this, struct DirectUI::Element *, struct IRootCause *, struct DirectUI::DUIXmlParser *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x140010308`
- `0x14001b8f0`
- `0x140020420`
- `0x140041c54`
- `0x14004e43c`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001b931`
- `KERNEL32!HeapAlloc` at `0x14001b931`
- `KERNEL32!HeapFree` at `0x14001bbb1`
- `KERNEL32!HeapFree` at `0x14001bbb1`
- `KERNEL32!GetProcessHeap` at `0x14001b91a`
- `KERNEL32!GetProcessHeap` at `0x14001bb9d`
- `KERNEL32!GetProcessHeap` at `0x14001b91a`
- `KERNEL32!GetProcessHeap` at `0x14001bb9d`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bb83`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bb83`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001bb45`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001bb45`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001badd`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14001badd`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001bb23`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001bb23`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001ba52`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14001ba52`
- `DUI70!StrToID` at `0x14001b960`
- `DUI70!StrToID` at `0x14001b99f`
- `DUI70!StrToID` at `0x14001b960`
- `DUI70!StrToID` at `0x14001b99f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b972`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b9b1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b972`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001b9b1`

## string_xrefs

- `0x14001bb61`: `FinalLinksPage::SetupRootCauseResult`

## pseudocode

```c
__int64 __fastcall FinalLinksPage::SetupRootCauseResult(
        FinalLinksPage *this,
        struct DirectUI::Element *a2,
        struct IRootCause *a3,
        struct DirectUI::DUIXmlParser *a4)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rsi
  unsigned int v9; // ebx
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // r14
  int LocalString; // eax
  int v13; // r9d
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rbp
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  UINT v20; // ecx
  const unsigned __int16 *v21; // rdi
  WizardPage *v22; // rcx
  WizardPage *v23; // rcx
  HANDLE v24; // rax
  BSTR bstrString; // [rsp+30h] [rbp-48h] BYREF
  struct DirectUI::Element *v27; // [rsp+38h] [rbp-40h] BYREF

  v27 = 0;
  bstrString = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v8 )
  {
    v9 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::SetupRootCauseResult", 567, -2147024882);
    goto LABEL_35;
  }
  v10 = StrToID(L"txtResult");
  Descendent = DirectUI::Element::FindDescendent(a2, v10);
  if ( !Descendent )
  {
    LocalString = -2147418113;
    v13 = 570;
    v9 = -2147418113;
    goto LABEL_34;
  }
  v14 = StrToID(L"rcpic");
  v15 = DirectUI::Element::FindDescendent(a2, v14);
  if ( !v15 )
  {
    LocalString = -2147418113;
    v13 = 573;
    v9 = -2147418113;
    goto LABEL_34;
  }
  v16 = RootCause_GetState(a3) - 1;
  if ( !v16 || (v17 = v16 - 1) == 0 )
  {
    v21 = L"warningicon";
    v20 = 118;
    goto LABEL_18;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    v20 = 119;
    goto LABEL_16;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
    v20 = 116;
LABEL_16:
    v21 = L"checkicon";
    goto LABEL_18;
  }
  if ( v19 == 1 )
  {
    v20 = 117;
    v21 = L"failicon";
  }
  else
  {
    v20 = 0;
    v21 = 0;
  }
LABEL_18:
  LocalString = DwzLoadLocalString(v20, v8, 0x400u);
  v9 = LocalString;
  if ( LocalString >= 0 )
  {
    LocalString = DirectUI::Element::SetContentString(Descendent, v8);
    v9 = LocalString;
    if ( LocalString >= 0 )
    {
      LocalString = (*(__int64 (__fastcall **)(struct IRootCause *, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
      v9 = LocalString;
      if ( LocalString >= 0 )
      {
        LocalString = WizardPage::SetAccValues(v22, Descendent, bstrString, v8, 0);
        v9 = LocalString;
        if ( LocalString >= 0 )
        {
          LocalString = DirectUI::DUIXmlParser::CreateElement(a4, v21, 0, 0, 0, &v27);
          v9 = LocalString;
          if ( LocalString >= 0 )
          {
            LocalString = WizardPage::SetAccValues(v23, v27, bstrString, v8, 0);
            v9 = LocalString;
            if ( LocalString >= 0 )
            {
              LocalString = DirectUI::Element::RemoveAll(v15);
              v9 = LocalString;
              if ( LocalString >= 0 )
              {
                LocalString = DirectUI::Element::Add(v15, v27);
                v9 = LocalString;
                if ( LocalString >= 0 )
                  goto LABEL_35;
                v13 = 638;
              }
              else
              {
                v13 = 635;
              }
            }
            else
            {
              v13 = 632;
            }
          }
          else
          {
            v13 = 626;
          }
        }
        else
        {
          v13 = 620;
        }
      }
      else
      {
        v13 = 617;
      }
    }
    else
    {
      v13 = 614;
    }
  }
  else
  {
    v13 = 611;
  }
LABEL_34:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalLinksPage::SetupRootCauseResult", v13, LocalString);
LABEL_35:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v8 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x14001b8f0  push    rbx
0x14001b8f2  push    rbp
0x14001b8f3  push    rsi
0x14001b8f4  push    rdi
0x14001b8f5  push    r12
0x14001b8f7  push    r14
0x14001b8f9  push    r15
0x14001b8fb  sub     rsp, 40h
0x14001b8ff  mov     r12, r9
0x14001b902  mov     [rsp+78h+var_40], 0
0x14001b90b  mov     r15, r8
0x14001b90e  mov     [rsp+78h+bstrString], 0
0x14001b917  mov     rbx, rdx
0x14001b91a  call    cs:__imp_GetProcessHeap
0x14001b921  nop     dword ptr [rax+rax+00h]
0x14001b926  xor     edx, edx; dwFlags
0x14001b928  mov     r8d, 800h; dwBytes
0x14001b92e  mov     rcx, rax; hHeap
0x14001b931  call    cs:__imp_HeapAlloc
0x14001b938  nop     dword ptr [rax+rax+00h]
0x14001b93d  mov     rsi, rax
0x14001b940  test    rax, rax
0x14001b943  jnz     short loc_14001B959
0x14001b945  mov     ebx, 8007000Eh
0x14001b94a  mov     r9d, 237h
0x14001b950  mov     dword ptr [rsp+78h+var_58], ebx
0x14001b954  jmp     loc_14001BB61
0x14001b959  lea     rcx, aTxtresult; "txtResult"
0x14001b960  call    cs:__imp_StrToID
0x14001b967  nop     dword ptr [rax+rax+00h]
0x14001b96c  movzx   edx, ax
0x14001b96f  mov     rcx, rbx
0x14001b972  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001b979  nop     dword ptr [rax+rax+00h]
0x14001b97e  mov     r14, rax
0x14001b981  test    rax, rax
0x14001b984  jnz     short loc_14001B998
0x14001b986  mov     eax, 8000FFFFh
0x14001b98b  mov     r9d, 23Ah
0x14001b991  mov     ebx, eax
0x14001b993  jmp     loc_14001BB5D
0x14001b998  lea     rcx, aRcpic; "rcpic"
0x14001b99f  call    cs:__imp_StrToID
0x14001b9a6  nop     dword ptr [rax+rax+00h]
0x14001b9ab  movzx   edx, ax
0x14001b9ae  mov     rcx, rbx
0x14001b9b1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001b9b8  nop     dword ptr [rax+rax+00h]
0x14001b9bd  mov     rbp, rax
0x14001b9c0  test    rax, rax
0x14001b9c3  jnz     short loc_14001B9D7
0x14001b9c5  mov     eax, 8000FFFFh
0x14001b9ca  mov     r9d, 23Dh
0x14001b9d0  mov     ebx, eax
0x14001b9d2  jmp     loc_14001BB5D
0x14001b9d7  mov     rcx, r15
0x14001b9da  call    ?RootCause_GetState@@YA?AW4_STATE@RootCauseExtension@@PEAVIRootCause@@@Z; RootCause_GetState(IRootCause *)
0x14001b9df  sub     eax, 1
0x14001b9e2  jz      short loc_14001BA21
0x14001b9e4  sub     eax, 1
0x14001b9e7  jz      short loc_14001BA21
0x14001b9e9  sub     eax, 1
0x14001b9ec  jz      short loc_14001BA13
0x14001b9ee  sub     eax, 1
0x14001b9f1  jz      short loc_14001BA0C
0x14001b9f3  cmp     eax, 1
0x14001b9f6  jz      short loc_14001B9FE
0x14001b9f8  xor     ecx, ecx
0x14001b9fa  xor     edi, edi
0x14001b9fc  jmp     short loc_14001BA2D
0x14001b9fe  mov     ecx, 75h ; 'u'
0x14001ba03  lea     rdi, aFailicon; "failicon"
0x14001ba0a  jmp     short loc_14001BA2D
0x14001ba0c  mov     ecx, 74h ; 't'
0x14001ba11  jmp     short loc_14001BA18
0x14001ba13  mov     ecx, 77h ; 'w'
0x14001ba18  lea     rdi, aCheckicon; "checkicon"
0x14001ba1f  jmp     short loc_14001BA2D
0x14001ba21  lea     rdi, aWarningicon; "warningicon"
0x14001ba28  mov     ecx, 76h ; 'v'; uID
0x14001ba2d  mov     r8d, 400h; cchBufferMax
0x14001ba33  mov     rdx, rsi; lpBuffer
0x14001ba36  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14001ba3b  mov     ebx, eax
0x14001ba3d  test    eax, eax
0x14001ba3f  jns     short loc_14001BA4C
0x14001ba41  mov     r9d, 263h
0x14001ba47  jmp     loc_14001BB5D
0x14001ba4c  mov     rdx, rsi
0x14001ba4f  mov     rcx, r14
0x14001ba52  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x14001ba59  nop     dword ptr [rax+rax+00h]
0x14001ba5e  mov     ebx, eax
0x14001ba60  test    eax, eax
0x14001ba62  jns     short loc_14001BA6F
0x14001ba64  mov     r9d, 266h
0x14001ba6a  jmp     loc_14001BB5D
0x14001ba6f  mov     rax, [r15]
0x14001ba72  lea     rdx, [rsp+78h+bstrString]
0x14001ba77  mov     rcx, r15
0x14001ba7a  mov     rax, [rax+38h]
0x14001ba7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ba83  mov     ebx, eax
0x14001ba85  test    eax, eax
0x14001ba87  jns     short loc_14001BA94
0x14001ba89  mov     r9d, 269h
0x14001ba8f  jmp     loc_14001BB5D
0x14001ba94  mov     r8, [rsp+78h+bstrString]; unsigned __int16 *
0x14001ba99  mov     r9, rsi; unsigned __int16 *
0x14001ba9c  mov     rdx, r14; struct DirectUI::Element *
0x14001ba9f  mov     [rsp+78h+var_58], 0; unsigned __int16 *
0x14001baa8  call    ?SetAccValues@WizardPage@@IEAAJPEAVElement@DirectUI@@PEBG11@Z; WizardPage::SetAccValues(DirectUI::Element *,ushort const *,ushort const *,ushort const *)
0x14001baad  mov     ebx, eax
0x14001baaf  test    eax, eax
0x14001bab1  jns     short loc_14001BABE
0x14001bab3  mov     r9d, 26Ch
0x14001bab9  jmp     loc_14001BB5D
0x14001babe  lea     rax, [rsp+78h+var_40]
0x14001bac3  xor     r9d, r9d
0x14001bac6  mov     [rsp+78h+var_50], rax
0x14001bacb  xor     r8d, r8d
0x14001bace  mov     rdx, rdi
0x14001bad1  mov     [rsp+78h+var_58], 0
0x14001bada  mov     rcx, r12
0x14001badd  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14001bae4  nop     dword ptr [rax+rax+00h]
0x14001bae9  mov     ebx, eax
0x14001baeb  test    eax, eax
0x14001baed  jns     short loc_14001BAF7
0x14001baef  mov     r9d, 272h
0x14001baf5  jmp     short loc_14001BB5D
0x14001baf7  mov     r8, [rsp+78h+bstrString]; unsigned __int16 *
0x14001bafc  mov     r9, rsi; unsigned __int16 *
0x14001baff  mov     rdx, [rsp+78h+var_40]; struct DirectUI::Element *
0x14001bb04  mov     [rsp+78h+var_58], 0; unsigned __int16 *
0x14001bb0d  call    ?SetAccValues@WizardPage@@IEAAJPEAVElement@DirectUI@@PEBG11@Z; WizardPage::SetAccValues(DirectUI::Element *,ushort const *,ushort const *,ushort const *)
0x14001bb12  mov     ebx, eax
0x14001bb14  test    eax, eax
0x14001bb16  jns     short loc_14001BB20
0x14001bb18  mov     r9d, 278h
0x14001bb1e  jmp     short loc_14001BB5D
0x14001bb20  mov     rcx, rbp
0x14001bb23  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x14001bb2a  nop     dword ptr [rax+rax+00h]
0x14001bb2f  mov     ebx, eax
0x14001bb31  test    eax, eax
0x14001bb33  jns     short loc_14001BB3D
0x14001bb35  mov     r9d, 27Bh
0x14001bb3b  jmp     short loc_14001BB5D
0x14001bb3d  mov     rdx, [rsp+78h+var_40]
0x14001bb42  mov     rcx, rbp
0x14001bb45  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001bb4c  nop     dword ptr [rax+rax+00h]
0x14001bb51  mov     ebx, eax
0x14001bb53  test    eax, eax
0x14001bb55  jns     short loc_14001BB79
0x14001bb57  mov     r9d, 27Eh
0x14001bb5d  mov     dword ptr [rsp+78h+var_58], eax
0x14001bb61  lea     r8, aFinallinkspage_0; "FinalLinksPage::SetupRootCauseResult"
0x14001bb68  mov     ecx, 1; Level
0x14001bb6d  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001bb74  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001bb79  mov     rcx, [rsp+78h+bstrString]; bstrString
0x14001bb7e  test    rcx, rcx
0x14001bb81  jz      short loc_14001BB98
0x14001bb83  call    cs:__imp_SysFreeString
0x14001bb8a  nop     dword ptr [rax+rax+00h]
0x14001bb8f  mov     [rsp+78h+bstrString], 0
0x14001bb98  test    rsi, rsi
0x14001bb9b  jz      short loc_14001BBBD
0x14001bb9d  call    cs:__imp_GetProcessHeap
0x14001bba4  nop     dword ptr [rax+rax+00h]
0x14001bba9  mov     r8, rsi; lpMem
0x14001bbac  xor     edx, edx; dwFlags
0x14001bbae  mov     rcx, rax; hHeap
0x14001bbb1  call    cs:__imp_HeapFree
0x14001bbb8  nop     dword ptr [rax+rax+00h]
0x14001bbbd  mov     eax, ebx
0x14001bbbf  add     rsp, 40h
0x14001bbc3  pop     r15
0x14001bbc5  pop     r14
0x14001bbc7  pop     r12
0x14001bbc9  pop     rdi
0x14001bbca  pop     rsi
0x14001bbcb  pop     rbp
0x14001bbcc  pop     rbx
0x14001bbcd  retn
```
