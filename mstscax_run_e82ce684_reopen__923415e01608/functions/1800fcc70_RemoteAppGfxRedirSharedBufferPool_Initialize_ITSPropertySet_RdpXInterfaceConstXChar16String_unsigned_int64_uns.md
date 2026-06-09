# RemoteAppGfxRedirSharedBufferPool::Initialize(ITSPropertySet *,RdpXInterfaceConstXChar16String *,unsigned __int64,unsigned __int64)

- ea: `0x1800fcc70`
- end: `0x1800fd28b`
- name: `?Initialize@RemoteAppGfxRedirSharedBufferPool@@AEAAJPEAVITSPropertySet@@PEAURdpXInterfaceConstXChar16String@@_K2@Z`
- size: `1563`
- prototype: `__int64 __fastcall(RemoteAppGfxRedirSharedBufferPool *__hidden this, struct ITSPropertySet *, struct RdpXInterfaceConstXChar16String *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802c742c`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180085e04`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x1800fcc70`
- `0x180432ac4`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800fd259`
- `KERNEL32!CloseHandle` at `0x1800fd259`
- `KERNEL32!GetLastError` at `0x1800fcec2`
- `KERNEL32!GetLastError` at `0x1800fcefb`
- `KERNEL32!GetLastError` at `0x1800fcec2`
- `KERNEL32!GetLastError` at `0x1800fcefb`
- `KERNEL32!UnmapViewOfFile` at `0x1800fd1fe`
- `KERNEL32!UnmapViewOfFile` at `0x1800fd1fe`
- `KERNEL32!MapViewOfFile` at `0x1800fd100`
- `KERNEL32!MapViewOfFile` at `0x1800fd100`
- `KERNEL32!VirtualQuery` at `0x1800fd167`
- `KERNEL32!VirtualQuery` at `0x1800fd167`
- `KERNEL32!OpenFileMappingW` at `0x1800fce91`
- `KERNEL32!OpenFileMappingW` at `0x1800fce91`
- `OLE32!CLSIDFromString` at `0x1800fcfdc`
- `OLE32!CLSIDFromString` at `0x1800fd02c`
- `OLE32!CLSIDFromString` at `0x1800fcfdc`
- `OLE32!CLSIDFromString` at `0x1800fd02c`

## string_xrefs

- `0x1800fd0ba`: `Failed to create VM shared memory section`
- `0x1800fce7c`: `Failed to create section name with StringCchPrintf`
- `0x1800fcdf6`: `GetStringProperty(TS_PROP_CORE_WSLG_SHARED_MEMORY_PATH) failed`
- `0x1800fcdb3`: `WslgSharedMemoryPath`

## pseudocode

```c
__int64 __fastcall RemoteAppGfxRedirSharedBufferPool::Initialize(
        RemoteAppGfxRedirSharedBufferPool *this,
        struct ITSPropertySet *a2,
        struct RdpXInterfaceConstXChar16String *a3,
        __int64 a4,
        unsigned __int64 a5)
{
  __int64 v9; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // ebx
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(struct ITSPropertySet *, const char *, LPCOLESTR *); // rbx
  __int64 v17; // rax
  HANDLE v18; // rax
  signed int LastError; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 (__fastcall *v25)(struct ITSPropertySet *, const char *, LPCOLESTR *); // rax
  const OLECHAR *v26; // rax
  int v27; // eax
  const void *v28; // rax
  const void *v29; // rdi
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  LPCOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+48h] [rbp-B8h] BYREF
  GUID v38; // [rsp+78h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  v35 = 0;
  hObject = 0;
  memset(&Buffer, 0, sizeof(Buffer));
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v9 = (*(__int64 (__fastcall **)(struct RdpXInterfaceConstXChar16String *))(*(_QWORD *)a3 + 24LL))(a3);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_e4abe435090c3be44d2c881aae813c99_Traceguids,
      CurrentThreadActivityIdPrefix,
      v9);
  }
  v11 = (*(__int64 (__fastcall **)(struct ITSPropertySet *, const char *, int *))(*(_QWORD *)a2 + 120LL))(
          a2,
          "WslgModeEnabled",
          &v35);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 15;
      v14 = "GetBoolProperty(TS_PROP_CORE_WSLGMODE_ENABLED) failed";
