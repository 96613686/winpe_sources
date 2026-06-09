# RegisterRPCInterface

- ea: `0x18000ad28`
- end: `0x18000af30`
- name: `RegisterRPCInterface`
- size: `520`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b720`

## callees

- `0x18000ad28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ade0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ade0`
- `RPCRT4!RpcBindingVectorFree` at `0x18000aea0`
- `RPCRT4!RpcBindingVectorFree` at `0x18000aea0`
- `RPCRT4!RpcEpRegisterW` at `0x18000ae79`
- `RPCRT4!RpcEpRegisterW` at `0x18000ae79`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000ae52`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000ae52`
- `RPCRT4!RpcServerInqBindings` at `0x18000adc0`
- `RPCRT4!RpcServerInqBindings` at `0x18000adc0`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000ada5`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000ada5`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000ad88`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000ad88`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000adeb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000af05`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000af15`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000adeb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000af05`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000af15`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ad6b`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ae0d`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ad6b`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ae0d`

## string_xrefs

- `0x18000ad5f`: `DefaultRpcAccess`

## pseudocode

```c
__int64 __fastcall RegisterRPCInterface(__int64 a1, __int64 *a2)
{
  int v4; // eax
  int v5; // r8d
  unsigned int v6; // eax
  unsigned int v7; // ebx
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // eax
  __int64 v10; // rsi
  DWORD LastError; // ebx
  int v12; // eax
  RPC_STATUS v13; // eax
  void *SecurityDescriptor; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+88h] [rbp+38h] BYREF

  v16 = 0;
  BindingVector = 0;
  SecurityDescriptor = 0;
  v4 = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", &SecurityDescriptor);
  if ( v4 < 0 )
  {
    v5 = 175;
LABEL_3:
    v6 = v4 | 0x10000000;
LABEL_4:
    v7 = ZTraceReportOriginationNoThis(v6, "RegisterRPCInterface", v5);
    goto LABEL_18;
  }
  v8 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  if ( v8 )
  {
    v6 = v8 | 0x80010000;
    v5 = 182;
    goto LABEL_4;
  }
  v9 = RpcServerInqBindings(&BindingVector);
  if ( v9 )
  {
    v6 = v9 | 0x80010000;
    v5 = 185;
    goto LABEL_4;
  }
  v10 = v16;
  if ( v16 )
  {
    LastError = GetLastError();
    FreeTransientObjectSecurityDescriptor(v10);
    SetLastError(LastError);
  }
  v16 = 0;
  v4 = QueryTransientObjectSecurityDescriptor(9, a1, &v16);
  if ( v4 < 0 )
  {
    v5 = 192;
    goto LABEL_3;
  }
  v12 = RpcServerRegisterIf3(a2, 0, 0, 41, 1234, 0, 0, v16);
  if ( v12 )
  {
    v6 = v12 | 0x80010000;
    v5 = 205;
    goto LABEL_4;
  }
  v13 = RpcEpRegisterW(a2, BindingVector, 0, 0);
  if ( v13 )
  {
    v6 = v13 | 0x80010000;
    v5 = 208;
    goto LABEL_4;
  }
  v7 = 0;
LABEL_18:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  if ( v7 == -2147024891 )
  {
    if ( a2 == qword_18000EC70 )
    {
      v7 = -2080374779;
    }
    else if ( a2 == qword_18000F500 )
    {
      v7 = -2080374755;
    }
    else if ( a2 == qword_18000F430 )
    {
      v7 = -2080374778;
    }
    else if ( a2 == qword_18000E910 )
    {
      v7 = -2080374763;
    }
    else
    {
      __int2c();
    }
  }
  if ( v16 )
    FreeTransientObjectSecurityDescriptor(v16);
  if ( SecurityDescriptor )
    FreeTransientObjectSecurityDescriptor(SecurityDescriptor);
  return v7;
}

