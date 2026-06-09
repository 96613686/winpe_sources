# CreateNavPaneLinks(IUnknown * *)

- ea: `0x1800298d4`
- end: `0x180029b9b`
- name: `?CreateNavPaneLinks@@YAJPEAPEAUIUnknown@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800166e0`

## callees

- `0x180006598`
- `0x18001c0d0`
- `0x1800298d4`
- `0x18002f714`
- `0x18002f7cc`
- `0x18002f864`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x180029aa1`
- `SHLWAPI!PathFileExistsW` at `0x180029aa1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002995c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002995c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029a89`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029a89`

## string_xrefs

- `0x180029a02`: `https://go.microsoft.com/fwlink/?LinkId=142135`
- `0x180029a34`: `%windir%\system32\cttune.exe`
- `0x180029aff`: `input.dll`
- `0x180029b16`: `%windir%\system32\control.exe`
- `0x180029a7f`: `%windir%\system32\charmap.exe`
- `0x180029a0b`: `/open`

## pseudocode

```c
__int64 __fastcall CreateNavPaneLinks(struct IUnknown **a1, unsigned __int64 a2)
{
  struct IUnknown *v3; // rax
  struct IUnknown *v4; // rdi
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  LPVOID ppv; // [rsp+40h] [rbp-458h] BYREF
  unsigned __int16 v14[264]; // [rsp+50h] [rbp-448h] BYREF
  WCHAR Dst[264]; // [rsp+260h] [rbp-238h] BYREF

  *a1 = 0;
  v3 = (struct IUnknown *)DirectUI::HAllocAndZero((DirectUI *)0x18, a2);
  v4 = v3;
  if ( v3 )
  {
    v3[1].lpVtbl = 0;
    LODWORD(v3[2].lpVtbl) = 1;
    v3->lpVtbl = (struct IUnknownVtbl *)&CControlPanelNavLinks::`vftable';
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv);
    if ( v5 < 0 )
      goto LABEL_17;
    memset_0(v14, 0, 0x208u);
    v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, unsigned __int16 *, __int64))(*(_QWORD *)ppv + 32LL))(
           ppv,
           L"Microsoft.Fonts",
           v14,
           260);
    if ( v5 >= 0 )
    {
      v5 = StringCchCatW(v14, 0x104u, L"\\::{93412589-74D4-4E4E-AD0E-E0CB621440FD}");
      if ( v5 >= 0 )
        v5 = CControlPanelNavLinks::AddLinkShellEx(v4, 0, v6, 8018, v14, 0);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v5 < 0 )
      goto LABEL_17;
    v5 = CControlPanelNavLinks::AddLinkShellEx(
           v4,
           0,
           v7,
           8030,
           L"https://go.microsoft.com/fwlink/?LinkId=142135",
           L"/open");
    if ( v5 < 0 )
      goto LABEL_17;
    v5 = CControlPanelNavLinks::AddLinkShellEx(v4, 0, v8, 8020, L"%windir%\\system32\\cttune.exe", L"/open");
    if ( v5 < 0 )
      goto LABEL_17;
    memset_0(Dst, 0, 0x208u);
    v5 = ExpandEnvironmentStringsW(L"%windir%\\system32\\charmap.exe", Dst, 0x104u);
    if ( v5 < 0 )
      goto LABEL_17;
    if ( PathFileExistsW(Dst) )
    {
      v5 = CControlPanelNavLinks::AddLinkShellEx(v4, 0, v9, 8002, L"%windir%\\system32\\charmap.exe", L"/open");
      if ( v5 < 0 )
        goto LABEL_17;
    }
    v5 = CControlPanelNavLinks::AddLinkControlPanel(v4, 0, v9, 8003, L"Microsoft.Display");
    if ( v5 < 0
      || (v5 = CControlPanelNavLinks::AddLinkNotify(v4), v5 < 0)
      || (v5 = CControlPanelNavLinks::AddLinkShellEx(v4, 1, v10, 8004, L"%windir%\\system32\\control.exe", L"input.dll"),
          v5 < 0)
      || (v5 = CControlPanelNavLinks::AddLinkControlPanel(v4, 1, v11, 8005, L"Microsoft.Personalization"), v5 < 0) )
    {
LABEL_17:
      ((void (__fastcall *)(struct IUnknown *))v4->lpVtbl->Release)(v4);
    }
    else
    {
      *a1 = v4;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800298d4  mov     [rsp+arg_8], rbx
0x1800298d9  mov     [rsp+arg_10], rsi
0x1800298de  push    rdi
0x1800298df  push    r12
0x1800298e1  push    r15
0x1800298e3  sub     rsp, 480h
0x1800298ea  mov     rax, cs:__security_cookie
0x1800298f1  xor     rax, rsp
0x1800298f4  mov     [rsp+498h+var_28], rax
0x1800298fc  mov     rsi, rcx
0x1800298ff  mov     qword ptr [rcx], 0
0x180029906  mov     ecx, 18h; this
0x18002990b  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180029910  mov     rdi, rax
0x180029913  test    rax, rax
0x180029916  jz      loc_180029B6B
0x18002991c  xor     edx, edx; pUnkOuter
0x18002991e  mov     qword ptr [rdi+8], 0
0x180029926  lea     rax, ??_7CControlPanelNavLinks@@6B@; const CControlPanelNavLinks::`vftable'
0x18002992d  mov     dword ptr [rdi+10h], 1
0x180029934  mov     [rdi], rax
0x180029937  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18002993e  lea     rax, [rsp+498h+var_458]
0x180029943  mov     [rsp+498h+var_458], 0
0x18002994c  lea     r8d, [rdx+1]; dwClsContext
0x180029950  mov     [rsp+498h+ppv], rax; ppv
0x180029955  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18002995c  call    cs:__imp_CoCreateInstance
0x180029962  mov     ebx, eax
0x180029964  test    eax, eax
0x180029966  js      loc_180029B5A
0x18002996c  xor     edx, edx; Val
0x18002996e  lea     rcx, [rsp+498h+var_448]; void *
0x180029973  mov     r8d, 208h; Size
0x180029979  call    memset_0
0x18002997e  mov     rcx, [rsp+498h+var_458]
0x180029983  lea     r8, [rsp+498h+var_448]
0x180029988  mov     r12d, 104h
0x18002998e  lea     rdx, c_szMicrosoftFonts; "Microsoft.Fonts"
0x180029995  mov     r9d, r12d
0x180029998  mov     rax, [rcx]
0x18002999b  mov     rax, [rax+20h]
0x18002999f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299a4  mov     ebx, eax
0x1800299a6  test    eax, eax
0x1800299a8  js      short loc_1800299E9
0x1800299aa  lea     r8, a9341258974d44e; "\\::{93412589-74D4-4E4E-AD0E-E0CB621440"...
0x1800299b1  mov     edx, r12d; unsigned __int64
0x1800299b4  lea     rcx, [rsp+498h+var_448]; unsigned __int16 *
0x1800299b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800299be  mov     ebx, eax
0x1800299c0  test    eax, eax
0x1800299c2  js      short loc_1800299E9
0x1800299c4  lea     rax, [rsp+498h+var_448]
0x1800299c9  mov     [rsp+498h+var_470], 0
0x1800299d2  xor     edx, edx
0x1800299d4  mov     [rsp+498h+ppv], rax
0x1800299d9  mov     r9d, 1F52h
0x1800299df  mov     rcx, rdi
0x1800299e2  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x1800299e7  mov     ebx, eax
0x1800299e9  mov     rcx, [rsp+498h+var_458]
0x1800299ee  mov     rax, [rcx]
0x1800299f1  mov     rax, [rax+10h]
0x1800299f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299fa  test    ebx, ebx
0x1800299fc  js      loc_180029B5A
0x180029a02  lea     rax, c_szGetMoreFontsURL; "https://go.microsoft.com/fwlink/?LinkId"...
0x180029a09  xor     edx, edx
0x180029a0b  lea     r15, c_szActionOpen; "/open"
0x180029a12  mov     r9d, 1F5Eh
0x180029a18  mov     [rsp+498h+var_470], r15
0x180029a1d  mov     rcx, rdi
0x180029a20  mov     [rsp+498h+ppv], rax
0x180029a25  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180029a2a  mov     ebx, eax
0x180029a2c  test    eax, eax
0x180029a2e  js      loc_180029B5A
0x180029a34  lea     rax, c_szClearTypeTuner; "%windir%\\system32\\cttune.exe"
0x180029a3b  mov     [rsp+498h+var_470], r15
0x180029a40  xor     edx, edx
0x180029a42  mov     [rsp+498h+ppv], rax
0x180029a47  mov     r9d, 1F54h
0x180029a4d  mov     rcx, rdi
0x180029a50  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180029a55  mov     ebx, eax
0x180029a57  test    eax, eax
0x180029a59  js      loc_180029B5A
0x180029a5f  xor     edx, edx; Val
0x180029a61  lea     rcx, [rsp+498h+Dst]; void *
0x180029a69  mov     r8d, 208h; Size
0x180029a6f  call    memset_0
0x180029a74  mov     r8d, r12d; nSize
0x180029a77  lea     rdx, [rsp+498h+Dst]; lpDst
0x180029a7f  lea     r12, c_szCharmapPath; "%windir%\\system32\\charmap.exe"
0x180029a86  mov     rcx, r12; lpSrc
0x180029a89  call    cs:__imp_ExpandEnvironmentStringsW
0x180029a8f  mov     ebx, eax
0x180029a91  test    eax, eax
0x180029a93  js      loc_180029B5A
0x180029a99  lea     rcx, [rsp+498h+Dst]; pszPath
0x180029aa1  call    cs:__imp_PathFileExistsW
0x180029aa7  test    eax, eax
0x180029aa9  jz      short loc_180029ACF
0x180029aab  mov     [rsp+498h+var_470], r15
0x180029ab0  xor     edx, edx
0x180029ab2  mov     r9d, 1F42h
0x180029ab8  mov     [rsp+498h+ppv], r12
0x180029abd  mov     rcx, rdi
0x180029ac0  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180029ac5  mov     ebx, eax
0x180029ac7  test    eax, eax
0x180029ac9  js      loc_180029B5A
0x180029acf  lea     rax, c_szMicrosoftDisplay; "Microsoft.Display"
0x180029ad6  xor     edx, edx
0x180029ad8  mov     r9d, 1F43h
0x180029ade  mov     [rsp+498h+ppv], rax
0x180029ae3  mov     rcx, rdi
0x180029ae6  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180029aeb  mov     ebx, eax
0x180029aed  test    eax, eax
0x180029aef  js      short loc_180029B5A
0x180029af1  mov     rcx, rdi
0x180029af4  call    ?AddLinkNotify@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IHPEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkNotify(CPNAV_LIST,HINSTANCE__ *,uint,int,CControlPanelNavLink * *)
0x180029af9  mov     ebx, eax
0x180029afb  test    eax, eax
0x180029afd  js      short loc_180029B5A
0x180029aff  lea     rax, c_szInputDll; "input.dll"
0x180029b06  mov     edx, 1
0x180029b0b  mov     [rsp+498h+var_470], rax
0x180029b10  mov     r9d, 1F44h
0x180029b16  lea     rax, c_szControlPath; "%windir%\\system32\\control.exe"
0x180029b1d  mov     rcx, rdi
0x180029b20  mov     [rsp+498h+ppv], rax
0x180029b25  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180029b2a  mov     ebx, eax
0x180029b2c  test    eax, eax
0x180029b2e  js      short loc_180029B5A
0x180029b30  lea     rax, c_szMicrosoftPersonlization; "Microsoft.Personalization"
0x180029b37  mov     edx, 1
0x180029b3c  mov     r9d, 1F45h
0x180029b42  mov     [rsp+498h+ppv], rax
0x180029b47  mov     rcx, rdi
0x180029b4a  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180029b4f  mov     ebx, eax
0x180029b51  test    eax, eax
0x180029b53  js      short loc_180029B5A
0x180029b55  mov     [rsi], rdi
0x180029b58  jmp     short loc_180029B70
0x180029b5a  mov     rax, [rdi]
0x180029b5d  mov     rcx, rdi
0x180029b60  mov     rax, [rax+10h]
0x180029b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b69  jmp     short loc_180029B70
0x180029b6b  mov     ebx, 8007000Eh
0x180029b70  mov     eax, ebx
0x180029b72  mov     rcx, [rsp+498h+var_28]
0x180029b7a  xor     rcx, rsp; StackCookie
0x180029b7d  call    __security_check_cookie
0x180029b82  lea     r11, [rsp+498h+var_18]
0x180029b8a  mov     rbx, [r11+28h]
0x180029b8e  mov     rsi, [r11+30h]
0x180029b92  mov     rsp, r11
0x180029b95  pop     r15
0x180029b97  pop     r12
0x180029b99  pop     rdi
0x180029b9a  retn
```
