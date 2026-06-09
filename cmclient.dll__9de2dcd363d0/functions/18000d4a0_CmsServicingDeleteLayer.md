# CmsServicingDeleteLayer

- ea: `0x18000d4a0`
- end: `0x18000d4ea`
- name: `CmsServicingDeleteLayer`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000d4a0`

## string_xrefs

- `0x18000d4ca`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingDeleteLayer(__int64 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = *a1;
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_DeleteLayer,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x175,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d4a0  push    rbx; int
0x18000d4a2  sub     rsp, 20h
0x18000d4a6  mov     rax, [rcx]
0x18000d4a9  lea     rdx, [rsp+28h+arg_0]
0x18000d4ae  lea     rcx, CmsRpcClt_DeleteLayer
0x18000d4b5  mov     [rsp+28h+arg_0], rax
0x18000d4ba  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000d4bf  mov     ebx, eax
0x18000d4c1  test    eax, eax
0x18000d4c3  jns     short loc_18000D4E2
0x18000d4c5  mov     rcx, [rsp+28h]; this
0x18000d4ca  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d4d1  mov     r9d, eax; char *
0x18000d4d4  mov     edx, 175h; void *
0x18000d4d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4de  mov     eax, ebx
0x18000d4e0  jmp     short loc_18000D4E4
0x18000d4e2  xor     eax, eax
0x18000d4e4  add     rsp, 20h
0x18000d4e8  pop     rbx
0x18000d4e9  retn
```
