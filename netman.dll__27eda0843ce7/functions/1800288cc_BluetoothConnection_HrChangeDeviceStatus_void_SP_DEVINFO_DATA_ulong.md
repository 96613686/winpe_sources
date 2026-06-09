# BluetoothConnection::HrChangeDeviceStatus(void *,_SP_DEVINFO_DATA *,ulong)

- ea: `0x1800288cc`
- end: `0x180028a65`
- name: `?HrChangeDeviceStatus@BluetoothConnection@@AEAAJPEAXPEAU_SP_DEVINFO_DATA@@K@Z`
- size: `409`
- prototype: `int(BluetoothConnection *__hidden this, void *, struct _SP_DEVINFO_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180028a6c`

## callees

- `0x180001710`
- `0x18000538c`
- `0x1800288cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028997`
- `KERNEL32!GetLastError` at `0x1800289d8`
- `KERNEL32!GetLastError` at `0x180028997`
- `KERNEL32!GetLastError` at `0x1800289d8`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18002891b`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180028976`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18002891b`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180028976`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180028934`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180028989`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180028934`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180028989`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::HrChangeDeviceStatus(
        BluetoothConnection *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        int a4)
{
  signed int v7; // ebx
  signed int LastError; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  signed int v11; // eax
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+20h] [rbp-20h] BYREF
  int v14; // [rsp+28h] [rbp-18h]
  __int64 v15; // [rsp+2Ch] [rbp-14h]

  v14 = a4;
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 18;
  v15 = 1;
  if ( SetupDiSetClassInstallParamsW(a2, a3, &ClassInstallParams, 0x14u) && SetupDiCallClassInstaller(0x12u, a2, a3) )
  {
    v7 = 0;
    if ( a4 == 1 )
    {
      ClassInstallParams.cbSize = 8;
      ClassInstallParams.InstallFunction = 18;
      v14 = 1;
      v15 = 2;
      if ( !SetupDiSetClassInstallParamsW(a2, a3, &ClassInstallParams, 0x14u)
        || !SetupDiCallClassInstaller(0x12u, a2, a3) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 23;
LABEL_18:
              WPP_SF_d(v9[2], v10, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, (unsigned int)v7);
              v9 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_19;
            }
            goto LABEL_19;
          }
        }
      }
    }
  }
  else
  {
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 22;
          goto LABEL_18;
        }
LABEL_19:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
          WPP_SF_d(v9[2], 24, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, (unsigned int)v7);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800288cc  push    rbp
