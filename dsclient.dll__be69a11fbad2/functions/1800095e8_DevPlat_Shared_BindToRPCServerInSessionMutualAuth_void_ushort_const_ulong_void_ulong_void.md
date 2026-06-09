# DevPlat::Shared::BindToRPCServerInSessionMutualAuth(void *,ushort const *,ulong,void * *,ulong,void *)

- ea: `0x1800095e8`
- end: `0x1800097d6`
- name: `?BindToRPCServerInSessionMutualAuth@Shared@DevPlat@@YAJPEAXPEBGKPEAPEAXK0@Z`
- size: `494`
- prototype: `__int64 __fastcall(DevPlat::Shared *this, void *, const unsigned __int16 *, RPC_BINDING_HANDLE *, void **, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cf0`
- `0x180004fb0`

## callees

- `0x180001e80`
- `0x1800095e8`
- `0x1800097dc`
- `0x180009922`
- `0x180009950`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x180009765`
- `RPCRT4!RpcBindingBind` at `0x180009765`
- `RPCRT4!RpcBindingFree` at `0x180009787`
- `RPCRT4!RpcBindingFree` at `0x180009787`
- `RPCRT4!RpcBindingCreateW` at `0x18000973c`
- `RPCRT4!RpcBindingCreateW` at `0x18000973c`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180009797`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180009797`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800096fd`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800096fd`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::BindToRPCServerInSessionMutualAuth(
        DevPlat::Shared *this,
        void *a2,
        const unsigned __int16 *a3,
        RPC_BINDING_HANDLE *a4,
        void **a5,
        __int64 a6)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rax
  RPC_STATUS v12; // eax
  bool v13; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD v17[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+3Ch] [rbp-C4h]
  int v19; // [rsp+44h] [rbp-BCh]
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-98h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26[264]; // [rsp+D0h] [rbp-30h] BYREF

  Binding = 0;
  v16 = 0;
  memset_0(v26, 0, 0x208u);
  *(_QWORD *)&Template.ProtocolSequence = 3;
  v8 = 1;
  v19 = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v17;
  *(_QWORD *)&Template.Version = 1;
  v17[0] = 5;
  v17[1] = 17;
  v17[2] = 1;
  v18 = 3;
  v20 = 0;
  v21 = a6;
  v22 = 0;
  v23 = 0;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  memset(&Template.NetworkAddress, 0, 40);
  if ( !a4 )
  {
    v9 = -2147024809;
LABEL_20:
    if ( (byte_18000FA44 & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v7,
        v8,
        L"DevPlat::Shared::BindToRPCServerInSessionMutualAuth",
        (unsigned int)v9);
    return (unsigned int)v9;
  }
  *a4 = 0;
  v9 = StringCchPrintfW(v26, 0x104u, L"%s\\Interface", L"Dssvc\\Server");
  if ( v9 >= 0 )
  {
    v10 = QueryTransientObjectSecurityDescriptor(9, v26, &v16);
    v9 = v10 | 0x10000000;
    if ( v10 >= 0 )
    {
      v11 = v16;
      goto LABEL_8;
    }
    if ( v9 == -805306316 )
    {
      v11 = 0;
      v9 = 0;
      v16 = 0;
LABEL_8:
      v23 = v11;
      v12 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
      v13 = v12 <= 0;
      if ( v12 || (v12 = RpcBindingBind(0, Binding, qword_18000B520), v13 = v12 <= 0, v12) )
      {
        if ( v13 )
          v9 = v12;
        else
          v9 = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        *a4 = Binding;
      }
      if ( v9 >= 0 )
        goto LABEL_17;
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
LABEL_17:
  v7 = v16;
  if ( v16 )
    FreeTransientObjectSecurityDescriptor();
  if ( v9 < 0 )
    goto LABEL_20;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800095e8  push    rbp
0x1800095ea  push    rbx
0x1800095eb  push    rsi
0x1800095ec  push    rdi
0x1800095ed  lea     rbp, [rsp-1F8h]
0x1800095f5  sub     rsp, 2F8h
0x1800095fc  mov     rax, cs:__security_cookie
0x180009603  xor     rax, rsp
0x180009606  mov     [rbp+210h+var_30], rax
0x18000960d  mov     rbx, qword ptr [rbp+210h+arg_28]
0x180009614  lea     rcx, [rbp+210h+var_240]; void *
0x180009618  xor     esi, esi
0x18000961a  xor     edx, edx; Val
0x18000961c  mov     r8d, 208h; Size
0x180009622  mov     [rsp+310h+Binding], rsi
0x180009627  mov     [rsp+310h+var_2E8], rsi
0x18000962c  mov     rdi, r9
0x18000962f  call    memset_0
0x180009634  xor     eax, eax
0x180009636  mov     qword ptr [rbp+210h+Template.ProtocolSequence], 3
0x18000963e  mov     qword ptr [rbp+210h+Template.ObjectUuid.Data2], rax
0x180009642  lea     edx, [rsi+1]
0x180009645  mov     dword ptr [rbp+210h+Template.ObjectUuid.Data4+4], eax
0x180009648  xorps   xmm0, xmm0
0x18000964b  mov     [rsp+310h+var_2CC], eax
0x18000964f  lea     rax, [rsp+310h+var_2E0]
0x180009654  mov     [rbp+210h+Security.SecurityQos], rax
0x180009658  mov     qword ptr [rbp+210h+Template.Version], rdx
0x18000965c  mov     qword ptr [rbp+210h+Template.u1], rsi
0x180009660  mov     [rbp+210h+Template.ObjectUuid.Data1], esi
0x180009663  mov     [rsp+310h+var_2E0], 5
0x18000966b  mov     [rsp+310h+var_2DC], 11h
0x180009673  mov     [rsp+310h+var_2D8], edx
0x180009677  mov     [rsp+310h+var_2D4], 3
0x180009680  mov     [rsp+310h+var_2C8], rsi
0x180009685  mov     [rsp+310h+var_2C0], rbx
0x18000968a  mov     [rsp+310h+var_2B8], rsi
0x18000968f  mov     [rsp+310h+var_2B0], rsi
0x180009694  mov     qword ptr [rsp+310h+Security.Version], rdx
0x180009699  mov     [rsp+310h+Security.ServerPrincName], rsi
0x18000969e  mov     [rsp+310h+Security.AuthnLevel], 6
0x1800096a6  mov     [rsp+310h+Security.AuthnSvc], 0Ah
0x1800096ae  mov     [rbp+210h+Security.AuthIdentity], rsi
0x1800096b2  movdqu  xmmword ptr [rbp+210h+Template.NetworkAddress], xmm0
0x1800096b7  test    rdi, rdi
0x1800096ba  jnz     short loc_1800096C6
0x1800096bc  mov     ebx, 80070057h
0x1800096c1  jmp     loc_1800097A1
0x1800096c6  lea     r9, aDssvcServer; "Dssvc\\Server"
0x1800096cd  mov     [rdi], rsi
0x1800096d0  lea     r8, aSInterface; "%s\\Interface"
0x1800096d7  mov     edx, 104h; unsigned __int64
0x1800096dc  lea     rcx, [rbp+210h+var_240]; unsigned __int16 *
0x1800096e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800096e5  mov     ebx, eax
0x1800096e7  test    eax, eax
0x1800096e9  js      loc_18000977B
0x1800096ef  lea     r8, [rsp+310h+var_2E8]
0x1800096f4  mov     ecx, 9
0x1800096f9  lea     rdx, [rbp+210h+var_240]
0x1800096fd  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180009703  mov     ebx, eax
0x180009705  or      ebx, 10000000h
0x18000970b  jge     short loc_180009721
0x18000970d  cmp     ebx, 0D0000034h
0x180009713  jnz     short loc_18000977B
0x180009715  mov     rax, rsi
0x180009718  mov     ebx, esi
0x18000971a  mov     [rsp+310h+var_2E8], rax
0x18000971f  jmp     short loc_180009726
0x180009721  mov     rax, [rsp+310h+var_2E8]
0x180009726  lea     r9, [rsp+310h+Binding]; Binding
0x18000972b  mov     [rsp+310h+var_2B0], rax
0x180009730  xor     r8d, r8d; Options
0x180009733  lea     rdx, [rsp+310h+Security]; Security
0x180009738  lea     rcx, [rbp+210h+Template]; Template
0x18000973c  call    cs:__imp_RpcBindingCreateW
0x180009742  test    eax, eax
0x180009744  jz      short loc_180009757
0x180009746  jg      short loc_18000974C
0x180009748  mov     ebx, eax
0x18000974a  jmp     short loc_180009777
0x18000974c  movzx   ebx, ax
0x18000974f  or      ebx, 80070000h
0x180009755  jmp     short loc_180009777
0x180009757  mov     rdx, [rsp+310h+Binding]; Binding
0x18000975c  lea     r8, qword_18000B520; IfSpec
0x180009763  xor     ecx, ecx; pAsync
0x180009765  call    cs:__imp_RpcBindingBind
0x18000976b  test    eax, eax
0x18000976d  jnz     short loc_180009746
0x18000976f  mov     rax, [rsp+310h+Binding]
0x180009774  mov     [rdi], rax
0x180009777  test    ebx, ebx
0x180009779  jns     short loc_18000978D
0x18000977b  cmp     [rsp+310h+Binding], rsi
0x180009780  jz      short loc_18000978D
0x180009782  lea     rcx, [rsp+310h+Binding]; Binding
0x180009787  call    cs:__imp_RpcBindingFree
0x18000978d  mov     rcx, [rsp+310h+var_2E8]
0x180009792  test    rcx, rcx
0x180009795  jz      short loc_18000979D
0x180009797  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000979d  test    ebx, ebx
0x18000979f  jns     short loc_1800097B9
0x1800097a1  test    cs:byte_18000FA44, 2
0x1800097a8  jz      short loc_1800097B9
0x1800097aa  mov     r9d, ebx
0x1800097ad  lea     r8, aDevplatSharedB; "DevPlat::Shared::BindToRPCServerInSessi"...
0x1800097b4  call    McTemplateU0zd_EventWriteTransfer
0x1800097b9  mov     eax, ebx
0x1800097bb  mov     rcx, [rbp+210h+var_30]
0x1800097c2  xor     rcx, rsp; StackCookie
0x1800097c5  call    __security_check_cookie
0x1800097ca  add     rsp, 2F8h
0x1800097d1  pop     rdi
0x1800097d2  pop     rsi
0x1800097d3  pop     rbx
0x1800097d4  pop     rbp
0x1800097d5  retn
```
