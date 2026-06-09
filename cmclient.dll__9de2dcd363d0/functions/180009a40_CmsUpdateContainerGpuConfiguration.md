# CmsUpdateContainerGpuConfiguration

- ea: `0x180009a40`
- end: `0x180009a8c`
- name: `CmsUpdateContainerGpuConfiguration`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180002608`
- `0x1800066e4`
- `0x180009a40`

## string_xrefs

- `0x180009a6c`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsUpdateContainerGpuConfiguration(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  v7 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GPU_CONFIGURATION *),void *,_CMS_GPU_CONFIGURATION * &>(
         a1,
         &v7,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x513,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009a40  mov     r11, rsp
0x180009a43  mov     [r11+10h], rdx
0x180009a47  push    rbx; int
0x180009a48  sub     rsp, 20h
0x180009a4c  mov     rax, [rcx+8]
0x180009a50  lea     r8, [r11+10h]
0x180009a54  lea     rdx, [r11+8]
0x180009a58  mov     [r11+8], rax
0x180009a5c  call    ??$InvokeStubFunction@P6AJPEAXPEAU_CMS_GPU_CONFIGURATION@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_GPU_CONFIGURATION@@@Z$$QEAPEAXAEAPEAU3@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GPU_CONFIGURATION *),void *,_CMS_GPU_CONFIGURATION * &>(long (*)(void *,_CMS_GPU_CONFIGURATION *),void * &&,_CMS_GPU_CONFIGURATION * &)
0x180009a61  mov     ebx, eax
0x180009a63  test    eax, eax
0x180009a65  jns     short loc_180009A84
0x180009a67  mov     rcx, [rsp+28h]; this
0x180009a6c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009a73  mov     r9d, eax; char *
0x180009a76  mov     edx, 513h; void *
0x180009a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a80  mov     eax, ebx
0x180009a82  jmp     short loc_180009A86
0x180009a84  xor     eax, eax
0x180009a86  add     rsp, 20h
0x180009a8a  pop     rbx
0x180009a8b  retn
```
