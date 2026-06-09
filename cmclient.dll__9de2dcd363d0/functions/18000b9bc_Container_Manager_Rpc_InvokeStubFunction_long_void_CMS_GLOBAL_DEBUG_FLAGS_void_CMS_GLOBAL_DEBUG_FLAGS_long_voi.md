# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS),void *,_CMS_GLOBAL_DEBUG_FLAGS &>(long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS),void * &&,_CMS_GLOBAL_DEBUG_FLAGS &)

- ea: `0x18000b9bc`
- end: `0x18000ba1e`
- name: `??$InvokeStubFunction@P6AJPEAXW4_CMS_GLOBAL_DEBUG_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_GLOBAL_DEBUG_FLAGS@@@Z$$QEAPEAXAEAW43@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c9e0`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000b9bc`
- `0x18000ec40`

## string_xrefs

- `0x18000b9de`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000ba03`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_GLOBAL_DEBUG_FLAGS),void *,enum _CMS_GLOBAL_DEBUG_FLAGS &>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_SetGlobalDebugFlags(*a2, *a3);
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
0x18000b9bc  push    rbx; int
0x18000b9be  sub     rsp, 20h
0x18000b9c2  mov     rax, rdx
0x18000b9c5  mov     edx, [r8]
0x18000b9c8  mov     rcx, [rax]
0x18000b9cb  call    CmsRpcClt_SetGlobalDebugFlags
0x18000b9d0  mov     ebx, eax
0x18000b9d2  test    eax, eax
0x18000b9d4  jns     short loc_18000B9F3
0x18000b9d6  mov     rcx, [rsp+28h]; this
0x18000b9db  mov     r9d, eax; char *
0x18000b9de  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000b9e5  mov     edx, 56h ; 'V'; void *
0x18000b9ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9ef  mov     eax, ebx
0x18000b9f1  jmp     short loc_18000BA18
0x18000b9f3  xor     eax, eax
0x18000b9f5  jmp     short loc_18000BA18
0x18000b9f7  test    eax, eax
0x18000b9f9  jz      short loc_18000BA16
0x18000b9fb  mov     rcx, [rsp+28h]; this
0x18000ba00  mov     r9d, eax; char *
0x18000ba03  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000ba0a  mov     edx, 5Ch ; '\'; void *
0x18000ba0f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ba14  jmp     short loc_18000BA18
0x18000ba16  xor     eax, eax
0x18000ba18  add     rsp, 20h
0x18000ba1c  pop     rbx
0x18000ba1d  retn
```
