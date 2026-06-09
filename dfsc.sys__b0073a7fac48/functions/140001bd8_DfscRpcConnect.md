# DfscRpcConnect

- ea: `0x140001bd8`
- end: `0x140001df2`
- name: `DfscRpcConnect`
- size: `538`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000193c`
- `0x140005520`
- `0x1400057c4`
- `0x140005a70`

## callees

- `0x140001bd8`
- `0x1400027f8`
- `0x140005f70`

## import_xrefs

- `msrpc!RpcBindingCreateW` at `0x140001ca8`
- `msrpc!RpcBindingCreateW` at `0x140001ca8`
- `msrpc!RpcBindingBind` at `0x140001d08`
- `msrpc!RpcBindingBind` at `0x140001d08`
- `msrpc!I_RpcExceptionFilter` at `0x1400068d5`
- `msrpc!I_RpcExceptionFilter` at `0x1400068d5`
- `msrpc!RpcBindingFree` at `0x140001d57`
- `msrpc!RpcBindingFree` at `0x140001dbe`
- `msrpc!RpcBindingFree` at `0x140001d57`
- `msrpc!RpcBindingFree` at `0x140001dbe`

## pseudocode

```c
__int64 __fastcall DfscRpcConnect(RPC_BINDING_HANDLE *a1)
{
  unsigned int v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-E0h] BYREF
  unsigned int v5; // [rsp+30h] [rbp-D8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v7[4]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v8; // [rsp+70h] [rbp-98h]
  __int64 *v9; // [rsp+80h] [rbp-88h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v10; // [rsp+88h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v11; // [rsp+C0h] [rbp-48h] BYREF

  Binding = 0;
  *a1 = 0;
  *(_QWORD *)&v10.ProtocolSequence = 3;
  *(_QWORD *)&v10.Version = 1;
  memset(&v10.NetworkAddress, 0, 40);
  v8 = 0;
  v7[0] = 3;
  v7[1] = 1;
  v7[2] = 1;
  v7[3] = 3;
  v9 = NetworkService;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v7;
  *(_QWORD *)&v11.Version = 0x100000001LL;
  *(_QWORD *)&v11.ComTimeout = 5;
  v2 = RpcBindingCreateW(&v10, &Security, &v11, &Binding);
  v5 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v2);
    }
  }
  else
  {
    v2 = RpcBindingBind(0, Binding, qword_140008030);
    v5 = v2;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v2);
      }
      RpcBindingFree(&Binding);
      Binding = 0;
    }
    else
    {
      *a1 = Binding;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140001bd8  mov     r11, rsp
0x140001bdb  push    rbx
0x140001bdc  push    rsi
0x140001bdd  push    rdi
0x140001bde  push    r14
0x140001be0  sub     rsp, 0E8h
0x140001be7  mov     rax, cs:__security_cookie
0x140001bee  xor     rax, rsp
0x140001bf1  mov     [rsp+108h+var_38], rax
0x140001bf9  mov     rdi, rcx
0x140001bfc  xor     esi, esi
0x140001bfe  mov     [rsp+108h+var_E8], esi
0x140001c02  mov     [rsp+108h+Binding], rsi
0x140001c07  mov     [rcx], rsi
0x140001c0a  mov     qword ptr [r11-78h], 3
0x140001c12  xorps   xmm0, xmm0
0x140001c15  movdqu  xmmword ptr [r11-58h], xmm0
0x140001c1b  lea     r14d, [rsi+1]
0x140001c1f  mov     [r11-80h], r14
0x140001c23  lea     eax, [rsi+3]
0x140001c26  movdqu  xmmword ptr [r11-70h], xmm0
0x140001c2c  mov     [r11-60h], rsi
0x140001c30  xorps   xmm1, xmm1
0x140001c33  movdqu  [rsp+108h+var_98], xmm1
0x140001c39  mov     [rsp+108h+var_A8], eax
0x140001c3d  mov     [rsp+108h+var_A4], r14d
0x140001c42  mov     [rsp+108h+var_A0], r14d
0x140001c47  mov     [rsp+108h+var_9C], eax
0x140001c4b  lea     rax, NetworkService
0x140001c52  mov     [r11-88h], rax
0x140001c59  mov     qword ptr [rsp+108h+Security+4], rsi
0x140001c5e  mov     dword ptr [rsp+108h+Security.ServerPrincName+4], esi
0x140001c62  mov     [rsp+108h+Security.AuthIdentity], rsi
0x140001c67  mov     [rsp+108h+Security.Version], r14d
0x140001c6c  mov     [rsp+108h+Security.AuthnLevel], 6
0x140001c74  mov     [rsp+108h+Security.AuthnSvc], 0Ah
0x140001c7c  lea     rax, [rsp+108h+var_A8]
0x140001c81  mov     [rsp+108h+Security.SecurityQos], rax
0x140001c86  mov     [r11-48h], r14d
0x140001c8a  mov     [r11-44h], r14d
0x140001c8e  mov     qword ptr [r11-40h], 5
0x140001c96  lea     r9, [rsp+108h+Binding]; Binding
0x140001c9b  lea     r8, [r11-48h]; Options
0x140001c9f  lea     rdx, [rsp+108h+Security]; Security
0x140001ca4  lea     rcx, [r11-80h]; Template
0x140001ca8  call    cs:__imp_RpcBindingCreateW
0x140001caf  nop     dword ptr [rax+rax+00h]
0x140001cb4  mov     ebx, eax
0x140001cb6  mov     [rsp+108h+var_D8], eax
0x140001cba  test    eax, eax
0x140001cbc  jz      short loc_140001CF5
0x140001cbe  lea     rax, WPP_GLOBAL_Control
0x140001cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ccc  cmp     rcx, rax
0x140001ccf  jz      short loc_140001CF0
0x140001cd1  test    dword ptr [rcx+2Ch], 100000h
0x140001cd8  jz      short loc_140001CF0
0x140001cda  lea     edx, [rsi+0Ah]
0x140001cdd  mov     r9d, ebx
0x140001ce0  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001ce7  mov     rcx, [rcx+18h]
0x140001ceb  call    WPP_SF_D
0x140001cf0  jmp     loc_140001DD2
0x140001cf5  mov     [rsp+108h+var_E8], r14d
0x140001cfa  lea     r8, qword_140008030; IfSpec
0x140001d01  mov     rdx, [rsp+108h+Binding]; Binding
0x140001d06  xor     ecx, ecx; pAsync
0x140001d08  call    cs:__imp_RpcBindingBind
0x140001d0f  nop     dword ptr [rax+rax+00h]
0x140001d14  mov     ebx, eax
0x140001d16  mov     [rsp+108h+var_D8], eax
0x140001d1a  test    eax, eax
0x140001d1c  jz      short loc_140001D6E
0x140001d1e  lea     rax, WPP_GLOBAL_Control
0x140001d25  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d2c  cmp     rcx, rax
0x140001d2f  jz      short loc_140001D52
0x140001d31  test    dword ptr [rcx+2Ch], 100000h
0x140001d38  jz      short loc_140001D52
0x140001d3a  mov     edx, 0Bh
0x140001d3f  mov     r9d, ebx
0x140001d42  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001d49  mov     rcx, [rcx+18h]
0x140001d4d  call    WPP_SF_D
0x140001d52  lea     rcx, [rsp+108h+Binding]; Binding
0x140001d57  call    cs:__imp_RpcBindingFree
0x140001d5e  nop     dword ptr [rax+rax+00h]
0x140001d63  mov     [rsp+108h+Binding], rsi
0x140001d68  mov     [rsp+108h+var_E8], esi
0x140001d6c  jmp     short loc_140001DD2
0x140001d6e  mov     rax, [rsp+108h+Binding]
0x140001d73  mov     [rdi], rax
0x140001d76  jmp     short loc_140001DD2
0x140001d78  mov     ebx, eax
0x140001d7a  mov     [rsp+108h+var_D8], eax
0x140001d7e  lea     rax, WPP_GLOBAL_Control
0x140001d85  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d8c  cmp     rcx, rax
0x140001d8f  jz      short loc_140001DB2
0x140001d91  test    dword ptr [rcx+2Ch], 100000h
0x140001d98  jz      short loc_140001DB2
0x140001d9a  mov     edx, 0Ch
0x140001d9f  mov     r9d, ebx
0x140001da2  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001da9  mov     rcx, [rcx+18h]
0x140001dad  call    WPP_SF_D
0x140001db2  cmp     [rsp+108h+var_E8], 0
0x140001db7  jz      short loc_140001DD2
0x140001db9  lea     rcx, [rsp+108h+Binding]; Binding
0x140001dbe  call    cs:__imp_RpcBindingFree
0x140001dc5  nop     dword ptr [rax+rax+00h]
0x140001dca  mov     [rsp+108h+var_E8], 0
0x140001dd2  mov     eax, ebx
0x140001dd4  mov     rcx, [rsp+108h+var_38]
0x140001ddc  xor     rcx, rsp; StackCookie
0x140001ddf  call    __security_check_cookie
0x140001de4  add     rsp, 0E8h
0x140001deb  pop     r14
0x140001ded  pop     rdi
0x140001dee  pop     rsi
0x140001def  pop     rbx
0x140001df0  retn
0x1400068c7  push    rbp
0x1400068c9  sub     rsp, 20h
0x1400068cd  mov     rbp, rdx
0x1400068d0  mov     rcx, [rcx]
0x1400068d3  mov     ecx, [rcx]; ExceptionCode
0x1400068d5  call    cs:__imp_I_RpcExceptionFilter
0x1400068dc  nop     dword ptr [rax+rax+00h]
0x1400068e1  nop
0x1400068e2  add     rsp, 20h
0x1400068e6  pop     rbp
0x1400068e7  retn
```
