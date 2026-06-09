# CTscSettings::LoadSupportedUsbDevices(uchar)

- ea: `0x14003c398`
- end: `0x14003cba6`
- name: `?LoadSupportedUsbDevices@CTscSettings@@AEAAJE@Z`
- size: `2062`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003ba18`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14000dcac`
- `0x14002d764`
- `0x14002d93c`
- `0x140033f98`
- `0x140035698`
- `0x140035758`
- `0x1400363b4`
- `0x14003683c`
- `0x1400374e0`
- `0x140037934`
- `0x14003c398`
- `0x1400408c4`
- `0x140113322`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x14003c5b8`
- `msvcrt!wcstok_s` at `0x14003c693`
- `msvcrt!wcstok_s` at `0x14003c8c5`
- `msvcrt!wcstok_s` at `0x14003c8f0`
- `msvcrt!wcstok_s` at `0x14003c5b8`
- `msvcrt!wcstok_s` at `0x14003c693`
- `msvcrt!wcstok_s` at `0x14003c8c5`
- `msvcrt!wcstok_s` at `0x14003c8f0`
- `msvcrt!_wcsnicmp` at `0x14003c9e4`
- `msvcrt!_wcsnicmp` at `0x14003c9e4`
- `KERNEL32!CompareStringOrdinal` at `0x14003c5ea`
- `KERNEL32!CompareStringOrdinal` at `0x14003c5ea`
- `ole32!CLSIDFromString` at `0x14003c6a5`
- `ole32!CLSIDFromString` at `0x14003c76e`
- `ole32!CLSIDFromString` at `0x14003c6a5`
- `ole32!CLSIDFromString` at `0x14003c76e`

## string_xrefs

- `0x14003c59e`: `StringCchCopy failed`

## pseudocode

```c
__int64 __fastcall CTscSettings::LoadSupportedUsbDevices(CTscSettings *this, char a2)
{
  unsigned int v2; // r15d
  CTscSettings *v3; // r12
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  wchar_t *i; // rax
  const OLECHAR *v11; // rbx
  unsigned int j; // r14d
  unsigned int k; // r14d
  const OLECHAR *ClassGuid; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int CmDeviceInstance; // eax
  unsigned int v18; // eax
  int v19; // edx
  wchar_t *m; // rax
  const wchar_t *v21; // r14
  unsigned int n; // r12d
  const wchar_t *DeviceInstanceId; // rcx
  unsigned int v24; // eax
  size_t v25; // r8
  unsigned __int64 v26; // rax
  unsigned int ii; // eax
  unsigned int v28; // eax
  struct IMsRdpDeviceCollection *v29; // rcx
  __int64 v30; // rcx
  bool v32; // [rsp+30h] [rbp-D0h]
  struct IMsRdpDevice *v33; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Delimiter[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct IMsRdpDeviceCollection *v35; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *Context; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[20]; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+94h] [rbp-6Ch]
  _BYTE v42[56]; // [rsp+B8h] [rbp-48h] BYREF
  GUID Buf1; // [rsp+F0h] [rbp-10h] BYREF
  GUID pclsid; // [rsp+100h] [rbp+0h] BYREF
  wchar_t String[1024]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  *(_QWORD *)&Buf1.Data1 = this;
  v3 = this;
  v38 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27150);
  v35 = 0;
  v36 = 0;
  wcscpy(Delimiter, L";");
  Context = 0;
  pclsid = 0;
  if ( !v4 )
  {
    v6 = 1;
    goto LABEL_113;
  }
  v6 = (**v4)(v4, &IID_IMsRdpClientNonScriptable3, &v38);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 439;
    v9 = "QI for IMsRdpClientNonScriptable3 failed!";
    goto LABEL_8;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, struct IMsRdpDeviceCollection **))(*(_QWORD *)v38 + 232LL))(v38, &v35);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 440;
    v9 = "IMsRdpClient5::get_DeviceCollection failed!";
    goto LABEL_8;
  }
  v6 = (*(__int64 (__fastcall **)(struct IMsRdpDeviceCollection *, unsigned int *))(*(_QWORD *)v35 + 48LL))(v35, &v36);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 441;
    v9 = "IMsRdpDeviceCollection::GetDeviceCount failed";
    goto LABEL_8;
  }
  if ( a2 )
  {
    v6 = StringCchCopyW(String, 0x400u, (const unsigned __int16 *)v3 + 24174);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_113;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 442;
LABEL_25:
      v9 = "StringCchCopy failed";
LABEL_8:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v9,
        v6);
      goto LABEL_113;
    }
    for ( i = wcstok_s(String, Delimiter, &Context); ; i = wcstok_s(0, Delimiter, &Context) )
    {
      v11 = i;
      if ( !i )
        goto LABEL_112;
      if ( CompareStringOrdinal(i, -1, L"*", -1, 1) == 2 )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= v36 )
          {
            *((_DWORD *)v3 + 11570) = 1;
            goto LABEL_37;
          }
          v33 = 0;
          v6 = (*(__int64 (__fastcall **)(struct IMsRdpDeviceCollection *, _QWORD, struct IMsRdpDevice **))(*(_QWORD *)v35 + 32LL))(
                 v35,
                 j,
                 &v33);
          if ( v6 < 0 )
            break;
          CMsRdpDeviceHelp::CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40, v35, v33);
          if ( CMsRdpDeviceHelp::IsUsbDevice((CMsRdpDeviceHelp *)v40)
            && !CMsRdpDeviceHelp::IsOptionalDevice((CMsRdpDeviceHelp *)v40) )
          {
            CMsRdpDeviceHelp::SetRedirectionState((CMsRdpDeviceHelp *)v40, 1u);
          }
          CMsRdpDeviceHelp::~CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40);
          TCntPtr<IXMLDOMNodeList>::SafeRelease(&v33);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 443;
