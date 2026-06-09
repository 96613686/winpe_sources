# _ShowPortableWorkspaceLauncherConfigurationUX_::_1_::catch$5

- ea: `0x18001035e`
- end: `0x180010427`
- name: `_ShowPortableWorkspaceLauncherConfigurationUX_::_1_::catch$5`
- size: `201`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005528`
- `0x180008ac8`
- `0x180008d9c`
- `0x180009360`
- `0x180009974`
- `0x18001035e`

## import_xrefs

- `USER32!GetActiveWindow` at `0x1800103c7`
- `USER32!GetActiveWindow` at `0x1800103c7`

## string_xrefs

- `0x18001039d`: `drivers\wdm\usbpw\launcher\dll\ux.cpp`

## pseudocode

```c
__int64 __fastcall ShowPortableWorkspaceLauncherConfigurationUX_::_1_::catch_5(__int64 a1, __int64 a2)
{
  HWND ActiveWindow; // rax
  int v5; // [rsp+28h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = **(_DWORD **)(a2 + 56);
    WPP_SF_sdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
      (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
      92,
      v5);
  }
  ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog(a2 + 96, 0xD8u, 0xD6u);
  ActiveWindow = GetActiveWindow();
  if ( (int)WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(a2 + 104, (__int64)ActiveWindow) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_10512c3147f2350527aef22e4c614f89_Traceguids);
  }
  ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)(a2 + 96));
  return 0;
}

```

## disassembly

```asm
0x18001035e  mov     [rsp+arg_8], rdx
0x180010363  push    rbp
0x180010364  sub     rsp, 30h
0x180010368  mov     rbp, rdx
0x18001036b  lea     rax, WPP_GLOBAL_Control
0x180010372  mov     rcx, cs:WPP_GLOBAL_Control
0x180010379  cmp     rcx, rax
0x18001037c  jz      short loc_1800103B4
0x18001037e  test    byte ptr [rcx+1Ch], 1
0x180010382  jz      short loc_1800103B4
0x180010384  mov     edx, 10h
0x180010389  mov     rax, [rbp+38h]
0x18001038d  mov     r8d, [rax]
0x180010390  mov     [rsp+38h+var_10], r8d
0x180010395  mov     [rsp+38h+var_18], 5Ch ; '\'
0x18001039d  lea     r9, aDriversWdmUsbp_6; "drivers\\wdm\\usbpw\\launcher\\dll\\ux."...
0x1800103a4  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x1800103ab  mov     rcx, [rcx+10h]
0x1800103af  call    WPP_SF_sdD
0x1800103b4  mov     edx, 0D8h; int
0x1800103b9  lea     r8d, [rdx-2]; int
0x1800103bd  lea     rcx, [rbp+60h]; this
0x1800103c1  call    ??0CLauncherErrorTaskDialog@ux@@QEAA@HH@Z; ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog(int,int)
0x1800103c6  nop
0x1800103c7  call    cs:__imp_GetActiveWindow
0x1800103cd  mov     rdx, rax
0x1800103d0  lea     rcx, [rbp+68h]
0x1800103d4  call    ?DoModal@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@QEAAJPEAUHWND__@@PEAH11@Z; WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(HWND__ *,int *,int *,int *)
0x1800103d9  test    eax, eax
0x1800103db  jns     short loc_18001040C
0x1800103dd  lea     rax, WPP_GLOBAL_Control
0x1800103e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103eb  cmp     rcx, rax
0x1800103ee  jz      short loc_18001040C
0x1800103f0  test    byte ptr [rcx+1Ch], 2
0x1800103f4  jz      short loc_18001040C
0x1800103f6  mov     edx, 11h
0x1800103fb  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x180010402  mov     rcx, [rcx+10h]
0x180010406  call    WPP_SF_
0x18001040b  nop
0x18001040c  lea     rcx, [rbp+60h]; this
0x180010410  call    ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
0x180010415  nop
0x180010416  mov     rax, 0
0x180010420  add     rsp, 30h
0x180010424  pop     rbp
0x180010425  retn
```
