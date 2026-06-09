# CmsServicingAdjustLayer

- ea: `0x18000cdf0`
- end: `0x18000ce42`
- name: `CmsServicingAdjustLayer`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000cdf0`

## string_xrefs

- `0x18000ce22`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingAdjustLayer(__int64 *a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *a1;
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_AdjustLayer,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA3,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000cdf0  mov     r11, rsp
0x18000cdf3  mov     [r11+10h], rdx
0x18000cdf7  push    rbx; int
0x18000cdf8  sub     rsp, 20h
0x18000cdfc  mov     rax, [rcx]
0x18000cdff  lea     r8, [r11+10h]
0x18000ce03  lea     rcx, CmsRpcClt_AdjustLayer
0x18000ce0a  mov     [r11+8], rax
0x18000ce0e  lea     rdx, [r11+8]
0x18000ce12  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000ce17  mov     ebx, eax
0x18000ce19  test    eax, eax
0x18000ce1b  jns     short loc_18000CE3A
0x18000ce1d  mov     rcx, [rsp+28h]; this
0x18000ce22  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ce29  mov     r9d, eax; char *
0x18000ce2c  mov     edx, 0A3h; void *
0x18000ce31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce36  mov     eax, ebx
0x18000ce38  jmp     short loc_18000CE3C
0x18000ce3a  xor     eax, eax
0x18000ce3c  add     rsp, 20h
0x18000ce40  pop     rbx
0x18000ce41  retn
```