LABEL_62:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
            v18,
            (__int64)"IMsRdpDeviceCollection::get_DeviceByIndex failed!",
            v6);
        }
LABEL_63:
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v33);
        goto LABEL_113;
      }
      if ( CLSIDFromString(v11, &pclsid) >= 0 )
        break;
LABEL_37:
      ;
    }
    for ( k = 0; ; ++k )
    {
      if ( k >= v36 )
        goto LABEL_37;
      v33 = 0;
      v6 = (*(__int64 (__fastcall **)(struct IMsRdpDeviceCollection *, _QWORD, struct IMsRdpDevice **))(*(_QWORD *)v35 + 32LL))(
             v35,
             k,
             &v33);
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 444;
          goto LABEL_62;
        }
        goto LABEL_63;
      }
      CMsRdpDeviceHelp::CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40, v35, v33);
      if ( CMsRdpDeviceHelp::IsUsbDevice((CMsRdpDeviceHelp *)v40) )
      {
        ClassGuid = CMsRdpDeviceHelp::GetClassGuid((CMsRdpDeviceHelp *)v40);
        if ( ClassGuid )
        {
          Buf1 = 0;
          if ( CLSIDFromString(ClassGuid, &Buf1) >= 0 )
          {
            if ( !memcmp_0(&Buf1, &pclsid, 0x10u)
              || (CmDeviceInstance = CMsRdpDeviceHelp::GetCmDeviceInstance((CMsRdpDeviceHelp *)v40),
                  v39 = pclsid,
                  CTscSettings::ChildDeviceHasClassGuid(v3, CmDeviceInstance, &v39)) )
            {
              CMsRdpDeviceHelp::SetRedirectionState((CMsRdpDeviceHelp *)v40, 1u);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            v16 = 446;
            goto LABEL_48;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 445;
LABEL_48:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids, v15);
        }
      }
      CMsRdpDeviceHelp::~CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40);
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&v33);
    }
  }
