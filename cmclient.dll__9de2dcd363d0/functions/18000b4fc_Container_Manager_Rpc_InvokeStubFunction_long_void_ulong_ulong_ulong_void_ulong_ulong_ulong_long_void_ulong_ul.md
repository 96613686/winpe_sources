# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,ulong,ulong),void *,ulong &,ulong &,ulong &>(long (*)(void *,ulong,ulong,ulong),void * &&,ulong &,ulong &,ulong &)

- ea: `0x18000b4fc`
- end: `0x18000b56f`
- name: `??$InvokeStubFunction@P6AJPEAXKKK@ZPEAXAEAKAEAKAEAK@Rpc@Manager@Container@@YAJP6AJPEAXKKK@Z$$QEAPEAXAEAK33@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c720`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b4fc`
- `0x18000ec0c`

## string_xrefs

- `0x18000b52f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b554`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,unsigned long,unsigned long),void *,unsigned long &,unsigned long &,unsigned long &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = CmsRpcClt_SetCustomHeartbeatSettings(*a2, *a3, *a4, *a5);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x18000b4fc  push    rbx; int
0x18000b4fe  sub     rsp, 20h
0x18000b502  mov     rax, r9
0x18000b505  mov     r10, r8
0x18000b508  mov     r11, rdx
0x18000b50b  mov     r9, [rsp+28h+arg_20]
0x18000b510  mov     r9d, [r9]
0x18000b513  mov     r8d, [rax]
0x18000b516  mov     edx, [r10]
0x18000b519  mov     rcx, [r11]
0x18000b51c  call    CmsRpcClt_SetCustomHeartbeatSettings
0x18000b521  mov     ebx, eax
0x18000b523  test    eax, eax
0x18000b525  jns     short loc_18000B544
0x18000b527  mov     rcx, [rsp+28h]; this
0x18000b52c  mov     r9d, eax; char *
0x18000b52f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b536  mov     edx, 56h ; 'V'; void *
0x18000b53b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b540  mov     eax, ebx
0x18000b542  jmp     short loc_18000B569
0x18000b544  xor     eax, eax
0x18000b546  jmp     short loc_18000B569
0x18000b548  test    eax, eax
0x18000b54a  jz      short loc_18000B567
0x18000b54c  mov     rcx, [rsp+28h]; this
0x18000b551  mov     r9d, eax; char *
0x18000b554  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b55b  mov     edx, 5Ch ; '\'; void *
0x18000b560  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b565  jmp     short loc_18000B569
0x18000b567  xor     eax, eax
0x18000b569  add     rsp, 20h
0x18000b56d  pop     rbx
0x18000b56e  retn
```