0x1800288ce  push    rbx
0x1800288cf  push    rsi
0x1800288d0  push    rdi
0x1800288d1  push    r14
0x1800288d3  mov     rbp, rsp
0x1800288d6  sub     rsp, 40h
0x1800288da  mov     rax, cs:__security_cookie
0x1800288e1  xor     rax, rsp
0x1800288e4  mov     [rbp+var_8], rax
0x1800288e8  mov     rsi, r8
0x1800288eb  mov     [rbp+var_18], r9d
0x1800288ef  mov     rdi, rdx
0x1800288f2  mov     [rbp+ClassInstallParams.cbSize], 8
0x1800288f9  mov     r14d, r9d
0x1800288fc  mov     [rbp+ClassInstallParams.InstallFunction], 12h
0x180028903  mov     rdx, rsi; DeviceInfoData
0x180028906  mov     [rbp+var_14], 1
0x18002890e  mov     rcx, rdi; DeviceInfoSet
0x180028911  lea     r8, [rbp+ClassInstallParams]; ClassInstallParams
0x180028915  mov     r9d, 14h; ClassInstallParamsSize
0x18002891b  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180028921  test    eax, eax
0x180028923  jz      loc_1800289D8
0x180028929  mov     r8, rsi; DeviceInfoData
0x18002892c  mov     rdx, rdi; DeviceInfoSet
0x18002892f  mov     ecx, 12h; InstallFunction
0x180028934  call    cs:__imp_SetupDiCallClassInstaller
0x18002893a  test    eax, eax
0x18002893c  jz      loc_1800289D8
0x180028942  xor     ebx, ebx
0x180028944  cmp     r14d, 1
0x180028948  jnz     loc_180028A4C
0x18002894e  lea     r9d, [rbx+14h]; ClassInstallParamsSize
0x180028952  mov     [rbp+ClassInstallParams.cbSize], 8
0x180028959  lea     r8, [rbp+ClassInstallParams]; ClassInstallParams
0x18002895d  mov     [rbp+ClassInstallParams.InstallFunction], 12h
0x180028964  mov     rdx, rsi; DeviceInfoData
0x180028967  mov     [rbp+var_18], r14d
0x18002896b  mov     rcx, rdi; DeviceInfoSet
0x18002896e  mov     [rbp+var_14], 2
0x180028976  call    cs:__imp_SetupDiSetClassInstallParamsW
0x18002897c  test    eax, eax
0x18002897e  jz      short loc_180028997
0x180028980  mov     r8, rsi; DeviceInfoData
0x180028983  lea     ecx, [rbx+12h]; InstallFunction
0x180028986  mov     rdx, rdi; DeviceInfoSet
0x180028989  call    cs:__imp_SetupDiCallClassInstaller
0x18002898f  test    eax, eax
0x180028991  jnz     loc_180028A4C
0x180028997  call    cs:__imp_GetLastError
0x18002899d  mov     ebx, eax
0x18002899f  test    eax, eax
0x1800289a1  jle     short loc_1800289AC
0x1800289a3  movzx   ebx, ax
0x1800289a6  or      ebx, 80070000h
0x1800289ac  test    ebx, ebx
0x1800289ae  jns     loc_180028A4C
0x1800289b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289bb  lea     rdi, WPP_GLOBAL_Control
0x1800289c2  cmp     rcx, rdi
0x1800289c5  jz      loc_180028A4C
0x1800289cb  test    byte ptr [rcx+1Ch], 1
0x1800289cf  jz      short loc_180028A29
0x1800289d1  mov     edx, 17h
0x1800289d6  jmp     short loc_180028A0F
0x1800289d8  call    cs:__imp_GetLastError
0x1800289de  mov     ebx, eax
0x1800289e0  test    eax, eax
0x1800289e2  jle     short loc_1800289ED
0x1800289e4  movzx   ebx, ax
0x1800289e7  or      ebx, 80070000h
0x1800289ed  test    ebx, ebx
0x1800289ef  jns     short loc_180028A4C
0x1800289f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289f8  lea     rdi, WPP_GLOBAL_Control
0x1800289ff  cmp     rcx, rdi
0x180028a02  jz      short loc_180028A4C
0x180028a04  test    byte ptr [rcx+1Ch], 1
0x180028a08  jz      short loc_180028A29
0x180028a0a  mov     edx, 16h
0x180028a0f  mov     rcx, [rcx+10h]
0x180028a13  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180028a1a  mov     r9d, ebx
0x180028a1d  call    WPP_SF_d
0x180028a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a29  cmp     rcx, rdi
0x180028a2c  jz      short loc_180028A4C
0x180028a2e  test    byte ptr [rcx+1Ch], 1
0x180028a32  jz      short loc_180028A4C
0x180028a34  mov     rcx, [rcx+10h]
0x180028a38  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180028a3f  mov     edx, 18h
0x180028a44  mov     r9d, ebx
0x180028a47  call    WPP_SF_d
0x180028a4c  mov     eax, ebx
0x180028a4e  mov     rcx, [rbp+var_8]
0x180028a52  xor     rcx, rsp; StackCookie
0x180028a55  call    __security_check_cookie
0x180028a5a  add     rsp, 40h
0x180028a5e  pop     r14
0x180028a60  pop     rdi
0x180028a61  pop     rsi
0x180028a62  pop     rbx
0x180028a63  pop     rbp
0x180028a64  retn
```