LABEL_68:
  if ( v2 >= 2 )
  {
LABEL_112:
    v6 = 0;
    goto LABEL_113;
  }
  v32 = v2 == 0;
  v6 = StringCchCopyW(String, 0x400u, (const unsigned __int16 *)v3 + 24174);
  if ( v6 >= 0 )
  {
    for ( m = wcstok_s(String, Delimiter, &Context); ; m = wcstok_s(0, Delimiter, &Context) )
    {
      v21 = m;
      if ( !m )
      {
        v3 = *(CTscSettings **)&Buf1.Data1;
        ++v2;
        goto LABEL_68;
      }
      if ( *m == 45 )
      {
        if ( !v2 )
          continue;
        v21 = m + 1;
      }
      else if ( v2 )
      {
        continue;
      }
      for ( n = 0; n < v36; ++n )
      {
        v33 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IMsRdpDeviceCollection *, _QWORD, struct IMsRdpDevice **))(*(_QWORD *)v35 + 32LL))(
               v35,
               n,
               &v33);
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            v19 = 448;
            goto LABEL_62;
          }
          goto LABEL_63;
        }
        CMsRdpDeviceHelp::CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40, v35, v33);
        if ( CMsRdpDeviceHelp::IsUsbDevice((CMsRdpDeviceHelp *)v40) )
        {
          DeviceInstanceId = CMsRdpDeviceHelp::GetDeviceInstanceId((CMsRdpDeviceHelp *)v40);
          if ( DeviceInstanceId )
          {
            v25 = -1;
            do
              ++v25;
            while ( v21[v25] );
            v26 = -1;
            do
              ++v26;
            while ( DeviceInstanceId[v26] );
            if ( v25 > v26 )
              v25 = v26;
            if ( !_wcsnicmp(DeviceInstanceId, v21, v25) )
            {
              CMsRdpDeviceHelp::SetRedirectionState((CMsRdpDeviceHelp *)v40, v32);
              CMsRdpDeviceHelp::GetCmDeviceInstance((CMsRdpDeviceHelp *)v40);
              v41 = 0;
              for ( ii = CMsRdpDeviceHelp::GetNextChildIndex((CMsRdpDeviceHelp *)v40);
                    ii != -1;
                    ii = CMsRdpDeviceHelp::GetNextChildIndex((CMsRdpDeviceHelp *)v40) )
              {
                *(_QWORD *)&v39.Data1 = 0;
                v6 = (*(__int64 (__fastcall **)(struct IMsRdpDeviceCollection *, _QWORD, struct _GUID *))(*(_QWORD *)v35 + 32LL))(
                       v35,
                       ii,
                       &v39);
                if ( v6 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      450,
                      (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
                      v28,
                      (__int64)"IMsRdpDeviceCollection::get_DeviceByIndex failed!",
                      v6);
                  }
                  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v39);
                  CMsRdpDeviceHelp::~CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40);
                  goto LABEL_63;
                }
                CMsRdpDeviceHelp::CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v42, v35, *(struct IMsRdpDevice **)&v39.Data1);
                CMsRdpDeviceHelp::SetRedirectionState((CMsRdpDeviceHelp *)v42, v32);
                CMsRdpDeviceHelp::~CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v42);
                TCntPtr<IXMLDOMNodeList>::SafeRelease(&v39);
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v24 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 449, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids, v24);
          }
        }
        CMsRdpDeviceHelp::~CMsRdpDeviceHelp((CMsRdpDeviceHelp *)v40);
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v33);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 447;
    goto LABEL_25;
  }
