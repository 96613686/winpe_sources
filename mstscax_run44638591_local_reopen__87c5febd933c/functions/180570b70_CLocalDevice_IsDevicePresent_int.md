# CLocalDevice::IsDevicePresent(int *)

- ea: `0x180570b70`
- end: `0x180570f25`
- name: `?IsDevicePresent@CLocalDevice@@UEAAJPEAH@Z`
- size: `949`
- prototype: `__int64 __fastcall(CLocalDevice *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18056d1a0`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x18056f8a0`
- `0x180570b70`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180570cba`
- `KERNEL32!GetLastError` at `0x180570d3d`
- `KERNEL32!GetLastError` at `0x180570e4d`
- `KERNEL32!GetLastError` at `0x180570eb5`
- `KERNEL32!GetLastError` at `0x180570ec6`
- `KERNEL32!GetLastError` at `0x180570cba`
- `KERNEL32!GetLastError` at `0x180570d3d`
- `KERNEL32!GetLastError` at `0x180570e4d`
- `KERNEL32!GetLastError` at `0x180570eb5`
- `KERNEL32!GetLastError` at `0x180570ec6`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180570e05`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180570e05`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180570ddc`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180570ddc`
- `DEVOBJ!DevObjGetClassDevs` at `0x180570d33`
- `DEVOBJ!DevObjGetClassDevs` at `0x180570d33`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180570ee4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180570ee4`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180570ca6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180570ca6`
- `OLE32!CoTaskMemFree` at `0x180570ef7`
- `OLE32!CoTaskMemFree` at `0x180570ef7`
- `OLE32!CLSIDFromString` at `0x180570c46`
- `OLE32!CLSIDFromString` at `0x180570c46`

## string_xrefs

- `0x180570c87`: `CLSIDFromString failed`
- `0x180570d04`: `DevObjCreateDeviceInfoList FAILED`

## pseudocode

```c
__int64 __fastcall CLocalDevice::IsDevicePresent(CLocalDevice *this, int *a2)
{
  int DeviceSetupClassGuid; // ebx
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 DeviceInfoList; // r14
  signed int LastError; // eax
  signed int v11; // eax
  unsigned int v12; // eax
  unsigned int i; // esi
  int DeviceInstanceId; // eax
  unsigned __int16 *v15; // rax
  int v16; // edx
  int v17; // ecx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v19; // eax
  __int64 v20; // [rsp+28h] [rbp-D8h]
  LPCOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v23[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[1022]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v25; // [rsp+47Eh] [rbp+37Eh]

  lpsz = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  DeviceSetupClassGuid = CLocalDevice::GetDeviceSetupClassGuid(this, (unsigned __int16 **)&lpsz);
  if ( DeviceSetupClassGuid >= 0 )
  {
    pclsid = 0;
    DeviceSetupClassGuid = CLSIDFromString(lpsz, &pclsid);
    if ( DeviceSetupClassGuid >= 0 )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      if ( DeviceInfoList != -1 )
        goto LABEL_25;
      LastError = GetLastError();
      DeviceSetupClassGuid = LastError;
      if ( LastError > 0 )
        DeviceSetupClassGuid = (unsigned __int16)LastError | 0x80070000;
      if ( DeviceSetupClassGuid >= 0 )
      {
LABEL_25:
        if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &pclsid, 0, 2, 0, 0) )
          goto LABEL_30;
        v11 = GetLastError();
        DeviceSetupClassGuid = v11;
        if ( v11 > 0 )
          DeviceSetupClassGuid = (unsigned __int16)v11 | 0x80070000;
        if ( DeviceSetupClassGuid >= 0 )
        {
LABEL_30:
          for ( i = 0; ; ++i )
          {
            memset(v23, 0, sizeof(v23));
            LODWORD(v23[0]) = 48;
            if ( !(unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, i, v23) )
              break;
            DeviceInstanceId = DevObjGetDeviceInstanceId(DeviceInfoList, v23, v24, 511, 0);
            v25 = 0;
            if ( !DeviceInstanceId )
            {
              DeviceSetupClassGuid = GetLastError();
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  54,
                  WPP_714a6d298d2233154907540e19009056_Traceguids,
                  CurrentThreadActivityIdPrefix,
                  DeviceSetupClassGuid);
              }
              if ( DeviceSetupClassGuid > 0 )
                DeviceSetupClassGuid = (unsigned __int16)DeviceSetupClassGuid | 0x80070000;
              if ( DeviceSetupClassGuid >= 0 )
                DeviceSetupClassGuid = -2147467259;
              goto LABEL_52;
            }
            v15 = (unsigned __int16 *)v24;
            do
            {
              v16 = *(unsigned __int16 *)((char *)v15 + *((_QWORD *)this + 9) - (_QWORD)v24);
              v17 = *v15 - v16;
              if ( v17 )
                break;
              ++v15;
            }
            while ( v16 );
            if ( !v17 )
            {
              *a2 = 1;
              goto LABEL_52;
            }
          }
          if ( GetLastError() == 259 )
          {
            DeviceSetupClassGuid = 0;
          }
          else
          {
            v19 = GetLastError();
            DeviceSetupClassGuid = v19;
            if ( v19 > 0 )
              DeviceSetupClassGuid = (unsigned __int16)v19 | 0x80070000;
          }
        }
        else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
               && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v20) = DeviceSetupClassGuid;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
            v12,
            (__int64)"DevObjGetClassDevs FAILED",
            v20);
        }
LABEL_52:
        if ( DeviceInfoList != -1 )
          DevObjDestroyDeviceInfoList(DeviceInfoList);
        goto LABEL_54;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 52;
        v8 = "DevObjCreateDeviceInfoList FAILED";
        goto LABEL_8;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 51;
      v8 = "CLSIDFromString failed";
      goto LABEL_8;
    }
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 50;
    v8 = "Failed to get device class GUID";
LABEL_8:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
      v6,
      (__int64)v8,
      DeviceSetupClassGuid);
  }
LABEL_54:
  if ( lpsz )
    CoTaskMemFree((LPVOID)lpsz);
  return (unsigned int)DeviceSetupClassGuid;
}

```

