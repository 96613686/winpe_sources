# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)

- ea: `0x18000230c`
- end: `0x180002374`
- name: `??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z`
- size: `104`
- prototype: ``
- caller_count: `19`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007f20`
- `0x180008260`
- `0x180008320`
- `0x180008380`
- `0x180009480`
- `0x180009540`
- `0x180009800`
- `0x180009860`
- `0x1800098c0`
- `0x180009920`
- `0x180009980`
- `0x1800099e0`
- `0x18000bb20`
- `0x18000bd30`
- `0x18000c160`
- `0x18000c270`
- `0x18000c850`
- `0x18000cdf0`
- `0x18000d390`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000672c`
- `0x180010010`

## string_xrefs

- `0x180002334`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002359`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
        __int64 (__fastcall *a1)(_QWORD, _QWORD),
        _QWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = a1(*a2, *a3);
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
0x18000230c  push    rbx; int
0x18000230e  sub     rsp, 20h
0x180002312  mov     rax, rdx
0x180002315  mov     r9, rcx
0x180002318  mov     rdx, [r8]
0x18000231b  mov     rcx, [rax]
0x18000231e  mov     rax, r9
0x180002321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002326  mov     ebx, eax
0x180002328  test    eax, eax
0x18000232a  jns     short loc_180002349
0x18000232c  mov     rcx, [rsp+28h]; this
0x180002331  mov     r9d, eax; char *
0x180002334  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000233b  mov     edx, 56h ; 'V'; void *
0x180002340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002345  mov     eax, ebx
0x180002347  jmp     short loc_18000236E
0x180002349  xor     eax, eax
0x18000234b  jmp     short loc_18000236E
0x18000234d  test    eax, eax
0x18000234f  jz      short loc_18000236C
0x180002351  mov     rcx, [rsp+28h]; this
0x180002356  mov     r9d, eax; char *
0x180002359  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002360  mov     edx, 5Ch ; '\'; void *
0x180002365  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000236a  jmp     short loc_18000236E
0x18000236c  xor     eax, eax
0x18000236e  add     rsp, 20h
0x180002372  pop     rbx
0x180002373  retn
```
