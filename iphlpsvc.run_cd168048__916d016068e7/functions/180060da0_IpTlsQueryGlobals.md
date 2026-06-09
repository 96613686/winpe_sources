# IpTlsQueryGlobals

- ea: `0x180060da0`
- end: `0x1800613be`
- name: `IpTlsQueryGlobals`
- size: `1566`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180004f50`
- `0x18000d7b0`
- `0x180013570`
- `0x18004b630`
- `0x18004c1c8`
- `0x180053058`
- `0x180060da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061323`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061323`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061366`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800611e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800611e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061375`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180060f7b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180060f7b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180060f9c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180060f9c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060e2e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060e96`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060eeb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060e2e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060e96`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060eeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061341`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061341`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061357`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060f5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060f5e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180060fd5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180060fd5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800612ec`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800612ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800610ce`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800611a6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061236`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800612a8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800610ce`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800611a6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061236`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800612a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006101a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006101a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180060f3c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180060f3c`

## string_xrefs

- `0x180061387`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180060fca`: `%windir%\temp\iphttps.txt`
- `0x18006106e`: `Detected target hardlink file path %s`

## pseudocode

```c
void __fastcall IpTlsQueryGlobals(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  HLOCAL v3; // rax
  void *v4; // r14
  HANDLE v5; // rdi
  __int64 *v6; // rcx
  int v7; // eax
  __int64 i; // rbx
  _OWORD *v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rdx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  struct _RTL_CRITICAL_SECTION *v16; // r15
  HANDLE *p_LockSemaphore; // rsi
  HANDLE *LockSemaphore; // rdx
  int v19; // eax
  bool v20; // zf
  HANDLE *v21; // rbx
  HANDLE *v22; // rdx
  HANDLE *v23; // rax
  DWORD LastError; // eax
  char v25[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  PACL NewAcl; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v31; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v32; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-98h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  __int128 v35; // [rsp+90h] [rbp-70h]
  _BYTE v36[522]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v37; // [rsp+2AAh] [rbp+1AAh]
  int v38; // [rsp+2ACh] [rbp+1ACh]
  __int128 v39; // [rsp+2B0h] [rbp+1B0h]
  __int64 v40; // [rsp+2C0h] [rbp+1C0h]
  __int64 v41; // [rsp+2C8h] [rbp+1C8h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v43; // [rsp+300h] [rbp+200h]
  __int64 v44; // [rsp+304h] [rbp+204h]
  int v45; // [rsp+31Ch] [rbp+21Ch]
  int v46; // [rsp+320h] [rbp+220h]
  _BYTE *v47; // [rsp+328h] [rbp+228h]
  int v48; // [rsp+330h] [rbp+230h]
  __int64 v49; // [rsp+334h] [rbp+234h]
  int v50; // [rsp+34Ch] [rbp+24Ch]
  int v51; // [rsp+350h] [rbp+250h]
  _BYTE *v52; // [rsp+358h] [rbp+258h]
  _BYTE pSid[80]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v54[80]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v55[80]; // [rsp+400h] [rbp+300h] BYREF
  WCHAR Dst[264]; // [rsp+450h] [rbp+350h] BYREF

  NumberOfBytesWritten = 0;
  NewAcl = 0;
  Buffer = 0;
  v37 = 0;
  memset_0(v36, 0, 0x22Eu);
  v25[0] = 0;
  cbSid = 68;
  v31 = 68;
  v32 = 68;
  memset(&SecurityAttributes, 0, 20);
  if ( CreateWellKnownSid(WinWorldSid, 0, pSid, &cbSid) )
  {
    memset_0(&pListOfExplicitEntries, 0, 0x90u);
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, v54, &v31) )
    {
      v44 = 1;
      v47 = v54;
      v43 = 0x10000000;
      v45 = 0;
      v46 = 2;
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v55, &v32) )
      {
        v48 = 0x10000000;
        v52 = v55;
        v49 = 1;
        v50 = 0;
        v51 = 2;
        if ( SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, &NewAcl) )
        {
          NewAcl = 0;
          goto LABEL_49;
        }
        v3 = LocalAlloc(0x40u, 0x28u);
        v4 = v3;
        if ( v3 )
        {
          if ( !InitializeSecurityDescriptor(v3, 1u) )
            goto LABEL_46;
          if ( !SetSecurityDescriptorDacl(v4, 1, NewAcl, 0) )
            goto LABEL_46;
          SecurityAttributes.nLength = 24;
          SecurityAttributes.lpSecurityDescriptor = v4;
          SecurityAttributes.bInheritHandle = 0;
          if ( ExpandEnvironmentStringsW(L"%windir%\\temp\\iphttps.txt", Dst, 0x104u) - 1 > 0x103 )
            goto LABEL_46;
          v5 = CreateFileW(Dst, 0x40000000u, 1u, &SecurityAttributes, 4u, 0x80u, 0);
          if ( v5 == (HANDLE)-1LL )
            goto LABEL_46;
          if ( GetLastError() == 183 )
          {
            if ( (unsigned int)IsHardLinkFile(v5, v25) )
            {
LABEL_45:
              CloseHandle(v5);
LABEL_46:
              LocalFree(v4);
              goto LABEL_47;
            }
            if ( v25[0] )
            {
              EventWrite0(0x800000, L"Detected target hardlink file path %s", Dst);
              goto LABEL_45;
            }
          }
          IpTlsAcquireLock(g_IpTlsInterfaceListLock);
          v6 = (__int64 *)g_IpTlsInterfaceListHead;
          if ( g_IpTlsInterfaceListHead )
          {
            if ( (__int64 *)g_IpTlsInterfaceListHead != &g_IpTlsInterfaceListHead )
            {
              v7 = Buffer;
              do
              {
                v6 = (__int64 *)*v6;
                Buffer = ++v7;
              }
              while ( v6 != &g_IpTlsInterfaceListHead );
            }
            if ( WriteFile(v5, &Buffer, 4u, &NumberOfBytesWritten, 0) )
            {
              for ( i = g_IpTlsInterfaceListHead; (__int64 *)i != &g_IpTlsInterfaceListHead; i = v10 )
              {
                v9 = v36;
                v10 = *(_QWORD *)i;
                v11 = 2;
                v38 = *(_DWORD *)(i + 1012);
                v12 = (_OWORD *)(i + 56);
                do
                {
                  *v9 = *v12;
                  v9[1] = v12[1];
                  v9[2] = v12[2];
                  v9[3] = v12[3];
                  v9[4] = v12[4];
                  v9[5] = v12[5];
                  v9[6] = v12[6];
                  v13 = v12[7];
                  v12 += 8;
                  v9[7] = v13;
                  v9 += 8;
                  --v11;
                }
                while ( v11 );
                *(_QWORD *)((char *)v9 - 3) = *(_QWORD *)((char *)v12 - 3);
                v14 = *(_OWORD *)(i + 1040);
                v40 = g_IpTlsGlobalStatsBytesIn;
                v41 = g_IpTlsGlobalStatsBytesOut;
                v39 = v14;
                if ( !WriteFile(v5, v36, 0x230u, &NumberOfBytesWritten, 0) )
                  goto LABEL_44;
                if ( *(_DWORD *)(i + 1012) )
                {
                  v15 = *(struct _RTL_CRITICAL_SECTION **)(i + 1104);
                  v28 = 0;
                  v34 = 0;
                  v16 = v15 + 6;
                  v35 = 0;
                  EnterCriticalSection(v15 + 6);
                  p_LockSemaphore = &v15[5].LockSemaphore;
                  LockSemaphore = (HANDLE *)v15[5].LockSemaphore;
                  if ( LockSemaphore != &v15[5].LockSemaphore )
                  {
                    v19 = v28;
                    do
                    {
                      v20 = LockSemaphore[2] == 0;
                      LockSemaphore = (HANDLE *)*LockSemaphore;
                      if ( !v20 )
                        v28 = ++v19;
                    }
                    while ( LockSemaphore != p_LockSemaphore );
                  }
                  if ( !WriteFile(v5, &v28, 4u, &NumberOfBytesWritten, 0) )
                  {
LABEL_39:
                    LeaveCriticalSection(v16);
                    goto LABEL_44;
                  }
                  v21 = (HANDLE *)*p_LockSemaphore;
                  while ( v21 != p_LockSemaphore )
                  {
                    v22 = v21;
                    v21 = (HANDLE *)*v21;
                    v23 = (HANDLE *)v22[2];
                    if ( v23 )
                    {
                      v34 = v23 == v22 + 2 ? 0LL : *(_OWORD *)(v23 - 3);
                      v35 = *((_OWORD *)v22 + 25);
                      if ( !WriteFile(v5, &v34, 0x20u, &NumberOfBytesWritten, 0) )
                        goto LABEL_39;
                    }
                  }
                  LeaveCriticalSection(v16);
                }
              }
              if ( !SetEndOfFile(v5) )
              {
                LastError = GetLastError();
                EventWrite0(0x800000, L"Fail to truncate current TLS file %d", LastError);
              }
            }
          }
LABEL_44:
          ReleaseMutex(g_IpTlsInterfaceListLock);
          goto LABEL_45;
        }
      }
    }
  }
LABEL_47:
  if ( NewAcl )
    LocalFree(NewAcl);
LABEL_49:
  SetEvent(Context);
  CloseHandle(Context);
  DereferenceServiceEx("IpTlsQueryGlobals", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c", 4603);
}

```

