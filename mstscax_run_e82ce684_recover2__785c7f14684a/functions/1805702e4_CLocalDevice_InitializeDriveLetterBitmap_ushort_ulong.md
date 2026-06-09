# CLocalDevice::InitializeDriveLetterBitmap(ushort *,ulong *)

- ea: `0x1805702e4`
- end: `0x180570a5e`
- name: `?InitializeDriveLetterBitmap@CLocalDevice@@AEAAJPEAGPEAK@Z`
- size: `1914`
- prototype: `__int64 __fastcall(CLocalDevice *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1805702e4`
- `0x1805715f0`

## callees

- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18012966c`
- `0x1805702e4`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180570a2f`
- `KERNEL32!CloseHandle` at `0x180570a2f`
- `KERNEL32!DeviceIoControl` at `0x18057077b`
- `KERNEL32!DeviceIoControl` at `0x18057077b`
- `KERNEL32!GetLastError` at `0x18057037b`
- `KERNEL32!GetLastError` at `0x180570422`
- `KERNEL32!GetLastError` at `0x1805704c3`
- `KERNEL32!GetLastError` at `0x180570572`
- `KERNEL32!GetLastError` at `0x1805705bf`
- `KERNEL32!GetLastError` at `0x180570646`
- `KERNEL32!GetLastError` at `0x1805706f4`
- `KERNEL32!GetLastError` at `0x180570785`
- `KERNEL32!GetLastError` at `0x18057037b`
- `KERNEL32!GetLastError` at `0x180570422`
- `KERNEL32!GetLastError` at `0x1805704c3`
- `KERNEL32!GetLastError` at `0x180570572`
- `KERNEL32!GetLastError` at `0x1805705bf`
- `KERNEL32!GetLastError` at `0x180570646`
- `KERNEL32!GetLastError` at `0x1805706f4`
- `KERNEL32!GetLastError` at `0x180570785`
- `KERNEL32!CreateFileW` at `0x1805706e1`
- `KERNEL32!CreateFileW` at `0x1805706e1`
- `setupapi!CM_Get_Device_ID_Size` at `0x18057083b`
- `setupapi!CM_Get_Device_ID_Size` at `0x18057083b`
- `setupapi!CM_Get_Device_IDW` at `0x180570880`
- `setupapi!CM_Get_Device_IDW` at `0x180570880`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805705af`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805705af`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180570566`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180570566`
- `DEVOBJ!DevObjGetClassDevs` at `0x180570418`
- `DEVOBJ!DevObjGetClassDevs` at `0x180570418`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180570a07`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180570a07`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1805704b9`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1805704b9`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180570362`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180570362`
- `CFGMGR32!CM_Get_Sibling` at `0x180570905`
- `CFGMGR32!CM_Get_Sibling` at `0x180570905`
- `CFGMGR32!CM_Get_Child` at `0x180570818`
- `CFGMGR32!CM_Get_Child` at `0x180570818`

## string_xrefs

- `0x1805703c1`: `DevObjCreateDeviceInfoList FAILED`
- `0x18057050e`: `DevObjOpenDeviceInfo failed`
- `0x180570742`: `CreateFile failed`

## pseudocode

