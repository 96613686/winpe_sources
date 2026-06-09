# InitializeSuspendFolderPolicyAndUploadTaskConfig

- ea: `0x1800029d0`
- end: `0x180002f0b`
- name: `InitializeSuspendFolderPolicyAndUploadTaskConfig`
- size: `1339`
- prototype: `void __fastcall(HKEY, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800029d0`
- `0x180002f14`
- `0x180002f6c`
- `0x180003090`
- `0x180005b54`
- `0x180006a9c`
- `0x18000a520`
- `0x18000aef8`
- `0x18000f86c`
- `0x18000fca8`
- `0x180019380`
- `0x180019af8`
- `0x180019cdc`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002eb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c2d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002bfb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002bfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ae6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800029fd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800029fd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002a34`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002a34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b90`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002bc8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002bc8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c09`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002a8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002a8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d33`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002aac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002aac`

## string_xrefs

- `0x180002ec5`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x180002ef7`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
void __fastcall InitializeSuspendFolderPolicyAndUploadTaskConfig(HKEY a1, int a2)
{
  CRupUserList *v4; // rcx
  __int64 v5; // rax
  __int64 v7; // rdi
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  __int64 v10; // r10
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // r9
  WCHAR *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  WCHAR *v18; // rdx
  signed int v19; // edi
  LPWSTR v20; // rcx
  LSTATUS LastState; // eax
  unsigned __int16 *v22; // rbx
  LPWSTR v23; // rcx
  HKEY v24; // rcx
  int v25; // eax
  CRupUserList *v26; // rcx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rax
  WCHAR *v30; // rcx
  __int64 v31; // rcx
  LPWSTR v32; // rdx
  WCHAR *v33; // rax
  __int64 i; // rdi
  WCHAR *v35; // rcx
  LSTATUS v36; // eax
  signed int LastError; // eax
  signed int v38; // eax
  unsigned int v39; // r14d
  unsigned int j; // edi
  unsigned __int16 *v41; // r15
  int v42; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD v44[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  void **v47[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v48[64]; // [rsp+80h] [rbp-80h] BYREF
  PSID TokenInformation[9]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( CoInitializeEx(0, 0) >= 0 )
  {
    v47[0] = &CscSuspendLogProfsvc::`vftable';
    if ( a2 )
    {
      CscSuspendPolicy_LogOn(a1, v47);
      if ( !(unsigned int)CHiveUploadTaskConfigurator::_IsRupUser(a1) )
      {
LABEL_4:
        CoUninitialize();
        return;
      }
      v27 = CRupUserList::AddUser(v4, a1);
      if ( v27 >= 0 )
      {
        v27 = CHiveUploadTaskConfigurator::_ConfigureTask();
        if ( v27 >= 0 )
          goto LABEL_4;
        v28 = 260;
      }
      else
      {
        v28 = 259;
      }
    }
    else
    {
      hKey = 0;
      v44[0] = 0;
      if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x44u, v44) )
      {
        StringSid[0] = 0;
        if ( ConvertSidToStringSidW(TokenInformation[0], StringSid) )
        {
          v5 = -1;
          while ( StringSid[0][++v5] != 0 )
            ;
          v7 = (unsigned int)(v5 + 58);
          v8 = (WCHAR *)CoTaskMemAlloc(2 * v7);
          v9 = v8;
          if ( v8 )
          {
            *v8 = 0;
            v10 = 2147483646;
            if ( (unsigned __int64)(v7 - 1) > 0x7FFFFFFE )
              goto LABEL_23;
            v11 = (unsigned int)v7;
            v12 = v9;
            do
            {
              if ( !*v12 )
              {
                v13 = (unsigned int)v7 - v11;
                goto LABEL_15;
              }
              ++v12;
              --v11;
            }
            while ( v11 );
            v13 = 0;
LABEL_15:
            if ( !v11 )
              goto LABEL_23;
            v14 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\";
            v15 = &v9[v13];
            v16 = 2147483646;
            v17 = v7 - v13;
            if ( v7 != v13 )
            {
              do
              {
                if ( !v16 )
                  break;
                if ( !*v14 )
                  break;
                *v15++ = *v14++;
                --v16;
                --v17;
              }
              while ( v17 );
            }
            v18 = v15 - 1;
            if ( v17 )
              v18 = v15;
            *v18 = 0;
            if ( !v17 )
              goto LABEL_23;
            v29 = v7;
            v30 = v9;
            do
            {
              if ( !*v30 )
              {
                v31 = v7 - v29;
                goto LABEL_43;
              }
              ++v30;
              --v29;
            }
            while ( v29 );
            v31 = 0;
LABEL_43:
            if ( !v29 )
              goto LABEL_23;
            v32 = StringSid[0];
            v33 = &v9[v31];
            for ( i = v7 - v31; i; --i )
            {
              if ( !v10 )
                break;
              if ( !*v32 )
                break;
              *v33++ = *v32++;
              --v10;
            }
            v35 = v33 - 1;
            if ( i )
              v35 = v33;
            *v35 = 0;
            if ( i )
            {
              v36 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
              v19 = v36;
              if ( v36 )
              {
                if ( v36 > 0 )
                  v19 = (unsigned __int16)v36 | 0x80070000;
              }
              else
              {
                v19 = 0;
              }
            }
            else
            {
LABEL_23:
              v19 = -2147418113;
            }
          }
          else
          {
            v19 = -2147024882;
          }
          CoTaskMemFree(v9);
        }
        else
        {
          LastError = GetLastError();
          v19 = LastError;
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
        }
        v20 = StringSid[0];
        StringSid[0] = 0;
        LocalFree(v20);
      }
      else
      {
        v38 = GetLastError();
        v19 = v38;
        if ( v38 > 0 )
          v19 = (unsigned __int16)v38 | 0x80070000;
      }
      if ( v19 >= 0 )
      {
        StringSid[0] = 0;
        v44[0] = 0;
        LastState = LoadLastState(hKey, StringSid, v44);
        v22 = StringSid[0];
        if ( LastState >= 0 )
        {
          if ( ImpersonateLoggedOnUser(a1) )
          {
            StringSid[0] = 0;
            if ( CoCreateInstance(
                   &CLSID_OfflineFilesCache,
                   0,
                   1u,
                   &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
                   (LPVOID *)StringSid) >= 0 )
            {
              memset_0(v48, 0, sizeof(v48));
              v39 = MultiStringToArray(v22, v44[0], (const unsigned __int16 **)v48);
              for ( j = 0; j < v39; ++j )
              {
                ReturnLength = 0;
                v41 = v48[j];
                *(_QWORD *)v44 = v41;
                v42 = (*(__int64 (__fastcall **)(LPWSTR, _QWORD, DWORD *, __int64))(*(_QWORD *)StringSid[0] + 24LL))(
                        StringSid[0],
                        0,
                        v44,
                        1);
                if ( v42 < 0 )
                  (*((void (__fastcall **)(void ***, _QWORD, unsigned __int16 *))v47[0] + 3))(
                    v47,
                    (unsigned int)v42,
                    v41);
              }
            }
            RevertToSelf();
            v23 = StringSid[0];
            if ( StringSid[0] )
            {
              StringSid[0] = 0;
              (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)v23 + 16LL))(v23);
            }
          }
          else
          {
            GetLastError();
          }
        }
        CoTaskMemFree(v22);
      }
      v24 = hKey;
      hKey = 0;
      if ( v24 )
        RegCloseKey(v24);
      hKey = a1;
      StringSid[0] = (LPWSTR)&hKey;
      v44[0] = 0;
      StringSid[1] = (LPWSTR)v44;
      v25 = lambda_b41eca68381dbaccfa3ca70d9f77ac5d_::operator()(StringSid);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x12A,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
          (const char *)(unsigned int)v25);
      if ( !v44[0] )
        goto LABEL_4;
      v27 = CRupUserList::RemoveUser(v26, a1);
      if ( v27 >= 0 )
      {
        v27 = CHiveUploadTaskConfigurator::_ConfigureTask();
        if ( v27 >= 0 )
          goto LABEL_4;
        v28 = 270;
      }
      else
      {
        v28 = 269;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)(unsigned int)v27,
      ReturnLength);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1800029d0  push    rbp
0x1800029d2  push    rbx
0x1800029d3  push    rsi
0x1800029d4  lea     rbp, [rsp-1E0h]
0x1800029dc  sub     rsp, 2E0h
0x1800029e3  mov     rax, cs:__security_cookie
0x1800029ea  xor     rax, rsp
0x1800029ed  mov     [rbp+1F0h+var_28], rax
0x1800029f4  mov     ebx, edx
0x1800029f6  mov     rsi, rcx
0x1800029f9  xor     edx, edx; dwCoInit
0x1800029fb  xor     ecx, ecx; pvReserved
0x1800029fd  call    cs:__imp_CoInitializeEx
0x180002a03  test    eax, eax
0x180002a05  js      short loc_180002A3A
0x180002a07  lea     rax, ??_7CscSuspendLogProfsvc@@6B@; const CscSuspendLogProfsvc::`vftable'
0x180002a0e  mov     rcx, rsi; void *
0x180002a11  mov     [rsp+2F0h+var_280], rax
0x180002a16  test    ebx, ebx
0x180002a18  jz      short loc_180002A54
0x180002a1a  lea     rdx, [rsp+2F0h+var_280]; struct CscSuspendLog *
0x180002a1f  call    ?CscSuspendPolicy_LogOn@@YAXPEAXPEAVCscSuspendLog@@@Z; CscSuspendPolicy_LogOn(void *,CscSuspendLog *)
0x180002a24  mov     rcx, rsi; void *
0x180002a27  call    ?_IsRupUser@CHiveUploadTaskConfigurator@@CAHPEAX@Z; CHiveUploadTaskConfigurator::_IsRupUser(void *)
0x180002a2c  test    eax, eax
0x180002a2e  jnz     loc_180002D97
0x180002a34  call    cs:__imp_CoUninitialize
0x180002a3a  mov     rcx, [rbp+1F0h+var_28]
0x180002a41  xor     rcx, rsp; StackCookie
0x180002a44  call    __security_check_cookie
0x180002a49  add     rsp, 2E0h
0x180002a50  pop     rsi
0x180002a51  pop     rbx
0x180002a52  pop     rbp
0x180002a53  retn
0x180002a54  lea     rax, [rsp+2F0h+var_2A0]
0x180002a59  mov     [rsp+2F0h+arg_8], rdi
0x180002a61  mov     [rsp+2F0h+arg_10], r12
0x180002a69  lea     r8, [rbp+1F0h+TokenInformation]; TokenInformation
0x180002a70  xor     r12d, r12d
0x180002a73  mov     [rsp+2F0h+ReturnLength], rax; ReturnLength
0x180002a78  mov     r9d, 44h ; 'D'; TokenInformationLength
0x180002a7e  mov     [rsp+2F0h+hKey], r12
0x180002a83  mov     edx, 1; TokenInformationClass
0x180002a88  mov     [rsp+2F0h+var_2A0], r12d
0x180002a8d  call    cs:__imp_GetTokenInformation
0x180002a93  test    eax, eax
0x180002a95  jz      loc_180002D79
0x180002a9b  mov     rcx, [rbp+1F0h+TokenInformation]; Sid
0x180002aa2  lea     rdx, [rsp+2F0h+StringSid]; StringSid
0x180002aa7  mov     [rsp+2F0h+StringSid], r12
0x180002aac  call    cs:__imp_ConvertSidToStringSidW
0x180002ab2  test    eax, eax
0x180002ab4  jz      loc_180002D5B
0x180002aba  mov     rcx, [rsp+2F0h+StringSid]
0x180002abf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002ac6  nop     word ptr [rax+rax+00000000h]
0x180002ad0  cmp     [rcx+rax*2+2], r12w
0x180002ad6  lea     rax, [rax+1]
0x180002ada  jnz     short loc_180002AD0
0x180002adc  lea     rdi, [rax+3Ah]
0x180002ae0  mov     edi, edi
0x180002ae2  lea     rcx, [rdi+rdi]; cb
0x180002ae6  call    cs:__imp_CoTaskMemAlloc
0x180002aec  mov     rbx, rax
0x180002aef  test    rax, rax
0x180002af2  jz      loc_180002DF0
0x180002af8  mov     [rax], r12w
0x180002afc  mov     r10d, 7FFFFFFEh
0x180002b02  lea     rax, [rdi-1]
0x180002b06  cmp     rax, r10
0x180002b09  ja      short loc_180002B78
0x180002b0b  mov     eax, edi
0x180002b0d  mov     rcx, rbx
0x180002b10  mov     edx, edi
0x180002b12  cmp     [rcx], r12w
0x180002b16  jnz     loc_180002DC4
0x180002b1c  sub     rdx, rax
0x180002b1f  test    rax, rax
0x180002b22  jz      short loc_180002B78
0x180002b24  mov     rax, rdi
0x180002b27  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180002b2e  lea     r8, [rbx+rdx*2]
0x180002b32  mov     rcx, r10
0x180002b35  sub     rax, rdx
0x180002b38  jz      short loc_180002B63
0x180002b3a  nop     word ptr [rax+rax+00h]
0x180002b40  test    rcx, rcx
0x180002b43  jz      short loc_180002B63
0x180002b45  movzx   edx, word ptr [r9]
0x180002b49  test    dx, dx
0x180002b4c  jz      short loc_180002B63
0x180002b4e  mov     [r8], dx
0x180002b52  add     r9, 2
0x180002b56  add     r8, 2
0x180002b5a  dec     rcx
0x180002b5d  sub     rax, 1
0x180002b61  jnz     short loc_180002B40
0x180002b63  test    rax, rax
0x180002b66  lea     rdx, [r8-2]
0x180002b6a  cmovnz  rdx, r8
0x180002b6e  mov     [rdx], r12w
0x180002b72  jnz     loc_180002CAD
0x180002b78  mov     edi, 8000FFFFh
0x180002b7d  mov     rcx, rbx; pv
0x180002b80  call    cs:__imp_CoTaskMemFree
0x180002b86  mov     rcx, [rsp+2F0h+StringSid]; hMem
0x180002b8b  mov     [rsp+2F0h+StringSid], r12
0x180002b90  call    cs:__imp_LocalFree
0x180002b96  test    edi, edi
0x180002b98  js      loc_180002C33
0x180002b9e  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x180002ba3  lea     r8, [rsp+2F0h+var_2A0]; unsigned int *
0x180002ba8  lea     rdx, [rsp+2F0h+StringSid]; unsigned __int16 **
0x180002bad  mov     [rsp+2F0h+StringSid], r12
0x180002bb2  mov     [rsp+2F0h+var_2A0], r12d
0x180002bb7  call    ?LoadLastState@@YAJPEAUHKEY__@@PEAPEAGAEAI@Z; LoadLastState(HKEY__ *,ushort * *,uint &)
0x180002bbc  mov     rbx, [rsp+2F0h+StringSid]
0x180002bc1  test    eax, eax
0x180002bc3  js      short loc_180002C2A
0x180002bc5  mov     rcx, rsi; hToken
0x180002bc8  call    cs:__imp_ImpersonateLoggedOnUser
0x180002bce  test    eax, eax
0x180002bd0  jz      loc_180002EB3
0x180002bd6  lea     rax, [rsp+2F0h+StringSid]
0x180002bdb  mov     [rsp+2F0h+StringSid], r12
0x180002be0  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180002be7  mov     [rsp+2F0h+ReturnLength], rax; int
0x180002bec  xor     edx, edx; pUnkOuter
0x180002bee  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180002bf5  mov     r8d, 1; dwClsContext
0x180002bfb  call    cs:__imp_CoCreateInstance
0x180002c01  test    eax, eax
0x180002c03  jns     loc_180002DFA
0x180002c09  call    cs:__imp_RevertToSelf
0x180002c0f  mov     rcx, [rsp+2F0h+StringSid]
0x180002c14  test    rcx, rcx
0x180002c17  jz      short loc_180002C2A
0x180002c19  mov     [rsp+2F0h+StringSid], r12
0x180002c1e  mov     rax, [rcx]
0x180002c21  mov     rax, [rax+10h]
0x180002c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2a  mov     rcx, rbx; pv
0x180002c2d  call    cs:__imp_CoTaskMemFree
0x180002c33  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002c38  mov     rdi, [rsp+2F0h+arg_8]
0x180002c40  mov     [rsp+2F0h+hKey], r12
0x180002c45  test    rcx, rcx
0x180002c48  jz      short loc_180002C50
0x180002c4a  call    cs:__imp_RegCloseKey
0x180002c50  lea     rax, [rsp+2F0h+hKey]
0x180002c55  mov     [rsp+2F0h+hKey], rsi
0x180002c5a  mov     [rsp+2F0h+StringSid], rax
0x180002c5f  lea     rcx, [rsp+2F0h+StringSid]
0x180002c64  lea     rax, [rsp+2F0h+var_2A0]
0x180002c69  mov     [rsp+2F0h+var_2A0], r12d
0x180002c6e  mov     [rsp+2F0h+var_290], rax
0x180002c73  call    _lambda_b41eca68381dbaccfa3ca70d9f77ac5d___operator__
0x180002c78  mov     r12, [rsp+2F0h+arg_10]
0x180002c80  test    eax, eax
0x180002c82  js      loc_180002EBE
0x180002c88  cmp     [rsp+2F0h+var_2A0], 0
0x180002c8d  jz      loc_180002A34
0x180002c93  mov     rdx, rsi; void *
0x180002c96  call    ?RemoveUser@CRupUserList@@QEAAJPEAX@Z; CRupUserList::RemoveUser(void *)
0x180002c9b  test    eax, eax
0x180002c9d  jns     loc_180002EDE
0x180002ca3  mov     edx, 10Dh
0x180002ca8  jmp     loc_180002EF0
0x180002cad  mov     rax, rdi
0x180002cb0  mov     rcx, rbx
0x180002cb3  cmp     [rcx], r12w
0x180002cb7  jnz     loc_180002DDA
0x180002cbd  mov     rcx, rdi
0x180002cc0  sub     rcx, rax
0x180002cc3  test    rax, rax
0x180002cc6  jz      loc_180002B78
0x180002ccc  mov     rdx, [rsp+2F0h+StringSid]
0x180002cd1  lea     rax, [rbx+rcx*2]
0x180002cd5  sub     rdi, rcx
0x180002cd8  jz      short loc_180002D01
0x180002cda  nop     word ptr [rax+rax+00h]
0x180002ce0  test    r10, r10
0x180002ce3  jz      short loc_180002D01
0x180002ce5  movzx   ecx, word ptr [rdx]
0x180002ce8  test    cx, cx
0x180002ceb  jz      short loc_180002D01
0x180002ced  mov     [rax], cx
0x180002cf0  add     rdx, 2
0x180002cf4  add     rax, 2
0x180002cf8  dec     r10
0x180002cfb  sub     rdi, 1
0x180002cff  jnz     short loc_180002CE0
0x180002d01  test    rdi, rdi
0x180002d04  lea     rcx, [rax-2]
0x180002d08  cmovnz  rcx, rax
0x180002d0c  mov     [rcx], r12w
0x180002d10  jz      loc_180002B78
0x180002d16  lea     rax, [rsp+2F0h+hKey]
0x180002d1b  mov     r9d, 20019h; samDesired
0x180002d21  xor     r8d, r8d; ulOptions
0x180002d24  mov     [rsp+2F0h+ReturnLength], rax; phkResult
0x180002d29  mov     rdx, rbx; lpSubKey
0x180002d2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002d33  call    cs:__imp_RegOpenKeyExW
0x180002d39  mov     edi, eax
0x180002d3b  test    eax, eax
0x180002d3d  jnz     short loc_180002D47
0x180002d3f  mov     edi, r12d
0x180002d42  jmp     loc_180002B7D
0x180002d47  jle     loc_180002B7D
0x180002d4d  movzx   edi, ax
0x180002d50  or      edi, 80070000h
0x180002d56  jmp     loc_180002B7D
0x180002d5b  call    cs:__imp_GetLastError
0x180002d61  mov     edi, eax
0x180002d63  test    eax, eax
0x180002d65  jle     loc_180002B86
0x180002d6b  movzx   edi, ax
0x180002d6e  or      edi, 80070000h
0x180002d74  jmp     loc_180002B86
0x180002d79  call    cs:__imp_GetLastError
0x180002d7f  mov     edi, eax
0x180002d81  test    eax, eax
0x180002d83  jle     loc_180002B96
0x180002d89  movzx   edi, ax
0x180002d8c  or      edi, 80070000h
0x180002d92  jmp     loc_180002B96
0x180002d97  mov     rdx, rsi; void *
0x180002d9a  call    ?AddUser@CRupUserList@@QEAAJPEAX@Z; CRupUserList::AddUser(void *)
0x180002d9f  test    eax, eax
0x180002da1  jns     short loc_180002DAD
0x180002da3  mov     edx, 103h
0x180002da8  jmp     loc_180002EF0
0x180002dad  call    ?_ConfigureTask@CHiveUploadTaskConfigurator@@CAJXZ; CHiveUploadTaskConfigurator::_ConfigureTask(void)
0x180002db2  test    eax, eax
0x180002db4  jns     loc_180002A34
0x180002dba  mov     edx, 104h
0x180002dbf  jmp     loc_180002EF0
0x180002dc4  add     rcx, 2
0x180002dc8  sub     rax, 1
0x180002dcc  jnz     loc_180002B12
0x180002dd2  mov     rdx, r12
0x180002dd5  jmp     loc_180002B1F
0x180002dda  add     rcx, 2
0x180002dde  sub     rax, 1
0x180002de2  jnz     loc_180002CB3
0x180002de8  mov     rcx, r12
0x180002deb  jmp     loc_180002CC3
0x180002df0  mov     edi, 8007000Eh
0x180002df5  jmp     loc_180002B7D
0x180002dfa  xor     edx, edx; Val
0x180002dfc  mov     [rsp+2F0h+var_18], r14
0x180002e04  mov     r8d, 200h; Size
0x180002e0a  lea     rcx, [rbp+1F0h+var_270]; void *
0x180002e0e  call    memset_0
0x180002e13  mov     edx, [rsp+2F0h+var_2A0]; unsigned int
0x180002e17  lea     r8, [rbp+1F0h+var_270]; unsigned __int16 **
0x180002e1b  mov     rcx, rbx; unsigned __int16 *
0x180002e1e  call    ?MultiStringToArray@@YAIPEBGIPEAPEBGI@Z; MultiStringToArray(ushort const *,uint,ushort const * *,uint)
0x180002e23  mov     r14d, eax
0x180002e26  mov     edi, r12d
0x180002e29  test    eax, eax
0x180002e2b  jz      short loc_180002EA6
0x180002e2d  mov     [rsp+2F0h+var_20], r15
0x180002e35  mov     [rsp+2F0h+var_2B0], r12
0x180002e3a  lea     r8, [rsp+2F0h+var_2A0]
0x180002e3f  mov     [rsp+2F0h+var_2B8], r12
0x180002e44  mov     r9d, 1
0x180002e4a  mov     ecx, edi
0x180002e4c  mov     [rsp+2F0h+var_2C0], r12
0x180002e51  mov     [rsp+2F0h+var_2C8], 30000004h
0x180002e59  mov     dword ptr [rsp+2F0h+ReturnLength], r12d
0x180002e5e  mov     r15, [rbp+rcx*8+1F0h+var_270]
0x180002e63  mov     rcx, [rsp+2F0h+StringSid]
0x180002e68  mov     qword ptr [rsp+2F0h+var_2A0], r15
0x180002e6d  mov     rdx, [rcx]
0x180002e70  mov     rax, [rdx+18h]
0x180002e74  xor     edx, edx
0x180002e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7b  mov     edx, eax
0x180002e7d  test    eax, eax
0x180002e7f  jns     short loc_180002E97
0x180002e81  mov     rcx, [rsp+2F0h+var_280]
0x180002e86  mov     r8, r15
0x180002e89  mov     rax, [rcx+18h]
0x180002e8d  lea     rcx, [rsp+2F0h+var_280]
0x180002e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e97  inc     edi
0x180002e99  cmp     edi, r14d
0x180002e9c  jb      short loc_180002E35
0x180002e9e  mov     r15, [rsp+2F0h+var_20]
0x180002ea6  mov     r14, [rsp+2F0h+var_18]
0x180002eae  jmp     loc_180002C09
0x180002eb3  call    cs:__imp_GetLastError
0x180002eb9  jmp     loc_180002C2A
0x180002ebe  mov     rcx, [rbp+1F8h]; this
0x180002ec5  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180002ecc  mov     r9d, eax; char *
0x180002ecf  mov     edx, 12Ah; void *
  ... truncated ...
```
