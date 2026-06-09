# CLocalDevice::GetFileName(_GUID,ushort * *)

- ea: `0x18056f950`
- end: `0x18056fdd2`
- name: `?GetFileName@CLocalDevice@@UEAAJU_GUID@@PEAPEAG@Z`
- size: `1154`
- prototype: `__int64 __fastcall(CLocalDevice *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180039ce4`
- `0x18008a2c0`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18012966c`
- `0x18056f950`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056f99d`
- `KERNEL32!GetLastError` at `0x18056fa44`
- `KERNEL32!GetLastError` at `0x18056fafb`
- `KERNEL32!GetLastError` at `0x18056fb08`
- `KERNEL32!GetLastError` at `0x18056fb86`
- `KERNEL32!GetLastError` at `0x18056fb91`
- `KERNEL32!GetLastError` at `0x18056fc79`
- `KERNEL32!GetLastError` at `0x18056f99d`
- `KERNEL32!GetLastError` at `0x18056fa44`
- `KERNEL32!GetLastError` at `0x18056fafb`
- `KERNEL32!GetLastError` at `0x18056fb08`
- `KERNEL32!GetLastError` at `0x18056fb86`
- `KERNEL32!GetLastError` at `0x18056fb91`
- `KERNEL32!GetLastError` at `0x18056fc79`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18056fb80`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18056fc6f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18056fb80`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18056fc6f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18056faf1`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18056faf1`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056fa3a`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056fa3a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056fd86`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056fd86`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056f98e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056f98e`
- `OLE32!CoTaskMemFree` at `0x18056fda5`
- `OLE32!CoTaskMemFree` at `0x18056fda5`
- `OLE32!CoTaskMemAlloc` at `0x18056fce9`
- `OLE32!CoTaskMemAlloc` at `0x18056fce9`

## string_xrefs

- `0x18056fcc3`: `DevObjGetDeviceRegistryProperty FAILED`
- `0x18056fd6d`: `StringCbCopyW FAILED`
- `0x18056f9e6`: `DevObjCreateDeviceInfoList FAILED`

## pseudocode

