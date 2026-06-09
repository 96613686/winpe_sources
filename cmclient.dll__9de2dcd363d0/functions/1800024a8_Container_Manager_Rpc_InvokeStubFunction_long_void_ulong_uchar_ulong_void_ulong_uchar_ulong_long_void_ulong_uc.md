# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,uchar * *,ulong *),void *,ulong &,uchar * *,ulong *>(long (*)(void *,ulong,uchar * *,ulong *),void * &&,ulong &,uchar * * &&,ulong * &&)

- ea: `0x1800024a8`
- end: `0x18000251b`
- name: `??$InvokeStubFunction@P6AJPEAXKPEAPEAEPEAK@ZPEAXAEAKPEAPEAEPEAK@Rpc@Manager@Container@@YAJP6AJPEAXKPEAPEAEPEAK@Z$$QEAPEAXAEAK$$QEAPEAPEAE$$QEAPEAK@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008060`

## callees

- `0x1800024a8`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e1bc`

## string_xrefs

- `0x1800024db`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002500`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,unsigned char * *,unsigned long *),void *,unsigned long &,unsigned char * *,unsigned long *>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int ContainerSecurityInformation; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ContainerSecurityInformation = CmsRpcClt_GetContainerSecurityInformation(*a2, *a3, *a4, *a5);
  v6 = ContainerSecurityInformation;
  if ( ContainerSecurityInformation >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerSecurityInformation,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800024a8  push    rbx; int
0x1800024aa  sub     rsp, 20h
0x1800024ae  mov     rax, r9
0x1800024b1  mov     r10, r8
0x1800024b4  mov     r11, rdx
0x1800024b7  mov     r9, [rsp+28h+arg_20]
0x1800024bc  mov     r9, [r9]
0x1800024bf  mov     r8, [rax]
0x1800024c2  mov     edx, [r10]
0x1800024c5  mov     rcx, [r11]
0x1800024c8  call    CmsRpcClt_GetContainerSecurityInformation
0x1800024cd  mov     ebx, eax
0x1800024cf  test    eax, eax
0x1800024d1  jns     short loc_1800024F0
0x1800024d3  mov     rcx, [rsp+28h]; this
0x1800024d8  mov     r9d, eax; char *
0x1800024db  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800024e2  mov     edx, 56h ; 'V'; void *
0x1800024e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800024ec  mov     eax, ebx
0x1800024ee  jmp     short loc_180002515
0x1800024f0  xor     eax, eax
0x1800024f2  jmp     short loc_180002515
0x1800024f4  test    eax, eax
0x1800024f6  jz      short loc_180002513
0x1800024f8  mov     rcx, [rsp+28h]; this
0x1800024fd  mov     r9d, eax; char *
0x180002500  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002507  mov     edx, 5Ch ; '\'; void *
0x18000250c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002511  jmp     short loc_180002515
0x180002513  xor     eax, eax
0x180002515  add     rsp, 20h
0x180002519  pop     rbx
0x18000251a  retn
```
