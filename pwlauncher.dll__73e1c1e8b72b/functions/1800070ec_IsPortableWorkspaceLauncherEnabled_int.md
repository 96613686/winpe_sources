# IsPortableWorkspaceLauncherEnabled(int *)

- ea: `0x1800070ec`
- end: `0x1800074dd`
- name: `?IsPortableWorkspaceLauncherEnabled@@YAHPEAH@Z`
- size: `1009`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180005c98`
- `0x18000c450`

## callees

- `0x180005528`
- `0x1800070ec`
- `0x1800075fc`
- `0x1800077f8`
- `0x180007c78`
- `0x180007e74`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fdd6`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000725f`
- `KERNEL32!GetLastError` at `0x18000737c`
- `KERNEL32!GetLastError` at `0x1800073c7`
- `KERNEL32!GetLastError` at `0x180007405`
- `KERNEL32!GetLastError` at `0x18000746e`
- `KERNEL32!GetLastError` at `0x18000725f`
- `KERNEL32!GetLastError` at `0x18000737c`
- `KERNEL32!GetLastError` at `0x1800073c7`
- `KERNEL32!GetLastError` at `0x180007405`
- `KERNEL32!GetLastError` at `0x18000746e`
- `KERNEL32!SetLastError` at `0x180007456`
- `KERNEL32!SetLastError` at `0x180007456`
- `ntdll!NtQuerySystemInformation` at `0x180007304`
- `ntdll!NtQuerySystemInformation` at `0x180007304`
- `ntdll!RtlNtStatusToDosError` at `0x1800071de`
- `ntdll!RtlNtStatusToDosError` at `0x180007312`
- `ntdll!RtlNtStatusToDosError` at `0x1800071de`
- `ntdll!RtlNtStatusToDosError` at `0x180007312`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x1800071c9`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x1800071c9`

## string_xrefs

- `0x1800071b0`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x1800072c3`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007338`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall IsPortableWorkspaceLauncherEnabled(int *a1)
{
  unsigned int v2; // r14d
  _QWORD *v3; // rcx
  DWORD v4; // ebx
  NTSTATUS v5; // eax
  ULONG v6; // eax
  DWORD LastError; // eax
  int v8; // eax
  char v9; // di
  int v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rcx
  char v18; // [rsp+30h] [rbp-D0h]
  char v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 SystemInformation; // [rsp+41h] [rbp-BFh] BYREF
  _BYTE v21[2]; // [rsp+42h] [rbp-BEh] BYREF
  enum _FIRMWARE_TYPE v22; // [rsp+44h] [rbp-BCh] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v22 = FirmwareTypeUnknown;
  memset_0(FileName, 0, 0x20Au);
  v23 = 0;
  v21[0] = 0;
  v19 = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v4 = 87;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v3[2],
        130,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        143,
        87);
    goto LABEL_51;
  }
  v5 = RtlCheckPortableOperatingSystem(&v19);
  if ( v5 == -1073741275 )
  {
    v5 = 0;
    v19 = 0;
  }
  v6 = RtlNtStatusToDosError(v5);
  v4 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        131,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        146,
        v6);
    goto LABEL_51;
  }
  if ( v19 )
  {
    v4 = 50;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        149,
        50);
    goto LABEL_51;
  }
  if ( !(unsigned int)LauncherGetFirmwareType(&v22) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        151,
        LastError);
    goto LABEL_51;
  }
  if ( v22 != FirmwareTypeBios )
  {
    if ( v22 != FirmwareTypeUefi )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          178,
          v22);
      v4 = 50;
      goto LABEL_51;
    }
    SystemInformation = 0;
    v8 = NtQuerySystemInformation(SystemVdmInstemulInformation|0x80, &SystemInformation, 1u, 0);
    v9 = v8;
    if ( v8 < 0 )
    {
      v4 = RtlNtStatusToDosError(v8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          137,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          172,
          v9);
      goto LABEL_51;
    }
    v10 = SystemInformation;
LABEL_50:
    v4 = 0;
    *a1 = v10;
    v2 = 1;
    goto LABEL_51;
  }
  if ( (unsigned int)LauncherGetSystemPartitionFilePath(L"\\\\?\\GlobalRoot%s\\BOOTTGT", FileName) )
  {
    if ( (unsigned int)LauncherIsFileExist(FileName, &v23) )
    {
      if ( (unsigned int)LauncherReadBootNextFile((struct _BOOT_NEXT_HEADER *)v21) )
      {
        v10 = v23 && v21[0];
        goto LABEL_50;
      }
      v13 = GetLastError();
      v4 = v13;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          136,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          162,
          v13);
    }
    else
    {
      v12 = GetLastError();
      v4 = v12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          160,
          v12);
    }
  }
  else
  {
    v11 = GetLastError();
    v4 = v11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        158,
        v11);
  }
LABEL_51:
  SetLastError(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v18 = GetLastError();
    v16 = "Success";
    if ( !v2 )
      v16 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, v14, v15, 189, (__int64)v16, v18);
  }
  return v2;
}

```

