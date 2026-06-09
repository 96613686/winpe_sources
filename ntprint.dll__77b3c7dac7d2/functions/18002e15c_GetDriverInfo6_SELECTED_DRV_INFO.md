# GetDriverInfo6(_SELECTED_DRV_INFO *)

- ea: `0x18002e15c`
- end: `0x18002e329`
- name: `?GetDriverInfo6@@YAPEAU_DRIVER_INFO_6W@@PEAU_SELECTED_DRV_INFO@@@Z`
- size: `461`
- prototype: `struct _DRIVER_INFO_6W *__fastcall(struct _SELECTED_DRV_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002e540`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18001c5c0`
- `0x1800217e0`
- `0x180026ed4`
- `0x180027a10`
- `0x18002e15c`
- `0x18002e330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e2e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e2e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e2bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e2bf`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002e1f7`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002e1f7`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002e24f`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002e24f`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002e21c`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002e21c`

## pseudocode

```c
struct _DRIVER_INFO_6W *__fastcall GetDriverInfo6(const unsigned __int16 **a1)
{
  _QWORD *v2; // rdi
  struct _DRIVER_INFO_6W *v3; // rbp
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // rax
  HDEVINFO DeviceInfoList; // rax
  __int64 v7; // rbx
  _QWORD *v8; // rax
  unsigned int v9; // esi
  struct _DRIVER_INFO_6W *v10; // rax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+50h] [rbp-278h] BYREF

