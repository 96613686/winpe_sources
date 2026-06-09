# CEfsClientBase::CreateLocalRpcBinding(void * *)

- ea: `0x18000ade8`
- end: `0x18000af78`
- name: `?CreateLocalRpcBinding@CEfsClientBase@@IEAAKPEAPEAX@Z`
- size: `400`
- prototype: `unsigned int __fastcall(CEfsClientBase *__hidden this, void **)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000af80`
- `0x18000b1e0`
- `0x18000b424`
- `0x18000b808`
- `0x18000ba38`
- `0x18000bc88`
- `0x18000bd78`
- `0x18000bfc0`
- `0x18000c21c`

## callees

- `0x18000ade8`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000af25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000af25`
- `ntdll!RtlNtStatusToDosError` at `0x18000aecc`
- `ntdll!RtlNtStatusToDosError` at `0x18000aef5`
- `ntdll!RtlNtStatusToDosError` at `0x18000aecc`
- `ntdll!RtlNtStatusToDosError` at `0x18000aef5`
- `RPCRT4!RpcBindingFree` at `0x18000af54`
- `RPCRT4!RpcBindingFree` at `0x18000af54`
- `RPCRT4!RpcBindingBind` at `0x18000aee7`
- `RPCRT4!RpcBindingBind` at `0x18000aee7`
- `RPCRT4!RpcBindingCreateW` at `0x18000aec0`
- `RPCRT4!RpcBindingCreateW` at `0x18000aec0`

## pseudocode

```c
__int64 __fastcall CEfsClientBase::CreateLocalRpcBinding(CEfsClientBase *this, void **a2)
{
  RPC_STATUS v3; // eax
  ULONG v4; // ebx
  unsigned int i; // esi
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // edi
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-99h] BYREF
  _DWORD v12[3]; // [rsp+28h] [rbp-91h] BYREF
  __int64 v13; // [rsp+34h] [rbp-85h]
  int v14; // [rsp+3Ch] [rbp-7Dh]
  __int64 v15; // [rsp+40h] [rbp-79h]
  __int64 *v16; // [rsp+48h] [rbp-71h]
  __int64 v17; // [rsp+50h] [rbp-69h]
  __int64 v18; // [rsp+58h] [rbp-61h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+60h] [rbp-59h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+88h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+C0h] [rbp+7h] BYREF

  *(_QWORD *)&Template.Version = 1;
  *a2 = 0;
  v14 = 0;
  Binding = 0;
  v12[0] = 5;
  v16 = qword_180018760;
  *(_QWORD *)&Options.ComTimeout = 5;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v12;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  v12[1] = 17;
  v12[2] = 1;
  v13 = 3;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  *(_QWORD *)&Options.Version = 1;
  v3 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v3 )
  {
    v4 = RtlNtStatusToDosError(v3);
  }
  else
  {
    for ( i = 0; i < 3; ++i )
    {
      v6 = RpcBindingBind(0, Binding, qword_180016C60);
      v7 = v6;
      if ( !v6 )
      {
        v4 = 0;
        goto LABEL_12;
      }
      v4 = RtlNtStatusToDosError(v6);
      v8 = (unsigned int)(v7 - 1708);
      if ( (unsigned int)v8 > 0x2D || (v9 = 0x2000000CC201LL, !_bittest64(&v9, v8)) )
      {
        if ( v7 != 1460 )
          goto LABEL_13;
      }
      Sleep(0x12Cu);
    }
    if ( v4 )
      goto LABEL_13;
LABEL_12:
    *a2 = Binding;
    Binding = 0;
  }
LABEL_13:
  if ( Binding )
    RpcBindingFree(&Binding);
  return v4;
}

