# CreateCamRpcBinding(void * *)

- ea: `0x180018bb4`
- end: `0x180018db7`
- name: `?CreateCamRpcBinding@@YAJPEAPEAX@Z`
- size: `515`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018804`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x180018bb4`
- `0x18001eeb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018cfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cd4`
- `RPCRT4!RpcBindingBind` at `0x180018d7d`
- `RPCRT4!RpcBindingBind` at `0x180018d7d`
- `RPCRT4!RpcBindingCreateW` at `0x180018d21`
- `RPCRT4!RpcBindingCreateW` at `0x180018d21`
- `RPCRT4!RpcBindingFree` at `0x180018cec`
- `RPCRT4!RpcBindingFree` at `0x180018d5f`
- `RPCRT4!RpcBindingFree` at `0x180018cec`
- `RPCRT4!RpcBindingFree` at `0x180018d5f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180018c83`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180018c83`

## string_xrefs

- `0x180018d3a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateCamRpcBinding(void **a1)
{
  DWORD LastError; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE v7; // [rsp+20h] [rbp-E0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-D8h] BYREF
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v12; // [rsp+64h] [rbp-9Ch]
  int v13; // [rsp+6Ch] [rbp-94h]
  __int128 v14; // [rsp+70h] [rbp-90h]
  __int128 v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+98h] [rbp-68h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE pSid[80]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v7 = 0;
  *a1 = 0;
  v16 = 0;
  memset(&Template.ProtocolSequence + 1, 0, 28);
  Options = 0;
  v14 = 0;
  v15 = 0;
  Template.Version = 1;
  Template.Flags = 1;
  memset(&Security, 0, sizeof(Security));
  Template.ProtocolSequence = 3;
  v11 = 5;
  Template.ObjectUuid = (UUID)xmmword_1800D13C4;
  v13 = 3;
  v12 = 17;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid);
  Options.ComTimeout = 5;
  *(_QWORD *)&v15 = pSid;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v11;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Options.Version = 1;
  Options.Flags = 2;
  if ( v7 )
  {
    Binding = v7;
    LastError = GetLastError();
    RpcBindingFree(&Binding);
    SetLastError(LastError);
  }
  v7 = 0;
  v3 = RpcBindingCreateW(&Template, &Security, &Options, &v7);
  if ( v3 )
  {
    v4 = 421;
  }
  else
  {
    v3 = RpcBindingBind(0, v7, byte_1800D13C0);
    if ( !v3 )
    {
      *a1 = v7;
      return 0;
    }
    v4 = 426;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v4,
         (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
         (const char *)v3,
         (unsigned int)v7);
  if ( v7 )
  {
    Binding = v7;
    RpcBindingFree(&Binding);
  }
  return v5;
}