  v2 = 0;
  v3 = 0;
  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  if ( a1 && *a1 && **a1 && (v4 = a1[1]) != 0 && *v4 && (v5 = a1[2]) != 0 && *v5 )
  {
    DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, 0);
    v7 = (__int64)DeviceInfoList;
    if ( DeviceInfoList != (HDEVINFO)-1LL )
    {
      DeviceInstallParams.cbSize = 584;
      if ( SetupDiGetDeviceInstallParamsW(DeviceInfoList, 0, &DeviceInstallParams) )
      {
        StringCchCopyW(DeviceInstallParams.DriverPath, 0x104u, *a1);
        DeviceInstallParams.Flags |= 0x10000u;
        if ( SetupDiSetDeviceInstallParamsW((HDEVINFO)v7, 0, &DeviceInstallParams) )
        {
          v8 = (_QWORD *)PSetupDriverInfoFromName(v7, a1[1]);
          v2 = v8;
          if ( v8 )
          {
            if ( ParseInf((void *)v7, v8, MyPlatform, 0, 0, -1, 0, 0, 0, 0) )
            {
              v9 = *((_DWORD *)v2 + 64);
              v10 = (struct _DRIVER_INFO_6W *)LocalAlloc(0x40u, v9);
              v3 = v10;
              if ( v10 )
                PackDriverInfo6((struct _DRIVER_INFO_6W *)(v2 + 33), v10, v9);
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -1;
    SetLastError(0x57u);
  }
  DestroyOnlyPrinterDeviceInfoList(v7);
  DestroyLocalData(v2);
  return v3;
}

```

## disassembly

```asm
0x18002e15c  mov     [rsp+arg_8], rbx
0x18002e161  mov     [rsp+arg_10], rbp
0x18002e166  push    rsi
0x18002e167  push    rdi
0x18002e168  push    r14
0x18002e16a  sub     rsp, 2B0h
0x18002e171  mov     rax, cs:__security_cookie
0x18002e178  xor     rax, rsp
0x18002e17b  mov     [rsp+2C8h+var_28], rax
0x18002e183  mov     rsi, rcx
0x18002e186  xor     r14d, r14d
0x18002e189  lea     rcx, [rsp+2C8h+DeviceInstallParams]; void *
0x18002e18e  xor     edx, edx; Val
0x18002e190  mov     r8d, 248h; Size
0x18002e196  mov     edi, r14d
0x18002e199  mov     ebp, r14d
0x18002e19c  call    memset_0
0x18002e1a1  test    rsi, rsi
0x18002e1a4  jz      loc_18002E2E1
0x18002e1aa  mov     rax, [rsi]
0x18002e1ad  test    rax, rax
0x18002e1b0  jz      loc_18002E2E1
0x18002e1b6  cmp     [rax], r14w
0x18002e1ba  jz      loc_18002E2E1
0x18002e1c0  mov     rax, [rsi+8]
0x18002e1c4  test    rax, rax
0x18002e1c7  jz      loc_18002E2E1
0x18002e1cd  cmp     [rax], r14w
0x18002e1d1  jz      loc_18002E2E1
0x18002e1d7  mov     rax, [rsi+10h]
0x18002e1db  test    rax, rax
0x18002e1de  jz      loc_18002E2E1
0x18002e1e4  cmp     [rax], r14w
0x18002e1e8  jz      loc_18002E2E1
0x18002e1ee  xor     edx, edx; hwndParent
0x18002e1f0  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x18002e1f7  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18002e1fd  mov     rbx, rax
0x18002e200  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e204  jz      loc_18002E2EE
0x18002e20a  lea     r8, [rsp+2C8h+DeviceInstallParams]; DeviceInstallParams
0x18002e20f  mov     [rsp+2C8h+DeviceInstallParams.cbSize], 248h
0x18002e217  xor     edx, edx; DeviceInfoData
0x18002e219  mov     rcx, rax; DeviceInfoSet
0x18002e21c  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18002e222  test    eax, eax
0x18002e224  jz      loc_18002E2EE
0x18002e22a  mov     r8, [rsi]; unsigned __int16 *
0x18002e22d  lea     rcx, [rsp+2C8h+DeviceInstallParams.DriverPath]; unsigned __int16 *
0x18002e235  mov     edx, 104h; unsigned __int64
0x18002e23a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e23f  bts     [rsp+2C8h+DeviceInstallParams.Flags], 10h
0x18002e245  lea     r8, [rsp+2C8h+DeviceInstallParams]; DeviceInstallParams
0x18002e24a  xor     edx, edx; DeviceInfoData
0x18002e24c  mov     rcx, rbx; DeviceInfoSet
0x18002e24f  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18002e255  test    eax, eax
0x18002e257  jz      loc_18002E2EE
0x18002e25d  mov     r8d, cs:MyPlatform
0x18002e264  mov     rcx, rbx; int
0x18002e267  mov     rdx, [rsi+8]; LPCWSTR
0x18002e26b  call    PSetupDriverInfoFromName
0x18002e270  mov     rdi, rax
0x18002e273  test    rax, rax
0x18002e276  jz      short loc_18002E2EE
0x18002e278  mov     r8d, cs:MyPlatform
0x18002e27f  xor     r9d, r9d
0x18002e282  mov     [rsp+2C8h+var_280], r14
0x18002e287  mov     rdx, rax
0x18002e28a  mov     [rsp+2C8h+var_288], r14
0x18002e28f  mov     rcx, rbx
0x18002e292  mov     [rsp+2C8h+var_290], r14d
0x18002e297  mov     [rsp+2C8h+var_298], r14
0x18002e29c  mov     [rsp+2C8h+var_2A0], 0FFFFFFFFFFFFFFFFh
0x18002e2a5  mov     [rsp+2C8h+var_2A8], r14d
0x18002e2aa  call    ParseInf
0x18002e2af  test    eax, eax
0x18002e2b1  jz      short loc_18002E2EE
0x18002e2b3  mov     esi, [rdi+100h]
0x18002e2b9  lea     ecx, [r14+40h]; uFlags
0x18002e2bd  mov     edx, esi; uBytes
0x18002e2bf  call    cs:__imp_LocalAlloc
0x18002e2c5  mov     rbp, rax
0x18002e2c8  test    rax, rax
0x18002e2cb  jz      short loc_18002E2EE
0x18002e2cd  lea     rcx, [rdi+108h]; struct _DRIVER_INFO_6W *
0x18002e2d4  mov     r8d, esi; unsigned int
0x18002e2d7  mov     rdx, rax; struct _DRIVER_INFO_6W *
0x18002e2da  call    ?PackDriverInfo6@@YAXPEAU_DRIVER_INFO_6W@@0K@Z; PackDriverInfo6(_DRIVER_INFO_6W *,_DRIVER_INFO_6W *,ulong)
0x18002e2df  jmp     short loc_18002E2EE
0x18002e2e1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e2e5  lea     ecx, [rbx+58h]; dwErrCode
0x18002e2e8  call    cs:__imp_SetLastError
0x18002e2ee  mov     rcx, rbx
0x18002e2f1  call    DestroyOnlyPrinterDeviceInfoList
0x18002e2f6  mov     rcx, rdi; hMem
0x18002e2f9  call    DestroyLocalData
0x18002e2fe  mov     rax, rbp
0x18002e301  mov     rcx, [rsp+2C8h+var_28]
0x18002e309  xor     rcx, rsp; StackCookie
0x18002e30c  call    __security_check_cookie
0x18002e311  lea     r11, [rsp+2C8h+var_18]
0x18002e319  mov     rbx, [r11+28h]
0x18002e31d  mov     rbp, [r11+30h]
0x18002e321  mov     rsp, r11
0x18002e324  pop     r14
0x18002e326  pop     rdi
0x18002e327  pop     rsi
0x18002e328  retn
```