LABEL_113:
  v29 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(struct IMsRdpDeviceCollection *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003c398  push    rbp
0x14003c39a  push    rbx
0x14003c39b  push    rdi
0x14003c39c  push    r12
0x14003c39e  push    r14
0x14003c3a0  push    r15
0x14003c3a2  lea     rbp, [rsp-828h]
0x14003c3aa  sub     rsp, 928h
0x14003c3b1  mov     rax, cs:__security_cookie
0x14003c3b8  xor     rax, rsp
0x14003c3bb  mov     [rbp+850h+var_40], rax
0x14003c3c2  xor     r15d, r15d
0x14003c3c5  mov     qword ptr [rbp+850h+Buf1.Data1], rcx
0x14003c3c9  mov     r12, rcx
0x14003c3cc  mov     [rsp+950h+var_8F0], r15
0x14003c3d1  mov     rcx, [rcx+35070h]
0x14003c3d8  xorps   xmm0, xmm0
0x14003c3db  mov     [rsp+950h+var_908], r15
0x14003c3e0  mov     dil, dl
0x14003c3e3  mov     [rsp+950h+var_900], r15d
0x14003c3e8  mov     dword ptr [rsp+950h+Delimiter], 3Bh ; ';'
0x14003c3f0  mov     [rsp+950h+Context], r15
0x14003c3f5  movups  xmmword ptr [rbp+850h+pclsid.Data1], xmm0
0x14003c3f9  test    rcx, rcx
0x14003c3fc  jnz     short loc_14003C406
0x14003c3fe  lea     ebx, [rcx+1]
0x14003c401  jmp     loc_14003CB4C
0x14003c406  mov     rax, [rcx]
0x14003c409  lea     r8, [rsp+950h+var_8F0]
0x14003c40e  lea     rdx, IID_IMsRdpClientNonScriptable3
0x14003c415  mov     rax, [rax]
0x14003c418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c41d  mov     ebx, eax
0x14003c41f  test    eax, eax
0x14003c421  jns     short loc_14003C487
0x14003c423  mov     rax, cs:WPP_GLOBAL_Control
0x14003c42a  lea     rdi, WPP_GLOBAL_Control
0x14003c431  cmp     rax, rdi
0x14003c434  jz      loc_14003CB4C
0x14003c43a  test    byte ptr [rax+1Ch], 8
0x14003c43e  jz      loc_14003CB4C
0x14003c444  cmp     byte ptr [rax+19h], 2
0x14003c448  jb      loc_14003CB4C
0x14003c44e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c453  mov     edx, 1B7h
0x14003c458  lea     rcx, aQiForImsrdpcli_0; "QI for IMsRdpClientNonScriptable3 faile"...
0x14003c45f  mov     [rsp+950h+var_928], ebx
0x14003c463  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003c46a  mov     qword ptr [rsp+950h+bIgnoreCase], rcx
0x14003c46f  mov     r9d, eax
0x14003c472  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c479  mov     rcx, [rcx+10h]
0x14003c47d  call    WPP_SF_DsD
0x14003c482  jmp     loc_14003CB4C
0x14003c487  mov     rcx, [rsp+950h+var_8F0]
0x14003c48c  lea     rdx, [rsp+950h+var_908]
0x14003c491  mov     rax, [rcx]
0x14003c494  mov     rax, [rax+0E8h]
0x14003c49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c4a0  mov     ebx, eax
0x14003c4a2  test    eax, eax
0x14003c4a4  jns     short loc_14003C4E7
0x14003c4a6  mov     rax, cs:WPP_GLOBAL_Control
0x14003c4ad  lea     rdi, WPP_GLOBAL_Control
0x14003c4b4  cmp     rax, rdi
0x14003c4b7  jz      loc_14003CB4C
0x14003c4bd  test    byte ptr [rax+1Ch], 8
0x14003c4c1  jz      loc_14003CB4C
0x14003c4c7  cmp     byte ptr [rax+19h], 2
0x14003c4cb  jb      loc_14003CB4C
0x14003c4d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c4d6  mov     edx, 1B8h
0x14003c4db  lea     rcx, aImsrdpclient5G_0; "IMsRdpClient5::get_DeviceCollection fai"...
0x14003c4e2  jmp     loc_14003C45F
0x14003c4e7  mov     rcx, [rsp+950h+var_908]
0x14003c4ec  lea     rdx, [rsp+950h+var_900]
0x14003c4f1  mov     rax, [rcx]
0x14003c4f4  mov     rax, [rax+30h]
0x14003c4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c4fd  mov     ebx, eax
0x14003c4ff  test    eax, eax
0x14003c501  jns     short loc_14003C544
0x14003c503  mov     rax, cs:WPP_GLOBAL_Control
0x14003c50a  lea     rdi, WPP_GLOBAL_Control
0x14003c511  cmp     rax, rdi
0x14003c514  jz      loc_14003CB4C
0x14003c51a  test    byte ptr [rax+1Ch], 8
0x14003c51e  jz      loc_14003CB4C
0x14003c524  cmp     byte ptr [rax+19h], 2
0x14003c528  jb      loc_14003CB4C
0x14003c52e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c533  mov     edx, 1B9h
0x14003c538  lea     rcx, aImsrdpdeviceco_3; "IMsRdpDeviceCollection::GetDeviceCount "...
0x14003c53f  jmp     loc_14003C45F
0x14003c544  test    dil, dil
0x14003c547  jz      loc_14003C87E
0x14003c54d  lea     r8, [r12+0BCDCh]; unsigned __int16 *
0x14003c555  mov     edx, 400h; unsigned __int64
0x14003c55a  lea     rcx, [rbp+850h+String]; unsigned __int16 *
0x14003c55e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003c563  mov     ebx, eax
0x14003c565  test    eax, eax
0x14003c567  jns     short loc_14003C5AA
0x14003c569  mov     rax, cs:WPP_GLOBAL_Control
0x14003c570  lea     rdi, WPP_GLOBAL_Control
0x14003c577  cmp     rax, rdi
0x14003c57a  jz      loc_14003CB4C
0x14003c580  test    byte ptr [rax+1Ch], 8
0x14003c584  jz      loc_14003CB4C
0x14003c58a  cmp     byte ptr [rax+19h], 2
0x14003c58e  jb      loc_14003CB4C
0x14003c594  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c599  mov     edx, 1BAh
0x14003c59e  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x14003c5a5  jmp     loc_14003C45F
0x14003c5aa  lea     r8, [rsp+950h+Context]; Context
0x14003c5af  lea     rdx, [rsp+950h+Delimiter]; Delimiter
0x14003c5b4  lea     rcx, [rbp+850h+String]; String
0x14003c5b8  call    cs:__imp_wcstok_s
0x14003c5be  lea     rdi, WPP_GLOBAL_Control
0x14003c5c5  mov     rbx, rax
0x14003c5c8  test    rax, rax
0x14003c5cb  jz      loc_14003CB49
0x14003c5d1  or      r9d, 0FFFFFFFFh; cchCount2
0x14003c5d5  mov     [rsp+950h+bIgnoreCase], 1; bIgnoreCase
0x14003c5dd  or      edx, r9d; cchCount1
0x14003c5e0  lea     r8, pszMore; "*"
0x14003c5e7  mov     rcx, rax; lpString1
0x14003c5ea  call    cs:__imp_CompareStringOrdinal
0x14003c5f0  cmp     eax, 2
0x14003c5f3  jnz     loc_14003C69E
0x14003c5f9  mov     r14d, r15d
0x14003c5fc  cmp     r14d, [rsp+950h+var_900]
0x14003c601  jnb     short loc_14003C67B
0x14003c603  mov     rcx, [rsp+950h+var_908]
0x14003c608  lea     r8, [rsp+950h+var_918]
0x14003c60d  mov     [rsp+950h+var_918], r15
0x14003c612  mov     edx, r14d
0x14003c615  mov     rax, [rcx]
0x14003c618  mov     rax, [rax+20h]
0x14003c61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c621  mov     ebx, eax
0x14003c623  test    eax, eax
0x14003c625  js      loc_14003C7FF
0x14003c62b  mov     r8, [rsp+950h+var_918]; struct IMsRdpDevice *
0x14003c630  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c634  mov     rdx, [rsp+950h+var_908]; struct IMsRdpDeviceCollection *
0x14003c639  call    ??0CMsRdpDeviceHelp@@QEAA@PEAUIMsRdpDeviceCollection@@PEAUIMsRdpDevice@@@Z; CMsRdpDeviceHelp::CMsRdpDeviceHelp(IMsRdpDeviceCollection *,IMsRdpDevice *)
0x14003c63e  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c642  call    ?IsUsbDevice@CMsRdpDeviceHelp@@QEAAEXZ; CMsRdpDeviceHelp::IsUsbDevice(void)
0x14003c647  test    al, al
0x14003c649  jz      short loc_14003C663
0x14003c64b  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c64f  call    ?IsOptionalDevice@CMsRdpDeviceHelp@@QEAAEXZ; CMsRdpDeviceHelp::IsOptionalDevice(void)
0x14003c654  test    al, al
0x14003c656  jnz     short loc_14003C663
0x14003c658  mov     dl, 1; unsigned __int8
0x14003c65a  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c65e  call    ?SetRedirectionState@CMsRdpDeviceHelp@@QEAAXE@Z; CMsRdpDeviceHelp::SetRedirectionState(uchar)
0x14003c663  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c667  call    ??1CMsRdpDeviceHelp@@QEAA@XZ; CMsRdpDeviceHelp::~CMsRdpDeviceHelp(void)
0x14003c66c  lea     rcx, [rsp+950h+var_918]
0x14003c671  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14003c676  inc     r14d
0x14003c679  jmp     short loc_14003C5FC
0x14003c67b  mov     dword ptr [r12+0B4C8h], 1
0x14003c687  lea     r8, [rsp+950h+Context]; Context
0x14003c68c  xor     ecx, ecx; String
0x14003c68e  lea     rdx, [rsp+950h+Delimiter]; Delimiter
0x14003c693  call    cs:__imp_wcstok_s
0x14003c699  jmp     loc_14003C5C5
0x14003c69e  lea     rdx, [rbp+850h+pclsid]; pclsid
0x14003c6a2  mov     rcx, rbx; lpsz
0x14003c6a5  call    cs:__imp_CLSIDFromString
0x14003c6ab  test    eax, eax
0x14003c6ad  js      short loc_14003C687
0x14003c6af  mov     r14d, r15d
0x14003c6b2  cmp     r14d, [rsp+950h+var_900]
0x14003c6b7  jnb     short loc_14003C687
0x14003c6b9  mov     rcx, [rsp+950h+var_908]
0x14003c6be  lea     r8, [rsp+950h+var_918]
0x14003c6c3  mov     [rsp+950h+var_918], r15
0x14003c6c8  mov     edx, r14d
0x14003c6cb  mov     rax, [rcx]
0x14003c6ce  mov     rax, [rax+20h]
0x14003c6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c6d7  mov     ebx, eax
0x14003c6d9  test    eax, eax
0x14003c6db  js      loc_14003C85A
0x14003c6e1  mov     r8, [rsp+950h+var_918]; struct IMsRdpDevice *
0x14003c6e6  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c6ea  mov     rdx, [rsp+950h+var_908]; struct IMsRdpDeviceCollection *
0x14003c6ef  call    ??0CMsRdpDeviceHelp@@QEAA@PEAUIMsRdpDeviceCollection@@PEAUIMsRdpDevice@@@Z; CMsRdpDeviceHelp::CMsRdpDeviceHelp(IMsRdpDeviceCollection *,IMsRdpDevice *)
0x14003c6f4  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c6f8  call    ?IsUsbDevice@CMsRdpDeviceHelp@@QEAAEXZ; CMsRdpDeviceHelp::IsUsbDevice(void)
0x14003c6fd  test    al, al
0x14003c6ff  jz      loc_14003C7E4
0x14003c705  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c709  call    ?GetClassGuid@CMsRdpDeviceHelp@@QEAAPEAGXZ; CMsRdpDeviceHelp::GetClassGuid(void)
0x14003c70e  test    rax, rax
0x14003c711  jnz     short loc_14003C760
0x14003c713  mov     rax, cs:WPP_GLOBAL_Control
0x14003c71a  cmp     rax, rdi
0x14003c71d  jz      loc_14003C7E4
0x14003c723  test    byte ptr [rax+1Ch], 1
0x14003c727  jz      loc_14003C7E4
0x14003c72d  cmp     byte ptr [rax+19h], 2
0x14003c731  jb      loc_14003C7E4
0x14003c737  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c73c  mov     edx, 1BDh
0x14003c741  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c748  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003c74f  mov     r9d, eax
0x14003c752  mov     rcx, [rcx+10h]
0x14003c756  call    WPP_SF_d
0x14003c75b  jmp     loc_14003C7E4
0x14003c760  xorps   xmm0, xmm0
0x14003c763  lea     rdx, [rbp+850h+Buf1]; pclsid
0x14003c767  mov     rcx, rax; lpsz
0x14003c76a  movups  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x14003c76e  call    cs:__imp_CLSIDFromString
0x14003c774  test    eax, eax
0x14003c776  jns     short loc_14003C79C
0x14003c778  mov     rax, cs:WPP_GLOBAL_Control
0x14003c77f  cmp     rax, rdi
0x14003c782  jz      short loc_14003C7E4
0x14003c784  test    byte ptr [rax+1Ch], 1
0x14003c788  jz      short loc_14003C7E4
0x14003c78a  cmp     byte ptr [rax+19h], 2
0x14003c78e  jb      short loc_14003C7E4
0x14003c790  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c795  mov     edx, 1BEh
0x14003c79a  jmp     short loc_14003C741
0x14003c79c  mov     r8d, 10h; Size
0x14003c7a2  lea     rdx, [rbp+850h+pclsid]; Buf2
0x14003c7a6  lea     rcx, [rbp+850h+Buf1]; Buf1
0x14003c7aa  call    memcmp_0
0x14003c7af  test    eax, eax
0x14003c7b1  jz      short loc_14003C7D9
0x14003c7b3  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c7b7  call    ?GetCmDeviceInstance@CMsRdpDeviceHelp@@QEAAKXZ; CMsRdpDeviceHelp::GetCmDeviceInstance(void)
0x14003c7bc  movaps  xmm0, xmmword ptr [rbp+850h+pclsid.Data1]
0x14003c7c0  lea     r8, [rsp+950h+var_8E0]; struct _GUID
0x14003c7c5  mov     edx, eax; unsigned int
0x14003c7c7  movdqa  xmmword ptr [rsp+950h+var_8E0.Data1], xmm0
0x14003c7cd  mov     rcx, r12; this
0x14003c7d0  call    ?ChildDeviceHasClassGuid@CTscSettings@@AEAAEKU_GUID@@@Z; CTscSettings::ChildDeviceHasClassGuid(ulong,_GUID)
0x14003c7d5  test    al, al
0x14003c7d7  jz      short loc_14003C7E4
0x14003c7d9  mov     dl, 1; unsigned __int8
0x14003c7db  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c7df  call    ?SetRedirectionState@CMsRdpDeviceHelp@@QEAAXE@Z; CMsRdpDeviceHelp::SetRedirectionState(uchar)
0x14003c7e4  lea     rcx, [rbp+850h+var_8D0]; this
0x14003c7e8  call    ??1CMsRdpDeviceHelp@@QEAA@XZ; CMsRdpDeviceHelp::~CMsRdpDeviceHelp(void)
0x14003c7ed  lea     rcx, [rsp+950h+var_918]
0x14003c7f2  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14003c7f7  inc     r14d
0x14003c7fa  jmp     loc_14003C6B2
0x14003c7ff  mov     rax, cs:WPP_GLOBAL_Control
0x14003c806  cmp     rax, rdi
0x14003c809  jz      short loc_14003C84B
0x14003c80b  test    byte ptr [rax+1Ch], 8
0x14003c80f  jz      short loc_14003C84B
0x14003c811  cmp     byte ptr [rax+19h], 2
0x14003c815  jb      short loc_14003C84B
0x14003c817  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c81c  mov     edx, 1BBh
0x14003c821  lea     rcx, aImsrdpdeviceco_1; "IMsRdpDeviceCollection::get_DeviceByInd"...
0x14003c828  mov     [rsp+950h+var_928], ebx
0x14003c82c  mov     qword ptr [rsp+950h+bIgnoreCase], rcx
0x14003c831  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003c838  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c83f  mov     r9d, eax
0x14003c842  mov     rcx, [rcx+10h]
0x14003c846  call    WPP_SF_DsD
0x14003c84b  lea     rcx, [rsp+950h+var_918]
0x14003c850  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14003c855  jmp     loc_14003CB4C
0x14003c85a  mov     rax, cs:WPP_GLOBAL_Control
0x14003c861  cmp     rax, rdi
0x14003c864  jz      short loc_14003C84B
0x14003c866  test    byte ptr [rax+1Ch], 8
0x14003c86a  jz      short loc_14003C84B
0x14003c86c  cmp     byte ptr [rax+19h], 2
0x14003c870  jb      short loc_14003C84B
0x14003c872  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c877  mov     edx, 1BCh
0x14003c87c  jmp     short loc_14003C821
0x14003c87e  lea     rdi, WPP_GLOBAL_Control
0x14003c885  cmp     r15d, 2
0x14003c889  jnb     loc_14003CB46
0x14003c88f  test    r15d, r15d
0x14003c892  lea     r8, [r12+0BCDCh]; unsigned __int16 *
0x14003c89a  mov     edx, 400h; unsigned __int64
0x14003c89f  lea     rcx, [rbp+850h+String]; unsigned __int16 *
0x14003c8a3  setz    [rsp+950h+var_920]
0x14003c8a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003c8ad  mov     ebx, eax
0x14003c8af  test    eax, eax
0x14003c8b1  js      loc_14003CB1F
  ... truncated ...
```
