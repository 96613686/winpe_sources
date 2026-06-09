# CLocalDevice::GetDeviceProperty2(_DEVPROPKEY const *,ulong *,uchar * *,ulong *)

- ea: `0x18056f030`
- end: `0x18056f412`
- name: `?GetDeviceProperty2@CLocalDevice@@QEAAJPEBU_DEVPROPKEY@@PEAKPEAPEAE1@Z`
- size: `994`
- prototype: `__int64 __fastcall(CLocalDevice *__hidden this, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18056e220`

## callees

- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18056f030`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056f090`
- `KERNEL32!GetLastError` at `0x18056f143`
- `KERNEL32!GetLastError` at `0x18056f1db`
- `KERNEL32!GetLastError` at `0x18056f242`
- `KERNEL32!GetLastError` at `0x18056f361`
- `KERNEL32!GetLastError` at `0x18056f090`
- `KERNEL32!GetLastError` at `0x18056f143`
- `KERNEL32!GetLastError` at `0x18056f1db`
- `KERNEL32!GetLastError` at `0x18056f242`
- `KERNEL32!GetLastError` at `0x18056f361`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18056f1d1`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18056f357`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18056f1d1`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18056f357`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056f3ec`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056f3ec`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18056f139`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18056f139`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056f081`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056f081`
- `OLE32!CoTaskMemFree` at `0x18056f3d0`
- `OLE32!CoTaskMemFree` at `0x18056f3d0`
- `OLE32!CoTaskMemAlloc` at `0x18056f2c4`
- `OLE32!CoTaskMemAlloc` at `0x18056f2c4`

## string_xrefs

- `0x18056f290`: `DevObjGetDeviceRegistryProperty FAILED`
- `0x18056f0d9`: `DevObjCreateDeviceInfoList FAILED`
- `0x18056f191`: `DevObjOpenDeviceInfo FAILED`

## pseudocode

