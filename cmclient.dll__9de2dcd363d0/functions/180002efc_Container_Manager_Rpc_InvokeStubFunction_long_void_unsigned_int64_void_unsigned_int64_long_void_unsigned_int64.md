# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned __int64),void *,unsigned __int64 &>(long (*)(void *,unsigned __int64),void * &&,unsigned __int64 &)

- ea: `0x180002efc`
- end: `0x180002f5e`
- name: `??$InvokeStubFunction@P6AJPEAX_K@ZPEAXAEA_K@Rpc@Manager@Container@@YAJP6AJPEAX_K@Z$$QEAPEAXAEA_K@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800094e0`

## callees

- `0x180002efc`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e77c`

## string_xrefs

- `0x180002f1e`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002f43`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned __int64),void *,unsigned __int64 &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = CmsRpcClt_ResizeContainerStorage(*a2, *a3);
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
0x180002efc  push    rbx; int
0x180002efe  sub     rsp, 20h
0x180002f02  mov     rax, rdx
0x180002f05  mov     rdx, [r8]
0x180002f08  mov     rcx, [rax]
0x180002f0b  call    CmsRpcClt_ResizeContainerStorage
0x180002f10  mov     ebx, eax
0x180002f12  test    eax, eax
0x180002f14  jns     short loc_180002F33
0x180002f16  mov     rcx, [rsp+28h]; this
0x180002f1b  mov     r9d, eax; char *
0x180002f1e  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002f25  mov     edx, 56h ; 'V'; void *
0x180002f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f2f  mov     eax, ebx
0x180002f31  jmp     short loc_180002F58
0x180002f33  xor     eax, eax
0x180002f35  jmp     short loc_180002F58
0x180002f37  test    eax, eax
0x180002f39  jz      short loc_180002F56
0x180002f3b  mov     rcx, [rsp+28h]; this
0x180002f40  mov     r9d, eax; char *
0x180002f43  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002f4a  mov     edx, 5Ch ; '\'; void *
0x180002f4f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002f54  jmp     short loc_180002F58
0x180002f56  xor     eax, eax
0x180002f58  add     rsp, 20h
0x180002f5c  pop     rbx
0x180002f5d  retn
```