LABEL_58:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)WPP_e4abe435090c3be44d2c881aae813c99_Traceguids,
        v12,
        (__int64)v14,
        v11);
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  v15 = *(_QWORD *)a2;
  lpsz = 0;
  v16 = *(__int64 (__fastcall **)(struct ITSPropertySet *, const char *, LPCOLESTR *))(v15 + 128);
  if ( !v35 )
  {
    v25 = *(__int64 (__fastcall **)(struct ITSPropertySet *, const char *, LPCOLESTR *))(v15 + 128);
    v38 = 0;
    pclsid = 0;
    v11 = v25(a2, "HiDefRemoteAppContainerGUID", &lpsz);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 20;
        v14 = "GetStringProperty(TS_PROP_CORE_HIDEF_REMOTEAPP_CONTAINER_GUID) failed";
        goto LABEL_58;
      }
      goto LABEL_84;
    }
    if ( lpsz && *lpsz )
    {
      v26 = (const OLECHAR *)(*(__int64 (__fastcall **)(struct RdpXInterfaceConstXChar16String *))(*(_QWORD *)a3 + 24LL))(a3);
      v11 = CLSIDFromString(v26, &pclsid);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          v13 = 22;
          v14 = "Failed to convert section name to GUID";
          goto LABEL_58;
        }
        goto LABEL_84;
      }
      v11 = CLSIDFromString(lpsz, &v38);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          v13 = 23;
          v14 = "Failed to convert Vm Guid string to GUID";
          goto LABEL_58;
        }
        goto LABEL_84;
      }
      v27 = OpenVmSharedMemorySection(&hObject);
      v11 = v27 | 0x10000000;
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          v13 = 24;
          v14 = "Failed to create VM shared memory section";
          goto LABEL_58;
        }
        goto LABEL_84;
      }
      v18 = hObject;
      goto LABEL_60;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 21;
      goto LABEL_82;
    }
LABEL_83:
    v11 = -2147467259;
    goto LABEL_84;
  }
  memset_0(Name, 0, 0x208u);
  v11 = v16(a2, "WslgSharedMemoryPath", &lpsz);
  if ( v11 >= 0 )
  {
    if ( lpsz && *lpsz )
    {
      v17 = (*(__int64 (__fastcall **)(struct RdpXInterfaceConstXChar16String *))(*(_QWORD *)a3 + 24LL))(a3);
      v11 = StringCchPrintfW(Name, 0x104u, L"%s\\%s", lpsz, v17);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          v13 = 18;
          v14 = "Failed to create section name with StringCchPrintf";
          goto LABEL_58;
        }
        goto LABEL_84;
      }
      v18 = OpenFileMappingW(4u, 0, Name);
      hObject = v18;
      if ( !v18 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v20 = LastError;
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids, v21, v20);
        }
        v22 = GetLastError();
        v11 = v22;
        if ( v22 > 0 )
          v11 = (unsigned __int16)v22 | 0x80070000;
        goto LABEL_84;
      }
LABEL_60:
      v28 = MapViewOfFile(v18, 4u, 0, 0, 0);
      v29 = v28;
      if ( !v28 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids, v30);
        }
        goto LABEL_83;
      }
      if ( VirtualQuery(v28, &Buffer, 0x30u) )
      {
        if ( LODWORD(Buffer.RegionSize) >= a5 )
        {
          *((_QWORD *)this + 6) = a4;
          v11 = 0;
          *((_QWORD *)this + 7) = a5;
          *((_QWORD *)this + 8) = v29;
          goto LABEL_84;
        }
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v31 = RdpWppGetCurrentThreadActivityIdPrefix();
        v32 = 28;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v31 = RdpWppGetCurrentThreadActivityIdPrefix();
        v32 = 27;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids, v31);
LABEL_77:
      v11 = -2147467259;
      UnmapViewOfFile(v29);
      goto LABEL_84;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 17;
LABEL_82:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        WPP_e4abe435090c3be44d2c881aae813c99_Traceguids,
        v23,
        -2147467259);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 16;
    v14 = "GetStringProperty(TS_PROP_CORE_WSLG_SHARED_MEMORY_PATH) failed";
    goto LABEL_58;
  }
