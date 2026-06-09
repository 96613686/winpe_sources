# CmsInternalOpenContainerMemoryHostingProcess

- ea: `0x18000c360`
- end: `0x18000c3b4`
- name: `CmsInternalOpenContainerMemoryHostingProcess`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b578`
- `0x18000c360`

## string_xrefs

- `0x18000c394`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalOpenContainerMemoryHostingProcess(__int64 a1, unsigned int a2, __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v8 = *(_QWORD *)(a1 + 24);
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,void * *),void *,unsigned long &,void * * &>(
         a1,
         &v8,
         &v9,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BA,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000c360  mov     r11, rsp
0x18000c363  mov     [r11+18h], r8
0x18000c367  mov     [rsp+arg_8], edx
0x18000c36b  push    rbx; int
0x18000c36c  sub     rsp, 20h
0x18000c370  mov     rax, [rcx+18h]
0x18000c374  lea     r9, [r11+18h]
0x18000c378  lea     r8, [r11+10h]
0x18000c37c  mov     [r11+8], rax
0x18000c380  lea     rdx, [r11+8]
0x18000c384  call    ??$InvokeStubFunction@P6AJPEAXKPEAPEAX@ZPEAXAEAKAEAPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXKPEAPEAX@Z$$QEAPEAXAEAKAEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,void * *),void *,ulong &,void * * &>(long (*)(void *,ulong,void * *),void * &&,ulong &,void * * &)
0x18000c389  mov     ebx, eax
0x18000c38b  test    eax, eax
0x18000c38d  jns     short loc_18000C3AC
0x18000c38f  mov     rcx, [rsp+28h]; this
0x18000c394  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c39b  mov     r9d, eax; char *
0x18000c39e  mov     edx, 1BAh; void *
0x18000c3a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3a8  mov     eax, ebx
0x18000c3aa  jmp     short loc_18000C3AE
0x18000c3ac  xor     eax, eax
0x18000c3ae  add     rsp, 20h
0x18000c3b2  pop     rbx
0x18000c3b3  retn
```