```

## disassembly

```asm
0x18000ad28  mov     [rsp-18h+arg_0], rbx
0x18000ad2d  mov     [rsp-18h+arg_8], rsi
0x18000ad32  push    rbp
0x18000ad33  push    rdi
0x18000ad34  push    r14
0x18000ad36  mov     rbp, rsp
0x18000ad39  sub     rsp, 50h
0x18000ad3d  mov     rdi, rdx
0x18000ad40  mov     r14, rcx
0x18000ad43  mov     [rbp+arg_10], 0
0x18000ad4b  mov     [rbp+BindingVector], 0
0x18000ad53  mov     [rbp+SecurityDescriptor], 0
0x18000ad5b  lea     r8, [rbp+SecurityDescriptor]
0x18000ad5f  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x18000ad66  mov     ecx, 8
0x18000ad6b  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000ad71  test    eax, eax
0x18000ad73  jns     short loc_18000AD95
0x18000ad75  mov     r8d, 0AFh
0x18000ad7b  bts     eax, 1Ch
0x18000ad7f  lea     rdx, aRegisterrpcint; "RegisterRPCInterface"
0x18000ad86  mov     ecx, eax
0x18000ad88  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000ad8e  mov     ebx, eax
0x18000ad90  jmp     loc_18000AE95
0x18000ad95  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000ad99  mov     edx, 0Ah; MaxCalls
0x18000ad9e  lea     rcx, Protseq; "ncalrpc"
0x18000ada5  call    cs:__imp_RpcServerUseProtseqW
0x18000adab  test    eax, eax
0x18000adad  jz      short loc_18000ADBC
0x18000adaf  or      eax, 80010000h
0x18000adb4  mov     r8d, 0B6h
0x18000adba  jmp     short loc_18000AD7F
0x18000adbc  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000adc0  call    cs:__imp_RpcServerInqBindings
0x18000adc6  test    eax, eax
0x18000adc8  jz      short loc_18000ADD7
0x18000adca  or      eax, 80010000h
0x18000adcf  mov     r8d, 0B9h
0x18000add5  jmp     short loc_18000AD7F
0x18000add7  mov     rsi, [rbp+arg_10]
0x18000addb  test    rsi, rsi
0x18000adde  jz      short loc_18000ADF9
0x18000ade0  call    cs:__imp_GetLastError
0x18000ade6  mov     ebx, eax
0x18000ade8  mov     rcx, rsi
0x18000adeb  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000adf1  mov     ecx, ebx; dwErrCode
0x18000adf3  call    cs:__imp_SetLastError
0x18000adf9  mov     [rbp+arg_10], 0
0x18000ae01  lea     r8, [rbp+arg_10]
0x18000ae05  mov     rdx, r14
0x18000ae08  mov     ecx, 9
0x18000ae0d  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000ae13  test    eax, eax
0x18000ae15  jns     short loc_18000AE22
0x18000ae17  mov     r8d, 0C0h
0x18000ae1d  jmp     loc_18000AD7B
0x18000ae22  mov     rax, [rbp+arg_10]
0x18000ae26  mov     [rsp+50h+var_18], rax
0x18000ae2b  mov     [rsp+50h+var_20], 0
0x18000ae34  mov     [rsp+50h+var_28], 0
0x18000ae3c  mov     [rsp+50h+var_30], 4D2h
0x18000ae44  mov     r9d, 29h ; ')'
0x18000ae4a  xor     r8d, r8d
0x18000ae4d  xor     edx, edx
0x18000ae4f  mov     rcx, rdi
0x18000ae52  call    cs:__imp_RpcServerRegisterIf3
0x18000ae58  test    eax, eax
0x18000ae5a  jz      short loc_18000AE6C
0x18000ae5c  or      eax, 80010000h
0x18000ae61  mov     r8d, 0CDh
0x18000ae67  jmp     loc_18000AD7F
0x18000ae6c  xor     r9d, r9d; Annotation
0x18000ae6f  xor     r8d, r8d; UuidVector
0x18000ae72  mov     rdx, [rbp+BindingVector]; BindingVector
0x18000ae76  mov     rcx, rdi; IfSpec
0x18000ae79  call    cs:__imp_RpcEpRegisterW
0x18000ae7f  test    eax, eax
0x18000ae81  jz      short loc_18000AE93
0x18000ae83  or      eax, 80010000h
0x18000ae88  mov     r8d, 0D0h
0x18000ae8e  jmp     loc_18000AD7F
0x18000ae93  xor     ebx, ebx
0x18000ae95  cmp     [rbp+BindingVector], 0
0x18000ae9a  jz      short loc_18000AEA6
0x18000ae9c  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000aea0  call    cs:__imp_RpcBindingVectorFree
0x18000aea6  cmp     ebx, 80070005h
0x18000aeac  jnz     short loc_18000AEFC
0x18000aeae  lea     rax, qword_18000EC70
0x18000aeb5  cmp     rdi, rax
0x18000aeb8  jnz     short loc_18000AEC1
0x18000aeba  mov     ebx, 84000005h
0x18000aebf  jmp     short loc_18000AEFC
0x18000aec1  lea     rax, qword_18000F500
0x18000aec8  cmp     rdi, rax
0x18000aecb  jnz     short loc_18000AED4
0x18000aecd  mov     ebx, 8400001Dh
0x18000aed2  jmp     short loc_18000AEFC
0x18000aed4  lea     rax, qword_18000F430
0x18000aedb  cmp     rdi, rax
0x18000aede  jnz     short loc_18000AEE7
0x18000aee0  mov     ebx, 84000006h
0x18000aee5  jmp     short loc_18000AEFC
0x18000aee7  lea     rax, qword_18000E910
0x18000aeee  cmp     rdi, rax
0x18000aef1  jnz     short loc_18000AEFA
0x18000aef3  mov     ebx, 84000015h
0x18000aef8  jmp     short loc_18000AEFC
0x18000aefa  int     2Ch; Windows NT - assertion failure
0x18000aefc  mov     rcx, [rbp+arg_10]
0x18000af00  test    rcx, rcx
0x18000af03  jz      short loc_18000AF0C
0x18000af05  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000af0b  nop
0x18000af0c  mov     rcx, [rbp+SecurityDescriptor]
0x18000af10  test    rcx, rcx
0x18000af13  jz      short loc_18000AF1B
0x18000af15  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000af1b  mov     eax, ebx
0x18000af1d  mov     rbx, [rsp+50h+arg_0]
0x18000af22  mov     rsi, [rsp+50h+arg_8]
0x18000af27  add     rsp, 50h
0x18000af2b  pop     r14
0x18000af2d  pop     rdi
0x18000af2e  pop     rbp
0x18000af2f  retn
```
