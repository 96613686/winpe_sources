# SMBAccessDeniedMessageBox(HINSTANCE__ *,HWND__ *,ushort const *)

- ea: `0x180010460`
- end: `0x18001065b`
- name: `?SMBAccessDeniedMessageBox@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBG@Z`
- size: `507`
- prototype: `int(HINSTANCE, HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015590`

## callees

- `0x180010250`
- `0x180010460`
- `0x18001084c`
- `0x18001b7e4`
- `0x18001f652`
- `0x180021010`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x1800105f2`
- `KERNEL32!ReleaseActCtx` at `0x1800105f2`
- `KERNEL32!DeactivateActCtx` at `0x1800105d7`
- `KERNEL32!DeactivateActCtx` at `0x1800105d7`
- `KERNEL32!GetLastError` at `0x1800105e1`
- `KERNEL32!GetLastError` at `0x1800105e1`
- `KERNEL32!MulDiv` at `0x18001057b`
- `KERNEL32!MulDiv` at `0x18001057b`
- `USER32!GetDialogBaseUnits` at `0x180010567`
- `USER32!GetDialogBaseUnits` at `0x180010567`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x1800105c8`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x1800105c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SMBAccessDeniedMessageBox(HINSTANCE a1, HWND a2, const unsigned __int16 *a3)
{
  HINSTANCE v5; // rsi
  __int64 v7; // rax
  const WCHAR *v8; // rdi
  const WCHAR *v9; // rbx
  unsigned __int16 DialogBaseUnits; // ax
  HINSTANCE v11; // rdx
  HRESULT v12; // esi
  const WCHAR *v13; // [rsp+20h] [rbp-C8h] BYREF
  HANDLE hActCtx; // [rsp+28h] [rbp-C0h] BYREF
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-B8h]
  const ATL::CAtlException *v16; // [rsp+38h] [rbp-B0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-A8h] BYREF
  HINSTANCE pnButton; // [rsp+F0h] [rbp+8h] BYREF
  const WCHAR *v19; // [rsp+108h] [rbp+20h] BYREF

  pnButton = a1;
  v5 = g_hinstDll;
  memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
  pTaskConfig.cbSize = 160;
  if ( (int)ShowAccessDeniedRemediation(a2, a3) >= 0 )
    return 0;
  v19 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    v13 = (const WCHAR *)(v7 + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v19,
      40127,
      a3);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v13,
      40128,
      a3);
    pTaskConfig.pfCallback = SMBAccessDeniedDialogCallback;
    pTaskConfig.hInstance = v5;
    pTaskConfig.hwndParent = a2;
    pTaskConfig.pszWindowTitle = (PCWSTR)40081;
    pTaskConfig.dwFlags = 9;
    pTaskConfig.dwCommonButtons = 32;
    v8 = v19;
    pTaskConfig.pszMainInstruction = v19;
    v9 = v13;
    pTaskConfig.pszContent = v13;
    DialogBaseUnits = GetDialogBaseUnits();
    pTaskConfig.cxWidth = MulDiv(518, 4, DialogBaseUnits);
    LODWORD(pnButton) = 0;
    hActCtx = (HANDLE)-1LL;
    ulCookie = 0;
    v12 = CActivationContextV6::Activate((CActivationContextV6 *)&hActCtx, v11);
    if ( v12 >= 0 )
      v12 = TaskDialogIndirect(&pTaskConfig, (int *)&pnButton, 0, 0);
    if ( !DeactivateActCtx(0, ulCookie) )
      GetLastError();
    if ( hActCtx != (HANDLE)-1LL )
      ReleaseActCtx(hActCtx);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  }
  catch ( const ATL::CAtlException *v16 )
  {
    LODWORD(pnButton) = *(_DWORD *)v16;
    return (unsigned int)pnButton;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180010460  mov     [rsp+arg_8], rbx
0x180010465  mov     [rsp+arg_10], rsi
0x18001046a  mov     [rsp+pnButton], rcx
0x18001046f  push    rdi
0x180010470  sub     rsp, 0E0h
0x180010477  mov     rbx, r8
0x18001047a  mov     rdi, rdx
0x18001047d  mov     rsi, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstDll
0x180010484  xor     edx, edx; Val
0x180010486  mov     r8d, 9Ch; Size
0x18001048c  lea     rcx, [rsp+0E8h+pTaskConfig.hwndParent]; void *
0x180010491  call    memset_0
0x180010496  mov     [rsp+0E8h+pTaskConfig.cbSize], 0A0h
0x18001049e  mov     rdx, rbx; unsigned __int16 *
0x1800104a1  mov     rcx, rdi; HWND
0x1800104a4  call    ?ShowAccessDeniedRemediation@@YAJPEAUHWND__@@PEBG@Z; ShowAccessDeniedRemediation(HWND__ *,ushort const *)
0x1800104a9  test    eax, eax
0x1800104ab  js      short loc_1800104B4
0x1800104ad  xor     eax, eax
0x1800104af  jmp     loc_180010646
0x1800104b4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800104bb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800104c2  mov     rax, [rax+18h]
0x1800104c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104cb  add     rax, 18h
0x1800104cf  mov     [rsp+0E8h+arg_18], rax
0x1800104d7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800104de  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800104e5  mov     rax, [rax+18h]
0x1800104e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ee  add     rax, 18h
0x1800104f2  mov     [rsp+0E8h+var_C8], rax
0x1800104f7  mov     r8, rbx
0x1800104fa  mov     edx, 9CBFh
0x1800104ff  lea     rcx, [rsp+0E8h+arg_18]
0x180010507  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXIZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(uint,...)
0x18001050c  mov     r8, rbx
0x18001050f  mov     edx, 9CC0h
0x180010514  lea     rcx, [rsp+0E8h+var_C8]
0x180010519  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXIZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(uint,...)
0x18001051e  lea     rax, ?SMBAccessDeniedDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z; SMBAccessDeniedDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180010525  mov     [rsp+0E8h+pTaskConfig.pfCallback], rax
0x18001052d  mov     [rsp+0E8h+pTaskConfig.hInstance], rsi
0x180010532  mov     [rsp+0E8h+pTaskConfig.hwndParent], rdi
0x180010537  mov     [rsp+0E8h+pTaskConfig.pszWindowTitle], 9C91h
0x180010540  mov     [rsp+0E8h+pTaskConfig.dwFlags], 9
0x180010548  mov     [rsp+0E8h+pTaskConfig.dwCommonButtons], 20h ; ' '
0x180010550  mov     rdi, [rsp+0E8h+arg_18]
0x180010558  mov     [rsp+0E8h+pTaskConfig.pszMainInstruction], rdi
0x18001055d  mov     rbx, [rsp+0E8h+var_C8]
0x180010562  mov     [rsp+0E8h+pTaskConfig.pszContent], rbx
0x180010567  call    cs:__imp_GetDialogBaseUnits
0x18001056d  movzx   r8d, ax; nDenominator
0x180010571  mov     edx, 4; nNumerator
0x180010576  mov     ecx, 206h; nNumber
0x18001057b  call    cs:__imp_MulDiv
0x180010581  mov     [rsp+0E8h+pTaskConfig.cxWidth], eax
0x180010588  mov     dword ptr [rsp+0E8h+pnButton], 0
0x180010593  mov     [rsp+0E8h+hActCtx], 0FFFFFFFFFFFFFFFFh
0x18001059c  mov     [rsp+0E8h+ulCookie], 0
0x1800105a5  lea     rcx, [rsp+0E8h+hActCtx]; this
0x1800105aa  call    ?Activate@CActivationContextV6@@QEAAJPEAUHINSTANCE__@@@Z; CActivationContextV6::Activate(HINSTANCE__ *)
0x1800105af  mov     esi, eax
0x1800105b1  test    eax, eax
0x1800105b3  js      short loc_1800105D0
0x1800105b5  xor     r9d, r9d; pfVerificationFlagChecked
0x1800105b8  xor     r8d, r8d; pnRadioButton
0x1800105bb  lea     rdx, [rsp+0E8h+pnButton]; pnButton
0x1800105c3  lea     rcx, [rsp+0E8h+pTaskConfig]; pTaskConfig
0x1800105c8  call    cs:__imp_TaskDialogIndirect
0x1800105ce  mov     esi, eax
0x1800105d0  mov     rdx, [rsp+0E8h+ulCookie]; ulCookie
0x1800105d5  xor     ecx, ecx; dwFlags
0x1800105d7  call    cs:__imp_DeactivateActCtx
0x1800105dd  test    eax, eax
0x1800105df  jnz     short loc_1800105E7
0x1800105e1  call    cs:__imp_GetLastError
0x1800105e7  mov     rcx, [rsp+0E8h+hActCtx]; hActCtx
0x1800105ec  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800105f0  jz      short loc_1800105F9
0x1800105f2  call    cs:__imp_ReleaseActCtx
0x1800105f8  nop
0x1800105f9  lea     rdx, [rbx-18h]
0x1800105fd  or      eax, 0FFFFFFFFh
0x180010600  lock xadd [rdx+10h], eax
0x180010605  sub     eax, 1
0x180010608  jg      short loc_18001061A
0x18001060a  mov     rcx, [rdx]
0x18001060d  mov     rax, [rcx]
0x180010610  mov     rax, [rax+8]
0x180010614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010619  nop
0x18001061a  lea     rdx, [rdi-18h]
0x18001061e  or      eax, 0FFFFFFFFh
0x180010621  lock xadd [rdx+10h], eax
0x180010626  sub     eax, 1
0x180010629  jg      short loc_18001063B
0x18001062b  mov     rcx, [rdx]
0x18001062e  mov     rax, [rcx]
0x180010631  mov     rax, [rax+8]
0x180010635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063a  nop
0x18001063b  jmp     short loc_180010644
0x18001063d  mov     esi, dword ptr [rsp+0E8h+pnButton]
0x180010644  mov     eax, esi
0x180010646  lea     r11, [rsp+0E8h+var_8]
0x18001064e  mov     rbx, [r11+18h]
0x180010652  mov     rsi, [r11+20h]
0x180010656  mov     rsp, r11
0x180010659  pop     rdi
0x18001065a  retn
```
