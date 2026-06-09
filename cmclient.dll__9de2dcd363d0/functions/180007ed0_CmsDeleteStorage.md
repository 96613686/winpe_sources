# CmsDeleteStorage

- ea: `0x180007ed0`
- end: `0x180007f1a`
- name: `CmsDeleteStorage`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x180007ed0`

## string_xrefs

- `0x180007efa`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsDeleteStorage(__int64 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = *a1;
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_DeleteStorage,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A7,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180007ed0  push    rbx; int
0x180007ed2  sub     rsp, 20h
0x180007ed6  mov     rax, [rcx]
0x180007ed9  lea     rdx, [rsp+28h+arg_0]
0x180007ede  lea     rcx, CmsRpcClt_DeleteStorage
0x180007ee5  mov     [rsp+28h+arg_0], rax
0x180007eea  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180007eef  mov     ebx, eax
0x180007ef1  test    eax, eax
0x180007ef3  jns     short loc_180007F12
0x180007ef5  mov     rcx, [rsp+28h]; this
0x180007efa  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007f01  mov     r9d, eax; char *
0x180007f04  mov     edx, 5A7h; void *
0x180007f09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f0e  mov     eax, ebx
0x180007f10  jmp     short loc_180007F14
0x180007f12  xor     eax, eax
0x180007f14  add     rsp, 20h
0x180007f18  pop     rbx
0x180007f19  retn
```
