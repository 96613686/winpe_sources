# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,void * *),void *,_GUID *,void * *>(long (*)(void *,_GUID *,void * *),void * &&,_GUID * &&,void * * &&)

- ea: `0x180002814`
- end: `0x18000287c`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEAPEAX@ZPEAXPEAU1@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEAPEAX@Z$$QEAPEAX$$QEAPEAU3@$$QEAPEAPEAX@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008730`

## callees

- `0x180002814`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e524`

## string_xrefs

- `0x18000283c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002861`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,void * *),void *,_GUID *,void * *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = CmsRpcClt_OpenContainerStorage(*a2, *a3, *a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x180002814  push    rbx; int
0x180002816  sub     rsp, 20h
0x18000281a  mov     rax, r8
0x18000281d  mov     r10, rdx
0x180002820  mov     r8, [r9]
0x180002823  mov     rdx, [rax]
0x180002826  mov     rcx, [r10]
0x180002829  call    CmsRpcClt_OpenContainerStorage
0x18000282e  mov     ebx, eax
0x180002830  test    eax, eax
0x180002832  jns     short loc_180002851
0x180002834  mov     rcx, [rsp+28h]; this
0x180002839  mov     r9d, eax; char *
0x18000283c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002843  mov     edx, 56h ; 'V'; void *
0x180002848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000284d  mov     eax, ebx
0x18000284f  jmp     short loc_180002876
0x180002851  xor     eax, eax
0x180002853  jmp     short loc_180002876
0x180002855  test    eax, eax
0x180002857  jz      short loc_180002874
0x180002859  mov     rcx, [rsp+28h]; this
0x18000285e  mov     r9d, eax; char *
0x180002861  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002868  mov     edx, 5Ch ; '\'; void *
0x18000286d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002872  jmp     short loc_180002876
0x180002874  xor     eax, eax
0x180002876  add     rsp, 20h
0x18000287a  pop     rbx
0x18000287b  retn
```
