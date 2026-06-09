# CommandLineData::DumpDisplayDevices(void)

- ea: `0x140054570`
- end: `0x140054849`
- name: `?DumpDisplayDevices@CommandLineData@@AEAAXXZ`
- size: `729`
- prototype: `void __fastcall(CommandLineData *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140056004`

## callees

- `0x140004703`
- `0x140008940`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cf70`
- `0x1400403d0`
- `0x140054570`
- `0x1400fa960`
- `0x140111220`
- `0x1401112e0`

## import_xrefs

- `USER32!EnumDisplayDevicesW` at `0x14005467a`
- `USER32!EnumDisplayDevicesW` at `0x1400547f2`
- `USER32!EnumDisplayDevicesW` at `0x14005467a`
- `USER32!EnumDisplayDevicesW` at `0x1400547f2`
- `USER32!EnumDisplayMonitors` at `0x1400546eb`
- `USER32!EnumDisplayMonitors` at `0x1400546eb`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x140054826`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x140054826`
- `KERNEL32!GetModuleHandleW` at `0x1400545d4`
- `KERNEL32!GetModuleHandleW` at `0x1400545d4`
- `GDI32!CreateDCW` at `0x14005469c`
- `GDI32!CreateDCW` at `0x14005469c`

## pseudocode

```c
void __fastcall CommandLineData::DumpDisplayDevices(CommandLineData *this)
{
  HMODULE ModuleHandleW; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v3; // ebx
  int v4; // ecx
  __int64 v5; // r9
  DWORD v6; // edx
  __int64 fuStyle; // [rsp+20h] [rbp-E0h]
  __int64 fuStylea; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+30h] [rbp-D0h]
  LPARAM dwData; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h]
  unsigned int v13; // [rsp+4Ch] [rbp-B4h]
  int v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+54h] [rbp-ACh]
  int v16; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v17[32]; // [rsp+70h] [rbp-90h] BYREF
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v19[256]; // [rsp+400h] [rbp+300h] BYREF
  WCHAR cTitle[256]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int16 v21[4096]; // [rsp+800h] [rbp+700h] BYREF

  memset_0(v21, 0, sizeof(v21));
  memset_0(&DisplayDevice, 0, sizeof(DisplayDevice));
  memset_0(&dwData, 0, 0x70u);
  ModuleHandleW = GetModuleHandleW(0);
  if ( TSLoadString(ModuleHandleW, 0x3ECu, cTitle, 256) )
  {
    memset_0(v19, 0, sizeof(v19));
    DisplayDevice.cb = 840;
    v3 = 1;
    if ( EnumDisplayDevicesW(0, 0, &DisplayDevice, 0) )
    {
      do
      {
        if ( CreateDCW(DisplayDevice.DeviceName, DisplayDevice.DeviceName, 0, 0) )
        {
          if ( (DisplayDevice.StateFlags & 1) != 0 )
          {
            memset_0(&dwData, 0, 0x70u);
            StringCbCopyW(v17, 0x40u, DisplayDevice.DeviceName);
            EnumDisplayMonitors(0, 0, MonitorEnumFunc, (LPARAM)&dwData);
            if ( v12 )
            {
              StringCchPrintfW(v19, 0x100u, L"%d: ", (unsigned int)(v3 - 1));
              StringCchCatW(v21, 0x1000u, v19);
              v4 = v14 - v16;
              if ( v14 - v16 < 0 )
                v4 = v16 - v14;
              LODWORD(fuStyle) = v4;
              v5 = v13 - v15;
              if ( (int)(v13 - v15) < 0 )
                v5 = v15 - v13;
              StringCchPrintfW(v19, 0x100u, L"%d x %d; ", v5, fuStyle);
              StringCchCatW(v21, 0x1000u, v19);
              LODWORD(v10) = v16 - 1;
              LODWORD(v9) = v15 - 1;
              LODWORD(fuStylea) = v14;
              StringCchPrintfW(v19, 0x100u, L"(%d, %d, %d, %d)\n", v13, fuStylea, v9, v10);
              StringCchCatW(v21, 0x1000u, v19);
            }
          }
        }
        memset_0(v19, 0, sizeof(v19));
        v6 = v3;
        DisplayDevice.cb = 840;
        ++v3;
      }
      while ( EnumDisplayDevicesW(0, v6, &DisplayDevice, 0) );
    }
    ShellMessageBoxW(0, 0, L"%1", cTitle, 0x40u, v21);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
}

