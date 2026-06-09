# UninitializeService(long)

- ea: `0x18000bcc0`
- end: `0x18000bd91`
- name: `?UninitializeService@@YAJJ@Z`
- size: `209`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b8e0`
- `0x18000bac0`

## callees

- `0x18000b30c`
- `0x18000b38c`
- `0x18000b648`
- `0x18000bcc0`

## import_xrefs

- `RPCRT4!RpcBindingVectorFree` at `0x18000bd61`
- `RPCRT4!RpcBindingVectorFree` at `0x18000bd61`
- `RPCRT4!RpcServerInqBindings` at `0x18000bce6`
- `RPCRT4!RpcServerInqBindings` at `0x18000bce6`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000bd04`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000bd04`

## pseudocode

```c
__int64 __fastcall UninitializeService(int a1)
{
  int v1; // ebx
  RPC_STATUS v2; // eax
  int v3; // edi
  int v4; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+38h] [rbp+10h] BYREF

  v1 = a1;
  SvcLogEventFromServiceEngine(2, a1);
  BindingVector = 0;
  v2 = RpcServerInqBindings(&BindingVector);
  if ( v2 )
  {
    v3 = ZTraceReportOriginationNoThis(v2 | 0x80010000, "SvcUnregisterRPCInterface", 285);
  }
  else
  {
    v3 = 0;
    UnregisterRPCInterface(qword_18000EC70, BindingVector);
    UnregisterRPCInterface(qword_18000F500, BindingVector);
    UnregisterRPCInterface(qword_18000F430, BindingVector);
    UnregisterRPCInterface(qword_18000E910, BindingVector);
  }
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  v4 = SvcUninitialize(v1);
  if ( v3 >= 0 )
    v3 = v4;
  if ( !v1 )
    v1 = v3;
  SvcLogEventFromServiceEngine(3, v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000bcc0  mov     [rsp+arg_0], rbx
0x18000bcc5  push    rdi
0x18000bcc6  sub     rsp, 20h
0x18000bcca  mov     ebx, ecx
0x18000bccc  mov     edx, ecx
0x18000bcce  mov     ecx, 2
0x18000bcd3  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x18000bcd8  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000bcdd  mov     [rsp+28h+BindingVector], 0
0x18000bce6  call    cs:__imp_RpcServerInqBindings
0x18000bcec  test    eax, eax
0x18000bcee  jz      short loc_18000BD0E
0x18000bcf0  or      eax, 80010000h
0x18000bcf5  lea     rdx, aSvcunregisterr; "SvcUnregisterRPCInterface"
0x18000bcfc  mov     ecx, eax
0x18000bcfe  mov     r8d, 11Dh
0x18000bd04  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000bd0a  mov     edi, eax
0x18000bd0c  jmp     short loc_18000BD54
0x18000bd0e  mov     rdx, [rsp+28h+BindingVector]; struct _RPC_BINDING_VECTOR *
0x18000bd13  lea     rcx, qword_18000EC70; IfSpec
0x18000bd1a  xor     edi, edi
0x18000bd1c  call    ?UnregisterRPCInterface@@YAJPEAXPEAU_RPC_BINDING_VECTOR@@@Z; UnregisterRPCInterface(void *,_RPC_BINDING_VECTOR *)
0x18000bd21  mov     rdx, [rsp+28h+BindingVector]; struct _RPC_BINDING_VECTOR *
0x18000bd26  lea     rcx, qword_18000F500; IfSpec
0x18000bd2d  call    ?UnregisterRPCInterface@@YAJPEAXPEAU_RPC_BINDING_VECTOR@@@Z; UnregisterRPCInterface(void *,_RPC_BINDING_VECTOR *)
0x18000bd32  mov     rdx, [rsp+28h+BindingVector]; struct _RPC_BINDING_VECTOR *
0x18000bd37  lea     rcx, qword_18000F430; IfSpec
0x18000bd3e  call    ?UnregisterRPCInterface@@YAJPEAXPEAU_RPC_BINDING_VECTOR@@@Z; UnregisterRPCInterface(void *,_RPC_BINDING_VECTOR *)
0x18000bd43  mov     rdx, [rsp+28h+BindingVector]; struct _RPC_BINDING_VECTOR *
0x18000bd48  lea     rcx, qword_18000E910; IfSpec
0x18000bd4f  call    ?UnregisterRPCInterface@@YAJPEAXPEAU_RPC_BINDING_VECTOR@@@Z; UnregisterRPCInterface(void *,_RPC_BINDING_VECTOR *)
0x18000bd54  cmp     [rsp+28h+BindingVector], 0
0x18000bd5a  jz      short loc_18000BD67
0x18000bd5c  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000bd61  call    cs:__imp_RpcBindingVectorFree
0x18000bd67  mov     ecx, ebx; int
0x18000bd69  call    ?SvcUninitialize@@YAJJ@Z; SvcUninitialize(long)
0x18000bd6e  test    edi, edi
0x18000bd70  mov     ecx, 3
0x18000bd75  cmovns  edi, eax
0x18000bd78  test    ebx, ebx
0x18000bd7a  cmovz   ebx, edi
0x18000bd7d  mov     edx, ebx
0x18000bd7f  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x18000bd84  mov     rbx, [rsp+28h+arg_0]
0x18000bd89  mov     eax, edi
0x18000bd8b  add     rsp, 20h
0x18000bd8f  pop     rdi
0x18000bd90  retn
```
