# IpTlsQueryGlobals

- ea: `0x180060dc0`
- end: `0x1800613de`
- name: `IpTlsQueryGlobals`
- size: `1566`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180004f60`
- `0x18000d7c0`
- `0x180013580`
- `0x18004b5f0`
- `0x18004c188`
- `0x180053018`
- `0x180060dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061343`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061343`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061386`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061386`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800612ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006131c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006131c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061352`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061352`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061395`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180060f9b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180060f9b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180060fbc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180060fbc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060e4e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060eb6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060f0b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060e4e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060eb6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180060f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061361`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061361`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061377`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060f7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060f7e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180060ff5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180060ff5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006130c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006130c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800610ee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800611c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061256`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800612c8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800610ee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800611c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061256`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800612c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006103a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006103a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180060f5c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180060f5c`

## string_xrefs

- `0x1800613a7`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180060fea`: `%windir%\temp\iphttps.txt`
- `0x18006108e`: `Detected target hardlink file path %s`

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
0x180060dc0  push    rbp
0x180060dc2  push    rbx
0x180060dc3  push    rsi
0x180060dc4  push    rdi
0x180060dc5  push    r12
0x180060dc7  push    r13
0x180060dc9  push    r14
0x180060dcb  push    r15
0x180060dcd  lea     rbp, [rsp-578h]
0x180060dd5  sub     rsp, 678h
0x180060ddc  mov     rax, cs:__security_cookie
0x180060de3  xor     rax, rsp
0x180060de6  mov     [rbp+5B0h+var_50], rax
0x180060ded  xor     esi, esi
0x180060def  lea     rcx, [rbp+5B0h+var_610]; void *
0x180060df3  mov     r13, rdx
0x180060df6  mov     [rsp+6B0h+NumberOfBytesWritten], esi
0x180060dfa  xor     eax, eax
0x180060dfc  mov     [rsp+6B0h+NewAcl], rsi
0x180060e01  xor     edx, edx; Val
0x180060e03  mov     [rsp+6B0h+Buffer], esi
0x180060e07  mov     r8d, 22Eh; Size
0x180060e0d  mov     [rbp+5B0h+var_406], ax
0x180060e14  call    memset_0
0x180060e19  xor     eax, eax
0x180060e1b  mov     [rsp+6B0h+var_670], sil
0x180060e20  mov     [rsp+6B0h+SecurityAttributes.bInheritHandle], eax
0x180060e24  lea     ebx, [rsi+1]
0x180060e27  lea     eax, [rsi+44h]
0x180060e2a  xorps   xmm0, xmm0
0x180060e2d  lea     r9, [rsp+6B0h+cbSid]; cbSid
0x180060e32  mov     [rsp+6B0h+cbSid], eax
0x180060e36  lea     r8, [rbp+5B0h+pSid]; pSid
0x180060e3d  mov     [rsp+6B0h+var_654], eax
0x180060e41  xor     edx, edx; DomainSid
0x180060e43  mov     [rsp+6B0h+var_650], eax
0x180060e47  mov     ecx, ebx; WellKnownSidType
0x180060e49  movups  xmmword ptr [rsp+6B0h+SecurityAttributes.nLength], xmm0
0x180060e4e  call    cs:__imp_CreateWellKnownSid
0x180060e55  nop     dword ptr [rax+rax+00h]
0x180060e5a  test    eax, eax
0x180060e5c  jz      loc_18006136D
0x180060e62  xor     edx, edx; Val
0x180060e64  lea     rcx, [rbp+5B0h+pListOfExplicitEntries]; void *
0x180060e6b  mov     r8d, 90h; Size
0x180060e71  call    memset_0
0x180060e76  lea     rax, [rbp+5B0h+pSid]
0x180060e7d  mov     [rbp+5B0h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180060e87  lea     r9, [rsp+6B0h+var_654]; cbSid
0x180060e8c  mov     [rbp+5B0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180060e93  lea     r8, [rbp+5B0h+var_300]; pSid
0x180060e9a  mov     qword ptr [rbp+5B0h+pListOfExplicitEntries.grfAccessMode], rbx
0x180060ea1  xor     edx, edx; DomainSid
0x180060ea3  mov     [rbp+5B0h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180060ea9  lea     ecx, [rsi+16h]; WellKnownSidType
0x180060eac  mov     [rbp+5B0h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180060eb6  call    cs:__imp_CreateWellKnownSid
0x180060ebd  nop     dword ptr [rax+rax+00h]
0x180060ec2  test    eax, eax
0x180060ec4  jz      loc_18006136D
0x180060eca  lea     rax, [rbp+5B0h+var_300]
0x180060ed1  mov     [rbp+5B0h+var_3AC], rbx
0x180060ed8  mov     edi, 10000000h
0x180060edd  mov     [rbp+5B0h+var_388], rax
0x180060ee4  lea     r9, [rsp+6B0h+var_650]; cbSid
0x180060ee9  mov     [rbp+5B0h+var_3B0], edi
0x180060eef  lea     r8, [rbp+5B0h+var_2B0]; pSid
0x180060ef6  mov     [rbp+5B0h+var_394], esi
0x180060efc  xor     edx, edx; DomainSid
0x180060efe  mov     [rbp+5B0h+var_390], 2
0x180060f08  lea     ecx, [rsi+1Ah]; WellKnownSidType
0x180060f0b  call    cs:__imp_CreateWellKnownSid
0x180060f12  nop     dword ptr [rax+rax+00h]
0x180060f17  test    eax, eax
0x180060f19  jz      loc_18006136D
0x180060f1f  lea     rax, [rbp+5B0h+var_2B0]
0x180060f26  mov     [rbp+5B0h+var_380], edi
0x180060f2c  lea     r9, [rsp+6B0h+NewAcl]; NewAcl
0x180060f31  mov     [rbp+5B0h+var_358], rax
0x180060f38  xor     r8d, r8d; OldAcl
0x180060f3b  mov     [rbp+5B0h+var_37C], rbx
0x180060f42  lea     rdx, [rbp+5B0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180060f49  mov     [rbp+5B0h+var_364], esi
0x180060f4f  lea     ecx, [rsi+3]; cCountOfExplicitEntries
0x180060f52  mov     [rbp+5B0h+var_360], 2
0x180060f5c  call    cs:__imp_SetEntriesInAclW
0x180060f63  nop     dword ptr [rax+rax+00h]
0x180060f68  test    eax, eax
0x180060f6a  jz      short loc_180060F76
0x180060f6c  mov     [rsp+6B0h+NewAcl], rsi
0x180060f71  jmp     loc_180061383
0x180060f76  mov     edx, 28h ; '('; uBytes
0x180060f7b  lea     ecx, [rdx+18h]; uFlags
0x180060f7e  call    cs:__imp_LocalAlloc
0x180060f85  nop     dword ptr [rax+rax+00h]
0x180060f8a  mov     r14, rax
0x180060f8d  test    rax, rax
0x180060f90  jz      loc_18006136D
0x180060f96  mov     edx, ebx; dwRevision
0x180060f98  mov     rcx, rax; pSecurityDescriptor
0x180060f9b  call    cs:__imp_InitializeSecurityDescriptor
0x180060fa2  nop     dword ptr [rax+rax+00h]
0x180060fa7  test    eax, eax
0x180060fa9  jz      loc_18006135E
0x180060faf  mov     r8, [rsp+6B0h+NewAcl]; pDacl
0x180060fb4  xor     r9d, r9d; bDaclDefaulted
0x180060fb7  mov     edx, ebx; bDaclPresent
0x180060fb9  mov     rcx, r14; pSecurityDescriptor
0x180060fbc  call    cs:__imp_SetSecurityDescriptorDacl
0x180060fc3  nop     dword ptr [rax+rax+00h]
0x180060fc8  test    eax, eax
0x180060fca  jz      loc_18006135E
0x180060fd0  mov     r8d, 104h; nSize
0x180060fd6  mov     [rsp+6B0h+SecurityAttributes.nLength], 18h
0x180060fde  lea     rdx, [rbp+5B0h+Dst]; lpDst
0x180060fe5  mov     [rsp+6B0h+SecurityAttributes.lpSecurityDescriptor], r14
0x180060fea  lea     rcx, aWindirTempIpht; "%windir%\\temp\\iphttps.txt"
0x180060ff1  mov     [rsp+6B0h+SecurityAttributes.bInheritHandle], esi
0x180060ff5  call    cs:__imp_ExpandEnvironmentStringsW
0x180060ffc  nop     dword ptr [rax+rax+00h]
0x180061001  dec     eax
0x180061003  cmp     eax, 103h
0x180061008  ja      loc_18006135E
0x18006100e  mov     [rsp+6B0h+hTemplateFile], rsi; hTemplateFile
0x180061013  lea     r9, [rsp+6B0h+SecurityAttributes]; lpSecurityAttributes
0x180061018  mov     r12d, 4
0x18006101e  mov     [rsp+6B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180061026  mov     r8d, ebx; dwShareMode
0x180061029  mov     [rsp+6B0h+dwCreationDisposition], r12d; dwCreationDisposition
0x18006102e  mov     edx, 40000000h; dwDesiredAccess
0x180061033  lea     rcx, [rbp+5B0h+Dst]; lpFileName
0x18006103a  call    cs:__imp_CreateFileW
0x180061041  nop     dword ptr [rax+rax+00h]
0x180061046  mov     rdi, rax
0x180061049  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006104d  jz      loc_18006135E
0x180061053  call    cs:__imp_GetLastError
0x18006105a  nop     dword ptr [rax+rax+00h]
0x18006105f  cmp     eax, 0B7h
0x180061064  jnz     short loc_18006109F
0x180061066  lea     rdx, [rsp+6B0h+var_670]
0x18006106b  mov     rcx, rdi
0x18006106e  call    IsHardLinkFile
0x180061073  test    eax, eax
0x180061075  jnz     loc_18006134F
0x18006107b  cmp     [rsp+6B0h+var_670], sil
0x180061080  jz      short loc_18006109F
0x180061082  lea     r8, [rbp+5B0h+Dst]
0x180061089  mov     ecx, 800000h
0x18006108e  lea     rdx, aDetectedTarget; "Detected target hardlink file path %s"
0x180061095  call    EventWrite0
0x18006109a  jmp     loc_18006134F
0x18006109f  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800610a6  call    IpTlsAcquireLock
0x1800610ab  mov     rcx, cs:g_IpTlsInterfaceListHead
0x1800610b2  test    rcx, rcx
0x1800610b5  jz      loc_18006133C
0x1800610bb  lea     r15, g_IpTlsInterfaceListHead
0x1800610c2  cmp     rcx, r15
0x1800610c5  jz      short loc_1800610D9
0x1800610c7  mov     eax, [rsp+6B0h+Buffer]
0x1800610cb  mov     rcx, [rcx]
0x1800610ce  add     eax, ebx
0x1800610d0  mov     [rsp+6B0h+Buffer], eax
0x1800610d4  cmp     rcx, r15
0x1800610d7  jnz     short loc_1800610CB
0x1800610d9  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800610de  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rsi; lpOverlapped
0x1800610e3  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800610e6  lea     rdx, [rsp+6B0h+Buffer]; lpBuffer
0x1800610eb  mov     rcx, rdi; hFile
0x1800610ee  call    cs:__imp_WriteFile
0x1800610f5  nop     dword ptr [rax+rax+00h]
0x1800610fa  test    eax, eax
0x1800610fc  jz      loc_18006133C
0x180061102  mov     rbx, cs:g_IpTlsInterfaceListHead
0x180061109  cmp     rbx, r15
0x18006110c  jz      loc_180061309
0x180061112  mov     eax, [rbx+3F4h]
0x180061118  lea     rcx, [rbp+5B0h+var_610]
0x18006111c  mov     r12, [rbx]
0x18006111f  mov     edx, 2
0x180061124  mov     [rbp+5B0h+var_404], eax
0x18006112a  lea     rax, [rbx+38h]
0x18006112e  lea     r8d, [rdx+7Eh]
0x180061132  movups  xmm0, xmmword ptr [rax]
0x180061135  movups  xmmword ptr [rcx], xmm0
0x180061138  movups  xmm1, xmmword ptr [rax+10h]
0x18006113c  movups  xmmword ptr [rcx+10h], xmm1
0x180061140  movups  xmm0, xmmword ptr [rax+20h]
0x180061144  movups  xmmword ptr [rcx+20h], xmm0
0x180061148  movups  xmm1, xmmword ptr [rax+30h]
0x18006114c  movups  xmmword ptr [rcx+30h], xmm1
0x180061150  movups  xmm0, xmmword ptr [rax+40h]
0x180061154  movups  xmmword ptr [rcx+40h], xmm0
0x180061158  movups  xmm1, xmmword ptr [rax+50h]
0x18006115c  movups  xmmword ptr [rcx+50h], xmm1
0x180061160  movups  xmm0, xmmword ptr [rax+60h]
0x180061164  movups  xmmword ptr [rcx+60h], xmm0
0x180061168  movups  xmm1, xmmword ptr [rax+70h]
0x18006116c  add     rax, r8
0x18006116f  movups  xmmword ptr [rcx+70h], xmm1
0x180061173  add     rcx, r8
0x180061176  sub     rdx, 1
0x18006117a  jnz     short loc_180061132
0x18006117c  mov     rax, [rax-3]
0x180061180  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180061185  mov     [rcx-3], rax
0x180061189  lea     rdx, [rbp+5B0h+var_610]; lpBuffer
0x18006118d  movups  xmm0, xmmword ptr [rbx+410h]
0x180061194  mov     rax, cs:g_IpTlsGlobalStatsBytesIn
0x18006119b  mov     r8d, 230h; nNumberOfBytesToWrite
0x1800611a1  mov     [rbp+5B0h+var_3F0], rax
0x1800611a8  mov     rcx, rdi; hFile
0x1800611ab  mov     rax, cs:g_IpTlsGlobalStatsBytesOut
0x1800611b2  mov     [rbp+5B0h+var_3E8], rax
0x1800611b9  movdqu  [rbp+5B0h+var_400], xmm0
0x1800611c1  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rsi; lpOverlapped
0x1800611c6  call    cs:__imp_WriteFile
0x1800611cd  nop     dword ptr [rax+rax+00h]
0x1800611d2  test    eax, eax
0x1800611d4  jz      loc_18006133C
0x1800611da  cmp     [rbx+3F4h], esi
0x1800611e0  jz      loc_180061301
0x1800611e6  mov     rbx, [rbx+450h]
0x1800611ed  xorps   xmm0, xmm0
0x1800611f0  mov     [rsp+6B0h+var_664], esi
0x1800611f4  movups  [rbp+5B0h+var_630], xmm0
0x1800611f8  lea     r15, [rbx+0F0h]
0x1800611ff  mov     rcx, r15; lpCriticalSection
0x180061202  movups  [rbp+5B0h+var_620], xmm0
0x180061206  call    cs:__imp_EnterCriticalSection
0x18006120d  nop     dword ptr [rax+rax+00h]
0x180061212  lea     rsi, [rbx+0E0h]
0x180061219  mov     rdx, [rsi]
0x18006121c  cmp     rdx, rsi
0x18006121f  jz      short loc_18006123A
0x180061221  mov     eax, [rsp+6B0h+var_664]
0x180061225  cmp     qword ptr [rdx+10h], 0
0x18006122a  mov     rdx, [rdx]
0x18006122d  jz      short loc_180061235
0x18006122f  inc     eax
0x180061231  mov     [rsp+6B0h+var_664], eax
0x180061235  cmp     rdx, rsi
0x180061238  jnz     short loc_180061225
0x18006123a  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006123f  mov     qword ptr [rsp+6B0h+dwCreationDisposition], 0; lpOverlapped
0x180061248  mov     r8d, 4; nNumberOfBytesToWrite
0x18006124e  lea     rdx, [rsp+6B0h+var_664]; lpBuffer
0x180061253  mov     rcx, rdi; hFile
0x180061256  call    cs:__imp_WriteFile
0x18006125d  nop     dword ptr [rax+rax+00h]
0x180061262  test    eax, eax
0x180061264  jz      short loc_1800612D8
0x180061266  mov     rbx, [rsi]
0x180061269  cmp     rbx, rsi
0x18006126c  jz      short loc_1800612E9
0x18006126e  mov     rdx, rbx
0x180061271  mov     rbx, [rbx]
0x180061274  lea     rcx, [rdx+10h]
0x180061278  mov     rax, [rcx]
0x18006127b  test    rax, rax
0x18006127e  jz      short loc_180061269
0x180061280  cmp     rax, rcx
0x180061283  jnz     short loc_18006128E
0x180061285  xorps   xmm0, xmm0
0x180061288  movups  [rbp+5B0h+var_630], xmm0
0x18006128c  jmp     short loc_180061297
0x18006128e  movups  xmm0, xmmword ptr [rax-18h]
0x180061292  movdqu  [rbp+5B0h+var_630], xmm0
0x180061297  mov     rax, [rdx+190h]
0x18006129e  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800612a3  mov     qword ptr [rbp+5B0h+var_620], rax
0x1800612a7  mov     r8d, 20h ; ' '; nNumberOfBytesToWrite
0x1800612ad  mov     rax, [rdx+198h]
0x1800612b4  mov     rcx, rdi; hFile
0x1800612b7  lea     rdx, [rbp+5B0h+var_630]; lpBuffer
0x1800612bb  mov     qword ptr [rbp+5B0h+var_620+8], rax
0x1800612bf  mov     qword ptr [rsp+6B0h+dwCreationDisposition], 0; lpOverlapped
0x1800612c8  call    cs:__imp_WriteFile
0x1800612cf  nop     dword ptr [rax+rax+00h]
0x1800612d4  test    eax, eax
0x1800612d6  jnz     short loc_180061269
0x1800612d8  mov     rcx, r15; lpCriticalSection
0x1800612db  call    cs:__imp_LeaveCriticalSection
0x1800612e2  nop     dword ptr [rax+rax+00h]
0x1800612e7  jmp     short loc_18006133C
0x1800612e9  mov     rcx, r15; lpCriticalSection
0x1800612ec  call    cs:__imp_LeaveCriticalSection
0x1800612f3  nop     dword ptr [rax+rax+00h]
0x1800612f8  xor     esi, esi
0x1800612fa  lea     r15, g_IpTlsInterfaceListHead
0x180061301  mov     rbx, r12
0x180061304  jmp     loc_180061109
0x180061309  mov     rcx, rdi; hFile
0x18006130c  call    cs:__imp_SetEndOfFile
0x180061313  nop     dword ptr [rax+rax+00h]
0x180061318  test    eax, eax
0x18006131a  jnz     short loc_18006133C
0x18006131c  call    cs:__imp_GetLastError
  ... truncated ...
```
