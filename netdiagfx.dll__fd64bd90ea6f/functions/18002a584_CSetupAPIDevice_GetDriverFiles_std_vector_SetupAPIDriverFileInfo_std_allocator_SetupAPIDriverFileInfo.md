# CSetupAPIDevice::GetDriverFiles(std::vector<SetupAPIDriverFileInfo,std::allocator<SetupAPIDriverFileInfo>> *)

- ea: `0x18002a584`
- end: `0x18002a813`
- name: `?GetDriverFiles@CSetupAPIDevice@@QEAAJPEAV?$vector@USetupAPIDriverFileInfo@@V?$allocator@USetupAPIDriverFileInfo@@@std@@@std@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180027020`

## callees

- `0x18001006c`
- `0x18002a584`
- `0x18002ad14`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a5dd`
- `KERNEL32!GetLastError` at `0x18002a6b9`
- `KERNEL32!GetLastError` at `0x18002a6fb`
- `KERNEL32!GetLastError` at `0x18002a7b4`
- `KERNEL32!GetLastError` at `0x18002a5dd`
- `KERNEL32!GetLastError` at `0x18002a6b9`
- `KERNEL32!GetLastError` at `0x18002a6fb`
- `KERNEL32!GetLastError` at `0x18002a7b4`
- `SETUPAPI!SetupOpenFileQueue` at `0x18002a5cb`
- `SETUPAPI!SetupOpenFileQueue` at `0x18002a5cb`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002a633`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002a633`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x18002a65a`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x18002a65a`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002a68b`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002a6f3`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002a68b`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002a6f3`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18002a6af`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18002a6af`
- `SETUPAPI!SetupScanFileQueueW` at `0x18002a76a`
- `SETUPAPI!SetupScanFileQueueW` at `0x18002a76a`
- `SETUPAPI!SetupCloseFileQueue` at `0x18002a7e0`
- `SETUPAPI!SetupCloseFileQueue` at `0x18002a7e0`

## pseudocode

```c
__int64 __fastcall CSetupAPIDevice::GetDriverFiles(__int64 a1, __int64 *a2)
{
  __int64 result; // rax
  signed int v5; // ebx
  HSPFILEQ v6; // r12
  __int64 v7; // rdi
  signed int LastError; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  signed int v17; // eax
  __int64 v18; // rax
  signed int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  signed int v23; // eax
  DWORD Result; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _QWORD CallbackContext[2]; // [rsp+50h] [rbp-B0h] BYREF
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+60h] [rbp-A0h] BYREF

  result = CSetupAPIDevice::InitializeDriverInfo((CSetupAPIDevice *)a1);
  v5 = result;
  if ( (int)result >= 0 )
  {
    v6 = SetupOpenFileQueue();
    v7 = -1;
    if ( v6 == (HSPFILEQ)-1LL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
      DeviceInstallParams.cbSize = 584;
      v9 = *(_QWORD *)(a1 + 8);
      if ( v9 )
        v10 = *(_QWORD *)(v9 + 8);
      else
        v10 = -1;
      if ( SetupDiGetDeviceInstallParamsW((HDEVINFO)v10, (PSP_DEVINFO_DATA)(a1 + 16), &DeviceInstallParams)
        && ((v11 = *(_QWORD *)(a1 + 8)) == 0 ? (v12 = -1) : (v12 = *(_QWORD *)(v11 + 8)),
            SetupDiSetSelectedDriverW((HDEVINFO)v12, (PSP_DEVINFO_DATA)(a1 + 16), (PSP_DRVINFO_DATA_W)(a1 + 64))
         && ((DeviceInstallParams.FileQueue = v6, DeviceInstallParams.Flags |= 8u, (v13 = *(_QWORD *)(a1 + 8)) == 0)
           ? (v14 = -1)
           : (v14 = *(_QWORD *)(v13 + 8)),
             SetupDiSetDeviceInstallParamsW((HDEVINFO)v14, (PSP_DEVINFO_DATA)(a1 + 16), &DeviceInstallParams))) )
      {
        v15 = *(_QWORD *)(a1 + 8);
        if ( v15 )
          v16 = *(_QWORD *)(v15 + 8);
        else
          v16 = -1;
        if ( !SetupDiCallClassInstaller(0x15u, (HDEVINFO)v16, (PSP_DEVINFO_DATA)(a1 + 16)) )
        {
          v17 = GetLastError();
          v5 = v17;
          if ( v17 > 0 )
            v5 = (unsigned __int16)v17 | 0x80070000;
        }
        DeviceInstallParams.FileQueue = 0;
        DeviceInstallParams.Flags &= ~8u;
        v18 = *(_QWORD *)(a1 + 8);
        if ( v18 )
          v7 = *(_QWORD *)(v18 + 8);
        SetupDiSetDeviceInstallParamsW((HDEVINFO)v7, (PSP_DEVINFO_DATA)(a1 + 16), &DeviceInstallParams);
      }
      else
      {
        v19 = GetLastError();
        v5 = v19;
        if ( v19 > 0 )
          v5 = (unsigned __int16)v19 | 0x80070000;
      }
      if ( v5 >= 0 )
      {
        v25 = 0;
        v26 = 0;
        CallbackContext[0] = 0;
        CallbackContext[1] = &v25;
        Result = 0;
        if ( SetupScanFileQueueW(v6, 0x40u, 0, DriverListCallback, CallbackContext, &Result) )
        {
          if ( a2 != (__int64 *)&v25 )
          {
            v20 = *a2;
            *a2 = v25;
            *(_QWORD *)&v25 = v20;
            v21 = a2[1];
            a2[1] = *((_QWORD *)&v25 + 1);
            *((_QWORD *)&v25 + 1) = v21;
            v22 = a2[2];
            a2[2] = v26;
            v26 = v22;
          }
        }
        else
        {
          v23 = GetLastError();
          v5 = v23;
          if ( v23 > 0 )
            v5 = (unsigned __int16)v23 | 0x80070000;
          if ( SLODWORD(CallbackContext[0]) < 0 )
            v5 = CallbackContext[0];
        }
        std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>(&v25);
      }
      SetupCloseFileQueue(v6);
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002a584  mov     [rsp-8+arg_10], rbx
0x18002a589  mov     [rsp-8+arg_18], rsi
0x18002a58e  push    rbp
0x18002a58f  push    rdi
0x18002a590  push    r12
0x18002a592  push    r14
0x18002a594  push    r15
0x18002a596  lea     rbp, [rsp-1C0h]
0x18002a59e  sub     rsp, 2C0h
0x18002a5a5  mov     rax, cs:__security_cookie
0x18002a5ac  xor     rax, rsp
0x18002a5af  mov     [rbp+1E0h+var_30], rax
0x18002a5b6  mov     r14, rdx
0x18002a5b9  mov     rsi, rcx
0x18002a5bc  call    ?InitializeDriverInfo@CSetupAPIDevice@@AEAAJXZ; CSetupAPIDevice::InitializeDriverInfo(void)
0x18002a5c1  mov     ebx, eax
0x18002a5c3  test    eax, eax
0x18002a5c5  js      loc_18002A7E8
0x18002a5cb  call    cs:__imp_SetupOpenFileQueue
0x18002a5d1  mov     r12, rax
0x18002a5d4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a5d8  cmp     rax, rdi
0x18002a5db  jnz     short loc_18002A5FB
0x18002a5dd  call    cs:__imp_GetLastError
0x18002a5e3  mov     ebx, eax
0x18002a5e5  test    eax, eax
0x18002a5e7  jle     loc_18002A7E6
0x18002a5ed  movzx   ebx, ax
0x18002a5f0  or      ebx, 80070000h
0x18002a5f6  jmp     loc_18002A7E6
0x18002a5fb  xor     edx, edx; Val
0x18002a5fd  mov     r8d, 244h; Size
0x18002a603  lea     rcx, [rsp+2E0h+DeviceInstallParams.Flags]; void *
0x18002a608  call    memset_0
0x18002a60d  mov     [rsp+2E0h+DeviceInstallParams.cbSize], 248h
0x18002a615  mov     rax, [rsi+8]
0x18002a619  test    rax, rax
0x18002a61c  jz      short loc_18002A624
0x18002a61e  mov     rcx, [rax+8]
0x18002a622  jmp     short loc_18002A627
0x18002a624  mov     rcx, rdi; DeviceInfoSet
0x18002a627  lea     r15, [rsi+10h]
0x18002a62b  lea     r8, [rsp+2E0h+DeviceInstallParams]; DeviceInstallParams
0x18002a630  mov     rdx, r15; DeviceInfoData
0x18002a633  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18002a639  test    eax, eax
0x18002a63b  jz      loc_18002A6FB
0x18002a641  mov     rax, [rsi+8]
0x18002a645  test    rax, rax
0x18002a648  jz      short loc_18002A650
0x18002a64a  mov     rcx, [rax+8]
0x18002a64e  jmp     short loc_18002A653
0x18002a650  mov     rcx, rdi; DeviceInfoSet
0x18002a653  lea     r8, [rsi+40h]; DriverInfoData
0x18002a657  mov     rdx, r15; DeviceInfoData
0x18002a65a  call    cs:__imp_SetupDiSetSelectedDriverW
0x18002a660  test    eax, eax
0x18002a662  jz      loc_18002A6FB
0x18002a668  mov     [rbp+1E0h+DeviceInstallParams.FileQueue], r12
0x18002a66c  or      [rsp+2E0h+DeviceInstallParams.Flags], 8
0x18002a671  mov     rax, [rsi+8]
0x18002a675  test    rax, rax
0x18002a678  jz      short loc_18002A680
0x18002a67a  mov     rcx, [rax+8]
0x18002a67e  jmp     short loc_18002A683
0x18002a680  mov     rcx, rdi; DeviceInfoSet
0x18002a683  lea     r8, [rsp+2E0h+DeviceInstallParams]; DeviceInstallParams
0x18002a688  mov     rdx, r15; DeviceInfoData
0x18002a68b  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18002a691  test    eax, eax
0x18002a693  jz      short loc_18002A6FB
0x18002a695  mov     rax, [rsi+8]
0x18002a699  test    rax, rax
0x18002a69c  jz      short loc_18002A6A4
0x18002a69e  mov     rdx, [rax+8]
0x18002a6a2  jmp     short loc_18002A6A7
0x18002a6a4  mov     rdx, rdi; DeviceInfoSet
0x18002a6a7  mov     r8, r15; DeviceInfoData
0x18002a6aa  mov     ecx, 15h; InstallFunction
0x18002a6af  call    cs:__imp_SetupDiCallClassInstaller
0x18002a6b5  test    eax, eax
0x18002a6b7  jnz     short loc_18002A6CE
0x18002a6b9  call    cs:__imp_GetLastError
0x18002a6bf  mov     ebx, eax
0x18002a6c1  test    eax, eax
0x18002a6c3  jle     short loc_18002A6CE
0x18002a6c5  movzx   ebx, ax
0x18002a6c8  or      ebx, 80070000h
0x18002a6ce  mov     [rbp+1E0h+DeviceInstallParams.FileQueue], 0
0x18002a6d6  and     [rsp+2E0h+DeviceInstallParams.Flags], 0FFFFFFF7h
0x18002a6db  mov     rax, [rsi+8]
0x18002a6df  test    rax, rax
0x18002a6e2  jz      short loc_18002A6E8
0x18002a6e4  mov     rdi, [rax+8]
0x18002a6e8  lea     r8, [rsp+2E0h+DeviceInstallParams]; DeviceInstallParams
0x18002a6ed  mov     rdx, r15; DeviceInfoData
0x18002a6f0  mov     rcx, rdi; DeviceInfoSet
0x18002a6f3  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18002a6f9  jmp     short loc_18002A710
0x18002a6fb  call    cs:__imp_GetLastError
0x18002a701  mov     ebx, eax
0x18002a703  test    eax, eax
0x18002a705  jle     short loc_18002A710
0x18002a707  movzx   ebx, ax
0x18002a70a  or      ebx, 80070000h
0x18002a710  test    ebx, ebx
0x18002a712  js      loc_18002A7DD
0x18002a718  xorps   xmm0, xmm0
0x18002a71b  movdqu  [rsp+2E0h+var_2A8], xmm0
0x18002a721  mov     [rsp+2E0h+var_298], 0
0x18002a72a  mov     [rsp+2E0h+var_290], 0
0x18002a733  lea     rax, [rsp+2E0h+var_2A8]
0x18002a738  mov     [rsp+2E0h+var_288], rax
0x18002a73d  mov     [rsp+2E0h+var_2B0], 0
0x18002a745  lea     rax, [rsp+2E0h+var_2B0]
0x18002a74a  mov     [rsp+2E0h+Result], rax; Result
0x18002a74f  lea     rax, [rsp+2E0h+var_290]
0x18002a754  mov     [rsp+2E0h+CallbackContext], rax; CallbackContext
0x18002a759  lea     r9, ?DriverListCallback@@YAIPEAXI_K1@Z; CallbackRoutine
0x18002a760  xor     r8d, r8d; Window
0x18002a763  lea     edx, [r8+40h]; Flags
0x18002a767  mov     rcx, r12; FileQueue
0x18002a76a  call    cs:__imp_SetupScanFileQueueW
0x18002a770  test    eax, eax
0x18002a772  jz      short loc_18002A7B4
0x18002a774  lea     rax, [rsp+2E0h+var_2A8]
0x18002a779  cmp     r14, rax
0x18002a77c  jz      short loc_18002A7D3
0x18002a77e  mov     rcx, [r14]
0x18002a781  mov     rax, qword ptr [rsp+2E0h+var_2A8]
0x18002a786  mov     [r14], rax
0x18002a789  mov     qword ptr [rsp+2E0h+var_2A8], rcx
0x18002a78e  mov     rcx, [r14+8]
0x18002a792  mov     rax, qword ptr [rsp+2E0h+var_2A8+8]
0x18002a797  mov     [r14+8], rax
0x18002a79b  mov     qword ptr [rsp+2E0h+var_2A8+8], rcx
0x18002a7a0  mov     rcx, [r14+10h]
0x18002a7a4  mov     rax, [rsp+2E0h+var_298]
0x18002a7a9  mov     [r14+10h], rax
0x18002a7ad  mov     [rsp+2E0h+var_298], rcx
0x18002a7b2  jmp     short loc_18002A7D3
0x18002a7b4  call    cs:__imp_GetLastError
0x18002a7ba  mov     ebx, eax
0x18002a7bc  test    eax, eax
0x18002a7be  jle     short loc_18002A7C9
0x18002a7c0  movzx   ebx, ax
0x18002a7c3  or      ebx, 80070000h
0x18002a7c9  mov     rax, [rsp+2E0h+var_290]
0x18002a7ce  test    eax, eax
0x18002a7d0  cmovs   ebx, eax
0x18002a7d3  lea     rcx, [rsp+2E0h+var_2A8]
0x18002a7d8  call    ??1?$vector@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>(void)
0x18002a7dd  mov     rcx, r12; QueueHandle
0x18002a7e0  call    cs:__imp_SetupCloseFileQueue
0x18002a7e6  mov     eax, ebx
0x18002a7e8  mov     rcx, [rbp+1E0h+var_30]
0x18002a7ef  xor     rcx, rsp; StackCookie
0x18002a7f2  call    __security_check_cookie
0x18002a7f7  lea     r11, [rsp+2E0h+var_20]
0x18002a7ff  mov     rbx, [r11+40h]
0x18002a803  mov     rsi, [r11+48h]
0x18002a807  mov     rsp, r11
0x18002a80a  pop     r15
0x18002a80c  pop     r14
0x18002a80e  pop     r12
0x18002a810  pop     rdi
0x18002a811  pop     rbp
0x18002a812  retn
```
