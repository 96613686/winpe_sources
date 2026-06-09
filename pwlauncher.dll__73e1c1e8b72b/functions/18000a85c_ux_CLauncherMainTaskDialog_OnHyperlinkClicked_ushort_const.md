# ux::CLauncherMainTaskDialog::OnHyperlinkClicked(ushort const *)

- ea: `0x18000a85c`
- end: `0x18000aa03`
- name: `?OnHyperlinkClicked@CLauncherMainTaskDialog@ux@@QEAAXPEBG@Z`
- size: `423`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b0c0`

## callees

- `0x18000374c`
- `0x180008b30`
- `0x1800092dc`
- `0x18000a85c`
- `0x18000ef8c`
- `0x18000fde2`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000a8a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a916`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a9bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a8a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a916`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a9bf`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a8be`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a928`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a9d3`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a8be`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a928`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a9d3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a8cd`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a937`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a9de`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a8cd`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a937`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a9de`

## string_xrefs

- `0x18000a96d`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::OnHyperlinkClicked(
        ux::CLauncherMainTaskDialog *this,
        const unsigned __int16 *a2)
{
  OLECHAR *v2; // rbx
  UINT v3; // eax
  BSTR v4; // rax
  bool v5; // zf
  UINT v6; // eax
  wchar_t *v7; // rdx
  UINT v8; // eax
  BSTR v9; // [rsp+50h] [rbp+20h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp+28h] BYREF

  v2 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &String1,
    (unsigned __int64)a2);
  if ( !wcscmp_0(String1, L"PolicyHelpTopic") )
  {
    if ( !ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL )
      goto LABEL_16;
    SysFreeString(0);
    if ( !ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL )
      goto LABEL_4;
    v3 = SysStringByteLen(ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL);
    v4 = SysAllocStringByteLen((LPCSTR)ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL, v3);
    v5 = ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL == 0;
LABEL_6:
    v2 = v4;
    if ( !v5 && !v4 )
      ATL::AtlThrowImpl(-2147024882);
    goto LABEL_16;
  }
  if ( !wcscmp_0(String1, L"RightOptionHelpTopic") )
  {
    if ( !ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL )
      goto LABEL_16;
    SysFreeString(0);
    if ( !ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL )
    {
LABEL_4:
      v2 = 0;
      goto LABEL_16;
    }
    v6 = SysStringByteLen(ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL);
    v4 = SysAllocStringByteLen((LPCSTR)ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL, v6);
    v5 = ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL == 0;
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
      (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
      138);
LABEL_16:
  if ( v2 )
  {
    v8 = SysStringByteLen(v2);
    v9 = SysAllocStringByteLen((LPCSTR)v2, v8);
    if ( !v9 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v9 = 0;
  }
  utils::CHelpPane::Open(&v9);
  v7 = String1 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)String1 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  SysFreeString(v2);
}

```

## disassembly

