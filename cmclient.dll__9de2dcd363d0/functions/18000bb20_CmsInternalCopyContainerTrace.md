# CmsInternalCopyContainerTrace

- ea: `0x18000bb20`
- end: `0x18000bb73`
- name: `CmsInternalCopyContainerTrace`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000bb20`

## string_xrefs

- `0x18000bb53`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalCopyContainerTrace(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_CopyContainerTrace,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x272,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000bb20  mov     r11, rsp
0x18000bb23  mov     [r11+10h], rdx
0x18000bb27  push    rbx; int
0x18000bb28  sub     rsp, 20h
0x18000bb2c  mov     rax, [rcx+8]
0x18000bb30  lea     r8, [r11+10h]
0x18000bb34  lea     rcx, CmsRpcClt_CopyContainerTrace
0x18000bb3b  mov     [r11+8], rax
0x18000bb3f  lea     rdx, [r11+8]
0x18000bb43  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000bb48  mov     ebx, eax
0x18000bb4a  test    eax, eax
0x18000bb4c  jns     short loc_18000BB6B
0x18000bb4e  mov     rcx, [rsp+28h]; this
0x18000bb53  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bb5a  mov     r9d, eax; char *
0x18000bb5d  mov     edx, 272h; void *
0x18000bb62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb67  mov     eax, ebx
0x18000bb69  jmp     short loc_18000BB6D
0x18000bb6b  xor     eax, eax
0x18000bb6d  add     rsp, 20h
0x18000bb71  pop     rbx
0x18000bb72  retn
```
