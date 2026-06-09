# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)

- ea: `0x18000237c`
- end: `0x1800023ea`
- name: `??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z`
- size: `110`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800084e0`
- `0x180008550`
- `0x1800085c0`
- `0x18000aba0`
- `0x18000ce50`
- `0x18000d4f0`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x18000672c`
- `0x180010010`

## string_xrefs

- `0x1800023aa`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800023cf`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,unsigned short const *),void *,void *,unsigned short const * &>(
        __int64 (__fastcall *a1)(_QWORD, _QWORD, _QWORD),
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = a1(*a2, *a3, *a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x18000237c  push    rbx; int
0x18000237e  sub     rsp, 20h
0x180002382  mov     rax, r8
0x180002385  mov     r10, rdx
0x180002388  mov     r11, rcx
0x18000238b  mov     r8, [r9]
0x18000238e  mov     rdx, [rax]
0x180002391  mov     rcx, [r10]
0x180002394  mov     rax, r11
0x180002397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239c  mov     ebx, eax
0x18000239e  test    eax, eax
0x1800023a0  jns     short loc_1800023BF
0x1800023a2  mov     rcx, [rsp+28h]; this
0x1800023a7  mov     r9d, eax; char *
0x1800023aa  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800023b1  mov     edx, 56h ; 'V'; void *
0x1800023b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800023bb  mov     eax, ebx
0x1800023bd  jmp     short loc_1800023E4
0x1800023bf  xor     eax, eax
0x1800023c1  jmp     short loc_1800023E4
0x1800023c3  test    eax, eax
0x1800023c5  jz      short loc_1800023E2
0x1800023c7  mov     rcx, [rsp+28h]; this
0x1800023cc  mov     r9d, eax; char *
0x1800023cf  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800023d6  mov     edx, 5Ch ; '\'; void *
0x1800023db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800023e0  jmp     short loc_1800023E4
0x1800023e2  xor     eax, eax
0x1800023e4  add     rsp, 20h
0x1800023e8  pop     rbx
0x1800023e9  retn
```
