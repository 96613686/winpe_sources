# DNS_RPC_HANDLE_bind

- ea: `0x140076fb0`
- end: `0x140077111`
- name: `DNS_RPC_HANDLE_bind`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140076fb0`
- `0x140077fa0`

## import_xrefs

- `msrpc!RpcBindingCreateW` at `0x140077080`
- `msrpc!RpcBindingCreateW` at `0x140077080`
- `msrpc!RpcBindingFree` at `0x1400770e0`
- `msrpc!RpcBindingFree` at `0x1400770e0`
- `msrpc!RpcBindingBind` at `0x1400770b7`
- `msrpc!RpcBindingBind` at `0x1400770b7`
- `msrpc!RpcBindingSetOption` at `0x14007709a`
- `msrpc!RpcBindingSetOption` at `0x14007709a`

## pseudocode

```c
RPC_BINDING_HANDLE DNS_RPC_HANDLE_bind()
{
  RPC_BINDING_HANDLE v0; // rbx
  RPC_BINDING_HANDLE v1; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-61h] BYREF
  _DWORD v5[4]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v6; // [rsp+60h] [rbp-29h]
  __int64 *v7; // [rsp+70h] [rbp-19h]
  __int64 v8; // [rsp+78h] [rbp-11h]
  __int64 *v9; // [rsp+80h] [rbp-9h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+88h] [rbp-1h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+C0h] [rbp+37h] BYREF

  *(_QWORD *)&Options.ComTimeout = 5;
  Binding = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v8 = 0;
  Options.Version = 1;
  memset(&Template, 0, 24);
  v0 = 0;
  Template.Version = 1;
  Template.StringEndpoint = L"DNSResolver";
  memset(&Template.u1, 0, 24);
  Template.ProtocolSequence = 3;
  v5[0] = 5;
  v9 = qword_14008F510;
  v7 = qword_14008F558;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v5;
  v6 = 0;
  Options.Flags = 1;
  v5[1] = 17;
  v5[2] = 1;
  v5[3] = 2;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  if ( RpcBindingCreateW(&Template, &Security, &Options, &Binding)
    || RpcBindingSetOption(Binding, 9u, 1u)
    || RpcBindingBind(0, Binding, qword_140085140) )
  {
    v1 = Binding;
  }
  else
  {
    v0 = Binding;
    v1 = 0;
    Binding = 0;
  }
  if ( v1 )
    RpcBindingFree(&Binding);
  return v0;
}

```

## disassembly

```asm
0x140076fb0  mov     [rsp-8+arg_0], rbx
0x140076fb5  mov     [rsp-8+arg_8], rsi
0x140076fba  push    rbp
0x140076fbb  lea     rbp, [rsp-57h]
0x140076fc0  sub     rsp, 0E0h
0x140076fc7  mov     rax, cs:__security_cookie
0x140076fce  xor     rax, rsp
0x140076fd1  mov     [rbp+57h+var_10], rax
0x140076fd5  xor     eax, eax
0x140076fd7  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x140076fdf  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x140076fe3  lea     r9, [rbp+57h+Binding]; Binding
0x140076fe7  mov     [rbp+57h+Binding], rax
0x140076feb  lea     r8, [rbp+57h+Options]; Options
0x140076fef  mov     qword ptr [rbp+57h+Security+4], rax
0x140076ff3  lea     rdx, [rbp+57h+Security]; Security
0x140076ff7  lea     esi, [rax+1]
0x140076ffa  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], eax
0x140076ffd  mov     [rbp+57h+Security.AuthIdentity], rax
0x140077001  lea     rcx, [rbp+57h+Template]; Template
0x140077005  mov     [rbp+57h+var_68], rax
0x140077009  xorps   xmm0, xmm0
0x14007700c  lea     rax, aDnsresolver; "DNSResolver"
0x140077013  mov     [rbp+57h+Options.Version], esi
0x140077016  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x14007701a  xor     ebx, ebx
0x14007701c  mov     [rbp+57h+Template.Version], esi
0x14007701f  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x140077023  mov     [rbp+57h+Template.StringEndpoint], rax
0x140077027  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x14007702b  lea     eax, [rbx+5]
0x14007702e  mov     [rbp+57h+Template.ProtocolSequence], 3
0x140077035  mov     [rbp+57h+var_90], eax
0x140077038  lea     rax, qword_14008F510
0x14007703f  mov     [rbp+57h+var_60], rax
0x140077043  lea     rax, qword_14008F558
0x14007704a  mov     [rbp+57h+var_70], rax
0x14007704e  lea     rax, [rbp+57h+var_90]
0x140077052  mov     [rbp+57h+Security.SecurityQos], rax
0x140077056  movdqu  [rbp+57h+var_80], xmm0
0x14007705b  mov     [rbp+57h+Options.Flags], esi
0x14007705e  mov     [rbp+57h+var_8C], 11h
0x140077065  mov     [rbp+57h+var_88], esi
0x140077068  mov     [rbp+57h+var_84], 2
0x14007706f  mov     [rbp+57h+Security.Version], esi
0x140077072  mov     [rbp+57h+Security.AuthnLevel], 6
0x140077079  mov     [rbp+57h+Security.AuthnSvc], 14h
0x140077080  call    cs:__imp_RpcBindingCreateW
0x140077087  nop     dword ptr [rax+rax+00h]
0x14007708c  test    eax, eax
0x14007708e  jnz     short loc_1400770D3
0x140077090  mov     rcx, [rbp+57h+Binding]; hBinding
0x140077094  lea     edx, [rbx+9]; option
0x140077097  mov     r8d, esi; optionValue
0x14007709a  call    cs:__imp_RpcBindingSetOption
0x1400770a1  nop     dword ptr [rax+rax+00h]
0x1400770a6  test    eax, eax
0x1400770a8  jnz     short loc_1400770D3
0x1400770aa  mov     rdx, [rbp+57h+Binding]; Binding
0x1400770ae  lea     r8, qword_140085140; IfSpec
0x1400770b5  xor     ecx, ecx; pAsync
0x1400770b7  call    cs:__imp_RpcBindingBind
0x1400770be  nop     dword ptr [rax+rax+00h]
0x1400770c3  test    eax, eax
0x1400770c5  jnz     short loc_1400770D3
0x1400770c7  mov     rbx, [rbp+57h+Binding]
0x1400770cb  xor     eax, eax
0x1400770cd  mov     [rbp+57h+Binding], rax
0x1400770d1  jmp     short loc_1400770D7
0x1400770d3  mov     rax, [rbp+57h+Binding]
0x1400770d7  test    rax, rax
0x1400770da  jz      short loc_1400770EC
0x1400770dc  lea     rcx, [rbp+57h+Binding]; Binding
0x1400770e0  call    cs:__imp_RpcBindingFree
0x1400770e7  nop     dword ptr [rax+rax+00h]
0x1400770ec  mov     rax, rbx
0x1400770ef  mov     rcx, [rbp+57h+var_10]
0x1400770f3  xor     rcx, rsp; StackCookie
0x1400770f6  call    __security_check_cookie
0x1400770fb  lea     r11, [rsp+0E0h+var_s0]
0x140077103  mov     rbx, [r11+10h]
0x140077107  mov     rsi, [r11+18h]
0x14007710b  mov     rsp, r11
0x14007710e  pop     rbp
0x14007710f  retn
```
