# CmsInternalGetContainerDebugFlags

- ea: `0x18000bcd0`
- end: `0x18000bd1c`
- name: `CmsInternalGetContainerDebugFlags`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b650`
- `0x18000bcd0`

## string_xrefs

- `0x18000bcfc`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetContainerDebugFlags(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_DEBUG_FLAGS *),void *,enum _CMS_CONTAINER_DEBUG_FLAGS * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x76,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000bcd0  mov     r11, rsp
0x18000bcd3  mov     [r11+10h], rdx
0x18000bcd7  push    rbx; int
0x18000bcd8  sub     rsp, 20h
0x18000bcdc  mov     rax, [rcx+18h]
0x18000bce0  lea     r8, [r11+10h]
0x18000bce4  lea     rdx, [r11+8]
0x18000bce8  mov     [r11+8], rax
0x18000bcec  call    ??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_CONTAINER_DEBUG_FLAGS@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_CONTAINER_DEBUG_FLAGS@@@Z$$QEAPEAXAEAPEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS *),void *,_CMS_CONTAINER_DEBUG_FLAGS * &>(long (*)(void *,_CMS_CONTAINER_DEBUG_FLAGS *),void * &&,_CMS_CONTAINER_DEBUG_FLAGS * &)
0x18000bcf1  mov     ebx, eax
0x18000bcf3  test    eax, eax
0x18000bcf5  jns     short loc_18000BD14
0x18000bcf7  mov     rcx, [rsp+28h]; this
0x18000bcfc  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bd03  mov     r9d, eax; char *
0x18000bd06  mov     edx, 76h ; 'v'; void *
0x18000bd0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd10  mov     eax, ebx
0x18000bd12  jmp     short loc_18000BD16
0x18000bd14  xor     eax, eax
0x18000bd16  add     rsp, 20h
0x18000bd1a  pop     rbx
0x18000bd1b  retn
```
