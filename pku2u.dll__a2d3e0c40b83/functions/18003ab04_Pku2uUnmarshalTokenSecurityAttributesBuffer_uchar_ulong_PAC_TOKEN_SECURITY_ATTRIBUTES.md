# Pku2uUnmarshalTokenSecurityAttributesBuffer(uchar *,ulong,_PAC_TOKEN_SECURITY_ATTRIBUTES * *)

- ea: `0x18003ab04`
- end: `0x18003abfa`
- name: `?Pku2uUnmarshalTokenSecurityAttributesBuffer@@YAJPEAEKPEAPEAU_PAC_TOKEN_SECURITY_ATTRIBUTES@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(char *, unsigned int, struct _PAC_TOKEN_SECURITY_ATTRIBUTES **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039f20`

## callees

- `0x1800057f0`
- `0x180038a70`
- `0x180038b78`
- `0x18003ab04`
- `0x180044d98`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18003ab34`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18003ab34`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003ab3c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003ab3c`

## pseudocode

```c
__int64 __fastcall Pku2uUnmarshalTokenSecurityAttributesBuffer(
        char *a1,
        unsigned int a2,
        struct _PAC_TOKEN_SECURITY_ATTRIBUTES **a3)
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
    lambda_a832ef9c1eede26f3bc2ff12f7c9d028_::operator()(v11);
    v5 = v12;
    if ( v12 >= 0 )
    {
      if ( v9 )
      {
        *a3 = (struct _PAC_TOKEN_SECURITY_ATTRIBUTES *)v9;
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
0x18003ab04  mov     [rsp-8+arg_0], rbx
0x18003ab09  mov     [rsp-8+arg_8], rdi
0x18003ab0e  push    rbp
0x18003ab0f  mov     rbp, rsp
0x18003ab12  sub     rsp, 50h
0x18003ab16  mov     rdi, r8
0x18003ab19  mov     [rbp+arg_18], 0
0x18003ab20  mov     [rbp+var_30], 0
0x18003ab28  mov     [rbp+pHandle], 0
0x18003ab30  lea     r8, [rbp+pHandle]; pHandle
0x18003ab34  call    cs:__imp_MesDecodeBufferHandleCreate
0x18003ab3a  mov     ecx, eax; Status
0x18003ab3c  call    cs:__imp_I_RpcMapWin32Status
0x18003ab42  mov     ebx, eax
0x18003ab44  mov     [rbp+arg_18], eax
0x18003ab47  test    eax, eax
0x18003ab49  jns     short loc_18003AB64
0x18003ab4b  mov     rcx, [rbp+var_30]; void *
0x18003ab4f  mov     [rbp+var_30], 0
0x18003ab57  test    rcx, rcx
0x18003ab5a  jz      short loc_18003AB62
0x18003ab5c  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003ab61  nop
0x18003ab62  jmp     short loc_18003ABDF
0x18003ab64  lea     rax, [rbp+pHandle]
0x18003ab68  mov     [rbp+var_20], rax
0x18003ab6c  lea     rax, [rbp+var_30]
0x18003ab70  mov     [rbp+var_18], rax
0x18003ab74  lea     rax, [rbp+arg_18]
0x18003ab78  mov     [rbp+var_10], rax
0x18003ab7c  lea     rcx, [rbp+var_20]
0x18003ab80  call    _lambda_a832ef9c1eede26f3bc2ff12f7c9d028___operator__
0x18003ab85  mov     ebx, [rbp+arg_18]
0x18003ab88  test    ebx, ebx
0x18003ab8a  jns     short loc_18003ABA5
0x18003ab8c  mov     rcx, [rbp+var_30]; void *
0x18003ab90  mov     [rbp+var_30], 0
0x18003ab98  test    rcx, rcx
0x18003ab9b  jz      short loc_18003ABA3
0x18003ab9d  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003aba2  nop
0x18003aba3  jmp     short loc_18003ABDF
0x18003aba5  mov     rax, [rbp+var_30]
0x18003aba9  test    rax, rax
0x18003abac  jnz     short loc_18003ABD2
0x18003abae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003abb3  nop
0x18003abb4  mov     rcx, [rbp+var_30]; void *
0x18003abb8  mov     [rbp+var_30], 0
0x18003abc0  test    rcx, rcx
0x18003abc3  jz      short loc_18003ABCB
0x18003abc5  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003abca  nop
0x18003abcb  mov     ebx, 0C00000E5h
0x18003abd0  jmp     short loc_18003ABDF
0x18003abd2  mov     [rdi], rax
0x18003abd5  mov     [rbp+var_30], 0
0x18003abdd  xor     ebx, ebx
0x18003abdf  lea     rcx, [rbp+pHandle]
0x18003abe3  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003abe8  mov     eax, ebx
0x18003abea  mov     rbx, [rsp+50h+arg_0]
0x18003abef  mov     rdi, [rsp+50h+arg_8]
0x18003abf4  add     rsp, 50h
0x18003abf8  pop     rbp
0x18003abf9  retn
```
