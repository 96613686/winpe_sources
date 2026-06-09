# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS),void *,_CMS_CONTAINER_DEBUG_FLAGS &>(long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS),void * &&,_CMS_CONTAINER_DEBUG_FLAGS &)

- ea: `0x18000b8ec`
- end: `0x18000b94e`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_CONTAINER_DEBUG_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CONTAINER_DEBUG_FLAGS@@@Z$$QEAPEAXAEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c5f0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b8ec`
- `0x18000e7a8`

## string_xrefs

- `0x18000b90e`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b933`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_DEBUG_FLAGS),void *,enum _CMS_CONTAINER_DEBUG_FLAGS &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_SetContainerDebugFlags(*a2, *a3);
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
0x18000b8ec  push    rbx; int
0x18000b8ee  sub     rsp, 20h
0x18000b8f2  mov     rax, rdx
0x18000b8f5  mov     edx, [r8]
0x18000b8f8  mov     rcx, [rax]
0x18000b8fb  call    CmsRpcClt_SetContainerDebugFlags
0x18000b900  mov     ebx, eax
0x18000b902  test    eax, eax
0x18000b904  jns     short loc_18000B923
0x18000b906  mov     rcx, [rsp+28h]; this
0x18000b90b  mov     r9d, eax; char *
0x18000b90e  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b915  mov     edx, 56h ; 'V'; void *
0x18000b91a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b91f  mov     eax, ebx
0x18000b921  jmp     short loc_18000B948
0x18000b923  xor     eax, eax
0x18000b925  jmp     short loc_18000B948
0x18000b927  test    eax, eax
0x18000b929  jz      short loc_18000B946
0x18000b92b  mov     rcx, [rsp+28h]; this
0x18000b930  mov     r9d, eax; char *
0x18000b933  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b93a  mov     edx, 5Ch ; '\'; void *
0x18000b93f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b944  jmp     short loc_18000B948
0x18000b946  xor     eax, eax
0x18000b948  add     rsp, 20h
0x18000b94c  pop     rbx
0x18000b94d  retn
```