```

## disassembly

```asm
0x140054570  push    rbp
0x140054572  push    rbx
0x140054573  push    r12
0x140054575  push    r13
0x140054577  lea     rbp, [rsp-2718h]
0x14005457f  mov     eax, 2818h
0x140054584  call    _alloca_probe
0x140054589  sub     rsp, rax
0x14005458c  mov     rax, cs:__security_cookie
0x140054593  xor     rax, rsp
0x140054596  mov     [rbp+2730h+var_30], rax
0x14005459d  xor     edx, edx; Val
0x14005459f  lea     rcx, [rbp+2730h+var_2030]; void *
0x1400545a6  mov     r8d, 2000h; Size
0x1400545ac  call    memset_0
0x1400545b1  xor     edx, edx; Val
0x1400545b3  lea     rcx, [rbp+2730h+DisplayDevice]; void *
0x1400545b7  mov     r8d, 348h; Size
0x1400545bd  call    memset_0
0x1400545c2  xor     edx, edx; Val
0x1400545c4  lea     rcx, [rsp+2830h+dwData]; void *
0x1400545c9  lea     r8d, [rdx+70h]; Size
0x1400545cd  call    memset_0
0x1400545d2  xor     ecx, ecx; lpModuleName
0x1400545d4  call    cs:__imp_GetModuleHandleW
0x1400545da  mov     r12d, 100h
0x1400545e0  lea     r8, [rbp+2730h+cTitle]; unsigned __int16 *
0x1400545e7  mov     rcx, rax; HINSTANCE
0x1400545ea  mov     r9d, r12d; int
0x1400545ed  mov     edx, 3ECh; unsigned int
0x1400545f2  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x1400545f7  test    eax, eax
0x1400545f9  jnz     short loc_14005464F
0x1400545fb  mov     rax, cs:WPP_GLOBAL_Control
0x140054602  lea     rcx, WPP_GLOBAL_Control
0x140054609  cmp     rax, rcx
0x14005460c  jz      loc_14005482C
0x140054612  test    byte ptr [rax+1Ch], 1
0x140054616  jz      loc_14005482C
0x14005461c  cmp     byte ptr [rax+19h], 2
0x140054620  jb      loc_14005482C
0x140054626  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005462b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054632  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140054639  mov     edx, 1Ah
0x14005463e  mov     r9d, eax
0x140054641  mov     rcx, [rcx+10h]
0x140054645  call    WPP_SF_d
0x14005464a  jmp     loc_14005482C
0x14005464f  xor     edx, edx; Val
0x140054651  lea     rcx, [rbp+2730h+var_2430]; void *
0x140054658  mov     r8d, 200h; Size
0x14005465e  call    memset_0
0x140054663  xor     r9d, r9d; dwFlags
0x140054666  mov     [rbp+2730h+DisplayDevice.cb], 348h
0x14005466d  lea     r8, [rbp+2730h+DisplayDevice]; lpDisplayDevice
0x140054671  xor     edx, edx; iDevNum
0x140054673  xor     ecx, ecx; lpDevice
0x140054675  mov     ebx, 1
0x14005467a  call    cs:__imp_EnumDisplayDevicesW
0x140054680  test    eax, eax
0x140054682  jz      loc_140054800
0x140054688  mov     r13d, 1000h
0x14005468e  xor     r9d, r9d; pdm
0x140054691  lea     rdx, [rbp+2730h+DisplayDevice.DeviceName]; pwszDevice
0x140054695  xor     r8d, r8d; pszPort
0x140054698  lea     rcx, [rbp+2730h+DisplayDevice.DeviceName]; pwszDriver
0x14005469c  call    cs:__imp_CreateDCW
0x1400546a2  test    rax, rax
0x1400546a5  jz      loc_1400547CA
0x1400546ab  test    byte ptr [rbp+2730h+DisplayDevice.StateFlags], 1
0x1400546b2  jz      loc_1400547CA
0x1400546b8  xor     edx, edx; Val
0x1400546ba  lea     rcx, [rsp+2830h+dwData]; void *
0x1400546bf  lea     r8d, [rdx+70h]; Size
0x1400546c3  call    memset_0
0x1400546c8  lea     r8, [rbp+2730h+DisplayDevice.DeviceName]; unsigned __int16 *
0x1400546cc  mov     edx, 40h ; '@'; unsigned __int64
0x1400546d1  lea     rcx, [rsp+2830h+var_27C0]; unsigned __int16 *
0x1400546d6  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400546db  lea     r9, [rsp+2830h+dwData]; dwData
0x1400546e0  xor     edx, edx; lprcClip
0x1400546e2  lea     r8, ?MonitorEnumFunc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x1400546e9  xor     ecx, ecx; hdc
0x1400546eb  call    cs:__imp_EnumDisplayMonitors
0x1400546f1  cmp     [rsp+2830h+var_27E8], 0
0x1400546f6  jz      loc_1400547CA
0x1400546fc  lea     r9d, [rbx-1]
0x140054700  mov     rdx, r12; unsigned __int64
0x140054703  lea     r8, aD_0; "%d: "
0x14005470a  lea     rcx, [rbp+2730h+var_2430]; unsigned __int16 *
0x140054711  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140054716  lea     r8, [rbp+2730h+var_2430]; unsigned __int16 *
0x14005471d  mov     rdx, r13; unsigned __int64
0x140054720  lea     rcx, [rbp+2730h+var_2030]; unsigned __int16 *
0x140054727  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005472c  mov     eax, [rsp+2830h+var_27D8]
0x140054730  lea     r8, aDXD; "%d x %d; "
0x140054737  sub     eax, [rsp+2830h+var_27E0]
0x14005473b  mov     rdx, r12; unsigned __int64
0x14005473e  mov     ecx, eax
0x140054740  neg     ecx
0x140054742  cmovs   ecx, eax
0x140054745  mov     eax, [rsp+2830h+var_27DC]
0x140054749  sub     eax, [rsp+2830h+var_27E4]
0x14005474d  mov     r9d, eax
0x140054750  mov     dword ptr [rsp+2830h+fuStyle], ecx
0x140054754  neg     r9d
0x140054757  lea     rcx, [rbp+2730h+var_2430]; unsigned __int16 *
0x14005475e  cmovs   r9d, eax
0x140054762  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140054767  lea     r8, [rbp+2730h+var_2430]; unsigned __int16 *
0x14005476e  mov     rdx, r13; unsigned __int64
0x140054771  lea     rcx, [rbp+2730h+var_2030]; unsigned __int16 *
0x140054778  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005477d  mov     ecx, [rsp+2830h+var_27D8]
0x140054781  lea     r8, aDDDD; "(%d, %d, %d, %d)\n"
0x140054788  mov     eax, [rsp+2830h+var_27DC]
0x14005478c  dec     ecx
0x14005478e  mov     r9d, [rsp+2830h+var_27E4]
0x140054793  dec     eax
0x140054795  mov     [rsp+2830h+var_2800], ecx
0x140054799  mov     rdx, r12; unsigned __int64
0x14005479c  mov     dword ptr [rsp+2830h+var_2808], eax
0x1400547a0  lea     rcx, [rbp+2730h+var_2430]; unsigned __int16 *
0x1400547a7  mov     eax, [rsp+2830h+var_27E0]
0x1400547ab  mov     dword ptr [rsp+2830h+fuStyle], eax
0x1400547af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400547b4  lea     r8, [rbp+2730h+var_2430]; unsigned __int16 *
0x1400547bb  mov     rdx, r13; unsigned __int64
0x1400547be  lea     rcx, [rbp+2730h+var_2030]; unsigned __int16 *
0x1400547c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400547ca  xor     edx, edx; Val
0x1400547cc  lea     rcx, [rbp+2730h+var_2430]; void *
0x1400547d3  mov     r8d, 200h; Size
0x1400547d9  call    memset_0
0x1400547de  mov     edx, ebx; iDevNum
0x1400547e0  mov     [rbp+2730h+DisplayDevice.cb], 348h
0x1400547e7  xor     r9d, r9d; dwFlags
0x1400547ea  lea     r8, [rbp+2730h+DisplayDevice]; lpDisplayDevice
0x1400547ee  xor     ecx, ecx; lpDevice
0x1400547f0  inc     ebx
0x1400547f2  call    cs:__imp_EnumDisplayDevicesW
0x1400547f8  test    eax, eax
0x1400547fa  jnz     loc_14005468E
0x140054800  lea     rax, [rbp+2730h+var_2030]
0x140054807  xor     edx, edx; hWnd
0x140054809  mov     [rsp+2830h+var_2808], rax
0x14005480e  lea     r9, [rbp+2730h+cTitle]; lpcTitle
0x140054815  lea     r8, cText; "%1"
0x14005481c  mov     dword ptr [rsp+2830h+fuStyle], 40h ; '@'; fuStyle
0x140054824  xor     ecx, ecx; hAppInst
0x140054826  call    cs:__imp_ShellMessageBoxW
0x14005482c  mov     rcx, [rbp+2730h+var_30]
0x140054833  xor     rcx, rsp; StackCookie
0x140054836  call    __security_check_cookie
0x14005483b  add     rsp, 2818h
0x140054842  pop     r13
0x140054844  pop     r12
0x140054846  pop     rbx
0x140054847  pop     rbp
0x140054848  retn
```
