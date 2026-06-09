# InstallSecurityPromptRunDllW(HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x180007630`
- end: `0x180007984`
- name: `?InstallSecurityPromptRunDllW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEAGH@Z`
- size: `852`
- prototype: `void __fastcall(HWND, HINSTANCE, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001254`
- `0x180001294`
- `0x180003110`
- `0x180005fd4`
- `0x180006700`
- `0x180007630`
- `0x18000a900`
- `0x18000ccde`
- `0x18000cd10`

## import_xrefs

- `msvcrt!_wtoi` at `0x180007729`
- `msvcrt!_wtoi` at `0x180007729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007836`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007812`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000786d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007812`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000786d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800077d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000782c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007883`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800077d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000782c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007883`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000791f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000791f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000790e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000790e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800076e1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800076e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000795b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000795b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007928`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007928`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x1800076f8`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x1800076f8`
- `USER32!SetProcessDPIAware` at `0x1800076db`
- `USER32!SetProcessDPIAware` at `0x1800076db`
- `SHELL32!SHGetStockIconInfo` at `0x1800078d2`
- `SHELL32!SHGetStockIconInfo` at `0x1800078d2`
- `ole32!CoInitialize` at `0x180007676`
- `ole32!CoInitialize` at `0x180007676`
- `ole32!OleUninitialize` at `0x180007955`
- `ole32!OleUninitialize` at `0x180007955`
- `ole32!OleInitialize` at `0x180007686`
- `ole32!OleInitialize` at `0x180007686`
- `DUI70!InitPreprocessor` at `0x18000766e`
- `DUI70!InitPreprocessor` at `0x18000766e`
- `DUI70!InitProcessPriv` at `0x1800076ab`
- `DUI70!InitProcessPriv` at `0x1800076ab`
- `DUI70!UnInitProcessPriv` at `0x18000794f`
- `DUI70!UnInitProcessPriv` at `0x18000794f`

## string_xrefs

- `0x1800077b1`: `pnpui.dll`
- `0x18000780b`: `pnpui.dll`
- `0x180007863`: `pnpui.dll`

## pseudocode

