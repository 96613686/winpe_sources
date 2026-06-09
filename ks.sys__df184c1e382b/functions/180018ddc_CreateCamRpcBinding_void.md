# CreateCamRpcBinding(void * *)

- ea: `0x180018ddc`
- end: `0x180018f79`
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

- `0x180018ddc`
- `0x180019bd0`

## import_xrefs

- `ntoskrnl!SeExports` at `0x180018e8a`
- `msrpc!RpcBindingBind` at `0x180018f0a`
- `msrpc!RpcBindingBind` at `0x180018f0a`
- `msrpc!RpcBindingFree` at `0x180018f49`
- `msrpc!RpcBindingFree` at `0x180018f49`
- `msrpc!RpcBindingCreateW` at `0x180018eda`
- `msrpc!RpcBindingCreateW` at `0x180018eda`

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
  Template.ObjectUuid = (UUID)xmmword_18001D464;
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
  v4 = RpcBindingBind(0, Binding, byte_18001D460);
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
0x180018ddc  mov     [rsp-8+arg_8], rbx
0x180018de1  mov     [rsp-8+arg_10], rdi
0x180018de6  push    rbp
0x180018de7  lea     rbp, [rsp-57h]
0x180018dec  sub     rsp, 0E0h
0x180018df3  mov     rax, cs:__security_cookie
0x180018dfa  xor     rax, rsp
0x180018dfd  mov     [rbp+57h+var_10], rax
0x180018e01  xorps   xmm0, xmm0
0x180018e04  mov     [rbp+57h+Binding], 0
0x180018e0c  xor     eax, eax
0x180018e0e  mov     [rbp+57h+Template.StringEndpoint+4], 0
0x180018e16  mov     dword ptr [rbp+57h+Template.u1+4], 0
0x180018e1d  xorps   xmm1, xmm1
0x180018e20  mov     [rbp+57h+Security.SecurityQos], rax
0x180018e24  mov     rdi, rcx
0x180018e27  mov     [rbp+57h+var_60], rax
0x180018e2b  movdqu  xmmword ptr [rbp+57h+Template+0Ch], xmm0
0x180018e30  movups  xmmword ptr [rbp+57h+Options.Version], xmm0
0x180018e34  movups  xmmword ptr [rbp+57h+Security.Version], xmm1
0x180018e38  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm1
0x180018e3c  movups  [rbp+57h+var_90], xmm0
0x180018e40  movups  [rbp+57h+var_80], xmm0
0x180018e44  movups  [rbp+57h+var_70], xmm0
0x180018e48  test    rcx, rcx
0x180018e4b  jnz     short loc_180018E57
0x180018e4d  mov     ebx, 0C000000Dh
0x180018e52  jmp     loc_180018F55
0x180018e57  mov     [rcx], rax
0x180018e5a  lea     r9, [rbp+57h+Binding]; Binding
0x180018e5e  movups  xmm0, cs:xmmword_18001D464
0x180018e65  xor     ebx, ebx
0x180018e67  mov     dword ptr [rbp+57h+var_90+4], 11h
0x180018e6e  mov     dword ptr [rbp+57h+var_90+8], ebx
0x180018e71  movdqu  xmmword ptr [rbp+57h+Template.ObjectUuid.Data1], xmm0
0x180018e76  lea     r8d, [rbx+1]
0x180018e7a  lea     eax, [rbx+3]
0x180018e7d  mov     [rbp+57h+Template.Version], r8d
0x180018e81  mov     [rbp+57h+Template.ProtocolSequence], eax
0x180018e84  lea     edx, [rbx+5]
0x180018e87  mov     dword ptr [rbp+57h+var_90+0Ch], eax
0x180018e8a  mov     rax, cs:__imp_SeExports
0x180018e91  mov     [rbp+57h+Template.Flags], r8d
0x180018e95  mov     dword ptr [rbp+57h+var_90], edx
0x180018e98  mov     rcx, [rax]
0x180018e9b  mov     rax, [rcx+108h]
0x180018ea2  lea     rcx, [rbp+57h+Template]; Template
0x180018ea6  mov     qword ptr [rbp+57h+var_70], rax
0x180018eaa  lea     rax, [rbp+57h+var_90]
0x180018eae  mov     [rbp+57h+Security.Version], r8d
0x180018eb2  mov     [rbp+57h+Options.Version], r8d
0x180018eb6  lea     r8, [rbp+57h+Options]; Options
0x180018eba  mov     [rbp+57h+Options.ComTimeout], edx
0x180018ebd  lea     rdx, [rbp+57h+Security]; Security
0x180018ec1  mov     [rbp+57h+Security.SecurityQos], rax
0x180018ec5  mov     [rbp+57h+Security.AuthnLevel], 6
0x180018ecc  mov     [rbp+57h+Security.AuthnSvc], 14h
0x180018ed3  mov     [rbp+57h+Options.Flags], 2
0x180018eda  call    cs:__imp_RpcBindingCreateW
0x180018ee1  nop     dword ptr [rax+rax+00h]
0x180018ee6  test    eax, eax
0x180018ee8  jz      short loc_180018EFD
0x180018eea  jg      short loc_180018EF0
0x180018eec  mov     ebx, eax
0x180018eee  jmp     short loc_180018EF9
0x180018ef0  movzx   ebx, ax
0x180018ef3  or      ebx, 0C0070000h
0x180018ef9  test    ebx, ebx
0x180018efb  js      short loc_180018F2D
0x180018efd  mov     rdx, [rbp+57h+Binding]; Binding
0x180018f01  lea     r8, byte_18001D460; IfSpec
0x180018f08  xor     ecx, ecx; pAsync
0x180018f0a  call    cs:__imp_RpcBindingBind
0x180018f11  nop     dword ptr [rax+rax+00h]
0x180018f16  test    eax, eax
0x180018f18  jz      short loc_180018F33
0x180018f1a  jg      short loc_180018F20
0x180018f1c  mov     ebx, eax
0x180018f1e  jmp     short loc_180018F29
0x180018f20  movzx   ebx, ax
0x180018f23  or      ebx, 0C0070000h
0x180018f29  test    ebx, ebx
0x180018f2b  jns     short loc_180018F33
0x180018f2d  mov     rax, [rbp+57h+Binding]
0x180018f31  jmp     short loc_180018F40
0x180018f33  mov     rcx, [rbp+57h+Binding]
0x180018f37  xor     eax, eax
0x180018f39  mov     [rdi], rcx
0x180018f3c  mov     [rbp+57h+Binding], rax
0x180018f40  test    rax, rax
0x180018f43  jz      short loc_180018F55
0x180018f45  lea     rcx, [rbp+57h+Binding]; Binding
0x180018f49  call    cs:__imp_RpcBindingFree
0x180018f50  nop     dword ptr [rax+rax+00h]
0x180018f55  mov     eax, ebx
0x180018f57  mov     rcx, [rbp+57h+var_10]
0x180018f5b  xor     rcx, rsp; StackCookie
0x180018f5e  call    __security_check_cookie
0x180018f63  lea     r11, [rsp+0E0h+var_s0]
0x180018f6b  mov     rbx, [r11+18h]
0x180018f6f  mov     rdi, [r11+20h]
0x180018f73  mov     rsp, r11
0x180018f76  pop     rbp
0x180018f77  retn
```
