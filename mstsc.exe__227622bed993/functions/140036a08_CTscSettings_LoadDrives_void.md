# CTscSettings::LoadDrives(void)

- ea: `0x140036a08`
- end: `0x14003717f`
- name: `?LoadDrives@CTscSettings@@AEAAJXZ`
- size: `1911`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a128`

## callees

- `0x1400043c4`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000d078`
- `0x14000dcac`
- `0x140036a08`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `SHLWAPI!StrStrIW` at `0x140037044`
- `SHLWAPI!StrStrIW` at `0x140037044`
- `KERNEL32!CompareStringOrdinal` at `0x140036f2f`
- `KERNEL32!CompareStringOrdinal` at `0x140036f2f`
- `KERNEL32!lstrcmpW` at `0x140036c12`
- `KERNEL32!lstrcmpW` at `0x140036c26`
- `KERNEL32!lstrcmpW` at `0x140036c12`
- `KERNEL32!lstrcmpW` at `0x140036c26`
- `OLEAUT32!__imp_SysFreeString` at `0x1400370b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400370b8`
- `OLEAUT32!__imp_SysStringLen` at `0x140037026`
- `OLEAUT32!__imp_SysStringLen` at `0x140037026`

## string_xrefs

- `0x140036bfa`: `StringCchCopy failed`

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
      (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
            (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
            (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
          (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
          (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
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
0x140036a08  mov     [rsp-8+arg_8], rbx
0x140036a0d  mov     [rsp-8+arg_10], rsi
0x140036a12  push    rbp
0x140036a13  push    rdi
0x140036a14  push    r13
0x140036a16  push    r14
0x140036a18  push    r15
0x140036a1a  lea     rbp, [rsp-770h]
0x140036a22  sub     rsp, 870h
0x140036a29  mov     rax, cs:__security_cookie
0x140036a30  xor     rax, rsp
0x140036a33  mov     [rbp+790h+var_30], rax
0x140036a3a  xor     r13d, r13d
0x140036a3d  mov     dword ptr [rsp+890h+Delimiter], 3Bh ; ';'
0x140036a45  mov     rsi, rcx
0x140036a48  mov     [rsp+890h+var_838], r13
0x140036a4d  mov     rcx, [rcx+35070h]
0x140036a54  mov     [rsp+890h+var_850], r13
0x140036a59  mov     [rsp+890h+var_858], r13d
0x140036a5e  test    rcx, rcx
0x140036a61  jnz     short loc_140036A6B
0x140036a63  lea     ebx, [rcx+1]
0x140036a66  jmp     loc_140036CAC
0x140036a6b  mov     rax, [rcx]
0x140036a6e  lea     r8, [rsp+890h+var_838]
0x140036a73  lea     rdx, IID_IMsRdpClientNonScriptable3
0x140036a7a  mov     rax, [rax]
0x140036a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036a82  mov     ebx, eax
0x140036a84  test    eax, eax
0x140036a86  jns     short loc_140036AEC
0x140036a88  mov     rax, cs:WPP_GLOBAL_Control
0x140036a8f  lea     rdi, WPP_GLOBAL_Control
0x140036a96  cmp     rax, rdi
0x140036a99  jz      loc_140036CAC
0x140036a9f  test    byte ptr [rax+1Ch], 8
0x140036aa3  jz      loc_140036CAC
0x140036aa9  cmp     byte ptr [rax+19h], 2
0x140036aad  jb      loc_140036CAC
0x140036ab3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036ab8  mov     edx, 1F8h
0x140036abd  lea     rcx, aQiForImsrdpcli_0; "QI for IMsRdpClientNonScriptable3 faile"...
0x140036ac4  mov     dword ptr [rsp+890h+var_868], ebx
0x140036ac8  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140036acf  mov     qword ptr [rsp+890h+bIgnoreCase], rcx
0x140036ad4  mov     r9d, eax
0x140036ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x140036ade  mov     rcx, [rcx+10h]
0x140036ae2  call    WPP_SF_DsD
0x140036ae7  jmp     loc_140036CAC
0x140036aec  mov     rcx, [rsp+890h+var_838]
0x140036af1  lea     rdx, [rsp+890h+var_850]
0x140036af6  mov     rax, [rcx]
0x140036af9  mov     rax, [rax+0F0h]
0x140036b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036b05  mov     ebx, eax
0x140036b07  test    eax, eax
0x140036b09  jns     short loc_140036B4C
0x140036b0b  mov     rax, cs:WPP_GLOBAL_Control
0x140036b12  lea     rdi, WPP_GLOBAL_Control
0x140036b19  cmp     rax, rdi
0x140036b1c  jz      loc_140036CAC
0x140036b22  test    byte ptr [rax+1Ch], 8
0x140036b26  jz      loc_140036CAC
0x140036b2c  cmp     byte ptr [rax+19h], 2
0x140036b30  jb      loc_140036CAC
0x140036b36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036b3b  mov     edx, 1F9h
0x140036b40  lea     rcx, aImsrdpclient5G; "IMsRdpClient5::get_DriveCollection fail"...
0x140036b47  jmp     loc_140036AC4
0x140036b4c  mov     rcx, [rsp+890h+var_850]
0x140036b51  lea     rdx, [rsp+890h+var_858]
0x140036b56  mov     rax, [rcx]
0x140036b59  mov     rax, [rax+28h]
0x140036b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036b62  mov     ebx, eax
0x140036b64  test    eax, eax
0x140036b66  jns     short loc_140036BA9
0x140036b68  mov     rax, cs:WPP_GLOBAL_Control
0x140036b6f  lea     rdi, WPP_GLOBAL_Control
0x140036b76  cmp     rax, rdi
0x140036b79  jz      loc_140036CAC
0x140036b7f  test    byte ptr [rax+1Ch], 8
0x140036b83  jz      loc_140036CAC
0x140036b89  cmp     byte ptr [rax+19h], 2
0x140036b8d  jb      loc_140036CAC
0x140036b93  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036b98  mov     edx, 1FAh
0x140036b9d  lea     rcx, aImsrdpdrivecol; "IMsRdpDriveCollection::GetDriveCount fa"...
0x140036ba4  jmp     loc_140036AC4
0x140036ba9  lea     r8, [rsi+0C4DCh]; unsigned __int16 *
0x140036bb0  mov     edx, 400h; unsigned __int64
0x140036bb5  lea     rcx, [rsp+890h+String1]; unsigned __int16 *
0x140036bba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140036bbf  mov     ebx, eax
0x140036bc1  test    eax, eax
0x140036bc3  jns     short loc_140036C06
0x140036bc5  mov     rax, cs:WPP_GLOBAL_Control
0x140036bcc  lea     rdi, WPP_GLOBAL_Control
0x140036bd3  cmp     rax, rdi
0x140036bd6  jz      loc_140036CAC
0x140036bdc  test    byte ptr [rax+1Ch], 8
0x140036be0  jz      loc_140036CAC
0x140036be6  cmp     byte ptr [rax+19h], 2
0x140036bea  jb      loc_140036CAC
0x140036bf0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036bf5  mov     edx, 1FBh
0x140036bfa  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x140036c01  jmp     loc_140036AC4
0x140036c06  lea     rdx, asc_140122C04; "-"
0x140036c0d  lea     rcx, [rsp+890h+String1]; lpString1
0x140036c12  call    cs:__imp_lstrcmpW
0x140036c18  lea     rdx, pszMore; "*"
0x140036c1f  mov     ebx, eax
0x140036c21  lea     rcx, [rsp+890h+String1]; lpString1
0x140036c26  call    cs:__imp_lstrcmpW
0x140036c2c  mov     edi, r13d
0x140036c2f  test    ebx, ebx
0x140036c31  jnz     loc_140036DAC
0x140036c37  cmp     [rsp+890h+var_858], r13d
0x140036c3c  jbe     short loc_140036C9D
0x140036c3e  mov     rcx, [rsp+890h+var_850]
0x140036c43  lea     r8, [rsp+890h+var_860]
0x140036c48  mov     [rsp+890h+var_860], r13
0x140036c4d  mov     edx, edi
0x140036c4f  mov     rax, [rcx]
0x140036c52  mov     rax, [rax+20h]
0x140036c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036c5b  mov     ebx, eax
0x140036c5d  test    eax, eax
0x140036c5f  js      loc_140036D4A
0x140036c65  mov     eax, [rsi+0B4A4h]
0x140036c6b  mov     rcx, [rsp+890h+var_860]
0x140036c70  neg     eax
0x140036c72  sbb     dx, dx
0x140036c75  mov     r8, [rcx]
0x140036c78  mov     rax, [r8+20h]
0x140036c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036c81  mov     ebx, eax
0x140036c83  test    eax, eax
0x140036c85  js      loc_140036D0F
0x140036c8b  lea     rcx, [rsp+890h+var_860]
0x140036c90  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140036c95  inc     edi
0x140036c97  cmp     edi, [rsp+890h+var_858]
0x140036c9b  jb      short loc_140036C3E
0x140036c9d  mov     eax, [rsi+0B4A4h]
0x140036ca3  mov     [rsi+0B4C0h], eax
0x140036ca9  mov     ebx, r13d
0x140036cac  mov     rcx, [rsp+890h+var_850]
0x140036cb1  test    rcx, rcx
0x140036cb4  jz      short loc_140036CC7
0x140036cb6  mov     [rsp+890h+var_850], r13
0x140036cbb  mov     rax, [rcx]
0x140036cbe  mov     rax, [rax+10h]
0x140036cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036cc7  mov     rcx, [rsp+890h+var_838]
0x140036ccc  test    rcx, rcx
0x140036ccf  jz      short loc_140036CE2
0x140036cd1  mov     [rsp+890h+var_838], r13
0x140036cd6  mov     rax, [rcx]
0x140036cd9  mov     rax, [rax+10h]
0x140036cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ce2  mov     eax, ebx
0x140036ce4  mov     rcx, [rbp+790h+var_30]
0x140036ceb  xor     rcx, rsp; StackCookie
0x140036cee  call    __security_check_cookie
0x140036cf3  lea     r11, [rsp+890h+var_20]
0x140036cfb  mov     rbx, [r11+38h]
0x140036cff  mov     rsi, [r11+40h]
0x140036d03  mov     rsp, r11
0x140036d06  pop     r15
0x140036d08  pop     r14
0x140036d0a  pop     r13
0x140036d0c  pop     rdi
0x140036d0d  pop     rbp
0x140036d0e  retn
0x140036d0f  mov     rax, cs:WPP_GLOBAL_Control
0x140036d16  lea     rdi, WPP_GLOBAL_Control
0x140036d1d  cmp     rax, rdi
0x140036d20  jz      short loc_140036D9D
0x140036d22  test    byte ptr [rax+1Ch], 8
0x140036d26  jz      short loc_140036D9D
0x140036d28  cmp     byte ptr [rax+19h], 2
0x140036d2c  jb      short loc_140036D9D
0x140036d2e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036d33  mov     edx, 1FDh
0x140036d38  lea     r14, aImsrdpdrivePut; "IMsRdpDrive::put_RedirectionState faile"...
0x140036d3f  mov     dword ptr [rsp+890h+var_868], ebx
0x140036d43  mov     qword ptr [rsp+890h+bIgnoreCase], r14
0x140036d48  jmp     short loc_140036D83
0x140036d4a  mov     rax, cs:WPP_GLOBAL_Control
0x140036d51  lea     rdi, WPP_GLOBAL_Control
0x140036d58  cmp     rax, rdi
0x140036d5b  jz      short loc_140036D9D
0x140036d5d  test    byte ptr [rax+1Ch], 8
0x140036d61  jz      short loc_140036D9D
0x140036d63  cmp     byte ptr [rax+19h], 2
0x140036d67  jb      short loc_140036D9D
0x140036d69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036d6e  mov     edx, 1FCh
0x140036d73  lea     rcx, aImsrdpdrivecol_1; "IMsRdpDriveCollection::get_DriveByIndex"...
0x140036d7a  mov     dword ptr [rsp+890h+var_868], ebx
0x140036d7e  mov     qword ptr [rsp+890h+bIgnoreCase], rcx
0x140036d83  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d8a  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140036d91  mov     r9d, eax
0x140036d94  mov     rcx, [rcx+10h]
0x140036d98  call    WPP_SF_DsD
0x140036d9d  lea     rcx, [rsp+890h+var_860]
0x140036da2  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140036da7  jmp     loc_140036CAC
0x140036dac  test    eax, eax
0x140036dae  jnz     loc_140036E8D
0x140036db4  cmp     [rsp+890h+var_858], r13d
0x140036db9  jbe     short loc_140036E0A
0x140036dbb  mov     rcx, [rsp+890h+var_850]
0x140036dc0  lea     r8, [rsp+890h+var_860]
0x140036dc5  mov     [rsp+890h+var_860], r13
0x140036dca  mov     edx, edi
0x140036dcc  mov     rax, [rcx]
0x140036dcf  mov     rax, [rax+20h]
0x140036dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036dd8  mov     ebx, eax
0x140036dda  test    eax, eax
0x140036ddc  js      short loc_140036E53
0x140036dde  mov     rcx, [rsp+890h+var_860]
0x140036de3  or      edx, 0FFFFFFFFh
0x140036de6  mov     rax, [rcx]
0x140036de9  mov     rax, [rax+20h]
0x140036ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036df2  mov     ebx, eax
0x140036df4  test    eax, eax
0x140036df6  js      short loc_140036E19
0x140036df8  lea     rcx, [rsp+890h+var_860]
0x140036dfd  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140036e02  inc     edi
0x140036e04  cmp     edi, [rsp+890h+var_858]
0x140036e08  jb      short loc_140036DBB
0x140036e0a  mov     dword ptr [rsi+0B4C0h], 1
0x140036e14  jmp     loc_140036CA9
0x140036e19  mov     rax, cs:WPP_GLOBAL_Control
0x140036e20  lea     rdi, WPP_GLOBAL_Control
0x140036e27  cmp     rax, rdi
0x140036e2a  jz      loc_140036D9D
0x140036e30  test    byte ptr [rax+1Ch], 8
0x140036e34  jz      loc_140036D9D
0x140036e3a  cmp     byte ptr [rax+19h], 2
0x140036e3e  jb      loc_140036D9D
0x140036e44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036e49  mov     edx, 1FFh
0x140036e4e  jmp     loc_140036D38
0x140036e53  mov     rax, cs:WPP_GLOBAL_Control
0x140036e5a  lea     rdi, WPP_GLOBAL_Control
0x140036e61  cmp     rax, rdi
0x140036e64  jz      loc_140036D9D
0x140036e6a  test    byte ptr [rax+1Ch], 8
0x140036e6e  jz      loc_140036D9D
0x140036e74  cmp     byte ptr [rax+19h], 2
0x140036e78  jb      loc_140036D9D
0x140036e7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140036e83  mov     edx, 1FEh
0x140036e88  jmp     loc_140036D73
0x140036e8d  cmp     [rsp+890h+var_858], r13d
0x140036e92  jbe     short loc_140036EE6
0x140036e94  mov     rcx, [rsp+890h+var_850]
0x140036e99  lea     r8, [rsp+890h+var_860]
0x140036e9e  mov     [rsp+890h+var_860], r13
0x140036ea3  mov     edx, edi
0x140036ea5  mov     rax, [rcx]
0x140036ea8  mov     rax, [rax+20h]
0x140036eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036eb1  mov     ebx, eax
0x140036eb3  test    eax, eax
0x140036eb5  js      loc_140036F87
0x140036ebb  mov     rcx, [rsp+890h+var_860]
0x140036ec0  xor     edx, edx
0x140036ec2  mov     rax, [rcx]
0x140036ec5  mov     rax, [rax+20h]
0x140036ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ece  mov     ebx, eax
0x140036ed0  test    eax, eax
0x140036ed2  js      short loc_140036F4D
0x140036ed4  lea     rcx, [rsp+890h+var_860]
0x140036ed9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140036ede  inc     edi
0x140036ee0  cmp     edi, [rsp+890h+var_858]
0x140036ee4  jb      short loc_140036E94
0x140036ee6  lea     rdx, [rsp+890h+Delimiter]; Delimiter
0x140036eeb  mov     [rsi+0B4C0h], r13d
0x140036ef2  lea     rcx, [rsp+890h+String1]; String
0x140036ef7  call    wcstok_mvcrt_legacy_two_parameter_form
0x140036efc  mov     r15, rax
0x140036eff  test    rax, rax
0x140036f02  jz      loc_140036CA9
0x140036f08  lea     rdi, WPP_GLOBAL_Control
0x140036f0f  lea     r14, aImsrdpdrivePut; "IMsRdpDrive::put_RedirectionState faile"...
0x140036f16  or      r9d, 0FFFFFFFFh; cchCount2
0x140036f1a  mov     [rsp+890h+bIgnoreCase], 1; bIgnoreCase
0x140036f22  or      edx, r9d; cchCount1
  ... truncated ...
```
