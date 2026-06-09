# BluetoothConnection::HrGetDeviceProperty(void *,_SP_DEVINFO_DATA *,ulong,uchar * *)

- ea: `0x180028dfc`
- end: `0x18002906f`
- name: `?HrGetDeviceProperty@BluetoothConnection@@AEAAJPEAXPEAU_SP_DEVINFO_DATA@@KPEAPEAE@Z`
- size: `627`
- prototype: `__int64 __fastcall(BluetoothConnection *this, void *, struct _SP_DEVINFO_DATA *, __int64, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028170`
- `0x180028250`

## callees

- `0x180001710`
- `0x18000538c`
- `0x180028dfc`
- `0x180029bdc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028e8f`
- `KERNEL32!GetLastError` at `0x180028f65`
- `KERNEL32!GetLastError` at `0x180028e8f`
- `KERNEL32!GetLastError` at `0x180028f65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028f18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028f18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f58`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180028e89`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180028f4b`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180028e89`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180028f4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BluetoothConnection::HrGetDeviceProperty(
        BluetoothConnection *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        __int64 a4,
        unsigned __int8 **a5)
{
  DWORD v5; // edi
  signed int LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  unsigned __int8 *PropertyBuffer; // rax
  signed int v14; // eax
  __int64 v15; // rdx
  DWORD RequiredSize; // [rsp+40h] [rbp-38h] BYREF

  v5 = a4;
  RequiredSize = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, a4);
  SetupDiGetDeviceRegistryPropertyW(a2, a3, v5, 0, 0, 0, &RequiredSize);
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 != -2147024774 )
  {
    if ( (v11 & 0x80000000) == 0 )
      return v11;
    if ( v11 != -2147024883 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v11;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, v11);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_38;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, RequiredSize, v5);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !RequiredSize )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      WPP_SF_d(v12[2], RequiredSize + 38, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, v5);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = -2147418113;
LABEL_38:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_d(v12[2], 42, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, v11);
    return v11;
  }
  PropertyBuffer = (unsigned __int8 *)CoTaskMemAlloc(RequiredSize);
  *a5 = PropertyBuffer;
  if ( !PropertyBuffer )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v11 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 40;
      goto LABEL_27;
    }
LABEL_29:
    if ( (v11 & 0x80000000) == 0 )
      return v11;
LABEL_37:
    if ( v11 == -2147024883 )
      return v11;
    goto LABEL_38;
  }
  if ( SetupDiGetDeviceRegistryPropertyW(a2, a3, v5, 0, PropertyBuffer, RequiredSize, 0) )
  {
    v11 = 0;
LABEL_28:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  CoTaskMemFree(*a5);
  *a5 = 0;
  v14 = GetLastError();
  v11 = v14;
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  if ( (v11 & 0x80000000) != 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 39;
LABEL_27:
      WPP_SF_d(v12[2], v15, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, v11);
      goto LABEL_28;
    }
    goto LABEL_29;
  }
  return v11;
}

```

## disassembly

