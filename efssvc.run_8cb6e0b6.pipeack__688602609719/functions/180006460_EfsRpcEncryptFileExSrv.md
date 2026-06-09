# EfsRpcEncryptFileExSrv

- ea: `0x180006460`
- end: `0x18000699e`
- name: `EfsRpcEncryptFileExSrv`
- size: `1342`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800069b0`

## callees

- `0x1800036e0`
- `0x1800037b8`
- `0x180005d00`
- `0x180006460`
- `0x1800080c4`
- `0x18000bf0c`
- `0x18000d192`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006789`
- `msvcrt!_wcsicmp` at `0x180006789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006526`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006526`
- `RPCRT4!RpcRevertToSelf` at `0x180006561`
- `RPCRT4!RpcRevertToSelf` at `0x180006891`
- `RPCRT4!RpcRevertToSelf` at `0x180006561`
- `RPCRT4!RpcRevertToSelf` at `0x180006891`
- `RPCRT4!RpcImpersonateClient` at `0x1800066df`
- `RPCRT4!RpcImpersonateClient` at `0x180006824`
- `RPCRT4!RpcImpersonateClient` at `0x18000685b`
- `RPCRT4!RpcImpersonateClient` at `0x1800066df`
- `RPCRT4!RpcImpersonateClient` at `0x180006824`
- `RPCRT4!RpcImpersonateClient` at `0x18000685b`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006639`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006639`
- `ntdll!RtlFreeHeap` at `0x180006586`
- `ntdll!RtlFreeHeap` at `0x1800068da`
- `ntdll!RtlFreeHeap` at `0x180006586`
- `ntdll!RtlFreeHeap` at `0x1800068da`
- `ntdll!RtlInitUnicodeString` at `0x1800067dd`
- `ntdll!RtlInitUnicodeString` at `0x1800067f5`
- `ntdll!RtlInitUnicodeString` at `0x1800067dd`
- `ntdll!RtlInitUnicodeString` at `0x1800067f5`
- `ntdll!RtlNtStatusToDosError` at `0x1800068f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800068f0`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x180006848`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x180006848`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000653b`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000653b`
- `EFSCORE!EfsDllEncryptFileSrv` at `0x180006990`
- `EFSCORE!EfsDllEncryptFileSrv` at `0x180006990`
- `EFSCORE!EfsDllDisabled` at `0x180006612`
- `EFSCORE!EfsDllDisabled` at `0x180006612`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006550`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006550`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180006883`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180006883`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006937`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006937`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180006716`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180006716`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006963`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006963`
- `EFSCORE!EfsDllGetLogFile` at `0x1800068b8`
- `EFSCORE!EfsDllGetLogFile` at `0x1800068b8`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800064dd`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800064fd`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800064dd`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800064fd`

## pseudocode

```c
__int64 __fastcall EfsRpcEncryptFileExSrv(RPC_BINDING_HANDLE BindingHandle, __int64 a2, const wchar_t *a3)
{
  int v6; // r15d
  int v7; // r12d
  int v8; // r13d
  unsigned int VolumeRoot; // ebx
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  __int64 i; // rdi
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v16; // eax
  int v17; // ecx
  int v18; // r9d
  RPC_STATUS v19; // eax
  int v20; // ecx
  RPC_STATUS v21; // eax
  int v22; // ecx
  unsigned int v23; // r8d
  int v24; // ecx
  unsigned int v25; // eax
  int v26; // ecx
  NTSTATUS LogFile; // esi
  int v28; // ecx
  DWORD LastError; // eax
  char v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  void *v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+54h] [rbp-ACh]
  int v35; // [rsp+58h] [rbp-A8h]
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h] BYREF
  PVOID v38[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v40; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[176]; // [rsp+A0h] [rbp-60h] BYREF

  v34 = 0;
  hObject = 0;
  P = 0;
  DestinationString = 0;
  *(_OWORD *)v38 = 0;
  memset_0(v41, 0, 0x70u);
  ClientLocalFlag = 0;
  v40 = 0;
  v6 = 0;
  v35 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v32 = 0;
  if ( (unsigned __int8)EfsDllIsNonEfsSKU(L"feclient-EfsEnabled")
    && (!a3 || (unsigned __int8)EfsDllIsNonEfsSKU(L"feclient-EfsEnabledBasic")) )
  {
    VolumeRoot = 50;
    goto LABEL_5;
  }
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    VolumeRoot = 6015;
    goto LABEL_5;
  }
  if ( a3 && (I_RpcBindingIsClientLocal(BindingHandle, &ClientLocalFlag) || !ClientLocalFlag) )
  {
    VolumeRoot = 87;
    goto LABEL_5;
  }
  v16 = EfsEnforceClientAuthentication();
  VolumeRoot = v16;
  if ( v16 )
  {
    fnEfsLogTrace1(v17, (unsigned int)EFS_API_ERROR, v16, 6, 135);
    goto LABEL_5;
  }
  VolumeRoot = EfspEncryptFileCommonPrologue((_DWORD)BindingHandle, a2, (unsigned int)&P, v18);
  if ( VolumeRoot )
    goto LABEL_5;
  if ( !v34 )
  {
    if ( !a3 )
      goto LABEL_5;
    if ( !v35 )
    {
      v19 = RpcImpersonateClient(0);
      VolumeRoot = v19;
      if ( v19 )
      {
        fnEfsLogTrace1(v20, (unsigned int)EFS_API_ERROR, v19, 6, 177);
        goto LABEL_5;
      }
      v6 = 1;
      v21 = EfsDllQueryProtectorsSrv(P, &v31, &v32);
      VolumeRoot = v21;
      if ( v21 )
      {
        v30 = -71;
LABEL_42:
        v23 = v21;
LABEL_43:
        fnEfsLogTrace1(v22, (unsigned int)EFS_API_ERROR, v23, 6, v30);
        goto LABEL_5;
      }
      if ( !v31 )
      {
        VolumeRoot = 5;
        fnEfsLogTrace1(v22, (unsigned int)EFS_API_ERROR, 5, 6, 196);
        goto LABEL_5;
      }
      if ( v31 <= 1 )
      {
        if ( _wcsicmp(*(const wchar_t **)(*(_QWORD *)v32 + 16LL), a3) )
        {
          VolumeRoot = 5;
          fnEfsLogTrace1(v24, (unsigned int)EFS_API_ERROR, 5, 6, 212);
        }
        goto LABEL_5;
      }
      VolumeRoot = 13;
      v30 = -50;
LABEL_48:
      v23 = VolumeRoot;
      goto LABEL_43;
    }
    v25 = EfsRpcDecryptFileSrvInternal(BindingHandle, a2, 2);
    VolumeRoot = v25;
    if ( v25 )
    {
      fnEfsLogTrace1(v26, (unsigned int)EFS_API_ERROR, v25, 6, 231);
      goto LABEL_5;
    }
  }
  RtlInitUnicodeString(&DestinationString, (PCWSTR)P);
  if ( a3 )
    RtlInitUnicodeString(&v40, a3);
  v21 = RpcImpersonateClient(0);
  VolumeRoot = v21;
  if ( v21 )
  {
    v30 = 21;
    goto LABEL_42;
  }
  VolumeRoot = EfsDllGetVolumeRoot(&DestinationString, v38);
  RpcRevertToSelf();
  if ( VolumeRoot )
  {
    v30 = 29;
    goto LABEL_48;
  }
  LogFile = EfsDllGetLogFile(v38, &hObject);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v38[1]);
  if ( LogFile >= 0 )
  {
    VolumeRoot = RpcImpersonateClient(0);
    if ( VolumeRoot )
    {
      if ( !hObject )
        goto LABEL_13;
      EfsDllMarkFileForDelete();
    }
    else
    {
      v6 = 1;
      if ( (unsigned __int8)EfsDllGetUserInfo(v41) && (v7 = 1, (unsigned int)EfsDllLoadUserProfile(v41, 0)) )
      {
        v8 = 1;
        LastError = EfsDllEncryptFileSrv(v41, &DestinationString, (unsigned __int64)&v40 & -(__int64)(a3 != 0), hObject);
      }
      else
      {
        LastError = GetLastError();
      }
      VolumeRoot = LastError;
    }
  }
  else
  {
    VolumeRoot = RtlNtStatusToDosError(LogFile);
    if ( VolumeRoot == 317 )
    {
      fnEfsLogTrace1(v28, (unsigned int)EFS_API_ERROR, LogFile, 6, 44);
      VolumeRoot = 6000;
    }
  }
