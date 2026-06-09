# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,ushort const *),void *,_GUID &,ushort const * &>(long (*)(void *,_GUID,ushort const *),void * &&,_GUID &,ushort const * &)

- ea: `0x18000b874`
- end: `0x18000b8e5`
- name: `??$InvokeStubFunction@P6AJPEAXU_GUID@@PEBG@ZPEAXAEAU1@AEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAXU_GUID@@PEBG@Z$$QEAPEAXAEAU3@AEAPEBG@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bb80`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b874`
- `0x18000ddac`

## string_xrefs

- `0x18000b8a5`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b8ca`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,unsigned short const *),void *,_GUID &,unsigned short const * &>(
        __int64 a1,
        _QWORD *a2,
        _OWORD *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_OWORD *)v7 = *a3;
  v4 = CmsRpcClt_CopyLayerTrace(*a2, v7, *a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v4,
    v7[0]);
  return v5;
}

```

## disassembly

```asm
0x18000b874  push    rbx
0x18000b876  sub     rsp, 30h
0x18000b87a  mov     rax, rdx
0x18000b87d  movups  xmm0, xmmword ptr [r8]
0x18000b881  movdqu  xmmword ptr [rsp+38h+var_18], xmm0; int
0x18000b887  mov     r8, [r9]
0x18000b88a  lea     rdx, [rsp+38h+var_18]
0x18000b88f  mov     rcx, [rax]
0x18000b892  call    CmsRpcClt_CopyLayerTrace
0x18000b897  mov     ebx, eax
0x18000b899  test    eax, eax
0x18000b89b  jns     short loc_18000B8BA
0x18000b89d  mov     rcx, [rsp+38h]; this
0x18000b8a2  mov     r9d, eax; char *
0x18000b8a5  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b8ac  mov     edx, 56h ; 'V'; void *
0x18000b8b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8b6  mov     eax, ebx
0x18000b8b8  jmp     short loc_18000B8DF
0x18000b8ba  xor     eax, eax
0x18000b8bc  jmp     short loc_18000B8DF
0x18000b8be  test    eax, eax
0x18000b8c0  jz      short loc_18000B8DD
0x18000b8c2  mov     rcx, [rsp+38h]; this
0x18000b8c7  mov     r9d, eax; char *
0x18000b8ca  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b8d1  mov     edx, 5Ch ; '\'; void *
0x18000b8d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b8db  jmp     short loc_18000B8DF
0x18000b8dd  xor     eax, eax
0x18000b8df  add     rsp, 30h
0x18000b8e3  pop     rbx
0x18000b8e4  retn
```
