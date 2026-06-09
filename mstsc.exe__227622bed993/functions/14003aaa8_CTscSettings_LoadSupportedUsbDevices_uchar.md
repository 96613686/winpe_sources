# CTscSettings::LoadSupportedUsbDevices(uchar)

- ea: `0x14003aaa8`
- end: `0x14003b2b6`
- name: `?LoadSupportedUsbDevices@CTscSettings@@AEAAJE@Z`
- size: `2062`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003a128`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14000dcac`
- `0x14002d764`
- `0x14002d93c`
- `0x140033f78`
- `0x14003466c`
- `0x14003472c`
- `0x140034ac0`
- `0x140034f48`
- `0x140035bf0`
- `0x140036044`
- `0x14003aaa8`
- `0x14003e900`
- `0x1401111b2`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x14003acc8`
- `msvcrt!wcstok_s` at `0x14003ada3`
- `msvcrt!wcstok_s` at `0x14003afd5`
- `msvcrt!wcstok_s` at `0x14003b000`
- `msvcrt!wcstok_s` at `0x14003acc8`
- `msvcrt!wcstok_s` at `0x14003ada3`
- `msvcrt!wcstok_s` at `0x14003afd5`
- `msvcrt!wcstok_s` at `0x14003b000`
- `msvcrt!_wcsnicmp` at `0x14003b0f4`
- `msvcrt!_wcsnicmp` at `0x14003b0f4`
- `KERNEL32!CompareStringOrdinal` at `0x14003acfa`
- `KERNEL32!CompareStringOrdinal` at `0x14003acfa`
- `ole32!CLSIDFromString` at `0x14003adb5`
- `ole32!CLSIDFromString` at `0x14003ae7e`
- `ole32!CLSIDFromString` at `0x14003adb5`
- `ole32!CLSIDFromString` at `0x14003ae7e`

## string_xrefs

- `0x14003acae`: `StringCchCopy failed`

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
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
            (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v15);
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
                      (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 449, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v24);
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
0x14003aaa8  push    rbp
0x14003aaaa  push    rbx
0x14003aaab  push    rdi
0x14003aaac  push    r12
0x14003aaae  push    r14
0x14003aab0  push    r15
0x14003aab2  lea     rbp, [rsp-828h]
0x14003aaba  sub     rsp, 928h
0x14003aac1  mov     rax, cs:__security_cookie
0x14003aac8  xor     rax, rsp
0x14003aacb  mov     [rbp+850h+var_40], rax
0x14003aad2  xor     r15d, r15d
0x14003aad5  mov     qword ptr [rbp+850h+Buf1.Data1], rcx
0x14003aad9  mov     r12, rcx
0x14003aadc  mov     [rsp+950h+var_8F0], r15
0x14003aae1  mov     rcx, [rcx+35070h]
0x14003aae8  xorps   xmm0, xmm0
0x14003aaeb  mov     [rsp+950h+var_908], r15
0x14003aaf0  mov     dil, dl
0x14003aaf3  mov     [rsp+950h+var_900], r15d
0x14003aaf8  mov     dword ptr [rsp+950h+Delimiter], 3Bh ; ';'
0x14003ab00  mov     [rsp+950h+Context], r15
0x14003ab05  movups  xmmword ptr [rbp+850h+pclsid.Data1], xmm0
0x14003ab09  test    rcx, rcx
0x14003ab0c  jnz     short loc_14003AB16
0x14003ab0e  lea     ebx, [rcx+1]
0x14003ab11  jmp     loc_14003B25C
0x14003ab16  mov     rax, [rcx]
0x14003ab19  lea     r8, [rsp+950h+var_8F0]
0x14003ab1e  lea     rdx, IID_IMsRdpClientNonScriptable3
0x14003ab25  mov     rax, [rax]
0x14003ab28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ab2d  mov     ebx, eax
0x14003ab2f  test    eax, eax
0x14003ab31  jns     short loc_14003AB97
0x14003ab33  mov     rax, cs:WPP_GLOBAL_Control
0x14003ab3a  lea     rdi, WPP_GLOBAL_Control
0x14003ab41  cmp     rax, rdi
0x14003ab44  jz      loc_14003B25C
0x14003ab4a  test    byte ptr [rax+1Ch], 8
0x14003ab4e  jz      loc_14003B25C
0x14003ab54  cmp     byte ptr [rax+19h], 2
0x14003ab58  jb      loc_14003B25C
0x14003ab5e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ab63  mov     edx, 1B7h
0x14003ab68  lea     rcx, aQiForImsrdpcli_0; "QI for IMsRdpClientNonScriptable3 faile"...
0x14003ab6f  mov     [rsp+950h+var_928], ebx
0x14003ab73  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x14003ab7a  mov     qword ptr [rsp+950h+bIgnoreCase], rcx
0x14003ab7f  mov     r9d, eax
0x14003ab82  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab89  mov     rcx, [rcx+10h]
0x14003ab8d  call    WPP_SF_DsD
0x14003ab92  jmp     loc_14003B25C
0x14003ab97  mov     rcx, [rsp+950h+var_8F0]
0x14003ab9c  lea     rdx, [rsp+950h+var_908]
0x14003aba1  mov     rax, [rcx]
0x14003aba4  mov     rax, [rax+0E8h]
0x14003abab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003abb0  mov     ebx, eax
0x14003abb2  test    eax, eax
0x14003abb4  jns     short loc_14003ABF7
0x14003abb6  mov     rax, cs:WPP_GLOBAL_Control
0x14003abbd  lea     rdi, WPP_GLOBAL_Control
0x14003abc4  cmp     rax, rdi
0x14003abc7  jz      loc_14003B25C
0x14003abcd  test    byte ptr [rax+1Ch], 8
0x14003abd1  jz      loc_14003B25C
0x14003abd7  cmp     byte ptr [rax+19h], 2
0x14003abdb  jb      loc_14003B25C
0x14003abe1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003abe6  mov     edx, 1B8h
0x14003abeb  lea     rcx, aImsrdpclient5G_0; "IMsRdpClient5::get_DeviceCollection fai"...
0x14003abf2  jmp     loc_14003AB6F
0x14003abf7  mov     rcx, [rsp+950h+var_908]
0x14003abfc  lea     rdx, [rsp+950h+var_900]
0x14003ac01  mov     rax, [rcx]
0x14003ac04  mov     rax, [rax+30h]
0x14003ac08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac0d  mov     ebx, eax
0x14003ac0f  test    eax, eax
0x14003ac11  jns     short loc_14003AC54
0x14003ac13  mov     rax, cs:WPP_GLOBAL_Control
0x14003ac1a  lea     rdi, WPP_GLOBAL_Control
0x14003ac21  cmp     rax, rdi
0x14003ac24  jz      loc_14003B25C
0x14003ac2a  test    byte ptr [rax+1Ch], 8
0x14003ac2e  jz      loc_14003B25C
0x14003ac34  cmp     byte ptr [rax+19h], 2
0x14003ac38  jb      loc_14003B25C
0x14003ac3e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ac43  mov     edx, 1B9h
0x14003ac48  lea     rcx, aImsrdpdeviceco_3; "IMsRdpDeviceCollection::GetDeviceCount "...
0x14003ac4f  jmp     loc_14003AB6F
0x14003ac54  test    dil, dil
0x14003ac57  jz      loc_14003AF8E
0x14003ac5d  lea     r8, [r12+0BCDCh]; unsigned __int16 *
0x14003ac65  mov     edx, 400h; unsigned __int64
0x14003ac6a  lea     rcx, [rbp+850h+String]; unsigned __int16 *
0x14003ac6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003ac73  mov     ebx, eax
0x14003ac75  test    eax, eax
0x14003ac77  jns     short loc_14003ACBA
0x14003ac79  mov     rax, cs:WPP_GLOBAL_Control
0x14003ac80  lea     rdi, WPP_GLOBAL_Control
0x14003ac87  cmp     rax, rdi
0x14003ac8a  jz      loc_14003B25C
0x14003ac90  test    byte ptr [rax+1Ch], 8
0x14003ac94  jz      loc_14003B25C
0x14003ac9a  cmp     byte ptr [rax+19h], 2
0x14003ac9e  jb      loc_14003B25C
0x14003aca4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003aca9  mov     edx, 1BAh
0x14003acae  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x14003acb5  jmp     loc_14003AB6F
0x14003acba  lea     r8, [rsp+950h+Context]; Context
0x14003acbf  lea     rdx, [rsp+950h+Delimiter]; Delimiter
0x14003acc4  lea     rcx, [rbp+850h+String]; String
0x14003acc8  call    cs:__imp_wcstok_s
0x14003acce  lea     rdi, WPP_GLOBAL_Control
0x14003acd5  mov     rbx, rax
0x14003acd8  test    rax, rax
0x14003acdb  jz      loc_14003B259
0x14003ace1  or      r9d, 0FFFFFFFFh; cchCount2
0x14003ace5  mov     [rsp+950h+bIgnoreCase], 1; bIgnoreCase
0x14003aced  or      edx, r9d; cchCount1
0x14003acf0  lea     r8, pszMore; "*"
0x14003acf7  mov     rcx, rax; lpString1
0x14003acfa  call    cs:__imp_CompareStringOrdinal
0x14003ad00  cmp     eax, 2
0x14003ad03  jnz     loc_14003ADAE
0x14003ad09  mov     r14d, r15d
0x14003ad0c  cmp     r14d, [rsp+950h+var_900]
0x14003ad11  jnb     short loc_14003AD8B
0x14003ad13  mov     rcx, [rsp+950h+var_908]
0x14003ad18  lea     r8, [rsp+950h+var_918]
0x14003ad1d  mov     [rsp+950h+var_918], r15
0x14003ad22  mov     edx, r14d
0x14003ad25  mov     rax, [rcx]
0x14003ad28  mov     rax, [rax+20h]
0x14003ad2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad31  mov     ebx, eax
0x14003ad33  test    eax, eax
0x14003ad35  js      loc_14003AF0F
0x14003ad3b  mov     r8, [rsp+950h+var_918]; struct IMsRdpDevice *
0x14003ad40  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ad44  mov     rdx, [rsp+950h+var_908]; struct IMsRdpDeviceCollection *
0x14003ad49  call    ??0CMsRdpDeviceHelp@@QEAA@PEAUIMsRdpDeviceCollection@@PEAUIMsRdpDevice@@@Z; CMsRdpDeviceHelp::CMsRdpDeviceHelp(IMsRdpDeviceCollection *,IMsRdpDevice *)
0x14003ad4e  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ad52  call    ?IsUsbDevice@CMsRdpDeviceHelp@@QEAAEXZ; CMsRdpDeviceHelp::IsUsbDevice(void)
0x14003ad57  test    al, al
0x14003ad59  jz      short loc_14003AD73
0x14003ad5b  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ad5f  call    ?IsOptionalDevice@CMsRdpDeviceHelp@@QEAAEXZ; CMsRdpDeviceHelp::IsOptionalDevice(void)
0x14003ad64  test    al, al
0x14003ad66  jnz     short loc_14003AD73
0x14003ad68  mov     dl, 1; unsigned __int8
0x14003ad6a  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ad6e  call    ?SetRedirectionState@CMsRdpDeviceHelp@@QEAAXE@Z; CMsRdpDeviceHelp::SetRedirectionState(uchar)
0x14003ad73  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ad77  call    ??1CMsRdpDeviceHelp@@QEAA@XZ; CMsRdpDeviceHelp::~CMsRdpDeviceHelp(void)
0x14003ad7c  lea     rcx, [rsp+950h+var_918]
0x14003ad81  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14003ad86  inc     r14d
0x14003ad89  jmp     short loc_14003AD0C
0x14003ad8b  mov     dword ptr [r12+0B4C8h], 1
0x14003ad97  lea     r8, [rsp+950h+Context]; Context
0x14003ad9c  xor     ecx, ecx; String
0x14003ad9e  lea     rdx, [rsp+950h+Delimiter]; Delimiter
0x14003ada3  call    cs:__imp_wcstok_s
0x14003ada9  jmp     loc_14003ACD5
0x14003adae  lea     rdx, [rbp+850h+pclsid]; pclsid
0x14003adb2  mov     rcx, rbx; lpsz
0x14003adb5  call    cs:__imp_CLSIDFromString
0x14003adbb  test    eax, eax
0x14003adbd  js      short loc_14003AD97
0x14003adbf  mov     r14d, r15d
0x14003adc2  cmp     r14d, [rsp+950h+var_900]
0x14003adc7  jnb     short loc_14003AD97
0x14003adc9  mov     rcx, [rsp+950h+var_908]
0x14003adce  lea     r8, [rsp+950h+var_918]
0x14003add3  mov     [rsp+950h+var_918], r15
0x14003add8  mov     edx, r14d
0x14003addb  mov     rax, [rcx]
0x14003adde  mov     rax, [rax+20h]
0x14003ade2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ade7  mov     ebx, eax
0x14003ade9  test    eax, eax
0x14003adeb  js      loc_14003AF6A
0x14003adf1  mov     r8, [rsp+950h+var_918]; struct IMsRdpDevice *
0x14003adf6  lea     rcx, [rbp+850h+var_8D0]; this
0x14003adfa  mov     rdx, [rsp+950h+var_908]; struct IMsRdpDeviceCollection *
0x14003adff  call    ??0CMsRdpDeviceHelp@@QEAA@PEAUIMsRdpDeviceCollection@@PEAUIMsRdpDevice@@@Z; CMsRdpDeviceHelp::CMsRdpDeviceHelp(IMsRdpDeviceCollection *,IMsRdpDevice *)
0x14003ae04  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ae08  call    ?IsUsbDevice@CMsRdpDeviceHelp@@QEAAEXZ; CMsRdpDeviceHelp::IsUsbDevice(void)
0x14003ae0d  test    al, al
0x14003ae0f  jz      loc_14003AEF4
0x14003ae15  lea     rcx, [rbp+850h+var_8D0]; this
0x14003ae19  call    ?GetClassGuid@CMsRdpDeviceHelp@@QEAAPEAGXZ; CMsRdpDeviceHelp::GetClassGuid(void)
0x14003ae1e  test    rax, rax
0x14003ae21  jnz     short loc_14003AE70
0x14003ae23  mov     rax, cs:WPP_GLOBAL_Control
0x14003ae2a  cmp     rax, rdi
0x14003ae2d  jz      loc_14003AEF4
0x14003ae33  test    byte ptr [rax+1Ch], 1
0x14003ae37  jz      loc_14003AEF4
0x14003ae3d  cmp     byte ptr [rax+19h], 2
0x14003ae41  jb      loc_14003AEF4
0x14003ae47  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ae4c  mov     edx, 1BDh
0x14003ae51  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae58  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x14003ae5f  mov     r9d, eax
0x14003ae62  mov     rcx, [rcx+10h]
0x14003ae66  call    WPP_SF_d
0x14003ae6b  jmp     loc_14003AEF4
0x14003ae70  xorps   xmm0, xmm0
0x14003ae73  lea     rdx, [rbp+850h+Buf1]; pclsid
0x14003ae77  mov     rcx, rax; lpsz
0x14003ae7a  movups  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x14003ae7e  call    cs:__imp_CLSIDFromString
0x14003ae84  test    eax, eax
0x14003ae86  jns     short loc_14003AEAC
0x14003ae88  mov     rax, cs:WPP_GLOBAL_Control
0x14003ae8f  cmp     rax, rdi
0x14003ae92  jz      short loc_14003AEF4
0x14003ae94  test    byte ptr [rax+1Ch], 1
0x14003ae98  jz      short loc_14003AEF4
0x14003ae9a  cmp     byte ptr [rax+19h], 2
0x14003ae9e  jb      short loc_14003AEF4
0x14003aea0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003aea5  mov     edx, 1BEh
0x14003aeaa  jmp     short loc_14003AE51
0x14003aeac  mov     r8d, 10h; Size
0x14003aeb2  lea     rdx, [rbp+850h+pclsid]; Buf2
0x14003aeb6  lea     rcx, [rbp+850h+Buf1]; Buf1
0x14003aeba  call    memcmp_0
0x14003aebf  test    eax, eax
0x14003aec1  jz      short loc_14003AEE9
0x14003aec3  lea     rcx, [rbp+850h+var_8D0]; this
0x14003aec7  call    ?GetCmDeviceInstance@CMsRdpDeviceHelp@@QEAAKXZ; CMsRdpDeviceHelp::GetCmDeviceInstance(void)
0x14003aecc  movaps  xmm0, xmmword ptr [rbp+850h+pclsid.Data1]
0x14003aed0  lea     r8, [rsp+950h+var_8E0]; struct _GUID
0x14003aed5  mov     edx, eax; unsigned int
0x14003aed7  movdqa  xmmword ptr [rsp+950h+var_8E0.Data1], xmm0
0x14003aedd  mov     rcx, r12; this
0x14003aee0  call    ?ChildDeviceHasClassGuid@CTscSettings@@AEAAEKU_GUID@@@Z; CTscSettings::ChildDeviceHasClassGuid(ulong,_GUID)
0x14003aee5  test    al, al
0x14003aee7  jz      short loc_14003AEF4
0x14003aee9  mov     dl, 1; unsigned __int8
0x14003aeeb  lea     rcx, [rbp+850h+var_8D0]; this
0x14003aeef  call    ?SetRedirectionState@CMsRdpDeviceHelp@@QEAAXE@Z; CMsRdpDeviceHelp::SetRedirectionState(uchar)
0x14003aef4  lea     rcx, [rbp+850h+var_8D0]; this
0x14003aef8  call    ??1CMsRdpDeviceHelp@@QEAA@XZ; CMsRdpDeviceHelp::~CMsRdpDeviceHelp(void)
0x14003aefd  lea     rcx, [rsp+950h+var_918]
0x14003af02  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14003af07  inc     r14d
0x14003af0a  jmp     loc_14003ADC2
0x14003af0f  mov     rax, cs:WPP_GLOBAL_Control
0x14003af16  cmp     rax, rdi
0x14003af19  jz      short loc_14003AF5B
0x14003af1b  test    byte ptr [rax+1Ch], 8
0x14003af1f  jz      short loc_14003AF5B
0x14003af21  cmp     byte ptr [rax+19h], 2
0x14003af25  jb      short loc_14003AF5B
0x14003af27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003af2c  mov     edx, 1BBh
0x14003af31  lea     rcx, aImsrdpdeviceco_1; "IMsRdpDeviceCollection::get_DeviceByInd"...
0x14003af38  mov     [rsp+950h+var_928], ebx
0x14003af3c  mov     qword ptr [rsp+950h+bIgnoreCase], rcx
0x14003af41  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x14003af48  mov     rcx, cs:WPP_GLOBAL_Control
0x14003af4f  mov     r9d, eax
0x14003af52  mov     rcx, [rcx+10h]
0x14003af56  call    WPP_SF_DsD
0x14003af5b  lea     rcx, [rsp+950h+var_918]
0x14003af60  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14003af65  jmp     loc_14003B25C
0x14003af6a  mov     rax, cs:WPP_GLOBAL_Control
0x14003af71  cmp     rax, rdi
0x14003af74  jz      short loc_14003AF5B
0x14003af76  test    byte ptr [rax+1Ch], 8
0x14003af7a  jz      short loc_14003AF5B
0x14003af7c  cmp     byte ptr [rax+19h], 2
0x14003af80  jb      short loc_14003AF5B
0x14003af82  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003af87  mov     edx, 1BCh
0x14003af8c  jmp     short loc_14003AF31
0x14003af8e  lea     rdi, WPP_GLOBAL_Control
0x14003af95  cmp     r15d, 2
0x14003af99  jnb     loc_14003B256
0x14003af9f  test    r15d, r15d
0x14003afa2  lea     r8, [r12+0BCDCh]; unsigned __int16 *
0x14003afaa  mov     edx, 400h; unsigned __int64
0x14003afaf  lea     rcx, [rbp+850h+String]; unsigned __int16 *
0x14003afb3  setz    [rsp+950h+var_920]
0x14003afb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003afbd  mov     ebx, eax
0x14003afbf  test    eax, eax
0x14003afc1  js      loc_14003B22F
  ... truncated ...
```
