# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_MEMORY_INFO *),void *,_CMS_CONTAINER_MEMORY_INFO * &>(long (*)(void *,_CMS_CONTAINER_MEMORY_INFO *),void * &&,_CMS_CONTAINER_MEMORY_INFO * &)

- ea: `0x1800025a0`
- end: `0x180002602`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_CMS_CONTAINER_MEMORY_INFO@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_CONTAINER_MEMORY_INFO@@@Z$$QEAPEAXAEAPEAU3@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008e30`

## callees

- `0x1800025a0`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e690`

## string_xrefs

- `0x1800025c2`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800025e7`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_MEMORY_INFO *),void *,_CMS_CONTAINER_MEMORY_INFO * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int ContainerMemoryInfo; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ContainerMemoryInfo = CmsRpcClt_QueryContainerMemoryInfo(*a2, *a3);
  v4 = ContainerMemoryInfo;
  if ( ContainerMemoryInfo >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)ContainerMemoryInfo,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800025a0  push    rbx; int
0x1800025a2  sub     rsp, 20h
0x1800025a6  mov     rax, rdx
0x1800025a9  mov     rdx, [r8]
0x1800025ac  mov     rcx, [rax]
0x1800025af  call    CmsRpcClt_QueryContainerMemoryInfo
0x1800025b4  mov     ebx, eax
0x1800025b6  test    eax, eax
0x1800025b8  jns     short loc_1800025D7
0x1800025ba  mov     rcx, [rsp+28h]; this
0x1800025bf  mov     r9d, eax; char *
0x1800025c2  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800025c9  mov     edx, 56h ; 'V'; void *
0x1800025ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800025d3  mov     eax, ebx
0x1800025d5  jmp     short loc_1800025FC
0x1800025d7  xor     eax, eax
0x1800025d9  jmp     short loc_1800025FC
0x1800025db  test    eax, eax
0x1800025dd  jz      short loc_1800025FA
0x1800025df  mov     rcx, [rsp+28h]; this
0x1800025e4  mov     r9d, eax; char *
0x1800025e7  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800025ee  mov     edx, 5Ch ; '\'; void *
0x1800025f3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800025f8  jmp     short loc_1800025FC
0x1800025fa  xor     eax, eax
0x1800025fc  add     rsp, 20h
0x180002600  pop     rbx
0x180002601  retn
```
