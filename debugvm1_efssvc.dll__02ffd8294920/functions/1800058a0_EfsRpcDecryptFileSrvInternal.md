# EfsRpcDecryptFileSrvInternal

- ea: `0x1800058a0`
- end: `0x180005bb6`
- name: `EfsRpcDecryptFileSrvInternal`
- size: `790`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180005890`
- `0x180005ef0`

## callees

- `0x180003604`
- `0x1800058a0`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`
- `0x18000b480`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b8f`
- `RPCRT4!RpcRevertToSelf` at `0x180005a5f`
- `RPCRT4!RpcRevertToSelf` at `0x180005a9f`
- `RPCRT4!RpcRevertToSelf` at `0x180005b80`
- `RPCRT4!RpcRevertToSelf` at `0x180005a5f`
- `RPCRT4!RpcRevertToSelf` at `0x180005a9f`
- `RPCRT4!RpcRevertToSelf` at `0x180005b80`
- `RPCRT4!RpcImpersonateClient` at `0x18000596a`
- `RPCRT4!RpcImpersonateClient` at `0x180005a67`
- `RPCRT4!RpcImpersonateClient` at `0x18000596a`
- `RPCRT4!RpcImpersonateClient` at `0x180005a67`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005a15`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005a15`
- `ntdll!RtlFreeHeap` at `0x180005adc`
- `ntdll!RtlFreeHeap` at `0x180005adc`
- `ntdll!RtlInitUnicodeString` at `0x180005a4a`
- `ntdll!RtlInitUnicodeString` at `0x180005a4a`
- `ntdll!RtlNtStatusToDosError` at `0x180005aec`
- `ntdll!RtlNtStatusToDosError` at `0x180005aec`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x180005a84`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x180005a84`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x180005b64`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x180005b64`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005b70`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005b70`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005952`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005952`
- `EFSCORE!EfsDllDisabled` at `0x180005904`
- `EFSCORE!EfsDllDisabled` at `0x180005904`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005b7a`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005b7a`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005a97`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005a97`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005b27`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005b27`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180005b41`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180005b41`
- `EFSCORE!EfsDllShareDecline` at `0x1800059f5`
- `EFSCORE!EfsDllShareDecline` at `0x1800059f5`
- `EFSCORE!EfsDllFreeHeap` at `0x180005b9e`
- `EFSCORE!EfsDllFreeHeap` at `0x180005b9e`
- `EFSCORE!EfsDllGetLogFile` at `0x180005ac1`
- `EFSCORE!EfsDllGetLogFile` at `0x180005ac1`

## pseudocode

```c
__int64 __fastcall EfsRpcDecryptFileSrvInternal(__int64 a1, __int64 a2, unsigned int a3)
{
  DWORD LastError; // ebx
  RPC_STATUS LocalFileName; // eax
  int v8; // ecx
  DWORD v9; // eax
  int v10; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v12; // ecx
  int v13; // ecx
  DWORD FileAttributesW; // eax
  int v15; // ecx
  int v16; // ecx
  NTSTATUS LogFile; // edi
  int v18; // ecx
  char v20; // [rsp+20h] [rbp-89h]
  HANDLE hObject; // [rsp+30h] [rbp-79h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-71h] BYREF
  PVOID P[2]; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v25[160]; // [rsp+60h] [rbp-49h] BYREF
  __int16 v26; // [rsp+128h] [rbp+7Fh] BYREF

  hObject = 0;
  lpFileName = 0;
  v26 = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  memset_0(v25, 0, 0x70u);
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_44;
  }
  LocalFileName = EfsEnforceClientAuthentication();
  LastError = LocalFileName;
  if ( LocalFileName )
  {
    v20 = -76;
LABEL_7:
    fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, LocalFileName, 6, v20);
