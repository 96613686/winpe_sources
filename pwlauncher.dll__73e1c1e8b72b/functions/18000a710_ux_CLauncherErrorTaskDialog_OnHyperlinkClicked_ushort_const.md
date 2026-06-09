# ux::CLauncherErrorTaskDialog::OnHyperlinkClicked(ushort const *)

- ea: `0x18000a710`
- end: `0x18000a856`
- name: `?OnHyperlinkClicked@CLauncherErrorTaskDialog@ux@@QEAAXPEBG@Z`
- size: `326`
- prototype: `void __fastcall(OLECHAR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b050`

## callees

- `0x18000374c`
- `0x180008b30`
- `0x1800092dc`
- `0x18000a710`
- `0x18000ef8c`
- `0x18000fde2`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000a750`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a816`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a750`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a816`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a769`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a825`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a769`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000a825`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a778`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a830`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a778`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a830`

## string_xrefs

- `0x18000a7c1`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`

## pseudocode

```c
void __fastcall ux::CLauncherErrorTaskDialog::OnHyperlinkClicked(OLECHAR *this, const unsigned __int16 *a2)
{
  OLECHAR *v2; // rbx
  UINT v3; // eax
  BSTR v4; // rax
  wchar_t *v5; // rdx
  UINT v6; // eax
  BSTR v7; // [rsp+40h] [rbp+8h] BYREF
  BSTR v8; // [rsp+50h] [rbp+18h]
  wchar_t *String1; // [rsp+58h] [rbp+20h] BYREF

  v7 = this;
  v2 = 0;
  v8 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &String1,
    (unsigned __int64)a2);
  if ( !wcscmp_0(String1, L"FirmwareHelpTopic") )
  {
    if ( ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC )
    {
      SysFreeString(0);
      if ( ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC )
      {
        v3 = SysStringByteLen(ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC);
        v4 = SysAllocStringByteLen((LPCSTR)ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC, v3);
        v2 = v4;
        v8 = v4;
        if ( ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC && !v4 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v8 = 0;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
      (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
      238);
  }
  if ( v2 )
  {
    v6 = SysStringByteLen(v2);
    v7 = SysAllocStringByteLen((LPCSTR)v2, v6);
    if ( !v7 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v7 = 0;
  }
  utils::CHelpPane::Open(&v7);
  v5 = String1 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)String1 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  SysFreeString(v2);
}

```

## disassembly

```asm
0x18000a710  mov     [rsp+arg_0], rcx
0x18000a715  push    rbx
0x18000a716  sub     rsp, 30h
0x18000a71a  xor     ebx, ebx
0x18000a71c  mov     [rsp+38h+arg_10], rbx
0x18000a721  lea     rcx, [rsp+38h+String1]
0x18000a726  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000a72b  nop
0x18000a72c  lea     rdx, aFirmwarehelpto; "FirmwareHelpTopic"
0x18000a733  mov     rcx, [rsp+38h+String1]; String1
0x18000a738  call    wcscmp_0
0x18000a73d  test    eax, eax
0x18000a73f  jnz     short loc_18000A79B
0x18000a741  cmp     cs:?FIRMWARE_HELP_TOPIC@CLauncherErrorTaskDialog@ux@@0VCComBSTR@ATL@@B, rbx; ATL::CComBSTR const ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC
0x18000a748  jz      loc_18000A7D8
0x18000a74e  xor     ecx, ecx; bstrString
0x18000a750  call    cs:__imp_SysFreeString
0x18000a756  mov     rcx, cs:?FIRMWARE_HELP_TOPIC@CLauncherErrorTaskDialog@ux@@0VCComBSTR@ATL@@B; bstr
0x18000a75d  test    rcx, rcx
0x18000a760  jnz     short loc_18000A769
0x18000a762  mov     [rsp+38h+arg_10], rbx
0x18000a767  jmp     short loc_18000A7D8
0x18000a769  call    cs:__imp_SysStringByteLen
0x18000a76f  mov     edx, eax; len
0x18000a771  mov     rcx, cs:?FIRMWARE_HELP_TOPIC@CLauncherErrorTaskDialog@ux@@0VCComBSTR@ATL@@B; psz
0x18000a778  call    cs:__imp_SysAllocStringByteLen
0x18000a77e  mov     rbx, rax
0x18000a781  mov     [rsp+38h+arg_10], rax
0x18000a786  cmp     cs:?FIRMWARE_HELP_TOPIC@CLauncherErrorTaskDialog@ux@@0VCComBSTR@ATL@@B, 0; ATL::CComBSTR const ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC
0x18000a78e  jz      short loc_18000A7D8
0x18000a790  test    rax, rax
0x18000a793  jz      loc_18000A84B
0x18000a799  jmp     short loc_18000A7D8
0x18000a79b  lea     rax, WPP_GLOBAL_Control
0x18000a7a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7a9  cmp     rcx, rax
0x18000a7ac  jz      short loc_18000A7D8
0x18000a7ae  test    byte ptr [rcx+1Ch], 1
0x18000a7b2  jz      short loc_18000A7D8
0x18000a7b4  mov     edx, 27h ; '''
0x18000a7b9  mov     [rsp+38h+var_18], 1EEh
0x18000a7c1  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a7c8  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a7cf  mov     rcx, [rcx+10h]
0x18000a7d3  call    WPP_SF_sd
0x18000a7d8  test    rbx, rbx
0x18000a7db  jnz     short loc_18000A822
0x18000a7dd  mov     [rsp+38h+arg_0], rbx
0x18000a7e2  lea     rcx, [rsp+38h+arg_0]
0x18000a7e7  call    ?Open@CHelpPane@utils@@SAXVCComBSTR@ATL@@@Z; utils::CHelpPane::Open(ATL::CComBSTR)
0x18000a7ec  nop
0x18000a7ed  mov     rdx, [rsp+38h+String1]
0x18000a7f2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000a7f6  or      eax, 0FFFFFFFFh
0x18000a7f9  lock xadd [rdx+10h], eax
0x18000a7fe  sub     eax, 1
0x18000a801  jg      short loc_18000A813
0x18000a803  mov     rcx, [rdx]
0x18000a806  mov     rax, [rcx]
0x18000a809  mov     rax, [rax+8]
0x18000a80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a812  nop
0x18000a813  mov     rcx, rbx; bstrString
0x18000a816  call    cs:__imp_SysFreeString
0x18000a81c  add     rsp, 30h
0x18000a820  pop     rbx
0x18000a821  retn
0x18000a822  mov     rcx, rbx; bstr
0x18000a825  call    cs:__imp_SysStringByteLen
0x18000a82b  mov     edx, eax; len
0x18000a82d  mov     rcx, rbx; psz
0x18000a830  call    cs:__imp_SysAllocStringByteLen
0x18000a836  mov     [rsp+38h+arg_0], rax
0x18000a83b  test    rax, rax
0x18000a83e  jnz     short loc_18000A7E2
0x18000a840  mov     ecx, 8007000Eh; int
0x18000a845  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000a84b  mov     ecx, 8007000Eh; int
0x18000a850  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
