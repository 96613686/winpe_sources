# CmsQueryContainerMemoryInfo

- ea: `0x180008e30`
- end: `0x180008e7c`
- name: `CmsQueryContainerMemoryInfo`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800025a0`
- `0x1800066e4`
- `0x180008e30`

## string_xrefs

- `0x180008e5c`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsQueryContainerMemoryInfo(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_MEMORY_INFO *),void *,_CMS_CONTAINER_MEMORY_INFO * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x288,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008e30  mov     r11, rsp
0x180008e33  mov     [r11+10h], rdx
0x180008e37  push    rbx; int
0x180008e38  sub     rsp, 20h
0x180008e3c  mov     rax, [rcx+18h]
0x180008e40  lea     r8, [r11+10h]
0x180008e44  lea     rdx, [r11+8]
0x180008e48  mov     [r11+8], rax
0x180008e4c  call    ??$InvokeStubFunction@P6AJPEAXPEAU_CMS_CONTAINER_MEMORY_INFO@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_CONTAINER_MEMORY_INFO@@@Z$$QEAPEAXAEAPEAU3@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_MEMORY_INFO *),void *,_CMS_CONTAINER_MEMORY_INFO * &>(long (*)(void *,_CMS_CONTAINER_MEMORY_INFO *),void * &&,_CMS_CONTAINER_MEMORY_INFO * &)
0x180008e51  mov     ebx, eax
0x180008e53  test    eax, eax
0x180008e55  jns     short loc_180008E74
0x180008e57  mov     rcx, [rsp+28h]; this
0x180008e5c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008e63  mov     r9d, eax; char *
0x180008e66  mov     edx, 288h; void *
0x180008e6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e70  mov     eax, ebx
0x180008e72  jmp     short loc_180008E76
0x180008e74  xor     eax, eax
0x180008e76  add     rsp, 20h
0x180008e7a  pop     rbx
0x180008e7b  retn
```
