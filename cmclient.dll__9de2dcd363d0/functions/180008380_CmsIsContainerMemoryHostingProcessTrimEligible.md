# CmsIsContainerMemoryHostingProcessTrimEligible

- ea: `0x180008380`
- end: `0x1800083d3`
- name: `CmsIsContainerMemoryHostingProcessTrimEligible`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180008380`

## string_xrefs

- `0x1800083b3`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsIsContainerMemoryHostingProcessTrimEligible(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_IsContainerMemoryHostingProcessTrimEligible,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x273,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008380  mov     r11, rsp
0x180008383  mov     [r11+10h], rdx
0x180008387  push    rbx; int
0x180008388  sub     rsp, 20h
0x18000838c  mov     rax, [rcx+18h]
0x180008390  lea     r8, [r11+10h]
0x180008394  lea     rcx, CmsRpcClt_IsContainerMemoryHostingProcessTrimEligible
0x18000839b  mov     [r11+8], rax
0x18000839f  lea     rdx, [r11+8]
0x1800083a3  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x1800083a8  mov     ebx, eax
0x1800083aa  test    eax, eax
0x1800083ac  jns     short loc_1800083CB
0x1800083ae  mov     rcx, [rsp+28h]; this
0x1800083b3  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800083ba  mov     r9d, eax; char *
0x1800083bd  mov     edx, 273h; void *
0x1800083c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083c7  mov     eax, ebx
0x1800083c9  jmp     short loc_1800083CD
0x1800083cb  xor     eax, eax
0x1800083cd  add     rsp, 20h
0x1800083d1  pop     rbx
0x1800083d2  retn
```
