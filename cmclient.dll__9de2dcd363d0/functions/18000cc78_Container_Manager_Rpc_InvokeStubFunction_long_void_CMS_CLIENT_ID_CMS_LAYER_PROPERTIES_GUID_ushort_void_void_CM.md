# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_ID,_CMS_LAYER_PROPERTIES *,_GUID *,ushort * *,void * *),void *,_CMS_CLIENT_ID &,_CMS_LAYER_PROPERTIES * &,_GUID *,ushort * *,void * *>(long (*)(void *,_CMS_CLIENT_ID,_CMS_LAYER_PROPERTIES *,_GUID *,ushort * *,void * *),void * &&,_CMS_CLIENT_ID &,_CMS_LAYER_PROPERTIES * &,_GUID * &&,ushort * * &&,void * * &&)

- ea: `0x18000cc78`
- end: `0x18000cd05`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_LAYER_PROPERTIES@@PEAU_GUID@@PEAPEAGPEAPEAX@ZPEAXAEAW41@AEAPEAU2@PEAU3@PEAPEAGPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_LAYER_PROPERTIES@@PEAU_GUID@@PEAPEAGPEAPEAX@Z$$QEAPEAXAEAW43@AEAPEAU4@$$QEAPEAU5@$$QEAPEAPEAG$$QEAPEAPEAX@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d010`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000cc78`
- `0x18000df24`

## string_xrefs

- `0x18000ccc5`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000ccea`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_ID,_CMS_LAYER_PROPERTIES *,_GUID *,unsigned short * *,void * *),void *,enum _CMS_CLIENT_ID &,_CMS_LAYER_PROPERTIES * &,_GUID *,unsigned short * *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        __int64 *a7)
{
  int Layer; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Layer = CmsRpcClt_CreateLayer(*a2, *a3, *a4, *a5, *a6, *a7);
  v8 = Layer;
  if ( Layer >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)Layer,
    v10);
  return v8;
}

```

## disassembly

```asm
0x18000cc78  push    rbx
0x18000cc7a  sub     rsp, 30h
0x18000cc7e  mov     r10, r9
0x18000cc81  mov     r11, r8
0x18000cc84  mov     rbx, rdx
0x18000cc87  mov     rax, [rsp+38h+arg_30]
0x18000cc8c  mov     rcx, [rax]
0x18000cc8f  mov     [rsp+38h+var_10], rcx
0x18000cc94  mov     rax, [rsp+38h+arg_28]
0x18000cc99  mov     rcx, [rax]
0x18000cc9c  mov     qword ptr [rsp+38h+var_18], rcx; int
0x18000cca1  mov     r9, [rsp+38h+arg_20]
0x18000cca6  mov     r9, [r9]
0x18000cca9  mov     r8, [r10]
0x18000ccac  mov     edx, [r11]
0x18000ccaf  mov     rcx, [rbx]
0x18000ccb2  call    CmsRpcClt_CreateLayer
0x18000ccb7  mov     ebx, eax
0x18000ccb9  test    eax, eax
0x18000ccbb  jns     short loc_18000CCDA
0x18000ccbd  mov     rcx, [rsp+38h]; this
0x18000ccc2  mov     r9d, eax; char *
0x18000ccc5  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cccc  mov     edx, 56h ; 'V'; void *
0x18000ccd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccd6  mov     eax, ebx
0x18000ccd8  jmp     short loc_18000CCFF
0x18000ccda  xor     eax, eax
0x18000ccdc  jmp     short loc_18000CCFF
0x18000ccde  test    eax, eax
0x18000cce0  jz      short loc_18000CCFD
0x18000cce2  mov     rcx, [rsp+38h]; this
0x18000cce7  mov     r9d, eax; char *
0x18000ccea  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000ccf1  mov     edx, 5Ch ; '\'; void *
0x18000ccf6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ccfb  jmp     short loc_18000CCFF
0x18000ccfd  xor     eax, eax
0x18000ccff  add     rsp, 30h
0x18000cd03  pop     rbx
0x18000cd04  retn
```
