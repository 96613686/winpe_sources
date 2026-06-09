# PsmpCreateRpcBinding

- ea: `0x180005160`
- end: `0x1800052e7`
- name: `PsmpCreateRpcBinding`
- size: `391`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE IfSpec)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800050c0`

## callees

- `0x180005160`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180005219`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180005219`
- `RPCRT4!RpcBindingFree` at `0x1800052da`
- `RPCRT4!RpcBindingFree` at `0x1800052da`
- `RPCRT4!RpcBindingBind` at `0x18000529b`
- `RPCRT4!RpcBindingBind` at `0x18000529b`
- `RPCRT4!RpcBindingCreateW` at `0x180005287`
- `RPCRT4!RpcBindingCreateW` at `0x180005287`

## pseudocode

```c
__int64 __fastcall PsmpCreateRpcBinding(RPC_IF_HANDLE IfSpec, RPC_BINDING_HANDLE *a2)
{
  __int64 result; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-E0h] BYREF
  DWORD cbSid; // [rsp+28h] [rbp-D8h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v8[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v9; // [rsp+78h] [rbp-88h]
  __int64 *v10; // [rsp+88h] [rbp-78h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+90h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pSid[80]; // [rsp+E0h] [rbp-20h] BYREF

  Options.Version = 1;
  Options.Flags = 1;
  *(_QWORD *)&Options.ComTimeout = 5;
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  memset_0(pSid, 0, 0x44u);
  Binding = 0;
  cbSid = 68;
  v10 = 0;
  memset(&Security, 0, sizeof(Security));
  memset(v8, 0, sizeof(v8));
  v9 = 0;
  CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid);
  *(_QWORD *)&v8[0] = 0x100000005LL;
  *(_QWORD *)&v9 = pSid;
  v10 = PsmpSystemDescriptor;
  *((_QWORD *)&v8[0] + 1) = 0x300000001LL;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v8;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  if ( !RpcBindingCreateW(&Template, &Security, &Options, &Binding) )
  {
    if ( !RpcBindingBind(0, Binding, IfSpec) )
    {
      result = 0;
      *a2 = Binding;
      return result;
    }
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x180005160  mov     [rsp-8+arg_10], rbx
0x180005165  push    rbp
0x180005166  push    rsi
0x180005167  push    rdi
0x180005168  lea     rbp, [rsp-40h]
0x18000516d  sub     rsp, 140h
0x180005174  mov     rax, cs:__security_cookie
0x18000517b  xor     rax, rsp
0x18000517e  mov     [rbp+50h+var_20], rax
0x180005182  xorps   xmm0, xmm0
0x180005185  mov     [rbp+50h+Options.Version], 1
0x18000518c  mov     rbx, rdx
0x18000518f  mov     [rbp+50h+Options.Flags], 1
0x180005196  mov     rdi, rcx
0x180005199  mov     qword ptr [rbp+50h+Options.ComTimeout], 5
0x1800051a1  xor     eax, eax
0x1800051a3  mov     qword ptr [rbp+50h+Template.Version], 1
0x1800051ab  xor     edx, edx; Val
0x1800051ad  mov     qword ptr [rbp+50h+Template.ObjectUuid.Data4], rax
0x1800051b1  lea     rcx, [rbp+50h+pSid]; void *
0x1800051b5  mov     qword ptr [rbp+50h+Template.ProtocolSequence], 3
0x1800051bd  mov     r8d, 44h ; 'D'; Size
0x1800051c3  xor     esi, esi
0x1800051c5  movups  xmmword ptr [rbp+50h+Template.NetworkAddress], xmm0
0x1800051c9  movups  xmmword ptr [rbp+50h+Template.u1], xmm0
0x1800051cd  call    memset_0
0x1800051d2  xorps   xmm1, xmm1
0x1800051d5  mov     [rsp+150h+Binding], rsi
0x1800051da  xorps   xmm0, xmm0
0x1800051dd  mov     [rsp+150h+cbSid], 44h ; 'D'
0x1800051e5  xor     eax, eax
0x1800051e7  lea     r9, [rsp+150h+cbSid]; cbSid
0x1800051ec  lea     r8, [rbp+50h+pSid]; pSid
0x1800051f0  mov     [rsp+150h+Security.SecurityQos], rax
0x1800051f5  xor     edx, edx; DomainSid
0x1800051f7  mov     [rbp+50h+var_C8], rax
0x1800051fb  mov     ecx, 16h; WellKnownSidType
0x180005200  movups  xmmword ptr [rsp+150h+Security.Version], xmm0
0x180005205  movups  xmmword ptr [rsp+150h+Security.AuthnLevel], xmm0
0x18000520a  movups  [rsp+150h+var_F8], xmm1
0x18000520f  movups  [rsp+150h+var_E8], xmm1
0x180005214  movups  [rsp+150h+var_D8], xmm1
0x180005219  call    cs:__imp_CreateWellKnownSid
0x18000521f  lea     rax, [rbp+50h+pSid]
0x180005223  mov     dword ptr [rsp+150h+var_F8], 5
0x18000522b  mov     qword ptr [rsp+150h+var_D8], rax
0x180005230  lea     r9, [rsp+150h+Binding]; Binding
0x180005235  lea     rax, PsmpSystemDescriptor
0x18000523c  mov     dword ptr [rsp+150h+var_F8+4], 1
0x180005244  mov     [rbp+50h+var_C8], rax
0x180005248  lea     r8, [rbp+50h+Options]; Options
0x18000524c  lea     rax, [rsp+150h+var_F8]
0x180005251  mov     dword ptr [rsp+150h+var_F8+8], 1
0x180005259  lea     rdx, [rsp+150h+Security]; Security
0x18000525e  mov     [rsp+150h+Security.SecurityQos], rax
0x180005263  lea     rcx, [rbp+50h+Template]; Template
0x180005267  mov     dword ptr [rsp+150h+var_F8+0Ch], 3
0x18000526f  mov     [rsp+150h+Security.Version], 1
0x180005277  mov     [rsp+150h+Security.AuthnLevel], 6
0x18000527f  mov     [rsp+150h+Security.AuthnSvc], 14h
0x180005287  call    cs:__imp_RpcBindingCreateW
0x18000528d  test    eax, eax
0x18000528f  jnz     short loc_1800052E0
0x180005291  mov     rdx, [rsp+150h+Binding]; Binding
0x180005296  mov     r8, rdi; IfSpec
0x180005299  xor     ecx, ecx; pAsync
0x18000529b  call    cs:__imp_RpcBindingBind
0x1800052a1  test    eax, eax
0x1800052a3  jnz     short loc_1800052CE
0x1800052a5  mov     rcx, [rsp+150h+Binding]
0x1800052aa  mov     eax, esi
0x1800052ac  mov     [rbx], rcx
0x1800052af  mov     rcx, [rbp+50h+var_20]
0x1800052b3  xor     rcx, rsp; StackCookie
0x1800052b6  call    __security_check_cookie
0x1800052bb  mov     rbx, [rsp+150h+arg_10]
0x1800052c3  add     rsp, 140h
0x1800052ca  pop     rdi
0x1800052cb  pop     rsi
0x1800052cc  pop     rbp
0x1800052cd  retn
0x1800052ce  cmp     [rsp+150h+Binding], rsi
0x1800052d3  jz      short loc_1800052E0
0x1800052d5  lea     rcx, [rsp+150h+Binding]; Binding
0x1800052da  call    cs:__imp_RpcBindingFree
0x1800052e0  mov     eax, 0C0000001h
0x1800052e5  jmp     short loc_1800052AF
```
