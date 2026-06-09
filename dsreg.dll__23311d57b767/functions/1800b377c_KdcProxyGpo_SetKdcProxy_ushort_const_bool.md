# KdcProxyGpo::SetKdcProxy(ushort const *,bool &)

- ea: `0x1800b377c`
- end: `0x1800b3dee`
- name: `?SetKdcProxy@KdcProxyGpo@@QEAAJPEBGAEA_N@Z`
- size: `1650`
- prototype: `__int64 __fastcall(KdcProxyGpo *__hidden this, LPCWSTR pwszUrl, bool *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ae820`

## callees

- `0x1800048cc`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x18003334c`
- `0x1800377e0`
- `0x18003a63c`
- `0x18003ec7c`
- `0x1800b2e10`
- `0x1800b2eb0`
- `0x1800b30c0`
- `0x1800b316c`
- `0x1800b3184`
- `0x1800b31f4`
- `0x1800b357c`
- `0x1800b377c`
- `0x1800b3df4`
- `0x1800b3e94`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b398e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b398e`

## string_xrefs

- `0x1800b393f`: `KdcProxyGpoValue::Compare`
- `0x1800b3c3b`: `KdcProxyGpoValue::Compare`
- `0x1800b38e4`: `KdcProxyGpoRegKey::Read`
- `0x1800b3b23`: `KdcProxyGpoRegKey::Read`
- `0x1800b3b85`: `KdcProxyGpoRegKey::Write`
- `0x1800b3d29`: `KERBEROS.MICROSOFTONLINE.COM`
- `0x1800b3dba`: `KERBEROS.MICROSOFTONLINE.COM`
- `0x1800b3a36`: `m_pCreateGroupPolicyObject`
- `0x1800b3a50`: `m_pCreateGroupPolicyObject`
- `0x1800b3975`: `%s: The KDC Proxy GPO registry key already has the correct value.`
- `0x1800b3959`: `KdcProxyGpoValue::LogicalCompare`
- `0x1800b3ba2`: `%s: The local KDC Proxy GPO has been updated to the correct value.`
- `0x1800b3ae5`: `GroupPolicyObject::GetMachineRegistryKey`
- `0x1800b3aac`: `GroupPolicyObject::OpenLocalMachineGpo`
- `0x1800b3c57`: `%s: The local KDC Proxy GPO already has the correct value.`

## pseudocode

