# AreMultipleInternalBootableDisksFound(int *)

- ea: `0x180005638`
- end: `0x180005a60`
- name: `?AreMultipleInternalBootableDisksFound@@YAHPEAH@Z`
- size: `1064`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005a68`

## callees

- `0x180005528`
- `0x180005638`
- `0x1800065bc`
- `0x180006814`
- `0x180008798`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800057f9`
- `KERNEL32!GetProcessHeap` at `0x1800059be`
- `KERNEL32!GetProcessHeap` at `0x1800057f9`
- `KERNEL32!GetProcessHeap` at `0x1800059be`
- `KERNEL32!CloseHandle` at `0x1800057f3`
- `KERNEL32!CloseHandle` at `0x1800059b3`
- `KERNEL32!CloseHandle` at `0x1800057f3`
- `KERNEL32!CloseHandle` at `0x1800059b3`
- `KERNEL32!GetLastError` at `0x180005726`
- `KERNEL32!GetLastError` at `0x180005849`
- `KERNEL32!GetLastError` at `0x18000585a`
- `KERNEL32!GetLastError` at `0x1800058af`
- `KERNEL32!GetLastError` at `0x1800058eb`
- `KERNEL32!GetLastError` at `0x18000593e`
- `KERNEL32!GetLastError` at `0x1800059f3`
- `KERNEL32!GetLastError` at `0x180005726`
- `KERNEL32!GetLastError` at `0x180005849`
- `KERNEL32!GetLastError` at `0x18000585a`
- `KERNEL32!GetLastError` at `0x1800058af`
- `KERNEL32!GetLastError` at `0x1800058eb`
- `KERNEL32!GetLastError` at `0x18000593e`
- `KERNEL32!GetLastError` at `0x1800059f3`
- `KERNEL32!HeapFree` at `0x180005807`
- `KERNEL32!HeapFree` at `0x1800059cc`
- `KERNEL32!HeapFree` at `0x180005807`
- `KERNEL32!HeapFree` at `0x1800059cc`
- `KERNEL32!SetLastError` at `0x1800059db`
- `KERNEL32!SetLastError` at `0x1800059db`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800059a4`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800059a4`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000577e`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180005834`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000577e`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180005834`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180005717`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180005717`

## string_xrefs

- `0x1800056ed`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180005878`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180005929`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180005963`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall AreMultipleInternalBootableDisksFound(int *a1)
{
  unsigned int v1; // r13d
  void *v2; // r14
  _QWORD *v4; // rcx
  DWORD v5; // ebx
  HDEVINFO ClassDevsW; // r15
  DWORD LastError; // eax
  int v8; // ebx
  HANDLE v9; // rax
  __int64 v10; // rsi
  HANDLE ProcessHeap; // rax
  DWORD v12; // eax
  int v13; // eax
  HANDLE v14; // rax
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rcx
  char v19; // [rsp+30h] [rbp-39h]
  int v20; // [rsp+40h] [rbp-29h] BYREF
  DWORD v21; // [rsp+44h] [rbp-25h]
  LPVOID lpMem; // [rsp+48h] [rbp-21h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+50h] [rbp-19h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+70h] [rbp+7h] BYREF

  v1 = 0;
  v2 = 0;
  v20 = 0;
  lpMem = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
    if ( ClassDevsW == (HDEVINFO)-1LL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          93,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          230,
          LastError);
    }
    else
    {
      DeviceInterfaceData.cbSize = 32;
      v8 = 0;
      v21 = 0;
      if ( SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVINTERFACE_DISK, 0, &DeviceInterfaceData) )
      {
        while ( (unsigned int)GetDiskInfo(
                                ClassDevsW,
                                &DeviceInterfaceData,
                                &DeviceInfoData,
                                (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W **)&lpMem) )
        {
          v2 = lpMem;
          v9 = OpenDisk((LPCWSTR)lpMem + 2);
          v10 = (__int64)v9;
          if ( v9 == (HANDLE)-1LL )
          {
            v5 = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                96,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                2,
                v5);
            goto LABEL_38;
          }
          if ( !(unsigned int)IsDiskBootCompatibleWithLauncher(ClassDevsW, &DeviceInfoData, v9, &v20) )
          {
            v5 = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                97,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                7,
                v5);
            goto LABEL_38;
          }
          if ( v20 )
          {
            if ( v8 )
            {
              v13 = 1;
              goto LABEL_37;
            }
            v8 = 1;
          }
          CloseHandle((HANDLE)v10);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v2);
          v2 = 0;
          ++v21;
          lpMem = 0;
          if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVINTERFACE_DISK, v21, &DeviceInterfaceData) )
            goto LABEL_20;
        }
        v5 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            255,
            v5);
        v2 = lpMem;
        v10 = -1;
      }
      else
      {
LABEL_20:
        if ( GetLastError() == 259 )
        {
          v13 = 0;
          v10 = -1;
LABEL_37:
          v5 = 0;
          *a1 = v13;
          v1 = 1;
        }
        else
        {
          v12 = GetLastError();
          v5 = v12;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              94,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              244,
              v12);
          v10 = -1;
        }
      }
LABEL_38:
      SetupDiDestroyDeviceInfoList(ClassDevsW);
      if ( v10 != -1 )
        CloseHandle((HANDLE)v10);
      if ( v2 )
      {
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v2);
      }
    }
  }
  else
  {
    v5 = 87;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v4[2],
        92,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        223,
        87);
  }
  SetLastError(v5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v19 = GetLastError();
    v17 = "Success";
    if ( !v1 )
      v17 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, v15, v16, 52, (__int64)v17, v19);
  }
  return v1;
}

```

