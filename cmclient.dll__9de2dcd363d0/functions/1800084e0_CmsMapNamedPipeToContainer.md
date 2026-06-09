# CmsMapNamedPipeToContainer

- ea: `0x1800084e0`
- end: `0x18000853b`
- name: `CmsMapNamedPipeToContainer`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x1800084e0`

## string_xrefs

- `0x18000851b`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsMapNamedPipeToContainer(__int64 a1, __int64 a2, __int64 a3)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))CmsRpcClt_MapNamedPipeToContainer,
         &v8,
         &v9,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C4,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800084e0  mov     r11, rsp
0x1800084e3  mov     [r11+18h], r8
0x1800084e7  mov     [r11+10h], rdx
0x1800084eb  push    rbx; int
0x1800084ec  sub     rsp, 20h
0x1800084f0  mov     rax, [rcx+8]
0x1800084f4  lea     r9, [r11+18h]
0x1800084f8  lea     rcx, CmsRpcClt_MapNamedPipeToContainer
0x1800084ff  mov     [r11+8], rax
0x180008503  lea     r8, [r11+10h]
0x180008507  lea     rdx, [r11+8]
0x18000850b  call    ??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)
0x180008510  mov     ebx, eax
0x180008512  test    eax, eax
0x180008514  jns     short loc_180008533
0x180008516  mov     rcx, [rsp+28h]; this
0x18000851b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008522  mov     r9d, eax; char *
0x180008525  mov     edx, 4C4h; void *
0x18000852a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000852f  mov     eax, ebx
0x180008531  jmp     short loc_180008535
0x180008533  xor     eax, eax
0x180008535  add     rsp, 20h
0x180008539  pop     rbx
0x18000853a  retn
```
