# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FOLDER_PROPERTIES *),void *,_CMS_MAPPED_FOLDER_PROPERTIES * &>(long (*)(void *,_CMS_MAPPED_FOLDER_PROPERTIES *),void * &&,_CMS_MAPPED_FOLDER_PROPERTIES * &)

- ea: `0x1800026e0`
- end: `0x180002742`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_CMS_MAPPED_FOLDER_PROPERTIES@@@ZPEAXAEAPEAU1@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_MAPPED_FOLDER_PROPERTIES@@@Z$$QEAPEAXAEAPEAU3@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008480`

## callees

- `0x1800026e0`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e36c`

## string_xrefs

- `0x180002702`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002727`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FOLDER_PROPERTIES *),void *,_CMS_MAPPED_FOLDER_PROPERTIES * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_MapFolderToContainer(*a2, *a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800026e0  push    rbx; int
0x1800026e2  sub     rsp, 20h
0x1800026e6  mov     rax, rdx
0x1800026e9  mov     rdx, [r8]
0x1800026ec  mov     rcx, [rax]
0x1800026ef  call    CmsRpcClt_MapFolderToContainer
0x1800026f4  mov     ebx, eax
0x1800026f6  test    eax, eax
0x1800026f8  jns     short loc_180002717
0x1800026fa  mov     rcx, [rsp+28h]; this
0x1800026ff  mov     r9d, eax; char *
0x180002702  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002709  mov     edx, 56h ; 'V'; void *
0x18000270e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002713  mov     eax, ebx
0x180002715  jmp     short loc_18000273C
0x180002717  xor     eax, eax
0x180002719  jmp     short loc_18000273C
0x18000271b  test    eax, eax
0x18000271d  jz      short loc_18000273A
0x18000271f  mov     rcx, [rsp+28h]; this
0x180002724  mov     r9d, eax; char *
0x180002727  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000272e  mov     edx, 5Ch ; '\'; void *
0x180002733  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002738  jmp     short loc_18000273C
0x18000273a  xor     eax, eax
0x18000273c  add     rsp, 20h
0x180002740  pop     rbx
0x180002741  retn
```