```c
__int64 __fastcall KdcProxyGpo::SetKdcProxy(KdcProxyGpo *this, LPCWSTR pwszUrl, bool *a3)
{
  unsigned __int16 *v6; // r12
  int ProxyServer; // eax
  signed int v8; // ebx
  unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // rsi
  unsigned int v11; // eax
  const unsigned __int16 *v12; // r8
  int v13; // edi
  int v14; // eax
  const wchar_t *v15; // r8
  __int64 v16; // r9
  char v17; // r14
  char v18; // al
  char v19; // dl
  char v20; // al
  char v21; // dl
  __int64 v23; // rcx
  int v24; // eax
  const wchar_t *v25; // r8
  const unsigned __int16 *v26; // r8
  KdcProxyGpoValue *v27; // rcx
  unsigned int v28; // esi
  char v29; // al
  char v30; // r8
  bool v31; // r15
  bool v32; // r14
  bool v33; // si
  bool v34; // di
  const wchar_t *v35; // rdx
  const wchar_t *v36; // rcx
  const wchar_t *v37; // r9
  const wchar_t *v38; // r8
  unsigned __int16 *v39; // rbx
  bool v40; // al
  const unsigned __int16 *v41; // rdx
  bool v42; // r9
  const wchar_t *v43; // rax
  const unsigned __int16 *v44; // r8
  bool *v45; // [rsp+20h] [rbp-79h]
  unsigned int v46[2]; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v47; // [rsp+50h] [rbp-49h]
  unsigned int v48[2]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v49; // [rsp+60h] [rbp-39h]
  __int64 v50; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v51; // [rsp+70h] [rbp-29h]
  HKEY hKey; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v53[7]; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 *v55; // [rsp+110h] [rbp+77h] BYREF
  bool IsTrue; // [rsp+118h] [rbp+7Fh]

  Logger::TraceVerbose((wchar_t *)L"%s started", L"KdcProxyGpo::SetKdcProxy");
  v55 = 0;
  hKey = 0;
  v6 = 0;
  v49 = 0;
  *(_QWORD *)v46 = 0;
  v47 = 0;
  v50 = 0;
  v51 = 0;
  memset(v53, 0, 64);
  *a3 = 0;
  ProxyServer = KdcProxyGpo::GetProxyServer(pwszUrl, &v55);
  v8 = ProxyServer;
  if ( ProxyServer >= 0 )
  {
    Logger::TraceVerbose((wchar_t *)L"%s: KDC proxy server: %s", L"KdcProxyGpo::SetKdcProxy", v55);
    *(_QWORD *)v48 = 1;
    KdcProxyGpoValue::SetProxyServer((KdcProxyGpoValue *)v48, v55);
    v11 = KdcProxyGpo::LockGpo(this);
    v13 = v11;
    v6 = v49;
    if ( v11 )
      goto LABEL_4;
    v14 = KdcProxyGpoRegKey::Initialize((KdcProxyGpoRegKey *)v53, HKEY_LOCAL_MACHINE, v12);
    v8 = v14;
    if ( v14 < 0 )
    {
      v15 = L"KdcProxyGpoRegKey::Initialize";
LABEL_7:
      v16 = (unsigned int)v14;
LABEL_8:
      Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"KdcProxyGpo::SetKdcProxy", v15, v16);
      v10 = pwszUrl;
LABEL_74:
      v9 = 0;
      goto LABEL_75;
    }
    v14 = KdcProxyGpoRegKey::Read((KdcProxyGpoRegKey *)v53, (struct KdcProxyGpoValue *)v46);
    v8 = v14;
    if ( v14 < 0 )
    {
LABEL_10:
      v15 = L"KdcProxyGpoRegKey::Read";
      goto LABEL_7;
    }
    v8 = 0;
    v17 = 0;
    LOBYTE(v55) = 0;
    IsTrue = KdcProxyGpoValue::IsTrue(v48[0]);
    v18 = KdcProxyGpoValue::IsTrue(v46[0]);
    if ( v18 == v19 )
    {
      KdcProxyGpoValue::IsTrue(v48[1]);
      v20 = KdcProxyGpoValue::IsTrue(v46[1]);
      if ( v20 == v21 )
      {
        v8 = KdcProxyGpoValue::CompareProxyServer((KdcProxyGpoValue *)v46, v6, (bool *)&v55);
        v17 = (char)v55;
      }
    }
    Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"KdcProxyGpoValue::Compare", (unsigned int)v8);
    if ( v8 < 0 )
    {
LABEL_15:
      v16 = (unsigned int)v8;
      v15 = L"KdcProxyGpoValue::LogicalCompare";
      goto LABEL_8;
    }
    if ( v17 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: The KDC Proxy GPO registry key already has the correct value.",
        L"KdcProxyGpo::SetKdcProxy");
      goto LABEL_18;
    }
    if ( !*((_QWORD *)this + 8) )
    {
      v23 = *((_QWORD *)this + 1);
      if ( !v23 )
      {
        if ( !*(_QWORD *)this )
        {
          v8 = -2147024809;
          Logger::TraceError(
            L"%s: \"%s\" should not be null.",
            L"KdcProxyGpo::SetKdcProxy",
            L"m_pCreateGroupPolicyObject");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"KdcProxyGpo::SetKdcProxy", L"m_pCreateGroupPolicyObject");
          goto LABEL_26;
        }
        v23 = (*(__int64 (**)(void))this)();
        *((_QWORD *)this + 1) = v23;
        if ( !v23 )
        {
          v8 = -2147024882;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"KdcProxyGpo::SetKdcProxy");
          goto LABEL_26;
        }
      }
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
      v8 = v24;
      if ( v24 < 0 )
      {
        v25 = L"GroupPolicyObject::OpenLocalMachineGpo";
        goto LABEL_31;
      }
      v24 = (*(__int64 (__fastcall **)(_QWORD, HKEY *))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), &hKey);
      v8 = v24;
      if ( v24 < 0 )
      {
        v25 = L"GroupPolicyObject::GetMachineRegistryKey";
        goto LABEL_31;
      }
      v24 = KdcProxyGpoRegKey::Initialize((KdcProxyGpo *)((char *)this + 32), hKey, v26);
      v8 = v24;
      if ( v24 < 0 )
      {
        v25 = L"KdcProxyGpoRegKey::Initialize";
        goto LABEL_31;
      }
      hKey = 0;
    }
    v24 = KdcProxyGpoRegKey::Read((KdcProxyGpo *)((char *)this + 32), (struct KdcProxyGpoValue *)&v50);
    v8 = v24;
    if ( v24 >= 0 )
    {
      v8 = KdcProxyGpoRegKey::Write(
             (KdcProxyGpo *)((char *)this + 32),
             (const struct KdcProxyGpoValue *)v48,
             (const struct KdcProxyGpoValue *)&v50,
             0,
             a3);
      if ( !*((_BYTE *)this + 24) && *a3 )
      {
        v27 = (KdcProxyGpo *)((char *)this + 96);
        if ( (__int64 *)((char *)this + 96) != &v50 )
        {
          *(_DWORD *)v27 = v50;
          *((_DWORD *)this + 25) = HIDWORD(v50);
          KdcProxyGpoValue::SetProxyServer(v27, v51);
          v51 = 0;
        }
        *((_BYTE *)this + 24) = 1;
      }
      if ( v8 < 0 )
      {
        v16 = (unsigned int)v8;
        v15 = L"KdcProxyGpoRegKey::Write";
        goto LABEL_8;
      }
      if ( *a3 )
      {
        Logger::TraceInformation(
          L"%s: The local KDC Proxy GPO has been updated to the correct value.",
          L"KdcProxyGpo::SetKdcProxy");
        v14 = KdcProxyGpo::Save(this);
        v8 = v14;
        if ( v14 < 0 )
        {
          v15 = L"KdcProxyGpo::Save";
          goto LABEL_7;
        }
        v11 = KdcProxyGpo::LockGpo(this);
        v13 = v11;
        if ( v11 )
        {
LABEL_4:
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"KdcProxyGpo::SetKdcProxy",
            L"KdcProxyGpo::LockGpo",
            v11);
          v10 = pwszUrl;
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
          else
            v8 = v13;
          goto LABEL_73;
        }
        v14 = KdcProxyGpoRegKey::Read((KdcProxyGpoRegKey *)v53, (struct KdcProxyGpoValue *)v46);
        v8 = v14;
        if ( v14 < 0 )
          goto LABEL_10;
        v8 = 0;
        v17 = 0;
        LOBYTE(v55) = 0;
        v28 = v46[0];
        if ( KdcProxyGpoValue::IsTrue(v46[0]) == IsTrue )
        {
          KdcProxyGpoValue::IsTrue(v48[1]);
          v29 = KdcProxyGpoValue::IsTrue(v46[1]);
          if ( v29 == v30 )
          {
            v8 = KdcProxyGpoValue::CompareProxyServer((KdcProxyGpoValue *)v46, v6, (bool *)&v55);
            v17 = (char)v55;
          }
        }
        Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"KdcProxyGpoValue::Compare", (unsigned int)v8);
        if ( v8 < 0 )
          goto LABEL_15;
      }
      else
      {
        Logger::TraceInformation(
          L"%s: The local KDC Proxy GPO already has the correct value.",
          L"KdcProxyGpo::SetKdcProxy");
        v28 = v46[0];
      }
      if ( v17 )
      {
        if ( *a3 )
        {
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Successfully set the KDC proxy server for realm \"%s\" to \"%s\" in group policy.",
            L"KdcProxyGpo::SetKdcProxy",
            L"KERBEROS.MICROSOFTONLINE.COM",
            v6);
          KdcProxyGpoValue::IsTrue(v48[1]);
          v40 = KdcProxyGpoValue::IsTrue(v48[0]);
          v10 = pwszUrl;
          Logger::WriteSetKdcProxyGpoSuccessEvent(pwszUrl, v41, v40, v42, v6);
        }
        else
        {
          v10 = pwszUrl;
        }
LABEL_73:
        if ( v8 < 0 )
          goto LABEL_74;
LABEL_18:
        v9 = 0;
        goto LABEL_19;
      }
      v31 = KdcProxyGpoValue::IsTrue(v46[1]);
      v32 = KdcProxyGpoValue::IsTrue(v28);
      v33 = KdcProxyGpoValue::IsTrue(v48[1]);
      v34 = KdcProxyGpoValue::IsTrue(v48[0]);
      v35 = L"TRUE";
      if ( !v31 )
        v35 = L"FALSE";
      v36 = L"TRUE";
      if ( !v32 )
        v36 = L"FALSE";
      v37 = L"TRUE";
      if ( !v33 )
        v37 = L"FALSE";
      v38 = L"TRUE";
      if ( !v34 )
        v38 = L"FALSE";
      v39 = v47;
      Logger::TraceError(
        L"%s: The local KDC Proxy GPO has the correct value. But there are some other higher prededence GPO with wrong val"
         "ue.\n"
         "Expected value:\n"
         "  KdcProxyServer_Enabled: %s\n"
         "  NoRevocationCheck: %s\n"
         "  Proxy Server: %s\n"
         "Actual value:\n"
         "  KdcProxyServer_Enabled: %s\n"
         "  NoRevocationCheck: %s\n"
         "  Proxy Server: %s",
        L"KdcProxyGpo::SetKdcProxy",
        v38,
        v37,
        v6,
        v36,
        v35,
        v47);
      Logger::WriteBadKdcProxyGpoEvent(v34, v33, v6, v32, v31, v39);
      v8 = -2145648492;
LABEL_26:
      v10 = pwszUrl;
      goto LABEL_74;
    }
    v25 = L"KdcProxyGpoRegKey::Read";
LABEL_31:
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"KdcProxyGpo::SetKdcProxy", v25, (unsigned int)v24);
    goto LABEL_26;
  }
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"KdcProxyGpo::SetKdcProxy",
    L"GetProxyServer",
    (unsigned int)ProxyServer);
  v9 = v55;
  v10 = pwszUrl;
LABEL_75:
  if ( !v6 )
    v6 = v9;
  v43 = L"TRUE";
  if ( !*a3 )
    v43 = L"FALSE";
  LODWORD(v45) = v8;
  Logger::TraceError(
    L"%s: Failed to set the KDC proxy server for realm \"%s\" to \"%s\" in group policy. Error code: 0x%08x. LGPO modified: %s.",
    L"KdcProxyGpo::SetKdcProxy",
    L"KERBEROS.MICROSOFTONLINE.COM",
    v6,
    v45,
    v43);
  Logger::WriteSetKdcProxyGpoFailureEvent(v8, v10, v44, v6, *a3);
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  SafeFree(v9);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"KdcProxyGpo::SetKdcProxy", (unsigned int)v8);
  RegistryPath::Reset((RegistryPath *)v53);
  v50 = 0;
  KdcProxyGpoValue::SetProxyServer((KdcProxyGpoValue *)&v50, 0);
  *(_QWORD *)v46 = 0;
  KdcProxyGpoValue::SetProxyServer((KdcProxyGpoValue *)v46, 0);
  *(_QWORD *)v48 = 0;
  KdcProxyGpoValue::SetProxyServer((KdcProxyGpoValue *)v48, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800b377c  mov     [rsp-8+arg_0], rbx
0x1800b3781  mov     [rsp-8+arg_8], rdx
0x1800b3786  push    rbp
0x1800b3787  push    rsi
0x1800b3788  push    rdi
0x1800b3789  push    r12
0x1800b378b  push    r13
0x1800b378d  push    r14
0x1800b378f  push    r15
0x1800b3791  lea     rbp, [rsp-27h]
0x1800b3796  sub     rsp, 0C0h
0x1800b379d  mov     r13, r8
0x1800b37a0  mov     rbx, rdx
0x1800b37a3  mov     rsi, rcx
0x1800b37a6  lea     rdi, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b37ad  mov     rdx, rdi
0x1800b37b0  lea     rcx, aSStarted; "%s started"
0x1800b37b7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b37bc  xor     r15d, r15d
0x1800b37bf  mov     [rbp+57h+arg_10], r15
0x1800b37c3  mov     [rbp+57h+hKey], r15
0x1800b37c7  mov     r12d, r15d
0x1800b37ca  mov     [rbp+57h+var_90], r15
0x1800b37ce  mov     qword ptr [rbp+57h+var_A8], r15
0x1800b37d2  mov     [rbp+57h+var_A0], r15
0x1800b37d6  mov     [rbp+57h+var_88], r15
0x1800b37da  mov     [rbp+57h+var_80], r15
0x1800b37de  xorps   xmm0, xmm0
0x1800b37e1  movdqa  [rbp+57h+var_70], xmm0
0x1800b37e6  xorps   xmm1, xmm1
0x1800b37e9  movdqa  [rbp+57h+var_60], xmm1
0x1800b37ee  movdqa  [rbp+57h+var_50], xmm0
0x1800b37f3  movdqa  [rbp+57h+var_40], xmm1
0x1800b37f8  mov     [r13+0], r15b
0x1800b37fc  lea     rdx, [rbp+57h+arg_10]; unsigned __int16 **
0x1800b3800  mov     rcx, rbx; pwszUrl
0x1800b3803  call    ?GetProxyServer@KdcProxyGpo@@SAJPEBGPEAPEAG@Z; KdcProxyGpo::GetProxyServer(ushort const *,ushort * *)
0x1800b3808  mov     ebx, eax
0x1800b380a  mov     rdx, rdi
0x1800b380d  test    eax, eax
0x1800b380f  jns     short loc_1800B3834
0x1800b3811  mov     r9d, eax
0x1800b3814  lea     r8, aGetproxyserver; "GetProxyServer"
0x1800b381b  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b3822  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b3827  mov     rdi, [rbp+57h+arg_10]
0x1800b382b  mov     rsi, [rbp+57h+arg_8]
0x1800b382f  jmp     loc_1800B3D91
0x1800b3834  mov     r8, [rbp+57h+arg_10]
0x1800b3838  lea     rcx, aSKdcProxyServe; "%s: KDC proxy server: %s"
0x1800b383f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b3844  mov     qword ptr [rbp+57h+var_98], 1
0x1800b384c  mov     rdx, [rbp+57h+arg_10]; unsigned __int16 *
0x1800b3850  lea     rcx, [rbp+57h+var_98]; this
0x1800b3854  call    ?SetProxyServer@KdcProxyGpoValue@@QEAAXPEBG@Z; KdcProxyGpoValue::SetProxyServer(ushort const *)
0x1800b3859  mov     [rbp+57h+lpMem], r15
0x1800b385d  mov     rcx, rsi; this
0x1800b3860  call    ?LockGpo@KdcProxyGpo@@AEAAKXZ; KdcProxyGpo::LockGpo(void)
0x1800b3865  mov     edi, eax
0x1800b3867  mov     r12, [rbp+57h+var_90]
0x1800b386b  test    eax, eax
0x1800b386d  jz      short loc_1800B3895
0x1800b386f  mov     r9d, eax
0x1800b3872  lea     r8, aKdcproxygpoLoc; "KdcProxyGpo::LockGpo"
0x1800b3879  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3880  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800b3887  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b388c  mov     rsi, [rbp+57h+arg_8]
0x1800b3890  jmp     loc_1800B3D6E
0x1800b3895  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800b389c  lea     rcx, [rbp+57h+var_70]; this
0x1800b38a0  call    ?Initialize@KdcProxyGpoRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; KdcProxyGpoRegKey::Initialize(HKEY__ *,ushort const *)
0x1800b38a5  mov     ebx, eax
0x1800b38a7  test    eax, eax
0x1800b38a9  jns     short loc_1800B38D1
0x1800b38ab  lea     r8, aKdcproxygporeg_2; "KdcProxyGpoRegKey::Initialize"
0x1800b38b2  mov     r9d, eax
0x1800b38b5  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b38bc  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b38c3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b38c8  mov     rsi, [rbp+57h+arg_8]
0x1800b38cc  jmp     loc_1800B3D8D
0x1800b38d1  lea     rdx, [rbp+57h+var_A8]; struct KdcProxyGpoValue *
0x1800b38d5  lea     rcx, [rbp+57h+var_70]; this
0x1800b38d9  call    ?Read@KdcProxyGpoRegKey@@QEAAJAEAVKdcProxyGpoValue@@@Z; KdcProxyGpoRegKey::Read(KdcProxyGpoValue &)
0x1800b38de  mov     ebx, eax
0x1800b38e0  test    eax, eax
0x1800b38e2  jns     short loc_1800B38ED
0x1800b38e4  lea     r8, aKdcproxygporeg_1; "KdcProxyGpoRegKey::Read"
0x1800b38eb  jmp     short loc_1800B38B2
0x1800b38ed  mov     ebx, r15d
0x1800b38f0  mov     r14b, r15b
0x1800b38f3  mov     byte ptr [rbp+57h+arg_10], r15b
0x1800b38f7  mov     ecx, [rbp+57h+var_98]; unsigned int
0x1800b38fa  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b38ff  mov     dl, al
0x1800b3901  mov     [rbp+57h+arg_18], al
0x1800b3904  mov     ecx, [rbp+57h+var_A8]; unsigned int
0x1800b3907  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b390c  cmp     al, dl
0x1800b390e  jnz     short loc_1800B393C
0x1800b3910  mov     ecx, [rbp+57h+var_98+4]; unsigned int
0x1800b3913  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b3918  mov     dl, al
0x1800b391a  mov     ecx, [rbp+57h+var_A8+4]; unsigned int
0x1800b391d  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b3922  cmp     al, dl
0x1800b3924  jnz     short loc_1800B393C
0x1800b3926  lea     r8, [rbp+57h+arg_10]; bool *
0x1800b392a  mov     rdx, r12; unsigned __int16 *
0x1800b392d  lea     rcx, [rbp+57h+var_A8]; this
0x1800b3931  call    ?CompareProxyServer@KdcProxyGpoValue@@QEBAJPEBGAEA_N@Z; KdcProxyGpoValue::CompareProxyServer(ushort const *,bool &)
0x1800b3936  mov     ebx, eax
0x1800b3938  mov     r14b, byte ptr [rbp+57h+arg_10]
0x1800b393c  mov     r8d, ebx
0x1800b393f  lea     rdx, aKdcproxygpoval_1; "KdcProxyGpoValue::Compare"
0x1800b3946  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800b394d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b3952  test    ebx, ebx
0x1800b3954  jns     short loc_1800B3965
0x1800b3956  mov     r9d, ebx
0x1800b3959  lea     r8, aKdcproxygpoval; "KdcProxyGpoValue::LogicalCompare"
0x1800b3960  jmp     loc_1800B38B5
0x1800b3965  test    r14b, r14b
0x1800b3968  jz      loc_1800B3A11
0x1800b396e  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3975  lea     rcx, aSTheKdcProxyGp; "%s: The KDC Proxy GPO registry key alre"...
0x1800b397c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b3981  mov     rdi, [rbp+57h+lpMem]
0x1800b3985  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b3989  test    rcx, rcx
0x1800b398c  jz      short loc_1800B3994
0x1800b398e  call    cs:__imp_RegCloseKey
0x1800b3994  mov     rcx, rdi; lpMem
0x1800b3997  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800b399c  mov     r8d, ebx
0x1800b399f  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b39a6  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800b39ad  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b39b2  lea     rcx, [rbp+57h+var_70]; this
0x1800b39b6  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x1800b39bb  mov     [rbp+57h+var_88], 0
0x1800b39c3  xor     edx, edx; unsigned __int16 *
0x1800b39c5  lea     rcx, [rbp+57h+var_88]; this
0x1800b39c9  call    ?SetProxyServer@KdcProxyGpoValue@@QEAAXPEBG@Z; KdcProxyGpoValue::SetProxyServer(ushort const *)
0x1800b39ce  mov     qword ptr [rbp+57h+var_A8], 0
0x1800b39d6  xor     edx, edx; unsigned __int16 *
0x1800b39d8  lea     rcx, [rbp+57h+var_A8]; this
0x1800b39dc  call    ?SetProxyServer@KdcProxyGpoValue@@QEAAXPEBG@Z; KdcProxyGpoValue::SetProxyServer(ushort const *)
0x1800b39e1  mov     qword ptr [rbp+57h+var_98], 0
0x1800b39e9  xor     edx, edx; unsigned __int16 *
0x1800b39eb  lea     rcx, [rbp+57h+var_98]; this
0x1800b39ef  call    ?SetProxyServer@KdcProxyGpoValue@@QEAAXPEBG@Z; KdcProxyGpoValue::SetProxyServer(ushort const *)
0x1800b39f4  mov     eax, ebx
0x1800b39f6  mov     rbx, [rsp+0F0h+arg_0]
0x1800b39fe  add     rsp, 0C0h
0x1800b3a05  pop     r15
0x1800b3a07  pop     r14
0x1800b3a09  pop     r13
0x1800b3a0b  pop     r12
0x1800b3a0d  pop     rdi
0x1800b3a0e  pop     rsi
0x1800b3a0f  pop     rbp
0x1800b3a10  retn
0x1800b3a11  lea     r15, [rsi+20h]
0x1800b3a15  cmp     qword ptr [r15+20h], 0
0x1800b3a1a  jnz     loc_1800B3B11
0x1800b3a20  mov     rcx, [rsi+8]
0x1800b3a24  test    rcx, rcx
0x1800b3a27  jnz     short loc_1800B3A9A
0x1800b3a29  mov     rax, [rsi]
0x1800b3a2c  test    rax, rax
0x1800b3a2f  jnz     short loc_1800B3A6F
0x1800b3a31  mov     ebx, 80070057h
0x1800b3a36  lea     r8, aMPcreategroupp; "m_pCreateGroupPolicyObject"
0x1800b3a3d  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3a44  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800b3a4b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b3a50  lea     rdx, aMPcreategroupp; "m_pCreateGroupPolicyObject"
0x1800b3a57  lea     rcx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3a5e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b3a63  mov     rsi, [rbp+57h+arg_8]
0x1800b3a67  xor     r15d, r15d
0x1800b3a6a  jmp     loc_1800B3D8D
0x1800b3a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a74  mov     rcx, rax
0x1800b3a77  mov     [rsi+8], rax
0x1800b3a7b  test    rax, rax
0x1800b3a7e  jnz     short loc_1800B3A9A
0x1800b3a80  mov     ebx, 8007000Eh
0x1800b3a85  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3a8c  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800b3a93  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800b3a98  jmp     short loc_1800B3A63
0x1800b3a9a  mov     rax, [rcx]
0x1800b3a9d  mov     rax, [rax+8]
0x1800b3aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3aa6  mov     ebx, eax
0x1800b3aa8  test    eax, eax
0x1800b3aaa  jns     short loc_1800B3ACB
0x1800b3aac  lea     r8, aGrouppolicyobj_1; "GroupPolicyObject::OpenLocalMachineGpo"
0x1800b3ab3  mov     r9d, eax
0x1800b3ab6  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3abd  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b3ac4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b3ac9  jmp     short loc_1800B3A63
0x1800b3acb  mov     rcx, [rsi+8]
0x1800b3acf  mov     rax, [rcx]
0x1800b3ad2  lea     rdx, [rbp+57h+hKey]
0x1800b3ad6  mov     rax, [rax+10h]
0x1800b3ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3adf  mov     ebx, eax
0x1800b3ae1  test    eax, eax
0x1800b3ae3  jns     short loc_1800B3AEE
0x1800b3ae5  lea     r8, aGrouppolicyobj_0; "GroupPolicyObject::GetMachineRegistryKe"...
0x1800b3aec  jmp     short loc_1800B3AB3
0x1800b3aee  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800b3af2  mov     rcx, r15; this
0x1800b3af5  call    ?Initialize@KdcProxyGpoRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; KdcProxyGpoRegKey::Initialize(HKEY__ *,ushort const *)
0x1800b3afa  mov     ebx, eax
0x1800b3afc  test    eax, eax
0x1800b3afe  jns     short loc_1800B3B09
0x1800b3b00  lea     r8, aKdcproxygporeg_2; "KdcProxyGpoRegKey::Initialize"
0x1800b3b07  jmp     short loc_1800B3AB3
0x1800b3b09  mov     [rbp+57h+hKey], 0
0x1800b3b11  lea     rdx, [rbp+57h+var_88]; struct KdcProxyGpoValue *
0x1800b3b15  mov     rcx, r15; this
0x1800b3b18  call    ?Read@KdcProxyGpoRegKey@@QEAAJAEAVKdcProxyGpoValue@@@Z; KdcProxyGpoRegKey::Read(KdcProxyGpoValue &)
0x1800b3b1d  mov     ebx, eax
0x1800b3b1f  test    eax, eax
0x1800b3b21  jns     short loc_1800B3B2C
0x1800b3b23  lea     r8, aKdcproxygporeg_1; "KdcProxyGpoRegKey::Read"
0x1800b3b2a  jmp     short loc_1800B3AB3
0x1800b3b2c  mov     [rsp+0F0h+var_D0], r13; bool *
0x1800b3b31  xor     r9d, r9d; bool
0x1800b3b34  lea     r8, [rbp+57h+var_88]; struct KdcProxyGpoValue *
0x1800b3b38  lea     rdx, [rbp+57h+var_98]; struct KdcProxyGpoValue *
0x1800b3b3c  mov     rcx, r15; this
0x1800b3b3f  call    ?Write@KdcProxyGpoRegKey@@QEAAJAEBVKdcProxyGpoValue@@0_NAEA_N@Z; KdcProxyGpoRegKey::Write(KdcProxyGpoValue const &,KdcProxyGpoValue const &,bool,bool &)
0x1800b3b44  mov     ebx, eax
0x1800b3b46  xor     r15d, r15d
0x1800b3b49  cmp     [rsi+18h], r15b
0x1800b3b4d  jnz     short loc_1800B3B7E
0x1800b3b4f  cmp     [r13+0], r15b
0x1800b3b53  jz      short loc_1800B3B7E
0x1800b3b55  lea     rcx, [rsi+60h]; this
0x1800b3b59  lea     rax, [rbp+57h+var_88]
0x1800b3b5d  cmp     rcx, rax
0x1800b3b60  jz      short loc_1800B3B7A
0x1800b3b62  mov     eax, dword ptr [rbp+57h+var_88]
0x1800b3b65  mov     [rcx], eax
0x1800b3b67  mov     eax, dword ptr [rbp+57h+var_88+4]
0x1800b3b6a  mov     [rcx+4], eax
0x1800b3b6d  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x1800b3b71  call    ?SetProxyServer@KdcProxyGpoValue@@QEAAXPEBG@Z; KdcProxyGpoValue::SetProxyServer(ushort const *)
0x1800b3b76  mov     [rbp+57h+var_80], r15
0x1800b3b7a  mov     byte ptr [rsi+18h], 1
0x1800b3b7e  test    ebx, ebx
0x1800b3b80  jns     short loc_1800B3B91
0x1800b3b82  mov     r9d, ebx
0x1800b3b85  lea     r8, aKdcproxygporeg; "KdcProxyGpoRegKey::Write"
0x1800b3b8c  jmp     loc_1800B38B5
0x1800b3b91  lea     rdx, aKdcproxygpoSet; "KdcProxyGpo::SetKdcProxy"
0x1800b3b98  cmp     [r13+0], r15b
0x1800b3b9c  jz      loc_1800B3C57
0x1800b3ba2  lea     rcx, aSTheLocalKdcPr_4; "%s: The local KDC Proxy GPO has been up"...
0x1800b3ba9  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800b3bae  mov     rcx, rsi; this
0x1800b3bb1  call    ?Save@KdcProxyGpo@@AEAAJXZ; KdcProxyGpo::Save(void)
0x1800b3bb6  mov     ebx, eax
0x1800b3bb8  test    eax, eax
0x1800b3bba  jns     short loc_1800B3BC8
0x1800b3bbc  lea     r8, aKdcproxygpoSav; "KdcProxyGpo::Save"
0x1800b3bc3  jmp     loc_1800B38B2
0x1800b3bc8  mov     rcx, rsi; this
0x1800b3bcb  call    ?LockGpo@KdcProxyGpo@@AEAAKXZ; KdcProxyGpo::LockGpo(void)
0x1800b3bd0  mov     edi, eax
0x1800b3bd2  test    eax, eax
0x1800b3bd4  jnz     loc_1800B386F
0x1800b3bda  lea     rdx, [rbp+57h+var_A8]; struct KdcProxyGpoValue *
0x1800b3bde  lea     rcx, [rbp+57h+var_70]; this
0x1800b3be2  call    ?Read@KdcProxyGpoRegKey@@QEAAJAEAVKdcProxyGpoValue@@@Z; KdcProxyGpoRegKey::Read(KdcProxyGpoValue &)
0x1800b3be7  mov     ebx, eax
0x1800b3be9  test    eax, eax
0x1800b3beb  js      loc_1800B38E4
0x1800b3bf1  mov     ebx, r15d
0x1800b3bf4  mov     r14b, r15b
0x1800b3bf7  mov     byte ptr [rbp+57h+arg_10], r15b
0x1800b3bfb  mov     esi, [rbp+57h+var_A8]
0x1800b3bfe  mov     ecx, esi; unsigned int
0x1800b3c00  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b3c05  cmp     al, [rbp+57h+arg_18]
0x1800b3c08  jnz     short loc_1800B3C38
0x1800b3c0a  mov     ecx, [rbp+57h+var_98+4]; unsigned int
0x1800b3c0d  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b3c12  mov     r8b, al
0x1800b3c15  mov     ecx, [rbp+57h+var_A8+4]; unsigned int
0x1800b3c18  call    ?IsTrue@KdcProxyGpoValue@@CA_NK@Z; KdcProxyGpoValue::IsTrue(ulong)
0x1800b3c1d  cmp     al, r8b
0x1800b3c20  jnz     short loc_1800B3C38
  ... truncated ...
```
