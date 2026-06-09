# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int),void *,int &>(long (*)(void *,int),void * &&,int &)

- ea: `0x18000b494`
- end: `0x18000b4f6`
- name: `??$InvokeStubFunction@P6AJPEAXH@ZPEAXAEAH@Rpc@Manager@Container@@YAJP6AJPEAXH@Z$$QEAPEAXAEAH@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bac0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b494`
- `0x18000dd50`

## string_xrefs

- `0x18000b4b6`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b4db`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int),void *,int &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_ContainerSimulateUnresponsive(*a2, *a3);
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
0x18000b494  push    rbx; int
0x18000b496  sub     rsp, 20h
0x18000b49a  mov     rax, rdx
0x18000b49d  mov     edx, [r8]
0x18000b4a0  mov     rcx, [rax]
0x18000b4a3  call    CmsRpcClt_ContainerSimulateUnresponsive
0x18000b4a8  mov     ebx, eax
0x18000b4aa  test    eax, eax
0x18000b4ac  jns     short loc_18000B4CB
0x18000b4ae  mov     rcx, [rsp+28h]; this
0x18000b4b3  mov     r9d, eax; char *
0x18000b4b6  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b4bd  mov     edx, 56h ; 'V'; void *
0x18000b4c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4c7  mov     eax, ebx
0x18000b4c9  jmp     short loc_18000B4F0
0x18000b4cb  xor     eax, eax
0x18000b4cd  jmp     short loc_18000B4F0
0x18000b4cf  test    eax, eax
0x18000b4d1  jz      short loc_18000B4EE
0x18000b4d3  mov     rcx, [rsp+28h]; this
0x18000b4d8  mov     r9d, eax; char *
0x18000b4db  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b4e2  mov     edx, 5Ch ; '\'; void *
0x18000b4e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b4ec  jmp     short loc_18000B4F0
0x18000b4ee  xor     eax, eax
0x18000b4f0  add     rsp, 20h
0x18000b4f4  pop     rbx
0x18000b4f5  retn
```