```c
__int64 __fastcall CLocalDevice::GetDeviceProperty2(
        CLocalDevice *this,
        const struct _DEVPROPKEY *a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  __int64 DeviceInfoList; // rsi
  signed int LastError; // eax
  signed int v10; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v12; // rdx
  signed int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  signed int v17; // eax
  unsigned int v18; // eax
  signed int v19; // eax
  unsigned __int8 *v20; // rdi
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  __int64 v25; // [rsp+28h] [rbp-58h]
  __int64 v26; // [rsp+28h] [rbp-58h]
  SIZE_T cb; // [rsp+40h] [rbp-40h] BYREF
  _OWORD v28[3]; // [rsp+48h] [rbp-38h] BYREF

  cb = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList FAILED",
          v10);
      }
      return (unsigned int)v10;
    }
  }
  v12 = *((_QWORD *)this + 9);
  memset(v28, 0, sizeof(v28));
  LODWORD(v28[0]) = 48;
  if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, v12, 0, 0, v28) )
    goto LABEL_21;
  v13 = GetLastError();
  v10 = v13;
  if ( v13 > 0 )
    v10 = (unsigned __int16)v13 | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_21:
    if ( (unsigned int)DevObjGetDeviceProperty(
                         DeviceInfoList,
                         v28,
                         &DEVPKEY_Device_ContainerId,
                         (char *)&cb + 4,
                         0,
                         0,
                         &cb,
                         0) )
      goto LABEL_26;
    v17 = GetLastError();
    v10 = v17;
    if ( v17 == 122 )
      goto LABEL_26;
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_26:
      v18 = cb;
      if ( !(_DWORD)cb )
      {
        v19 = GetLastError();
        v10 = v19;
        if ( v19 > 0 )
          v10 = (unsigned __int16)v19 | 0x80070000;
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpWppGetCurrentThreadActivityIdPrefix();
            v15 = 25;
            v16 = "DevObjGetDeviceRegistryProperty FAILED";
            goto LABEL_34;
          }
          goto LABEL_52;
        }
        v18 = cb;
      }
      v20 = (unsigned __int8 *)CoTaskMemAlloc(v18);
      if ( v20 )
      {
        if ( (unsigned int)DevObjGetDeviceProperty(DeviceInfoList, v28, &DEVPKEY_Device_ContainerId, a3, v20, cb, 0, 0) )
          goto LABEL_51;
        v22 = GetLastError();
        v10 = v22;
        if ( v22 > 0 )
          v10 = (unsigned __int16)v22 | 0x80070000;
        if ( v10 >= 0 )
        {
LABEL_51:
          v10 = 0;
          *a5 = cb;
          *a4 = v20;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(v26) = v10;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
              v23,
              (__int64)"DevObjGetDeviceProperty FAILED",
              v26);
          }
          CoTaskMemFree(v20);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
            v21,
            (__int64)"PBYTE");
        }
        v10 = -2147024882;
      }
      goto LABEL_52;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 24;
      v16 = "DevObjGetDeviceProperty FAILED";
      goto LABEL_34;
    }
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 23;
    v16 = "DevObjOpenDeviceInfo FAILED";
LABEL_34:
    LODWORD(v25) = v10;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
      v14,
      (__int64)v16,
      v25);
  }
LABEL_52:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18056f030  push    rbp
0x18056f032  push    rbx
0x18056f033  push    rsi
0x18056f034  push    rdi
0x18056f035  push    r12
0x18056f037  push    r14
0x18056f039  push    r15
0x18056f03b  mov     rbp, rsp
0x18056f03e  sub     rsp, 80h
0x18056f045  mov     rax, cs:__security_cookie
0x18056f04c  xor     rax, rsp
0x18056f04f  mov     [rbp+var_8], rax
0x18056f053  mov     r15, [rbp+arg_20]
0x18056f057  mov     r14, r9
0x18056f05a  mov     r12, r8
0x18056f05d  mov     dword ptr [rbp+cb], 0
0x18056f064  mov     rdi, rcx
0x18056f067  mov     dword ptr [rbp+cb+4], 0
0x18056f06e  xor     r9d, r9d
0x18056f071  mov     [rsp+80h+var_60], 0
0x18056f07a  xor     r8d, r8d
0x18056f07d  xor     ecx, ecx
0x18056f07f  xor     edx, edx
0x18056f081  call    cs:__imp_DevObjCreateDeviceInfoList
0x18056f087  mov     rsi, rax
0x18056f08a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18056f08e  jnz     short loc_18056F10D
0x18056f090  call    cs:__imp_GetLastError
0x18056f096  mov     ebx, eax
0x18056f098  test    eax, eax
0x18056f09a  jle     short loc_18056F0A5
0x18056f09c  movzx   ebx, ax
0x18056f09f  or      ebx, 80070000h
0x18056f0a5  test    ebx, ebx
0x18056f0a7  jns     short loc_18056F10D
0x18056f0a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f0b0  lea     rax, WPP_GLOBAL_Control
0x18056f0b7  cmp     rcx, rax
0x18056f0ba  jz      loc_18056F3F2
0x18056f0c0  test    byte ptr [rcx+1Ch], 8
0x18056f0c4  jz      loc_18056F3F2
0x18056f0ca  cmp     byte ptr [rcx+19h], 2
0x18056f0ce  jb      loc_18056F3F2
0x18056f0d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f0d9  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x18056f0e0  mov     dword ptr [rsp+80h+var_58], ebx
0x18056f0e4  mov     [rsp+80h+var_60], rcx
0x18056f0e9  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f0f7  mov     edx, 16h
0x18056f0fc  mov     r9d, eax
0x18056f0ff  mov     rcx, [rcx+10h]
0x18056f103  call    WPP_SF_DsD
0x18056f108  jmp     loc_18056F3F2
0x18056f10d  mov     rdx, [rdi+48h]
0x18056f111  lea     rax, [rbp+var_38]
0x18056f115  xorps   xmm0, xmm0
0x18056f118  mov     [rsp+80h+var_60], rax
0x18056f11d  movups  [rbp+var_38], xmm0
0x18056f121  xor     r9d, r9d
0x18056f124  mov     dword ptr [rbp+var_38], 30h ; '0'
0x18056f12b  xor     r8d, r8d
0x18056f12e  mov     rcx, rsi
0x18056f131  movups  [rbp+var_28], xmm0
0x18056f135  movups  [rbp+var_18], xmm0
0x18056f139  call    cs:__imp_DevObjOpenDeviceInfo
0x18056f13f  test    eax, eax
0x18056f141  jnz     short loc_18056F19D
0x18056f143  call    cs:__imp_GetLastError
0x18056f149  mov     ebx, eax
0x18056f14b  test    eax, eax
0x18056f14d  jle     short loc_18056F158
0x18056f14f  movzx   ebx, ax
0x18056f152  or      ebx, 80070000h
0x18056f158  test    ebx, ebx
0x18056f15a  jns     short loc_18056F19D
0x18056f15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f163  lea     rax, WPP_GLOBAL_Control
0x18056f16a  cmp     rcx, rax
0x18056f16d  jz      loc_18056F3E3
0x18056f173  test    byte ptr [rcx+1Ch], 8
0x18056f177  jz      loc_18056F3E3
0x18056f17d  cmp     byte ptr [rcx+19h], 2
0x18056f181  jb      loc_18056F3E3
0x18056f187  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f18c  mov     edx, 17h
0x18056f191  lea     rcx, aDevobjopendevi_1; "DevObjOpenDeviceInfo FAILED"
0x18056f198  jmp     loc_18056F297
0x18056f19d  mov     [rsp+80h+var_48], 0
0x18056f1a5  lea     rax, [rbp+cb]
0x18056f1a9  mov     [rsp+80h+var_50], rax
0x18056f1ae  lea     r9, [rbp+cb+4]
0x18056f1b2  mov     dword ptr [rsp+80h+var_58], 0
0x18056f1ba  lea     r8, DEVPKEY_Device_ContainerId
0x18056f1c1  lea     rdx, [rbp+var_38]
0x18056f1c5  mov     [rsp+80h+var_60], 0
0x18056f1ce  mov     rcx, rsi
0x18056f1d1  call    cs:__imp_DevObjGetDeviceProperty
0x18056f1d7  test    eax, eax
0x18056f1d9  jnz     short loc_18056F237
0x18056f1db  call    cs:__imp_GetLastError
0x18056f1e1  mov     ebx, eax
0x18056f1e3  cmp     eax, 7Ah ; 'z'
0x18056f1e6  jz      short loc_18056F237
0x18056f1e8  test    eax, eax
0x18056f1ea  jle     short loc_18056F1F5
0x18056f1ec  movzx   ebx, ax
0x18056f1ef  or      ebx, 80070000h
0x18056f1f5  test    ebx, ebx
0x18056f1f7  jns     short loc_18056F237
0x18056f1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f200  lea     rax, WPP_GLOBAL_Control
0x18056f207  cmp     rcx, rax
0x18056f20a  jz      loc_18056F3E3
0x18056f210  test    byte ptr [rcx+1Ch], 8
0x18056f214  jz      loc_18056F3E3
0x18056f21a  cmp     byte ptr [rcx+19h], 2
0x18056f21e  jb      loc_18056F3E3
0x18056f224  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f229  mov     edx, 18h
0x18056f22e  lea     rcx, aDevobjgetdevic_1; "DevObjGetDeviceProperty FAILED"
0x18056f235  jmp     short loc_18056F297
0x18056f237  mov     eax, dword ptr [rbp+cb]
0x18056f23a  test    eax, eax
0x18056f23c  jnz     loc_18056F2C2
0x18056f242  call    cs:__imp_GetLastError
0x18056f248  mov     ebx, eax
0x18056f24a  test    eax, eax
0x18056f24c  jle     short loc_18056F257
0x18056f24e  movzx   ebx, ax
0x18056f251  or      ebx, 80070000h
0x18056f257  test    ebx, ebx
0x18056f259  jns     short loc_18056F2BF
0x18056f25b  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f262  lea     rax, WPP_GLOBAL_Control
0x18056f269  cmp     rcx, rax
0x18056f26c  jz      loc_18056F3E3
0x18056f272  test    byte ptr [rcx+1Ch], 8
0x18056f276  jz      loc_18056F3E3
0x18056f27c  cmp     byte ptr [rcx+19h], 2
0x18056f280  jb      loc_18056F3E3
0x18056f286  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f28b  mov     edx, 19h
0x18056f290  lea     rcx, aDevobjgetdevic; "DevObjGetDeviceRegistryProperty FAILED"
0x18056f297  mov     dword ptr [rsp+80h+var_58], ebx
0x18056f29b  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f2a2  mov     [rsp+80h+var_60], rcx
0x18056f2a7  mov     r9d, eax
0x18056f2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f2b1  mov     rcx, [rcx+10h]
0x18056f2b5  call    WPP_SF_DsD
0x18056f2ba  jmp     loc_18056F3E3
0x18056f2bf  mov     eax, dword ptr [rbp+cb]
0x18056f2c2  mov     ecx, eax; cb
0x18056f2c4  call    cs:__imp_CoTaskMemAlloc
0x18056f2ca  mov     rdi, rax
0x18056f2cd  test    rax, rax
0x18056f2d0  jnz     short loc_18056F329
0x18056f2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f2d9  lea     rax, WPP_GLOBAL_Control
0x18056f2e0  cmp     rcx, rax
0x18056f2e3  jz      short loc_18056F31F
0x18056f2e5  test    byte ptr [rcx+1Ch], 8
0x18056f2e9  jz      short loc_18056F31F
0x18056f2eb  cmp     byte ptr [rcx+19h], 2
0x18056f2ef  jb      short loc_18056F31F
0x18056f2f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f2f6  lea     rcx, aPbyte; "PBYTE"
0x18056f2fd  mov     r9d, eax
0x18056f300  mov     [rsp+80h+var_60], rcx
0x18056f305  lea     edx, [rdi+1Ah]
0x18056f308  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f30f  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f316  mov     rcx, [rcx+10h]
0x18056f31a  call    WPP_SF_Ds
0x18056f31f  mov     ebx, 8007000Eh
0x18056f324  jmp     loc_18056F3E3
0x18056f329  mov     eax, dword ptr [rbp+cb]
0x18056f32c  lea     r8, DEVPKEY_Device_ContainerId
0x18056f333  mov     [rsp+80h+var_48], 0
0x18056f33b  lea     rdx, [rbp+var_38]
0x18056f33f  mov     [rsp+80h+var_50], 0
0x18056f348  mov     r9, r12
0x18056f34b  mov     dword ptr [rsp+80h+var_58], eax
0x18056f34f  mov     rcx, rsi
0x18056f352  mov     [rsp+80h+var_60], rdi
0x18056f357  call    cs:__imp_DevObjGetDeviceProperty
0x18056f35d  test    eax, eax
0x18056f35f  jnz     short loc_18056F3D8
0x18056f361  call    cs:__imp_GetLastError
0x18056f367  mov     ebx, eax
0x18056f369  test    eax, eax
0x18056f36b  jle     short loc_18056F376
0x18056f36d  movzx   ebx, ax
0x18056f370  or      ebx, 80070000h
0x18056f376  test    ebx, ebx
0x18056f378  jns     short loc_18056F3D8
0x18056f37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f381  lea     rax, WPP_GLOBAL_Control
0x18056f388  cmp     rcx, rax
0x18056f38b  jz      short loc_18056F3CD
0x18056f38d  test    byte ptr [rcx+1Ch], 8
0x18056f391  jz      short loc_18056F3CD
0x18056f393  cmp     byte ptr [rcx+19h], 2
0x18056f397  jb      short loc_18056F3CD
0x18056f399  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f39e  lea     rcx, aDevobjgetdevic_1; "DevObjGetDeviceProperty FAILED"
0x18056f3a5  mov     dword ptr [rsp+80h+var_58], ebx
0x18056f3a9  mov     [rsp+80h+var_60], rcx
0x18056f3ae  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f3bc  mov     edx, 1Bh
0x18056f3c1  mov     r9d, eax
0x18056f3c4  mov     rcx, [rcx+10h]
0x18056f3c8  call    WPP_SF_DsD
0x18056f3cd  mov     rcx, rdi; pv
0x18056f3d0  call    cs:__imp_CoTaskMemFree
0x18056f3d6  jmp     short loc_18056F3E3
0x18056f3d8  mov     eax, dword ptr [rbp+cb]
0x18056f3db  xor     ebx, ebx
0x18056f3dd  mov     [r15], eax
0x18056f3e0  mov     [r14], rdi
0x18056f3e3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18056f3e7  jz      short loc_18056F3F2
0x18056f3e9  mov     rcx, rsi
0x18056f3ec  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18056f3f2  mov     eax, ebx
0x18056f3f4  mov     rcx, [rbp+var_8]
0x18056f3f8  xor     rcx, rsp; StackCookie
0x18056f3fb  call    __security_check_cookie
0x18056f400  add     rsp, 80h
0x18056f407  pop     r15
0x18056f409  pop     r14
0x18056f40b  pop     r12
0x18056f40d  pop     rdi
0x18056f40e  pop     rsi
0x18056f40f  pop     rbx
0x18056f410  pop     rbp
0x18056f411  retn
```
