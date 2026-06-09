# CmsMapVirtualDiskToContainer

- ea: `0x1800085c0`
- end: `0x18000861b`
- name: `CmsMapVirtualDiskToContainer`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x1800085c0`

## string_xrefs

- `0x1800085fb`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsMapVirtualDiskToContainer(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v8 = *(_QWORD *)(a1 + 8);
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,unsigned short const *),void *,void *,unsigned short const * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))CmsRpcClt_MapVirtualDiskToContainer,
         &v8,
         &v9,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4EC,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800085c0  mov     r11, rsp
0x1800085c3  mov     [r11+18h], r8
0x1800085c7  mov     [r11+10h], rdx
0x1800085cb  push    rbx; int
0x1800085cc  sub     rsp, 20h
0x1800085d0  mov     rax, [rcx+8]
0x1800085d4  lea     r9, [r11+18h]
0x1800085d8  lea     rcx, CmsRpcClt_MapVirtualDiskToContainer
0x1800085df  mov     [r11+8], rax
0x1800085e3  lea     r8, [r11+10h]
0x1800085e7  lea     rdx, [r11+8]
0x1800085eb  call    ??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)
0x1800085f0  mov     ebx, eax
0x1800085f2  test    eax, eax
0x1800085f4  jns     short loc_180008613
0x1800085f6  mov     rcx, [rsp+28h]; this
0x1800085fb  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008602  mov     r9d, eax; char *
0x180008605  mov     edx, 4ECh; void *
0x18000860a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000860f  mov     eax, ebx
0x180008611  jmp     short loc_180008615
0x180008613  xor     eax, eax
0x180008615  add     rsp, 20h
0x180008619  pop     rbx
0x18000861a  retn
```