LABEL_44:
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_46;
  }
  LocalFileName = EfsDllGetLocalFileName(a2, 0, &lpFileName, &v26);
  LastError = LocalFileName;
  if ( LocalFileName )
  {
    v20 = -71;
    goto LABEL_7;
  }
  LocalFileName = RpcImpersonateClient(0);
  LastError = LocalFileName;
  if ( LocalFileName )
  {
    v20 = -66;
    goto LABEL_7;
  }
  v9 = EfsEnsureLocalPath(lpFileName);
  LastError = v9;
  if ( v9 )
  {
    fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 196);
    goto LABEL_43;
  }
  if ( (unsigned int)EfspCheckForNetSession() )
  {
    if ( v26 == 1 )
    {
      LastError = 5;
LABEL_43:
      RpcRevertToSelf();
      goto LABEL_44;
    }
    IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
    LastError = IsValidNetworkProtSeq;
    if ( IsValidNetworkProtSeq )
    {
      fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 217);
      goto LABEL_43;
    }
    if ( (unsigned int)EfsDllShareDecline(a2, 1, 387) )
    {
      LastError = GetLastError();
      fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, LastError, 6, 228);
      goto LABEL_43;
    }
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    fnEfsLogTrace1(v15, (unsigned int)EFS_API_ERROR, LastError, 6, 236);
    goto LABEL_43;
  }
  if ( (FileAttributesW & 0x4000) == 0 )
  {
    LastError = 0;
    goto LABEL_43;
  }
  RtlInitUnicodeString(&DestinationString, lpFileName);
  if ( v26 == 1 )
  {
    hObject = 0;
    RpcRevertToSelf();
  }
  else
  {
    LastError = EfsDllGetVolumeRoot(&DestinationString, P);
    RpcRevertToSelf();
    if ( LastError )
    {
      fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, LastError, 6, 16);
      goto LABEL_44;
    }
    LogFile = EfsDllGetLogFile(P, &hObject);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    if ( LogFile < 0 )
    {
      LastError = RtlNtStatusToDosError(LogFile);
      if ( LastError == 317 )
      {
        fnEfsLogTrace1(v18, (unsigned int)EFS_API_ERROR, LogFile, 6, 32);
        LastError = 6001;
      }
      goto LABEL_44;
    }
  }
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    if ( (unsigned __int8)EfsDllGetUserInfo(v25) )
    {
      if ( (unsigned int)EfsDllLoadUserProfile(v25, 0) )
      {
        LastError = EfsDllDecryptFileSrv(v25, &DestinationString, hObject, a3);
        EfsDllUnloadUserProfile(v25);
      }
      else
      {
        LastError = GetLastError();
      }
      EfsDllFreeUserInfo(v25);
    }
    else
    {
      LastError = GetLastError();
    }
    goto LABEL_43;
  }
  if ( hObject )
  {
    EfsDllMarkFileForDelete();
    goto LABEL_44;
  }
LABEL_46:
  if ( lpFileName )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x1800058a0  push    rbp
