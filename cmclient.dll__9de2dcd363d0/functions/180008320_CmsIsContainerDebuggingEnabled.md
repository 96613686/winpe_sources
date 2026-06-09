# CmsIsContainerDebuggingEnabled

- ea: `0x180008320`
- end: `0x180008373`
- name: `CmsIsContainerDebuggingEnabled`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180008320`

## string_xrefs

- `0x180008353`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsIsContainerDebuggingEnabled(__int64 a1, __int64 a2)
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
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_IsContainerDebuggingEnabled,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6E9,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180008320  mov     r11, rsp
0x180008323  mov     [r11+10h], rdx
0x180008327  push    rbx; int
0x180008328  sub     rsp, 20h
0x18000832c  mov     rax, [rcx+18h]
0x180008330  lea     r8, [r11+10h]
0x180008334  lea     rcx, CmsRpcClt_IsContainerDebuggingEnabled
0x18000833b  mov     [r11+8], rax
0x18000833f  lea     rdx, [r11+8]
0x180008343  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x180008348  mov     ebx, eax
0x18000834a  test    eax, eax
0x18000834c  jns     short loc_18000836B
0x18000834e  mov     rcx, [rsp+28h]; this
0x180008353  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000835a  mov     r9d, eax; char *
0x18000835d  mov     edx, 6E9h; void *
0x180008362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008367  mov     eax, ebx
0x180008369  jmp     short loc_18000836D
0x18000836b  xor     eax, eax
0x18000836d  add     rsp, 20h
0x180008371  pop     rbx
0x180008372  retn
```