```c
void __fastcall InstallSecurityPromptRunDllW(HWND a1, HINSTANCE a2, unsigned __int16 *a3)
{
  __int64 v3; // r8
  const WCHAR *CommandLineW; // rax
  LPWSTR *v5; // rax
  LPWSTR *v6; // rbx
  const wchar_t *v7; // rcx
  unsigned int v8; // esi
  const WCHAR *v9; // r13
  const WCHAR *v10; // r12
  WCHAR *CertName; // rdi
  const unsigned __int16 *v12; // r14
  WCHAR *InfInfo; // rbx
  HMODULE ModuleHandleW; // rax
  int v15; // r15d
  HMODULE v16; // rax
  HMODULE v17; // rax
  HICON hIcon; // r8
  WCHAR *v19; // rdx
  const WCHAR *v20; // r8
  HANDLE v21; // rax
  void *v22; // rsi
  int pNumArgs; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  HICON v25; // [rsp+40h] [rbp-C0h] BYREF
  SHSTOCKICONINFO psii; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[256]; // [rsp+270h] [rbp+170h] BYREF

  pNumArgs = 0;
  v25 = 0;
  InitPreprocessor(a1, a2, a3);
  if ( CoInitialize(0) < 0 )
    goto LABEL_46;
  if ( OleInitialize(0) < 0 )
    goto LABEL_46;
  LOBYTE(v3) = 1;
  if ( (int)InitProcessPriv(14, &_ImageBase, v3) < 0 )
    goto LABEL_46;
  v24[0] = 8;
  v24[1] = 0x4000;
  if ( !(unsigned int)IsolationAwareInitCommonControlsEx(v24) )
    goto LABEL_46;
  SetProcessDPIAware();
  CommandLineW = GetCommandLineW();
  if ( !CommandLineW )
    goto LABEL_46;
  v5 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  v6 = v5;
  if ( !v5 )
    goto LABEL_46;
  if ( pNumArgs < 6 )
    goto LABEL_46;
  v7 = v5[2];
  if ( (*v7 & 0xFFDF) == 0 )
    goto LABEL_46;
  v8 = _wtoi(v7);
  if ( pNumArgs < 4 )
    goto LABEL_46;
  v9 = v6[3];
  if ( (*v9 & 0xFFDF) == 0 )
    goto LABEL_46;
  if ( pNumArgs < 5 )
    goto LABEL_46;
  v10 = v6[4];
  if ( (*v10 & 0xFFDF) == 0 || pNumArgs < 6 || (*v6[5] & 0xFFDF) == 0 )
    goto LABEL_46;
  CertName = 0;
  v12 = 0;
  if ( pNumArgs >= 7 && (*v6[6] & 0xFFDF) != 0 )
    v12 = v6[6];
  InfInfo = GetInfInfo(v6[5], &v25);
  if ( !InfInfo )
  {
    InfInfo = (WCHAR *)operator new(0x200u);
    ModuleHandleW = GetModuleHandleW(L"pnpui.dll");
    if ( !LoadStringW(ModuleHandleW, 0xCDu, InfInfo, 256) )
      goto LABEL_42;
  }
  v15 = 1000;
  if ( v8 == 10 )
    goto LABEL_25;
  if ( v8 == 20 )
  {
LABEL_29:
    CertName = GetCertName(v12);
    if ( CertName )
      goto LABEL_31;
    goto LABEL_30;
  }
  if ( v8 != 30 )
  {
    if ( v8 != 40 )
    {
      if ( v8 != 50 )
        goto LABEL_42;
LABEL_25:
      if ( !InfInfo )
        goto LABEL_46;
      v16 = GetModuleHandleW(L"pnpui.dll");
      if ( !LoadStringW(v16, 0xCBu, Buffer, 256) )
      {
LABEL_27:
        if ( GetLastError() )
          goto LABEL_42;
        goto LABEL_36;
      }
      memset_0(&psii.cbSize + 1, 0, 0x21Cu);
      psii.cbSize = 544;
      SHGetStockIconInfo(SIID_APPLICATION, 0x100u, &psii);
      hIcon = psii.hIcon;
      v19 = Buffer;
LABEL_35:
      v15 = InstallSecurityPrompt(InfInfo, v19, hIcon, v8);
LABEL_36:
      if ( v15 == 2 )
      {
        v20 = v10;
      }
      else
      {
        if ( v15 != 1 )
          goto LABEL_42;
        v20 = v9;
      }
      v21 = OpenEventW(2u, 0, v20);
      v22 = v21;
      if ( v21 )
      {
        SetEvent(v21);
        CloseHandle(v22);
      }
LABEL_42:
      if ( !InfInfo )
        goto LABEL_44;
      goto LABEL_43;
    }
    goto LABEL_29;
  }
LABEL_30:
  CertName = (WCHAR *)operator new(0x200u);
  v17 = GetModuleHandleW(L"pnpui.dll");
  if ( !LoadStringW(v17, 0xCBu, CertName, 256) )
    goto LABEL_27;
LABEL_31:
  if ( !InfInfo )
    goto LABEL_44;
  if ( CertName )
  {
    hIcon = v25;
    v19 = CertName;
    goto LABEL_35;
  }
LABEL_43:
  operator delete(InfInfo);
LABEL_44:
  if ( CertName )
    operator delete(CertName);
LABEL_46:
  UnInitProcessPriv(&_ImageBase);
  OleUninitialize();
  CoUninitialize();
}

```

## disassembly

