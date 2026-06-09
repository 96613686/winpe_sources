# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS *),void *,_CMS_GLOBAL_DEBUG_FLAGS * &>(long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS *),void * &&,_CMS_GLOBAL_DEBUG_FLAGS * &)

- ea: `0x18000b720`
- end: `0x18000b782`
- name: `??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_GLOBAL_DEBUG_FLAGS@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_GLOBAL_DEBUG_FLAGS@@@Z$$QEAPEAXAEAPEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bfa0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b720`
- `0x18000eb84`

## string_xrefs

- `0x18000b742`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000b767`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_GLOBAL_DEBUG_FLAGS *),void *,enum _CMS_GLOBAL_DEBUG_FLAGS * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int GlobalDebugFlags; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  GlobalDebugFlags = CmsRpcClt_GetGlobalDebugFlags(*a2, *a3);
  v4 = GlobalDebugFlags;
  if ( GlobalDebugFlags >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)GlobalDebugFlags,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b720  push    rbx; int
0x18000b722  sub     rsp, 20h
0x18000b726  mov     rax, rdx
0x18000b729  mov     rdx, [r8]
0x18000b72c  mov     rcx, [rax]
0x18000b72f  call    CmsRpcClt_GetGlobalDebugFlags
0x18000b734  mov     ebx, eax
0x18000b736  test    eax, eax
0x18000b738  jns     short loc_18000B757
0x18000b73a  mov     rcx, [rsp+28h]; this
0x18000b73f  mov     r9d, eax; char *
0x18000b742  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b749  mov     edx, 56h ; 'V'; void *
0x18000b74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b753  mov     eax, ebx
0x18000b755  jmp     short loc_18000B77C
0x18000b757  xor     eax, eax
0x18000b759  jmp     short loc_18000B77C
0x18000b75b  test    eax, eax
0x18000b75d  jz      short loc_18000B77A
0x18000b75f  mov     rcx, [rsp+28h]; this
0x18000b764  mov     r9d, eax; char *
0x18000b767  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b76e  mov     edx, 5Ch ; '\'; void *
0x18000b773  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b778  jmp     short loc_18000B77C
0x18000b77a  xor     eax, eax
0x18000b77c  add     rsp, 20h
0x18000b780  pop     rbx
0x18000b781  retn
```
