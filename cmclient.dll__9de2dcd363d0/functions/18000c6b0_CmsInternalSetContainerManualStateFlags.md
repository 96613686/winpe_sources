# CmsInternalSetContainerManualStateFlags

- ea: `0x18000c6b0`
- end: `0x18000c70d`
- name: `CmsInternalSetContainerManualStateFlags`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b954`
- `0x18000c6b0`

## string_xrefs

- `0x18000c6cd`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetContainerManualStateFlags(__int64 a1, unsigned int a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 132;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return (unsigned int)v2;
  }
  v7 = *(_QWORD *)(a1 + 24);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CONTAINER_MANUAL_STATE_FLAGS),void *,enum _CMS_CONTAINER_MANUAL_STATE_FLAGS &>(
         a1,
         &v7,
         &v8);
  if ( v2 < 0 )
  {
    v3 = 142;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c6b0  mov     [rsp+arg_8], edx
0x18000c6b4  push    rbx; int
0x18000c6b5  sub     rsp, 20h
0x18000c6b9  test    rcx, rcx
0x18000c6bc  jnz     short loc_18000C6E0
0x18000c6be  mov     ebx, 80070057h
0x18000c6c3  mov     edx, 84h; void *
0x18000c6c8  mov     rcx, [rsp+28h]; this
0x18000c6cd  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c6d4  mov     r9d, ebx; char *
0x18000c6d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6dc  mov     eax, ebx
0x18000c6de  jmp     short loc_18000C707
0x18000c6e0  mov     rax, [rcx+18h]
0x18000c6e4  lea     r8, [rsp+28h+arg_8]
0x18000c6e9  lea     rdx, [rsp+28h+arg_0]
0x18000c6ee  mov     [rsp+28h+arg_0], rax
0x18000c6f3  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_CONTAINER_MANUAL_STATE_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CONTAINER_MANUAL_STATE_FLAGS@@@Z$$QEAPEAXAEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CONTAINER_MANUAL_STATE_FLAGS),void *,_CMS_CONTAINER_MANUAL_STATE_FLAGS &>(long (*)(void *,_CMS_CONTAINER_MANUAL_STATE_FLAGS),void * &&,_CMS_CONTAINER_MANUAL_STATE_FLAGS &)
0x18000c6f8  mov     ebx, eax
0x18000c6fa  test    eax, eax
0x18000c6fc  jns     short loc_18000C705
0x18000c6fe  mov     edx, 8Eh
0x18000c703  jmp     short loc_18000C6C8
0x18000c705  xor     eax, eax
0x18000c707  add     rsp, 20h
0x18000c70b  pop     rbx
0x18000c70c  retn
```