```

## disassembly

```asm
0x18000ade8  push    rbp
0x18000adea  push    rbx
0x18000adeb  push    rsi
0x18000adec  push    rdi
0x18000aded  push    r14
0x18000adef  push    r15
0x18000adf1  lea     rbp, [rsp-2Fh]
0x18000adf6  sub     rsp, 0E8h
0x18000adfd  mov     rax, cs:__security_cookie
0x18000ae04  xor     rax, rsp
0x18000ae07  mov     [rbp+57h+var_40], rax
0x18000ae0b  xor     r15d, r15d
0x18000ae0e  mov     qword ptr [rbp+57h+Template.Version], 1
0x18000ae16  xor     eax, eax
0x18000ae18  mov     [rdx], r15
0x18000ae1b  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x18000ae1f  lea     r9, [rsp+110h+Binding]; Binding
0x18000ae24  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x18000ae27  lea     r8, [rbp+57h+Options]; Options
0x18000ae2b  mov     [rbp+57h+var_D4], eax
0x18000ae2e  mov     r14, rdx
0x18000ae31  lea     ecx, [rax+5]
0x18000ae34  mov     [rsp+110h+Binding], r15
0x18000ae39  lea     rax, qword_180018760
0x18000ae40  mov     [rsp+110h+var_E8], ecx
0x18000ae44  mov     [rbp+57h+var_C8], rax
0x18000ae48  lea     rdx, [rbp+57h+Security]; Security
0x18000ae4c  lea     rax, [rsp+110h+var_E8]
0x18000ae51  mov     qword ptr [rbp+57h+Options.ComTimeout], rcx
0x18000ae55  xorps   xmm0, xmm0
0x18000ae58  mov     [rbp+57h+Security.SecurityQos], rax
0x18000ae5c  lea     rcx, [rbp+57h+Template]; Template
0x18000ae60  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x18000ae68  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18000ae6d  mov     qword ptr [rbp+57h+Template.u1], r15
0x18000ae71  mov     [rbp+57h+Template.ObjectUuid.Data1], r15d
0x18000ae75  mov     [rsp+110h+var_E4], 11h
0x18000ae7d  mov     [rsp+110h+var_E0], 1
0x18000ae85  mov     [rsp+110h+var_DC], 3
0x18000ae8e  mov     [rbp+57h+var_D0], r15
0x18000ae92  mov     [rbp+57h+var_C0], r15
0x18000ae96  mov     [rbp+57h+var_B8], r15
0x18000ae9a  mov     qword ptr [rbp+57h+Security.Version], 1
0x18000aea2  mov     [rbp+57h+Security.ServerPrincName], r15
0x18000aea6  mov     [rbp+57h+Security.AuthnLevel], 6
0x18000aead  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18000aeb4  mov     [rbp+57h+Security.AuthIdentity], r15
0x18000aeb8  mov     qword ptr [rbp+57h+Options.Version], 1
0x18000aec0  call    cs:__imp_RpcBindingCreateW
0x18000aec6  test    eax, eax
0x18000aec8  jz      short loc_18000AED6
0x18000aeca  mov     ecx, eax; Status
0x18000aecc  call    cs:__imp_RtlNtStatusToDosError
0x18000aed2  mov     ebx, eax
0x18000aed4  jmp     short loc_18000AF48
0x18000aed6  mov     esi, r15d
0x18000aed9  mov     rdx, [rsp+110h+Binding]; Binding
0x18000aede  lea     r8, qword_180016C60; IfSpec
0x18000aee5  xor     ecx, ecx; pAsync
0x18000aee7  call    cs:__imp_RpcBindingBind
0x18000aeed  mov     edi, eax
0x18000aeef  test    eax, eax
0x18000aef1  jz      short loc_18000AF38
0x18000aef3  mov     ecx, eax; Status
0x18000aef5  call    cs:__imp_RtlNtStatusToDosError
0x18000aefb  mov     ebx, eax
0x18000aefd  lea     eax, [rdi-6ACh]
0x18000af03  cmp     eax, 2Dh ; '-'
0x18000af06  ja      short loc_18000AF18
0x18000af08  mov     rcx, 2000000CC201h
0x18000af12  bt      rcx, rax
0x18000af16  jb      short loc_18000AF20
0x18000af18  cmp     edi, 5B4h
0x18000af1e  jnz     short loc_18000AF48
0x18000af20  mov     ecx, 12Ch; dwMilliseconds
0x18000af25  call    cs:__imp_Sleep
0x18000af2b  inc     esi
0x18000af2d  cmp     esi, 3
0x18000af30  jb      short loc_18000AED9
0x18000af32  test    ebx, ebx
0x18000af34  jz      short loc_18000AF3B
0x18000af36  jmp     short loc_18000AF48
0x18000af38  mov     ebx, r15d
0x18000af3b  mov     rax, [rsp+110h+Binding]
0x18000af40  mov     [r14], rax
0x18000af43  mov     [rsp+110h+Binding], r15
0x18000af48  cmp     [rsp+110h+Binding], r15
0x18000af4d  jz      short loc_18000AF5A
0x18000af4f  lea     rcx, [rsp+110h+Binding]; Binding
0x18000af54  call    cs:__imp_RpcBindingFree
0x18000af5a  mov     eax, ebx
0x18000af5c  mov     rcx, [rbp+57h+var_40]
0x18000af60  xor     rcx, rsp; StackCookie
0x18000af63  call    __security_check_cookie
0x18000af68  add     rsp, 0E8h
0x18000af6f  pop     r15
0x18000af71  pop     r14
0x18000af73  pop     rdi
0x18000af74  pop     rsi
0x18000af75  pop     rbx
0x18000af76  pop     rbp
0x18000af77  retn
```
