# EfsRpcDecryptFileSrvInternal

- ea: `0x180005d00`
- end: `0x1800060b9`
- name: `EfsRpcDecryptFileSrvInternal`
- size: `953`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180005cf0`
- `0x180006460`

## callees

- `0x1800037b8`
- `0x180005d00`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`
- `0x18000c094`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006085`
- `RPCRT4!RpcRevertToSelf` at `0x180005ef2`
- `RPCRT4!RpcRevertToSelf` at `0x180005f4a`
- `RPCRT4!RpcRevertToSelf` at `0x180006070`
- `RPCRT4!RpcRevertToSelf` at `0x180005ef2`
- `RPCRT4!RpcRevertToSelf` at `0x180005f4a`
- `RPCRT4!RpcRevertToSelf` at `0x180006070`
- `RPCRT4!RpcImpersonateClient` at `0x180005dd6`
- `RPCRT4!RpcImpersonateClient` at `0x180005f00`
- `RPCRT4!RpcImpersonateClient` at `0x180005dd6`
- `RPCRT4!RpcImpersonateClient` at `0x180005f00`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005e96`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005e96`
- `ntdll!RtlFreeHeap` at `0x180005f93`
- `ntdll!RtlFreeHeap` at `0x180005f93`
- `ntdll!RtlInitUnicodeString` at `0x180005ed7`
- `ntdll!RtlInitUnicodeString` at `0x180005ed7`
- `ntdll!RtlNtStatusToDosError` at `0x180005fa9`
- `ntdll!RtlNtStatusToDosError` at `0x180005fa9`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x180005f23`
- `EFSCORE!EfsDllMarkFileForDelete` at `0x180005f23`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x180006042`
- `EFSCORE!EfsDllDecryptFileSrv` at `0x180006042`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180006054`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180006054`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005db8`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005db8`
- `EFSCORE!EfsDllDisabled` at `0x180005d64`
- `EFSCORE!EfsDllDisabled` at `0x180005d64`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006064`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006064`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005f3c`
- `EFSCORE!EfsDllGetVolumeRoot` at `0x180005f3c`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005fed`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005fed`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006013`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006013`
- `EFSCORE!EfsDllShareDecline` at `0x180005e67`
- `EFSCORE!EfsDllShareDecline` at `0x180005e67`
- `EFSCORE!EfsDllFreeHeap` at `0x18000609a`
- `EFSCORE!EfsDllFreeHeap` at `0x18000609a`
- `EFSCORE!EfsDllGetLogFile` at `0x180005f72`
- `EFSCORE!EfsDllGetLogFile` at `0x180005f72`

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
0x180005d00  push    rbp
0x180005d02  push    rbx
0x180005d03  push    rsi
0x180005d04  push    rdi
0x180005d05  push    r12
0x180005d07  push    r14
0x180005d09  lea     rbp, [rsp-2Fh]
0x180005d0e  sub     rsp, 0D8h
0x180005d15  xor     eax, eax
0x180005d17  mov     [rbp+57h+hObject], 0
0x180005d1f  mov     r14d, r8d
0x180005d22  mov     [rbp+57h+lpFileName], 0
0x180005d2a  mov     rdi, rdx
0x180005d2d  mov     [rbp+57h+arg_18], ax
0x180005d31  mov     rsi, rcx
0x180005d34  xorps   xmm0, xmm0
0x180005d37  xorps   xmm1, xmm1
0x180005d3a  lea     r8d, [rax+70h]; Size
0x180005d3e  xor     edx, edx; Val
0x180005d40  lea     rcx, [rbp+57h+var_A0]; void *
0x180005d44  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180005d48  movups  xmmword ptr [rbp+57h+P], xmm1
0x180005d4c  call    memset_0
0x180005d51  cmp     cs:EfsServerInitialized, 0
0x180005d58  jnz     short loc_180005D64
0x180005d5a  mov     ebx, 32h ; '2'
0x180005d5f  jmp     loc_1800060A6
0x180005d64  call    cs:__imp_EfsDllDisabled
0x180005d6b  nop     dword ptr [rax+rax+00h]
0x180005d70  test    al, al
0x180005d72  jz      short loc_180005D7E
0x180005d74  mov     ebx, 177Fh
0x180005d79  jmp     loc_18000607C
0x180005d7e  call    EfsEnforceClientAuthentication
0x180005d83  mov     ebx, eax
0x180005d85  test    eax, eax
0x180005d87  jz      short loc_180005DAB
0x180005d89  mov     dword ptr [rsp+100h+var_E0], 3B4h
0x180005d91  mov     r8d, eax
0x180005d94  mov     r9d, 6
0x180005d9a  lea     rdx, EFS_API_ERROR
0x180005da1  call    fnEfsLogTrace1
0x180005da6  jmp     loc_18000607C
0x180005dab  lea     r9, [rbp+57h+arg_18]
0x180005daf  xor     edx, edx
0x180005db1  lea     r8, [rbp+57h+lpFileName]
0x180005db5  mov     rcx, rdi
0x180005db8  call    cs:__imp_EfsDllGetLocalFileName
0x180005dbf  nop     dword ptr [rax+rax+00h]
0x180005dc4  mov     ebx, eax
0x180005dc6  test    eax, eax
0x180005dc8  jz      short loc_180005DD4
0x180005dca  mov     dword ptr [rsp+100h+var_E0], 3B9h
0x180005dd2  jmp     short loc_180005D91
0x180005dd4  xor     ecx, ecx; BindingHandle
0x180005dd6  call    cs:__imp_RpcImpersonateClient
0x180005ddd  nop     dword ptr [rax+rax+00h]
0x180005de2  mov     ebx, eax
0x180005de4  test    eax, eax
0x180005de6  jz      short loc_180005DF2
0x180005de8  mov     dword ptr [rsp+100h+var_E0], 3BEh
0x180005df0  jmp     short loc_180005D91
0x180005df2  mov     rcx, [rbp+57h+lpFileName]
0x180005df6  call    EfsEnsureLocalPath
0x180005dfb  mov     ebx, eax
0x180005dfd  test    eax, eax
0x180005dff  jz      short loc_180005E23
0x180005e01  mov     dword ptr [rsp+100h+var_E0], 3C4h
0x180005e09  mov     r9d, 6
0x180005e0f  lea     rdx, EFS_API_ERROR
0x180005e16  mov     r8d, eax
0x180005e19  call    fnEfsLogTrace1
0x180005e1e  jmp     loc_180006070
0x180005e23  call    EfspCheckForNetSession
0x180005e28  mov     r12d, 1
0x180005e2e  test    eax, eax
0x180005e30  jz      short loc_180005E92
0x180005e32  cmp     [rbp+57h+arg_18], r12w
0x180005e37  jnz     short loc_180005E43
0x180005e39  lea     ebx, [r12+4]
0x180005e3e  jmp     loc_180006070
0x180005e43  mov     rcx, rsi
0x180005e46  call    EfspIsValidNetworkProtSeq
0x180005e4b  mov     ebx, eax
0x180005e4d  test    eax, eax
0x180005e4f  jz      short loc_180005E5B
0x180005e51  mov     dword ptr [rsp+100h+var_E0], 3D9h
0x180005e59  jmp     short loc_180005E09
0x180005e5b  mov     r8d, 183h
0x180005e61  mov     edx, r12d
0x180005e64  mov     rcx, rdi
0x180005e67  call    cs:__imp_EfsDllShareDecline
0x180005e6e  nop     dword ptr [rax+rax+00h]
0x180005e73  test    eax, eax
0x180005e75  jz      short loc_180005E92
0x180005e77  call    cs:__imp_GetLastError
0x180005e7e  nop     dword ptr [rax+rax+00h]
0x180005e83  mov     ebx, eax
0x180005e85  mov     dword ptr [rsp+100h+var_E0], 3E4h
0x180005e8d  jmp     loc_180005E09
0x180005e92  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180005e96  call    cs:__imp_GetFileAttributesW
0x180005e9d  nop     dword ptr [rax+rax+00h]
0x180005ea2  cmp     eax, 0FFFFFFFFh
0x180005ea5  jnz     short loc_180005EC2
0x180005ea7  call    cs:__imp_GetLastError
0x180005eae  nop     dword ptr [rax+rax+00h]
0x180005eb3  mov     ebx, eax
0x180005eb5  mov     dword ptr [rsp+100h+var_E0], 3ECh
0x180005ebd  jmp     loc_180005E09
0x180005ec2  bt      eax, 0Eh
0x180005ec6  jb      short loc_180005ECF
0x180005ec8  xor     ebx, ebx
0x180005eca  jmp     loc_180006070
0x180005ecf  mov     rdx, [rbp+57h+lpFileName]; SourceString
0x180005ed3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180005ed7  call    cs:__imp_RtlInitUnicodeString
0x180005ede  nop     dword ptr [rax+rax+00h]
0x180005ee3  cmp     [rbp+57h+arg_18], r12w
0x180005ee8  jnz     short loc_180005F34
0x180005eea  mov     [rbp+57h+hObject], 0
0x180005ef2  call    cs:__imp_RpcRevertToSelf
0x180005ef9  nop     dword ptr [rax+rax+00h]
0x180005efe  xor     ecx, ecx; BindingHandle
0x180005f00  call    cs:__imp_RpcImpersonateClient
0x180005f07  nop     dword ptr [rax+rax+00h]
0x180005f0c  mov     ebx, eax
0x180005f0e  test    eax, eax
0x180005f10  jz      loc_180005FE9
0x180005f16  mov     rcx, [rbp+57h+hObject]
0x180005f1a  test    rcx, rcx
0x180005f1d  jz      loc_180006091
0x180005f23  call    cs:__imp_EfsDllMarkFileForDelete
0x180005f2a  nop     dword ptr [rax+rax+00h]
0x180005f2f  jmp     loc_18000607C
0x180005f34  lea     rdx, [rbp+57h+P]
0x180005f38  lea     rcx, [rbp+57h+DestinationString]
0x180005f3c  call    cs:__imp_EfsDllGetVolumeRoot
0x180005f43  nop     dword ptr [rax+rax+00h]
0x180005f48  mov     ebx, eax
0x180005f4a  call    cs:__imp_RpcRevertToSelf
0x180005f51  nop     dword ptr [rax+rax+00h]
0x180005f56  test    ebx, ebx
0x180005f58  jz      short loc_180005F6A
0x180005f5a  mov     dword ptr [rsp+100h+var_E0], 410h
0x180005f62  mov     r8d, ebx
0x180005f65  jmp     loc_180005D94
0x180005f6a  lea     rdx, [rbp+57h+hObject]
0x180005f6e  lea     rcx, [rbp+57h+P]
0x180005f72  call    cs:__imp_EfsDllGetLogFile
0x180005f79  nop     dword ptr [rax+rax+00h]
0x180005f7e  mov     rcx, gs:60h
0x180005f87  xor     edx, edx; Flags
0x180005f89  mov     r8, [rbp+57h+P+8]; P
0x180005f8d  mov     edi, eax
0x180005f8f  mov     rcx, [rcx+30h]; HeapHandle
0x180005f93  call    cs:__imp_RtlFreeHeap
0x180005f9a  nop     dword ptr [rax+rax+00h]
0x180005f9f  test    edi, edi
0x180005fa1  jns     loc_180005EFE
0x180005fa7  mov     ecx, edi; Status
0x180005fa9  call    cs:__imp_RtlNtStatusToDosError
0x180005fb0  nop     dword ptr [rax+rax+00h]
0x180005fb5  mov     ebx, eax
0x180005fb7  cmp     eax, 13Dh
0x180005fbc  jnz     loc_18000607C
0x180005fc2  mov     r9d, 6
0x180005fc8  mov     dword ptr [rsp+100h+var_E0], 420h
0x180005fd0  mov     r8d, edi
0x180005fd3  lea     rdx, EFS_API_ERROR
0x180005fda  call    fnEfsLogTrace1
0x180005fdf  mov     ebx, 1771h
0x180005fe4  jmp     loc_18000607C
0x180005fe9  lea     rcx, [rbp+57h+var_A0]
0x180005fed  call    cs:__imp_EfsDllGetUserInfo
0x180005ff4  nop     dword ptr [rax+rax+00h]
0x180005ff9  test    al, al
0x180005ffb  jnz     short loc_18000600D
0x180005ffd  call    cs:__imp_GetLastError
0x180006004  nop     dword ptr [rax+rax+00h]
0x180006009  mov     ebx, eax
0x18000600b  jmp     short loc_180006070
0x18000600d  xor     edx, edx
0x18000600f  lea     rcx, [rbp+57h+var_A0]
0x180006013  call    cs:__imp_EfsDllLoadUserProfile
0x18000601a  nop     dword ptr [rax+rax+00h]
0x18000601f  test    eax, eax
0x180006021  jnz     short loc_180006033
0x180006023  call    cs:__imp_GetLastError
0x18000602a  nop     dword ptr [rax+rax+00h]
0x18000602f  mov     ebx, eax
0x180006031  jmp     short loc_180006060
0x180006033  mov     r8, [rbp+57h+hObject]
0x180006037  lea     rdx, [rbp+57h+DestinationString]
0x18000603b  mov     r9d, r14d
0x18000603e  lea     rcx, [rbp+57h+var_A0]
0x180006042  call    cs:__imp_EfsDllDecryptFileSrv
0x180006049  nop     dword ptr [rax+rax+00h]
0x18000604e  mov     ebx, eax
0x180006050  lea     rcx, [rbp+57h+var_A0]
0x180006054  call    cs:__imp_EfsDllUnloadUserProfile
0x18000605b  nop     dword ptr [rax+rax+00h]
0x180006060  lea     rcx, [rbp+57h+var_A0]
0x180006064  call    cs:__imp_EfsDllFreeUserInfo
0x18000606b  nop     dword ptr [rax+rax+00h]
0x180006070  call    cs:__imp_RpcRevertToSelf
0x180006077  nop     dword ptr [rax+rax+00h]
0x18000607c  mov     rcx, [rbp+57h+hObject]; hObject
0x180006080  test    rcx, rcx
0x180006083  jz      short loc_180006091
0x180006085  call    cs:__imp_CloseHandle
0x18000608c  nop     dword ptr [rax+rax+00h]
0x180006091  mov     rcx, [rbp+57h+lpFileName]
0x180006095  test    rcx, rcx
0x180006098  jz      short loc_1800060A6
0x18000609a  call    cs:__imp_EfsDllFreeHeap
0x1800060a1  nop     dword ptr [rax+rax+00h]
0x1800060a6  mov     eax, ebx
0x1800060a8  add     rsp, 0D8h
0x1800060af  pop     r14
0x1800060b1  pop     r12
0x1800060b3  pop     rdi
0x1800060b4  pop     rsi
0x1800060b5  pop     rbx
0x1800060b6  pop     rbp
0x1800060b7  retn
```
