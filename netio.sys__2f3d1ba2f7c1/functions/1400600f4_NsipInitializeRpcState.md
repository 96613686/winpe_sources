# NsipInitializeRpcState

- ea: `0x1400600f4`
- end: `0x14006025a`
- name: `NsipInitializeRpcState`
- size: `358`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140060260`
- `0x1400a9d30`

## callees

- `0x140050ea4`
- `0x1400600f4`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14006022a`
- `ntoskrnl!KeInitializeEvent` at `0x14006022a`
- `ntoskrnl!SeExports` at `0x14006014b`
- `msrpc!RpcBindingCreateW` at `0x1400601cc`
- `msrpc!RpcBindingCreateW` at `0x1400601cc`

## pseudocode

```c
__int64 __fastcall NsipInitializeRpcState(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // edi
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+20h] [rbp-39h] BYREF
  int v5; // [rsp+48h] [rbp-11h] BYREF
  __int64 v6; // [rsp+4Ch] [rbp-Dh]
  int v7; // [rsp+54h] [rbp-5h]
  __int128 v8; // [rsp+58h] [rbp-1h]
  PSID SeLocalServiceSid; // [rsp+68h] [rbp+Fh]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+70h] [rbp+17h] BYREF

  SeLocalServiceSid = 0;
  LODWORD(Security.SecurityQos) = 0;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Security, 0, 32);
  v5 = 3;
  *(_QWORD *)&Template.Version = 1;
  memset(&Template.NetworkAddress, 0, 40);
  v8 = 0;
  v6 = 1;
  v7 = 2;
  SeLocalServiceSid = SeExports->SeLocalServiceSid;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v2 = RpcBindingCreateW(&Template, &Security, 0, Binding);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_96e5f86652cc3e4d3988e25c57f305f5_Traceguids, v2);
    }
    *Binding = 0;
  }
  KeInitializeEvent((PRKEVENT)(Binding + 2), SynchronizationEvent, 1u);
  return v2;
}

```

## disassembly

```asm
0x1400600f4  mov     [rsp-8+arg_8], rbx
0x1400600f9  mov     [rsp-8+arg_10], rdi
0x1400600fe  push    rbp
0x1400600ff  lea     rbp, [rsp-57h]
0x140060104  sub     rsp, 0B0h
0x14006010b  mov     rax, cs:__security_cookie
0x140060112  xor     rax, rsp
0x140060115  mov     [rbp+57h+var_8], rax
0x140060119  xor     eax, eax
0x14006011b  mov     [rbp+57h+var_48], 0
0x140060123  mov     dword ptr [rbp+57h+Security.SecurityQos], eax
0x140060126  lea     rdx, [rbp+57h+Security]; Security
0x14006012a  xorps   xmm0, xmm0
0x14006012d  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x140060135  movups  xmmword ptr [rbp+57h+Security.Version], xmm0
0x140060139  mov     rbx, rcx
0x14006013c  mov     eax, 3
0x140060141  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm0
0x140060145  mov     [rbp+57h+var_68], eax
0x140060148  mov     r9, rbx; Binding
0x14006014b  mov     rax, cs:__imp_SeExports
0x140060152  xorps   xmm1, xmm1
0x140060155  movdqu  xmmword ptr [rbp+57h+Template.ObjectUuid.Data1], xmm0
0x14006015a  mov     qword ptr [rbp+57h+Template.Version], 1
0x140060162  xor     r8d, r8d; Options
0x140060165  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x14006016a  mov     rcx, [rax]
0x14006016d  mov     qword ptr [rbp+57h+Template.u1], 0
0x140060175  movdqu  [rbp+57h+var_58], xmm1
0x14006017a  mov     [rbp+57h+var_64], 1
0x140060182  mov     [rbp+57h+var_5C], 2
0x140060189  mov     rax, [rcx+180h]
0x140060190  lea     rcx, [rbp+57h+Template]; Template
0x140060194  mov     [rbp+57h+var_48], rax
0x140060198  lea     rax, [rbp+57h+var_68]
0x14006019c  mov     [rbp+57h+Security.SecurityQos], rax
0x1400601a0  mov     qword ptr [rbp+57h+Security+4], 0
0x1400601a8  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], 0
0x1400601af  mov     [rbp+57h+Security.AuthIdentity], 0
0x1400601b7  mov     [rbp+57h+Security.Version], 1
0x1400601be  mov     [rbp+57h+Security.AuthnLevel], 6
0x1400601c5  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x1400601cc  call    cs:__imp_RpcBindingCreateW
0x1400601d3  nop     dword ptr [rax+rax+00h]
0x1400601d8  mov     edi, eax
0x1400601da  test    eax, eax
0x1400601dc  jz      short loc_14006021E
0x1400601de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400601e5  lea     rax, WPP_GLOBAL_Control
0x1400601ec  cmp     rcx, rax
0x1400601ef  jz      short loc_140060217
0x1400601f1  cmp     byte ptr [rcx+29h], 2
0x1400601f5  jb      short loc_140060217
0x1400601f7  mov     edx, [rcx+2Ch]
0x1400601fa  test    dl, 10h
0x1400601fd  jz      short loc_140060217
0x1400601ff  mov     rcx, [rcx+18h]
0x140060203  lea     r8, WPP_96e5f86652cc3e4d3988e25c57f305f5_Traceguids
0x14006020a  mov     edx, 0Bh
0x14006020f  mov     r9d, edi
0x140060212  call    WPP_SF_d
0x140060217  mov     qword ptr [rbx], 0
0x14006021e  lea     rcx, [rbx+10h]; Event
0x140060222  mov     r8b, 1; State
0x140060225  mov     edx, 1; Type
0x14006022a  call    cs:__imp_KeInitializeEvent
0x140060231  nop     dword ptr [rax+rax+00h]
0x140060236  mov     eax, edi
0x140060238  mov     rcx, [rbp+57h+var_8]
0x14006023c  xor     rcx, rsp; StackCookie
0x14006023f  call    __security_check_cookie
0x140060244  lea     r11, [rsp+0B0h+var_s0]
0x14006024c  mov     rbx, [r11+18h]
0x140060250  mov     rdi, [r11+20h]
0x140060254  mov     rsp, r11
0x140060257  pop     rbp
0x140060258  retn
```
