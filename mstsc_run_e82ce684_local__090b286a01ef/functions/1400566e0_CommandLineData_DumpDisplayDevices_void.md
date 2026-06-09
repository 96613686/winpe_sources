# CommandLineData::DumpDisplayDevices(void)

- ea: `0x1400566e0`
- end: `0x1400569b9`
- name: `?DumpDisplayDevices@CommandLineData@@AEAAXXZ`
- size: `729`
- prototype: `void __fastcall(CommandLineData *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140058174`

## callees

- `0x140004703`
- `0x140008940`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cf70`
- `0x140042394`
- `0x1400566e0`
- `0x1400fcad0`
- `0x140113390`
- `0x140113450`

## import_xrefs

- `USER32!EnumDisplayDevicesW` at `0x1400567ea`
- `USER32!EnumDisplayDevicesW` at `0x140056962`
- `USER32!EnumDisplayDevicesW` at `0x1400567ea`
- `USER32!EnumDisplayDevicesW` at `0x140056962`
- `USER32!EnumDisplayMonitors` at `0x14005685b`
- `USER32!EnumDisplayMonitors` at `0x14005685b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x140056996`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x140056996`
- `KERNEL32!GetModuleHandleW` at `0x140056744`
- `KERNEL32!GetModuleHandleW` at `0x140056744`
- `GDI32!CreateDCW` at `0x14005680c`
- `GDI32!CreateDCW` at `0x14005680c`

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
0x1400566e0  push    rbp
0x1400566e2  push    rbx
0x1400566e3  push    r12
0x1400566e5  push    r13
0x1400566e7  lea     rbp, [rsp-2718h]
0x1400566ef  mov     eax, 2818h
0x1400566f4  call    _alloca_probe
0x1400566f9  sub     rsp, rax
0x1400566fc  mov     rax, cs:__security_cookie
0x140056703  xor     rax, rsp
0x140056706  mov     [rbp+2730h+var_30], rax
0x14005670d  xor     edx, edx; Val
0x14005670f  lea     rcx, [rbp+2730h+var_2030]; void *
0x140056716  mov     r8d, 2000h; Size
0x14005671c  call    memset_0
0x140056721  xor     edx, edx; Val
0x140056723  lea     rcx, [rbp+2730h+DisplayDevice]; void *
0x140056727  mov     r8d, 348h; Size
0x14005672d  call    memset_0
0x140056732  xor     edx, edx; Val
0x140056734  lea     rcx, [rsp+2830h+dwData]; void *
0x140056739  lea     r8d, [rdx+70h]; Size
0x14005673d  call    memset_0
0x140056742  xor     ecx, ecx; lpModuleName
0x140056744  call    cs:__imp_GetModuleHandleW
0x14005674a  mov     r12d, 100h
0x140056750  lea     r8, [rbp+2730h+cTitle]; unsigned __int16 *
0x140056757  mov     rcx, rax; HINSTANCE
0x14005675a  mov     r9d, r12d; int
0x14005675d  mov     edx, 3ECh; unsigned int
0x140056762  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140056767  test    eax, eax
0x140056769  jnz     short loc_1400567BF
0x14005676b  mov     rax, cs:WPP_GLOBAL_Control
0x140056772  lea     rcx, WPP_GLOBAL_Control
0x140056779  cmp     rax, rcx
0x14005677c  jz      loc_14005699C
0x140056782  test    byte ptr [rax+1Ch], 1
0x140056786  jz      loc_14005699C
0x14005678c  cmp     byte ptr [rax+19h], 2
0x140056790  jb      loc_14005699C
0x140056796  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005679b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400567a2  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x1400567a9  mov     edx, 1Ah
0x1400567ae  mov     r9d, eax
0x1400567b1  mov     rcx, [rcx+10h]
0x1400567b5  call    WPP_SF_d
0x1400567ba  jmp     loc_14005699C
0x1400567bf  xor     edx, edx; Val
0x1400567c1  lea     rcx, [rbp+2730h+var_2430]; void *
0x1400567c8  mov     r8d, 200h; Size
0x1400567ce  call    memset_0
0x1400567d3  xor     r9d, r9d; dwFlags
0x1400567d6  mov     [rbp+2730h+DisplayDevice.cb], 348h
0x1400567dd  lea     r8, [rbp+2730h+DisplayDevice]; lpDisplayDevice
0x1400567e1  xor     edx, edx; iDevNum
0x1400567e3  xor     ecx, ecx; lpDevice
0x1400567e5  mov     ebx, 1
0x1400567ea  call    cs:__imp_EnumDisplayDevicesW
0x1400567f0  test    eax, eax
0x1400567f2  jz      loc_140056970
0x1400567f8  mov     r13d, 1000h
0x1400567fe  xor     r9d, r9d; pdm
0x140056801  lea     rdx, [rbp+2730h+DisplayDevice.DeviceName]; pwszDevice
0x140056805  xor     r8d, r8d; pszPort
0x140056808  lea     rcx, [rbp+2730h+DisplayDevice.DeviceName]; pwszDriver
0x14005680c  call    cs:__imp_CreateDCW
0x140056812  test    rax, rax
0x140056815  jz      loc_14005693A
0x14005681b  test    byte ptr [rbp+2730h+DisplayDevice.StateFlags], 1
0x140056822  jz      loc_14005693A
0x140056828  xor     edx, edx; Val
0x14005682a  lea     rcx, [rsp+2830h+dwData]; void *
0x14005682f  lea     r8d, [rdx+70h]; Size
0x140056833  call    memset_0
0x140056838  lea     r8, [rbp+2730h+DisplayDevice.DeviceName]; unsigned __int16 *
0x14005683c  mov     edx, 40h ; '@'; unsigned __int64
0x140056841  lea     rcx, [rsp+2830h+var_27C0]; unsigned __int16 *
0x140056846  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14005684b  lea     r9, [rsp+2830h+dwData]; dwData
0x140056850  xor     edx, edx; lprcClip
0x140056852  lea     r8, ?MonitorEnumFunc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x140056859  xor     ecx, ecx; hdc
0x14005685b  call    cs:__imp_EnumDisplayMonitors
0x140056861  cmp     [rsp+2830h+var_27E8], 0
0x140056866  jz      loc_14005693A
0x14005686c  lea     r9d, [rbx-1]
0x140056870  mov     rdx, r12; unsigned __int64
0x140056873  lea     r8, aD_0; "%d: "
0x14005687a  lea     rcx, [rbp+2730h+var_2430]; unsigned __int16 *
0x140056881  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140056886  lea     r8, [rbp+2730h+var_2430]; unsigned __int16 *
0x14005688d  mov     rdx, r13; unsigned __int64
0x140056890  lea     rcx, [rbp+2730h+var_2030]; unsigned __int16 *
0x140056897  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005689c  mov     eax, [rsp+2830h+var_27D8]
0x1400568a0  lea     r8, aDXD; "%d x %d; "
0x1400568a7  sub     eax, [rsp+2830h+var_27E0]
0x1400568ab  mov     rdx, r12; unsigned __int64
0x1400568ae  mov     ecx, eax
0x1400568b0  neg     ecx
0x1400568b2  cmovs   ecx, eax
0x1400568b5  mov     eax, [rsp+2830h+var_27DC]
0x1400568b9  sub     eax, [rsp+2830h+var_27E4]
0x1400568bd  mov     r9d, eax
0x1400568c0  mov     dword ptr [rsp+2830h+fuStyle], ecx
0x1400568c4  neg     r9d
0x1400568c7  lea     rcx, [rbp+2730h+var_2430]; unsigned __int16 *
0x1400568ce  cmovs   r9d, eax
0x1400568d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400568d7  lea     r8, [rbp+2730h+var_2430]; unsigned __int16 *
0x1400568de  mov     rdx, r13; unsigned __int64
0x1400568e1  lea     rcx, [rbp+2730h+var_2030]; unsigned __int16 *
0x1400568e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400568ed  mov     ecx, [rsp+2830h+var_27D8]
0x1400568f1  lea     r8, aDDDD; "(%d, %d, %d, %d)\n"
0x1400568f8  mov     eax, [rsp+2830h+var_27DC]
0x1400568fc  dec     ecx
0x1400568fe  mov     r9d, [rsp+2830h+var_27E4]
0x140056903  dec     eax
0x140056905  mov     [rsp+2830h+var_2800], ecx
0x140056909  mov     rdx, r12; unsigned __int64
0x14005690c  mov     dword ptr [rsp+2830h+var_2808], eax
0x140056910  lea     rcx, [rbp+2730h+var_2430]; unsigned __int16 *
0x140056917  mov     eax, [rsp+2830h+var_27E0]
0x14005691b  mov     dword ptr [rsp+2830h+fuStyle], eax
0x14005691f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140056924  lea     r8, [rbp+2730h+var_2430]; unsigned __int16 *
0x14005692b  mov     rdx, r13; unsigned __int64
0x14005692e  lea     rcx, [rbp+2730h+var_2030]; unsigned __int16 *
0x140056935  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005693a  xor     edx, edx; Val
0x14005693c  lea     rcx, [rbp+2730h+var_2430]; void *
0x140056943  mov     r8d, 200h; Size
0x140056949  call    memset_0
0x14005694e  mov     edx, ebx; iDevNum
0x140056950  mov     [rbp+2730h+DisplayDevice.cb], 348h
0x140056957  xor     r9d, r9d; dwFlags
0x14005695a  lea     r8, [rbp+2730h+DisplayDevice]; lpDisplayDevice
0x14005695e  xor     ecx, ecx; lpDevice
0x140056960  inc     ebx
0x140056962  call    cs:__imp_EnumDisplayDevicesW
0x140056968  test    eax, eax
0x14005696a  jnz     loc_1400567FE
0x140056970  lea     rax, [rbp+2730h+var_2030]
0x140056977  xor     edx, edx; hWnd
0x140056979  mov     [rsp+2830h+var_2808], rax
0x14005697e  lea     r9, [rbp+2730h+cTitle]; lpcTitle
0x140056985  lea     r8, cText; "%1"
0x14005698c  mov     dword ptr [rsp+2830h+fuStyle], 40h ; '@'; fuStyle
0x140056994  xor     ecx, ecx; hAppInst
0x140056996  call    cs:__imp_ShellMessageBoxW
0x14005699c  mov     rcx, [rbp+2730h+var_30]
0x1400569a3  xor     rcx, rsp; StackCookie
0x1400569a6  call    __security_check_cookie
0x1400569ab  add     rsp, 2818h
0x1400569b2  pop     r13
0x1400569b4  pop     r12
0x1400569b6  pop     rbx
0x1400569b7  pop     rbp
0x1400569b8  retn
```