## disassembly

```asm
0x180060da0  push    rbp
0x180060da2  push    rbx
0x180060da3  push    rsi
0x180060da4  push    rdi
0x180060da5  push    r12
0x180060da7  push    r13
0x180060da9  push    r14
0x180060dab  push    r15
0x180060dad  lea     rbp, [rsp-578h]
0x180060db5  sub     rsp, 678h
0x180060dbc  mov     rax, cs:__security_cookie
0x180060dc3  xor     rax, rsp
0x180060dc6  mov     [rbp+5B0h+var_50], rax
0x180060dcd  xor     esi, esi
0x180060dcf  lea     rcx, [rbp+5B0h+var_610]; void *
0x180060dd3  mov     r13, rdx
0x180060dd6  mov     [rsp+6B0h+NumberOfBytesWritten], esi
0x180060dda  xor     eax, eax
0x180060ddc  mov     [rsp+6B0h+NewAcl], rsi
0x180060de1  xor     edx, edx; Val
0x180060de3  mov     [rsp+6B0h+Buffer], esi
0x180060de7  mov     r8d, 22Eh; Size
0x180060ded  mov     [rbp+5B0h+var_406], ax
0x180060df4  call    memset_0
0x180060df9  xor     eax, eax
0x180060dfb  mov     [rsp+6B0h+var_670], sil
0x180060e00  mov     [rsp+6B0h+SecurityAttributes.bInheritHandle], eax
0x180060e04  lea     ebx, [rsi+1]
0x180060e07  lea     eax, [rsi+44h]
0x180060e0a  xorps   xmm0, xmm0
0x180060e0d  lea     r9, [rsp+6B0h+cbSid]; cbSid
0x180060e12  mov     [rsp+6B0h+cbSid], eax
0x180060e16  lea     r8, [rbp+5B0h+pSid]; pSid
0x180060e1d  mov     [rsp+6B0h+var_654], eax
0x180060e21  xor     edx, edx; DomainSid
0x180060e23  mov     [rsp+6B0h+var_650], eax
0x180060e27  mov     ecx, ebx; WellKnownSidType
0x180060e29  movups  xmmword ptr [rsp+6B0h+SecurityAttributes.nLength], xmm0
0x180060e2e  call    cs:__imp_CreateWellKnownSid
0x180060e35  nop     dword ptr [rax+rax+00h]
0x180060e3a  test    eax, eax
0x180060e3c  jz      loc_18006134D
0x180060e42  xor     edx, edx; Val
0x180060e44  lea     rcx, [rbp+5B0h+pListOfExplicitEntries]; void *
0x180060e4b  mov     r8d, 90h; Size
0x180060e51  call    memset_0
0x180060e56  lea     rax, [rbp+5B0h+pSid]
0x180060e5d  mov     [rbp+5B0h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180060e67  lea     r9, [rsp+6B0h+var_654]; cbSid
0x180060e6c  mov     [rbp+5B0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180060e73  lea     r8, [rbp+5B0h+var_300]; pSid
0x180060e7a  mov     qword ptr [rbp+5B0h+pListOfExplicitEntries.grfAccessMode], rbx
0x180060e81  xor     edx, edx; DomainSid
0x180060e83  mov     [rbp+5B0h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180060e89  lea     ecx, [rsi+16h]; WellKnownSidType
0x180060e8c  mov     [rbp+5B0h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180060e96  call    cs:__imp_CreateWellKnownSid
0x180060e9d  nop     dword ptr [rax+rax+00h]
0x180060ea2  test    eax, eax
0x180060ea4  jz      loc_18006134D
0x180060eaa  lea     rax, [rbp+5B0h+var_300]
0x180060eb1  mov     [rbp+5B0h+var_3AC], rbx
0x180060eb8  mov     edi, 10000000h
0x180060ebd  mov     [rbp+5B0h+var_388], rax
0x180060ec4  lea     r9, [rsp+6B0h+var_650]; cbSid
0x180060ec9  mov     [rbp+5B0h+var_3B0], edi
0x180060ecf  lea     r8, [rbp+5B0h+var_2B0]; pSid
0x180060ed6  mov     [rbp+5B0h+var_394], esi
0x180060edc  xor     edx, edx; DomainSid
0x180060ede  mov     [rbp+5B0h+var_390], 2
0x180060ee8  lea     ecx, [rsi+1Ah]; WellKnownSidType
0x180060eeb  call    cs:__imp_CreateWellKnownSid
0x180060ef2  nop     dword ptr [rax+rax+00h]
0x180060ef7  test    eax, eax
0x180060ef9  jz      loc_18006134D
0x180060eff  lea     rax, [rbp+5B0h+var_2B0]
0x180060f06  mov     [rbp+5B0h+var_380], edi
0x180060f0c  lea     r9, [rsp+6B0h+NewAcl]; NewAcl
0x180060f11  mov     [rbp+5B0h+var_358], rax
0x180060f18  xor     r8d, r8d; OldAcl
0x180060f1b  mov     [rbp+5B0h+var_37C], rbx
0x180060f22  lea     rdx, [rbp+5B0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180060f29  mov     [rbp+5B0h+var_364], esi
0x180060f2f  lea     ecx, [rsi+3]; cCountOfExplicitEntries
0x180060f32  mov     [rbp+5B0h+var_360], 2
0x180060f3c  call    cs:__imp_SetEntriesInAclW
0x180060f43  nop     dword ptr [rax+rax+00h]
0x180060f48  test    eax, eax
0x180060f4a  jz      short loc_180060F56
0x180060f4c  mov     [rsp+6B0h+NewAcl], rsi
0x180060f51  jmp     loc_180061363
0x180060f56  mov     edx, 28h ; '('; uBytes
0x180060f5b  lea     ecx, [rdx+18h]; uFlags
0x180060f5e  call    cs:__imp_LocalAlloc
0x180060f65  nop     dword ptr [rax+rax+00h]
0x180060f6a  mov     r14, rax
0x180060f6d  test    rax, rax
0x180060f70  jz      loc_18006134D
0x180060f76  mov     edx, ebx; dwRevision
0x180060f78  mov     rcx, rax; pSecurityDescriptor
0x180060f7b  call    cs:__imp_InitializeSecurityDescriptor
0x180060f82  nop     dword ptr [rax+rax+00h]
0x180060f87  test    eax, eax
0x180060f89  jz      loc_18006133E
0x180060f8f  mov     r8, [rsp+6B0h+NewAcl]; pDacl
0x180060f94  xor     r9d, r9d; bDaclDefaulted
0x180060f97  mov     edx, ebx; bDaclPresent
0x180060f99  mov     rcx, r14; pSecurityDescriptor
0x180060f9c  call    cs:__imp_SetSecurityDescriptorDacl
0x180060fa3  nop     dword ptr [rax+rax+00h]
0x180060fa8  test    eax, eax
0x180060faa  jz      loc_18006133E
0x180060fb0  mov     r8d, 104h; nSize
0x180060fb6  mov     [rsp+6B0h+SecurityAttributes.nLength], 18h
0x180060fbe  lea     rdx, [rbp+5B0h+Dst]; lpDst
0x180060fc5  mov     [rsp+6B0h+SecurityAttributes.lpSecurityDescriptor], r14
0x180060fca  lea     rcx, aWindirTempIpht; "%windir%\\temp\\iphttps.txt"
0x180060fd1  mov     [rsp+6B0h+SecurityAttributes.bInheritHandle], esi
0x180060fd5  call    cs:__imp_ExpandEnvironmentStringsW
0x180060fdc  nop     dword ptr [rax+rax+00h]
0x180060fe1  dec     eax
0x180060fe3  cmp     eax, 103h
0x180060fe8  ja      loc_18006133E
0x180060fee  mov     [rsp+6B0h+hTemplateFile], rsi; hTemplateFile
0x180060ff3  lea     r9, [rsp+6B0h+SecurityAttributes]; lpSecurityAttributes
0x180060ff8  mov     r12d, 4
0x180060ffe  mov     [rsp+6B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180061006  mov     r8d, ebx; dwShareMode
0x180061009  mov     [rsp+6B0h+dwCreationDisposition], r12d; dwCreationDisposition
0x18006100e  mov     edx, 40000000h; dwDesiredAccess
0x180061013  lea     rcx, [rbp+5B0h+Dst]; lpFileName
0x18006101a  call    cs:__imp_CreateFileW
0x180061021  nop     dword ptr [rax+rax+00h]
0x180061026  mov     rdi, rax
0x180061029  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006102d  jz      loc_18006133E
0x180061033  call    cs:__imp_GetLastError
0x18006103a  nop     dword ptr [rax+rax+00h]
0x18006103f  cmp     eax, 0B7h
0x180061044  jnz     short loc_18006107F
0x180061046  lea     rdx, [rsp+6B0h+var_670]
0x18006104b  mov     rcx, rdi
0x18006104e  call    IsHardLinkFile
0x180061053  test    eax, eax
0x180061055  jnz     loc_18006132F
0x18006105b  cmp     [rsp+6B0h+var_670], sil
0x180061060  jz      short loc_18006107F
0x180061062  lea     r8, [rbp+5B0h+Dst]
0x180061069  mov     ecx, 800000h
0x18006106e  lea     rdx, aDetectedTarget; "Detected target hardlink file path %s"
0x180061075  call    EventWrite0
0x18006107a  jmp     loc_18006132F
0x18006107f  mov     rcx, cs:g_IpTlsInterfaceListLock
0x180061086  call    IpTlsAcquireLock
0x18006108b  mov     rcx, cs:g_IpTlsInterfaceListHead
0x180061092  test    rcx, rcx
0x180061095  jz      loc_18006131C
0x18006109b  lea     r15, g_IpTlsInterfaceListHead
0x1800610a2  cmp     rcx, r15
0x1800610a5  jz      short loc_1800610B9
0x1800610a7  mov     eax, [rsp+6B0h+Buffer]
0x1800610ab  mov     rcx, [rcx]
0x1800610ae  add     eax, ebx
0x1800610b0  mov     [rsp+6B0h+Buffer], eax
0x1800610b4  cmp     rcx, r15
0x1800610b7  jnz     short loc_1800610AB
0x1800610b9  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800610be  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rsi; lpOverlapped
0x1800610c3  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800610c6  lea     rdx, [rsp+6B0h+Buffer]; lpBuffer
0x1800610cb  mov     rcx, rdi; hFile
0x1800610ce  call    cs:__imp_WriteFile
0x1800610d5  nop     dword ptr [rax+rax+00h]
0x1800610da  test    eax, eax
0x1800610dc  jz      loc_18006131C
0x1800610e2  mov     rbx, cs:g_IpTlsInterfaceListHead
0x1800610e9  cmp     rbx, r15
0x1800610ec  jz      loc_1800612E9
0x1800610f2  mov     eax, [rbx+3F4h]
0x1800610f8  lea     rcx, [rbp+5B0h+var_610]
0x1800610fc  mov     r12, [rbx]
0x1800610ff  mov     edx, 2
0x180061104  mov     [rbp+5B0h+var_404], eax
0x18006110a  lea     rax, [rbx+38h]
0x18006110e  lea     r8d, [rdx+7Eh]
0x180061112  movups  xmm0, xmmword ptr [rax]
0x180061115  movups  xmmword ptr [rcx], xmm0
0x180061118  movups  xmm1, xmmword ptr [rax+10h]
0x18006111c  movups  xmmword ptr [rcx+10h], xmm1
0x180061120  movups  xmm0, xmmword ptr [rax+20h]
0x180061124  movups  xmmword ptr [rcx+20h], xmm0
0x180061128  movups  xmm1, xmmword ptr [rax+30h]
0x18006112c  movups  xmmword ptr [rcx+30h], xmm1
0x180061130  movups  xmm0, xmmword ptr [rax+40h]
0x180061134  movups  xmmword ptr [rcx+40h], xmm0
0x180061138  movups  xmm1, xmmword ptr [rax+50h]
0x18006113c  movups  xmmword ptr [rcx+50h], xmm1
0x180061140  movups  xmm0, xmmword ptr [rax+60h]
0x180061144  movups  xmmword ptr [rcx+60h], xmm0
0x180061148  movups  xmm1, xmmword ptr [rax+70h]
0x18006114c  add     rax, r8
0x18006114f  movups  xmmword ptr [rcx+70h], xmm1
0x180061153  add     rcx, r8
0x180061156  sub     rdx, 1
0x18006115a  jnz     short loc_180061112
0x18006115c  mov     rax, [rax-3]
0x180061160  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180061165  mov     [rcx-3], rax
0x180061169  lea     rdx, [rbp+5B0h+var_610]; lpBuffer
0x18006116d  movups  xmm0, xmmword ptr [rbx+410h]
0x180061174  mov     rax, cs:g_IpTlsGlobalStatsBytesIn
0x18006117b  mov     r8d, 230h; nNumberOfBytesToWrite
0x180061181  mov     [rbp+5B0h+var_3F0], rax
0x180061188  mov     rcx, rdi; hFile
0x18006118b  mov     rax, cs:g_IpTlsGlobalStatsBytesOut
0x180061192  mov     [rbp+5B0h+var_3E8], rax
0x180061199  movdqu  [rbp+5B0h+var_400], xmm0
0x1800611a1  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rsi; lpOverlapped
0x1800611a6  call    cs:__imp_WriteFile
0x1800611ad  nop     dword ptr [rax+rax+00h]
0x1800611b2  test    eax, eax
0x1800611b4  jz      loc_18006131C
0x1800611ba  cmp     [rbx+3F4h], esi
0x1800611c0  jz      loc_1800612E1
0x1800611c6  mov     rbx, [rbx+450h]
0x1800611cd  xorps   xmm0, xmm0
0x1800611d0  mov     [rsp+6B0h+var_664], esi
0x1800611d4  movups  [rbp+5B0h+var_630], xmm0
0x1800611d8  lea     r15, [rbx+0F0h]
0x1800611df  mov     rcx, r15; lpCriticalSection
0x1800611e2  movups  [rbp+5B0h+var_620], xmm0
0x1800611e6  call    cs:__imp_EnterCriticalSection
0x1800611ed  nop     dword ptr [rax+rax+00h]
0x1800611f2  lea     rsi, [rbx+0E0h]
0x1800611f9  mov     rdx, [rsi]
0x1800611fc  cmp     rdx, rsi
0x1800611ff  jz      short loc_18006121A
0x180061201  mov     eax, [rsp+6B0h+var_664]
0x180061205  cmp     qword ptr [rdx+10h], 0
0x18006120a  mov     rdx, [rdx]
0x18006120d  jz      short loc_180061215
0x18006120f  inc     eax
0x180061211  mov     [rsp+6B0h+var_664], eax
0x180061215  cmp     rdx, rsi
0x180061218  jnz     short loc_180061205
0x18006121a  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006121f  mov     qword ptr [rsp+6B0h+dwCreationDisposition], 0; lpOverlapped
0x180061228  mov     r8d, 4; nNumberOfBytesToWrite
0x18006122e  lea     rdx, [rsp+6B0h+var_664]; lpBuffer
0x180061233  mov     rcx, rdi; hFile
0x180061236  call    cs:__imp_WriteFile
0x18006123d  nop     dword ptr [rax+rax+00h]
0x180061242  test    eax, eax
0x180061244  jz      short loc_1800612B8
0x180061246  mov     rbx, [rsi]
0x180061249  cmp     rbx, rsi
0x18006124c  jz      short loc_1800612C9
0x18006124e  mov     rdx, rbx
0x180061251  mov     rbx, [rbx]
0x180061254  lea     rcx, [rdx+10h]
0x180061258  mov     rax, [rcx]
0x18006125b  test    rax, rax
0x18006125e  jz      short loc_180061249
0x180061260  cmp     rax, rcx
0x180061263  jnz     short loc_18006126E
0x180061265  xorps   xmm0, xmm0
0x180061268  movups  [rbp+5B0h+var_630], xmm0
0x18006126c  jmp     short loc_180061277
0x18006126e  movups  xmm0, xmmword ptr [rax-18h]
0x180061272  movdqu  [rbp+5B0h+var_630], xmm0
0x180061277  mov     rax, [rdx+190h]
0x18006127e  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180061283  mov     qword ptr [rbp+5B0h+var_620], rax
0x180061287  mov     r8d, 20h ; ' '; nNumberOfBytesToWrite
0x18006128d  mov     rax, [rdx+198h]
0x180061294  mov     rcx, rdi; hFile
0x180061297  lea     rdx, [rbp+5B0h+var_630]; lpBuffer
0x18006129b  mov     qword ptr [rbp+5B0h+var_620+8], rax
0x18006129f  mov     qword ptr [rsp+6B0h+dwCreationDisposition], 0; lpOverlapped
0x1800612a8  call    cs:__imp_WriteFile
0x1800612af  nop     dword ptr [rax+rax+00h]
0x1800612b4  test    eax, eax
0x1800612b6  jnz     short loc_180061249
0x1800612b8  mov     rcx, r15; lpCriticalSection
0x1800612bb  call    cs:__imp_LeaveCriticalSection
0x1800612c2  nop     dword ptr [rax+rax+00h]
0x1800612c7  jmp     short loc_18006131C
0x1800612c9  mov     rcx, r15; lpCriticalSection
0x1800612cc  call    cs:__imp_LeaveCriticalSection
0x1800612d3  nop     dword ptr [rax+rax+00h]
0x1800612d8  xor     esi, esi
0x1800612da  lea     r15, g_IpTlsInterfaceListHead
0x1800612e1  mov     rbx, r12
0x1800612e4  jmp     loc_1800610E9
0x1800612e9  mov     rcx, rdi; hFile
0x1800612ec  call    cs:__imp_SetEndOfFile
0x1800612f3  nop     dword ptr [rax+rax+00h]
0x1800612f8  test    eax, eax
0x1800612fa  jnz     short loc_18006131C
0x1800612fc  call    cs:__imp_GetLastError
  ... truncated ...
```
