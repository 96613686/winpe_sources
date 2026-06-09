# Container::Manager::Rpc::InvokeStubFunction<long (*)(_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,void *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,void *,uchar *,ulong &,ulong &,_WNF_STATE_NAME *,void * *>(long (*)(_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,void *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,void * &&,uchar * &&,ulong &,ulong &,_WNF_STATE_NAME * &&,void * * &&)

- ea: `0x180002244`
- end: `0x180002306`
- name: `??$InvokeStubFunction@P6AJPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAXPEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@ZAEAPEAU1@AEAW42@AEAPEAU3@PEAXPEAEAEAKAEAKPEAU4@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAXPEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@ZAEAPEAU3@AEAW44@AEAPEAU5@$$QEAPEAX$$QEAPEAEAEAKAEAK$$QEAPEAU6@$$QEAPEAPEAX@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007610`

## callees

- `0x180002244`
- `0x1800066e4`
- `0x18000672c`
- `0x18000deb4`

## string_xrefs

- `0x1800022c6`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800022eb`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(_GUID *,enum _CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,void *,unsigned char *,unsigned long,unsigned long,_WNF_STATE_NAME *,void * *),_GUID * &,enum _CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,void *,unsigned char *,unsigned long &,unsigned long &,_WNF_STATE_NAME *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        _DWORD *a8,
        __int64 *a9,
        __int64 *a10)
{
  int ContainerWithContainerStorage; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  ContainerWithContainerStorage = CmsRpcClt_CreateContainerWithContainerStorage(
                                    *a2,
                                    *a3,
                                    *a4,
                                    *a5,
                                    *a6,
                                    *a7,
                                    *a8,
                                    *a9,
                                    *a10);
  v11 = ContainerWithContainerStorage;
  if ( ContainerWithContainerStorage >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerWithContainerStorage,
    v13);
  return v11;
}

```

## disassembly

```asm
0x180002244  push    rbx
0x180002246  sub     rsp, 50h
0x18000224a  mov     r10, r9
0x18000224d  mov     r11, r8
0x180002250  mov     rbx, rdx
0x180002253  mov     rax, [rsp+58h+arg_48]
0x18000225b  mov     rcx, [rax]
0x18000225e  mov     [rsp+58h+var_18], rcx
0x180002263  mov     rax, [rsp+58h+arg_40]
0x18000226b  mov     rcx, [rax]
0x18000226e  mov     [rsp+58h+var_20], rcx
0x180002273  mov     rax, [rsp+58h+arg_38]
0x18000227b  mov     ecx, [rax]
0x18000227d  mov     [rsp+58h+var_28], ecx
0x180002281  mov     rax, [rsp+58h+arg_30]
0x180002289  mov     ecx, [rax]
0x18000228b  mov     [rsp+58h+var_30], ecx
0x18000228f  mov     rax, [rsp+58h+arg_28]
0x180002297  mov     rcx, [rax]
0x18000229a  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18000229f  mov     r9, [rsp+58h+arg_20]
0x1800022a7  mov     r9, [r9]
0x1800022aa  mov     r8, [r10]
0x1800022ad  mov     edx, [r11]
0x1800022b0  mov     rcx, [rbx]
0x1800022b3  call    CmsRpcClt_CreateContainerWithContainerStorage
0x1800022b8  mov     ebx, eax
0x1800022ba  test    eax, eax
0x1800022bc  jns     short loc_1800022DB
0x1800022be  mov     rcx, [rsp+58h]; this
0x1800022c3  mov     r9d, eax; char *
0x1800022c6  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800022cd  mov     edx, 56h ; 'V'; void *
0x1800022d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800022d7  mov     eax, ebx
0x1800022d9  jmp     short loc_180002300
0x1800022db  xor     eax, eax
0x1800022dd  jmp     short loc_180002300
0x1800022df  test    eax, eax
0x1800022e1  jz      short loc_1800022FE
0x1800022e3  mov     rcx, [rsp+58h]; this
0x1800022e8  mov     r9d, eax; char *
0x1800022eb  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800022f2  mov     edx, 5Ch ; '\'; void *
0x1800022f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800022fc  jmp     short loc_180002300
0x1800022fe  xor     eax, eax
0x180002300  add     rsp, 50h
0x180002304  pop     rbx
0x180002305  retn
```