```asm
0x180028dfc  mov     [rsp+arg_0], rbx
0x180028e01  push    rbp
0x180028e02  push    rsi
0x180028e03  push    rdi
0x180028e04  push    r12
0x180028e06  push    r14
0x180028e08  sub     rsp, 50h
0x180028e0c  mov     rax, cs:__security_cookie
0x180028e13  xor     rax, rsp
0x180028e16  mov     [rsp+78h+var_30], rax
0x180028e1b  mov     rsi, [rsp+78h+arg_20]
0x180028e23  mov     edi, r9d
0x180028e26  mov     r14, r8
0x180028e29  mov     [rsp+78h+var_38], 0
0x180028e31  mov     rbp, rdx
0x180028e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e3b  lea     r12, WPP_GLOBAL_Control
0x180028e42  cmp     rcx, r12
0x180028e45  jz      short loc_180028E62
0x180028e47  test    byte ptr [rcx+1Ch], 8
0x180028e4b  jz      short loc_180028E62
0x180028e4d  mov     rcx, [rcx+10h]
0x180028e51  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180028e58  mov     edx, 24h ; '$'
0x180028e5d  call    WPP_SF_d
0x180028e62  lea     rax, [rsp+78h+var_38]
0x180028e67  xor     r9d, r9d; PropertyRegDataType
0x180028e6a  mov     [rsp+78h+RequiredSize], rax; RequiredSize
0x180028e6f  mov     r8d, edi; Property
0x180028e72  mov     [rsp+78h+PropertyBufferSize], 0; PropertyBufferSize
0x180028e7a  mov     rdx, r14; DeviceInfoData
0x180028e7d  mov     rcx, rbp; DeviceInfoSet
0x180028e80  mov     [rsp+78h+PropertyBuffer], 0; PropertyBuffer
0x180028e89  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180028e8f  call    cs:__imp_GetLastError
0x180028e95  mov     ebx, eax
0x180028e97  test    eax, eax
0x180028e99  jle     short loc_180028EA4
0x180028e9b  movzx   ebx, ax
0x180028e9e  or      ebx, 80070000h
0x180028ea4  cmp     ebx, 8007007Ah
0x180028eaa  jnz     loc_180028FDB
0x180028eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028eb7  cmp     rcx, r12
0x180028eba  jz      short loc_180028EDB
0x180028ebc  test    byte ptr [rcx+1Ch], 8
0x180028ec0  jz      short loc_180028EDB
0x180028ec2  mov     r9d, [rsp+78h+var_38]
0x180028ec7  mov     rcx, [rcx+10h]
0x180028ecb  mov     dword ptr [rsp+78h+PropertyBuffer], edi
0x180028ecf  call    WPP_SF_dD
0x180028ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028edb  mov     eax, [rsp+78h+var_38]
0x180028edf  test    eax, eax
0x180028ee1  jnz     short loc_180028F15
0x180028ee3  cmp     rcx, r12
0x180028ee6  jz      short loc_180028F0B
0x180028ee8  test    byte ptr [rcx+1Ch], 8
0x180028eec  jz      short loc_180028F0B
0x180028eee  mov     rcx, [rcx+10h]
0x180028ef2  lea     edx, [rax+26h]
0x180028ef5  mov     r9d, edi
0x180028ef8  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180028eff  call    WPP_SF_d
0x180028f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f0b  mov     ebx, 8000FFFFh
0x180028f10  jmp     loc_180029029
0x180028f15  mov     rcx, rax; cb
0x180028f18  call    cs:__imp_CoTaskMemAlloc
0x180028f1e  mov     [rsi], rax
0x180028f21  mov     r8, rax
0x180028f24  test    rax, rax
0x180028f27  jz      short loc_180028F9F
0x180028f29  mov     eax, [rsp+78h+var_38]
0x180028f2d  xor     r9d, r9d; PropertyRegDataType
0x180028f30  mov     [rsp+78h+RequiredSize], 0; RequiredSize
0x180028f39  mov     rdx, r14; DeviceInfoData
0x180028f3c  mov     [rsp+78h+PropertyBufferSize], eax; PropertyBufferSize
0x180028f40  mov     rcx, rbp; DeviceInfoSet
0x180028f43  mov     [rsp+78h+PropertyBuffer], r8; PropertyBuffer
0x180028f48  mov     r8d, edi; Property
0x180028f4b  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180028f51  test    eax, eax
0x180028f53  jnz     short loc_180028F9B
0x180028f55  mov     rcx, [rsi]; pv
0x180028f58  call    cs:__imp_CoTaskMemFree
0x180028f5e  mov     qword ptr [rsi], 0
0x180028f65  call    cs:__imp_GetLastError
0x180028f6b  mov     ebx, eax
0x180028f6d  test    eax, eax
0x180028f6f  jle     short loc_180028F7A
0x180028f71  movzx   ebx, ax
0x180028f74  or      ebx, 80070000h
0x180028f7a  test    ebx, ebx
0x180028f7c  jns     loc_18002904C
0x180028f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f89  cmp     rcx, r12
0x180028f8c  jz      short loc_180028FD5
0x180028f8e  test    byte ptr [rcx+1Ch], 1
0x180028f92  jz      short loc_180028FD5
0x180028f94  mov     edx, 27h ; '''
0x180028f99  jmp     short loc_180028FBB
0x180028f9b  xor     ebx, ebx
0x180028f9d  jmp     short loc_180028FCE
0x180028f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fa6  mov     ebx, 8007000Eh
0x180028fab  cmp     rcx, r12
0x180028fae  jz      short loc_180028FD5
0x180028fb0  test    byte ptr [rcx+1Ch], 1
0x180028fb4  jz      short loc_180028FD5
0x180028fb6  mov     edx, 28h ; '('
0x180028fbb  mov     rcx, [rcx+10h]
0x180028fbf  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180028fc6  mov     r9d, ebx
0x180028fc9  call    WPP_SF_d
0x180028fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fd5  test    ebx, ebx
0x180028fd7  jns     short loc_18002904C
0x180028fd9  jmp     short loc_180029021
0x180028fdb  test    ebx, ebx
0x180028fdd  jns     short loc_18002904C
0x180028fdf  cmp     ebx, 8007000Dh
0x180028fe5  jz      short loc_18002901A
0x180028fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fee  cmp     rcx, r12
0x180028ff1  jz      short loc_18002904C
0x180028ff3  test    byte ptr [rcx+1Ch], 1
0x180028ff7  jz      short loc_180029029
0x180028ff9  mov     rcx, [rcx+10h]
0x180028ffd  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180029004  mov     edx, 29h ; ')'
0x180029009  mov     r9d, ebx
0x18002900c  call    WPP_SF_d
0x180029011  mov     rcx, cs:WPP_GLOBAL_Control
0x180029018  jmp     short loc_180029029
0x18002901a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029021  cmp     ebx, 8007000Dh
0x180029027  jz      short loc_18002904C
0x180029029  cmp     rcx, r12
0x18002902c  jz      short loc_18002904C
0x18002902e  test    byte ptr [rcx+1Ch], 1
0x180029032  jz      short loc_18002904C
0x180029034  mov     rcx, [rcx+10h]
0x180029038  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x18002903f  mov     edx, 2Ah ; '*'
0x180029044  mov     r9d, ebx
0x180029047  call    WPP_SF_d
0x18002904c  mov     eax, ebx
0x18002904e  mov     rcx, [rsp+78h+var_30]
0x180029053  xor     rcx, rsp; StackCookie
0x180029056  call    __security_check_cookie
0x18002905b  mov     rbx, [rsp+78h+arg_0]
0x180029063  add     rsp, 50h
0x180029067  pop     r14
0x180029069  pop     r12
0x18002906b  pop     rdi
0x18002906c  pop     rsi
0x18002906d  pop     rbp
0x18002906e  retn
```
