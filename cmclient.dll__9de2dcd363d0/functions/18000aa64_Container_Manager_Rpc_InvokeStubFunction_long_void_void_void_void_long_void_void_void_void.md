# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *),void *,void * &>(long (*)(void *,void *),void * &&,void * &)

- ea: `0x18000aa64`
- end: `0x18000aac6`
- name: `??$InvokeStubFunction@P6AJPEAX0@ZPEAXAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX0@Z$$QEAPEAXAEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ab40`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000aa64`
- `0x18000dd00`

## string_xrefs

- `0x18000aa86`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000aaab`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *),void *,void * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_CollectContainerMemoryState(*a2, *a3);
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
0x18000aa64  push    rbx; int
0x18000aa66  sub     rsp, 20h
0x18000aa6a  mov     rax, rdx
0x18000aa6d  mov     rdx, [r8]
0x18000aa70  mov     rcx, [rax]
0x18000aa73  call    CmsRpcClt_CollectContainerMemoryState
0x18000aa78  mov     ebx, eax
0x18000aa7a  test    eax, eax
0x18000aa7c  jns     short loc_18000AA9B
0x18000aa7e  mov     rcx, [rsp+28h]; this
0x18000aa83  mov     r9d, eax; char *
0x18000aa86  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000aa8d  mov     edx, 56h ; 'V'; void *
0x18000aa92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa97  mov     eax, ebx
0x18000aa99  jmp     short loc_18000AAC0
0x18000aa9b  xor     eax, eax
0x18000aa9d  jmp     short loc_18000AAC0
0x18000aa9f  test    eax, eax
0x18000aaa1  jz      short loc_18000AABE
0x18000aaa3  mov     rcx, [rsp+28h]; this
0x18000aaa8  mov     r9d, eax; char *
0x18000aaab  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000aab2  mov     edx, 5Ch ; '\'; void *
0x18000aab7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000aabc  jmp     short loc_18000AAC0
0x18000aabe  xor     eax, eax
0x18000aac0  add     rsp, 20h
0x18000aac4  pop     rbx
0x18000aac5  retn
```
