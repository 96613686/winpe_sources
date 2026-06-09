# CLocalDevice::GetDeviceProperty(ulong,ulong *,uchar * *,ulong *)

- ea: `0x18056f418`
- end: `0x18056f7e8`
- name: `?GetDeviceProperty@CLocalDevice@@QEAAJKPEAKPEAPEAE0@Z`
- size: `976`
- prototype: `__int64 __fastcall(CLocalDevice *__hidden this, unsigned int, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18056e190`
- `0x18056e700`
- `0x18056e870`
- `0x18056f7f0`
- `0x18056f8a0`
- `0x18056fe00`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18056f418`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056f478`
- `KERNEL32!GetLastError` at `0x18056f52b`
- `KERNEL32!GetLastError` at `0x18056f5bd`
- `KERNEL32!GetLastError` at `0x18056f734`
- `KERNEL32!GetLastError` at `0x18056f478`
- `KERNEL32!GetLastError` at `0x18056f52b`
- `KERNEL32!GetLastError` at `0x18056f5bd`
- `KERNEL32!GetLastError` at `0x18056f734`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056f7c0`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056f7c0`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18056f5ac`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18056f72a`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18056f5ac`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18056f72a`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18056f521`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18056f521`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056f469`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056f469`
- `OLE32!CoTaskMemFree` at `0x18056f7a3`
- `OLE32!CoTaskMemFree` at `0x18056f7a3`
- `OLE32!CoTaskMemAlloc` at `0x18056f6a3`
- `OLE32!CoTaskMemAlloc` at `0x18056f6a3`

## string_xrefs

- `0x18056f66f`: `DevObjGetDeviceRegistryProperty FAILED`
- `0x18056f771`: `DevObjGetDeviceRegistryProperty FAILED`
- `0x18056f4c1`: `DevObjCreateDeviceInfoList FAILED`
- `0x18056f579`: `DevObjOpenDeviceInfo FAILED`

## pseudocode