```asm
0x18000a85c  mov     [rsp-8+arg_8], rbx
0x18000a861  mov     [rsp-8+arg_0], rcx
0x18000a866  push    rbp
0x18000a867  mov     rbp, rsp
0x18000a86a  sub     rsp, 30h
0x18000a86e  xor     ebx, ebx
0x18000a870  mov     [rbp+arg_0], rbx
0x18000a874  lea     rcx, [rbp+String1]
0x18000a878  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000a87d  nop
0x18000a87e  lea     rdx, aPolicyhelptopi; "PolicyHelpTopic"
0x18000a885  mov     rcx, [rbp+String1]; String1
0x18000a889  call    wcscmp_0
0x18000a88e  test    eax, eax
0x18000a890  jnz     short loc_18000A8F6
0x18000a892  cmp     cs:?GROUP_POLICY_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B, rbx; ATL::CComBSTR const ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL
0x18000a899  jz      loc_18000A984
0x18000a89f  xor     ecx, ecx; bstrString
0x18000a8a1  call    cs:__imp_SysFreeString
0x18000a8a7  mov     rcx, cs:?GROUP_POLICY_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B; bstr
0x18000a8ae  test    rcx, rcx
0x18000a8b1  jnz     short loc_18000A8BE
0x18000a8b3  xor     ebx, ebx
0x18000a8b5  mov     [rbp+arg_0], rbx
0x18000a8b9  jmp     loc_18000A984
0x18000a8be  call    cs:__imp_SysStringByteLen
0x18000a8c4  mov     edx, eax; len
0x18000a8c6  mov     rcx, cs:?GROUP_POLICY_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B; psz
0x18000a8cd  call    cs:__imp_SysAllocStringByteLen
0x18000a8d3  cmp     cs:?GROUP_POLICY_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B, 0; ATL::CComBSTR const ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL
0x18000a8db  mov     [rbp+arg_0], rax
0x18000a8df  mov     rbx, rax
0x18000a8e2  jz      loc_18000A984
0x18000a8e8  test    rax, rax
0x18000a8eb  jz      loc_18000A9F8
0x18000a8f1  jmp     loc_18000A984
0x18000a8f6  lea     rdx, aRightoptionhel; "RightOptionHelpTopic"
0x18000a8fd  mov     rcx, [rbp+String1]; String1
0x18000a901  call    wcscmp_0
0x18000a906  test    eax, eax
0x18000a908  jnz     short loc_18000A947
0x18000a90a  cmp     cs:?LAUNCHER_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B, 0; ATL::CComBSTR const ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL
0x18000a912  jz      short loc_18000A984
0x18000a914  xor     ecx, ecx; bstrString
0x18000a916  call    cs:__imp_SysFreeString
0x18000a91c  mov     rcx, cs:?LAUNCHER_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B; bstr
0x18000a923  test    rcx, rcx
0x18000a926  jz      short loc_18000A8B3
0x18000a928  call    cs:__imp_SysStringByteLen
0x18000a92e  mov     edx, eax; len
0x18000a930  mov     rcx, cs:?LAUNCHER_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B; psz
0x18000a937  call    cs:__imp_SysAllocStringByteLen
0x18000a93d  cmp     cs:?LAUNCHER_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B, 0; ATL::CComBSTR const ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL
0x18000a945  jmp     short loc_18000A8DB
0x18000a947  lea     rax, WPP_GLOBAL_Control
0x18000a94e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a955  cmp     rcx, rax
0x18000a958  jz      short loc_18000A984
0x18000a95a  test    byte ptr [rcx+1Ch], 1
0x18000a95e  jz      short loc_18000A984
0x18000a960  mov     edx, 1Fh
0x18000a965  mov     [rsp+30h+var_10], 18Ah
0x18000a96d  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a974  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a97b  mov     rcx, [rcx+10h]
0x18000a97f  call    WPP_SF_sd
0x18000a984  test    rbx, rbx
0x18000a987  jnz     short loc_18000A9D0
0x18000a989  mov     [rbp+arg_10], rbx
0x18000a98d  lea     rcx, [rbp+arg_10]
0x18000a991  call    ?Open@CHelpPane@utils@@SAXVCComBSTR@ATL@@@Z; utils::CHelpPane::Open(ATL::CComBSTR)
0x18000a996  nop
0x18000a997  mov     rdx, [rbp+String1]
0x18000a99b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000a99f  or      eax, 0FFFFFFFFh
0x18000a9a2  lock xadd [rdx+10h], eax
0x18000a9a7  sub     eax, 1
0x18000a9aa  jg      short loc_18000A9BC
0x18000a9ac  mov     rcx, [rdx]
0x18000a9af  mov     rax, [rcx]
0x18000a9b2  mov     rax, [rax+8]
0x18000a9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9bb  nop
0x18000a9bc  mov     rcx, rbx; bstrString
0x18000a9bf  call    cs:__imp_SysFreeString
0x18000a9c5  mov     rbx, [rsp+30h+arg_8]
0x18000a9ca  add     rsp, 30h
0x18000a9ce  pop     rbp
0x18000a9cf  retn
0x18000a9d0  mov     rcx, rbx; bstr
0x18000a9d3  call    cs:__imp_SysStringByteLen
0x18000a9d9  mov     edx, eax; len
0x18000a9db  mov     rcx, rbx; psz
0x18000a9de  call    cs:__imp_SysAllocStringByteLen
0x18000a9e4  mov     [rbp+arg_10], rax
0x18000a9e8  test    rax, rax
0x18000a9eb  jnz     short loc_18000A98D
0x18000a9ed  mov     ecx, 8007000Eh; int
0x18000a9f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000a9f8  mov     ecx, 8007000Eh; int
0x18000a9fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