```

## disassembly

```asm
0x180018bb4  push    rbp
0x180018bb6  push    rbx
0x180018bb7  push    rsi
0x180018bb8  push    rdi
0x180018bb9  lea     rbp, [rsp-48h]
0x180018bbe  sub     rsp, 148h
0x180018bc5  mov     rax, cs:__security_cookie
0x180018bcc  xor     rax, rsp
0x180018bcf  mov     [rbp+60h+var_30], rax
0x180018bd3  xor     eax, eax
0x180018bd5  mov     [rsp+160h+var_140], 0
0x180018bde  xorps   xmm0, xmm0
0x180018be1  mov     [rcx], rax
0x180018be4  movups  [rsp+160h+var_100], xmm0
0x180018be9  mov     [rsp+160h+Security.SecurityQos], rax
0x180018bee  mov     rdi, rcx
0x180018bf1  xorps   xmm1, xmm1
0x180018bf4  mov     [rbp+60h+var_D0], rax
0x180018bf8  mov     eax, 3
0x180018bfd  mov     [rbp+60h+Template.StringEndpoint+4], 0
0x180018c05  movdqu  xmmword ptr [rbp+60h+Template+0Ch], xmm0
0x180018c0a  xor     edx, edx; Val
0x180018c0c  lea     rcx, [rbp+60h+pSid]; void *
0x180018c10  movups  xmmword ptr [rbp+60h+Options.Version], xmm0
0x180018c14  lea     ebx, [rax+41h]
0x180018c17  mov     dword ptr [rbp+60h+Template.u1+4], 0
0x180018c1e  movups  [rsp+160h+var_F0], xmm0
0x180018c23  lea     esi, [rax+2]
0x180018c26  mov     r8d, ebx; Size
0x180018c29  movups  [rbp+60h+var_E0], xmm0
0x180018c2d  mov     [rbp+60h+Template.Version], 1
0x180018c34  movups  xmm0, cs:xmmword_1800D13C4
0x180018c3b  mov     [rbp+60h+Template.Flags], 1
0x180018c42  movups  xmmword ptr [rsp+160h+Security.Version], xmm1
0x180018c47  mov     [rbp+60h+Template.ProtocolSequence], eax
0x180018c4a  movups  xmmword ptr [rsp+160h+Security.AuthnLevel], xmm1
0x180018c4f  mov     dword ptr [rsp+160h+var_100], esi
0x180018c53  movdqu  xmmword ptr [rbp+60h+Template.ObjectUuid.Data1], xmm0
0x180018c58  mov     dword ptr [rsp+160h+var_100+8], 0
0x180018c60  mov     dword ptr [rsp+160h+var_100+0Ch], eax
0x180018c64  mov     dword ptr [rsp+160h+var_100+4], 11h
0x180018c6c  call    memset_0
0x180018c71  lea     r9, [rsp+160h+cbSid]; cbSid
0x180018c76  mov     [rsp+160h+cbSid], ebx
0x180018c7a  lea     r8, [rbp+60h+pSid]; pSid
0x180018c7e  xor     edx, edx; DomainSid
0x180018c80  lea     ecx, [rsi+11h]; WellKnownSidType
0x180018c83  call    cs:__imp_CreateWellKnownSid
0x180018c8a  nop     dword ptr [rax+rax+00h]
0x180018c8f  lea     rax, [rbp+60h+pSid]
0x180018c93  mov     [rbp+60h+Options.ComTimeout], esi
0x180018c96  mov     rsi, [rsp+160h+var_140]
0x180018c9b  mov     qword ptr [rbp+60h+var_E0], rax
0x180018c9f  lea     rax, [rsp+160h+var_100]
0x180018ca4  mov     [rsp+160h+Security.SecurityQos], rax
0x180018ca9  mov     [rsp+160h+Security.Version], 1
0x180018cb1  mov     [rsp+160h+Security.AuthnLevel], 6
0x180018cb9  mov     [rsp+160h+Security.AuthnSvc], 14h
0x180018cc1  mov     [rbp+60h+Options.Version], 1
0x180018cc8  mov     [rbp+60h+Options.Flags], 2
0x180018ccf  test    rsi, rsi
0x180018cd2  jz      short loc_180018D06
0x180018cd4  call    cs:__imp_GetLastError
0x180018cdb  nop     dword ptr [rax+rax+00h]
0x180018ce0  lea     rcx, [rsp+160h+Binding]; Binding
0x180018ce5  mov     [rsp+160h+Binding], rsi
0x180018cea  mov     ebx, eax
0x180018cec  call    cs:__imp_RpcBindingFree
0x180018cf3  nop     dword ptr [rax+rax+00h]
0x180018cf8  mov     ecx, ebx; dwErrCode
0x180018cfa  call    cs:__imp_SetLastError
0x180018d01  nop     dword ptr [rax+rax+00h]
0x180018d06  lea     r9, [rsp+160h+var_140]; Binding
0x180018d0b  mov     [rsp+160h+var_140], 0; unsigned int
0x180018d14  lea     r8, [rbp+60h+Options]; Options
0x180018d18  lea     rdx, [rsp+160h+Security]; Security
0x180018d1d  lea     rcx, [rbp+60h+Template]; Template
0x180018d21  call    cs:__imp_RpcBindingCreateW
0x180018d28  nop     dword ptr [rax+rax+00h]
0x180018d2d  test    eax, eax
0x180018d2f  jz      short loc_180018D6F
0x180018d31  mov     edx, 1A5h; void *
0x180018d36  mov     rcx, [rbp+68h]; this
0x180018d3a  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018d41  mov     r9d, eax; char *
0x180018d44  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018d49  mov     rcx, [rsp+160h+var_140]
0x180018d4e  mov     ebx, eax
0x180018d50  test    rcx, rcx
0x180018d53  jz      short loc_180018D6B
0x180018d55  mov     [rsp+160h+Binding], rcx
0x180018d5a  lea     rcx, [rsp+160h+Binding]; Binding
0x180018d5f  call    cs:__imp_RpcBindingFree
0x180018d66  nop     dword ptr [rax+rax+00h]
0x180018d6b  mov     eax, ebx
0x180018d6d  jmp     short loc_180018D9E
0x180018d6f  mov     rdx, [rsp+160h+var_140]; Binding
0x180018d74  lea     r8, byte_1800D13C0; IfSpec
0x180018d7b  xor     ecx, ecx; pAsync
0x180018d7d  call    cs:__imp_RpcBindingBind
0x180018d84  nop     dword ptr [rax+rax+00h]
0x180018d89  test    eax, eax
0x180018d8b  jz      short loc_180018D94
0x180018d8d  mov     edx, 1AAh
0x180018d92  jmp     short loc_180018D36
0x180018d94  mov     rax, [rsp+160h+var_140]
0x180018d99  mov     [rdi], rax
0x180018d9c  xor     eax, eax
0x180018d9e  mov     rcx, [rbp+60h+var_30]
0x180018da2  xor     rcx, rsp; StackCookie
0x180018da5  call    __security_check_cookie
0x180018daa  add     rsp, 148h
0x180018db1  pop     rdi
0x180018db2  pop     rsi
0x180018db3  pop     rbx
0x180018db4  pop     rbp
0x180018db5  retn
```
