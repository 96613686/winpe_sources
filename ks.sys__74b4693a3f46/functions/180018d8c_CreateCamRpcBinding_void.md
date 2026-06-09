# CreateCamRpcBinding(void * *)

- ea: `0x180018d8c`
- end: `0x180018f29`
- name: `?CreateCamRpcBinding@@YAJPEAPEAX@Z`
- size: `413`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180045030`
- `0x180045420`

## callees

- `0x180018d8c`
- `0x180019b80`

## import_xrefs

- `ntoskrnl!SeExports` at `0x180018e3a`
- `msrpc!RpcBindingBind` at `0x180018eba`
- `msrpc!RpcBindingBind` at `0x180018eba`
- `msrpc!RpcBindingFree` at `0x180018ef9`
- `msrpc!RpcBindingFree` at `0x180018ef9`
- `msrpc!RpcBindingCreateW` at `0x180018e8a`
- `msrpc!RpcBindingCreateW` at `0x180018e8a`

## pseudocode

```c
__int64 __fastcall CreateCamRpcBinding(void **a1)
{
  unsigned int v2; // ebx
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  RPC_BINDING_HANDLE v5; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-61h] BYREF
  _OWORD v9[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v10; // [rsp+70h] [rbp-19h]
  __int64 v11; // [rsp+80h] [rbp-9h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+88h] [rbp-1h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp+Fh] BYREF

  Binding = 0;
  v11 = 0;
  memset(&Template.ProtocolSequence + 1, 0, 28);
  Options = 0;
  memset(&Security, 0, sizeof(Security));
  memset(v9, 0, sizeof(v9));
  v10 = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  *a1 = 0;
  v2 = 0;
  *((_QWORD *)&v9[0] + 1) = 0x300000000LL;
  Template.ObjectUuid = (UUID)xmmword_18001D424;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Template.Flags = 1;
  *(_QWORD *)&v9[0] = 0x1100000005LL;
  *(_QWORD *)&v10 = SeExports->SeLocalSystemSid;
  Security.Version = 1;
  Options.Version = 1;
  Options.ComTimeout = 5;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v9;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Options.Flags = 2;
  v3 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v3 )
  {
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0xC0070000;
    else
      v2 = v3;
LABEL_11:
    v5 = Binding;
    goto LABEL_13;
  }
  v4 = RpcBindingBind(0, Binding, byte_18001D420);
  if ( v4 )
  {
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0xC0070000;
    else
      v2 = v4;
    goto LABEL_11;
  }
  v5 = 0;
  *a1 = Binding;
  Binding = 0;
LABEL_13:
  if ( v5 )
    RpcBindingFree(&Binding);
  return v2;
}