0x1800058a2  push    rbx
0x1800058a3  push    rsi
0x1800058a4  push    rdi
0x1800058a5  push    r12
0x1800058a7  push    r14
0x1800058a9  lea     rbp, [rsp-2Fh]
0x1800058ae  sub     rsp, 0D8h
0x1800058b5  xor     eax, eax
0x1800058b7  mov     [rbp+57h+hObject], 0
0x1800058bf  mov     r14d, r8d
0x1800058c2  mov     [rbp+57h+lpFileName], 0
0x1800058ca  mov     rdi, rdx
0x1800058cd  mov     [rbp+57h+arg_18], ax
0x1800058d1  mov     rsi, rcx
0x1800058d4  xorps   xmm0, xmm0
0x1800058d7  xorps   xmm1, xmm1
0x1800058da  lea     r8d, [rax+70h]; Size
0x1800058de  xor     edx, edx; Val
0x1800058e0  lea     rcx, [rbp+57h+var_A0]; void *
0x1800058e4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800058e8  movups  xmmword ptr [rbp+57h+P], xmm1
0x1800058ec  call    memset_0
0x1800058f1  cmp     cs:EfsServerInitialized, 0
0x1800058f8  jnz     short loc_180005904
0x1800058fa  mov     ebx, 32h ; '2'
0x1800058ff  jmp     loc_180005BA4
0x180005904  call    cs:__imp_EfsDllDisabled
0x18000590a  test    al, al
0x18000590c  jz      short loc_180005918
0x18000590e  mov     ebx, 177Fh
0x180005913  jmp     loc_180005B86
0x180005918  call    EfsEnforceClientAuthentication
0x18000591d  mov     ebx, eax
0x18000591f  test    eax, eax
0x180005921  jz      short loc_180005945
0x180005923  mov     dword ptr [rsp+100h+var_E0], 3B4h
0x18000592b  mov     r8d, eax
0x18000592e  mov     r9d, 6
0x180005934  lea     rdx, EFS_API_ERROR
0x18000593b  call    fnEfsLogTrace1
0x180005940  jmp     loc_180005B86
0x180005945  lea     r9, [rbp+57h+arg_18]
0x180005949  xor     edx, edx
0x18000594b  lea     r8, [rbp+57h+lpFileName]
0x18000594f  mov     rcx, rdi
0x180005952  call    cs:__imp_EfsDllGetLocalFileName
0x180005958  mov     ebx, eax
0x18000595a  test    eax, eax
0x18000595c  jz      short loc_180005968
0x18000595e  mov     dword ptr [rsp+100h+var_E0], 3B9h
0x180005966  jmp     short loc_18000592B
0x180005968  xor     ecx, ecx; BindingHandle
0x18000596a  call    cs:__imp_RpcImpersonateClient
0x180005970  mov     ebx, eax
0x180005972  test    eax, eax
0x180005974  jz      short loc_180005980
0x180005976  mov     dword ptr [rsp+100h+var_E0], 3BEh
0x18000597e  jmp     short loc_18000592B
0x180005980  mov     rcx, [rbp+57h+lpFileName]
0x180005984  call    EfsEnsureLocalPath
0x180005989  mov     ebx, eax
0x18000598b  test    eax, eax
0x18000598d  jz      short loc_1800059B1
0x18000598f  mov     dword ptr [rsp+100h+var_E0], 3C4h
0x180005997  mov     r9d, 6
0x18000599d  lea     rdx, EFS_API_ERROR
0x1800059a4  mov     r8d, eax
0x1800059a7  call    fnEfsLogTrace1
0x1800059ac  jmp     loc_180005B80
0x1800059b1  call    EfspCheckForNetSession
0x1800059b6  mov     r12d, 1
0x1800059bc  test    eax, eax
0x1800059be  jz      short loc_180005A11
0x1800059c0  cmp     [rbp+57h+arg_18], r12w
0x1800059c5  jnz     short loc_1800059D1
0x1800059c7  lea     ebx, [r12+4]
0x1800059cc  jmp     loc_180005B80
0x1800059d1  mov     rcx, rsi
0x1800059d4  call    EfspIsValidNetworkProtSeq
0x1800059d9  mov     ebx, eax
0x1800059db  test    eax, eax
0x1800059dd  jz      short loc_1800059E9
0x1800059df  mov     dword ptr [rsp+100h+var_E0], 3D9h
0x1800059e7  jmp     short loc_180005997
0x1800059e9  mov     r8d, 183h
0x1800059ef  mov     edx, r12d
0x1800059f2  mov     rcx, rdi
0x1800059f5  call    cs:__imp_EfsDllShareDecline
0x1800059fb  test    eax, eax
0x1800059fd  jz      short loc_180005A11
0x1800059ff  call    cs:__imp_GetLastError
0x180005a05  mov     ebx, eax
0x180005a07  mov     dword ptr [rsp+100h+var_E0], 3E4h
0x180005a0f  jmp     short loc_180005997
0x180005a11  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180005a15  call    cs:__imp_GetFileAttributesW
0x180005a1b  cmp     eax, 0FFFFFFFFh
0x180005a1e  jnz     short loc_180005A35
0x180005a20  call    cs:__imp_GetLastError
0x180005a26  mov     ebx, eax
0x180005a28  mov     dword ptr [rsp+100h+var_E0], 3ECh
0x180005a30  jmp     loc_180005997
0x180005a35  bt      eax, 0Eh
0x180005a39  jb      short loc_180005A42
0x180005a3b  xor     ebx, ebx
0x180005a3d  jmp     loc_180005B80
0x180005a42  mov     rdx, [rbp+57h+lpFileName]; SourceString
0x180005a46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180005a4a  call    cs:__imp_RtlInitUnicodeString
0x180005a50  cmp     [rbp+57h+arg_18], r12w
0x180005a55  jnz     short loc_180005A8F
0x180005a57  mov     [rbp+57h+hObject], 0
0x180005a5f  call    cs:__imp_RpcRevertToSelf
0x180005a65  xor     ecx, ecx; BindingHandle
0x180005a67  call    cs:__imp_RpcImpersonateClient
0x180005a6d  mov     ebx, eax
0x180005a6f  test    eax, eax
0x180005a71  jz      loc_180005B23
0x180005a77  mov     rcx, [rbp+57h+hObject]
0x180005a7b  test    rcx, rcx
0x180005a7e  jz      loc_180005B95
0x180005a84  call    cs:__imp_EfsDllMarkFileForDelete
0x180005a8a  jmp     loc_180005B86
0x180005a8f  lea     rdx, [rbp+57h+P]
0x180005a93  lea     rcx, [rbp+57h+DestinationString]
0x180005a97  call    cs:__imp_EfsDllGetVolumeRoot
0x180005a9d  mov     ebx, eax
0x180005a9f  call    cs:__imp_RpcRevertToSelf
0x180005aa5  test    ebx, ebx
0x180005aa7  jz      short loc_180005AB9
0x180005aa9  mov     dword ptr [rsp+100h+var_E0], 410h
0x180005ab1  mov     r8d, ebx
0x180005ab4  jmp     loc_18000592E
0x180005ab9  lea     rdx, [rbp+57h+hObject]
0x180005abd  lea     rcx, [rbp+57h+P]
0x180005ac1  call    cs:__imp_EfsDllGetLogFile
0x180005ac7  mov     rcx, gs:60h
0x180005ad0  xor     edx, edx; Flags
0x180005ad2  mov     r8, [rbp+57h+P+8]; P
0x180005ad6  mov     edi, eax
0x180005ad8  mov     rcx, [rcx+30h]; HeapHandle
0x180005adc  call    cs:__imp_RtlFreeHeap
0x180005ae2  test    edi, edi
0x180005ae4  jns     loc_180005A65
0x180005aea  mov     ecx, edi; Status
0x180005aec  call    cs:__imp_RtlNtStatusToDosError
0x180005af2  mov     ebx, eax
0x180005af4  cmp     eax, 13Dh
0x180005af9  jnz     loc_180005B86
0x180005aff  mov     r9d, 6
0x180005b05  mov     dword ptr [rsp+100h+var_E0], 420h
0x180005b0d  mov     r8d, edi
0x180005b10  lea     rdx, EFS_API_ERROR
0x180005b17  call    fnEfsLogTrace1
0x180005b1c  mov     ebx, 1771h
0x180005b21  jmp     short loc_180005B86
0x180005b23  lea     rcx, [rbp+57h+var_A0]
0x180005b27  call    cs:__imp_EfsDllGetUserInfo
0x180005b2d  test    al, al
0x180005b2f  jnz     short loc_180005B3B
0x180005b31  call    cs:__imp_GetLastError
0x180005b37  mov     ebx, eax
0x180005b39  jmp     short loc_180005B80
0x180005b3b  xor     edx, edx
0x180005b3d  lea     rcx, [rbp+57h+var_A0]
0x180005b41  call    cs:__imp_EfsDllLoadUserProfile
0x180005b47  test    eax, eax
0x180005b49  jnz     short loc_180005B55
0x180005b4b  call    cs:__imp_GetLastError
0x180005b51  mov     ebx, eax
0x180005b53  jmp     short loc_180005B76
0x180005b55  mov     r8, [rbp+57h+hObject]
0x180005b59  lea     rdx, [rbp+57h+DestinationString]
0x180005b5d  mov     r9d, r14d
0x180005b60  lea     rcx, [rbp+57h+var_A0]
0x180005b64  call    cs:__imp_EfsDllDecryptFileSrv
0x180005b6a  mov     ebx, eax
0x180005b6c  lea     rcx, [rbp+57h+var_A0]
0x180005b70  call    cs:__imp_EfsDllUnloadUserProfile
0x180005b76  lea     rcx, [rbp+57h+var_A0]
0x180005b7a  call    cs:__imp_EfsDllFreeUserInfo
0x180005b80  call    cs:__imp_RpcRevertToSelf
0x180005b86  mov     rcx, [rbp+57h+hObject]; hObject
0x180005b8a  test    rcx, rcx
0x180005b8d  jz      short loc_180005B95
0x180005b8f  call    cs:__imp_CloseHandle
0x180005b95  mov     rcx, [rbp+57h+lpFileName]
0x180005b99  test    rcx, rcx
0x180005b9c  jz      short loc_180005BA4
0x180005b9e  call    cs:__imp_EfsDllFreeHeap
0x180005ba4  mov     eax, ebx
0x180005ba6  add     rsp, 0D8h
0x180005bad  pop     r14
0x180005baf  pop     r12
0x180005bb1  pop     rdi
0x180005bb2  pop     rsi
0x180005bb3  pop     rbx
0x180005bb4  pop     rbp
0x180005bb5  retn
```