LABEL_84:
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800fcc70  mov     [rsp-8+arg_18], rbx
0x1800fcc75  push    rbp
0x1800fcc76  push    rsi
0x1800fcc77  push    rdi
0x1800fcc78  push    r12
0x1800fcc7a  push    r13
0x1800fcc7c  push    r14
0x1800fcc7e  push    r15
0x1800fcc80  lea     rbp, [rsp-1C0h]
0x1800fcc88  sub     rsp, 2C0h
0x1800fcc8f  mov     rax, cs:__security_cookie
0x1800fcc96  xor     rax, rsp
0x1800fcc99  mov     [rbp+1F0h+var_40], rax
0x1800fcca0  xorps   xmm0, xmm0
0x1800fcca3  xor     r12d, r12d
0x1800fcca6  mov     [rsp+2F0h+var_2B8], r12d
0x1800fccab  mov     r15, r9
0x1800fccae  mov     [rsp+2F0h+hObject], r12
0x1800fccb3  mov     r14, r8
0x1800fccb6  movups  xmmword ptr [rsp+2F0h+Buffer.BaseAddress], xmm0
0x1800fccbb  mov     rdi, rdx
0x1800fccbe  mov     rsi, rcx
0x1800fccc1  movups  xmmword ptr [rsp+2F0h+Buffer.AllocationProtect], xmm0
0x1800fccc6  movups  xmmword ptr [rsp+2F0h+Buffer.State], xmm0
0x1800fcccb  mov     rax, cs:WPP_GLOBAL_Control
0x1800fccd2  lea     r13, WPP_GLOBAL_Control
0x1800fccd9  cmp     rax, r13
0x1800fccdc  jz      short loc_1800FCD25
0x1800fccde  test    byte ptr [rax+1Ch], 40h
0x1800fcce2  jz      short loc_1800FCD25
0x1800fcce4  cmp     byte ptr [rax+19h], 4
0x1800fcce8  jb      short loc_1800FCD25
0x1800fccea  mov     rax, [r8]
0x1800fcced  mov     rcx, r8
0x1800fccf0  mov     rax, [rax+18h]
0x1800fccf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fccf9  mov     rbx, rax
0x1800fccfc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fcd01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fcd08  lea     edx, [r12+0Eh]
0x1800fcd0d  mov     r9d, eax
0x1800fcd10  mov     [rsp+2F0h+dwNumberOfBytesToMap], rbx
0x1800fcd15  lea     r8, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids
0x1800fcd1c  mov     rcx, [rcx+10h]
0x1800fcd20  call    WPP_SF_DS
0x1800fcd25  mov     rax, [rdi]
0x1800fcd28  lea     r8, [rsp+2F0h+var_2B8]
0x1800fcd2d  lea     rdx, aWslgmodeenable; "WslgModeEnabled"
0x1800fcd34  mov     rcx, rdi
0x1800fcd37  mov     rax, [rax+78h]
0x1800fcd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcd40  mov     ebx, eax
0x1800fcd42  test    eax, eax
0x1800fcd44  jns     short loc_1800FCD80
0x1800fcd46  mov     rax, cs:WPP_GLOBAL_Control
0x1800fcd4d  cmp     rax, r13
0x1800fcd50  jz      loc_1800FD24F
0x1800fcd56  test    byte ptr [rax+1Ch], 8
0x1800fcd5a  jz      loc_1800FD24F
0x1800fcd60  cmp     byte ptr [rax+19h], 2
0x1800fcd64  jb      loc_1800FD24F
0x1800fcd6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fcd6f  mov     edx, 0Fh
0x1800fcd74  lea     rcx, aGetboolpropert_33; "GetBoolProperty(TS_PROP_CORE_WSLGMODE_E"...
0x1800fcd7b  jmp     loc_1800FD0C1
0x1800fcd80  mov     rax, [rdi]
0x1800fcd83  mov     [rsp+2F0h+lpsz], r12
0x1800fcd88  mov     rbx, [rax+80h]
0x1800fcd8f  cmp     [rsp+2F0h+var_2B8], r12d
0x1800fcd94  jz      loc_1800FCF48
0x1800fcd9a  xor     edx, edx; Val
0x1800fcd9c  lea     rcx, [rbp+1F0h+Name]; void *
0x1800fcda0  mov     r8d, 208h; Size
0x1800fcda6  call    memset_0
0x1800fcdab  lea     r8, [rsp+2F0h+lpsz]
0x1800fcdb0  mov     rcx, rdi
0x1800fcdb3  lea     rdx, aWslgsharedmemo; "WslgSharedMemoryPath"
0x1800fcdba  mov     rax, rbx
0x1800fcdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcdc2  mov     ebx, eax
0x1800fcdc4  test    eax, eax
0x1800fcdc6  jns     short loc_1800FCE02
0x1800fcdc8  mov     rax, cs:WPP_GLOBAL_Control
0x1800fcdcf  cmp     rax, r13
0x1800fcdd2  jz      loc_1800FD24F
0x1800fcdd8  test    byte ptr [rax+1Ch], 8
0x1800fcddc  jz      loc_1800FD24F
0x1800fcde2  cmp     byte ptr [rax+19h], 2
0x1800fcde6  jb      loc_1800FD24F
0x1800fcdec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fcdf1  mov     edx, 10h
0x1800fcdf6  lea     rcx, aGetstringprope_14; "GetStringProperty(TS_PROP_CORE_WSLG_SHA"...
0x1800fcdfd  jmp     loc_1800FD0C1
0x1800fce02  mov     rax, [rsp+2F0h+lpsz]
0x1800fce07  test    rax, rax
0x1800fce0a  jz      loc_1800FCF15
0x1800fce10  cmp     [rax], r12w
0x1800fce14  jz      loc_1800FCF15
0x1800fce1a  mov     rax, [r14]
0x1800fce1d  mov     rcx, r14
0x1800fce20  mov     rax, [rax+18h]
0x1800fce24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fce29  mov     r9, [rsp+2F0h+lpsz]
0x1800fce2e  lea     r8, aSS_4; "%s\\%s"
0x1800fce35  mov     edx, 104h; unsigned __int64
0x1800fce3a  mov     [rsp+2F0h+dwNumberOfBytesToMap], rax
0x1800fce3f  lea     rcx, [rbp+1F0h+Name]; unsigned __int16 *
0x1800fce43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fce48  mov     ebx, eax
0x1800fce4a  test    eax, eax
0x1800fce4c  jns     short loc_1800FCE88
0x1800fce4e  mov     rax, cs:WPP_GLOBAL_Control
0x1800fce55  cmp     rax, r13
0x1800fce58  jz      loc_1800FD24F
0x1800fce5e  test    byte ptr [rax+1Ch], 8
0x1800fce62  jz      loc_1800FD24F
0x1800fce68  cmp     byte ptr [rax+19h], 2
0x1800fce6c  jb      loc_1800FD24F
0x1800fce72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fce77  mov     edx, 12h
0x1800fce7c  lea     rcx, aFailedToCreate_231; "Failed to create section name with Stri"...
0x1800fce83  jmp     loc_1800FD0C1
0x1800fce88  xor     edx, edx; bInheritHandle
0x1800fce8a  lea     r8, [rbp+1F0h+Name]; lpName
0x1800fce8e  lea     ecx, [rdx+4]; dwDesiredAccess
0x1800fce91  call    cs:__imp_OpenFileMappingW
0x1800fce97  mov     [rsp+2F0h+hObject], rax
0x1800fce9c  test    rax, rax
0x1800fce9f  jnz     loc_1800FD0EE
0x1800fcea5  mov     rax, cs:WPP_GLOBAL_Control
0x1800fceac  mov     edi, 80070000h
0x1800fceb1  cmp     rax, r13
0x1800fceb4  jz      short loc_1800FCEFB
0x1800fceb6  test    byte ptr [rax+1Ch], 8
0x1800fceba  jz      short loc_1800FCEFB
0x1800fcebc  cmp     byte ptr [rax+19h], 2
0x1800fcec0  jb      short loc_1800FCEFB
0x1800fcec2  call    cs:__imp_GetLastError
0x1800fcec8  mov     ebx, eax
0x1800fceca  test    eax, eax
0x1800fcecc  jle     short loc_1800FCED3
0x1800fcece  movzx   ebx, ax
0x1800fced1  or      ebx, edi
0x1800fced3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fced8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fcedf  lea     r8, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids
0x1800fcee6  mov     edx, 13h
0x1800fceeb  mov     dword ptr [rsp+2F0h+dwNumberOfBytesToMap], ebx
0x1800fceef  mov     r9d, eax
0x1800fcef2  mov     rcx, [rcx+10h]
0x1800fcef6  call    WPP_SF_Dd
0x1800fcefb  call    cs:__imp_GetLastError
0x1800fcf01  mov     ebx, eax
0x1800fcf03  test    eax, eax
0x1800fcf05  jle     loc_1800FD24F
0x1800fcf0b  movzx   ebx, ax
0x1800fcf0e  or      ebx, edi
0x1800fcf10  jmp     loc_1800FD24F
0x1800fcf15  mov     rax, cs:WPP_GLOBAL_Control
0x1800fcf1c  cmp     rax, r13
0x1800fcf1f  jz      loc_1800FD24A
0x1800fcf25  test    byte ptr [rax+1Ch], 8
0x1800fcf29  jz      loc_1800FD24A
0x1800fcf2f  cmp     byte ptr [rax+19h], 2
0x1800fcf33  jb      loc_1800FD24A
0x1800fcf39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fcf3e  mov     edx, 11h
0x1800fcf43  jmp     loc_1800FD228
0x1800fcf48  xorps   xmm0, xmm0
0x1800fcf4b  lea     r8, [rsp+2F0h+lpsz]
0x1800fcf50  xorps   xmm1, xmm1
0x1800fcf53  lea     rdx, aHidefremoteapp; "HiDefRemoteAppContainerGUID"
0x1800fcf5a  mov     rcx, rdi
0x1800fcf5d  mov     rax, rbx
0x1800fcf60  movups  xmmword ptr [rsp+2F0h+var_278.Data1], xmm0
0x1800fcf65  movups  xmmword ptr [rbp+1F0h+pclsid.Data1], xmm1
0x1800fcf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcf6e  mov     ebx, eax
0x1800fcf70  test    eax, eax
0x1800fcf72  jns     short loc_1800FCFAE
0x1800fcf74  mov     rax, cs:WPP_GLOBAL_Control
0x1800fcf7b  cmp     rax, r13
0x1800fcf7e  jz      loc_1800FD24F
0x1800fcf84  test    byte ptr [rax+1Ch], 8
0x1800fcf88  jz      loc_1800FD24F
0x1800fcf8e  cmp     byte ptr [rax+19h], 2
0x1800fcf92  jb      loc_1800FD24F
0x1800fcf98  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fcf9d  mov     edx, 14h
0x1800fcfa2  lea     rcx, aGetstringprope_44; "GetStringProperty(TS_PROP_CORE_HIDEF_RE"...
0x1800fcfa9  jmp     loc_1800FD0C1
0x1800fcfae  mov     rax, [rsp+2F0h+lpsz]
0x1800fcfb3  test    rax, rax
0x1800fcfb6  jz      loc_1800FD206
0x1800fcfbc  cmp     [rax], r12w
0x1800fcfc0  jz      loc_1800FD206
0x1800fcfc6  mov     rax, [r14]
0x1800fcfc9  mov     rcx, r14
0x1800fcfcc  mov     rax, [rax+18h]
0x1800fcfd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcfd5  mov     rcx, rax; lpsz
0x1800fcfd8  lea     rdx, [rbp+1F0h+pclsid]; pclsid
0x1800fcfdc  call    cs:__imp_CLSIDFromString
0x1800fcfe2  mov     ebx, eax
0x1800fcfe4  test    eax, eax
0x1800fcfe6  jns     short loc_1800FD022
0x1800fcfe8  mov     rax, cs:WPP_GLOBAL_Control
0x1800fcfef  cmp     rax, r13
0x1800fcff2  jz      loc_1800FD24F
0x1800fcff8  test    byte ptr [rax+1Ch], 8
0x1800fcffc  jz      loc_1800FD24F
0x1800fd002  cmp     byte ptr [rax+19h], 2
0x1800fd006  jb      loc_1800FD24F
0x1800fd00c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fd011  mov     edx, 16h
0x1800fd016  lea     rcx, aFailedToConver_4; "Failed to convert section name to GUID"
0x1800fd01d  jmp     loc_1800FD0C1
0x1800fd022  mov     rcx, [rsp+2F0h+lpsz]; lpsz
0x1800fd027  lea     rdx, [rsp+2F0h+var_278]; pclsid
0x1800fd02c  call    cs:__imp_CLSIDFromString
0x1800fd032  mov     ebx, eax
0x1800fd034  test    eax, eax
0x1800fd036  jns     short loc_1800FD06F
0x1800fd038  mov     rax, cs:WPP_GLOBAL_Control
0x1800fd03f  cmp     rax, r13
0x1800fd042  jz      loc_1800FD24F
0x1800fd048  test    byte ptr [rax+1Ch], 8
0x1800fd04c  jz      loc_1800FD24F
0x1800fd052  cmp     byte ptr [rax+19h], 2
0x1800fd056  jb      loc_1800FD24F
0x1800fd05c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fd061  mov     edx, 17h
0x1800fd066  lea     rcx, aFailedToConver_10; "Failed to convert Vm Guid string to GUI"...
0x1800fd06d  jmp     short loc_1800FD0C1
0x1800fd06f  lea     r8, [rsp+2F0h+var_278]
0x1800fd074  lea     rdx, [rbp+1F0h+pclsid]
0x1800fd078  lea     rcx, [rsp+2F0h+hObject]; SectionHandle
0x1800fd07d  call    OpenVmSharedMemorySection
0x1800fd082  mov     ebx, eax
0x1800fd084  or      ebx, 10000000h
0x1800fd08a  jge     short loc_1800FD0E9
0x1800fd08c  mov     rax, cs:WPP_GLOBAL_Control
0x1800fd093  cmp     rax, r13
0x1800fd096  jz      loc_1800FD24F
0x1800fd09c  test    byte ptr [rax+1Ch], 8
0x1800fd0a0  jz      loc_1800FD24F
0x1800fd0a6  cmp     byte ptr [rax+19h], 2
0x1800fd0aa  jb      loc_1800FD24F
0x1800fd0b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fd0b5  mov     edx, 18h
0x1800fd0ba  lea     rcx, aFailedToCreate_39; "Failed to create VM shared memory secti"...
0x1800fd0c1  mov     [rsp+2F0h+var_2C8], ebx
0x1800fd0c5  lea     r8, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids
0x1800fd0cc  mov     [rsp+2F0h+dwNumberOfBytesToMap], rcx
0x1800fd0d1  mov     r9d, eax
0x1800fd0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd0db  mov     rcx, [rcx+10h]
0x1800fd0df  call    WPP_SF_DsD
0x1800fd0e4  jmp     loc_1800FD24F
0x1800fd0e9  mov     rax, [rsp+2F0h+hObject]
0x1800fd0ee  xor     r9d, r9d; dwFileOffsetLow
0x1800fd0f1  mov     [rsp+2F0h+dwNumberOfBytesToMap], r12; dwNumberOfBytesToMap
0x1800fd0f6  xor     r8d, r8d; dwFileOffsetHigh
0x1800fd0f9  mov     rcx, rax; hFileMappingObject
0x1800fd0fc  lea     edx, [r9+4]; dwDesiredAccess
0x1800fd100  call    cs:__imp_MapViewOfFile
0x1800fd106  mov     rdi, rax
0x1800fd109  test    rax, rax
0x1800fd10c  jnz     short loc_1800FD159
0x1800fd10e  mov     rax, cs:WPP_GLOBAL_Control
0x1800fd115  cmp     rax, r13
0x1800fd118  jz      loc_1800FD24A
0x1800fd11e  test    byte ptr [rax+1Ch], 40h
0x1800fd122  jz      loc_1800FD24A
0x1800fd128  cmp     byte ptr [rax+19h], 2
0x1800fd12c  jb      loc_1800FD24A
0x1800fd132  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fd137  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd13e  lea     edx, [rdi+1Ah]
0x1800fd141  mov     r9d, eax
0x1800fd144  lea     r8, WPP_e4abe435090c3be44d2c881aae813c99_Traceguids
0x1800fd14b  mov     rcx, [rcx+10h]
0x1800fd14f  call    WPP_SF_d
0x1800fd154  jmp     loc_1800FD24A
0x1800fd159  mov     r8d, 30h ; '0'; dwLength
0x1800fd15f  lea     rdx, [rsp+2F0h+Buffer]; lpBuffer
0x1800fd164  mov     rcx, rdi; lpAddress
0x1800fd167  call    cs:__imp_VirtualQuery
0x1800fd16d  test    rax, rax
0x1800fd170  jz      short loc_1800FD1BA
0x1800fd172  mov     eax, dword ptr [rsp+2F0h+Buffer.RegionSize]
0x1800fd176  mov     rcx, [rbp+1F0h+arg_20]
0x1800fd17d  cmp     rax, rcx
0x1800fd180  jnb     short loc_1800FD1A6
0x1800fd182  mov     rax, cs:WPP_GLOBAL_Control
0x1800fd189  cmp     rax, r13
0x1800fd18c  jz      short loc_1800FD1F6
0x1800fd18e  test    byte ptr [rax+1Ch], 40h
0x1800fd192  jz      short loc_1800FD1F6
0x1800fd194  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