```asm
0x180007630  push    rbp
0x180007632  push    rbx
0x180007633  push    rsi
0x180007634  push    rdi
0x180007635  push    r12
0x180007637  push    r13
0x180007639  push    r14
0x18000763b  push    r15
0x18000763d  lea     rbp, [rsp-388h]
0x180007645  sub     rsp, 488h
0x18000764c  mov     rax, cs:__security_cookie
0x180007653  xor     rax, rsp
0x180007656  mov     [rbp+3C0h+var_50], rax
0x18000765d  mov     [rsp+4C0h+pNumArgs], 0
0x180007665  mov     [rsp+4C0h+var_480], 0
0x18000766e  call    cs:__imp_InitPreprocessor
0x180007674  xor     ecx, ecx; pvReserved
0x180007676  call    cs:__imp_CoInitialize
0x18000767c  test    eax, eax
0x18000767e  js      loc_180007948
0x180007684  xor     ecx, ecx; pvReserved
0x180007686  call    cs:__imp_OleInitialize
0x18000768c  test    eax, eax
0x18000768e  js      loc_180007948
0x180007694  mov     r9b, 1
0x180007697  mov     [rsp+4C0h+var_4A0], 1
0x18000769c  mov     r8b, r9b
0x18000769f  lea     rdx, __ImageBase
0x1800076a6  mov     ecx, 0Eh
0x1800076ab  call    cs:__imp_InitProcessPriv
0x1800076b1  test    eax, eax
0x1800076b3  js      loc_180007948
0x1800076b9  lea     rcx, [rsp+4C0h+var_488]
0x1800076be  mov     [rsp+4C0h+var_488], 8
0x1800076c6  mov     [rsp+4C0h+var_484], 4000h
0x1800076ce  call    IsolationAwareInitCommonControlsEx
0x1800076d3  test    eax, eax
0x1800076d5  jz      loc_180007948
0x1800076db  call    cs:__imp_SetProcessDPIAware
0x1800076e1  call    cs:__imp_GetCommandLineW
0x1800076e7  test    rax, rax
0x1800076ea  jz      loc_180007948
0x1800076f0  lea     rdx, [rsp+4C0h+pNumArgs]; pNumArgs
0x1800076f5  mov     rcx, rax; lpCmdLine
0x1800076f8  call    cs:__imp_CommandLineToArgvW
0x1800076fe  mov     rbx, rax
0x180007701  test    rax, rax
0x180007704  jz      loc_180007948
0x18000770a  cmp     [rsp+4C0h+pNumArgs], 6
0x18000770f  jl      loc_180007948
0x180007715  mov     rcx, [rax+10h]; String
0x180007719  mov     r15d, 0FFDFh
0x18000771f  test    [rcx], r15w
0x180007723  jz      loc_180007948
0x180007729  call    cs:__imp__wtoi
0x18000772f  mov     ecx, [rsp+4C0h+pNumArgs]
0x180007733  mov     esi, eax
0x180007735  cmp     ecx, 4
0x180007738  jl      loc_180007948
0x18000773e  mov     r13, [rbx+18h]
0x180007742  test    [r13+0], r15w
0x180007747  jz      loc_180007948
0x18000774d  cmp     ecx, 5
0x180007750  jl      loc_180007948
0x180007756  mov     r12, [rbx+20h]
0x18000775a  test    [r12], r15w
0x18000775f  jz      loc_180007948
0x180007765  cmp     ecx, 6
0x180007768  jl      loc_180007948
0x18000776e  mov     r8, [rbx+28h]
0x180007772  test    [r8], r15w
0x180007776  jz      loc_180007948
0x18000777c  xor     edi, edi
0x18000777e  xor     r14d, r14d
0x180007781  cmp     ecx, 7
0x180007784  jl      short loc_180007792
0x180007786  mov     rax, [rbx+30h]
0x18000778a  test    [rax], r15w
0x18000778e  cmovnz  r14, rax
0x180007792  lea     rdx, [rsp+4C0h+var_480]; HICON *
0x180007797  mov     rcx, r8; unsigned __int16 *
0x18000779a  call    ?GetInfInfo@@YAPEAGPEBGPEAPEAUHICON__@@@Z; GetInfInfo(ushort const *,HICON__ * *)
0x18000779f  mov     rbx, rax
0x1800077a2  test    rax, rax
0x1800077a5  jnz     short loc_1800077DF
0x1800077a7  mov     ecx, 200h; Size
0x1800077ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800077b1  lea     rcx, ModuleName; "pnpui.dll"
0x1800077b8  mov     rbx, rax
0x1800077bb  call    cs:__imp_GetModuleHandleW
0x1800077c1  mov     r9d, 100h; cchBufferMax
0x1800077c7  mov     r8, rbx; lpBuffer
0x1800077ca  mov     rcx, rax; hInstance
0x1800077cd  lea     edx, [r9-33h]; uID
0x1800077d1  call    cs:__imp_LoadStringW
0x1800077d7  test    eax, eax
0x1800077d9  jz      loc_18000792E
0x1800077df  mov     r15d, 3E8h
0x1800077e5  cmp     esi, 0Ah
0x1800077e8  jz      short loc_180007802
0x1800077ea  cmp     esi, 14h
0x1800077ed  jz      short loc_180007849
0x1800077ef  cmp     esi, 1Eh
0x1800077f2  jz      short loc_180007859
0x1800077f4  cmp     esi, 28h ; '('
0x1800077f7  jz      short loc_180007849
0x1800077f9  cmp     esi, 32h ; '2'
0x1800077fc  jnz     loc_18000792E
0x180007802  test    rbx, rbx
0x180007805  jz      loc_180007948
0x18000780b  lea     rcx, ModuleName; "pnpui.dll"
0x180007812  call    cs:__imp_GetModuleHandleW
0x180007818  mov     r9d, 100h; cchBufferMax
0x18000781e  lea     r8, [rbp+3C0h+Buffer]; lpBuffer
0x180007825  mov     rcx, rax; hInstance
0x180007828  lea     edx, [r9-35h]; uID
0x18000782c  call    cs:__imp_LoadStringW
0x180007832  test    eax, eax
0x180007834  jnz     short loc_1800078A9
0x180007836  call    cs:__imp_GetLastError
0x18000783c  test    eax, eax
0x18000783e  jnz     loc_18000792E
0x180007844  jmp     loc_1800078F2
0x180007849  mov     rcx, r14; unsigned __int16 *
0x18000784c  call    ?GetCertName@@YAPEAGPEBG@Z; GetCertName(ushort const *)
0x180007851  mov     rdi, rax
0x180007854  test    rax, rax
0x180007857  jnz     short loc_18000788D
0x180007859  mov     ecx, 200h; Size
0x18000785e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007863  lea     rcx, ModuleName; "pnpui.dll"
0x18000786a  mov     rdi, rax
0x18000786d  call    cs:__imp_GetModuleHandleW
0x180007873  mov     r9d, 100h; cchBufferMax
0x180007879  mov     r8, rdi; lpBuffer
0x18000787c  mov     rcx, rax; hInstance
0x18000787f  lea     edx, [r9-35h]; uID
0x180007883  call    cs:__imp_LoadStringW
0x180007889  test    eax, eax
0x18000788b  jz      short loc_180007836
0x18000788d  test    rbx, rbx
0x180007890  jz      loc_18000793B
0x180007896  test    rdi, rdi
0x180007899  jz      loc_180007933
0x18000789f  mov     r8, [rsp+4C0h+var_480]
0x1800078a4  mov     rdx, rdi
0x1800078a7  jmp     short loc_1800078E4
0x1800078a9  xor     edx, edx; Val
0x1800078ab  lea     rcx, [rsp+4C0h+psii+4]; void *
0x1800078b0  mov     r8d, 21Ch; Size
0x1800078b6  call    memset_0
0x1800078bb  lea     r8, [rsp+4C0h+psii]; psii
0x1800078c0  mov     [rsp+4C0h+psii.cbSize], 220h
0x1800078c8  mov     edx, 100h; uFlags
0x1800078cd  mov     ecx, 2; siid
0x1800078d2  call    cs:__imp_SHGetStockIconInfo
0x1800078d8  mov     r8, [rsp+4C0h+psii.hIcon]; HICON
0x1800078dd  lea     rdx, [rbp+3C0h+Buffer]; unsigned __int16 *
0x1800078e4  mov     r9d, esi; unsigned int
0x1800078e7  mov     rcx, rbx; unsigned __int16 *
0x1800078ea  call    ?InstallSecurityPrompt@@YAHPEBG0PEAUHICON__@@K@Z; InstallSecurityPrompt(ushort const *,ushort const *,HICON__ *,ulong)
0x1800078ef  mov     r15d, eax
0x1800078f2  mov     eax, 2
0x1800078f7  cmp     r15d, eax
0x1800078fa  jnz     short loc_180007901
0x1800078fc  mov     r8, r12
0x1800078ff  jmp     short loc_18000790A
0x180007901  cmp     r15d, 1
0x180007905  jnz     short loc_18000792E
0x180007907  mov     r8, r13; lpName
0x18000790a  xor     edx, edx; bInheritHandle
0x18000790c  mov     ecx, eax; dwDesiredAccess
0x18000790e  call    cs:__imp_OpenEventW
0x180007914  mov     rsi, rax
0x180007917  test    rax, rax
0x18000791a  jz      short loc_18000792E
0x18000791c  mov     rcx, rax; hEvent
0x18000791f  call    cs:__imp_SetEvent
0x180007925  mov     rcx, rsi; hObject
0x180007928  call    cs:__imp_CloseHandle
0x18000792e  test    rbx, rbx
0x180007931  jz      short loc_18000793B
0x180007933  mov     rcx, rbx; Block
0x180007936  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000793b  test    rdi, rdi
0x18000793e  jz      short loc_180007948
0x180007940  mov     rcx, rdi; Block
0x180007943  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007948  lea     rcx, __ImageBase
0x18000794f  call    cs:__imp_UnInitProcessPriv
0x180007955  call    cs:__imp_OleUninitialize
0x18000795b  call    cs:__imp_CoUninitialize
0x180007961  mov     rcx, [rbp+3C0h+var_50]
0x180007968  xor     rcx, rsp; StackCookie
0x18000796b  call    __security_check_cookie
0x180007970  add     rsp, 488h
0x180007977  pop     r15
0x180007979  pop     r14
0x18000797b  pop     r13
0x18000797d  pop     r12
0x18000797f  pop     rdi
0x180007980  pop     rsi
0x180007981  pop     rbx
0x180007982  pop     rbp
0x180007983  retn
```
