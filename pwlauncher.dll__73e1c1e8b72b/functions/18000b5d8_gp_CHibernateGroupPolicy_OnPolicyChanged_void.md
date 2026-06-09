# gp::CHibernateGroupPolicy::OnPolicyChanged(void)

- ea: `0x18000b5d8`
- end: `0x18000b92d`
- name: `?OnPolicyChanged@CHibernateGroupPolicy@gp@@SAXXZ`
- size: `853`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009100`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180008ac8`
- `0x18000b3ac`
- `0x18000b5d8`
- `0x18000b934`
- `0x18000b9d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000b77b`
- `ADVAPI32!RegCloseKey` at `0x18000b77b`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b722`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b722`
- `ADVAPI32!RegSetValueExW` at `0x18000b766`
- `ADVAPI32!RegSetValueExW` at `0x18000b766`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b6bb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b6bb`
- `POWRPROF!PowerInformationWithPrivileges` at `0x18000b798`
- `POWRPROF!PowerInformationWithPrivileges` at `0x18000b798`

## pseudocode

```c
void gp::CHibernateGroupPolicy::OnPolicyChanged(void)
{
  int Policy; // eax
  bool v1; // dl
  const wchar_t *v2; // r9
  LSTATUS v3; // r9d
  HKEY v4; // rbx
  LSTATUS v5; // r9d
  LSTATUS v6; // r9d
  int v7; // eax
  unsigned int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  int v14; // ebx
  unsigned int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // ebx
  unsigned int v19; // edx
  int v20; // r8d
  int v21; // r9d
  int v22; // ebx
  bool v23; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h] BYREF
  HKEY v25; // [rsp+A0h] [rbp+30h] BYREF

  Policy = gp::CHibernateGroupPolicy::GetPolicy();
  if ( Policy == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids);
  }
  else
  {
    v1 = Policy == 2;
    v23 = Policy == 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v2 = L"Enabled";
      if ( Policy != 2 )
        v2 = L"Disabled";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids, v2);
      v1 = v23;
    }
    if ( v1 )
    {
      hKey = 0;
      v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH, 0, 0x20006u, &hKey);
      if ( v3 )
      {
        if ( v3 != 2 )
        {
          if ( v3 > 0 )
            v19 = (unsigned __int16)v3 | 0x80070000;
          else
            v19 = v3;
          ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, v19);
          v22 = (int)hKey;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              v20,
              v21,
              (__int64)"CAtlException( HRESULT_FROM_WIN32( result ) )",
              (char)hKey);
          LODWORD(hKey) = v22;
          throw (ATL::CAtlException *)&hKey;
        }
        LODWORD(hKey) = 0;
        v25 = 0;
        v5 = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH,
               0,
               0,
               0,
               0x2001Fu,
               0,
               &v25,
               (LPDWORD)&hKey);
        if ( v5 )
        {
          if ( v5 > 0 )
            v15 = (unsigned __int16)v5 | 0x80070000;
          else
            v15 = v5;
          ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, v15);
          v18 = (int)hKey;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              v16,
              v17,
              (__int64)"CAtlException( HRESULT_FROM_WIN32( result ) )",
              (char)hKey);
          LODWORD(hKey) = v18;
          throw (ATL::CAtlException *)&hKey;
        }
        v4 = v25;
      }
      else
      {
        v4 = hKey;
      }
      LODWORD(hKey) = 0;
      v6 = RegSetValueExW(v4, gp::CHibernateGroupPolicy::HIBER_BOOT_VALUE_NAME, 0, 4u, (const BYTE *)&hKey, 4u);
      if ( v6 )
      {
        if ( v6 > 0 )
          v8 = (unsigned __int16)v6 | 0x80070000;
        else
          v8 = v6;
        ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, v8);
        v11 = (int)hKey;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            v9,
            v10,
            (__int64)"CAtlException( HRESULT_FROM_WIN32( result ) )",
            (char)hKey);
        LODWORD(hKey) = v11;
        throw (ATL::CAtlException *)&hKey;
      }
      if ( v4 )
        RegCloseKey(v4);
    }
    v7 = PowerInformationWithPrivileges(10, &v23, 1);
    if ( v7 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)&hKey, v7 | 0x10000000);
      v14 = (int)hKey;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          v12,
          v13,
          (__int64)"CAtlException( HRESULT_FROM_NT( status ) )",
          (char)hKey);
      LODWORD(hKey) = v14;
      throw (ATL::CAtlException *)&hKey;
    }
  }
}

