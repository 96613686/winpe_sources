# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *,ushort * *),void *,_GUID * &,_CMS_CLIENT_ID &,void * *,ushort * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *,ushort * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,void * * &&,ushort * * &&)

- ea: `0x180002a98`
- end: `0x180002b18`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAXPEAPEAG@ZPEAXAEAPEAU1@AEAW42@PEAPEAXPEAPEAG@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAXPEAPEAG@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAPEAX$$QEAPEAPEAG@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008850`

## callees

- `0x180002a98`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e554`

## string_xrefs

- `0x180002ad8`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002afd`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,void * *,unsigned short * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,void * *,unsigned short * *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4,
        _QWORD *a5,
        __int64 *a6)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = CmsRpcClt_OpenLayer(*a2, *a3, *a4, *a5, *a6);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v6,
    v9);
  return v7;
}

```

## disassembly

```asm
0x180002a98  push    rbx
0x180002a9a  sub     rsp, 30h
0x180002a9e  mov     r10, r9
0x180002aa1  mov     r11, r8
0x180002aa4  mov     rbx, rdx
0x180002aa7  mov     rax, [rsp+38h+arg_28]
0x180002aac  mov     rcx, [rax]
0x180002aaf  mov     qword ptr [rsp+38h+var_18], rcx; int
0x180002ab4  mov     r9, [rsp+38h+arg_20]
0x180002ab9  mov     r9, [r9]
0x180002abc  mov     r8d, [r10]
0x180002abf  mov     rdx, [r11]
0x180002ac2  mov     rcx, [rbx]
0x180002ac5  call    CmsRpcClt_OpenLayer
0x180002aca  mov     ebx, eax
0x180002acc  test    eax, eax
0x180002ace  jns     short loc_180002AED
0x180002ad0  mov     rcx, [rsp+38h]; this
0x180002ad5  mov     r9d, eax; char *
0x180002ad8  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002adf  mov     edx, 56h ; 'V'; void *
0x180002ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ae9  mov     eax, ebx
0x180002aeb  jmp     short loc_180002B12
0x180002aed  xor     eax, eax
0x180002aef  jmp     short loc_180002B12
0x180002af1  test    eax, eax
0x180002af3  jz      short loc_180002B10
0x180002af5  mov     rcx, [rsp+38h]; this
0x180002afa  mov     r9d, eax; char *
0x180002afd  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002b04  mov     edx, 5Ch ; '\'; void *
0x180002b09  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002b0e  jmp     short loc_180002B12
0x180002b10  xor     eax, eax
0x180002b12  add     rsp, 30h
0x180002b16  pop     rbx
0x180002b17  retn
```
