# Container::Manager::Rpc::InvokeStubFunction<long (*)(void * *),void * * &>(long (*)(void * *),void * * &)

- ea: `0x18000cbac`
- end: `0x18000cc08`
- name: `??$InvokeStubFunction@P6AJPEAPEAX@ZAEAPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAPEAX@ZAEAPEAPEAX@Z`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cf60`

## callees

- `0x1800066e4`
- `0x18000672c`
- `0x18000cbac`
- `0x18000dce0`

## string_xrefs

- `0x18000cbc8`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18000cbed`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void * *),void * * &>(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = CmsRpcClt_CloseTransaction(*a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000cbac  push    rbx; int
0x18000cbae  sub     rsp, 20h
0x18000cbb2  mov     rcx, [rdx]
0x18000cbb5  call    CmsRpcClt_CloseTransaction
0x18000cbba  mov     ebx, eax
0x18000cbbc  test    eax, eax
0x18000cbbe  jns     short loc_18000CBDD
0x18000cbc0  mov     rcx, [rsp+28h]; this
0x18000cbc5  mov     r9d, eax; char *
0x18000cbc8  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cbcf  mov     edx, 56h ; 'V'; void *
0x18000cbd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbd9  mov     eax, ebx
0x18000cbdb  jmp     short loc_18000CC02
0x18000cbdd  xor     eax, eax
0x18000cbdf  jmp     short loc_18000CC02
0x18000cbe1  test    eax, eax
0x18000cbe3  jz      short loc_18000CC00
0x18000cbe5  mov     rcx, [rsp+28h]; this
0x18000cbea  mov     r9d, eax; char *
0x18000cbed  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000cbf4  mov     edx, 5Ch ; '\'; void *
0x18000cbf9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000cbfe  jmp     short loc_18000CC02
0x18000cc00  xor     eax, eax
0x18000cc02  add     rsp, 20h
0x18000cc06  pop     rbx
0x18000cc07  retn
```