```

## disassembly

```asm
0x18000b5d8  push    rbp
0x18000b5da  push    rbx
0x18000b5db  push    rdi
0x18000b5dc  mov     rbp, rsp
0x18000b5df  sub     rsp, 70h
0x18000b5e3  call    ?GetPolicy@CHibernateGroupPolicy@gp@@CA?AW4HibernateGroupPolicy@2@XZ; gp::CHibernateGroupPolicy::GetPolicy(void)
0x18000b5e8  cmp     eax, 1
0x18000b5eb  jnz     short loc_18000B621
0x18000b5ed  lea     rdi, WPP_GLOBAL_Control
0x18000b5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5fb  cmp     rcx, rdi
0x18000b5fe  jz      short loc_18000B619
0x18000b600  test    byte ptr [rcx+1Ch], 4
0x18000b604  jz      short loc_18000B619
0x18000b606  lea     edx, [rax+0Ch]
0x18000b609  lea     r8, WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids
0x18000b610  mov     rcx, [rcx+10h]
0x18000b614  call    WPP_SF_
0x18000b619  add     rsp, 70h
0x18000b61d  pop     rdi
0x18000b61e  pop     rbx
0x18000b61f  pop     rbp
0x18000b620  retn
0x18000b621  cmp     eax, 2
0x18000b624  setz    dl
0x18000b627  mov     [rbp+arg_0], dl
0x18000b62a  lea     rdi, WPP_GLOBAL_Control
0x18000b631  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b638  cmp     rcx, rdi
0x18000b63b  jz      short loc_18000B670
0x18000b63d  test    byte ptr [rcx+1Ch], 4
0x18000b641  jz      short loc_18000B670
0x18000b643  lea     rdx, aDisabled; "Disabled"
0x18000b64a  lea     r9, aEnabled; "Enabled"
0x18000b651  cmp     eax, 2
0x18000b654  cmovnz  r9, rdx
0x18000b658  mov     edx, 0Eh
0x18000b65d  lea     r8, WPP_41015684a9fe312220e27f269d4aeb4f_Traceguids
0x18000b664  mov     rcx, [rcx+10h]
0x18000b668  call    WPP_SF_S
0x18000b66d  mov     dl, [rbp+arg_0]
0x18000b670  test    dl, dl
0x18000b672  jz      loc_18000B781
0x18000b678  mov     [rbp+var_20], 0
0x18000b680  mov     [rbp+var_18], 0
0x18000b688  mov     [rbp+var_10], 0
0x18000b690  mov     [rbp+hKey], 0
0x18000b698  lea     rax, [rbp+hKey]
0x18000b69c  mov     [rsp+70h+phkResult], rax; phkResult
0x18000b6a1  mov     r9d, 20006h; samDesired
0x18000b6a7  xor     r8d, r8d; ulOptions
0x18000b6aa  mov     rdx, cs:?HIBER_BOOT_KEY_PATH@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpSubKey
0x18000b6b1  mov     rbx, 0FFFFFFFF80000002h
0x18000b6b8  mov     rcx, rbx; hKey
0x18000b6bb  call    cs:__imp_RegOpenKeyExW
0x18000b6c1  mov     r9d, eax
0x18000b6c4  test    eax, eax
0x18000b6c6  jnz     short loc_18000B6CE
0x18000b6c8  mov     rbx, [rbp+hKey]
0x18000b6cc  jmp     short loc_18000B737
0x18000b6ce  cmp     r9d, 2
0x18000b6d2  jnz     loc_18000B8C9
0x18000b6d8  mov     dword ptr [rbp+hKey], 0
0x18000b6df  mov     [rbp+arg_10], 0
0x18000b6e7  lea     rax, [rbp+hKey]
0x18000b6eb  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18000b6f0  lea     rax, [rbp+arg_10]
0x18000b6f4  mov     [rsp+70h+var_38], rax; phkResult
0x18000b6f9  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000b702  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18000b70a  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x18000b712  xor     r9d, r9d; lpClass
0x18000b715  xor     r8d, r8d; Reserved
0x18000b718  mov     rdx, cs:?HIBER_BOOT_KEY_PATH@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpSubKey
0x18000b71f  mov     rcx, rbx; hKey
0x18000b722  call    cs:__imp_RegCreateKeyExW
0x18000b728  mov     r9d, eax
0x18000b72b  test    eax, eax
0x18000b72d  jnz     loc_18000B865
0x18000b733  mov     rbx, [rbp+arg_10]
0x18000b737  mov     [rbp+var_20], rbx
0x18000b73b  mov     dword ptr [rbp+hKey], 0
0x18000b742  mov     [rsp+70h+samDesired], 4; cbData
0x18000b74a  lea     rax, [rbp+hKey]
0x18000b74e  mov     [rsp+70h+phkResult], rax; lpData
0x18000b753  mov     r9d, 4; dwType
0x18000b759  xor     r8d, r8d; Reserved
0x18000b75c  mov     rdx, cs:?HIBER_BOOT_VALUE_NAME@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; lpValueName
0x18000b763  mov     rcx, rbx; hKey
0x18000b766  call    cs:__imp_RegSetValueExW
0x18000b76c  mov     r9d, eax
0x18000b76f  test    eax, eax
0x18000b771  jnz     short loc_18000B7AA
0x18000b773  test    rbx, rbx
0x18000b776  jz      short loc_18000B781
0x18000b778  mov     rcx, rbx; hKey
0x18000b77b  call    cs:__imp_RegCloseKey
0x18000b781  mov     dword ptr [rsp+70h+phkResult], 0
0x18000b789  xor     r9d, r9d
0x18000b78c  lea     r8d, [r9+1]
0x18000b790  lea     rdx, [rbp+arg_0]
0x18000b794  lea     ecx, [r9+0Ah]
0x18000b798  call    cs:__imp_PowerInformationWithPrivileges
0x18000b79e  mov     r9d, eax
0x18000b7a1  test    eax, eax
0x18000b7a3  js      short loc_18000B80E
0x18000b7a5  jmp     loc_18000B619
0x18000b7aa  test    r9d, r9d
0x18000b7ad  jg      short loc_18000B7B4
0x18000b7af  mov     edx, r9d
0x18000b7b2  jmp     short loc_18000B7BE
0x18000b7b4  movzx   edx, r9w
0x18000b7b8  or      edx, 80070000h; int
0x18000b7be  lea     rcx, [rbp+hKey]; this
0x18000b7c2  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b7c7  mov     ebx, dword ptr [rbp+hKey]
0x18000b7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7d1  cmp     rcx, rdi
0x18000b7d4  jz      short loc_18000B7FA
0x18000b7d6  test    byte ptr [rcx+1Ch], 1
0x18000b7da  jz      short loc_18000B7FA
0x18000b7dc  mov     edx, 11h
0x18000b7e1  mov     [rsp+70h+samDesired], ebx
0x18000b7e5  lea     rax, aCatlexceptionH_1; "CAtlException( HRESULT_FROM_WIN32( resu"...
0x18000b7ec  mov     [rsp+70h+phkResult], rax
0x18000b7f1  mov     rcx, [rcx+10h]
0x18000b7f5  call    WPP_SF_DsD
0x18000b7fa  mov     dword ptr [rbp+hKey], ebx
0x18000b7fd  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b804  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b808  call    _CxxThrowException_0
0x18000b80e  mov     edx, r9d
0x18000b811  bts     edx, 1Ch; int
0x18000b815  lea     rcx, [rbp+hKey]; this
0x18000b819  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b81e  mov     ebx, dword ptr [rbp+hKey]
0x18000b821  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b828  cmp     rcx, rdi
0x18000b82b  jz      short loc_18000B851
0x18000b82d  test    byte ptr [rcx+1Ch], 1
0x18000b831  jz      short loc_18000B851
0x18000b833  mov     edx, 12h
0x18000b838  mov     [rsp+70h+samDesired], ebx
0x18000b83c  lea     rax, aCatlexceptionH; "CAtlException( HRESULT_FROM_NT( status "...
0x18000b843  mov     [rsp+70h+phkResult], rax
0x18000b848  mov     rcx, [rcx+10h]
0x18000b84c  call    WPP_SF_DsD
0x18000b851  mov     dword ptr [rbp+hKey], ebx
0x18000b854  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b85b  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b85f  call    _CxxThrowException_0
0x18000b865  test    r9d, r9d
0x18000b868  jg      short loc_18000B86F
0x18000b86a  mov     edx, r9d
0x18000b86d  jmp     short loc_18000B879
0x18000b86f  movzx   edx, r9w
0x18000b873  or      edx, 80070000h; int
0x18000b879  lea     rcx, [rbp+hKey]; this
0x18000b87d  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b882  mov     ebx, dword ptr [rbp+hKey]
0x18000b885  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b88c  cmp     rcx, rdi
0x18000b88f  jz      short loc_18000B8B5
0x18000b891  test    byte ptr [rcx+1Ch], 1
0x18000b895  jz      short loc_18000B8B5
0x18000b897  mov     edx, 10h
0x18000b89c  mov     [rsp+70h+samDesired], ebx
0x18000b8a0  lea     rax, aCatlexceptionH_1; "CAtlException( HRESULT_FROM_WIN32( resu"...
0x18000b8a7  mov     [rsp+70h+phkResult], rax
0x18000b8ac  mov     rcx, [rcx+10h]
0x18000b8b0  call    WPP_SF_DsD
0x18000b8b5  mov     dword ptr [rbp+hKey], ebx
0x18000b8b8  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b8bf  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b8c3  call    _CxxThrowException_0
0x18000b8c9  test    r9d, r9d
0x18000b8cc  jg      short loc_18000B8D3
0x18000b8ce  mov     edx, r9d
0x18000b8d1  jmp     short loc_18000B8DD
0x18000b8d3  movzx   edx, r9w
0x18000b8d7  or      edx, 80070000h; int
0x18000b8dd  lea     rcx, [rbp+hKey]; this
0x18000b8e1  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000b8e6  mov     ebx, dword ptr [rbp+hKey]
0x18000b8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8f0  cmp     rcx, rdi
0x18000b8f3  jz      short loc_18000B919
0x18000b8f5  test    byte ptr [rcx+1Ch], 1
0x18000b8f9  jz      short loc_18000B919
0x18000b8fb  mov     edx, 0Fh
0x18000b900  mov     [rsp+70h+samDesired], ebx
0x18000b904  lea     rax, aCatlexceptionH_1; "CAtlException( HRESULT_FROM_WIN32( resu"...
0x18000b90b  mov     [rsp+70h+phkResult], rax
0x18000b910  mov     rcx, [rcx+10h]
0x18000b914  call    WPP_SF_DsD
0x18000b919  mov     dword ptr [rbp+hKey], ebx
0x18000b91c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b923  lea     rcx, [rbp+hKey]; pExceptionObject
0x18000b927  call    _CxxThrowException_0
```