LABEL_5:
  if ( hObject )
    CloseHandle(hObject);
  if ( v8 )
    EfsDllUnloadUserProfile(v41);
  if ( v7 )
    EfsDllFreeUserInfo(v41);
  if ( v6 )
    RpcRevertToSelf();
LABEL_13:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  v10 = v32;
  if ( v32 )
  {
    v11 = v31;
    for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
    {
      v13 = v10[i];
      if ( v13 )
      {
        if ( *(_QWORD *)(v13 + 16) )
        {
          MIDL_user_free(*(void **)(v13 + 16));
          v10 = v32;
        }
        v14 = v10[i];
        if ( *(_QWORD *)(v14 + 8) )
        {
          MIDL_user_free(*(void **)(v14 + 8));
          v10 = v32;
        }
        MIDL_user_free((void *)v10[i]);
        v11 = v31;
        v10 = v32;
      }
    }
    MIDL_user_free(v10);
  }
  return VolumeRoot;
}

```

## disassembly

```asm
0x180006460  push    rbp
0x180006462  push    rbx
0x180006463  push    rsi
0x180006464  push    rdi
0x180006465  push    r12
0x180006467  push    r13
0x180006469  push    r14
0x18000646b  push    r15
0x18000646d  lea     rbp, [rsp-18h]
0x180006472  sub     rsp, 118h
0x180006479  xor     ebx, ebx
0x18000647b  mov     rdi, r8
0x18000647e  mov     r14, rdx
0x180006481  mov     [rsp+150h+var_FC], ebx
0x180006485  mov     rsi, rcx
0x180006488  mov     [rsp+150h+hObject], rbx
0x18000648d  xorps   xmm0, xmm0
0x180006490  mov     [rsp+150h+P], rbx
0x180006495  xorps   xmm1, xmm1
0x180006498  lea     r8d, [rbx+70h]; Size
0x18000649c  xor     edx, edx; Val
0x18000649e  lea     rcx, [rbp+50h+var_B0]; void *
0x1800064a2  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x1800064a6  movups  xmmword ptr [rsp+150h+var_E0], xmm1
0x1800064ab  call    memset_0
0x1800064b0  xorps   xmm0, xmm0
0x1800064b3  mov     [rsp+150h+var_110], bx
0x1800064b8  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x1800064bf  mov     [rsp+150h+ClientLocalFlag], ebx
0x1800064c3  movups  xmmword ptr [rbp+50h+var_C0.Length], xmm0
0x1800064c7  mov     r15d, ebx
0x1800064ca  mov     [rsp+150h+var_F8], ebx
0x1800064ce  mov     r12d, ebx
0x1800064d1  mov     [rsp+150h+var_10C], ebx
0x1800064d5  mov     r13d, ebx
0x1800064d8  mov     [rsp+150h+var_108], rbx
0x1800064dd  call    cs:__imp_EfsDllIsNonEfsSKU
0x1800064e4  nop     dword ptr [rax+rax+00h]
0x1800064e9  test    al, al
0x1800064eb  jz      loc_180006612
0x1800064f1  test    rdi, rdi
0x1800064f4  jz      short loc_180006511
0x1800064f6  lea     rcx, aFeclientEfsena; "feclient-EfsEnabledBasic"
0x1800064fd  call    cs:__imp_EfsDllIsNonEfsSKU
0x180006504  nop     dword ptr [rax+rax+00h]
0x180006509  test    al, al
0x18000650b  jz      loc_180006612
0x180006511  mov     ebx, 32h ; '2'
0x180006516  mov     r14d, 1
0x18000651c  mov     rcx, [rsp+150h+hObject]; hObject
0x180006521  test    rcx, rcx
0x180006524  jz      short loc_180006532
0x180006526  call    cs:__imp_CloseHandle
0x18000652d  nop     dword ptr [rax+rax+00h]
0x180006532  test    r13d, r13d
0x180006535  jz      short loc_180006547
0x180006537  lea     rcx, [rbp+50h+var_B0]
0x18000653b  call    cs:__imp_EfsDllUnloadUserProfile
0x180006542  nop     dword ptr [rax+rax+00h]
0x180006547  test    r12d, r12d
0x18000654a  jz      short loc_18000655C
0x18000654c  lea     rcx, [rbp+50h+var_B0]
0x180006550  call    cs:__imp_EfsDllFreeUserInfo
0x180006557  nop     dword ptr [rax+rax+00h]
0x18000655c  test    r15d, r15d
0x18000655f  jz      short loc_18000656D
0x180006561  call    cs:__imp_RpcRevertToSelf
0x180006568  nop     dword ptr [rax+rax+00h]
0x18000656d  mov     r8, [rsp+150h+P]; P
0x180006572  test    r8, r8
0x180006575  jz      short loc_180006592
0x180006577  mov     rcx, gs:60h
0x180006580  xor     edx, edx; Flags
0x180006582  mov     rcx, [rcx+30h]; HeapHandle
0x180006586  call    cs:__imp_RtlFreeHeap
0x18000658d  nop     dword ptr [rax+rax+00h]
0x180006592  mov     rcx, [rsp+150h+var_108]
0x180006597  test    rcx, rcx
0x18000659a  jz      short loc_1800065FB
0x18000659c  mov     eax, [rsp+150h+var_10C]
0x1800065a0  xor     edi, edi
0x1800065a2  test    eax, eax
0x1800065a4  jz      short loc_1800065F6
0x1800065a6  mov     rdx, [rcx+rdi*8]
0x1800065aa  test    rdx, rdx
0x1800065ad  jz      short loc_1800065EF
0x1800065af  cmp     qword ptr [rdx+10h], 0
0x1800065b4  jz      short loc_1800065C4
0x1800065b6  mov     rcx, [rdx+10h]; void *
0x1800065ba  call    MIDL_user_free
0x1800065bf  mov     rcx, [rsp+150h+var_108]
0x1800065c4  mov     rax, [rcx+rdi*8]
0x1800065c8  cmp     qword ptr [rax+8], 0
0x1800065cd  jz      short loc_1800065DD
0x1800065cf  mov     rcx, [rax+8]; void *
0x1800065d3  call    MIDL_user_free
0x1800065d8  mov     rcx, [rsp+150h+var_108]
0x1800065dd  mov     rcx, [rcx+rdi*8]; void *
0x1800065e1  call    MIDL_user_free
0x1800065e6  mov     eax, [rsp+150h+var_10C]
0x1800065ea  mov     rcx, [rsp+150h+var_108]; void *
0x1800065ef  add     edi, r14d
0x1800065f2  cmp     edi, eax
0x1800065f4  jb      short loc_1800065A6
0x1800065f6  call    MIDL_user_free
0x1800065fb  mov     eax, ebx
0x1800065fd  add     rsp, 118h
0x180006604  pop     r15
0x180006606  pop     r14
0x180006608  pop     r13
0x18000660a  pop     r12
0x18000660c  pop     rdi
0x18000660d  pop     rsi
0x18000660e  pop     rbx
0x18000660f  pop     rbp
0x180006610  retn
0x180006612  call    cs:__imp_EfsDllDisabled
0x180006619  nop     dword ptr [rax+rax+00h]
0x18000661e  test    al, al
0x180006620  jz      short loc_18000662C
0x180006622  mov     ebx, 177Fh
0x180006627  jmp     loc_180006516
0x18000662c  test    rdi, rdi
0x18000662f  jz      short loc_180006659
0x180006631  lea     rdx, [rsp+150h+ClientLocalFlag]; ClientLocalFlag
0x180006636  mov     rcx, rsi; BindingHandle
0x180006639  call    cs:__imp_I_RpcBindingIsClientLocal
0x180006640  nop     dword ptr [rax+rax+00h]
0x180006645  test    eax, eax
0x180006647  jnz     short loc_18000664F
0x180006649  cmp     [rsp+150h+ClientLocalFlag], ebx
0x18000664d  jnz     short loc_180006659
0x18000664f  mov     ebx, 57h ; 'W'
0x180006654  jmp     loc_180006516
0x180006659  call    EfsEnforceClientAuthentication
0x18000665e  mov     ebx, eax
0x180006660  test    eax, eax
0x180006662  jz      short loc_180006686
0x180006664  mov     dword ptr [rsp+150h+var_130], 287h
0x18000666c  mov     r9d, 6
0x180006672  lea     rdx, EFS_API_ERROR
0x180006679  mov     r8d, eax
0x18000667c  call    fnEfsLogTrace1
0x180006681  jmp     loc_180006516
0x180006686  lea     rax, [rsp+150h+var_F8]
0x18000668b  mov     rdx, r14
0x18000668e  mov     [rsp+150h+var_118], rax
0x180006693  lea     r8, [rsp+150h+P]
0x180006698  lea     rax, [rsp+150h+var_FC]
0x18000669d  mov     rcx, rsi
0x1800066a0  mov     [rsp+150h+var_120], rax
0x1800066a5  lea     rax, [rsp+150h+var_110]
0x1800066aa  mov     [rsp+150h+var_128], rax
0x1800066af  call    EfspEncryptFileCommonPrologue
0x1800066b4  mov     ebx, eax
0x1800066b6  test    eax, eax
0x1800066b8  jnz     loc_180006516
0x1800066be  cmp     [rsp+150h+var_FC], r12d
0x1800066c3  jnz     loc_1800067D4
0x1800066c9  test    rdi, rdi
0x1800066cc  jz      loc_180006516
0x1800066d2  cmp     [rsp+150h+var_F8], r12d
0x1800066d7  jnz     loc_1800067B0
0x1800066dd  xor     ecx, ecx; BindingHandle
0x1800066df  call    cs:__imp_RpcImpersonateClient
0x1800066e6  nop     dword ptr [rax+rax+00h]
0x1800066eb  mov     ebx, eax
0x1800066ed  test    eax, eax
0x1800066ef  jz      short loc_1800066FE
0x1800066f1  mov     dword ptr [rsp+150h+var_130], 2B1h
0x1800066f9  jmp     loc_18000666C
0x1800066fe  mov     rcx, [rsp+150h+P]
0x180006703  lea     r8, [rsp+150h+var_108]
0x180006708  mov     r14d, 1
0x18000670e  lea     rdx, [rsp+150h+var_10C]
0x180006713  mov     r15d, r14d
0x180006716  call    cs:__imp_EfsDllQueryProtectorsSrv
0x18000671d  nop     dword ptr [rax+rax+00h]
0x180006722  mov     ebx, eax
0x180006724  test    eax, eax
0x180006726  jz      short loc_18000674A
0x180006728  mov     dword ptr [rsp+150h+var_130], 2B9h
0x180006730  mov     r8d, eax
0x180006733  mov     r9d, 6
0x180006739  lea     rdx, EFS_API_ERROR
0x180006740  call    fnEfsLogTrace1
0x180006745  jmp     loc_18000651C
0x18000674a  mov     eax, [rsp+150h+var_10C]
0x18000674e  test    eax, eax
0x180006750  jnz     short loc_180006763
0x180006752  lea     r8d, [rax+5]
0x180006756  mov     dword ptr [rsp+150h+var_130], 2C4h
0x18000675e  mov     ebx, r8d
0x180006761  jmp     short loc_180006733
0x180006763  cmp     eax, r14d
0x180006766  jbe     short loc_18000677A
0x180006768  mov     ebx, 0Dh
0x18000676d  mov     dword ptr [rsp+150h+var_130], 2CEh
0x180006775  mov     r8d, ebx
0x180006778  jmp     short loc_180006733
0x18000677a  mov     rax, [rsp+150h+var_108]
0x18000677f  mov     rdx, rdi; String2
0x180006782  mov     rcx, [rax]
0x180006785  mov     rcx, [rcx+10h]; String1
0x180006789  call    cs:__imp__wcsicmp
0x180006790  nop     dword ptr [rax+rax+00h]
0x180006795  test    eax, eax
0x180006797  jz      loc_18000651C
0x18000679d  mov     r8d, 5
0x1800067a3  mov     dword ptr [rsp+150h+var_130], 2D4h
0x1800067ab  mov     ebx, r8d
0x1800067ae  jmp     short loc_180006733
0x1800067b0  mov     r8d, 2
0x1800067b6  mov     rdx, r14
0x1800067b9  mov     rcx, rsi
0x1800067bc  call    EfsRpcDecryptFileSrvInternal
0x1800067c1  mov     ebx, eax
0x1800067c3  test    eax, eax
0x1800067c5  jz      short loc_1800067D4
0x1800067c7  mov     dword ptr [rsp+150h+var_130], 2E7h
0x1800067cf  jmp     loc_18000666C
0x1800067d4  mov     rdx, [rsp+150h+P]; SourceString
0x1800067d9  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x1800067dd  call    cs:__imp_RtlInitUnicodeString
0x1800067e4  nop     dword ptr [rax+rax+00h]
0x1800067e9  test    rdi, rdi
0x1800067ec  jz      short loc_180006801
0x1800067ee  mov     rdx, rdi; SourceString
0x1800067f1  lea     rcx, [rbp+50h+var_C0]; DestinationString
0x1800067f5  call    cs:__imp_RtlInitUnicodeString
0x1800067fc  nop     dword ptr [rax+rax+00h]
0x180006801  mov     r14d, 1
0x180006807  cmp     [rsp+150h+var_110], r14w
0x18000680d  jnz     short loc_180006859
0x18000680f  test    rdi, rdi
0x180006812  jz      short loc_18000681D
0x180006814  lea     ebx, [r14+56h]
0x180006818  jmp     loc_18000651C
0x18000681d  mov     [rsp+150h+hObject], r12
0x180006822  xor     ecx, ecx; BindingHandle
0x180006824  call    cs:__imp_RpcImpersonateClient
0x18000682b  nop     dword ptr [rax+rax+00h]
0x180006830  mov     ebx, eax
0x180006832  test    eax, eax
0x180006834  jz      loc_180006930
0x18000683a  mov     rcx, [rsp+150h+hObject]
0x18000683f  test    rcx, rcx
0x180006842  jz      loc_18000656D
0x180006848  call    cs:__imp_EfsDllMarkFileForDelete
0x18000684f  nop     dword ptr [rax+rax+00h]
0x180006854  jmp     loc_18000651C
0x180006859  xor     ecx, ecx; BindingHandle
0x18000685b  call    cs:__imp_RpcImpersonateClient
0x180006862  nop     dword ptr [rax+rax+00h]
0x180006867  mov     ebx, eax
0x180006869  test    eax, eax
0x18000686b  jz      short loc_18000687A
0x18000686d  mov     dword ptr [rsp+150h+var_130], 315h
0x180006875  jmp     loc_180006730
0x18000687a  lea     rdx, [rsp+150h+var_E0]
0x18000687f  lea     rcx, [rbp+50h+DestinationString]
0x180006883  call    cs:__imp_EfsDllGetVolumeRoot
0x18000688a  nop     dword ptr [rax+rax+00h]
0x18000688f  mov     ebx, eax
0x180006891  call    cs:__imp_RpcRevertToSelf
0x180006898  nop     dword ptr [rax+rax+00h]
0x18000689d  test    ebx, ebx
0x18000689f  jz      short loc_1800068AE
0x1800068a1  mov     dword ptr [rsp+150h+var_130], 31Dh
0x1800068a9  jmp     loc_180006775
0x1800068ae  lea     rdx, [rsp+150h+hObject]
0x1800068b3  lea     rcx, [rsp+150h+var_E0]
0x1800068b8  call    cs:__imp_EfsDllGetLogFile
0x1800068bf  nop     dword ptr [rax+rax+00h]
0x1800068c4  mov     rcx, gs:60h
0x1800068cd  xor     edx, edx; Flags
0x1800068cf  mov     r8, [rsp+150h+var_E0+8]; P
0x1800068d4  mov     esi, eax
0x1800068d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800068da  call    cs:__imp_RtlFreeHeap
0x1800068e1  nop     dword ptr [rax+rax+00h]
0x1800068e6  test    esi, esi
0x1800068e8  jns     loc_180006822
0x1800068ee  mov     ecx, esi; Status
0x1800068f0  call    cs:__imp_RtlNtStatusToDosError
0x1800068f7  nop     dword ptr [rax+rax+00h]
0x1800068fc  mov     ebx, eax
0x1800068fe  cmp     eax, 13Dh
0x180006903  jnz     loc_18000651C
0x180006909  mov     r9d, 6
0x18000690f  mov     dword ptr [rsp+150h+var_130], 32Ch
0x180006917  mov     r8d, esi
0x18000691a  lea     rdx, EFS_API_ERROR
0x180006921  call    fnEfsLogTrace1
0x180006926  mov     ebx, 1770h
0x18000692b  jmp     loc_18000651C
0x180006930  lea     rcx, [rbp+50h+var_B0]
0x180006934  mov     r15d, r14d
0x180006937  call    cs:__imp_EfsDllGetUserInfo
0x18000693e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