```

## disassembly

```asm
0x180018d8c  mov     [rsp-8+arg_8], rbx
0x180018d91  mov     [rsp-8+arg_10], rdi
0x180018d96  push    rbp
0x180018d97  lea     rbp, [rsp-57h]
0x180018d9c  sub     rsp, 0E0h
0x180018da3  mov     rax, cs:__security_cookie
0x180018daa  xor     rax, rsp
0x180018dad  mov     [rbp+57h+var_10], rax
0x180018db1  xorps   xmm0, xmm0
0x180018db4  mov     [rbp+57h+Binding], 0
0x180018dbc  xor     eax, eax
0x180018dbe  mov     [rbp+57h+Template.StringEndpoint+4], 0
0x180018dc6  mov     dword ptr [rbp+57h+Template.u1+4], 0
0x180018dcd  xorps   xmm1, xmm1
0x180018dd0  mov     [rbp+57h+Security.SecurityQos], rax
0x180018dd4  mov     rdi, rcx
0x180018dd7  mov     [rbp+57h+var_60], rax
0x180018ddb  movdqu  xmmword ptr [rbp+57h+Template+0Ch], xmm0
0x180018de0  movups  xmmword ptr [rbp+57h+Options.Version], xmm0
0x180018de4  movups  xmmword ptr [rbp+57h+Security.Version], xmm1
0x180018de8  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm1
0x180018dec  movups  [rbp+57h+var_90], xmm0
0x180018df0  movups  [rbp+57h+var_80], xmm0
0x180018df4  movups  [rbp+57h+var_70], xmm0
0x180018df8  test    rcx, rcx
0x180018dfb  jnz     short loc_180018E07
0x180018dfd  mov     ebx, 0C000000Dh
0x180018e02  jmp     loc_180018F05
0x180018e07  mov     [rcx], rax
0x180018e0a  lea     r9, [rbp+57h+Binding]; Binding
0x180018e0e  movups  xmm0, cs:xmmword_18001D424
0x180018e15  xor     ebx, ebx
0x180018e17  mov     dword ptr [rbp+57h+var_90+4], 11h
0x180018e1e  mov     dword ptr [rbp+57h+var_90+8], ebx
0x180018e21  movdqu  xmmword ptr [rbp+57h+Template.ObjectUuid.Data1], xmm0
0x180018e26  lea     r8d, [rbx+1]
0x180018e2a  lea     eax, [rbx+3]
0x180018e2d  mov     [rbp+57h+Template.Version], r8d
0x180018e31  mov     [rbp+57h+Template.ProtocolSequence], eax
0x180018e34  lea     edx, [rbx+5]
0x180018e37  mov     dword ptr [rbp+57h+var_90+0Ch], eax
0x180018e3a  mov     rax, cs:__imp_SeExports
0x180018e41  mov     [rbp+57h+Template.Flags], r8d
0x180018e45  mov     dword ptr [rbp+57h+var_90], edx
0x180018e48  mov     rcx, [rax]
0x180018e4b  mov     rax, [rcx+108h]
0x180018e52  lea     rcx, [rbp+57h+Template]; Template
0x180018e56  mov     qword ptr [rbp+57h+var_70], rax
0x180018e5a  lea     rax, [rbp+57h+var_90]
0x180018e5e  mov     [rbp+57h+Security.Version], r8d
0x180018e62  mov     [rbp+57h+Options.Version], r8d
0x180018e66  lea     r8, [rbp+57h+Options]; Options
0x180018e6a  mov     [rbp+57h+Options.ComTimeout], edx
0x180018e6d  lea     rdx, [rbp+57h+Security]; Security
0x180018e71  mov     [rbp+57h+Security.SecurityQos], rax
0x180018e75  mov     [rbp+57h+Security.AuthnLevel], 6
0x180018e7c  mov     [rbp+57h+Security.AuthnSvc], 14h
0x180018e83  mov     [rbp+57h+Options.Flags], 2
0x180018e8a  call    cs:__imp_RpcBindingCreateW
0x180018e91  nop     dword ptr [rax+rax+00h]
0x180018e96  test    eax, eax
0x180018e98  jz      short loc_180018EAD
0x180018e9a  jg      short loc_180018EA0
0x180018e9c  mov     ebx, eax
0x180018e9e  jmp     short loc_180018EA9
0x180018ea0  movzx   ebx, ax
0x180018ea3  or      ebx, 0C0070000h
0x180018ea9  test    ebx, ebx
0x180018eab  js      short loc_180018EDD
0x180018ead  mov     rdx, [rbp+57h+Binding]; Binding
0x180018eb1  lea     r8, byte_18001D420; IfSpec
0x180018eb8  xor     ecx, ecx; pAsync
0x180018eba  call    cs:__imp_RpcBindingBind
0x180018ec1  nop     dword ptr [rax+rax+00h]
0x180018ec6  test    eax, eax
0x180018ec8  jz      short loc_180018EE3
0x180018eca  jg      short loc_180018ED0
0x180018ecc  mov     ebx, eax
0x180018ece  jmp     short loc_180018ED9
0x180018ed0  movzx   ebx, ax
0x180018ed3  or      ebx, 0C0070000h
0x180018ed9  test    ebx, ebx
0x180018edb  jns     short loc_180018EE3
0x180018edd  mov     rax, [rbp+57h+Binding]
0x180018ee1  jmp     short loc_180018EF0
0x180018ee3  mov     rcx, [rbp+57h+Binding]
0x180018ee7  xor     eax, eax
0x180018ee9  mov     [rdi], rcx
0x180018eec  mov     [rbp+57h+Binding], rax
0x180018ef0  test    rax, rax
0x180018ef3  jz      short loc_180018F05
0x180018ef5  lea     rcx, [rbp+57h+Binding]; Binding
0x180018ef9  call    cs:__imp_RpcBindingFree
0x180018f00  nop     dword ptr [rax+rax+00h]
0x180018f05  mov     eax, ebx
0x180018f07  mov     rcx, [rbp+57h+var_10]
0x180018f0b  xor     rcx, rsp; StackCookie
0x180018f0e  call    __security_check_cookie
0x180018f13  lea     r11, [rsp+0E0h+var_s0]
0x180018f1b  mov     rbx, [r11+18h]
0x180018f1f  mov     rdi, [r11+20h]
0x180018f23  mov     rsp, r11
0x180018f26  pop     rbp
0x180018f27  retn
```
