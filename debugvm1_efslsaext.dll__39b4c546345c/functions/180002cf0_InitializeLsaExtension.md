# InitializeLsaExtension

- ea: `0x180002cf0`
- end: `0x180002dac`
- name: `InitializeLsaExtension`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cf0`
- `0x180002eac`
- `0x180007e6c`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180002d41`
- `ntdll!EtwEventUnregister` at `0x180002d41`
- `ntdll!EtwEventRegister` at `0x180002d16`
- `ntdll!EtwEventRegister` at `0x180002d16`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180002d7b`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180002d7b`

## pseudocode

```c
__int64 __fastcall InitializeLsaExtension(int a1)
{
  unsigned int v1; // ebx
  int v2; // ebx
  __int64 v3; // rcx
  RPC_STATUS v4; // eax
  unsigned int v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  if ( !a1 )
  {
    v7 = 0;
    v2 = EtwEventRegister(EFS_PUBLISHER, 0, 0, &v7);
    if ( v2 )
    {
      v3 = v7;
    }
    else
    {
      v3 = 0;
      g_hPublisher = v7;
      v7 = 0;
    }
    if ( v3 )
      EtwEventUnregister();
    if ( v2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v6 = 0;
    v4 = RpcServerRegisterIfEx(qword_180014880, 0, 0, 9u, 0x4D2u, 0);
    v1 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v1 = (unsigned __int16)v4 | 0x80070000;
      v6 = v1;
    }
    else
    {
      v1 = 0;
    }
    EfsLsaRpcTelemetryProvider::EfsRpcRegisterDownlevelServer<long &>((WINBOOL *)&v6);
  }
  return v1;
}

```

## disassembly

```asm
0x180002cf0  push    rbx
0x180002cf2  sub     rsp, 30h
0x180002cf6  xor     ebx, ebx
0x180002cf8  test    ecx, ecx
0x180002cfa  jnz     loc_180002DA4
0x180002d00  lea     r9, [rsp+38h+arg_8]
0x180002d05  mov     [rsp+38h+arg_8], rbx
0x180002d0a  xor     r8d, r8d
0x180002d0d  lea     rcx, EFS_PUBLISHER
0x180002d14  xor     edx, edx
0x180002d16  call    cs:__imp_EtwEventRegister
0x180002d1c  mov     ebx, eax
0x180002d1e  test    eax, eax
0x180002d20  jnz     short loc_180002D37
0x180002d22  mov     rax, [rsp+38h+arg_8]
0x180002d27  xor     ecx, ecx
0x180002d29  mov     cs:g_hPublisher, rax
0x180002d30  mov     [rsp+38h+arg_8], rcx
0x180002d35  jmp     short loc_180002D3C
0x180002d37  mov     rcx, [rsp+38h+arg_8]
0x180002d3c  test    rcx, rcx
0x180002d3f  jz      short loc_180002D47
0x180002d41  call    cs:__imp_EtwEventUnregister
0x180002d47  test    ebx, ebx
0x180002d49  jz      short loc_180002D50
0x180002d4b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002d50  mov     [rsp+38h+IfCallback], 0; IfCallback
0x180002d59  lea     rcx, qword_180014880; IfSpec
0x180002d60  mov     r9d, 9; Flags
0x180002d66  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x180002d6e  xor     r8d, r8d; MgrEpv
0x180002d71  mov     [rsp+38h+arg_0], 0
0x180002d79  xor     edx, edx; MgrTypeUuid
0x180002d7b  call    cs:__imp_RpcServerRegisterIfEx
0x180002d81  mov     ebx, eax
0x180002d83  test    eax, eax
0x180002d85  jz      short loc_180002D98
0x180002d87  jle     short loc_180002D92
0x180002d89  movzx   ebx, ax
0x180002d8c  or      ebx, 80070000h
0x180002d92  mov     [rsp+38h+arg_0], ebx
0x180002d96  jmp     short loc_180002D9A
0x180002d98  xor     ebx, ebx
0x180002d9a  lea     rcx, [rsp+38h+arg_0]
0x180002d9f  call    ??$EfsRpcRegisterDownlevelServer@AEAJ@EfsLsaRpcTelemetryProvider@@SAXAEAJ@Z; EfsLsaRpcTelemetryProvider::EfsRpcRegisterDownlevelServer<long &>(long &)
0x180002da4  mov     eax, ebx
0x180002da6  add     rsp, 30h
0x180002daa  pop     rbx
0x180002dab  retn
```