## disassembly

```asm
0x1800070ec  mov     [rsp-8+arg_8], rbx
0x1800070f1  mov     [rsp-8+arg_10], rsi
0x1800070f6  push    rbp
0x1800070f7  push    rdi
0x1800070f8  push    r12
0x1800070fa  push    r13
0x1800070fc  push    r14
0x1800070fe  lea     rbp, [rsp-170h]
0x180007106  sub     rsp, 270h
0x18000710d  mov     rax, cs:__security_cookie
0x180007114  xor     rax, rsp
0x180007117  mov     [rbp+190h+var_30], rax
0x18000711e  mov     rsi, rcx
0x180007121  xor     r14d, r14d
0x180007124  lea     rcx, [rsp+290h+FileName]; void *
0x180007129  mov     [rsp+290h+var_24C], r14d
0x18000712e  xor     edx, edx; Val
0x180007130  mov     r8d, 20Ah; Size
0x180007136  call    memset_0
0x18000713b  mov     [rsp+290h+var_248], r14d
0x180007140  mov     [rsp+290h+var_24E], r14b
0x180007145  mov     [rsp+290h+var_250], r14b
0x18000714a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007151  lea     r12, WPP_GLOBAL_Control
0x180007158  lea     r13, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000715f  cmp     rcx, r12
0x180007162  jz      short loc_180007182
0x180007164  test    byte ptr [rcx+1Ch], 8
0x180007168  jz      short loc_180007182
0x18000716a  mov     rcx, [rcx+10h]
0x18000716e  mov     edx, 81h
0x180007173  mov     r8, r13
0x180007176  call    WPP_SF_
0x18000717b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007182  test    rsi, rsi
0x180007185  jnz     short loc_1800071C4
0x180007187  lea     ebx, [rsi+57h]
0x18000718a  cmp     rcx, r12
0x18000718d  jz      loc_180007454
0x180007193  test    byte ptr [rcx+1Ch], 1
0x180007197  jz      loc_180007454
0x18000719d  mov     dword ptr [rsp+290h+var_268], ebx
0x1800071a1  lea     edx, [rbx+2Bh]
0x1800071a4  mov     [rsp+290h+var_270], 68Fh
0x1800071ac  mov     rcx, [rcx+10h]
0x1800071b0  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800071b7  mov     r8, r13
0x1800071ba  call    WPP_SF_sdD
0x1800071bf  jmp     loc_180007454
0x1800071c4  lea     rcx, [rsp+290h+var_250]
0x1800071c9  call    cs:__imp_RtlCheckPortableOperatingSystem
0x1800071cf  cmp     eax, 0C0000225h
0x1800071d4  jnz     short loc_1800071DC
0x1800071d6  xor     eax, eax
0x1800071d8  mov     [rsp+290h+var_250], al
0x1800071dc  mov     ecx, eax; Status
0x1800071de  call    cs:__imp_RtlNtStatusToDosError
0x1800071e4  mov     ebx, eax
0x1800071e6  test    eax, eax
0x1800071e8  jz      short loc_180007217
0x1800071ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071f1  cmp     rcx, r12
0x1800071f4  jz      loc_180007454
0x1800071fa  test    byte ptr [rcx+1Ch], 1
0x1800071fe  jz      loc_180007454
0x180007204  mov     dword ptr [rsp+290h+var_268], eax
0x180007208  mov     edx, 83h
0x18000720d  mov     [rsp+290h+var_270], 692h
0x180007215  jmp     short loc_1800071AC
0x180007217  cmp     [rsp+290h+var_250], r14b
0x18000721c  jz      short loc_180007251
0x18000721e  mov     ebx, 32h ; '2'
0x180007223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000722a  cmp     rcx, r12
0x18000722d  jz      loc_180007454
0x180007233  test    byte ptr [rcx+1Ch], 1
0x180007237  jz      loc_180007454
0x18000723d  mov     dword ptr [rsp+290h+var_268], ebx
0x180007241  lea     edx, [rbx+52h]
0x180007244  mov     [rsp+290h+var_270], 695h
0x18000724c  jmp     loc_1800071AC
0x180007251  lea     rcx, [rsp+290h+var_24C]; enum _FIRMWARE_TYPE *
0x180007256  call    ?LauncherGetFirmwareType@@YAHPEAW4_FIRMWARE_TYPE@@@Z; LauncherGetFirmwareType(_FIRMWARE_TYPE *)
0x18000725b  test    eax, eax
0x18000725d  jnz     short loc_180007297
0x18000725f  call    cs:__imp_GetLastError
0x180007265  mov     ebx, eax
0x180007267  mov     rcx, cs:WPP_GLOBAL_Control
0x18000726e  cmp     rcx, r12
0x180007271  jz      loc_180007454
0x180007277  test    byte ptr [rcx+1Ch], 1
0x18000727b  jz      loc_180007454
0x180007281  mov     dword ptr [rsp+290h+var_268], eax
0x180007285  mov     edx, 85h
0x18000728a  mov     [rsp+290h+var_270], 697h
0x180007292  jmp     loc_1800071AC
0x180007297  mov     r8d, [rsp+290h+var_24C]
0x18000729c  mov     ecx, r8d
0x18000729f  sub     ecx, 1
0x1800072a2  jz      loc_180007367
0x1800072a8  cmp     ecx, 1
0x1800072ab  jz      short loc_1800072EE
0x1800072ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072b4  cmp     rcx, r12
0x1800072b7  jz      short loc_1800072E4
0x1800072b9  test    byte ptr [rcx+1Ch], 2
0x1800072bd  jz      short loc_1800072E4
0x1800072bf  mov     rcx, [rcx+10h]
0x1800072c3  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800072ca  mov     dword ptr [rsp+290h+var_268], r8d
0x1800072cf  mov     edx, 8Ah
0x1800072d4  mov     r8, r13
0x1800072d7  mov     [rsp+290h+var_270], 6B2h
0x1800072df  call    WPP_SF_sdD
0x1800072e4  mov     ebx, 32h ; '2'
0x1800072e9  jmp     loc_180007454
0x1800072ee  xor     r9d, r9d; ReturnLength
0x1800072f1  mov     [rsp+290h+SystemInformation], r14b
0x1800072f6  lea     rdx, [rsp+290h+SystemInformation]; SystemInformation
0x1800072fb  mov     ecx, 93h; SystemInformationClass
0x180007300  lea     r8d, [r9+1]; SystemInformationLength
0x180007304  call    cs:__imp_NtQuerySystemInformation
0x18000730a  mov     edi, eax
0x18000730c  test    eax, eax
0x18000730e  jns     short loc_18000735D
0x180007310  mov     ecx, eax; Status
0x180007312  call    cs:__imp_RtlNtStatusToDosError
0x180007318  mov     ebx, eax
0x18000731a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007321  cmp     rcx, r12
0x180007324  jz      loc_180007454
0x18000732a  test    byte ptr [rcx+1Ch], 1
0x18000732e  jz      loc_180007454
0x180007334  mov     rcx, [rcx+10h]
0x180007338  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000733f  mov     edx, 89h
0x180007344  mov     dword ptr [rsp+290h+var_268], edi
0x180007348  mov     r8, r13
0x18000734b  mov     [rsp+290h+var_270], 6ACh
0x180007353  call    WPP_SF_sdD
0x180007358  jmp     loc_180007454
0x18000735d  movzx   eax, [rsp+290h+SystemInformation]
0x180007362  jmp     loc_18000744C
0x180007367  lea     rdx, [rsp+290h+FileName]; unsigned __int16 *
0x18000736c  lea     rcx, aGlobalrootSBoo; "\\\\?\\GlobalRoot%s\\BOOTTGT"
0x180007373  call    ?LauncherGetSystemPartitionFilePath@@YAHPEBGPEAG@Z; LauncherGetSystemPartitionFilePath(ushort const *,ushort *)
0x180007378  test    eax, eax
0x18000737a  jnz     short loc_1800073B4
0x18000737c  call    cs:__imp_GetLastError
0x180007382  mov     ebx, eax
0x180007384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000738b  cmp     rcx, r12
0x18000738e  jz      loc_180007454
0x180007394  test    byte ptr [rcx+1Ch], 1
0x180007398  jz      loc_180007454
0x18000739e  mov     dword ptr [rsp+290h+var_268], eax
0x1800073a2  mov     edx, 86h
0x1800073a7  mov     [rsp+290h+var_270], 69Eh
0x1800073af  jmp     loc_1800071AC
0x1800073b4  lea     rdx, [rsp+290h+var_248]; int *
0x1800073b9  lea     rcx, [rsp+290h+FileName]; lpFileName
0x1800073be  call    ?LauncherIsFileExist@@YAHPEBGPEAH@Z; LauncherIsFileExist(ushort const *,int *)
0x1800073c3  test    eax, eax
0x1800073c5  jnz     short loc_1800073F7
0x1800073c7  call    cs:__imp_GetLastError
0x1800073cd  mov     ebx, eax
0x1800073cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073d6  cmp     rcx, r12
0x1800073d9  jz      short loc_180007454
0x1800073db  test    byte ptr [rcx+1Ch], 1
0x1800073df  jz      short loc_180007454
0x1800073e1  mov     dword ptr [rsp+290h+var_268], eax
0x1800073e5  mov     edx, 87h
0x1800073ea  mov     [rsp+290h+var_270], 6A0h
0x1800073f2  jmp     loc_1800071AC
0x1800073f7  lea     rcx, [rsp+290h+var_24E]; lpBuffer
0x1800073fc  call    ?LauncherReadBootNextFile@@YAHPEAU_BOOT_NEXT_HEADER@@@Z; LauncherReadBootNextFile(_BOOT_NEXT_HEADER *)
0x180007401  test    eax, eax
0x180007403  jnz     short loc_180007435
0x180007405  call    cs:__imp_GetLastError
0x18000740b  mov     ebx, eax
0x18000740d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007414  cmp     rcx, r12
0x180007417  jz      short loc_180007454
0x180007419  test    byte ptr [rcx+1Ch], 1
0x18000741d  jz      short loc_180007454
0x18000741f  mov     dword ptr [rsp+290h+var_268], eax
0x180007423  mov     edx, 88h
0x180007428  mov     [rsp+290h+var_270], 6A2h
0x180007430  jmp     loc_1800071AC
0x180007435  cmp     [rsp+290h+var_248], r14d
0x18000743a  jz      short loc_18000744A
0x18000743c  cmp     [rsp+290h+var_24E], r14b
0x180007441  jz      short loc_18000744A
0x180007443  mov     eax, 1
0x180007448  jmp     short loc_18000744C
0x18000744a  xor     eax, eax
0x18000744c  xor     ebx, ebx
0x18000744e  mov     [rsi], eax
0x180007450  lea     r14d, [rbx+1]
0x180007454  mov     ecx, ebx; dwErrCode
0x180007456  call    cs:__imp_SetLastError
0x18000745c  mov     rax, cs:WPP_GLOBAL_Control
0x180007463  cmp     rax, r12
0x180007466  jz      short loc_1800074AF
0x180007468  test    byte ptr [rax+1Ch], 4
0x18000746c  jz      short loc_1800074AF
0x18000746e  call    cs:__imp_GetLastError
0x180007474  lea     rdx, aFailure; "Failure"
0x18000747b  mov     dword ptr [rsp+290h+var_260], eax
0x18000747f  test    r14d, r14d
0x180007482  lea     rcx, aSuccess; "Success"
0x180007489  cmovz   rcx, rdx
0x18000748d  mov     edx, 8Bh
0x180007492  mov     [rsp+290h+var_268], rcx
0x180007497  mov     rcx, cs:WPP_GLOBAL_Control
0x18000749e  mov     [rsp+290h+var_270], 6BDh
0x1800074a6  mov     rcx, [rcx+10h]
0x1800074aa  call    WPP_SF_sdsd
0x1800074af  mov     eax, r14d
0x1800074b2  mov     rcx, [rbp+190h+var_30]
0x1800074b9  xor     rcx, rsp; StackCookie
0x1800074bc  call    __security_check_cookie
0x1800074c1  lea     r11, [rsp+290h+var_20]
0x1800074c9  mov     rbx, [r11+38h]
0x1800074cd  mov     rsi, [r11+40h]
0x1800074d1  mov     rsp, r11
0x1800074d4  pop     r14
0x1800074d6  pop     r13
0x1800074d8  pop     r12
0x1800074da  pop     rdi
0x1800074db  pop     rbp
0x1800074dc  retn
```
