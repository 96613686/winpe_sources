# CLanNetPage::RaiseDeviceConfiguration(HWND__ *,INetCfgComponent *)

- ea: `0x18003019c`
- end: `0x1800303d1`
- name: `?RaiseDeviceConfiguration@CLanNetPage@@KAJPEAUHWND__@@PEAUINetCfgComponent@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(HWND hwnd, struct INetCfgComponent *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002dc50`
- `0x18002de34`

## callees

- `0x18001e1e0`
- `0x18001eb7c`
- `0x1800227b0`
- `0x18003019c`
- `0x180034a44`
- `0x180034ba0`
- `0x180065010`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18003038c`
- `SHELL32!ShellExecuteW` at `0x18003038c`
- `USER32!FindWindowW` at `0x1800302a0`
- `USER32!FindWindowW` at `0x1800302a0`
- `USER32!SetForegroundWindow` at `0x1800302b8`
- `USER32!SetForegroundWindow` at `0x1800302b8`
- `USER32!LoadStringW` at `0x18003025a`
- `USER32!LoadStringW` at `0x18003025a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003023f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003023f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800302d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800302d0`
- `ole32!CoTaskMemFree` at `0x18003028d`
- `ole32!CoTaskMemFree` at `0x1800303a3`
- `ole32!CoTaskMemFree` at `0x18003028d`
- `ole32!CoTaskMemFree` at `0x1800303a3`

## string_xrefs

- `0x180030238`: `comctl32.dll`
- `0x1800302e9`: `devmgr.dll,DeviceProperties_RunDLL /DeviceId "`
- `0x180030380`: `rundll32.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLanNetPage::RaiseDeviceConfiguration(HWND hwnd, struct INetCfgComponent *a2)
{
  int v4; // ebx
  struct INetCfgComponentVtbl *lpVtbl; // rax
  struct INetCfgComponentVtbl *v6; // rcx
  int Win32Error; // edi
  HMODULE ModuleHandleW; // rax
  HWND WindowW; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[47]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[434]; // [rsp+9Eh] [rbp-62h] BYREF
  WCHAR WindowName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR Directory[264]; // [rsp+460h] [rbp+360h] BYREF

  v4 = -2147024809;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v12 = 0;
    v4 = ((__int64 (__fastcall *)(struct INetCfgComponent *, unsigned __int16 **))lpVtbl->GetPnpDevNodeId)(a2, &v12);
    if ( v4 >= 0 )
    {
      memset_0(WindowName, 0, 0x104u);
      v6 = a2->lpVtbl;
      pv = 0;
      Win32Error = ((__int64 (__fastcall *)(struct INetCfgComponent *, LPVOID *))v6->GetDisplayName)(a2, &pv);
      if ( Win32Error >= 0 )
      {
        ModuleHandleW = GetModuleHandleW(L"comctl32.dll");
        if ( ModuleHandleW
          && LoadStringW(ModuleHandleW, 0x1042u, Buffer, 260)
          && !DwFormatString(Buffer, WindowName, 0x104u, pv) )
        {
          Win32Error = HrFromLastWin32Error();
        }
        CoTaskMemFree(pv);
      }
      if ( Win32Error < 0
        || (WindowW = FindWindowW(0, WindowName), !WindowName[0])
        || !WindowW
        || !SetForegroundWindow(WindowW) )
      {
        if ( GetSystemDirectoryW(Directory, 0x104u) )
        {
          wcscpy(Buffer, L"devmgr.dll,DeviceProperties_RunDLL /DeiceId \"");
          memset_0(v14, 0, 0x1AAu);
          v4 = StringCchCatW(Buffer, 0x104u, v12);
          if ( v4 >= 0 )
          {
            v4 = StringCchCatW(Buffer, 0x104u, L"\"");
            if ( v4 >= 0 && (unsigned __int64)ShellExecuteW(hwnd, 0, L"rundll32.exe", Buffer, Directory, 5) <= 0x20 )
              v4 = -2147024894;
          }
        }
      }
      CoTaskMemFree(v12);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003019c  mov     [rsp-8+arg_10], rbx
0x1800301a1  push    rbp
0x1800301a2  push    rsi
0x1800301a3  push    rdi
0x1800301a4  push    r14
0x1800301a6  push    r15
0x1800301a8  lea     rbp, [rsp-580h]
0x1800301b0  sub     rsp, 680h
0x1800301b7  mov     rax, cs:__security_cookie
0x1800301be  xor     rax, rsp
0x1800301c1  mov     [rbp+5A0h+var_30], rax
0x1800301c8  xor     r14d, r14d
0x1800301cb  mov     rdi, rdx
0x1800301ce  mov     rsi, rcx
0x1800301d1  mov     ebx, 80070057h
0x1800301d6  test    rdx, rdx
0x1800301d9  jz      loc_1800303A9
0x1800301df  mov     rax, [rdx]
0x1800301e2  mov     rcx, rdi
0x1800301e5  lea     rdx, [rsp+6A0h+var_668]
0x1800301ea  mov     [rsp+6A0h+var_668], r14
0x1800301ef  mov     rax, [rax+48h]
0x1800301f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301f8  mov     ebx, eax
0x1800301fa  test    eax, eax
0x1800301fc  js      loc_1800303A9
0x180030202  mov     r15d, 104h
0x180030208  lea     rcx, [rbp+5A0h+WindowName]; void *
0x18003020f  mov     r8d, r15d; Size
0x180030212  xor     edx, edx; Val
0x180030214  call    memset_0
0x180030219  mov     rcx, [rdi]
0x18003021c  lea     rdx, [rsp+6A0h+pv]
0x180030221  mov     [rsp+6A0h+pv], r14
0x180030226  mov     rax, [rcx+18h]
0x18003022a  mov     rcx, rdi
0x18003022d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030232  mov     edi, eax
0x180030234  test    eax, eax
0x180030236  js      short loc_180030293
0x180030238  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18003023f  call    cs:__imp_GetModuleHandleW
0x180030245  test    rax, rax
0x180030248  jz      short loc_180030288
0x18003024a  mov     r9d, r15d; cchBufferMax
0x18003024d  lea     r8, [rsp+6A0h+Buffer]; lpBuffer
0x180030252  mov     edx, 1042h; uID
0x180030257  mov     rcx, rax; hInstance
0x18003025a  call    cs:__imp_LoadStringW
0x180030260  test    eax, eax
0x180030262  jz      short loc_180030288
0x180030264  mov     r9, [rsp+6A0h+pv]
0x180030269  lea     rdx, [rbp+5A0h+WindowName]; unsigned __int16 *
0x180030270  mov     r8d, r15d; unsigned int
0x180030273  lea     rcx, [rsp+6A0h+Buffer]; lpSource
0x180030278  call    ?DwFormatString@@YAKPEBGPEAGKZZ; DwFormatString(ushort const *,ushort *,ulong,...)
0x18003027d  test    eax, eax
0x18003027f  jnz     short loc_180030288
0x180030281  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030286  mov     edi, eax
0x180030288  mov     rcx, [rsp+6A0h+pv]; pv
0x18003028d  call    cs:__imp_CoTaskMemFree
0x180030293  test    edi, edi
0x180030295  js      short loc_1800302C6
0x180030297  lea     rdx, [rbp+5A0h+WindowName]; lpWindowName
0x18003029e  xor     ecx, ecx; lpClassName
0x1800302a0  call    cs:__imp_FindWindowW
0x1800302a6  cmp     [rbp+5A0h+WindowName], r14w
0x1800302ae  jz      short loc_1800302C6
0x1800302b0  test    rax, rax
0x1800302b3  jz      short loc_1800302C6
0x1800302b5  mov     rcx, rax; hWnd
0x1800302b8  call    cs:__imp_SetForegroundWindow
0x1800302be  test    eax, eax
0x1800302c0  jnz     loc_18003039E
0x1800302c6  mov     edx, r15d; uSize
0x1800302c9  lea     rcx, [rbp+5A0h+Directory]; lpBuffer
0x1800302d0  call    cs:__imp_GetSystemDirectoryW
0x1800302d6  test    eax, eax
0x1800302d8  jz      loc_18003039E
0x1800302de  movaps  xmm1, xmmword ptr cs:aDevmgrDllDevic+10h; "ll,DeviceProperties_RunDLL /DeviceId \""
0x1800302e5  lea     rcx, [rbp+5A0h+var_602]; void *
0x1800302e9  movaps  xmm0, xmmword ptr cs:aDevmgrDllDevic; "devmgr.dll,DeviceProperties_RunDLL /Dev"...
0x1800302f0  xor     edx, edx; Val
0x1800302f2  movaps  [rsp+6A0h+var_650], xmm1
0x1800302f7  mov     r8d, 1AAh; Size
0x1800302fd  movaps  xmm1, xmmword ptr cs:aDevmgrDllDevic+30h; "ies_RunDLL /DeviceId \""
0x180030304  movaps  xmmword ptr [rsp+6A0h+Buffer], xmm0
0x180030309  movaps  xmm0, xmmword ptr cs:aDevmgrDllDevic+20h; "eProperties_RunDLL /DeviceId \""
0x180030310  movaps  [rsp+6A0h+var_630], xmm1
0x180030315  movups  xmm1, xmmword ptr cs:aDevmgrDllDevic+4Eh; "iceId \""
0x18003031c  movaps  [rsp+6A0h+var_640], xmm0
0x180030321  movaps  xmm0, xmmword ptr cs:aDevmgrDllDevic+40h; "LL /DeviceId \""
0x180030328  movaps  [rbp+5A0h+var_620], xmm0
0x18003032c  movups  [rbp+5A0h+var_620+0Eh], xmm1
0x180030330  call    memset_0
0x180030335  mov     r8, [rsp+6A0h+var_668]; unsigned __int16 *
0x18003033a  lea     rcx, [rsp+6A0h+Buffer]; unsigned __int16 *
0x18003033f  mov     rdx, r15; unsigned __int64
0x180030342  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030347  mov     ebx, eax
0x180030349  test    eax, eax
0x18003034b  js      short loc_18003039E
0x18003034d  lea     r8, asc_180079570; "\""
0x180030354  mov     rdx, r15; unsigned __int64
0x180030357  lea     rcx, [rsp+6A0h+Buffer]; unsigned __int16 *
0x18003035c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030361  mov     ebx, eax
0x180030363  test    eax, eax
0x180030365  js      short loc_18003039E
0x180030367  lea     rax, [rbp+5A0h+Directory]
0x18003036e  mov     [rsp+6A0h+nShowCmd], 5; nShowCmd
0x180030376  lea     r9, [rsp+6A0h+Buffer]; lpParameters
0x18003037b  mov     [rsp+6A0h+lpDirectory], rax; lpDirectory
0x180030380  lea     r8, File; "rundll32.exe"
0x180030387  xor     edx, edx; lpOperation
0x180030389  mov     rcx, rsi; hwnd
0x18003038c  call    cs:__imp_ShellExecuteW
0x180030392  cmp     rax, 20h ; ' '
0x180030396  mov     ecx, 80070002h
0x18003039b  cmovbe  ebx, ecx
0x18003039e  mov     rcx, [rsp+6A0h+var_668]; pv
0x1800303a3  call    cs:__imp_CoTaskMemFree
0x1800303a9  mov     eax, ebx
0x1800303ab  mov     rcx, [rbp+5A0h+var_30]
0x1800303b2  xor     rcx, rsp; StackCookie
0x1800303b5  call    __security_check_cookie
0x1800303ba  mov     rbx, [rsp+6A0h+arg_10]
0x1800303c2  add     rsp, 680h
0x1800303c9  pop     r15
0x1800303cb  pop     r14
0x1800303cd  pop     rdi
0x1800303ce  pop     rsi
0x1800303cf  pop     rbp
0x1800303d0  retn
```
