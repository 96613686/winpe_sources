# CmsServicingWaitForPlatformReady

- ea: `0x18000d890`
- end: `0x18000d8da`
- name: `CmsServicingWaitForPlatformReady`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800021dc`
- `0x1800066e4`
- `0x18000d890`

## string_xrefs

- `0x18000d8ba`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingWaitForPlatformReady(__int64 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = *a1;
  v1 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_WaitForPlatformReady,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19E,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d890  push    rbx; int
0x18000d892  sub     rsp, 20h
0x18000d896  mov     rax, [rcx]
0x18000d899  lea     rdx, [rsp+28h+arg_0]
0x18000d89e  lea     rcx, CmsRpcClt_WaitForPlatformReady
0x18000d8a5  mov     [rsp+28h+arg_0], rax
0x18000d8aa  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000d8af  mov     ebx, eax
0x18000d8b1  test    eax, eax
0x18000d8b3  jns     short loc_18000D8D2
0x18000d8b5  mov     rcx, [rsp+28h]; this
0x18000d8ba  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d8c1  mov     r9d, eax; char *
0x18000d8c4  mov     edx, 19Eh; void *
0x18000d8c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8ce  mov     eax, ebx
0x18000d8d0  jmp     short loc_18000D8D4
0x18000d8d2  xor     eax, eax
0x18000d8d4  add     rsp, 20h
0x18000d8d8  pop     rbx
0x18000d8d9  retn
```
