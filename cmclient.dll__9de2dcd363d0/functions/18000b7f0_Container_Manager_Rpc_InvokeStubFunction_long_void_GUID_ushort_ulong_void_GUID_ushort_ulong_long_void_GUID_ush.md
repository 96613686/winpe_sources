# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,ushort * *,ulong *),void *,_GUID &,ushort * *,ulong *>(long (*)(void *,_GUID,ushort * *,ulong *),void * &&,_GUID &,ushort * * &&,ulong * &&)

- ea: `0x18000b7f0`
- end: `0x18000b86c`
- name: `??$InvokeStubFunction@P6AJPEAXU_GUID@@PEAPEAGPEAK@ZPEAXAEAU1@PEAPEAGPEAK@Rpc@Manager@Container@@YAJP6AJPEAXU_GUID@@PEAPEAGPEAK@Z$$QEAPEAXAEAU3@$$QEAPEAPEAG$$QEAPEAK@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bdf0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b7f0`
- `0x18000eb40`

## string_xrefs

- `0x18000b82c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b851`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,unsigned short * *,unsigned long *),void *,_GUID &,unsigned short * *,unsigned long *>(
        __int64 a1,
        _QWORD *a2,
        _OWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int DebugLayerPath; // eax
  unsigned int v6; // ebx
  int v8[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_OWORD *)v8 = *a3;
  DebugLayerPath = CmsRpcClt_GetDebugLayerPath(*a2, v8, *a4, *a5);
  v6 = DebugLayerPath;
  if ( DebugLayerPath >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)DebugLayerPath,
    v8[0]);
  return v6;
}

```

## disassembly

```asm
0x18000b7f0  push    rbx
0x18000b7f2  sub     rsp, 30h
0x18000b7f6  mov     r10, r9
0x18000b7f9  mov     r11, rdx
0x18000b7fc  mov     rax, [rsp+38h+arg_20]
0x18000b801  movups  xmm0, xmmword ptr [r8]
0x18000b805  movdqu  xmmword ptr [rsp+38h+var_18], xmm0; int
0x18000b80b  mov     r9, [rax]
0x18000b80e  mov     r8, [r10]
0x18000b811  lea     rdx, [rsp+38h+var_18]
0x18000b816  mov     rcx, [r11]
0x18000b819  call    CmsRpcClt_GetDebugLayerPath
0x18000b81e  mov     ebx, eax
0x18000b820  test    eax, eax
0x18000b822  jns     short loc_18000B841
0x18000b824  mov     rcx, [rsp+38h]; this
0x18000b829  mov     r9d, eax; char *
0x18000b82c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b833  mov     edx, 56h ; 'V'; void *
0x18000b838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b83d  mov     eax, ebx
0x18000b83f  jmp     short loc_18000B866
0x18000b841  xor     eax, eax
0x18000b843  jmp     short loc_18000B866
0x18000b845  test    eax, eax
0x18000b847  jz      short loc_18000B864
0x18000b849  mov     rcx, [rsp+38h]; this
0x18000b84e  mov     r9d, eax; char *
0x18000b851  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b858  mov     edx, 5Ch ; '\'; void *
0x18000b85d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b862  jmp     short loc_18000B866
0x18000b864  xor     eax, eax
0x18000b866  add     rsp, 30h
0x18000b86a  pop     rbx
0x18000b86b  retn
```
