# EfsRpcEncryptFileExSrv

- ea: `0x180005ef0`
- end: `0x180006391`
- name: `EfsRpcEncryptFileExSrv`
- size: `1185`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800063a0`

## callees

- `0x180003540`
- `0x180003604`
- `0x1800058a0`
- `0x180005ef0`
- `0x180007810`
- `0x18000b308`
- `0x18000c392`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800061d6`
- `msvcrt!_wcsicmp` at `0x1800061d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000634c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000634c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005faa`
- `RPCRT4!RpcRevertToSelf` at `0x180005fd3`
- `RPCRT4!RpcRevertToSelf` at `0x1800062b4`
- `RPCRT4!RpcRevertToSelf` at `0x180005fd3`
- `RPCRT4!RpcRevertToSelf` at `0x1800062b4`
- `RPCRT4!RpcImpersonateClient` at `0x180006138`
- `RPCRT4!RpcImpersonateClient` at `0x18000625f`
- `RPCRT4!RpcImpersonateClient` at `0x18000628a`
- `RPCRT4!RpcImpersonateClient` at `0x180006138`
- `RPCRT4!RpcImpersonateClient` at `0x18000625f`
- `RPCRT4!RpcImpersonateClient` at `0x18000628a`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006098`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006098`
- `ntdll!RtlFreeHeap` at `0x180005ff2`
- `ntdll!RtlFreeHeap` at `0x1800062f1`
- `ntdll!RtlFreeHeap` at `0x180005ff2`
- `ntdll!RtlFreeHeap` at `0x1800062f1`
- `ntdll!RtlInitUnicodeString` at `0x180006224`
- `ntdll!RtlInitUnicodeString` at `0x180006236`
- `ntdll!RtlInitUnicodeString` at `0x180006224`
- `ntdll!RtlInitUnicodeString` at `0x180006236`
- `ntdll!RtlNtStatusToDosError` at `0x180006301`
- `ntdll!RtlNtStatusToDosError` at `0x180006301`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x18000627d`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x18000627d`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005fb9`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005fb9`
- `EFSCORE!EfsDllEncryptFileSrv` at `0x180006389`
- `EFSCORE!EfsDllEncryptFileSrv` at `0x180006389`
- `EFSCORE!EfsDllDisabled` at `0x180006077`
- `EFSCORE!EfsDllDisabled` at `0x180006077`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005fc8`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005fc8`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x1800062ac`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x1800062ac`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006342`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006342`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180006169`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180006169`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006362`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006362`
- `EFSCORE!EfsDllGetLogFile` at `0x1800062d5`
- `EFSCORE!EfsDllGetLogFile` at `0x1800062d5`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180005f6d`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180005f87`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180005f6d`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180005f87`

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
0x180005ef0  push    rbp
0x180005ef2  push    rbx
0x180005ef3  push    rsi
0x180005ef4  push    rdi
0x180005ef5  push    r12
0x180005ef7  push    r13
0x180005ef9  push    r14
0x180005efb  push    r15
0x180005efd  lea     rbp, [rsp-18h]
0x180005f02  sub     rsp, 118h
0x180005f09  xor     ebx, ebx
0x180005f0b  mov     rdi, r8
0x180005f0e  mov     r14, rdx
0x180005f11  mov     [rsp+150h+var_FC], ebx
0x180005f15  mov     rsi, rcx
0x180005f18  mov     [rsp+150h+hObject], rbx
0x180005f1d  xorps   xmm0, xmm0
0x180005f20  mov     [rsp+150h+P], rbx
0x180005f25  xorps   xmm1, xmm1
0x180005f28  lea     r8d, [rbx+70h]; Size
0x180005f2c  xor     edx, edx; Val
0x180005f2e  lea     rcx, [rbp+50h+var_B0]; void *
0x180005f32  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x180005f36  movups  xmmword ptr [rsp+150h+var_E0], xmm1
0x180005f3b  call    memset_0
0x180005f40  xorps   xmm0, xmm0
0x180005f43  mov     [rsp+150h+var_110], bx
0x180005f48  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x180005f4f  mov     [rsp+150h+ClientLocalFlag], ebx
0x180005f53  movups  xmmword ptr [rbp+50h+var_C0.Length], xmm0
0x180005f57  mov     r15d, ebx
0x180005f5a  mov     [rsp+150h+var_F8], ebx
0x180005f5e  mov     r12d, ebx
0x180005f61  mov     [rsp+150h+var_10C], ebx
0x180005f65  mov     r13d, ebx
0x180005f68  mov     [rsp+150h+var_108], rbx
0x180005f6d  call    cs:__imp_EfsDllIsNonEfsSKU
0x180005f73  test    al, al
0x180005f75  jz      loc_180006077
0x180005f7b  test    rdi, rdi
0x180005f7e  jz      short loc_180005F95
0x180005f80  lea     rcx, aFeclientEfsena; "feclient-EfsEnabledBasic"
0x180005f87  call    cs:__imp_EfsDllIsNonEfsSKU
0x180005f8d  test    al, al
0x180005f8f  jz      loc_180006077
0x180005f95  mov     ebx, 32h ; '2'
0x180005f9a  mov     r14d, 1
0x180005fa0  mov     rcx, [rsp+150h+hObject]; hObject
0x180005fa5  test    rcx, rcx
0x180005fa8  jz      short loc_180005FB0
0x180005faa  call    cs:__imp_CloseHandle
0x180005fb0  test    r13d, r13d
0x180005fb3  jz      short loc_180005FBF
0x180005fb5  lea     rcx, [rbp+50h+var_B0]
0x180005fb9  call    cs:__imp_EfsDllUnloadUserProfile
0x180005fbf  test    r12d, r12d
0x180005fc2  jz      short loc_180005FCE
0x180005fc4  lea     rcx, [rbp+50h+var_B0]
0x180005fc8  call    cs:__imp_EfsDllFreeUserInfo
0x180005fce  test    r15d, r15d
0x180005fd1  jz      short loc_180005FD9
0x180005fd3  call    cs:__imp_RpcRevertToSelf
0x180005fd9  mov     r8, [rsp+150h+P]; P
0x180005fde  test    r8, r8
0x180005fe1  jz      short loc_180005FF8
0x180005fe3  mov     rcx, gs:60h
0x180005fec  xor     edx, edx; Flags
0x180005fee  mov     rcx, [rcx+30h]; HeapHandle
0x180005ff2  call    cs:__imp_RtlFreeHeap
0x180005ff8  mov     rcx, [rsp+150h+var_108]
0x180005ffd  test    rcx, rcx
0x180006000  jz      short loc_180006061
0x180006002  mov     eax, [rsp+150h+var_10C]
0x180006006  xor     edi, edi
0x180006008  test    eax, eax
0x18000600a  jz      short loc_18000605C
0x18000600c  mov     rdx, [rcx+rdi*8]
0x180006010  test    rdx, rdx
0x180006013  jz      short loc_180006055
0x180006015  cmp     qword ptr [rdx+10h], 0
0x18000601a  jz      short loc_18000602A
0x18000601c  mov     rcx, [rdx+10h]; void *
0x180006020  call    MIDL_user_free
0x180006025  mov     rcx, [rsp+150h+var_108]
0x18000602a  mov     rax, [rcx+rdi*8]
0x18000602e  cmp     qword ptr [rax+8], 0
0x180006033  jz      short loc_180006043
0x180006035  mov     rcx, [rax+8]; void *
0x180006039  call    MIDL_user_free
0x18000603e  mov     rcx, [rsp+150h+var_108]
0x180006043  mov     rcx, [rcx+rdi*8]; void *
0x180006047  call    MIDL_user_free
0x18000604c  mov     eax, [rsp+150h+var_10C]
0x180006050  mov     rcx, [rsp+150h+var_108]; void *
0x180006055  add     edi, r14d
0x180006058  cmp     edi, eax
0x18000605a  jb      short loc_18000600C
0x18000605c  call    MIDL_user_free
0x180006061  mov     eax, ebx
0x180006063  add     rsp, 118h
0x18000606a  pop     r15
0x18000606c  pop     r14
0x18000606e  pop     r13
0x180006070  pop     r12
0x180006072  pop     rdi
0x180006073  pop     rsi
0x180006074  pop     rbx
0x180006075  pop     rbp
0x180006076  retn
0x180006077  call    cs:__imp_EfsDllDisabled
0x18000607d  test    al, al
0x18000607f  jz      short loc_18000608B
0x180006081  mov     ebx, 177Fh
0x180006086  jmp     loc_180005F9A
0x18000608b  test    rdi, rdi
0x18000608e  jz      short loc_1800060B2
0x180006090  lea     rdx, [rsp+150h+ClientLocalFlag]; ClientLocalFlag
0x180006095  mov     rcx, rsi; BindingHandle
0x180006098  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000609e  test    eax, eax
0x1800060a0  jnz     short loc_1800060A8
0x1800060a2  cmp     [rsp+150h+ClientLocalFlag], ebx
0x1800060a6  jnz     short loc_1800060B2
0x1800060a8  mov     ebx, 57h ; 'W'
0x1800060ad  jmp     loc_180005F9A
0x1800060b2  call    EfsEnforceClientAuthentication
0x1800060b7  mov     ebx, eax
0x1800060b9  test    eax, eax
0x1800060bb  jz      short loc_1800060DF
0x1800060bd  mov     dword ptr [rsp+150h+var_130], 287h
0x1800060c5  mov     r9d, 6
0x1800060cb  lea     rdx, EFS_API_ERROR
0x1800060d2  mov     r8d, eax
0x1800060d5  call    fnEfsLogTrace1
0x1800060da  jmp     loc_180005F9A
0x1800060df  lea     rax, [rsp+150h+var_F8]
0x1800060e4  mov     rdx, r14
0x1800060e7  mov     [rsp+150h+var_118], rax
0x1800060ec  lea     r8, [rsp+150h+P]
0x1800060f1  lea     rax, [rsp+150h+var_FC]
0x1800060f6  mov     rcx, rsi
0x1800060f9  mov     [rsp+150h+var_120], rax
0x1800060fe  lea     rax, [rsp+150h+var_110]
0x180006103  mov     [rsp+150h+var_128], rax
0x180006108  call    EfspEncryptFileCommonPrologue
0x18000610d  mov     ebx, eax
0x18000610f  test    eax, eax
0x180006111  jnz     loc_180005F9A
0x180006117  cmp     [rsp+150h+var_FC], r12d
0x18000611c  jnz     loc_18000621B
0x180006122  test    rdi, rdi
0x180006125  jz      loc_180005F9A
0x18000612b  cmp     [rsp+150h+var_F8], r12d
0x180006130  jnz     loc_1800061F7
0x180006136  xor     ecx, ecx; BindingHandle
0x180006138  call    cs:__imp_RpcImpersonateClient
0x18000613e  mov     ebx, eax
0x180006140  test    eax, eax
0x180006142  jz      short loc_180006151
0x180006144  mov     dword ptr [rsp+150h+var_130], 2B1h
0x18000614c  jmp     loc_1800060C5
0x180006151  mov     rcx, [rsp+150h+P]
0x180006156  lea     r8, [rsp+150h+var_108]
0x18000615b  mov     r14d, 1
0x180006161  lea     rdx, [rsp+150h+var_10C]
0x180006166  mov     r15d, r14d
0x180006169  call    cs:__imp_EfsDllQueryProtectorsSrv
0x18000616f  mov     ebx, eax
0x180006171  test    eax, eax
0x180006173  jz      short loc_180006197
0x180006175  mov     dword ptr [rsp+150h+var_130], 2B9h
0x18000617d  mov     r8d, eax
0x180006180  mov     r9d, 6
0x180006186  lea     rdx, EFS_API_ERROR
0x18000618d  call    fnEfsLogTrace1
0x180006192  jmp     loc_180005FA0
0x180006197  mov     eax, [rsp+150h+var_10C]
0x18000619b  test    eax, eax
0x18000619d  jnz     short loc_1800061B0
0x18000619f  lea     r8d, [rax+5]
0x1800061a3  mov     dword ptr [rsp+150h+var_130], 2C4h
0x1800061ab  mov     ebx, r8d
0x1800061ae  jmp     short loc_180006180
0x1800061b0  cmp     eax, r14d
0x1800061b3  jbe     short loc_1800061C7
0x1800061b5  mov     ebx, 0Dh
0x1800061ba  mov     dword ptr [rsp+150h+var_130], 2CEh
0x1800061c2  mov     r8d, ebx
0x1800061c5  jmp     short loc_180006180
0x1800061c7  mov     rax, [rsp+150h+var_108]
0x1800061cc  mov     rdx, rdi; String2
0x1800061cf  mov     rcx, [rax]
0x1800061d2  mov     rcx, [rcx+10h]; String1
0x1800061d6  call    cs:__imp__wcsicmp
0x1800061dc  test    eax, eax
0x1800061de  jz      loc_180005FA0
0x1800061e4  mov     r8d, 5
0x1800061ea  mov     dword ptr [rsp+150h+var_130], 2D4h
0x1800061f2  mov     ebx, r8d
0x1800061f5  jmp     short loc_180006180
0x1800061f7  mov     r8d, 2
0x1800061fd  mov     rdx, r14
0x180006200  mov     rcx, rsi
0x180006203  call    EfsRpcDecryptFileSrvInternal
0x180006208  mov     ebx, eax
0x18000620a  test    eax, eax
0x18000620c  jz      short loc_18000621B
0x18000620e  mov     dword ptr [rsp+150h+var_130], 2E7h
0x180006216  jmp     loc_1800060C5
0x18000621b  mov     rdx, [rsp+150h+P]; SourceString
0x180006220  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x180006224  call    cs:__imp_RtlInitUnicodeString
0x18000622a  test    rdi, rdi
0x18000622d  jz      short loc_18000623C
0x18000622f  mov     rdx, rdi; SourceString
0x180006232  lea     rcx, [rbp+50h+var_C0]; DestinationString
0x180006236  call    cs:__imp_RtlInitUnicodeString
0x18000623c  mov     r14d, 1
0x180006242  cmp     [rsp+150h+var_110], r14w
0x180006248  jnz     short loc_180006288
0x18000624a  test    rdi, rdi
0x18000624d  jz      short loc_180006258
0x18000624f  lea     ebx, [r14+56h]
0x180006253  jmp     loc_180005FA0
0x180006258  mov     [rsp+150h+hObject], r12
0x18000625d  xor     ecx, ecx; BindingHandle
0x18000625f  call    cs:__imp_RpcImpersonateClient
0x180006265  mov     ebx, eax
0x180006267  test    eax, eax
0x180006269  jz      loc_18000633B
0x18000626f  mov     rcx, [rsp+150h+hObject]
0x180006274  test    rcx, rcx
0x180006277  jz      loc_180005FD9
0x18000627d  call    cs:__imp_EfsDllMarkFileForDelete
0x180006283  jmp     loc_180005FA0
0x180006288  xor     ecx, ecx; BindingHandle
0x18000628a  call    cs:__imp_RpcImpersonateClient
0x180006290  mov     ebx, eax
0x180006292  test    eax, eax
0x180006294  jz      short loc_1800062A3
0x180006296  mov     dword ptr [rsp+150h+var_130], 315h
0x18000629e  jmp     loc_18000617D
0x1800062a3  lea     rdx, [rsp+150h+var_E0]
0x1800062a8  lea     rcx, [rbp+50h+DestinationString]
0x1800062ac  call    cs:__imp_EfsDllGetVolumeRoot
0x1800062b2  mov     ebx, eax
0x1800062b4  call    cs:__imp_RpcRevertToSelf
0x1800062ba  test    ebx, ebx
0x1800062bc  jz      short loc_1800062CB
0x1800062be  mov     dword ptr [rsp+150h+var_130], 31Dh
0x1800062c6  jmp     loc_1800061C2
0x1800062cb  lea     rdx, [rsp+150h+hObject]
0x1800062d0  lea     rcx, [rsp+150h+var_E0]
0x1800062d5  call    cs:__imp_EfsDllGetLogFile
0x1800062db  mov     rcx, gs:60h
0x1800062e4  xor     edx, edx; Flags
0x1800062e6  mov     r8, [rsp+150h+var_E0+8]; P
0x1800062eb  mov     esi, eax
0x1800062ed  mov     rcx, [rcx+30h]; HeapHandle
0x1800062f1  call    cs:__imp_RtlFreeHeap
0x1800062f7  test    esi, esi
0x1800062f9  jns     loc_18000625D
0x1800062ff  mov     ecx, esi; Status
0x180006301  call    cs:__imp_RtlNtStatusToDosError
0x180006307  mov     ebx, eax
0x180006309  cmp     eax, 13Dh
0x18000630e  jnz     loc_180005FA0
0x180006314  mov     r9d, 6
0x18000631a  mov     dword ptr [rsp+150h+var_130], 32Ch
0x180006322  mov     r8d, esi
0x180006325  lea     rdx, EFS_API_ERROR
0x18000632c  call    fnEfsLogTrace1
0x180006331  mov     ebx, 1770h
0x180006336  jmp     loc_180005FA0
0x18000633b  lea     rcx, [rbp+50h+var_B0]
0x18000633f  mov     r15d, r14d
0x180006342  call    cs:__imp_EfsDllGetUserInfo
0x180006348  test    al, al
0x18000634a  jnz     short loc_180006359
0x18000634c  call    cs:__imp_GetLastError
0x180006352  mov     ebx, eax
0x180006354  jmp     loc_180005FA0
0x180006359  xor     edx, edx
0x18000635b  lea     rcx, [rbp+50h+var_B0]
0x18000635f  mov     r12d, r14d
0x180006362  call    cs:__imp_EfsDllLoadUserProfile
0x180006368  test    eax, eax
0x18000636a  jz      short loc_18000634C
0x18000636c  mov     r9, [rsp+150h+hObject]
0x180006371  lea     rax, [rbp+50h+var_C0]
0x180006375  neg     rdi
0x180006378  lea     rdx, [rbp+50h+DestinationString]
0x18000637c  lea     rcx, [rbp+50h+var_B0]
0x180006380  mov     r13d, r14d
0x180006383  sbb     r8, r8
0x180006386  and     r8, rax
0x180006389  call    cs:__imp_EfsDllEncryptFileSrv
0x18000638f  jmp     short loc_180006352
```
