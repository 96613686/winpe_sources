# Pku2uUnmarshalTokenSecurityCapabilitiesBuffer(uchar *,ulong,_SECURITY_CAPABILITIES * *)

- ea: `0x18003ac00`
- end: `0x18003acf6`
- name: `?Pku2uUnmarshalTokenSecurityCapabilitiesBuffer@@YAJPEAEKPEAPEAU_SECURITY_CAPABILITIES@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(char *, unsigned int, struct _SECURITY_CAPABILITIES **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039f20`

## callees

- `0x1800057f0`
- `0x180038a70`
- `0x180038c58`
- `0x18003ac00`
- `0x180044d98`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18003ac30`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18003ac30`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003ac38`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003ac38`

## pseudocode

```c
__int64 __fastcall Pku2uUnmarshalTokenSecurityCapabilitiesBuffer(
        char *a1,
        unsigned int a2,
        struct _SECURITY_CAPABILITIES **a3)
{
  RPC_STATUS v4; // eax
  int v5; // ebx
  void *v6; // rcx
  void *v7; // rcx
  void *v9; // [rsp+20h] [rbp-30h] BYREF
  handle_t pHandle; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v11[4]; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+78h] [rbp+28h] BYREF

  v12 = 0;
  v9 = 0;
  pHandle = 0;
  v4 = MesDecodeBufferHandleCreate(a1, a2, &pHandle);
  v5 = I_RpcMapWin32Status(v4);
  v12 = v5;
  if ( v5 >= 0 )
  {
    v11[0] = &pHandle;
    v11[1] = &v9;
    v11[2] = &v12;
    lambda_b761cd282be3ad407bc9c9412ad8a7c2_::operator()(v11);
    v5 = v12;
    if ( v12 >= 0 )
    {
      if ( v9 )
      {
        *a3 = (struct _SECURITY_CAPABILITIES *)v9;
        v9 = 0;
        v5 = 0;
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v7 = v9;
        v9 = 0;
        if ( v7 )
          Pku2uFree(v7);
        v5 = -1073741595;
      }
    }
    else
    {
      v6 = v9;
      v9 = 0;
      if ( v6 )
        Pku2uFree(v6);
    }
  }
  else
  {
    v9 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003ac00  mov     [rsp-8+arg_0], rbx
0x18003ac05  mov     [rsp-8+arg_8], rdi
0x18003ac0a  push    rbp
0x18003ac0b  mov     rbp, rsp
0x18003ac0e  sub     rsp, 50h
0x18003ac12  mov     rdi, r8
0x18003ac15  mov     [rbp+arg_18], 0
0x18003ac1c  mov     [rbp+var_30], 0
0x18003ac24  mov     [rbp+pHandle], 0
0x18003ac2c  lea     r8, [rbp+pHandle]; pHandle
0x18003ac30  call    cs:__imp_MesDecodeBufferHandleCreate
0x18003ac36  mov     ecx, eax; Status
0x18003ac38  call    cs:__imp_I_RpcMapWin32Status
0x18003ac3e  mov     ebx, eax
0x18003ac40  mov     [rbp+arg_18], eax
0x18003ac43  test    eax, eax
0x18003ac45  jns     short loc_18003AC60
0x18003ac47  mov     rcx, [rbp+var_30]; void *
0x18003ac4b  mov     [rbp+var_30], 0
0x18003ac53  test    rcx, rcx
0x18003ac56  jz      short loc_18003AC5E
0x18003ac58  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003ac5d  nop
0x18003ac5e  jmp     short loc_18003ACDB
0x18003ac60  lea     rax, [rbp+pHandle]
0x18003ac64  mov     [rbp+var_20], rax
0x18003ac68  lea     rax, [rbp+var_30]
0x18003ac6c  mov     [rbp+var_18], rax
0x18003ac70  lea     rax, [rbp+arg_18]
0x18003ac74  mov     [rbp+var_10], rax
0x18003ac78  lea     rcx, [rbp+var_20]
0x18003ac7c  call    _lambda_b761cd282be3ad407bc9c9412ad8a7c2___operator__
0x18003ac81  mov     ebx, [rbp+arg_18]
0x18003ac84  test    ebx, ebx
0x18003ac86  jns     short loc_18003ACA1
0x18003ac88  mov     rcx, [rbp+var_30]; void *
0x18003ac8c  mov     [rbp+var_30], 0
0x18003ac94  test    rcx, rcx
0x18003ac97  jz      short loc_18003AC9F
0x18003ac99  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003ac9e  nop
0x18003ac9f  jmp     short loc_18003ACDB
0x18003aca1  mov     rax, [rbp+var_30]
0x18003aca5  test    rax, rax
0x18003aca8  jnz     short loc_18003ACCE
0x18003acaa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003acaf  nop
0x18003acb0  mov     rcx, [rbp+var_30]; void *
0x18003acb4  mov     [rbp+var_30], 0
0x18003acbc  test    rcx, rcx
0x18003acbf  jz      short loc_18003ACC7
0x18003acc1  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003acc6  nop
0x18003acc7  mov     ebx, 0C00000E5h
0x18003accc  jmp     short loc_18003ACDB
0x18003acce  mov     [rdi], rax
0x18003acd1  mov     [rbp+var_30], 0
0x18003acd9  xor     ebx, ebx
0x18003acdb  lea     rcx, [rbp+pHandle]
0x18003acdf  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003ace4  mov     eax, ebx
0x18003ace6  mov     rbx, [rsp+50h+arg_0]
0x18003aceb  mov     rdi, [rsp+50h+arg_8]
0x18003acf0  add     rsp, 50h
0x18003acf4  pop     rbp
0x18003acf5  retn
```
