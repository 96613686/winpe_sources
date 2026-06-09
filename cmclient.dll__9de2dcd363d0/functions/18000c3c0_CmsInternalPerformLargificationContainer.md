# CmsInternalPerformLargificationContainer

- ea: `0x18000c3c0`
- end: `0x18000c40b`
- name: `CmsInternalPerformLargificationContainer`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000c3c0`

## string_xrefs

- `0x18000c3eb`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalPerformLargificationContainer(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 24);
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_PerformLargificationContainer,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14B,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000c3c0  push    rbx; int
0x18000c3c2  sub     rsp, 20h
0x18000c3c6  mov     rax, [rcx+18h]
0x18000c3ca  lea     rdx, [rsp+28h+arg_0]
0x18000c3cf  lea     rcx, CmsRpcClt_PerformLargificationContainer
0x18000c3d6  mov     [rsp+28h+arg_0], rax
0x18000c3db  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000c3e0  mov     ebx, eax
0x18000c3e2  test    eax, eax
0x18000c3e4  jns     short loc_18000C403
0x18000c3e6  mov     rcx, [rsp+28h]; this
0x18000c3eb  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c3f2  mov     r9d, eax; char *
0x18000c3f5  mov     edx, 14Bh; void *
0x18000c3fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3ff  mov     eax, ebx
0x18000c401  jmp     short loc_18000C405
0x18000c403  xor     eax, eax
0x18000c405  add     rsp, 20h
0x18000c409  pop     rbx
0x18000c40a  retn
```
