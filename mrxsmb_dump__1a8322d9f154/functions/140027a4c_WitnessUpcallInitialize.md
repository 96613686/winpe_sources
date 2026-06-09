# WitnessUpcallInitialize

- ea: `0x140027a4c`
- end: `0x140027c85`
- name: `WitnessUpcallInitialize`
- size: `569`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x140027a4c`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140027ad0`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140027ad0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027abd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027abd`
- `msrpc!RpcBindingFree` at `0x140027bf7`
- `msrpc!RpcBindingFree` at `0x140027c42`
- `msrpc!RpcBindingFree` at `0x140027bf7`
- `msrpc!RpcBindingFree` at `0x140027c42`
- `msrpc!I_RpcExceptionFilter` at `0x14005a890`
- `msrpc!I_RpcExceptionFilter` at `0x14005a890`
- `msrpc!RpcBindingBind` at `0x140027bda`
- `msrpc!RpcBindingBind` at `0x140027bda`
- `msrpc!RpcBindingCreateW` at `0x140027bac`
- `msrpc!RpcBindingCreateW` at `0x140027bac`

## pseudocode

```c
__int64 WitnessUpcallInitialize()
{
  unsigned int v0; // ebx
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-C0h] BYREF
  _QWORD v3[2]; // [rsp+50h] [rbp-98h] BYREF
  __int128 v4; // [rsp+60h] [rbp-88h]
  __int64 *v5; // [rsp+70h] [rbp-78h]
  UNICODE_STRING v6; // [rsp+78h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+88h] [rbp-60h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+C0h] [rbp-28h] BYREF

  memset(&Template, 0, sizeof(Template));
  Options = 0;
  v6 = 0;
  RtlInitUnicodeString(&v6, L"ncalrpc");
  ExInitializeRundownProtection(&WitnessRundownLock);
  *(_QWORD *)&Template.ProtocolSequence = 3;
  *(_QWORD *)&Template.Version = 1;
  memset(&Template.NetworkAddress, 0, 40);
  v4 = 0;
  v3[0] = 0x100000003LL;
  v3[1] = 0x300000001LL;
  v5 = NetworkServiceAcct;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v3;
  Options.Version = 1;
  Options.Flags = 1;
  *(_QWORD *)&Options.ComTimeout = 5;
  v0 = RpcBindingCreateW(&Template, &Security, &Options, &WitnessRpcBindingHandle);
  if ( !v0 )
  {
    v0 = RpcBindingBind(0, WitnessRpcBindingHandle, qword_140061C10);
    if ( v0 )
    {
      RpcBindingFree(&WitnessRpcBindingHandle);
      WitnessRpcBindingHandle = 0;
    }
    else
    {
      WitnessUpcallInitialized = 1;
      WitnessCCFreeFunc = (__int64)MRxSmbWitnessFreePoolWithTag;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140027a4c  mov     r11, rsp
0x140027a4f  mov     [r11+8], rbx
0x140027a53  push    rsi
0x140027a54  sub     rsp, 0E0h
0x140027a5b  mov     rax, cs:__security_cookie
0x140027a62  xor     rax, rsp
0x140027a65  mov     [rsp+0E8h+var_18], rax
0x140027a6d  xorps   xmm0, xmm0
0x140027a70  xor     eax, eax
0x140027a72  movups  xmmword ptr [r11-60h], xmm0
0x140027a77  movups  xmmword ptr [r11-50h], xmm0
0x140027a7c  movups  xmmword ptr [r11-40h], xmm0
0x140027a81  mov     [r11-30h], rax
0x140027a85  movups  xmmword ptr [rsp+0E8h+Security.Version], xmm0
0x140027a8a  movups  xmmword ptr [rsp+0E8h+Security.AuthnLevel], xmm0
0x140027a8f  mov     dword ptr [rsp+0E8h+Security.SecurityQos], eax
0x140027a93  movups  xmmword ptr [r11-28h], xmm0
0x140027a98  mov     [rsp+0E8h+var_C8], eax
0x140027a9c  movups  [rsp+0E8h+var_70], xmm0
0x140027aa1  xorps   xmm1, xmm1
0x140027aa4  movups  [rsp+0E8h+var_98], xmm1
0x140027aa9  movups  [rsp+0E8h+var_88], xmm1
0x140027aae  mov     [r11-78h], rax
0x140027ab2  lea     rdx, aNcalrpc; "ncalrpc"
0x140027ab9  lea     rcx, [r11-70h]; DestinationString
0x140027abd  call    cs:__imp_RtlInitUnicodeString
0x140027ac4  nop     dword ptr [rax+rax+00h]
0x140027ac9  lea     rcx, WitnessRundownLock; RunRef
0x140027ad0  call    cs:__imp_ExInitializeRundownProtection
0x140027ad7  nop     dword ptr [rax+rax+00h]
0x140027adc  mov     qword ptr [rsp+0E8h+Template.ProtocolSequence], 3
0x140027ae8  xorps   xmm0, xmm0
0x140027aeb  movdqu  xmmword ptr [rsp+0E8h+Template.ObjectUuid.Data1], xmm0
0x140027af4  mov     esi, 1
0x140027af9  mov     qword ptr [rsp+0E8h+Template.Version], rsi
0x140027b01  lea     eax, [rsi+2]
0x140027b04  movdqu  xmmword ptr [rsp+0E8h+Template.NetworkAddress], xmm0
0x140027b0d  mov     qword ptr [rsp+0E8h+Template.u1], 0
0x140027b19  xorps   xmm1, xmm1
0x140027b1c  movdqu  [rsp+0E8h+var_88], xmm1
0x140027b22  mov     dword ptr [rsp+0E8h+var_98], eax
0x140027b26  mov     dword ptr [rsp+0E8h+var_98+4], esi
0x140027b2a  mov     dword ptr [rsp+0E8h+var_98+8], esi
0x140027b2e  mov     dword ptr [rsp+0E8h+var_98+0Ch], eax
0x140027b32  lea     rax, NetworkServiceAcct
0x140027b39  mov     [rsp+0E8h+var_78], rax
0x140027b3e  mov     qword ptr [rsp+0E8h+Security+4], 0
0x140027b47  mov     dword ptr [rsp+0E8h+Security.ServerPrincName+4], 0
0x140027b4f  mov     [rsp+0E8h+Security.AuthIdentity], 0
0x140027b58  mov     [rsp+0E8h+Security.Version], esi
0x140027b5c  mov     [rsp+0E8h+Security.AuthnLevel], 6
0x140027b64  mov     [rsp+0E8h+Security.AuthnSvc], 0Ah
0x140027b6c  lea     rax, [rsp+0E8h+var_98]
0x140027b71  mov     [rsp+0E8h+Security.SecurityQos], rax
0x140027b76  mov     [rsp+0E8h+Options.Version], esi
0x140027b7d  mov     [rsp+0E8h+Options.Flags], esi
0x140027b84  mov     qword ptr [rsp+0E8h+Options.ComTimeout], 5
0x140027b90  lea     r9, WitnessRpcBindingHandle; Binding
0x140027b97  lea     r8, [rsp+0E8h+Options]; Options
0x140027b9f  lea     rdx, [rsp+0E8h+Security]; Security
0x140027ba4  lea     rcx, [rsp+0E8h+Template]; Template
0x140027bac  call    cs:__imp_RpcBindingCreateW
0x140027bb3  nop     dword ptr [rax+rax+00h]
0x140027bb8  mov     ebx, eax
0x140027bba  mov     [rsp+0E8h+var_C4], eax
0x140027bbe  test    eax, eax
0x140027bc0  jnz     loc_140027C61
0x140027bc6  mov     [rsp+0E8h+var_C8], esi
0x140027bca  lea     r8, qword_140061C10; IfSpec
0x140027bd1  mov     rdx, cs:WitnessRpcBindingHandle; Binding
0x140027bd8  xor     ecx, ecx; pAsync
0x140027bda  call    cs:__imp_RpcBindingBind
0x140027be1  nop     dword ptr [rax+rax+00h]
0x140027be6  mov     ebx, eax
0x140027be8  mov     [rsp+0E8h+var_C4], eax
0x140027bec  test    eax, eax
0x140027bee  jz      short loc_140027C18
0x140027bf0  lea     rcx, WitnessRpcBindingHandle; Binding
0x140027bf7  call    cs:__imp_RpcBindingFree
0x140027bfe  nop     dword ptr [rax+rax+00h]
0x140027c03  mov     cs:WitnessRpcBindingHandle, 0
0x140027c0e  mov     [rsp+0E8h+var_C8], 0
0x140027c16  jmp     short loc_140027C61
0x140027c18  mov     cs:WitnessUpcallInitialized, esi
0x140027c1e  lea     rax, MRxSmbWitnessFreePoolWithTag
0x140027c25  mov     cs:WitnessCCFreeFunc, rax
0x140027c2c  jmp     short loc_140027C61
0x140027c2e  mov     ebx, eax
0x140027c30  mov     [rsp+0E8h+var_C4], eax
0x140027c34  cmp     [rsp+0E8h+var_C8], 0
0x140027c39  jz      short loc_140027C61
0x140027c3b  lea     rcx, WitnessRpcBindingHandle; Binding
0x140027c42  call    cs:__imp_RpcBindingFree
0x140027c49  nop     dword ptr [rax+rax+00h]
0x140027c4e  mov     cs:WitnessRpcBindingHandle, 0
0x140027c59  mov     [rsp+0E8h+var_C8], 0
0x140027c61  mov     eax, ebx
0x140027c63  mov     rcx, [rsp+0E8h+var_18]
0x140027c6b  xor     rcx, rsp; StackCookie
0x140027c6e  call    __security_check_cookie
0x140027c73  mov     rbx, [rsp+0E8h+arg_0]
0x140027c7b  add     rsp, 0E0h
0x140027c82  pop     rsi
0x140027c83  retn
0x14005a882  push    rbp
0x14005a884  sub     rsp, 20h
0x14005a888  mov     rbp, rdx
0x14005a88b  mov     rcx, [rcx]
0x14005a88e  mov     ecx, [rcx]; ExceptionCode
0x14005a890  call    cs:__imp_I_RpcExceptionFilter
0x14005a897  nop     dword ptr [rax+rax+00h]
0x14005a89c  nop
0x14005a89d  add     rsp, 20h
0x14005a8a1  pop     rbp
0x14005a8a2  retn
```
