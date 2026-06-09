# CTscSettings::LoadDrives(void)

- ea: `0x1400382f8`
- end: `0x140038a6f`
- name: `?LoadDrives@CTscSettings@@AEAAJXZ`
- size: `1911`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ba18`

## callees

- `0x1400043c4`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000d078`
- `0x14000dcac`
- `0x1400382f8`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `SHLWAPI!StrStrIW` at `0x140038934`
- `SHLWAPI!StrStrIW` at `0x140038934`
- `KERNEL32!CompareStringOrdinal` at `0x14003881f`
- `KERNEL32!CompareStringOrdinal` at `0x14003881f`
- `KERNEL32!lstrcmpW` at `0x140038502`
- `KERNEL32!lstrcmpW` at `0x140038516`
- `KERNEL32!lstrcmpW` at `0x140038502`
- `KERNEL32!lstrcmpW` at `0x140038516`
- `OLEAUT32!__imp_SysFreeString` at `0x1400389a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400389a8`
- `OLEAUT32!__imp_SysStringLen` at `0x140038916`
- `OLEAUT32!__imp_SysStringLen` at `0x140038916`

## string_xrefs

- `0x1400384ea`: `StringCchCopy failed`

## pseudocode

```c
__int64 __fastcall CTscSettings::LoadDrives(CTscSettings *this)
{
  unsigned int v1; // r13d
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  int v8; // ebx
  int v9; // eax
  wchar_t **v10; // r8
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  int v19; // edx
  wchar_t *v20; // r15
  wchar_t **v21; // r8
  int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // rcx
  __int64 v27; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Delimiter[4]; // [rsp+48h] [rbp-B8h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR String1[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = 0;
  wcscpy(Delimiter, L";");
  v33 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27150);
  v30 = 0;
  v29 = 0;
  if ( !v3 )
  {
    v4 = 1;
    goto LABEL_31;
  }
  v4 = (**v3)(v3, &IID_IMsRdpClientNonScriptable3, &v33);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 504;
    v7 = "QI for IMsRdpClientNonScriptable3 failed!";
    goto LABEL_8;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 240LL))(v33, &v30);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 505;
    v7 = "IMsRdpClient5::get_DriveCollection failed!";
    goto LABEL_8;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v30 + 40LL))(v30, &v29);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 506;
    v7 = "IMsRdpDriveCollection::GetDriveCount failed";
    goto LABEL_8;
  }
  v4 = StringCchCopyW(String1, 0x400u, (const unsigned __int16 *)this + 25198);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 507;
    v7 = "StringCchCopy failed";
LABEL_8:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v7,
      v4);
    goto LABEL_31;
  }
  v8 = lstrcmpW(String1, L"-");
  v9 = lstrcmpW(String1, L"*");
  v11 = 0;
  if ( !v8 )
  {
    if ( v29 )
    {
      while ( 1 )
      {
        v28 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 32LL))(v30, v11, &v28);
        if ( v4 < 0 )
          break;
        LOWORD(v12) = -(*((_DWORD *)this + 11561) != 0);
        v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 32LL))(v28, v12);
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 509;
            goto LABEL_40;
          }
          goto LABEL_102;
        }
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
        if ( ++v11 >= v29 )
          goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 508;
        goto LABEL_45;
      }
      goto LABEL_102;
    }
LABEL_29:
    *((_DWORD *)this + 11568) = *((_DWORD *)this + 11561);
    goto LABEL_30;
  }
  if ( !v9 )
  {
    if ( v29 )
    {
      while ( 1 )
      {
        v28 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 32LL))(v30, v11, &v28);
        if ( v4 < 0 )
          break;
        v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 32LL))(v28, 0xFFFFFFFFLL);
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 511;
            goto LABEL_40;
          }
          goto LABEL_102;
        }
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
        if ( ++v11 >= v29 )
          goto LABEL_52;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 510;
        goto LABEL_45;
      }
      goto LABEL_102;
    }
LABEL_52:
    *((_DWORD *)this + 11568) = 1;
    goto LABEL_30;
  }
  if ( v29 )
  {
    do
    {
      v28 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 32LL))(v30, v11, &v28);
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 512;
LABEL_45:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
            v18,
            (__int64)"IMsRdpDriveCollection::get_DriveByIndex failed!",
            v4);
        }
        goto LABEL_102;
      }
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 32LL))(v28, 0);
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 513;
LABEL_40:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
            v16,
            (__int64)"IMsRdpDrive::put_RedirectionState failed!",
            v4);
        }
        goto LABEL_102;
      }
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
      ++v11;
    }
    while ( v11 < v29 );
  }
  *((_DWORD *)this + 11568) = 0;
  v20 = wcstok_mvcrt_legacy_two_parameter_form(String1, Delimiter, v10);
  if ( !v20 )
  {
LABEL_30:
    v4 = 0;
    goto LABEL_31;
  }
  while ( CompareStringOrdinal(v20, -1, L"DynamicDrives", -1, 1) == 2 )
  {
    *((_DWORD *)this + 11568) = 1;
LABEL_91:
    v20 = wcstok_mvcrt_legacy_two_parameter_form(0, Delimiter, v21);
    if ( !v20 )
      goto LABEL_30;
  }
  if ( !v29 )
  {
LABEL_90:
    v1 = 0;
    goto LABEL_91;
  }
  while ( 1 )
  {
    pbstr = 0;
    v28 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 32LL))(v30, v1, &v28);
    if ( v4 < 0 )
      break;
    v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 24LL))(v28, &pbstr);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        v25 = 515;
        v26 = "IMsRdpDrive::get_Name failed!";
LABEL_101:
        LODWORD(v27) = v4;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
          v24,
          (__int64)v26,
          v27);
        goto LABEL_102;
      }
      goto LABEL_102;
    }
    if ( SysStringLen(pbstr) >= 3 )
      pbstr[2] = 0;
    if ( StrStrIW(v20, pbstr) )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 32LL))(v28, 0xFFFFFFFFLL);
      if ( v22 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v27) = v22;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          516,
          (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
          v23,
          (__int64)"IMsRdpDrive::put_RedirectionState failed!",
          v27);
      }
    }
    if ( pbstr )
      SysFreeString(pbstr);
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
    if ( ++v1 >= v29 )
      goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 514;
    v26 = "IMsRdpDriveCollection::get_DriveByIndex failed!";
    goto LABEL_101;
  }
LABEL_102:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
LABEL_31:
  v13 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400382f8  mov     [rsp-8+arg_8], rbx
0x1400382fd  mov     [rsp-8+arg_10], rsi
0x140038302  push    rbp
0x140038303  push    rdi
0x140038304  push    r13
0x140038306  push    r14
0x140038308  push    r15
0x14003830a  lea     rbp, [rsp-770h]
0x140038312  sub     rsp, 870h
0x140038319  mov     rax, cs:__security_cookie
0x140038320  xor     rax, rsp
0x140038323  mov     [rbp+790h+var_30], rax
0x14003832a  xor     r13d, r13d
0x14003832d  mov     dword ptr [rsp+890h+Delimiter], 3Bh ; ';'
0x140038335  mov     rsi, rcx
0x140038338  mov     [rsp+890h+var_838], r13
0x14003833d  mov     rcx, [rcx+35070h]
0x140038344  mov     [rsp+890h+var_850], r13
0x140038349  mov     [rsp+890h+var_858], r13d
0x14003834e  test    rcx, rcx
0x140038351  jnz     short loc_14003835B
0x140038353  lea     ebx, [rcx+1]
0x140038356  jmp     loc_14003859C
0x14003835b  mov     rax, [rcx]
0x14003835e  lea     r8, [rsp+890h+var_838]
0x140038363  lea     rdx, IID_IMsRdpClientNonScriptable3
0x14003836a  mov     rax, [rax]
0x14003836d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038372  mov     ebx, eax
0x140038374  test    eax, eax
0x140038376  jns     short loc_1400383DC
0x140038378  mov     rax, cs:WPP_GLOBAL_Control
0x14003837f  lea     rdi, WPP_GLOBAL_Control
0x140038386  cmp     rax, rdi
0x140038389  jz      loc_14003859C
0x14003838f  test    byte ptr [rax+1Ch], 8
0x140038393  jz      loc_14003859C
0x140038399  cmp     byte ptr [rax+19h], 2
0x14003839d  jb      loc_14003859C
0x1400383a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400383a8  mov     edx, 1F8h
0x1400383ad  lea     rcx, aQiForImsrdpcli_0; "QI for IMsRdpClientNonScriptable3 faile"...
0x1400383b4  mov     dword ptr [rsp+890h+var_868], ebx
0x1400383b8  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x1400383bf  mov     qword ptr [rsp+890h+bIgnoreCase], rcx
0x1400383c4  mov     r9d, eax
0x1400383c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400383ce  mov     rcx, [rcx+10h]
0x1400383d2  call    WPP_SF_DsD
0x1400383d7  jmp     loc_14003859C
0x1400383dc  mov     rcx, [rsp+890h+var_838]
0x1400383e1  lea     rdx, [rsp+890h+var_850]
0x1400383e6  mov     rax, [rcx]
0x1400383e9  mov     rax, [rax+0F0h]
0x1400383f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400383f5  mov     ebx, eax
0x1400383f7  test    eax, eax
0x1400383f9  jns     short loc_14003843C
0x1400383fb  mov     rax, cs:WPP_GLOBAL_Control
0x140038402  lea     rdi, WPP_GLOBAL_Control
0x140038409  cmp     rax, rdi
0x14003840c  jz      loc_14003859C
0x140038412  test    byte ptr [rax+1Ch], 8
0x140038416  jz      loc_14003859C
0x14003841c  cmp     byte ptr [rax+19h], 2
0x140038420  jb      loc_14003859C
0x140038426  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003842b  mov     edx, 1F9h
0x140038430  lea     rcx, aImsrdpclient5G; "IMsRdpClient5::get_DriveCollection fail"...
0x140038437  jmp     loc_1400383B4
0x14003843c  mov     rcx, [rsp+890h+var_850]
0x140038441  lea     rdx, [rsp+890h+var_858]
0x140038446  mov     rax, [rcx]
0x140038449  mov     rax, [rax+28h]
0x14003844d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038452  mov     ebx, eax
0x140038454  test    eax, eax
0x140038456  jns     short loc_140038499
0x140038458  mov     rax, cs:WPP_GLOBAL_Control
0x14003845f  lea     rdi, WPP_GLOBAL_Control
0x140038466  cmp     rax, rdi
0x140038469  jz      loc_14003859C
0x14003846f  test    byte ptr [rax+1Ch], 8
0x140038473  jz      loc_14003859C
0x140038479  cmp     byte ptr [rax+19h], 2
0x14003847d  jb      loc_14003859C
0x140038483  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140038488  mov     edx, 1FAh
0x14003848d  lea     rcx, aImsrdpdrivecol; "IMsRdpDriveCollection::GetDriveCount fa"...
0x140038494  jmp     loc_1400383B4
0x140038499  lea     r8, [rsi+0C4DCh]; unsigned __int16 *
0x1400384a0  mov     edx, 400h; unsigned __int64
0x1400384a5  lea     rcx, [rsp+890h+String1]; unsigned __int16 *
0x1400384aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400384af  mov     ebx, eax
0x1400384b1  test    eax, eax
0x1400384b3  jns     short loc_1400384F6
0x1400384b5  mov     rax, cs:WPP_GLOBAL_Control
0x1400384bc  lea     rdi, WPP_GLOBAL_Control
0x1400384c3  cmp     rax, rdi
0x1400384c6  jz      loc_14003859C
0x1400384cc  test    byte ptr [rax+1Ch], 8
0x1400384d0  jz      loc_14003859C
0x1400384d6  cmp     byte ptr [rax+19h], 2
0x1400384da  jb      loc_14003859C
0x1400384e0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400384e5  mov     edx, 1FBh
0x1400384ea  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x1400384f1  jmp     loc_1400383B4
0x1400384f6  lea     rdx, asc_140124BF4; "-"
0x1400384fd  lea     rcx, [rsp+890h+String1]; lpString1
0x140038502  call    cs:__imp_lstrcmpW
0x140038508  lea     rdx, pszMore; "*"
0x14003850f  mov     ebx, eax
0x140038511  lea     rcx, [rsp+890h+String1]; lpString1
0x140038516  call    cs:__imp_lstrcmpW
0x14003851c  mov     edi, r13d
0x14003851f  test    ebx, ebx
0x140038521  jnz     loc_14003869C
0x140038527  cmp     [rsp+890h+var_858], r13d
0x14003852c  jbe     short loc_14003858D
0x14003852e  mov     rcx, [rsp+890h+var_850]
0x140038533  lea     r8, [rsp+890h+var_860]
0x140038538  mov     [rsp+890h+var_860], r13
0x14003853d  mov     edx, edi
0x14003853f  mov     rax, [rcx]
0x140038542  mov     rax, [rax+20h]
0x140038546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003854b  mov     ebx, eax
0x14003854d  test    eax, eax
0x14003854f  js      loc_14003863A
0x140038555  mov     eax, [rsi+0B4A4h]
0x14003855b  mov     rcx, [rsp+890h+var_860]
0x140038560  neg     eax
0x140038562  sbb     dx, dx
0x140038565  mov     r8, [rcx]
0x140038568  mov     rax, [r8+20h]
0x14003856c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038571  mov     ebx, eax
0x140038573  test    eax, eax
0x140038575  js      loc_1400385FF
0x14003857b  lea     rcx, [rsp+890h+var_860]
0x140038580  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140038585  inc     edi
0x140038587  cmp     edi, [rsp+890h+var_858]
0x14003858b  jb      short loc_14003852E
0x14003858d  mov     eax, [rsi+0B4A4h]
0x140038593  mov     [rsi+0B4C0h], eax
0x140038599  mov     ebx, r13d
0x14003859c  mov     rcx, [rsp+890h+var_850]
0x1400385a1  test    rcx, rcx
0x1400385a4  jz      short loc_1400385B7
0x1400385a6  mov     [rsp+890h+var_850], r13
0x1400385ab  mov     rax, [rcx]
0x1400385ae  mov     rax, [rax+10h]
0x1400385b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400385b7  mov     rcx, [rsp+890h+var_838]
0x1400385bc  test    rcx, rcx
0x1400385bf  jz      short loc_1400385D2
0x1400385c1  mov     [rsp+890h+var_838], r13
0x1400385c6  mov     rax, [rcx]
0x1400385c9  mov     rax, [rax+10h]
0x1400385cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400385d2  mov     eax, ebx
0x1400385d4  mov     rcx, [rbp+790h+var_30]
0x1400385db  xor     rcx, rsp; StackCookie
0x1400385de  call    __security_check_cookie
0x1400385e3  lea     r11, [rsp+890h+var_20]
0x1400385eb  mov     rbx, [r11+38h]
0x1400385ef  mov     rsi, [r11+40h]
0x1400385f3  mov     rsp, r11
0x1400385f6  pop     r15
0x1400385f8  pop     r14
0x1400385fa  pop     r13
0x1400385fc  pop     rdi
0x1400385fd  pop     rbp
0x1400385fe  retn
0x1400385ff  mov     rax, cs:WPP_GLOBAL_Control
0x140038606  lea     rdi, WPP_GLOBAL_Control
0x14003860d  cmp     rax, rdi
0x140038610  jz      short loc_14003868D
0x140038612  test    byte ptr [rax+1Ch], 8
0x140038616  jz      short loc_14003868D
0x140038618  cmp     byte ptr [rax+19h], 2
0x14003861c  jb      short loc_14003868D
0x14003861e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140038623  mov     edx, 1FDh
0x140038628  lea     r14, aImsrdpdrivePut; "IMsRdpDrive::put_RedirectionState faile"...
0x14003862f  mov     dword ptr [rsp+890h+var_868], ebx
0x140038633  mov     qword ptr [rsp+890h+bIgnoreCase], r14
0x140038638  jmp     short loc_140038673
0x14003863a  mov     rax, cs:WPP_GLOBAL_Control
0x140038641  lea     rdi, WPP_GLOBAL_Control
0x140038648  cmp     rax, rdi
0x14003864b  jz      short loc_14003868D
0x14003864d  test    byte ptr [rax+1Ch], 8
0x140038651  jz      short loc_14003868D
0x140038653  cmp     byte ptr [rax+19h], 2
0x140038657  jb      short loc_14003868D
0x140038659  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003865e  mov     edx, 1FCh
0x140038663  lea     rcx, aImsrdpdrivecol_1; "IMsRdpDriveCollection::get_DriveByIndex"...
0x14003866a  mov     dword ptr [rsp+890h+var_868], ebx
0x14003866e  mov     qword ptr [rsp+890h+bIgnoreCase], rcx
0x140038673  mov     rcx, cs:WPP_GLOBAL_Control
0x14003867a  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x140038681  mov     r9d, eax
0x140038684  mov     rcx, [rcx+10h]
0x140038688  call    WPP_SF_DsD
0x14003868d  lea     rcx, [rsp+890h+var_860]
0x140038692  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140038697  jmp     loc_14003859C
0x14003869c  test    eax, eax
0x14003869e  jnz     loc_14003877D
0x1400386a4  cmp     [rsp+890h+var_858], r13d
0x1400386a9  jbe     short loc_1400386FA
0x1400386ab  mov     rcx, [rsp+890h+var_850]
0x1400386b0  lea     r8, [rsp+890h+var_860]
0x1400386b5  mov     [rsp+890h+var_860], r13
0x1400386ba  mov     edx, edi
0x1400386bc  mov     rax, [rcx]
0x1400386bf  mov     rax, [rax+20h]
0x1400386c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400386c8  mov     ebx, eax
0x1400386ca  test    eax, eax
0x1400386cc  js      short loc_140038743
0x1400386ce  mov     rcx, [rsp+890h+var_860]
0x1400386d3  or      edx, 0FFFFFFFFh
0x1400386d6  mov     rax, [rcx]
0x1400386d9  mov     rax, [rax+20h]
0x1400386dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400386e2  mov     ebx, eax
0x1400386e4  test    eax, eax
0x1400386e6  js      short loc_140038709
0x1400386e8  lea     rcx, [rsp+890h+var_860]
0x1400386ed  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400386f2  inc     edi
0x1400386f4  cmp     edi, [rsp+890h+var_858]
0x1400386f8  jb      short loc_1400386AB
0x1400386fa  mov     dword ptr [rsi+0B4C0h], 1
0x140038704  jmp     loc_140038599
0x140038709  mov     rax, cs:WPP_GLOBAL_Control
0x140038710  lea     rdi, WPP_GLOBAL_Control
0x140038717  cmp     rax, rdi
0x14003871a  jz      loc_14003868D
0x140038720  test    byte ptr [rax+1Ch], 8
0x140038724  jz      loc_14003868D
0x14003872a  cmp     byte ptr [rax+19h], 2
0x14003872e  jb      loc_14003868D
0x140038734  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140038739  mov     edx, 1FFh
0x14003873e  jmp     loc_140038628
0x140038743  mov     rax, cs:WPP_GLOBAL_Control
0x14003874a  lea     rdi, WPP_GLOBAL_Control
0x140038751  cmp     rax, rdi
0x140038754  jz      loc_14003868D
0x14003875a  test    byte ptr [rax+1Ch], 8
0x14003875e  jz      loc_14003868D
0x140038764  cmp     byte ptr [rax+19h], 2
0x140038768  jb      loc_14003868D
0x14003876e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140038773  mov     edx, 1FEh
0x140038778  jmp     loc_140038663
0x14003877d  cmp     [rsp+890h+var_858], r13d
0x140038782  jbe     short loc_1400387D6
0x140038784  mov     rcx, [rsp+890h+var_850]
0x140038789  lea     r8, [rsp+890h+var_860]
0x14003878e  mov     [rsp+890h+var_860], r13
0x140038793  mov     edx, edi
0x140038795  mov     rax, [rcx]
0x140038798  mov     rax, [rax+20h]
0x14003879c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400387a1  mov     ebx, eax
0x1400387a3  test    eax, eax
0x1400387a5  js      loc_140038877
0x1400387ab  mov     rcx, [rsp+890h+var_860]
0x1400387b0  xor     edx, edx
0x1400387b2  mov     rax, [rcx]
0x1400387b5  mov     rax, [rax+20h]
0x1400387b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400387be  mov     ebx, eax
0x1400387c0  test    eax, eax
0x1400387c2  js      short loc_14003883D
0x1400387c4  lea     rcx, [rsp+890h+var_860]
0x1400387c9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400387ce  inc     edi
0x1400387d0  cmp     edi, [rsp+890h+var_858]
0x1400387d4  jb      short loc_140038784
0x1400387d6  lea     rdx, [rsp+890h+Delimiter]; Delimiter
0x1400387db  mov     [rsi+0B4C0h], r13d
0x1400387e2  lea     rcx, [rsp+890h+String1]; String
0x1400387e7  call    wcstok_mvcrt_legacy_two_parameter_form
0x1400387ec  mov     r15, rax
0x1400387ef  test    rax, rax
0x1400387f2  jz      loc_140038599
0x1400387f8  lea     rdi, WPP_GLOBAL_Control
0x1400387ff  lea     r14, aImsrdpdrivePut; "IMsRdpDrive::put_RedirectionState faile"...
0x140038806  or      r9d, 0FFFFFFFFh; cchCount2
0x14003880a  mov     [rsp+890h+bIgnoreCase], 1; bIgnoreCase
0x140038812  or      edx, r9d; cchCount1
  ... truncated ...
```