## disassembly

```asm
0x180570b70  mov     [rsp-8+arg_10], rbx
0x180570b75  push    rbp
0x180570b76  push    rsi
0x180570b77  push    rdi
0x180570b78  push    r14
0x180570b7a  push    r15
0x180570b7c  lea     rbp, [rsp-390h]
0x180570b84  sub     rsp, 490h
0x180570b8b  mov     rax, cs:__security_cookie
0x180570b92  xor     rax, rsp
0x180570b95  mov     [rbp+3B0h+var_30], rax
0x180570b9c  mov     [rsp+4B0h+lpsz], 0
0x180570ba5  mov     rdi, rdx
0x180570ba8  mov     r15, rcx
0x180570bab  test    rdx, rdx
0x180570bae  jnz     short loc_180570BBA
0x180570bb0  mov     eax, 80004003h
0x180570bb5  jmp     loc_180570EFF
0x180570bba  mov     dword ptr [rdx], 0
0x180570bc0  lea     rdx, [rsp+4B0h+lpsz]; unsigned __int16 **
0x180570bc5  call    ?GetDeviceSetupClassGuid@CLocalDevice@@UEAAJPEAPEAG@Z; CLocalDevice::GetDeviceSetupClassGuid(ushort * *)
0x180570bca  mov     ebx, eax
0x180570bcc  test    eax, eax
0x180570bce  jns     short loc_180570C34
0x180570bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180570bd7  lea     rax, WPP_GLOBAL_Control
0x180570bde  cmp     rcx, rax
0x180570be1  jz      loc_180570EEA
0x180570be7  test    byte ptr [rcx+1Ch], 8
0x180570beb  jz      loc_180570EEA
0x180570bf1  cmp     byte ptr [rcx+19h], 2
0x180570bf5  jb      loc_180570EEA
0x180570bfb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570c00  mov     edx, 32h ; '2'
0x180570c05  lea     rcx, aFailedToGetDev_4; "Failed to get device class GUID"
0x180570c0c  mov     dword ptr [rsp+4B0h+var_488], ebx
0x180570c10  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x180570c17  mov     [rsp+4B0h+var_490], rcx
0x180570c1c  mov     r9d, eax
0x180570c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180570c26  mov     rcx, [rcx+10h]
0x180570c2a  call    WPP_SF_DsD
0x180570c2f  jmp     loc_180570EEA
0x180570c34  mov     rcx, [rsp+4B0h+lpsz]; lpsz
0x180570c39  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x180570c3e  xorps   xmm0, xmm0
0x180570c41  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x180570c46  call    cs:__imp_CLSIDFromString
0x180570c4c  mov     ebx, eax
0x180570c4e  test    eax, eax
0x180570c50  jns     short loc_180570C93
0x180570c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180570c59  lea     rax, WPP_GLOBAL_Control
0x180570c60  cmp     rcx, rax
0x180570c63  jz      loc_180570EEA
0x180570c69  test    byte ptr [rcx+1Ch], 8
0x180570c6d  jz      loc_180570EEA
0x180570c73  cmp     byte ptr [rcx+19h], 2
0x180570c77  jb      loc_180570EEA
0x180570c7d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570c82  mov     edx, 33h ; '3'
0x180570c87  lea     rcx, aClsidfromstrin_0; "CLSIDFromString failed"
0x180570c8e  jmp     loc_180570C0C
0x180570c93  xor     r9d, r9d
0x180570c96  mov     [rsp+4B0h+var_490], 0
0x180570c9f  xor     r8d, r8d
0x180570ca2  xor     edx, edx
0x180570ca4  xor     ecx, ecx
0x180570ca6  call    cs:__imp_DevObjCreateDeviceInfoList
0x180570cac  mov     r14, rax
0x180570caf  mov     esi, 80070000h
0x180570cb4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180570cb8  jnz     short loc_180570D10
0x180570cba  call    cs:__imp_GetLastError
0x180570cc0  mov     ebx, eax
0x180570cc2  test    eax, eax
0x180570cc4  jle     short loc_180570CCB
0x180570cc6  movzx   ebx, ax
0x180570cc9  or      ebx, esi
0x180570ccb  test    ebx, ebx
0x180570ccd  jns     short loc_180570D10
0x180570ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180570cd6  lea     rax, WPP_GLOBAL_Control
0x180570cdd  cmp     rcx, rax
0x180570ce0  jz      loc_180570EEA
0x180570ce6  test    byte ptr [rcx+1Ch], 8
0x180570cea  jz      loc_180570EEA
0x180570cf0  cmp     byte ptr [rcx+19h], 2
0x180570cf4  jb      loc_180570EEA
0x180570cfa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570cff  mov     edx, 34h ; '4'
0x180570d04  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x180570d0b  jmp     loc_180570C0C
0x180570d10  mov     [rsp+4B0h+var_488], 0
0x180570d19  lea     rdx, [rsp+4B0h+pclsid]
0x180570d1e  mov     r9d, 2
0x180570d24  mov     [rsp+4B0h+var_490], 0
0x180570d2d  xor     r8d, r8d
0x180570d30  mov     rcx, r14
0x180570d33  call    cs:__imp_DevObjGetClassDevs
0x180570d39  test    eax, eax
0x180570d3b  jnz     short loc_180570DB6
0x180570d3d  call    cs:__imp_GetLastError
0x180570d43  mov     ebx, eax
0x180570d45  test    eax, eax
0x180570d47  jle     short loc_180570D4E
0x180570d49  movzx   ebx, ax
0x180570d4c  or      ebx, esi
0x180570d4e  test    ebx, ebx
0x180570d50  jns     short loc_180570DB6
0x180570d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180570d59  lea     rax, WPP_GLOBAL_Control
0x180570d60  cmp     rcx, rax
0x180570d63  jz      loc_180570EDB
0x180570d69  test    byte ptr [rcx+1Ch], 8
0x180570d6d  jz      loc_180570EDB
0x180570d73  cmp     byte ptr [rcx+19h], 2
0x180570d77  jb      loc_180570EDB
0x180570d7d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570d82  lea     rcx, aDevobjgetclass_0; "DevObjGetClassDevs FAILED"
0x180570d89  mov     dword ptr [rsp+4B0h+var_488], ebx
0x180570d8d  mov     [rsp+4B0h+var_490], rcx
0x180570d92  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x180570d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180570da0  mov     edx, 35h ; '5'
0x180570da5  mov     r9d, eax
0x180570da8  mov     rcx, [rcx+10h]
0x180570dac  call    WPP_SF_DsD
0x180570db1  jmp     loc_180570EDB
0x180570db6  xor     esi, esi
0x180570db8  xorps   xmm0, xmm0
0x180570dbb  lea     r8, [rsp+4B0h+var_468]
0x180570dc0  movups  [rsp+4B0h+var_468], xmm0
0x180570dc5  mov     edx, esi
0x180570dc7  mov     dword ptr [rsp+4B0h+var_468], 30h ; '0'
0x180570dcf  mov     rcx, r14
0x180570dd2  movups  [rsp+4B0h+var_458], xmm0
0x180570dd7  movups  [rsp+4B0h+var_448], xmm0
0x180570ddc  call    cs:__imp_DevObjEnumDeviceInfo
0x180570de2  test    eax, eax
0x180570de4  jz      loc_180570EB5
0x180570dea  mov     r9d, 1FFh
0x180570df0  mov     [rsp+4B0h+var_490], 0
0x180570df9  lea     r8, [rbp+3B0h+var_430]
0x180570dfd  mov     rcx, r14
0x180570e00  lea     rdx, [rsp+4B0h+var_468]
0x180570e05  call    cs:__imp_DevObjGetDeviceInstanceId
0x180570e0b  xor     ecx, ecx
0x180570e0d  mov     [rbp+3B0h+var_32], cx
0x180570e14  test    eax, eax
0x180570e16  jz      short loc_180570E4D
0x180570e18  mov     r8, [r15+48h]
0x180570e1c  lea     rax, [rbp+3B0h+var_430]
0x180570e20  sub     r8, rax
0x180570e23  movzx   ecx, word ptr [rax]
0x180570e26  movzx   edx, word ptr [rax+r8]
0x180570e2b  sub     ecx, edx
0x180570e2d  jnz     short loc_180570E37
0x180570e2f  add     rax, 2
0x180570e33  test    edx, edx
0x180570e35  jnz     short loc_180570E23
0x180570e37  test    ecx, ecx
0x180570e39  jz      short loc_180570E42
0x180570e3b  inc     esi
0x180570e3d  jmp     loc_180570DB8
0x180570e42  mov     dword ptr [rdi], 1
0x180570e48  jmp     loc_180570EDB
0x180570e4d  call    cs:__imp_GetLastError
0x180570e53  mov     ebx, eax
0x180570e55  mov     rcx, cs:WPP_GLOBAL_Control
0x180570e5c  lea     rax, WPP_GLOBAL_Control
0x180570e63  cmp     rcx, rax
0x180570e66  jz      short loc_180570E9C
0x180570e68  test    byte ptr [rcx+1Ch], 8
0x180570e6c  jz      short loc_180570E9C
0x180570e6e  cmp     byte ptr [rcx+19h], 2
0x180570e72  jb      short loc_180570E9C
0x180570e74  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180570e80  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x180570e87  mov     edx, 36h ; '6'
0x180570e8c  mov     dword ptr [rsp+4B0h+var_490], ebx
0x180570e90  mov     r9d, eax
0x180570e93  mov     rcx, [rcx+10h]
0x180570e97  call    WPP_SF_Dd
0x180570e9c  test    ebx, ebx
0x180570e9e  jle     short loc_180570EA9
0x180570ea0  movzx   ebx, bx
0x180570ea3  or      ebx, 80070000h
0x180570ea9  test    ebx, ebx
0x180570eab  mov     eax, 80004005h
0x180570eb0  cmovns  ebx, eax
0x180570eb3  jmp     short loc_180570EDB
0x180570eb5  call    cs:__imp_GetLastError
0x180570ebb  cmp     eax, 103h
0x180570ec0  jnz     short loc_180570EC6
0x180570ec2  xor     ebx, ebx
0x180570ec4  jmp     short loc_180570EDB
0x180570ec6  call    cs:__imp_GetLastError
0x180570ecc  mov     ebx, eax
0x180570ece  test    eax, eax
0x180570ed0  jle     short loc_180570EDB
0x180570ed2  movzx   ebx, ax
0x180570ed5  or      ebx, 80070000h
0x180570edb  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180570edf  jz      short loc_180570EEA
0x180570ee1  mov     rcx, r14
0x180570ee4  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180570eea  cmp     [rsp+4B0h+lpsz], 0
0x180570ef0  jz      short loc_180570EFD
0x180570ef2  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180570ef7  call    cs:__imp_CoTaskMemFree
0x180570efd  mov     eax, ebx
0x180570eff  mov     rcx, [rbp+3B0h+var_30]
0x180570f06  xor     rcx, rsp; StackCookie
0x180570f09  call    __security_check_cookie
0x180570f0e  mov     rbx, [rsp+4B0h+arg_10]
0x180570f16  add     rsp, 490h
0x180570f1d  pop     r15
0x180570f1f  pop     r14
0x180570f21  pop     rdi
0x180570f22  pop     rsi
0x180570f23  pop     rbp
0x180570f24  retn
```
