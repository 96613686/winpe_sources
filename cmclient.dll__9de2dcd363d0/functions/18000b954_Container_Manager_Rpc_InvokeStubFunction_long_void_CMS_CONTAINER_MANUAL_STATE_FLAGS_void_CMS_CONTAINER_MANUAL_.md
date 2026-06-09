# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_MANUAL_STATE_FLAGS),void *,_CMS_CONTAINER_MANUAL_STATE_FLAGS &>(long (*)(void *,_CMS_CONTAINER_MANUAL_STATE_FLAGS),void * &&,_CMS_CONTAINER_MANUAL_STATE_FLAGS &)

- ea: `0x18000b954`
- end: `0x18000b9b6`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_CONTAINER_MANUAL_STATE_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CONTAINER_MANUAL_STATE_FLAGS@@@Z$$QEAPEAXAEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c6b0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b954`
- `0x18000e800`

## string_xrefs

- `0x18000b976`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b99b`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_MANUAL_STATE_FLAGS),void *,enum _CMS_CONTAINER_MANUAL_STATE_FLAGS &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_SetContainerManualStateFlags(*a2, *a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b954  push    rbx; int
0x18000b956  sub     rsp, 20h
0x18000b95a  mov     rax, rdx
0x18000b95d  mov     edx, [r8]
0x18000b960  mov     rcx, [rax]
0x18000b963  call    CmsRpcClt_SetContainerManualStateFlags
0x18000b968  mov     ebx, eax
0x18000b96a  test    eax, eax
0x18000b96c  jns     short loc_18000B98B
0x18000b96e  mov     rcx, [rsp+28h]; this
0x18000b973  mov     r9d, eax; char *
0x18000b976  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b97d  mov     edx, 56h ; 'V'; void *
0x18000b982  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b987  mov     eax, ebx
0x18000b989  jmp     short loc_18000B9B0
0x18000b98b  xor     eax, eax
0x18000b98d  jmp     short loc_18000B9B0
0x18000b98f  test    eax, eax
0x18000b991  jz      short loc_18000B9AE
0x18000b993  mov     rcx, [rsp+28h]; this
0x18000b998  mov     r9d, eax; char *
0x18000b99b  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b9a2  mov     edx, 5Ch ; '\'; void *
0x18000b9a7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b9ac  jmp     short loc_18000B9B0
0x18000b9ae  xor     eax, eax
0x18000b9b0  add     rsp, 20h
0x18000b9b4  pop     rbx
0x18000b9b5  retn
```
