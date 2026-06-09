# CmsServicingSetupViewOfLayer

- ea: `0x18000d830`
- end: `0x18000d87b`
- name: `CmsServicingSetupViewOfLayer`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000cc10`
- `0x18000d830`

## string_xrefs

- `0x18000d85b`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingSetupViewOfLayer(__int64 *a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *a1;
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void * *),void *,void * * &>((__int64)a1, &v7, &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000d830  mov     r11, rsp
0x18000d833  mov     [r11+10h], rdx
0x18000d837  push    rbx; int
0x18000d838  sub     rsp, 20h
0x18000d83c  mov     rax, [rcx]
0x18000d83f  lea     r8, [r11+10h]
0x18000d843  lea     rdx, [r11+8]
0x18000d847  mov     [r11+8], rax
0x18000d84b  call    ??$InvokeStubFunction@P6AJPEAXPEAPEAX@ZPEAXAEAPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAPEAX@Z$$QEAPEAXAEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void * *),void *,void * * &>(long (*)(void *,void * *),void * &&,void * * &)
0x18000d850  mov     ebx, eax
0x18000d852  test    eax, eax
0x18000d854  jns     short loc_18000D873
0x18000d856  mov     rcx, [rsp+28h]; this
0x18000d85b  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d862  mov     r9d, eax; char *
0x18000d865  mov     edx, 90h; void *
0x18000d86a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d86f  mov     eax, ebx
0x18000d871  jmp     short loc_18000D875
0x18000d873  xor     eax, eax
0x18000d875  add     rsp, 20h
0x18000d879  pop     rbx
0x18000d87a  retn
```
