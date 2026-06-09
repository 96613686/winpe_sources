# CmsServicingCloseTransaction

- ea: `0x18000cf60`
- end: `0x18000cfb3`
- name: `CmsServicingCloseTransaction`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000cbac`
- `0x18000cf60`

## string_xrefs

- `0x18000cf87`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingCloseTransaction(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1;
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void * *),void * * &>((__int64)a1, &v7);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *a1 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return v3;
  }
}

```

## disassembly

```asm
0x18000cf60  mov     [rsp+arg_8], rbx
0x18000cf65  push    rdi; int
0x18000cf66  sub     rsp, 20h
0x18000cf6a  lea     rdx, [rsp+28h+arg_0]
0x18000cf6f  mov     [rsp+28h+arg_0], rcx
0x18000cf74  mov     rdi, rcx
0x18000cf77  call    ??$InvokeStubFunction@P6AJPEAPEAX@ZAEAPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAPEAX@ZAEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void * *),void * * &>(long (*)(void * *),void * * &)
0x18000cf7c  mov     ebx, eax
0x18000cf7e  test    eax, eax
0x18000cf80  jns     short loc_18000CF9F
0x18000cf82  mov     rcx, [rsp+28h]; this
0x18000cf87  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000cf8e  mov     r9d, eax; char *
0x18000cf91  mov     edx, 116h; void *
0x18000cf96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf9b  mov     eax, ebx
0x18000cf9d  jmp     short loc_18000CFA8
0x18000cf9f  mov     qword ptr [rdi], 0
0x18000cfa6  xor     eax, eax
0x18000cfa8  mov     rbx, [rsp+28h+arg_8]
0x18000cfad  add     rsp, 20h
0x18000cfb1  pop     rdi
0x18000cfb2  retn
```