```c
__int64 __fastcall CLocalDevice::InitializeDriveLetterBitmap(
        CLocalDevice *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  __int64 DeviceInfoList; // rax
  __int64 v6; // r14
  signed int LastError; // eax
  signed int v8; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned __int16 *v10; // rsi
  WCHAR *v11; // r12
  signed int v12; // eax
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  signed int v16; // eax
  DEVINST v17; // r15d
  unsigned int v18; // r14d
  unsigned int v19; // ebx
  int DeviceInterfaceDetail; // edi
  GUID *v21; // r8
  unsigned int i; // ebx
  WCHAR *v23; // rax
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // rcx
  signed int v27; // eax
  unsigned int v28; // eax
  int v29; // edx
  const char *v30; // rcx
  signed int v31; // eax
  signed int v32; // eax
  __int64 v33; // rcx
  CONFIGRET j; // eax
  WCHAR *v35; // rax
  int v36; // eax
  char v37; // bl
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  __int64 FileW; // [rsp+40h] [rbp-79h]
  DEVNODE pdnDevInst; // [rsp+48h] [rbp-71h] BYREF
  ULONG pulLen; // [rsp+4Ch] [rbp-6Dh] BYREF
  size_t Size; // [rsp+50h] [rbp-69h] BYREF
  __int64 v46; // [rsp+58h] [rbp-61h]
  DWORD BytesReturned; // [rsp+60h] [rbp-59h] BYREF
  unsigned int *v48; // [rsp+68h] [rbp-51h]
  __int64 OutBuffer; // [rsp+70h] [rbp-49h] BYREF
  int v50; // [rsp+78h] [rbp-41h]
  _OWORD v51[2]; // [rsp+80h] [rbp-39h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-19h] BYREF
  DEVINST dnDevInst[4]; // [rsp+B0h] [rbp-9h]
  __int128 v54; // [rsp+C0h] [rbp+7h]

  v48 = a3;
  pdnDevInst = 0;
  OutBuffer = 0;
  v50 = 0;
  BytesReturned = 0;
  Size = 0;
  pulLen = 0;
  v52 = 0;
  *(_OWORD *)dnDevInst = 0;
  v54 = 0;
  memset(v51, 0, sizeof(v51));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = -1;
  v46 = DeviceInfoList;
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
          110,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList FAILED",
          v8);
      }
      return (unsigned int)v8;
    }
    DeviceInfoList = v46;
  }
  v10 = 0;
  FileW = -1;
  v11 = 0;
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, a2, 20, 0, 0) )
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
        goto LABEL_106;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 111;
      v15 = "DevObjGetClassDevs FAILED";
      goto LABEL_18;
    }
  }
  LODWORD(v52) = 48;
  if ( !(unsigned int)DevObjOpenDeviceInfo(v46, a2, 0, 0, &v52) )
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
        goto LABEL_106;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 112;
      v15 = "DevObjOpenDeviceInfo failed";
LABEL_18:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
        v13,
        (__int64)v15,
        v8);
      goto LABEL_106;
    }
  }
  v17 = dnDevInst[1];
  v18 = 0;
  v19 = 0;
  DeviceInterfaceDetail = 0;
  do
  {
    if ( DeviceInterfaceDetail )
      goto LABEL_37;
    if ( v19 )
    {
      v21 = &GUID_DEVINTERFACE_CDROM;
      if ( v19 != 1 )
        v21 = &GUID_DEVINTERFACE_FLOPPY;
    }
    else
    {
      v21 = &GUID_DEVINTERFACE_DISK;
    }
    LODWORD(v51[0]) = 32;
    DeviceInterfaceDetail = DevObjEnumDeviceInterfaces(v46, &v52, v21, 0, v51);
    if ( !DeviceInterfaceDetail )
      GetLastError();
    ++v19;
  }
  while ( v19 < 3 );
  if ( DeviceInterfaceDetail )
  {
LABEL_37:
    for ( i = 0; i < 2; ++i )
    {
      DeviceInterfaceDetail = DevObjGetDeviceInterfaceDetail(v46, v51, v11, (unsigned int)Size, &Size, 0);
      if ( DeviceInterfaceDetail )
        goto LABEL_60;
      if ( GetLastError() == 122 && !v11 )
      {
        v23 = (WCHAR *)operator new((unsigned int)Size);
        v11 = v23;
        if ( !v23 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v24 = RdpWppGetCurrentThreadActivityIdPrefix();
            v25 = 113;
            v26 = "UCHAR";
LABEL_49:
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v25,
              (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
              v24,
              (__int64)v26);
          }
LABEL_50:
          v8 = -2147024882;
          goto LABEL_105;
        }
        *(_DWORD *)v23 = 8;
      }
    }
    if ( !DeviceInterfaceDetail )
    {
      v27 = GetLastError();
      v8 = v27;
      if ( v27 > 0 )
        v8 = (unsigned __int16)v27 | 0x80070000;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 114;
        v30 = "DevObjGetDeviceInterfaceDetail failed";
LABEL_59:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          v28,
          (__int64)v30,
          v8);
        goto LABEL_105;
      }
    }
LABEL_60:
    FileW = (__int64)CreateFileW(v11 + 2, 0, 0, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      v31 = GetLastError();
      v8 = v31;
      if ( v31 > 0 )
        v8 = (unsigned __int16)v31 | 0x80070000;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 115;
        v30 = "CreateFile failed";
        goto LABEL_59;
      }
    }
    if ( !DeviceIoControl((HANDLE)FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
    {
      v32 = GetLastError();
      v8 = v32;
      if ( v32 > 0 )
        v8 = (unsigned __int16)v32 | 0x80070000;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 116;
        v30 = "DeviceIoControl(IOCTL_STORAGE_GET_DEVICE_NUMBER) failed";
        goto LABEL_59;
      }
    }
    v33 = 0;
    do
    {
      if ( *(_QWORD *)((char *)this + 8 * v33 + 628) == OutBuffer )
        v18 |= 1 << v33;
      v33 = (unsigned int)(v33 + 1);
    }
    while ( (unsigned int)v33 < 0x1A );
  }
  for ( j = CM_Get_Child(&pdnDevInst, v17, 0); ; j = CM_Get_Sibling(&pdnDevInst, pdnDevInst, 0) )
  {
    if ( j )
    {
      v8 = 0;
      *v48 = v18;
LABEL_104:
      v10 = 0;
      goto LABEL_105;
    }
    if ( CM_Get_Device_ID_Size(&pulLen, pdnDevInst, 0) )
    {
      v8 = -2147024865;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v40 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          117,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          v40,
          (__int64)"CM_Get_Device_ID_Size failed",
          31);
      }
      goto LABEL_104;
    }
    v35 = (WCHAR *)operator new(saturated_mul(++pulLen, 2u));
    v10 = v35;
    if ( !v35 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        v25 = 118;
        v26 = "WCHAR";
        goto LABEL_49;
      }
      goto LABEL_50;
    }
    if ( CM_Get_Device_IDW(pdnDevInst, v35, pulLen, 0) )
      break;
    v36 = CLocalDevice::InitializeDriveLetterBitmap(this, v10, (unsigned int *)&Size + 1);
    v37 = v36;
    if ( v36 < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v38 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
        v38,
        (__int64)"InitializeDriveLetterBitmap failed",
        v37);
    }
    operator delete(v10);
    v18 |= HIDWORD(Size);
  }
  v8 = -2147024865;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v39 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
      v39,
      (__int64)"CM_Get_Device_ID failed",
      31);
  }
LABEL_105:
  v6 = FileW;
LABEL_106:
  if ( v46 != -1 )
    DevObjDestroyDeviceInfoList(v46);
  if ( v10 )
    operator delete(v10);
  if ( v11 )
    operator delete(v11);
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1805702e4  mov     [rsp-8+arg_18], rbx
0x1805702e9  push    rbp
0x1805702ea  push    rsi
0x1805702eb  push    rdi
0x1805702ec  push    r12
0x1805702ee  push    r13
0x1805702f0  push    r14
0x1805702f2  push    r15
0x1805702f4  lea     rbp, [rsp-27h]
0x1805702f9  sub     rsp, 0E0h
0x180570300  mov     rax, cs:__security_cookie
0x180570307  xor     rax, rsp
0x18057030a  mov     [rbp+57h+var_40], rax
0x18057030e  xorps   xmm0, xmm0
0x180570311  mov     [rbp+57h+var_A8], r8
0x180570315  xor     eax, eax
0x180570317  mov     [rbp+57h+pdnDevInst], 0
0x18057031e  mov     rdi, rdx
0x180570321  mov     [rbp+57h+OutBuffer], rax
0x180570325  mov     r13, rcx
0x180570328  mov     [rbp+57h+var_98], eax
0x18057032b  xor     r8d, r8d
0x18057032e  mov     [rbp+57h+BytesReturned], eax
0x180570331  xor     edx, edx
0x180570333  mov     dword ptr [rbp+57h+Size], eax
0x180570336  xor     ecx, ecx
0x180570338  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18057033d  xor     r9d, r9d
0x180570340  mov     [rbp+57h+pulLen], 0
0x180570347  movups  [rbp+57h+var_70], xmm0
0x18057034b  mov     dword ptr [rbp+57h+Size+4], 0
0x180570352  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x180570356  movups  [rbp+57h+var_50], xmm0
0x18057035a  movups  [rbp+57h+var_90], xmm0
0x18057035e  movups  [rbp+57h+var_80], xmm0
0x180570362  call    cs:__imp_DevObjCreateDeviceInfoList
0x180570368  or      r14, 0FFFFFFFFFFFFFFFFh
0x18057036c  mov     [rbp+57h+var_B8], rax
0x180570370  mov     r15d, 80070000h
0x180570376  cmp     rax, r14
0x180570379  jnz     short loc_1805703F9
0x18057037b  call    cs:__imp_GetLastError
0x180570381  mov     ebx, eax
0x180570383  test    eax, eax
0x180570385  jle     short loc_18057038D
0x180570387  movzx   ebx, ax
0x18057038a  or      ebx, r15d
0x18057038d  test    ebx, ebx
0x18057038f  jns     short loc_1805703F5
0x180570391  mov     rax, cs:WPP_GLOBAL_Control
0x180570398  lea     rdi, WPP_GLOBAL_Control
0x18057039f  cmp     rax, rdi
0x1805703a2  jz      loc_180570A35
0x1805703a8  test    byte ptr [rax+1Ch], 8
0x1805703ac  jz      loc_180570A35
0x1805703b2  cmp     byte ptr [rax+19h], 2
0x1805703b6  jb      loc_180570A35
0x1805703bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805703c1  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x1805703c8  mov     [rsp+110h+dwFlagsAndAttributes], ebx
0x1805703cc  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx
0x1805703d1  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x1805703d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1805703df  mov     edx, 6Eh ; 'n'
0x1805703e4  mov     r9d, eax
0x1805703e7  mov     rcx, [rcx+10h]
0x1805703eb  call    WPP_SF_DsD
0x1805703f0  jmp     loc_180570A35
0x1805703f5  mov     rax, [rbp+57h+var_B8]
0x1805703f9  xor     esi, esi
0x1805703fb  mov     [rbp+57h+var_D0], r14
0x1805703ff  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rsi
0x180570404  mov     r8, rdi
0x180570407  xor     edx, edx
0x180570409  mov     qword ptr [rsp+110h+dwCreationDisposition], rsi
0x18057040e  mov     rcx, rax
0x180570411  xor     r12d, r12d
0x180570414  lea     r9d, [rsi+14h]
0x180570418  call    cs:__imp_DevObjGetClassDevs
0x18057041e  test    eax, eax
0x180570420  jnz     short loc_18057049C
0x180570422  call    cs:__imp_GetLastError
0x180570428  mov     ebx, eax
0x18057042a  test    eax, eax
0x18057042c  jle     short loc_180570434
0x18057042e  movzx   ebx, ax
0x180570431  or      ebx, r15d
0x180570434  test    ebx, ebx
0x180570436  jns     short loc_18057049C
0x180570438  mov     rax, cs:WPP_GLOBAL_Control
0x18057043f  lea     rdi, WPP_GLOBAL_Control
0x180570446  cmp     rax, rdi
0x180570449  jz      loc_1805709F7
0x18057044f  test    byte ptr [rax+1Ch], 8
0x180570453  jz      loc_1805709F7
0x180570459  cmp     byte ptr [rax+19h], 2
0x18057045d  jb      loc_1805709F7
0x180570463  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570468  mov     edx, 6Fh ; 'o'
0x18057046d  lea     rcx, aDevobjgetclass_0; "DevObjGetClassDevs FAILED"
0x180570474  mov     [rsp+110h+dwFlagsAndAttributes], ebx
0x180570478  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18057047f  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx
0x180570484  mov     r9d, eax
0x180570487  mov     rcx, cs:WPP_GLOBAL_Control
0x18057048e  mov     rcx, [rcx+10h]
0x180570492  call    WPP_SF_DsD
0x180570497  jmp     loc_1805709F7
0x18057049c  mov     rcx, [rbp+57h+var_B8]
0x1805704a0  lea     rax, [rbp+57h+var_70]
0x1805704a4  xor     r9d, r9d
0x1805704a7  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1805704ac  xor     r8d, r8d
0x1805704af  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x1805704b6  mov     rdx, rdi
0x1805704b9  call    cs:__imp_DevObjOpenDeviceInfo
0x1805704bf  test    eax, eax
0x1805704c1  jnz     short loc_18057051A
0x1805704c3  call    cs:__imp_GetLastError
0x1805704c9  mov     ebx, eax
0x1805704cb  test    eax, eax
0x1805704cd  jle     short loc_1805704D5
0x1805704cf  movzx   ebx, ax
0x1805704d2  or      ebx, r15d
0x1805704d5  test    ebx, ebx
0x1805704d7  jns     short loc_18057051A
0x1805704d9  mov     rax, cs:WPP_GLOBAL_Control
0x1805704e0  lea     rdi, WPP_GLOBAL_Control
0x1805704e7  cmp     rax, rdi
0x1805704ea  jz      loc_1805709F7
0x1805704f0  test    byte ptr [rax+1Ch], 8
0x1805704f4  jz      loc_1805709F7
0x1805704fa  cmp     byte ptr [rax+19h], 2
0x1805704fe  jb      loc_1805709F7
0x180570504  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180570509  mov     edx, 70h ; 'p'
0x18057050e  lea     rcx, aDevobjopendevi_0; "DevObjOpenDeviceInfo failed"
0x180570515  jmp     loc_180570474
0x18057051a  mov     r15d, [rbp+57h+dnDevInst+4]
0x18057051e  xor     r14d, r14d
0x180570521  xor     ebx, ebx
0x180570523  xor     edi, edi
0x180570525  test    edi, edi
0x180570527  jnz     short loc_180570587
0x180570529  test    ebx, ebx
0x18057052b  jnz     short loc_180570536
0x18057052d  lea     r8, GUID_DEVINTERFACE_DISK
0x180570534  jmp     short loc_18057054B
0x180570536  cmp     ebx, 1
0x180570539  lea     r8, GUID_DEVINTERFACE_CDROM
0x180570540  lea     rax, GUID_DEVINTERFACE_FLOPPY
0x180570547  cmovnz  r8, rax
0x18057054b  mov     rcx, [rbp+57h+var_B8]
0x18057054f  lea     rax, [rbp+57h+var_90]
0x180570553  xor     r9d, r9d
0x180570556  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18057055b  lea     rdx, [rbp+57h+var_70]
0x18057055f  mov     dword ptr [rbp+57h+var_90], 20h ; ' '
0x180570566  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18057056c  mov     edi, eax
0x18057056e  test    eax, eax
0x180570570  jnz     short loc_180570578
0x180570572  call    cs:__imp_GetLastError
0x180570578  inc     ebx
0x18057057a  cmp     ebx, 3
0x18057057d  jb      short loc_180570525
0x18057057f  test    edi, edi
0x180570581  jz      loc_18057080E
0x180570587  xor     ebx, ebx
0x180570589  cmp     ebx, 2
0x18057058c  jnb     loc_180570642
0x180570592  mov     r9d, dword ptr [rbp+57h+Size]
0x180570596  lea     rax, [rbp+57h+Size]
0x18057059a  mov     rcx, [rbp+57h+var_B8]
0x18057059e  lea     rdx, [rbp+57h+var_90]
0x1805705a2  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rsi
0x1805705a7  mov     r8, r12
0x1805705aa  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1805705af  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1805705b5  mov     edi, eax
0x1805705b7  test    eax, eax
0x1805705b9  jnz     loc_1805706C3
0x1805705bf  call    cs:__imp_GetLastError
0x1805705c5  cmp     eax, 7Ah ; 'z'
0x1805705c8  jnz     short loc_1805705E5
0x1805705ca  test    r12, r12
0x1805705cd  jnz     short loc_1805705E5
0x1805705cf  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x1805705d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805705d7  mov     r12, rax
0x1805705da  test    rax, rax
0x1805705dd  jz      short loc_1805705E9
0x1805705df  mov     dword ptr [rax], 8
0x1805705e5  inc     ebx
0x1805705e7  jmp     short loc_180570589
0x1805705e9  mov     rax, cs:WPP_GLOBAL_Control
0x1805705f0  lea     rdi, WPP_GLOBAL_Control
0x1805705f7  cmp     rax, rdi
0x1805705fa  jz      short loc_180570638
0x1805705fc  test    byte ptr [rax+1Ch], 8
0x180570600  jz      short loc_180570638
0x180570602  cmp     byte ptr [rax+19h], 2
0x180570606  jb      short loc_180570638
0x180570608  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18057060d  mov     edx, 71h ; 'q'
0x180570612  lea     rcx, aUchar; "UCHAR"
0x180570619  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx
0x18057061e  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x180570625  mov     rcx, cs:WPP_GLOBAL_Control
0x18057062c  mov     r9d, eax
0x18057062f  mov     rcx, [rcx+10h]
0x180570633  call    WPP_SF_Ds
0x180570638  mov     ebx, 8007000Eh
0x18057063d  jmp     loc_1805709F3
0x180570642  test    edi, edi
0x180570644  jnz     short loc_1805706C3
0x180570646  call    cs:__imp_GetLastError
0x18057064c  mov     ebx, eax
0x18057064e  test    eax, eax
0x180570650  jle     short loc_18057065B
0x180570652  movzx   ebx, ax
0x180570655  or      ebx, 80070000h
0x18057065b  test    ebx, ebx
0x18057065d  jns     short loc_1805706C3
0x18057065f  mov     rax, cs:WPP_GLOBAL_Control
0x180570666  lea     rdi, WPP_GLOBAL_Control
0x18057066d  cmp     rax, rdi
0x180570670  jz      loc_1805709F3
0x180570676  test    byte ptr [rax+1Ch], 8
0x18057067a  jz      loc_1805709F3
0x180570680  cmp     byte ptr [rax+19h], 2
0x180570684  jb      loc_1805709F3
0x18057068a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18057068f  mov     edx, 72h ; 'r'
0x180570694  lea     rcx, aDevobjgetdevic_0; "DevObjGetDeviceInterfaceDetail failed"
0x18057069b  mov     [rsp+110h+dwFlagsAndAttributes], ebx
0x18057069f  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx
0x1805706a4  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x1805706ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1805706b2  mov     r9d, eax
0x1805706b5  mov     rcx, [rcx+10h]
0x1805706b9  call    WPP_SF_DsD
0x1805706be  jmp     loc_1805709F3
0x1805706c3  mov     [rsp+110h+hTemplateFile], rsi; hTemplateFile
0x1805706c8  lea     rcx, [r12+4]; lpFileName
0x1805706cd  mov     [rsp+110h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1805706d1  xor     r9d, r9d; lpSecurityAttributes
0x1805706d4  xor     r8d, r8d; dwShareMode
0x1805706d7  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x1805706df  xor     edx, edx; dwDesiredAccess
0x1805706e1  call    cs:__imp_CreateFileW
0x1805706e7  mov     [rbp+57h+var_D0], rax
0x1805706eb  mov     rdi, rax
0x1805706ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805706f2  jnz     short loc_18057074E
0x1805706f4  call    cs:__imp_GetLastError
0x1805706fa  mov     ebx, eax
0x1805706fc  test    eax, eax
0x1805706fe  jle     short loc_180570709
0x180570700  movzx   ebx, ax
0x180570703  or      ebx, 80070000h
0x180570709  test    ebx, ebx
0x18057070b  jns     short loc_18057074E
0x18057070d  mov     rax, cs:WPP_GLOBAL_Control
0x180570714  lea     rdi, WPP_GLOBAL_Control
0x18057071b  cmp     rax, rdi
0x18057071e  jz      loc_1805709F3
0x180570724  test    byte ptr [rax+1Ch], 8
0x180570728  jz      loc_1805709F3
0x18057072e  cmp     byte ptr [rax+19h], 2
0x180570732  jb      loc_1805709F3
0x180570738  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18057073d  mov     edx, 73h ; 's'
0x180570742  lea     rcx, aCreatefileFail; "CreateFile failed"
0x180570749  jmp     loc_18057069B
0x18057074e  mov     [rsp+110h+lpOverlapped], rsi; lpOverlapped
0x180570753  lea     rax, [rbp+57h+BytesReturned]
0x180570757  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x18057075c  xor     r9d, r9d; nInBufferSize
0x18057075f  lea     rax, [rbp+57h+OutBuffer]
0x180570763  mov     [rsp+110h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18057076b  xor     r8d, r8d; lpInBuffer
0x18057076e  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpOutBuffer
0x180570773  mov     edx, 2D1080h; dwIoControlCode
0x180570778  mov     rcx, rdi; hDevice
0x18057077b  call    cs:__imp_DeviceIoControl
0x180570781  test    eax, eax
0x180570783  jnz     short loc_1805707DF
0x180570785  call    cs:__imp_GetLastError
0x18057078b  mov     ebx, eax
0x18057078d  test    eax, eax
0x18057078f  jle     short loc_18057079A
0x180570791  movzx   ebx, ax
0x180570794  or      ebx, 80070000h
0x18057079a  test    ebx, ebx
0x18057079c  jns     short loc_1805707DF
0x18057079e  mov     rax, cs:WPP_GLOBAL_Control
0x1805707a5  lea     rdi, WPP_GLOBAL_Control
0x1805707ac  cmp     rax, rdi
0x1805707af  jz      loc_1805709F3
  ... truncated ...
```
