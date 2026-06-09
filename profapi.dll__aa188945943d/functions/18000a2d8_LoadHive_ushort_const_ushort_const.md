# _LoadHive(ushort const *,ushort const *)

- ea: `0x18000a2d8`
- end: `0x18000a3d3`
- name: `?_LoadHive@@YAJPEBG0@Z`
- size: `251`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpFile, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a250`

## callees

- `0x180003fdc`
- `0x180005b60`
- `0x1800061a4`
- `0x18000a2d8`
- `0x18000a7c4`
- `0x18000ccec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a35a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a35a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a368`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000a397`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000a397`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a380`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a380`
- `RPCRT4!RpcRevertToSelf` at `0x18000a374`
- `RPCRT4!RpcRevertToSelf` at `0x18000a374`

## pseudocode

```c
__int64 __fastcall _LoadHive(LPCWSTR lpSubKey, LPCWSTR lpFile, unsigned int a3)
{
  int v5; // eax
  unsigned int v6; // edi
  HANDLE v7; // rbx
  unsigned int KeyW; // eax
  unsigned int v10; // ebx
  unsigned int v11; // [rsp+20h] [rbp-38h] BYREF
  HANDLE Token; // [rsp+28h] [rbp-30h]
  __int64 v13; // [rsp+30h] [rbp-28h]
  int v14; // [rsp+38h] [rbp-20h]
  __int128 v15; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  unsigned int v17; // [rsp+90h] [rbp+38h] BYREF

  v11 = 0;
  Token = 0;
  v13 = 0;
  v14 = 0;
  v17 = 18;
  v15 = 0;
  v5 = CThreadContext::EnablePrivileges((CThreadContext *)&v11, &v17, a3);
  v6 = v5;
  if ( v5 >= 0 )
  {
    KeyW = RegLoadKeyW(HKEY_USERS, lpSubKey, lpFile);
    if ( KeyW )
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x163,
              (unsigned int)"minio\\profapi\\load.cpp",
              (const char *)KeyW,
              v11);
    else
      v10 = 0;
    CThreadContext::~CThreadContext((CThreadContext *)&v11);
    return v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)v5,
      v11);
    CThreadContext::RevertPrivileges((CThreadContext *)&v11);
    if ( v11 )
    {
      v7 = Token;
      SetThreadToken(0, Token);
      if ( v7 )
        CloseHandle(v7);
    }
    if ( HIDWORD(v13) )
      RpcRevertToSelf();
    if ( (_DWORD)v13 )
      RevertToSelf();
    return v6;
  }
}

```

## disassembly

```asm
0x18000a2d8  push    rbp
0x18000a2da  push    rbx
0x18000a2db  push    rsi
0x18000a2dc  push    rdi
0x18000a2dd  mov     rbp, rsp
0x18000a2e0  sub     rsp, 58h
0x18000a2e4  mov     rbx, rdx
0x18000a2e7  mov     [rbp+var_38], 0
0x18000a2ee  mov     rsi, rcx
0x18000a2f1  mov     [rbp+Token], 0
0x18000a2f9  xorps   xmm0, xmm0
0x18000a2fc  mov     [rbp+var_28], 0
0x18000a304  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000a308  mov     [rbp+var_20], 0
0x18000a30f  lea     rcx, [rbp+var_38]; this
0x18000a313  mov     [rbp+arg_10], 12h
0x18000a31a  movdqu  [rbp+var_18], xmm0
0x18000a31f  call    ?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z; CThreadContext::EnablePrivileges(ulong *,ulong)
0x18000a324  mov     edi, eax
0x18000a326  test    eax, eax
0x18000a328  jns     short loc_18000A38A
0x18000a32a  mov     rcx, [rbp+20h]; this
0x18000a32e  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000a335  mov     r9d, eax; char *
0x18000a338  mov     edx, 162h; void *
0x18000a33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a342  lea     rcx, [rbp+var_38]; this
0x18000a346  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18000a34b  cmp     [rbp+var_38], 0
0x18000a34f  jz      short loc_18000A36E
0x18000a351  mov     rbx, [rbp+Token]
0x18000a355  xor     ecx, ecx; Thread
0x18000a357  mov     rdx, rbx; Token
0x18000a35a  call    cs:__imp_SetThreadToken
0x18000a360  test    rbx, rbx
0x18000a363  jz      short loc_18000A36E
0x18000a365  mov     rcx, rbx; hObject
0x18000a368  call    cs:__imp_CloseHandle
0x18000a36e  cmp     dword ptr [rbp+var_28+4], 0
0x18000a372  jz      short loc_18000A37A
0x18000a374  call    cs:__imp_RpcRevertToSelf
0x18000a37a  cmp     dword ptr [rbp+var_28], 0
0x18000a37e  jz      short loc_18000A386
0x18000a380  call    cs:__imp_RevertToSelf
0x18000a386  mov     eax, edi
0x18000a388  jmp     short loc_18000A3CA
0x18000a38a  mov     r8, rbx; lpFile
0x18000a38d  mov     rdx, rsi; lpSubKey
0x18000a390  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000a397  call    cs:__imp_RegLoadKeyW
0x18000a39d  test    eax, eax
0x18000a39f  jz      short loc_18000A3BD
0x18000a3a1  mov     rcx, [rbp+20h]; this
0x18000a3a5  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000a3ac  mov     r9d, eax; char *
0x18000a3af  mov     edx, 163h; void *
0x18000a3b4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a3b9  mov     ebx, eax
0x18000a3bb  jmp     short loc_18000A3BF
0x18000a3bd  xor     ebx, ebx
0x18000a3bf  lea     rcx, [rbp+var_38]; this
0x18000a3c3  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18000a3c8  mov     eax, ebx
0x18000a3ca  add     rsp, 58h
0x18000a3ce  pop     rdi
0x18000a3cf  pop     rsi
0x18000a3d0  pop     rbx
0x18000a3d1  pop     rbp
0x18000a3d2  retn
```
