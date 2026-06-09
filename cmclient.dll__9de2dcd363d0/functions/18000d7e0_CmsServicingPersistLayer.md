# CmsServicingPersistLayer

- ea: `0x18000d7e0`
- end: `0x18000d82a`
- name: `CmsServicingPersistLayer`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000d7e0`

## string_xrefs

- `0x18000d80a`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingPersistLayer(__int64 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = *a1;
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_PersistLayer,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d7e0  push    rbx; int
0x18000d7e2  sub     rsp, 20h
0x18000d7e6  mov     rax, [rcx]
0x18000d7e9  lea     rdx, [rsp+28h+arg_0]
0x18000d7ee  lea     rcx, CmsRpcClt_PersistLayer
0x18000d7f5  mov     [rsp+28h+arg_0], rax
0x18000d7fa  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000d7ff  mov     ebx, eax
0x18000d801  test    eax, eax
0x18000d803  jns     short loc_18000D822
0x18000d805  mov     rcx, [rsp+28h]; this
0x18000d80a  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d811  mov     r9d, eax; char *
0x18000d814  mov     edx, 0B4h; void *
0x18000d819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d81e  mov     eax, ebx
0x18000d820  jmp     short loc_18000D824
0x18000d822  xor     eax, eax
0x18000d824  add     rsp, 20h
0x18000d828  pop     rbx
0x18000d829  retn
```