## disassembly

```asm
0x180005638  mov     [rsp-8+arg_8], rbx
0x18000563d  mov     [rsp-8+arg_10], rsi
0x180005642  push    rbp
0x180005643  push    r12
0x180005645  push    r13
0x180005647  push    r14
0x180005649  push    r15
0x18000564b  lea     rbp, [rsp-37h]
0x180005650  sub     rsp, 0A0h
0x180005657  mov     rax, cs:__security_cookie
0x18000565e  xor     rax, rsp
0x180005661  mov     [rbp+57h+var_30], rax
0x180005665  xorps   xmm0, xmm0
0x180005668  xor     r13d, r13d
0x18000566b  xor     r14d, r14d
0x18000566e  mov     [rbp+57h+var_80], r13d
0x180005672  mov     [rbp+57h+lpMem], r14
0x180005676  mov     r12, rcx
0x180005679  movups  xmmword ptr [rbp+57h+var_70.cbSize], xmm0
0x18000567d  movups  xmmword ptr [rbp+57h+var_70.InterfaceClassGuid.Data4+4], xmm0
0x180005681  movups  xmmword ptr [rbp+57h+DeviceInfoData.cbSize], xmm0
0x180005685  movups  xmmword ptr [rbp+57h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180005689  mov     rcx, cs:WPP_GLOBAL_Control
0x180005690  lea     rsi, WPP_GLOBAL_Control
0x180005697  cmp     rcx, rsi
0x18000569a  jz      short loc_1800056BD
0x18000569c  test    byte ptr [rcx+1Ch], 8
0x1800056a0  jz      short loc_1800056BD
0x1800056a2  mov     rcx, [rcx+10h]
0x1800056a6  lea     edx, [r13+5Bh]
0x1800056aa  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800056b1  call    WPP_SF_
0x1800056b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056bd  test    r12, r12
0x1800056c0  jnz     short loc_180005705
0x1800056c2  lea     ebx, [r12+57h]
0x1800056c7  cmp     rcx, rsi
0x1800056ca  jz      loc_1800059D9
0x1800056d0  test    byte ptr [rcx+1Ch], 1
0x1800056d4  jz      loc_1800059D9
0x1800056da  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1800056de  lea     edx, [rbx+5]
0x1800056e1  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 4DFh
0x1800056e9  mov     rcx, [rcx+10h]
0x1800056ed  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800056f4  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800056fb  call    WPP_SF_sdD
0x180005700  jmp     loc_1800059D9
0x180005705  mov     r9d, 12h; Flags
0x18000570b  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x180005712  xor     r8d, r8d; hwndParent
0x180005715  xor     edx, edx; Enumerator
0x180005717  call    cs:__imp_SetupDiGetClassDevsW
0x18000571d  mov     r15, rax
0x180005720  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005724  jnz     short loc_18000575A
0x180005726  call    cs:__imp_GetLastError
0x18000572c  mov     ebx, eax
0x18000572e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005735  cmp     rcx, rsi
0x180005738  jz      loc_1800059D9
0x18000573e  test    byte ptr [rcx+1Ch], 1
0x180005742  jz      loc_1800059D9
0x180005748  mov     dword ptr [rsp+0C0h+var_98], eax
0x18000574c  lea     edx, [r15+5Eh]
0x180005750  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 4E6h
0x180005758  jmp     short loc_1800056E9
0x18000575a  lea     rax, [rbp+57h+var_70]
0x18000575e  mov     [rbp+57h+var_70.cbSize], 20h ; ' '
0x180005765  xor     ebx, ebx
0x180005767  mov     [rsp+0C0h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000576c  xor     r9d, r9d; MemberIndex
0x18000576f  mov     [rbp+57h+var_7C], ebx
0x180005772  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x180005779  xor     edx, edx; DeviceInfoData
0x18000577b  mov     rcx, r15; DeviceInfoSet
0x18000577e  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180005784  test    eax, eax
0x180005786  jz      loc_180005849
0x18000578c  lea     r9, [rbp+57h+lpMem]; struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W **
0x180005790  mov     rcx, r15; DeviceInfoSet
0x180005793  lea     r8, [rbp+57h+DeviceInfoData]; DeviceInfoData
0x180005797  lea     rdx, [rbp+57h+var_70]; DeviceInterfaceData
0x18000579b  call    ?GetDiskInfo@@YAHPEAXPEAU_SP_DEVICE_INTERFACE_DATA@@PEAU_SP_DEVINFO_DATA@@PEAPEAU_SP_DEVICE_INTERFACE_DETAIL_DATA_W@@@Z; GetDiskInfo(void *,_SP_DEVICE_INTERFACE_DATA *,_SP_DEVINFO_DATA *,_SP_DEVICE_INTERFACE_DETAIL_DATA_W * *)
0x1800057a0  test    eax, eax
0x1800057a2  jz      loc_18000593E
0x1800057a8  mov     r14, [rbp+57h+lpMem]
0x1800057ac  lea     rcx, [r14+4]; lpFileName
0x1800057b0  call    ?OpenDisk@@YAPEAXPEBG@Z; OpenDisk(ushort const *)
0x1800057b5  mov     rsi, rax
0x1800057b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800057bc  jz      loc_1800058EB
0x1800057c2  lea     r9, [rbp+57h+var_80]; int *
0x1800057c6  mov     r8, rax; hDevice
0x1800057c9  lea     rdx, [rbp+57h+DeviceInfoData]; DeviceInfoData
0x1800057cd  mov     rcx, r15; DeviceInfoSet
0x1800057d0  call    ?IsDiskBootCompatibleWithLauncher@@YAHPEAXPEAU_SP_DEVINFO_DATA@@0PEAH@Z; IsDiskBootCompatibleWithLauncher(void *,_SP_DEVINFO_DATA *,void *,int *)
0x1800057d5  test    eax, eax
0x1800057d7  jz      loc_1800058AF
0x1800057dd  cmp     [rbp+57h+var_80], r13d
0x1800057e1  jz      short loc_1800057F0
0x1800057e3  test    ebx, ebx
0x1800057e5  jnz     loc_1800058A5
0x1800057eb  mov     ebx, 1
0x1800057f0  mov     rcx, rsi; hObject
0x1800057f3  call    cs:__imp_CloseHandle
0x1800057f9  call    cs:__imp_GetProcessHeap
0x1800057ff  mov     r8, r14; lpMem
0x180005802  xor     edx, edx; dwFlags
0x180005804  mov     rcx, rax; hHeap
0x180005807  call    cs:__imp_HeapFree
0x18000580d  mov     esi, [rbp+57h+var_7C]
0x180005810  lea     rax, [rbp+57h+var_70]
0x180005814  inc     esi
0x180005816  mov     [rsp+0C0h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000581b  xor     r14d, r14d
0x18000581e  mov     [rbp+57h+var_7C], esi
0x180005821  mov     r9d, esi; MemberIndex
0x180005824  mov     [rbp+57h+lpMem], r14
0x180005828  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x18000582f  xor     edx, edx; DeviceInfoData
0x180005831  mov     rcx, r15; DeviceInfoSet
0x180005834  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000583a  test    eax, eax
0x18000583c  jnz     loc_18000578C
0x180005842  lea     rsi, WPP_GLOBAL_Control
0x180005849  call    cs:__imp_GetLastError
0x18000584f  cmp     eax, 103h
0x180005854  jz      loc_180005991
0x18000585a  call    cs:__imp_GetLastError
0x180005860  mov     ebx, eax
0x180005862  mov     rcx, cs:WPP_GLOBAL_Control
0x180005869  cmp     rcx, rsi
0x18000586c  jz      short loc_18000589C
0x18000586e  test    byte ptr [rcx+1Ch], 1
0x180005872  jz      short loc_18000589C
0x180005874  mov     rcx, [rcx+10h]
0x180005878  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000587f  mov     dword ptr [rsp+0C0h+var_98], eax
0x180005883  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000588a  mov     edx, 5Eh ; '^'
0x18000588f  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 4F4h
0x180005897  call    WPP_SF_sdD
0x18000589c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800058a0  jmp     loc_1800059A1
0x1800058a5  mov     eax, 1
0x1800058aa  jmp     loc_180005997
0x1800058af  call    cs:__imp_GetLastError
0x1800058b5  mov     ebx, eax
0x1800058b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058be  lea     rax, WPP_GLOBAL_Control
0x1800058c5  cmp     rcx, rax
0x1800058c8  jz      loc_1800059A1
0x1800058ce  test    byte ptr [rcx+1Ch], 1
0x1800058d2  jz      loc_1800059A1
0x1800058d8  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1800058dc  mov     edx, 61h ; 'a'
0x1800058e1  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 507h
0x1800058e9  jmp     short loc_180005925
0x1800058eb  call    cs:__imp_GetLastError
0x1800058f1  mov     ebx, eax
0x1800058f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058fa  lea     rax, WPP_GLOBAL_Control
0x180005901  cmp     rcx, rax
0x180005904  jz      loc_1800059A1
0x18000590a  test    byte ptr [rcx+1Ch], 1
0x18000590e  jz      loc_1800059A1
0x180005914  mov     dword ptr [rsp+0C0h+var_98], ebx
0x180005918  mov     edx, 60h ; '`'
0x18000591d  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 502h
0x180005925  mov     rcx, [rcx+10h]
0x180005929  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180005930  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180005937  call    WPP_SF_sdD
0x18000593c  jmp     short loc_1800059A1
0x18000593e  call    cs:__imp_GetLastError
0x180005944  mov     ebx, eax
0x180005946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000594d  lea     rax, WPP_GLOBAL_Control
0x180005954  cmp     rcx, rax
0x180005957  jz      short loc_180005987
0x180005959  test    byte ptr [rcx+1Ch], 1
0x18000595d  jz      short loc_180005987
0x18000595f  mov     rcx, [rcx+10h]
0x180005963  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000596a  mov     edx, 5Fh ; '_'
0x18000596f  mov     dword ptr [rsp+0C0h+var_98], ebx
0x180005973  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000597a  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 4FFh
0x180005982  call    WPP_SF_sdD
0x180005987  mov     r14, [rbp+57h+lpMem]
0x18000598b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000598f  jmp     short loc_1800059A1
0x180005991  xor     eax, eax
0x180005993  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005997  xor     ebx, ebx
0x180005999  mov     [r12], eax
0x18000599d  lea     r13d, [rbx+1]
0x1800059a1  mov     rcx, r15; DeviceInfoSet
0x1800059a4  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800059aa  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800059ae  jz      short loc_1800059B9
0x1800059b0  mov     rcx, rsi; hObject
0x1800059b3  call    cs:__imp_CloseHandle
0x1800059b9  test    r14, r14
0x1800059bc  jz      short loc_1800059D2
0x1800059be  call    cs:__imp_GetProcessHeap
0x1800059c4  mov     r8, r14; lpMem
0x1800059c7  xor     edx, edx; dwFlags
0x1800059c9  mov     rcx, rax; hHeap
0x1800059cc  call    cs:__imp_HeapFree
0x1800059d2  lea     rsi, WPP_GLOBAL_Control
0x1800059d9  mov     ecx, ebx; dwErrCode
0x1800059db  call    cs:__imp_SetLastError
0x1800059e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800059e8  cmp     rax, rsi
0x1800059eb  jz      short loc_180005A34
0x1800059ed  test    byte ptr [rax+1Ch], 4
0x1800059f1  jz      short loc_180005A34
0x1800059f3  call    cs:__imp_GetLastError
0x1800059f9  lea     rdx, aFailure; "Failure"
0x180005a00  mov     dword ptr [rsp+0C0h+var_90], eax
0x180005a04  test    r13d, r13d
0x180005a07  lea     rcx, aSuccess; "Success"
0x180005a0e  cmovz   rcx, rdx
0x180005a12  mov     edx, 62h ; 'b'
0x180005a17  mov     [rsp+0C0h+var_98], rcx
0x180005a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a23  mov     dword ptr [rsp+0C0h+DeviceInterfaceData], 534h
0x180005a2b  mov     rcx, [rcx+10h]
0x180005a2f  call    WPP_SF_sdsd
0x180005a34  mov     eax, r13d
0x180005a37  mov     rcx, [rbp+57h+var_30]
0x180005a3b  xor     rcx, rsp; StackCookie
0x180005a3e  call    __security_check_cookie
0x180005a43  lea     r11, [rsp+0C0h+var_20]
0x180005a4b  mov     rbx, [r11+38h]
0x180005a4f  mov     rsi, [r11+40h]
0x180005a53  mov     rsp, r11
0x180005a56  pop     r15
0x180005a58  pop     r14
0x180005a5a  pop     r13
0x180005a5c  pop     r12
0x180005a5e  pop     rbp
0x180005a5f  retn
```