```c
__int64 __fastcall CLocalDevice::GetDeviceProperty(
        CLocalDevice *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  __int64 DeviceInfoList; // rsi
  signed int LastError; // eax
  signed int v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx
  signed int v14; // eax
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  unsigned int v18; // eax
  signed int v19; // eax
  unsigned int v20; // eax
  unsigned __int8 *v21; // rdi
  unsigned int v22; // eax
  signed int v23; // eax
  unsigned int v24; // eax
  SIZE_T cb; // [rsp+40h] [rbp-31h] BYREF
  _OWORD v27[3]; // [rsp+48h] [rbp-29h] BYREF

  LODWORD(cb) = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList FAILED",
          v11);
      }
      return (unsigned int)v11;
    }
  }
  v13 = *((_QWORD *)this + 9);
  memset(v27, 0, sizeof(v27));
  LODWORD(v27[0]) = 48;
  if ( !(unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, v13, 0, 0, v27) )
  {
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 17;
        v17 = "DevObjOpenDeviceInfo FAILED";
LABEL_30:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          v15,
          (__int64)v17,
          v11);
        goto LABEL_48;
      }
      goto LABEL_48;
    }
  }
  DevObjGetDeviceRegistryProperty(DeviceInfoList, v27, a2, 0, 0, 0, &cb);
  v18 = cb;
  if ( (_DWORD)cb )
  {
LABEL_32:
    v21 = (unsigned __int8 *)CoTaskMemAlloc(v18);
    if ( v21 )
    {
      if ( (unsigned int)DevObjGetDeviceRegistryProperty(DeviceInfoList, v27, a2, a3, v21, cb, 0) )
        goto LABEL_47;
      v23 = GetLastError();
      v11 = v23;
      if ( v23 > 0 )
        v11 = (unsigned __int16)v23 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_47:
        v11 = 0;
        *a5 = cb;
        *a4 = v21;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
            v24,
            (__int64)"DevObjGetDeviceRegistryProperty FAILED",
            v11);
        }
        CoTaskMemFree(v21);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          v22,
          (__int64)"PBYTE");
      }
      v11 = -2147024882;
    }
    goto LABEL_48;
  }
  v19 = GetLastError();
  v11 = v19;
  if ( v19 > 0 )
    v11 = (unsigned __int16)v19 | 0x80070000;
  if ( v11 == -2147024883 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_714a6d298d2233154907540e19009056_Traceguids,
        v20,
        -2147024883);
    }
    goto LABEL_48;
  }
  if ( v11 >= 0 )
  {
    v18 = cb;
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 19;
    v17 = "DevObjGetDeviceRegistryProperty FAILED";
    goto LABEL_30;
  }
LABEL_48:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18056f418  push    rbp
0x18056f41a  push    rbx
0x18056f41b  push    rsi
0x18056f41c  push    rdi
0x18056f41d  push    r12
0x18056f41f  push    r13
0x18056f421  push    r14
0x18056f423  push    r15
0x18056f425  lea     rbp, [rsp-17h]
0x18056f42a  sub     rsp, 88h
0x18056f431  mov     rax, cs:__security_cookie
0x18056f438  xor     rax, rsp
0x18056f43b  mov     [rbp+4Fh+var_48], rax
0x18056f43f  mov     r12, [rbp+4Fh+arg_20]
0x18056f443  mov     r15, r9
0x18056f446  mov     r13, r8
0x18056f449  mov     dword ptr [rbp+4Fh+cb], 0
0x18056f450  mov     r14d, edx
0x18056f453  mov     [rsp+0C0h+var_A0], 0
0x18056f45c  mov     rdi, rcx
0x18056f45f  xor     r9d, r9d
0x18056f462  xor     r8d, r8d
0x18056f465  xor     edx, edx
0x18056f467  xor     ecx, ecx
0x18056f469  call    cs:__imp_DevObjCreateDeviceInfoList
0x18056f46f  mov     rsi, rax
0x18056f472  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18056f476  jnz     short loc_18056F4F5
0x18056f478  call    cs:__imp_GetLastError
0x18056f47e  mov     ebx, eax
0x18056f480  test    eax, eax
0x18056f482  jle     short loc_18056F48D
0x18056f484  movzx   ebx, ax
0x18056f487  or      ebx, 80070000h
0x18056f48d  test    ebx, ebx
0x18056f48f  jns     short loc_18056F4F5
0x18056f491  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f498  lea     rax, WPP_GLOBAL_Control
0x18056f49f  cmp     rcx, rax
0x18056f4a2  jz      loc_18056F7C6
0x18056f4a8  test    byte ptr [rcx+1Ch], 8
0x18056f4ac  jz      loc_18056F7C6
0x18056f4b2  cmp     byte ptr [rcx+19h], 2
0x18056f4b6  jb      loc_18056F7C6
0x18056f4bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f4c1  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x18056f4c8  mov     [rsp+0C0h+var_98], ebx
0x18056f4cc  mov     [rsp+0C0h+var_A0], rcx
0x18056f4d1  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f4d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f4df  mov     edx, 10h
0x18056f4e4  mov     r9d, eax
0x18056f4e7  mov     rcx, [rcx+10h]
0x18056f4eb  call    WPP_SF_DsD
0x18056f4f0  jmp     loc_18056F7C6
0x18056f4f5  mov     rdx, [rdi+48h]
0x18056f4f9  lea     rax, [rbp+4Fh+var_78]
0x18056f4fd  xorps   xmm0, xmm0
0x18056f500  mov     [rsp+0C0h+var_A0], rax
0x18056f505  movups  [rbp+4Fh+var_78], xmm0
0x18056f509  xor     r9d, r9d
0x18056f50c  mov     dword ptr [rbp+4Fh+var_78], 30h ; '0'
0x18056f513  xor     r8d, r8d
0x18056f516  mov     rcx, rsi
0x18056f519  movups  [rbp+4Fh+var_68], xmm0
0x18056f51d  movups  [rbp+4Fh+var_58], xmm0
0x18056f521  call    cs:__imp_DevObjOpenDeviceInfo
0x18056f527  test    eax, eax
0x18056f529  jnz     short loc_18056F585
0x18056f52b  call    cs:__imp_GetLastError
0x18056f531  mov     ebx, eax
0x18056f533  test    eax, eax
0x18056f535  jle     short loc_18056F540
0x18056f537  movzx   ebx, ax
0x18056f53a  or      ebx, 80070000h
0x18056f540  test    ebx, ebx
0x18056f542  jns     short loc_18056F585
0x18056f544  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f54b  lea     rax, WPP_GLOBAL_Control
0x18056f552  cmp     rcx, rax
0x18056f555  jz      loc_18056F7B7
0x18056f55b  test    byte ptr [rcx+1Ch], 8
0x18056f55f  jz      loc_18056F7B7
0x18056f565  cmp     byte ptr [rcx+19h], 2
0x18056f569  jb      loc_18056F7B7
0x18056f56f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f574  mov     edx, 11h
0x18056f579  lea     rcx, aDevobjopendevi_1; "DevObjOpenDeviceInfo FAILED"
0x18056f580  jmp     loc_18056F676
0x18056f585  lea     rax, [rbp+4Fh+cb]
0x18056f589  xor     r9d, r9d
0x18056f58c  mov     [rsp+0C0h+var_90], rax
0x18056f591  lea     rdx, [rbp+4Fh+var_78]
0x18056f595  mov     [rsp+0C0h+var_98], 0
0x18056f59d  mov     r8d, r14d
0x18056f5a0  mov     rcx, rsi
0x18056f5a3  mov     [rsp+0C0h+var_A0], 0
0x18056f5ac  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18056f5b2  mov     eax, dword ptr [rbp+4Fh+cb]
0x18056f5b5  test    eax, eax
0x18056f5b7  jnz     loc_18056F6A1
0x18056f5bd  call    cs:__imp_GetLastError
0x18056f5c3  mov     ebx, eax
0x18056f5c5  test    eax, eax
0x18056f5c7  jle     short loc_18056F5D2
0x18056f5c9  movzx   ebx, ax
0x18056f5cc  or      ebx, 80070000h
0x18056f5d2  cmp     ebx, 8007000Dh
0x18056f5d8  jnz     short loc_18056F636
0x18056f5da  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f5e1  lea     rax, WPP_GLOBAL_Control
0x18056f5e8  cmp     rcx, rax
0x18056f5eb  jz      loc_18056F7B7
0x18056f5f1  test    byte ptr [rcx+1Ch], 80h
0x18056f5f5  jz      loc_18056F7B7
0x18056f5fb  cmp     byte ptr [rcx+19h], 3
0x18056f5ff  jb      loc_18056F7B7
0x18056f605  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f611  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f618  mov     edx, 12h
0x18056f61d  mov     dword ptr [rsp+0C0h+var_A0], 8007000Dh
0x18056f625  mov     r9d, eax
0x18056f628  mov     rcx, [rcx+10h]
0x18056f62c  call    WPP_SF_Dd
0x18056f631  jmp     loc_18056F7B7
0x18056f636  test    ebx, ebx
0x18056f638  jns     short loc_18056F69E
0x18056f63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f641  lea     rax, WPP_GLOBAL_Control
0x18056f648  cmp     rcx, rax
0x18056f64b  jz      loc_18056F7B7
0x18056f651  test    byte ptr [rcx+1Ch], 8
0x18056f655  jz      loc_18056F7B7
0x18056f65b  cmp     byte ptr [rcx+19h], 2
0x18056f65f  jb      loc_18056F7B7
0x18056f665  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f66a  mov     edx, 13h
0x18056f66f  lea     rcx, aDevobjgetdevic; "DevObjGetDeviceRegistryProperty FAILED"
0x18056f676  mov     [rsp+0C0h+var_98], ebx
0x18056f67a  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f681  mov     [rsp+0C0h+var_A0], rcx
0x18056f686  mov     r9d, eax
0x18056f689  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f690  mov     rcx, [rcx+10h]
0x18056f694  call    WPP_SF_DsD
0x18056f699  jmp     loc_18056F7B7
0x18056f69e  mov     eax, dword ptr [rbp+4Fh+cb]
0x18056f6a1  mov     ecx, eax; cb
0x18056f6a3  call    cs:__imp_CoTaskMemAlloc
0x18056f6a9  mov     rdi, rax
0x18056f6ac  test    rax, rax
0x18056f6af  jnz     short loc_18056F708
0x18056f6b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f6b8  lea     rax, WPP_GLOBAL_Control
0x18056f6bf  cmp     rcx, rax
0x18056f6c2  jz      short loc_18056F6FE
0x18056f6c4  test    byte ptr [rcx+1Ch], 8
0x18056f6c8  jz      short loc_18056F6FE
0x18056f6ca  cmp     byte ptr [rcx+19h], 2
0x18056f6ce  jb      short loc_18056F6FE
0x18056f6d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f6d5  lea     rcx, aPbyte; "PBYTE"
0x18056f6dc  mov     r9d, eax
0x18056f6df  mov     [rsp+0C0h+var_A0], rcx
0x18056f6e4  lea     edx, [rdi+14h]
0x18056f6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f6ee  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f6f5  mov     rcx, [rcx+10h]
0x18056f6f9  call    WPP_SF_Ds
0x18056f6fe  mov     ebx, 8007000Eh
0x18056f703  jmp     loc_18056F7B7
0x18056f708  mov     eax, dword ptr [rbp+4Fh+cb]
0x18056f70b  lea     rdx, [rbp+4Fh+var_78]
0x18056f70f  mov     [rsp+0C0h+var_90], 0
0x18056f718  mov     r9, r13
0x18056f71b  mov     [rsp+0C0h+var_98], eax
0x18056f71f  mov     r8d, r14d
0x18056f722  mov     rcx, rsi
0x18056f725  mov     [rsp+0C0h+var_A0], rdi
0x18056f72a  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18056f730  test    eax, eax
0x18056f732  jnz     short loc_18056F7AB
0x18056f734  call    cs:__imp_GetLastError
0x18056f73a  mov     ebx, eax
0x18056f73c  test    eax, eax
0x18056f73e  jle     short loc_18056F749
0x18056f740  movzx   ebx, ax
0x18056f743  or      ebx, 80070000h
0x18056f749  test    ebx, ebx
0x18056f74b  jns     short loc_18056F7AB
0x18056f74d  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f754  lea     rax, WPP_GLOBAL_Control
0x18056f75b  cmp     rcx, rax
0x18056f75e  jz      short loc_18056F7A0
0x18056f760  test    byte ptr [rcx+1Ch], 8
0x18056f764  jz      short loc_18056F7A0
0x18056f766  cmp     byte ptr [rcx+19h], 2
0x18056f76a  jb      short loc_18056F7A0
0x18056f76c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056f771  lea     rcx, aDevobjgetdevic; "DevObjGetDeviceRegistryProperty FAILED"
0x18056f778  mov     [rsp+0C0h+var_98], ebx
0x18056f77c  mov     [rsp+0C0h+var_A0], rcx
0x18056f781  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056f788  mov     rcx, cs:WPP_GLOBAL_Control
0x18056f78f  mov     edx, 15h
0x18056f794  mov     r9d, eax
0x18056f797  mov     rcx, [rcx+10h]
0x18056f79b  call    WPP_SF_DsD
0x18056f7a0  mov     rcx, rdi; pv
0x18056f7a3  call    cs:__imp_CoTaskMemFree
0x18056f7a9  jmp     short loc_18056F7B7
0x18056f7ab  mov     eax, dword ptr [rbp+4Fh+cb]
0x18056f7ae  xor     ebx, ebx
0x18056f7b0  mov     [r12], eax
0x18056f7b4  mov     [r15], rdi
0x18056f7b7  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18056f7bb  jz      short loc_18056F7C6
0x18056f7bd  mov     rcx, rsi
0x18056f7c0  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18056f7c6  mov     eax, ebx
0x18056f7c8  mov     rcx, [rbp+4Fh+var_48]
0x18056f7cc  xor     rcx, rsp; StackCookie
0x18056f7cf  call    __security_check_cookie
0x18056f7d4  add     rsp, 88h
0x18056f7db  pop     r15
0x18056f7dd  pop     r14
0x18056f7df  pop     r13
0x18056f7e1  pop     r12
0x18056f7e3  pop     rdi
0x18056f7e4  pop     rsi
0x18056f7e5  pop     rbx
0x18056f7e6  pop     rbp
0x18056f7e7  retn
```
