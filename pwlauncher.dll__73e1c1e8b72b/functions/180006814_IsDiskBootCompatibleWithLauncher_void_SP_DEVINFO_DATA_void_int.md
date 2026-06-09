# IsDiskBootCompatibleWithLauncher(void *,_SP_DEVINFO_DATA *,void *,int *)

- ea: `0x180006814`
- end: `0x180006b2d`
- name: `?IsDiskBootCompatibleWithLauncher@@YAHPEAXPEAU_SP_DEVINFO_DATA@@0PEAH@Z`
- size: `793`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, HANDLE hDevice, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005638`

## callees

- `0x180005528`
- `0x180006814`
- `0x180006b34`
- `0x180006e44`
- `0x180008ac8`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006964`
- `KERNEL32!GetLastError` at `0x18000696e`
- `KERNEL32!GetLastError` at `0x1800069d3`
- `KERNEL32!GetLastError` at `0x180006a4e`
- `KERNEL32!GetLastError` at `0x180006ada`
- `KERNEL32!GetLastError` at `0x180006964`
- `KERNEL32!GetLastError` at `0x18000696e`
- `KERNEL32!GetLastError` at `0x1800069d3`
- `KERNEL32!GetLastError` at `0x180006a4e`
- `KERNEL32!GetLastError` at `0x180006ada`
- `KERNEL32!SetLastError` at `0x180006ac2`
- `KERNEL32!SetLastError` at `0x180006ac2`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180006905`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180006905`

## string_xrefs

- `0x1800068a7`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x1800069ab`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall IsDiskBootCompatibleWithLauncher(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        HANDLE hDevice,
        int *a4)
{
  unsigned int v8; // esi
  _QWORD *v9; // rcx
  DWORD v10; // edi
  bool v11; // r15
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  int v17; // r8d
  int v18; // r9d
  const char *v19; // rcx
  char RequiredSize; // [rsp+30h] [rbp-28h]
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-18h] BYREF
  DWORD v23; // [rsp+44h] [rbp-14h] BYREF
  int v24; // [rsp+48h] [rbp-10h] BYREF
  int v25[3]; // [rsp+4Ch] [rbp-Ch] BYREF
  BYTE PropertyBuffer; // [rsp+B8h] [rbp+60h] BYREF

  v24 = 0;
  v25[0] = 0;
  v8 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    v10 = 87;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v9[2],
        75,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        237,
        87);
    goto LABEL_39;
  }
  PropertyBuffer = 0;
  PropertyType = 0;
  v23 = 0;
  v11 = 0;
  if ( SetupDiGetDevicePropertyW(
         DeviceInfoSet,
         DeviceInfoData,
         &DEVPKEY_Device_InLocalMachineContainer,
         &PropertyType,
         &PropertyBuffer,
         1u,
         &v23,
         0) )
  {
    if ( PropertyType == 17 && v23 == 1 )
      v11 = PropertyBuffer != 0xFFu;
  }
  else if ( GetLastError() )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        253,
        LastError);
    goto LABEL_39;
  }
  v10 = 0;
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_17;
    v13 = 77;
LABEL_16:
    WPP_SF_(v12[2], v13, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
LABEL_17:
    *a4 = 0;
    v8 = 1;
    goto LABEL_39;
  }
  if ( (unsigned int)IsDiskMbrBootable(hDevice, &v24) )
  {
    if ( !v24 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_17;
      v13 = 79;
      goto LABEL_16;
    }
    if ( (unsigned int)IsDiskVhd(hDevice, v25) )
    {
      if ( !v25[0] )
      {
        *a4 = 1;
        v8 = 1;
        goto LABEL_39;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_17;
      v13 = 81;
      goto LABEL_16;
    }
    v16 = GetLastError();
    v10 = v16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        19,
        v16);
  }
  else
  {
    v15 = GetLastError();
    v10 = v15;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        8,
        v15);
  }
LABEL_39:
  SetLastError(v10);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    RequiredSize = GetLastError();
    v19 = "Success";
    if ( !v8 )
      v19 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, v17, v18, 36, (__int64)v19, RequiredSize);
  }
  return v8;
}

```

## disassembly

