# Rpc_Shutdown

- ea: `0x180050898`
- end: `0x1800509f9`
- name: `Rpc_Shutdown`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003cfc0`

## callees

- `0x18000b130`
- `0x180046ec0`
- `0x180050898`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x180050970`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180050970`
- `RPCRT4!RpcBindingVectorFree` at `0x18005095d`
- `RPCRT4!RpcBindingVectorFree` at `0x18005095d`
- `RPCRT4!RpcEpUnregister` at `0x180050918`
- `RPCRT4!RpcEpUnregister` at `0x180050918`
- `RPCRT4!RpcServerInqBindings` at `0x1800508ff`
- `RPCRT4!RpcServerInqBindings` at `0x1800508ff`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800509a4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800509a4`

## pseudocode

```c
void Rpc_Shutdown()
{
  char v0; // al
  __int64 v1; // rdx
  unsigned int v2; // eax
  __int64 v3; // rdx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+20h] [rbp-18h] BYREF

  BindingVector = 0;
  v0 = xmmword_1800AB5A0;
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
  {
    WPP_SF_(1031, 15, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids);
    v0 = xmmword_1800AB5A0;
  }
  if ( !g_fRpcInitialized )
  {
    if ( v0 >= 0 )
      return;
    v1 = 16;
    goto LABEL_19;
  }
  v2 = RpcServerInqBindings(&BindingVector);
  if ( v2 )
  {
    if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
      goto LABEL_13;
    v3 = 18;
    goto LABEL_12;
  }
  v2 = RpcEpUnregister(qword_18008FC50, BindingVector, 0);
  if ( v2 && SBYTE3(xmmword_1800AB5A0) < 0 )
  {
    v3 = 17;
LABEL_12:
    WPP_SF_d(1055, v3, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, v2);
  }
LABEL_13:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  RpcServerUnregisterIfEx(qword_18008FC50, 0, 1);
  g_fRpcInitialized = 0;
  MIDL_user_free(g_pAccessSecurityDescriptor);
  MIDL_user_free(g_pAccessAcl);
  if ( g_pAccessOwnerSid )
  {
    FreeSid(g_pAccessOwnerSid);
    g_pAccessOwnerSid = 0;
  }
  g_pAccessSecurityDescriptor = 0;
  g_pAccessAcl = 0;
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
  {
    v1 = 19;
LABEL_19:
    WPP_SF_(1031, v1, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids);
  }
}

```

## disassembly

```asm
0x180050898  push    rdi
0x18005089a  sub     rsp, 30h
0x18005089e  mov     rax, cs:__security_cookie
0x1800508a5  xor     rax, rsp
0x1800508a8  mov     [rsp+38h+var_10], rax
0x1800508ad  mov     [rsp+38h+BindingVector], 0
0x1800508b6  mov     al, byte ptr cs:xmmword_1800AB5A0
0x1800508bc  lea     rdi, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids
0x1800508c3  test    al, al
0x1800508c5  jns     short loc_1800508DF
0x1800508c7  mov     edx, 0Fh
0x1800508cc  mov     ecx, 407h
0x1800508d1  mov     r8, rdi
0x1800508d4  call    WPP_SF_
0x1800508d9  mov     al, byte ptr cs:xmmword_1800AB5A0
0x1800508df  cmp     cs:g_fRpcInitialized, 0
0x1800508e6  jnz     short loc_1800508FA
0x1800508e8  test    al, al
0x1800508ea  jns     loc_1800509E6
0x1800508f0  mov     edx, 10h
0x1800508f5  jmp     loc_1800509D9
0x1800508fa  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x1800508ff  call    cs:__imp_RpcServerInqBindings
0x180050905  test    eax, eax
0x180050907  jnz     short loc_180050932
0x180050909  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x18005090e  lea     rcx, qword_18008FC50; IfSpec
0x180050915  xor     r8d, r8d; UuidVector
0x180050918  call    cs:__imp_RpcEpUnregister
0x18005091e  test    eax, eax
0x180050920  jz      short loc_180050950
0x180050922  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x180050929  jge     short loc_180050950
0x18005092b  mov     edx, 11h
0x180050930  jmp     short loc_180050940
0x180050932  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x180050939  jge     short loc_180050950
0x18005093b  mov     edx, 12h
0x180050940  mov     r9d, eax
0x180050943  mov     r8, rdi
0x180050946  mov     ecx, 41Fh
0x18005094b  call    WPP_SF_d
0x180050950  cmp     [rsp+38h+BindingVector], 0
0x180050956  jz      short loc_180050963
0x180050958  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x18005095d  call    cs:__imp_RpcBindingVectorFree
0x180050963  xor     edx, edx; MgrTypeUuid
0x180050965  lea     rcx, qword_18008FC50; IfSpec
0x18005096c  lea     r8d, [rdx+1]; RundownContextHandles
0x180050970  call    cs:__imp_RpcServerUnregisterIfEx
0x180050976  mov     rcx, cs:g_pAccessSecurityDescriptor; void *
0x18005097d  mov     cs:g_fRpcInitialized, 0
0x180050987  call    MIDL_user_free
0x18005098c  mov     rcx, cs:g_pAccessAcl; void *
0x180050993  call    MIDL_user_free
0x180050998  mov     rcx, cs:g_pAccessOwnerSid; pSid
0x18005099f  test    rcx, rcx
0x1800509a2  jz      short loc_1800509B5
0x1800509a4  call    cs:__imp_FreeSid
0x1800509aa  mov     cs:g_pAccessOwnerSid, 0
0x1800509b5  mov     cs:g_pAccessSecurityDescriptor, 0
0x1800509c0  mov     cs:g_pAccessAcl, 0
0x1800509cb  cmp     byte ptr cs:xmmword_1800AB5A0, 0
0x1800509d2  jge     short loc_1800509E6
0x1800509d4  mov     edx, 13h
0x1800509d9  mov     r8, rdi
0x1800509dc  mov     ecx, 407h
0x1800509e1  call    WPP_SF_
0x1800509e6  mov     rcx, [rsp+38h+var_10]
0x1800509eb  xor     rcx, rsp; StackCookie
0x1800509ee  call    __security_check_cookie
0x1800509f3  add     rsp, 30h
0x1800509f7  pop     rdi
0x1800509f8  retn
```
