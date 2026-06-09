# JITManager::CreateBinding(void *,void *,_GUID *,void * *)

- ea: `0x18055d394`
- end: `0x18055d580`
- name: `?CreateBinding@JITManager@@AEAAJPEAX0PEAU_GUID@@PEAPEAX@Z`
- size: `492`
- prototype: `__int64 __fastcall(JITManager *__hidden this, void *, void *, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18055d284`

## callees

- `0x18055d394`
- `0x1805a9e80`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18055d448`
- `msvcrt!memcpy_s` at `0x18055d448`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18055d4fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18055d4fb`
- `RPCRT4!RpcBindingBind` at `0x18055d4d4`
- `RPCRT4!RpcBindingBind` at `0x18055d4d4`
- `RPCRT4!RpcBindingCreateW` at `0x18055d49c`
- `RPCRT4!RpcBindingCreateW` at `0x18055d49c`

## pseudocode

```c
RPC_STATUS __fastcall JITManager::CreateBinding(JITManager *this, void *a2, void *a3, struct _GUID *a4, void **a5)
{
  RPC_STATUS result; // eax
  unsigned int v7; // r14d
  DWORD i; // edi
  RPC_STATUS v9; // eax
  signed int v10; // edx
  signed int v11; // eax
  DWORD v12; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-81h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+30h] [rbp-79h] BYREF
  _DWORD v15[4]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v16; // [rsp+68h] [rbp-41h]
  __int128 v17; // [rsp+78h] [rbp-31h]
  void *v18; // [rsp+88h] [rbp-21h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp-19h] BYREF

  memset(&Template, 0, sizeof(Template));
  v18 = a3;
  v15[1] = 0;
  Binding = 0;
  v15[2] = 1;
  v15[3] = 2;
  v16 = 0;
  v15[0] = 5;
  v17 = 0;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  memcpy_s(&Template.ObjectUuid, 0x10u, a4, 0x10u);
  Template.Flags = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v15;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  result = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v7 = 0;
    for ( i = 100; ; i = v12 )
    {
      v9 = RpcBindingBind(0, Binding, qword_180617670);
      v10 = v9;
      if ( !v9 )
        break;
      if ( v9 != 1753 )
        goto LABEL_15;
      if ( v7 > 0x258 )
        goto LABEL_18;
      v11 = WaitForSingleObject(a2, i);
      v10 = v11;
      if ( !v11 )
      {
        LOWORD(v10) = 1722;
LABEL_18:
        *a5 = Binding;
        return (unsigned __int16)v10 | 0x80070000;
      }
      if ( v11 != 258 )
      {
        if ( v11 > 0 )
          v10 = (unsigned __int16)v11 | 0x80070000;
LABEL_15:
        *a5 = Binding;
        if ( v10 <= 0 )
          return v10;
        return (unsigned __int16)v10 | 0x80070000;
      }
      v12 = i + 100;
      ++v7;
      if ( i >= 0x1F4 )
        v12 = i;
    }
    *a5 = Binding;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18055d394  mov     rax, rsp
0x18055d397  mov     [rax+20h], r9
0x18055d39b  mov     [rax+18h], r8
0x18055d39f  mov     [rax+10h], rdx
0x18055d3a3  mov     [rax+8], rcx
0x18055d3a7  push    rbp
0x18055d3a8  push    rsi
0x18055d3a9  push    rdi
0x18055d3aa  push    r14
0x18055d3ac  push    r15
0x18055d3ae  lea     rbp, [rax-57h]
0x18055d3b2  sub     rsp, 0D0h
0x18055d3b9  mov     rax, cs:__security_cookie
0x18055d3c0  xor     rax, rsp
0x18055d3c3  mov     [rbp+4Fh+var_30], rax
0x18055d3c7  mov     rax, [rbp+4Fh+arg_10]
0x18055d3cb  xorps   xmm0, xmm0
0x18055d3ce  mov     r8, [rbp+4Fh+Source]; Source
0x18055d3d2  xor     ecx, ecx
0x18055d3d4  mov     r15, [rbp+4Fh+hHandle]
0x18055d3d8  xorps   xmm1, xmm1
0x18055d3db  mov     rsi, [rbp+4Fh+arg_20]
0x18055d3df  movups  xmmword ptr [rbp+4Fh+Template.Version], xmm0
0x18055d3e3  lea     edx, [rcx+10h]; DestinationSize
0x18055d3e6  mov     [rbp+4Fh+var_70], rax
0x18055d3ea  xor     eax, eax
0x18055d3ec  mov     [rbp+4Fh+Security.SecurityQos], rcx
0x18055d3f0  mov     [rbp+4Fh+var_9C], ecx
0x18055d3f3  mov     r9d, edx; SourceSize
0x18055d3f6  movups  xmmword ptr [rbp+4Fh+Template.NetworkAddress], xmm0
0x18055d3fa  lea     rcx, [rbp+4Fh+Template.ObjectUuid]; Destination
0x18055d3fe  mov     [rsp+0F0h+Binding], 0
0x18055d407  movups  xmmword ptr [rbp+4Fh+Security.Version], xmm0
0x18055d40b  mov     [rbp+4Fh+var_98], 1
0x18055d412  movups  xmmword ptr [rbp+4Fh+Security.AuthnLevel], xmm0
0x18055d416  mov     [rbp+4Fh+var_94], 2
0x18055d41d  movdqu  [rbp+4Fh+var_90], xmm0
0x18055d422  mov     [rbp+4Fh+var_A0], 5
0x18055d429  movdqu  [rbp+4Fh+var_80], xmm1
0x18055d42e  mov     qword ptr [rbp+4Fh+Template.ObjectUuid.Data4], rax
0x18055d432  movups  xmmword ptr [rbp+7], xmm0
0x18055d436  mov     [rbp+4Fh+Template.Version], 1
0x18055d43d  mov     [rbp+4Fh+Template.ProtocolSequence], 3
0x18055d444  mov     [rbp+4Fh+Template.StringEndpoint], rax
0x18055d448  call    cs:__imp_memcpy_s
0x18055d44f  nop     dword ptr [rax+rax+00h]
0x18055d454  or      [rbp+4Fh+Template.Flags], 1
0x18055d458  lea     rax, [rbp+4Fh+var_A0]
0x18055d45c  lea     r9, [rsp+0F0h+Binding]; Binding
0x18055d461  mov     [rbp+4Fh+Security.SecurityQos], rax
0x18055d465  xor     r8d, r8d; Options
0x18055d468  mov     qword ptr [rbp+4Fh+Security+4], 0
0x18055d470  lea     rdx, [rbp+4Fh+Security]; Security
0x18055d474  mov     dword ptr [rbp+4Fh+Security.ServerPrincName+4], 0
0x18055d47b  lea     rcx, [rbp+4Fh+Template]; Template
0x18055d47f  mov     [rbp+4Fh+Security.AuthIdentity], 0
0x18055d487  mov     [rbp+4Fh+Security.Version], 1
0x18055d48e  mov     [rbp+4Fh+Security.AuthnLevel], 6
0x18055d495  mov     [rbp+4Fh+Security.AuthnSvc], 14h
0x18055d49c  call    cs:__imp_RpcBindingCreateW
0x18055d4a3  nop     dword ptr [rax+rax+00h]
0x18055d4a8  test    eax, eax
0x18055d4aa  jz      short loc_18055D4BF
0x18055d4ac  jle     loc_18055D564
0x18055d4b2  movzx   eax, ax
0x18055d4b5  or      eax, 80070000h
0x18055d4ba  jmp     loc_18055D564
0x18055d4bf  xor     r14d, r14d
0x18055d4c2  lea     edi, [r14+64h]
0x18055d4c6  mov     rdx, [rsp+0F0h+Binding]; Binding
0x18055d4cb  lea     r8, qword_180617670; IfSpec
0x18055d4d2  xor     ecx, ecx; pAsync
0x18055d4d4  call    cs:__imp_RpcBindingBind
0x18055d4db  nop     dword ptr [rax+rax+00h]
0x18055d4e0  mov     edx, eax
0x18055d4e2  test    eax, eax
0x18055d4e4  jz      short loc_18055D55A
0x18055d4e6  cmp     eax, 6D9h
0x18055d4eb  jnz     short loc_18055D534
0x18055d4ed  cmp     r14d, 258h
0x18055d4f4  ja      short loc_18055D550
0x18055d4f6  mov     edx, edi; dwMilliseconds
0x18055d4f8  mov     rcx, r15; hHandle
0x18055d4fb  call    cs:__imp_WaitForSingleObject
0x18055d502  nop     dword ptr [rax+rax+00h]
0x18055d507  mov     edx, eax
0x18055d509  test    eax, eax
0x18055d50b  jz      short loc_18055D54B
0x18055d50d  cmp     eax, 102h
0x18055d512  jnz     short loc_18055D527
0x18055d514  lea     eax, [rdi+64h]
0x18055d517  inc     r14d
0x18055d51a  cmp     edi, 1F4h
0x18055d520  cmovnb  eax, edi
0x18055d523  mov     edi, eax
0x18055d525  jmp     short loc_18055D4C6
0x18055d527  test    eax, eax
0x18055d529  jle     short loc_18055D534
0x18055d52b  movzx   edx, ax
0x18055d52e  or      edx, 80070000h
0x18055d534  mov     rax, [rsp+0F0h+Binding]
0x18055d539  mov     [rsi], rax
0x18055d53c  test    edx, edx
0x18055d53e  jle     short loc_18055D562
0x18055d540  movzx   edx, dx
0x18055d543  or      edx, 80070000h
0x18055d549  jmp     short loc_18055D562
0x18055d54b  mov     edx, 6BAh
0x18055d550  mov     rax, [rsp+0F0h+Binding]
0x18055d555  mov     [rsi], rax
0x18055d558  jmp     short loc_18055D540
0x18055d55a  mov     rcx, [rsp+0F0h+Binding]
0x18055d55f  mov     [rsi], rcx
0x18055d562  mov     eax, edx
0x18055d564  mov     rcx, [rbp+4Fh+var_30]
0x18055d568  xor     rcx, rsp; StackCookie
0x18055d56b  call    __security_check_cookie
0x18055d570  add     rsp, 0D0h
0x18055d577  pop     r15
0x18055d579  pop     r14
0x18055d57b  pop     rdi
0x18055d57c  pop     rsi
0x18055d57d  pop     rbp
0x18055d57e  retn
```