```asm
0x180006814  push    rbp
0x180006816  push    rbx
0x180006817  push    rsi
0x180006818  push    rdi
0x180006819  push    r12
0x18000681b  push    r13
0x18000681d  push    r14
0x18000681f  push    r15
0x180006821  mov     rbp, rsp
0x180006824  sub     rsp, 58h
0x180006828  mov     r14, r9
0x18000682b  mov     [rbp+var_10], 0
0x180006832  mov     r12, r8
0x180006835  mov     [rbp+var_C], 0
0x18000683c  mov     rdi, rdx
0x18000683f  mov     r13, rcx
0x180006842  xor     esi, esi
0x180006844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000684b  lea     rax, WPP_GLOBAL_Control
0x180006852  cmp     rcx, rax
0x180006855  jz      short loc_18000687E
0x180006857  test    byte ptr [rcx+1Ch], 8
0x18000685b  jz      short loc_18000687E
0x18000685d  mov     rcx, [rcx+10h]
0x180006861  lea     edx, [rsi+4Ah]
0x180006864  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000686b  call    WPP_SF_
0x180006870  mov     rcx, cs:WPP_GLOBAL_Control
0x180006877  lea     rax, WPP_GLOBAL_Control
0x18000687e  test    r14, r14
0x180006881  jnz     short loc_1800068C7
0x180006883  lea     edi, [r14+57h]
0x180006887  cmp     rcx, rax
0x18000688a  jz      loc_180006AB9
0x180006890  lea     ebx, [rdi-56h]
0x180006893  test    [rcx+1Ch], bl
0x180006896  jz      loc_180006AB9
0x18000689c  mov     rcx, [rcx+10h]
0x1800068a0  lea     edx, [rdi-0Ch]
0x1800068a3  mov     [rsp+58h+PropertyBufferSize], edi
0x1800068a7  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800068ae  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800068b5  mov     dword ptr [rsp+58h+PropertyBuffer], 3EDh
0x1800068bd  call    WPP_SF_sdD
0x1800068c2  jmp     loc_180006AB9
0x1800068c7  xor     eax, eax
0x1800068c9  lea     r9, [rbp+PropertyType]; PropertyType
0x1800068cd  mov     [rsp+58h+Flags], eax; Flags
0x1800068d1  lea     r8, DEVPKEY_Device_InLocalMachineContainer; PropertyKey
0x1800068d8  mov     [rbp+arg_18], al
0x1800068db  mov     ebx, 1
0x1800068e0  mov     [rbp+PropertyType], eax
0x1800068e3  mov     rdx, rdi; DeviceInfoData
0x1800068e6  mov     [rbp+var_14], eax
0x1800068e9  mov     rcx, r13; DeviceInfoSet
0x1800068ec  lea     rax, [rbp+var_14]
0x1800068f0  xor     r15b, r15b
0x1800068f3  mov     [rsp+58h+RequiredSize], rax; RequiredSize
0x1800068f8  lea     rax, [rbp+arg_18]
0x1800068fc  mov     [rsp+58h+PropertyBufferSize], ebx; PropertyBufferSize
0x180006900  mov     [rsp+58h+PropertyBuffer], rax; PropertyBuffer
0x180006905  call    cs:__imp_SetupDiGetDevicePropertyW
0x18000690b  test    eax, eax
0x18000690d  jz      short loc_180006964
0x18000690f  cmp     [rbp+PropertyType], 11h
0x180006913  jnz     short loc_180006923
0x180006915  cmp     [rbp+var_14], ebx
0x180006918  jnz     short loc_180006923
0x18000691a  cmp     [rbp+arg_18], 0FFh
0x18000691e  jz      short loc_180006923
0x180006920  mov     r15b, bl
0x180006923  xor     edi, edi
0x180006925  test    r15b, r15b
0x180006928  jz      loc_1800069C3
0x18000692e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006935  lea     r15, WPP_GLOBAL_Control
0x18000693c  cmp     rcx, r15
0x18000693f  jz      short loc_18000695A
0x180006941  test    byte ptr [rcx+1Ch], 4
0x180006945  jz      short loc_18000695A
0x180006947  lea     edx, [rdi+4Dh]
0x18000694a  mov     rcx, [rcx+10h]
0x18000694e  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006955  call    WPP_SF_
0x18000695a  mov     [r14], esi
0x18000695d  mov     esi, ebx
0x18000695f  jmp     loc_180006AC0
0x180006964  call    cs:__imp_GetLastError
0x18000696a  test    eax, eax
0x18000696c  jz      short loc_180006923
0x18000696e  call    cs:__imp_GetLastError
0x180006974  mov     edi, eax
0x180006976  mov     rcx, cs:WPP_GLOBAL_Control
0x18000697d  lea     r15, WPP_GLOBAL_Control
0x180006984  cmp     rcx, r15
0x180006987  jz      loc_180006AC0
0x18000698d  test    [rcx+1Ch], bl
0x180006990  jz      loc_180006AC0
0x180006996  mov     [rsp+58h+PropertyBufferSize], eax
0x18000699a  mov     edx, 4Ch ; 'L'
0x18000699f  mov     dword ptr [rsp+58h+PropertyBuffer], 3FDh
0x1800069a7  mov     rcx, [rcx+10h]
0x1800069ab  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800069b2  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800069b9  call    WPP_SF_sdD
0x1800069be  jmp     loc_180006AC0
0x1800069c3  lea     rdx, [rbp+var_10]; int *
0x1800069c7  mov     rcx, r12; hDevice
0x1800069ca  call    ?IsDiskMbrBootable@@YAHPEAXPEAH@Z; IsDiskMbrBootable(void *,int *)
0x1800069cf  test    eax, eax
0x1800069d1  jnz     short loc_180006A0E
0x1800069d3  call    cs:__imp_GetLastError
0x1800069d9  mov     edi, eax
0x1800069db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069e2  lea     r15, WPP_GLOBAL_Control
0x1800069e9  cmp     rcx, r15
0x1800069ec  jz      loc_180006AC0
0x1800069f2  test    [rcx+1Ch], bl
0x1800069f5  jz      loc_180006AC0
0x1800069fb  mov     [rsp+58h+PropertyBufferSize], eax
0x1800069ff  mov     edx, 4Eh ; 'N'
0x180006a04  mov     dword ptr [rsp+58h+PropertyBuffer], 408h
0x180006a0c  jmp     short loc_1800069A7
0x180006a0e  cmp     [rbp+var_10], esi
0x180006a11  jnz     short loc_180006A3E
0x180006a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a1a  lea     r15, WPP_GLOBAL_Control
0x180006a21  cmp     rcx, r15
0x180006a24  jz      loc_18000695A
0x180006a2a  test    byte ptr [rcx+1Ch], 4
0x180006a2e  jz      loc_18000695A
0x180006a34  mov     edx, 4Fh ; 'O'
0x180006a39  jmp     loc_18000694A
0x180006a3e  lea     rdx, [rbp+var_C]; int *
0x180006a42  mov     rcx, r12; hDevice
0x180006a45  call    ?IsDiskVhd@@YAHPEAXPEAH@Z; IsDiskVhd(void *,int *)
0x180006a4a  test    eax, eax
0x180006a4c  jnz     short loc_180006A84
0x180006a4e  call    cs:__imp_GetLastError
0x180006a54  mov     edi, eax
0x180006a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a5d  lea     r15, WPP_GLOBAL_Control
0x180006a64  cmp     rcx, r15
0x180006a67  jz      short loc_180006AC0
0x180006a69  test    [rcx+1Ch], bl
0x180006a6c  jz      short loc_180006AC0
0x180006a6e  mov     [rsp+58h+PropertyBufferSize], eax
0x180006a72  mov     edx, 50h ; 'P'
0x180006a77  mov     dword ptr [rsp+58h+PropertyBuffer], 413h
0x180006a7f  jmp     loc_1800069A7
0x180006a84  cmp     [rbp+var_C], esi
0x180006a87  jz      short loc_180006AB4
0x180006a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a90  lea     r15, WPP_GLOBAL_Control
0x180006a97  cmp     rcx, r15
0x180006a9a  jz      loc_18000695A
0x180006aa0  test    byte ptr [rcx+1Ch], 4
0x180006aa4  jz      loc_18000695A
0x180006aaa  mov     edx, 51h ; 'Q'
0x180006aaf  jmp     loc_18000694A
0x180006ab4  mov     [r14], ebx
0x180006ab7  mov     esi, ebx
0x180006ab9  lea     r15, WPP_GLOBAL_Control
0x180006ac0  mov     ecx, edi; dwErrCode
0x180006ac2  call    cs:__imp_SetLastError
0x180006ac8  mov     rax, cs:WPP_GLOBAL_Control
0x180006acf  cmp     rax, r15
0x180006ad2  jz      short loc_180006B1A
0x180006ad4  test    byte ptr [rax+1Ch], 4
0x180006ad8  jz      short loc_180006B1A
0x180006ada  call    cs:__imp_GetLastError
0x180006ae0  lea     rdx, aFailure; "Failure"
0x180006ae7  mov     dword ptr [rsp+58h+RequiredSize], eax
0x180006aeb  test    esi, esi
0x180006aed  lea     rcx, aSuccess; "Success"
0x180006af4  cmovz   rcx, rdx
0x180006af8  mov     edx, 52h ; 'R'
0x180006afd  mov     qword ptr [rsp+58h+PropertyBufferSize], rcx
0x180006b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b09  mov     dword ptr [rsp+58h+PropertyBuffer], 424h
0x180006b11  mov     rcx, [rcx+10h]
0x180006b15  call    WPP_SF_sdsd
0x180006b1a  mov     eax, esi
0x180006b1c  add     rsp, 58h
0x180006b20  pop     r15
0x180006b22  pop     r14
0x180006b24  pop     r13
0x180006b26  pop     r12
0x180006b28  pop     rdi
0x180006b29  pop     rsi
0x180006b2a  pop     rbx
0x180006b2b  pop     rbp
0x180006b2c  retn
```
