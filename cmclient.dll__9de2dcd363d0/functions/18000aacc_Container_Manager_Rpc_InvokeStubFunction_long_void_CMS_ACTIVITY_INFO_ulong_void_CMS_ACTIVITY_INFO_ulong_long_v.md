# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_INFO * *,ulong *),void *,_CMS_ACTIVITY_INFO * *,ulong *>(long (*)(void *,_CMS_ACTIVITY_INFO * *,ulong *),void * &&,_CMS_ACTIVITY_INFO * * &&,ulong * &&)

- ea: `0x18000aacc`
- end: `0x18000ab34`
- name: `??$InvokeStubFunction@P6AJPEAXPEAPEAU_CMS_ACTIVITY_INFO@@PEAK@ZPEAXPEAPEAU1@PEAK@Rpc@Manager@Container@@YAJP6AJPEAXPEAPEAU_CMS_ACTIVITY_INFO@@PEAK@Z$$QEAPEAX$$QEAPEAPEAU3@$$QEAPEAK@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ad50`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000aacc`
- `0x18000e100`

## string_xrefs

- `0x18000aaf4`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000ab19`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_INFO * *,unsigned long *),void *,_CMS_ACTIVITY_INFO * *,unsigned long *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int ContainerActivityInfos; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ContainerActivityInfos = CmsRpcClt_GetContainerActivityInfos(*a2, *a3, *a4);
  v5 = ContainerActivityInfos;
  if ( ContainerActivityInfos >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerActivityInfos,
    v7);
  return v5;
}

```

## disassembly

```asm
0x18000aacc  push    rbx; int
0x18000aace  sub     rsp, 20h
0x18000aad2  mov     rax, r8
0x18000aad5  mov     r10, rdx
0x18000aad8  mov     r8, [r9]
0x18000aadb  mov     rdx, [rax]
0x18000aade  mov     rcx, [r10]
0x18000aae1  call    CmsRpcClt_GetContainerActivityInfos
0x18000aae6  mov     ebx, eax
0x18000aae8  test    eax, eax
0x18000aaea  jns     short loc_18000AB09
0x18000aaec  mov     rcx, [rsp+28h]; this
0x18000aaf1  mov     r9d, eax; char *
0x18000aaf4  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000aafb  mov     edx, 56h ; 'V'; void *
0x18000ab00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab05  mov     eax, ebx
0x18000ab07  jmp     short loc_18000AB2E
0x18000ab09  xor     eax, eax
0x18000ab0b  jmp     short loc_18000AB2E
0x18000ab0d  test    eax, eax
0x18000ab0f  jz      short loc_18000AB2C
0x18000ab11  mov     rcx, [rsp+28h]; this
0x18000ab16  mov     r9d, eax; char *
0x18000ab19  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000ab20  mov     edx, 5Ch ; '\'; void *
0x18000ab25  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ab2a  jmp     short loc_18000AB2E
0x18000ab2c  xor     eax, eax
0x18000ab2e  add     rsp, 20h
0x18000ab32  pop     rbx
0x18000ab33  retn
```
