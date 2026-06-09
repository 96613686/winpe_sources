# DNS_RPC_HANDLE_bind

- ea: `0x1800ca950`
- end: `0x1800caafb`
- name: `DNS_RPC_HANDLE_bind`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18008b5f0`
- `0x1800ca950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caa60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caa60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800caac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800caac9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800caa50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800caa50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800caa37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800caa37`
- `RPCRT4!RpcBindingBind` at `0x1800caa98`
- `RPCRT4!RpcBindingBind` at `0x1800caa98`
- `RPCRT4!RpcBindingFree` at `0x1800caaac`
- `RPCRT4!RpcBindingFree` at `0x1800caaac`
- `RPCRT4!RpcBindingCreateW` at `0x1800caa1f`
- `RPCRT4!RpcBindingCreateW` at `0x1800caa1f`

## pseudocode

```c
RPC_BINDING_HANDLE DNS_RPC_HANDLE_bind()
{
  int v0; // ebx
  HANDLE CurrentThread; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-69h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-61h] BYREF
  __int64 v5; // [rsp+30h] [rbp-59h] BYREF
  int v6; // [rsp+38h] [rbp-51h]
  int v7; // [rsp+3Ch] [rbp-4Dh]
  __int128 v8; // [rsp+40h] [rbp-49h]
  __int64 *v9; // [rsp+50h] [rbp-39h]
  __int64 v10; // [rsp+58h] [rbp-31h]
  __int64 *v11; // [rsp+60h] [rbp-29h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-21h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp+7h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+C8h] [rbp+3Fh] BYREF

  *(_QWORD *)&Options.ComTimeout = 5;
  Binding = 0;
  v0 = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v10 = 0;
  TokenHandle = 0;
  memset(&Template, 0, 24);
  Template.Version = 1;
  Template.StringEndpoint = L"DNSResolver";
  v5 = 0x1100000005LL;
  v11 = qword_1800FE360;
  v9 = qword_1800FE3A8;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v5;
  memset(&Template.u1, 0, 24);
  Template.ProtocolSequence = 3;
  v8 = 0;
  Options.Version = 1;
  Options.Flags = 1;
  v6 = 1;
  v7 = 3;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  while ( RpcBindingCreateW(&Template, &Security, &Options, &Binding) )
  {
    if ( v0 )
      goto LABEL_9;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) || GetLastError() == 1008 )
      goto LABEL_9;
    v5 = 1;
    v0 = 1;
    v11 = 0;
    v9 = 0;
  }
  if ( RpcBindingBind(0, Binding, qword_1800EB130) )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return Binding;
}

