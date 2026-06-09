# LuiApiServer::BindRpc(void)

- ea: `0x1800ed5a4`
- end: `0x1800ed7e4`
- name: `?BindRpc@LuiApiServer@@YAJXZ`
- size: `576`
- prototype: `__int64 __fastcall(LuiApiServer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800eb020`

## callees

- `0x18000df90`
- `0x18006ba8c`
- `0x1800ed5a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ed7c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ed7c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ed649`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ed649`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800ed7a3`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800ed7a3`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ed66f`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ed66f`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ed6c3`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ed6c3`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800ed6ec`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800ed6ec`
- `RPCRT4!RpcServerListen` at `0x1800ed70f`
- `RPCRT4!RpcServerListen` at `0x1800ed70f`
- `RPCRT4!RpcBindingVectorFree` at `0x1800ed7b4`
- `RPCRT4!RpcBindingVectorFree` at `0x1800ed7b4`
- `RPCRT4!RpcEpUnregister` at `0x1800ed78c`
- `RPCRT4!RpcEpUnregister` at `0x1800ed78c`
- `RPCRT4!RpcEpRegisterW` at `0x1800ed75f`
- `RPCRT4!RpcEpRegisterW` at `0x1800ed75f`
- `RPCRT4!RpcServerInqBindings` at `0x1800ed734`
- `RPCRT4!RpcServerInqBindings` at `0x1800ed734`

## string_xrefs

- `0x1800ed74e`: `LUI Service`

## pseudocode

```c
__int64 __fastcall LuiApiServer::BindRpc(LuiApiServer *this)
{
  char v1; // di
  CommonUtil *v2; // rcx
  signed int LastErrorToHResultAndForceFailure; // ebx
  RPC_STATUS v4; // eax
  int v5; // eax
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-71h] BYREF
  WCHAR StringSecurityDescriptor[72]; // [rsp+50h] [rbp-69h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;R;;;AC)");
  v1 = 0;
  BindingVector = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v2);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_25;
  }
  v4 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0, SecurityDescriptor);
  LastErrorToHResultAndForceFailure = v4;
  if ( v4 > 0 )
    LastErrorToHResultAndForceFailure = (unsigned __int16)v4 | 0x80070000;
  if ( LastErrorToHResultAndForceFailure < 0 )
    goto LABEL_25;
  v5 = RpcServerRegisterIf3(qword_18010A9F0, 0, 0, 40, 0, 0, 0, SecurityDescriptor);
  LastErrorToHResultAndForceFailure = v5;
  if ( v5 > 0 )
    LastErrorToHResultAndForceFailure = (unsigned __int16)v5 | 0x80070000;
  if ( LastErrorToHResultAndForceFailure < 0 )
    goto LABEL_25;
  v1 = 1;
  v6 = RpcServerRegisterAuthInfoW(0, 9u, 0, 0);
  LastErrorToHResultAndForceFailure = v6;
  if ( v6 > 0 )
    LastErrorToHResultAndForceFailure = (unsigned __int16)v6 | 0x80070000;
  if ( LastErrorToHResultAndForceFailure < 0 )
    goto LABEL_25;
  v7 = RpcServerListen(1u, 0x4D2u, 1u);
  LastErrorToHResultAndForceFailure = v7;
  if ( v7 )
  {
    if ( v7 != 1713 )
    {
      if ( v7 > 0 )
        LastErrorToHResultAndForceFailure = (unsigned __int16)v7 | 0x80070000;
      if ( LastErrorToHResultAndForceFailure < 0 )
        goto LABEL_25;
    }
  }
  v8 = RpcServerInqBindings(&BindingVector);
  LastErrorToHResultAndForceFailure = v8;
  if ( v8 > 0 )
    LastErrorToHResultAndForceFailure = (unsigned __int16)v8 | 0x80070000;
  if ( LastErrorToHResultAndForceFailure < 0 )
    goto LABEL_25;
  v9 = RpcEpRegisterW(qword_18010A9F0, BindingVector, 0, (RPC_WSTR)L"LUI Service");
  LastErrorToHResultAndForceFailure = v9;
  if ( v9 > 0 )
    LastErrorToHResultAndForceFailure = (unsigned __int16)v9 | 0x80070000;
  if ( LastErrorToHResultAndForceFailure < 0 )
  {
LABEL_25:
    if ( v1 )
      RpcServerUnregisterIfEx(qword_18010A9F0, 0, 0);
  }
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800ed5a4  push    rbp
0x1800ed5a6  push    rbx
0x1800ed5a7  push    rdi
0x1800ed5a8  push    r14
0x1800ed5aa  lea     rbp, [rsp-3Fh]
0x1800ed5af  sub     rsp, 0F8h
0x1800ed5b6  mov     rax, cs:__security_cookie
0x1800ed5bd  xor     rax, rsp
0x1800ed5c0  mov     [rbp+57h+var_30], rax
0x1800ed5c4  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800ed5cb  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800ed5cf  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+10h; "GWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)("...
0x1800ed5d6  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800ed5da  movups  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x1800ed5de  xor     r9d, r9d; SecurityDescriptorSize
0x1800ed5e1  xor     dil, dil
0x1800ed5e4  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+20h; "D)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;"...
0x1800ed5eb  movups  [rbp+57h+var_A0], xmm0
0x1800ed5ef  mov     [rbp+57h+BindingVector], 0
0x1800ed5f7  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+40h; "C)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x1800ed5fe  lea     edx, [r9+1]; StringSDRevision
0x1800ed602  movups  [rbp+57h+var_B0], xmm1
0x1800ed606  mov     [rbp+57h+SecurityDescriptor], 0
0x1800ed60e  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+30h; "GWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x1800ed615  movups  [rbp+57h+var_80], xmm0
0x1800ed619  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+60h; ";;GA;;;OW)(A;;GR;;;AC)"
0x1800ed620  movups  [rbp+57h+var_90], xmm1
0x1800ed624  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+50h; ";;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x1800ed62b  movups  [rbp+57h+var_60], xmm0
0x1800ed62f  movups  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+7Eh; "R;;;AC)"
0x1800ed636  movups  [rbp+57h+var_70], xmm1
0x1800ed63a  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+70h; "W)(A;;GR;;;AC)"
0x1800ed641  movups  [rbp+57h+var_50], xmm1
0x1800ed645  movups  [rbp+57h+var_50+0Eh], xmm0
0x1800ed649  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ed64f  test    eax, eax
0x1800ed651  jnz     short loc_1800ED662
0x1800ed653  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ed658  mov     ebx, eax
0x1800ed65a  test    eax, eax
0x1800ed65c  js      loc_1800ED775
0x1800ed662  mov     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800ed666  lea     rcx, Protseq; "ncalrpc"
0x1800ed66d  xor     edx, edx; MaxCalls
0x1800ed66f  call    cs:__imp_RpcServerUseProtseqW
0x1800ed675  mov     ebx, eax
0x1800ed677  mov     r14d, 80070000h
0x1800ed67d  test    eax, eax
0x1800ed67f  jle     short loc_1800ED687
0x1800ed681  movzx   ebx, ax
0x1800ed684  or      ebx, r14d
0x1800ed687  test    ebx, ebx
0x1800ed689  js      loc_1800ED775
0x1800ed68f  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800ed693  lea     rcx, qword_18010A9F0
0x1800ed69a  mov     [rsp+110h+var_D8], rax
0x1800ed69f  mov     r9d, 28h ; '('
0x1800ed6a5  mov     [rsp+110h+var_E0], 0
0x1800ed6ae  xor     r8d, r8d
0x1800ed6b1  mov     [rsp+110h+var_E8], 0
0x1800ed6b9  xor     edx, edx
0x1800ed6bb  mov     [rsp+110h+var_F0], 0
0x1800ed6c3  call    cs:__imp_RpcServerRegisterIf3
0x1800ed6c9  mov     ebx, eax
0x1800ed6cb  test    eax, eax
0x1800ed6cd  jle     short loc_1800ED6D5
0x1800ed6cf  movzx   ebx, ax
0x1800ed6d2  or      ebx, r14d
0x1800ed6d5  test    ebx, ebx
0x1800ed6d7  js      loc_1800ED775
0x1800ed6dd  xor     r9d, r9d; Arg
0x1800ed6e0  xor     r8d, r8d; GetKeyFn
0x1800ed6e3  xor     ecx, ecx; ServerPrincName
0x1800ed6e5  mov     dil, 1
0x1800ed6e8  lea     edx, [r9+9]; AuthnSvc
0x1800ed6ec  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800ed6f2  mov     ebx, eax
0x1800ed6f4  test    eax, eax
0x1800ed6f6  jle     short loc_1800ED6FE
0x1800ed6f8  movzx   ebx, ax
0x1800ed6fb  or      ebx, r14d
0x1800ed6fe  test    ebx, ebx
0x1800ed700  js      short loc_1800ED775
0x1800ed702  mov     ecx, 1; MinimumCallThreads
0x1800ed707  mov     edx, 4D2h; MaxCalls
0x1800ed70c  mov     r8d, ecx; DontWait
0x1800ed70f  call    cs:__imp_RpcServerListen
0x1800ed715  mov     ebx, eax
0x1800ed717  test    eax, eax
0x1800ed719  jz      short loc_1800ED730
0x1800ed71b  cmp     eax, 6B1h
0x1800ed720  jz      short loc_1800ED730
0x1800ed722  test    eax, eax
0x1800ed724  jle     short loc_1800ED72C
0x1800ed726  movzx   ebx, ax
0x1800ed729  or      ebx, r14d
0x1800ed72c  test    ebx, ebx
0x1800ed72e  js      short loc_1800ED775
0x1800ed730  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x1800ed734  call    cs:__imp_RpcServerInqBindings
0x1800ed73a  mov     ebx, eax
0x1800ed73c  test    eax, eax
0x1800ed73e  jle     short loc_1800ED746
0x1800ed740  movzx   ebx, ax
0x1800ed743  or      ebx, r14d
0x1800ed746  test    ebx, ebx
0x1800ed748  js      short loc_1800ED775
0x1800ed74a  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800ed74e  lea     r9, Annotation; "LUI Service"
0x1800ed755  xor     r8d, r8d; UuidVector
0x1800ed758  lea     rcx, qword_18010A9F0; IfSpec
0x1800ed75f  call    cs:__imp_RpcEpRegisterW
0x1800ed765  mov     ebx, eax
0x1800ed767  test    eax, eax
0x1800ed769  jle     short loc_1800ED771
0x1800ed76b  movzx   ebx, ax
0x1800ed76e  or      ebx, r14d
0x1800ed771  test    ebx, ebx
0x1800ed773  jns     short loc_1800ED7A9
0x1800ed775  mov     eax, ebx
0x1800ed777  shr     eax, 1Fh
0x1800ed77a  xor     al, 1
0x1800ed77c  jz      short loc_1800ED792
0x1800ed77e  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800ed782  lea     rcx, qword_18010A9F0; IfSpec
0x1800ed789  xor     r8d, r8d; UuidVector
0x1800ed78c  call    cs:__imp_RpcEpUnregister
0x1800ed792  test    dil, dil
0x1800ed795  jz      short loc_1800ED7A9
0x1800ed797  xor     r8d, r8d; RundownContextHandles
0x1800ed79a  lea     rcx, qword_18010A9F0; IfSpec
0x1800ed7a1  xor     edx, edx; MgrTypeUuid
0x1800ed7a3  call    cs:__imp_RpcServerUnregisterIfEx
0x1800ed7a9  cmp     [rbp+57h+BindingVector], 0
0x1800ed7ae  jz      short loc_1800ED7BA
0x1800ed7b0  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x1800ed7b4  call    cs:__imp_RpcBindingVectorFree
0x1800ed7ba  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800ed7be  test    rcx, rcx
0x1800ed7c1  jz      short loc_1800ED7C9
0x1800ed7c3  call    cs:__imp_LocalFree
0x1800ed7c9  mov     eax, ebx
0x1800ed7cb  mov     rcx, [rbp+57h+var_30]
0x1800ed7cf  xor     rcx, rsp; StackCookie
0x1800ed7d2  call    __security_check_cookie
0x1800ed7d7  add     rsp, 0F8h
0x1800ed7de  pop     r14
0x1800ed7e0  pop     rdi
0x1800ed7e1  pop     rbx
0x1800ed7e2  pop     rbp
0x1800ed7e3  retn
```