```c
__int64 __fastcall CLocalDevice::GetFileName(CLocalDevice *this, struct _GUID *a2, unsigned __int16 **a3)
{
  __int64 DeviceInfoList; // r15
  signed int LastError; // eax
  signed int v8; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // rbp
  signed int v12; // eax
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  signed int v16; // eax
  signed int v17; // eax
  unsigned __int16 *v18; // rax
  unsigned int v19; // eax
  int v20; // edx
  signed int v21; // eax
  __int64 v22; // rax
  SIZE_T v23; // rdi
  unsigned __int16 *v24; // rax
  __int64 v26; // [rsp+28h] [rbp-70h]
  size_t Size; // [rsp+30h] [rbp-68h] BYREF
  _OWORD v28[2]; // [rsp+38h] [rbp-60h] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList FAILED",
          v8);
      }
      return (unsigned int)v8;
    }
  }
  v10 = 0;
  v11 = 0;
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, a2, *((_QWORD *)this + 9), 16, 0, 0) )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 29;
      v15 = "DevObjGetClassDevs FAILED";
      goto LABEL_17;
    }
  }
  memset(v28, 0, sizeof(v28));
  LODWORD(v28[0]) = 32;
  if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, a2, 0, v28) && GetLastError() != 259 )
  {
    v16 = GetLastError();
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 30;
      v15 = "DevObjEnumDeviceInterfaces FAILED";
      goto LABEL_17;
    }
  }
  LODWORD(Size) = 0;
  DevObjGetDeviceInterfaceDetail(DeviceInfoList, v28, 0, 0, &Size, 0);
  if ( GetLastError() != 122 )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 31;
      v15 = "DevObjGetDeviceInterfaceDetail FAILED";
      goto LABEL_17;
    }
  }
  v18 = (unsigned __int16 *)operator new((unsigned int)Size);
  v10 = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_41;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 32;
    goto LABEL_40;
  }
  *(_DWORD *)v18 = 8;
  if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v28, v18, (unsigned int)Size, 0, 0) )
    goto LABEL_50;
  v21 = GetLastError();
  v8 = v21;
  if ( v21 > 0 )
    v8 = (unsigned __int16)v21 | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_50:
    v22 = -1;
    do
      ++v22;
    while ( v10[v22 + 2] );
    v23 = (unsigned int)(2 * v22 + 2);
    v24 = (unsigned __int16 *)CoTaskMemAlloc(v23);
    v11 = v24;
    if ( v24 )
    {
      v8 = StringCbCopyW(v24, v23, v10 + 2);
      if ( v8 >= 0 )
      {
        *a3 = v11;
        goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 35;
      v15 = "StringCbCopyW FAILED";
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_41:
      v8 = -2147024882;
      goto LABEL_63;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 34;
LABEL_40:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
      v19,
      (__int64)"PBYTE");
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_63;
  }
  v13 = RdpWppGetCurrentThreadActivityIdPrefix();
  v14 = 33;
  v15 = "DevObjGetDeviceRegistryProperty FAILED";
LABEL_17:
  LODWORD(v26) = v8;
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v14,
    (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
    v13,
    (__int64)v15,
    v26);
LABEL_63:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  if ( v10 )
    operator delete(v10);
  if ( v8 && v11 )
    CoTaskMemFree(v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18056f950  mov     [rsp+arg_18], rbx
0x18056f955  push    rbp
0x18056f956  push    rsi
0x18056f957  push    rdi
0x18056f958  push    r12
0x18056f95a  push    r13
0x18056f95c  push    r14
0x18056f95e  push    r15
0x18056f960  sub     rsp, 60h
0x18056f964  mov     rax, cs:__security_cookie
0x18056f96b  xor     rax, rsp
0x18056f96e  mov     [rsp+98h+var_40], rax
0x18056f973  mov     r12, r8
0x18056f976  mov     r14, rdx
0x18056f979  mov     rdi, rcx
0x18056f97c  xor     r13d, r13d
0x18056f97f  xor     r8d, r8d
0x18056f982  mov     [rsp+98h+var_78], r13
0x18056f987  xor     edx, edx
0x18056f989  xor     ecx, ecx
0x18056f98b  xor     r9d, r9d
0x18056f98e  call    cs:__imp_DevObjCreateDeviceInfoList
0x18056f994  mov     r15, rax
0x18056f997  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18056f99b  jnz     short loc_18056FA1A
0x18056f99d  call    cs:__imp_GetLastError
0x18056f9a3  mov     ebx, eax
0x18056f9a5  test    eax, eax
0x18056f9a7  jle     short loc_18056F9B2
0x18056f9a9  movzx   ebx, ax
0x18056f9ac  or      ebx, 80070000h
0x18056f9b2  test    ebx, ebx
0x18056f9b4  jns     short loc_18056FA1A
0x18056f9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f9bd  lea     rax, WPP_GLOBAL_Control
0x18056f9c4  cmp     rcx, rax
0x18056f9c7  jz      loc_18056FDAB
0x18056f9cd  test    byte ptr [rcx+1Ch], 8
0x18056f9d1  jz      loc_18056FDAB
0x18056f9d7  cmp     byte ptr [rcx+19h], 2
0x18056f9db  jb      loc_18056FDAB
0x18056f9e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f9e6  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x18056f9ed  mov     dword ptr [rsp+98h+var_70], ebx
0x18056f9f1  mov     [rsp+98h+var_78], rcx
0x18056f9f6  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f9fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fa04  mov     edx, 1Ch
0x18056fa09  mov     r9d, eax
0x18056fa0c  mov     rcx, [rcx+10h]
0x18056fa10  call    WPP_SF_DsD
0x18056fa15  jmp     loc_18056FDAB
0x18056fa1a  mov     r8, [rdi+48h]
0x18056fa1e  mov     r9d, 10h
0x18056fa24  mov     [rsp+98h+var_70], r13
0x18056fa29  mov     rdx, r14
0x18056fa2c  mov     rcx, r15
0x18056fa2f  mov     [rsp+98h+var_78], r13
0x18056fa34  mov     rsi, r13
0x18056fa37  mov     rbp, r13
0x18056fa3a  call    cs:__imp_DevObjGetClassDevs
0x18056fa40  test    eax, eax
0x18056fa42  jnz     short loc_18056FAC2
0x18056fa44  call    cs:__imp_GetLastError
0x18056fa4a  mov     ebx, eax
0x18056fa4c  mov     edi, 80070000h
0x18056fa51  test    eax, eax
0x18056fa53  jle     short loc_18056FA5A
0x18056fa55  movzx   ebx, ax
0x18056fa58  or      ebx, edi
0x18056fa5a  test    ebx, ebx
0x18056fa5c  jns     short loc_18056FAC7
0x18056fa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fa65  lea     rax, WPP_GLOBAL_Control
0x18056fa6c  cmp     rcx, rax
0x18056fa6f  jz      loc_18056FD7D
0x18056fa75  test    byte ptr [rcx+1Ch], 8
0x18056fa79  jz      loc_18056FD7D
0x18056fa7f  cmp     byte ptr [rcx+19h], 2
0x18056fa83  jb      loc_18056FD7D
0x18056fa89  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fa8e  mov     edx, 1Dh
0x18056fa93  lea     rcx, aDevobjgetclass_0; "DevObjGetClassDevs FAILED"
0x18056fa9a  mov     dword ptr [rsp+98h+var_70], ebx
0x18056fa9e  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056faa5  mov     [rsp+98h+var_78], rcx
0x18056faaa  mov     r9d, eax
0x18056faad  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fab4  mov     rcx, [rcx+10h]
0x18056fab8  call    WPP_SF_DsD
0x18056fabd  jmp     loc_18056FD7D
0x18056fac2  mov     edi, 80070000h
0x18056fac7  xorps   xmm0, xmm0
0x18056faca  lea     rax, [rsp+98h+var_60]
0x18056facf  movups  [rsp+98h+var_60], xmm0
0x18056fad4  xor     r9d, r9d
0x18056fad7  mov     dword ptr [rsp+98h+var_60], 20h ; ' '
0x18056fadf  mov     r8, r14
0x18056fae2  mov     [rsp+98h+var_78], rax
0x18056fae7  xor     edx, edx
0x18056fae9  mov     rcx, r15
0x18056faec  movups  [rsp+98h+var_50], xmm0
0x18056faf1  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18056faf7  test    eax, eax
0x18056faf9  jnz     short loc_18056FB5E
0x18056fafb  call    cs:__imp_GetLastError
0x18056fb01  cmp     eax, 103h
0x18056fb06  jz      short loc_18056FB5E
0x18056fb08  call    cs:__imp_GetLastError
0x18056fb0e  mov     ebx, eax
0x18056fb10  test    eax, eax
0x18056fb12  jle     short loc_18056FB19
0x18056fb14  movzx   ebx, ax
0x18056fb17  or      ebx, edi
0x18056fb19  test    ebx, ebx
0x18056fb1b  jns     short loc_18056FB5E
0x18056fb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fb24  lea     rax, WPP_GLOBAL_Control
0x18056fb2b  cmp     rcx, rax
0x18056fb2e  jz      loc_18056FD7D
0x18056fb34  test    byte ptr [rcx+1Ch], 8
0x18056fb38  jz      loc_18056FD7D
0x18056fb3e  cmp     byte ptr [rcx+19h], 2
0x18056fb42  jb      loc_18056FD7D
0x18056fb48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fb4d  mov     edx, 1Eh
0x18056fb52  lea     rcx, aDevobjenumdevi; "DevObjEnumDeviceInterfaces FAILED"
0x18056fb59  jmp     loc_18056FA9A
0x18056fb5e  lea     rax, [rsp+98h+Size]
0x18056fb63  mov     [rsp+98h+var_70], r13
0x18056fb68  xor     r9d, r9d
0x18056fb6b  mov     [rsp+98h+var_78], rax
0x18056fb70  xor     r8d, r8d
0x18056fb73  mov     dword ptr [rsp+98h+Size], r13d
0x18056fb78  lea     rdx, [rsp+98h+var_60]
0x18056fb7d  mov     rcx, r15
0x18056fb80  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18056fb86  call    cs:__imp_GetLastError
0x18056fb8c  cmp     eax, 7Ah ; 'z'
0x18056fb8f  jz      short loc_18056FBE7
0x18056fb91  call    cs:__imp_GetLastError
0x18056fb97  mov     ebx, eax
0x18056fb99  test    eax, eax
0x18056fb9b  jle     short loc_18056FBA2
0x18056fb9d  movzx   ebx, ax
0x18056fba0  or      ebx, edi
0x18056fba2  test    ebx, ebx
0x18056fba4  jns     short loc_18056FBE7
0x18056fba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fbad  lea     rax, WPP_GLOBAL_Control
0x18056fbb4  cmp     rcx, rax
0x18056fbb7  jz      loc_18056FD7D
0x18056fbbd  test    byte ptr [rcx+1Ch], 8
0x18056fbc1  jz      loc_18056FD7D
0x18056fbc7  cmp     byte ptr [rcx+19h], 2
0x18056fbcb  jb      loc_18056FD7D
0x18056fbd1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fbd6  mov     edx, 1Fh
0x18056fbdb  lea     rcx, aDevobjgetdevic_2; "DevObjGetDeviceInterfaceDetail FAILED"
0x18056fbe2  jmp     loc_18056FA9A
0x18056fbe7  mov     ecx, dword ptr [rsp+98h+Size]; Size
0x18056fbeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18056fbf0  mov     rsi, rax
0x18056fbf3  test    rax, rax
0x18056fbf6  jnz     short loc_18056FC4F
0x18056fbf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fbff  lea     rax, WPP_GLOBAL_Control
0x18056fc06  cmp     rcx, rax
0x18056fc09  jz      short loc_18056FC45
0x18056fc0b  test    byte ptr [rcx+1Ch], 8
0x18056fc0f  jz      short loc_18056FC45
0x18056fc11  cmp     byte ptr [rcx+19h], 2
0x18056fc15  jb      short loc_18056FC45
0x18056fc17  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fc1c  lea     edx, [rsi+20h]
0x18056fc1f  lea     rcx, aPbyte; "PBYTE"
0x18056fc26  mov     r9d, eax
0x18056fc29  mov     [rsp+98h+var_78], rcx
0x18056fc2e  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056fc35  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fc3c  mov     rcx, [rcx+10h]
0x18056fc40  call    WPP_SF_Ds
0x18056fc45  mov     ebx, 8007000Eh
0x18056fc4a  jmp     loc_18056FD7D
0x18056fc4f  mov     dword ptr [rax], 8
0x18056fc55  lea     rdx, [rsp+98h+var_60]
0x18056fc5a  mov     r9d, dword ptr [rsp+98h+Size]
0x18056fc5f  mov     r8, rsi
0x18056fc62  mov     [rsp+98h+var_70], r13
0x18056fc67  mov     rcx, r15
0x18056fc6a  mov     [rsp+98h+var_78], r13
0x18056fc6f  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18056fc75  test    eax, eax
0x18056fc77  jnz     short loc_18056FCCF
0x18056fc79  call    cs:__imp_GetLastError
0x18056fc7f  mov     ebx, eax
0x18056fc81  test    eax, eax
0x18056fc83  jle     short loc_18056FC8A
0x18056fc85  movzx   ebx, ax
0x18056fc88  or      ebx, edi
0x18056fc8a  test    ebx, ebx
0x18056fc8c  jns     short loc_18056FCCF
0x18056fc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fc95  lea     rax, WPP_GLOBAL_Control
0x18056fc9c  cmp     rcx, rax
0x18056fc9f  jz      loc_18056FD7D
0x18056fca5  test    byte ptr [rcx+1Ch], 8
0x18056fca9  jz      loc_18056FD7D
0x18056fcaf  cmp     byte ptr [rcx+19h], 2
0x18056fcb3  jb      loc_18056FD7D
0x18056fcb9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fcbe  mov     edx, 21h ; '!'
0x18056fcc3  lea     rcx, aDevobjgetdevic; "DevObjGetDeviceRegistryProperty FAILED"
0x18056fcca  jmp     loc_18056FA9A
0x18056fccf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18056fcd3  inc     rax
0x18056fcd6  cmp     [rsi+rax*2+4], r13w
0x18056fcdc  jnz     short loc_18056FCD3
0x18056fcde  lea     eax, ds:2[rax*2]
0x18056fce5  mov     ecx, eax; cb
0x18056fce7  mov     edi, eax
0x18056fce9  call    cs:__imp_CoTaskMemAlloc
0x18056fcef  mov     rbp, rax
0x18056fcf2  test    rax, rax
0x18056fcf5  jnz     short loc_18056FD2F
0x18056fcf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fcfe  lea     rax, WPP_GLOBAL_Control
0x18056fd05  cmp     rcx, rax
0x18056fd08  jz      loc_18056FC45
0x18056fd0e  test    byte ptr [rcx+1Ch], 8
0x18056fd12  jz      loc_18056FC45
0x18056fd18  cmp     byte ptr [rcx+19h], 2
0x18056fd1c  jb      loc_18056FC45
0x18056fd22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fd27  lea     edx, [rbp+22h]
0x18056fd2a  jmp     loc_18056FC1F
0x18056fd2f  lea     r8, [rsi+4]; unsigned __int16 *
0x18056fd33  mov     rdx, rdi; unsigned __int64
0x18056fd36  mov     rcx, rbp; unsigned __int16 *
0x18056fd39  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18056fd3e  mov     ebx, eax
0x18056fd40  test    eax, eax
0x18056fd42  jns     short loc_18056FD79
0x18056fd44  mov     rcx, cs:WPP_GLOBAL_Control
0x18056fd4b  lea     rax, WPP_GLOBAL_Control
0x18056fd52  cmp     rcx, rax
0x18056fd55  jz      short loc_18056FD7D
0x18056fd57  test    byte ptr [rcx+1Ch], 8
0x18056fd5b  jz      short loc_18056FD7D
0x18056fd5d  cmp     byte ptr [rcx+19h], 2
0x18056fd61  jb      short loc_18056FD7D
0x18056fd63  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056fd68  mov     edx, 23h ; '#'
0x18056fd6d  lea     rcx, aStringcbcopywF; "StringCbCopyW FAILED"
0x18056fd74  jmp     loc_18056FA9A
0x18056fd79  mov     [r12], rbp
0x18056fd7d  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18056fd81  jz      short loc_18056FD8C
0x18056fd83  mov     rcx, r15
0x18056fd86  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18056fd8c  test    rsi, rsi
0x18056fd8f  jz      short loc_18056FD99
0x18056fd91  mov     rcx, rsi; Block
0x18056fd94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18056fd99  test    ebx, ebx
0x18056fd9b  jz      short loc_18056FDAB
0x18056fd9d  test    rbp, rbp
0x18056fda0  jz      short loc_18056FDAB
0x18056fda2  mov     rcx, rbp; pv
0x18056fda5  call    cs:__imp_CoTaskMemFree
0x18056fdab  mov     eax, ebx
0x18056fdad  mov     rcx, [rsp+98h+var_40]
0x18056fdb2  xor     rcx, rsp; StackCookie
0x18056fdb5  call    __security_check_cookie
0x18056fdba  mov     rbx, [rsp+98h+arg_18]
0x18056fdc2  add     rsp, 60h
0x18056fdc6  pop     r15
0x18056fdc8  pop     r14
0x18056fdca  pop     r13
0x18056fdcc  pop     r12
0x18056fdce  pop     rdi
0x18056fdcf  pop     rsi
0x18056fdd0  pop     rbp
0x18056fdd1  retn
```