```

## disassembly

```asm
0x1800ca950  mov     [rsp-8+arg_0], rbx
0x1800ca955  mov     [rsp-8+arg_8], rsi
0x1800ca95a  push    rbp
0x1800ca95b  lea     rbp, [rsp-57h]
0x1800ca960  sub     rsp, 0E0h
0x1800ca967  mov     rax, cs:__security_cookie
0x1800ca96e  xor     rax, rsp
0x1800ca971  mov     [rbp+57h+var_8], rax
0x1800ca975  xor     eax, eax
0x1800ca977  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x1800ca97f  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x1800ca983  xorps   xmm0, xmm0
0x1800ca986  mov     [rbp+57h+Binding], rax
0x1800ca98a  xor     ebx, ebx
0x1800ca98c  mov     qword ptr [rbp+57h+Security+4], rax
0x1800ca990  lea     esi, [rax+1]
0x1800ca993  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], eax
0x1800ca996  lea     ecx, [rax+3]
0x1800ca999  mov     [rbp+57h+Security.AuthIdentity], rax
0x1800ca99d  mov     [rbp+57h+var_88], rax
0x1800ca9a1  mov     [rbp+57h+TokenHandle], rax
0x1800ca9a5  lea     rax, aDnsresolver; "DNSResolver"
0x1800ca9ac  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x1800ca9b0  mov     [rbp+57h+Template.Version], esi
0x1800ca9b3  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x1800ca9b7  mov     [rbp+57h+Template.StringEndpoint], rax
0x1800ca9bb  lea     eax, [rbx+5]
0x1800ca9be  mov     dword ptr [rbp+57h+var_B0], eax
0x1800ca9c1  lea     rax, qword_1800FE360
0x1800ca9c8  mov     [rbp+57h+var_80], rax
0x1800ca9cc  lea     rax, qword_1800FE3A8
0x1800ca9d3  mov     [rbp+57h+var_90], rax
0x1800ca9d7  lea     rax, [rbp+57h+var_B0]
0x1800ca9db  mov     [rbp+57h+Security.SecurityQos], rax
0x1800ca9df  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x1800ca9e3  mov     [rbp+57h+Template.ProtocolSequence], ecx
0x1800ca9e6  movdqu  [rbp+57h+var_A0], xmm0
0x1800ca9eb  mov     [rbp+57h+Options.Version], esi
0x1800ca9ee  mov     [rbp+57h+Options.Flags], esi
0x1800ca9f1  mov     dword ptr [rbp+57h+var_B0+4], 11h
0x1800ca9f8  mov     [rbp+57h+var_A8], esi
0x1800ca9fb  mov     [rbp+57h+var_A4], ecx
0x1800ca9fe  mov     [rbp+57h+Security.Version], esi
0x1800caa01  mov     [rbp+57h+Security.AuthnLevel], 6
0x1800caa08  mov     [rbp+57h+Security.AuthnSvc], 14h
0x1800caa0f  lea     r9, [rbp+57h+Binding]; Binding
0x1800caa13  lea     r8, [rbp+57h+Options]; Options
0x1800caa17  lea     rdx, [rbp+57h+Security]; Security
0x1800caa1b  lea     rcx, [rbp+57h+Template]; Template
0x1800caa1f  call    cs:__imp_RpcBindingCreateW
0x1800caa26  nop     dword ptr [rax+rax+00h]
0x1800caa2b  test    eax, eax
0x1800caa2d  jz      short loc_1800CAA8B
0x1800caa2f  test    ebx, ebx
0x1800caa31  jnz     loc_1800CAAC0
0x1800caa37  call    cs:__imp_GetCurrentThread
0x1800caa3e  nop     dword ptr [rax+rax+00h]
0x1800caa43  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800caa47  mov     r8d, esi; OpenAsSelf
0x1800caa4a  mov     rcx, rax; ThreadHandle
0x1800caa4d  lea     edx, [rbx+8]; DesiredAccess
0x1800caa50  call    cs:__imp_OpenThreadToken
0x1800caa57  nop     dword ptr [rax+rax+00h]
0x1800caa5c  test    eax, eax
0x1800caa5e  jnz     short loc_1800CAAC0
0x1800caa60  call    cs:__imp_GetLastError
0x1800caa67  nop     dword ptr [rax+rax+00h]
0x1800caa6c  cmp     eax, 3F0h
0x1800caa71  jz      short loc_1800CAAC0
0x1800caa73  mov     [rbp+57h+var_B0], rsi
0x1800caa77  mov     ebx, esi
0x1800caa79  mov     [rbp+57h+var_80], 0
0x1800caa81  mov     [rbp+57h+var_90], 0
0x1800caa89  jmp     short loc_1800CAA0F
0x1800caa8b  mov     rdx, [rbp+57h+Binding]; Binding
0x1800caa8f  lea     r8, qword_1800EB130; IfSpec
0x1800caa96  xor     ecx, ecx; pAsync
0x1800caa98  call    cs:__imp_RpcBindingBind
0x1800caa9f  nop     dword ptr [rax+rax+00h]
0x1800caaa4  test    eax, eax
0x1800caaa6  jz      short loc_1800CAAC0
0x1800caaa8  lea     rcx, [rbp+57h+Binding]; Binding
0x1800caaac  call    cs:__imp_RpcBindingFree
0x1800caab3  nop     dword ptr [rax+rax+00h]
0x1800caab8  mov     [rbp+57h+Binding], 0
0x1800caac0  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800caac4  test    rcx, rcx
0x1800caac7  jz      short loc_1800CAAD5
0x1800caac9  call    cs:__imp_CloseHandle
0x1800caad0  nop     dword ptr [rax+rax+00h]
0x1800caad5  mov     rax, [rbp+57h+Binding]
0x1800caad9  mov     rcx, [rbp+57h+var_8]
0x1800caadd  xor     rcx, rsp; StackCookie
0x1800caae0  call    __security_check_cookie
0x1800caae5  lea     r11, [rsp+0E0h+var_s0]
0x1800caaed  mov     rbx, [r11+10h]
0x1800caaf1  mov     rsi, [r11+18h]
0x1800caaf5  mov     rsp, r11
0x1800caaf8  pop     rbp
0x1800caaf9  retn
```
