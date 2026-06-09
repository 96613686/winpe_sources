# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,void * * &&)

- ea: `0x180002a18`
- end: `0x180002a91`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAPEAX@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008c90`
- `0x18000d6d0`

## callees

- `0x180002a18`
- `0x1800066e4`
- `0x18000672c`
- `0x180010010`

## string_xrefs

- `0x180002a51`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002a76`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,void * *>(
        __int64 (__fastcall *a1)(_QWORD, _QWORD, _QWORD, _QWORD),
        _QWORD *a2,
        _QWORD *a3,
        unsigned int *a4,
        _QWORD *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = a1(*a2, *a3, *a4, *a5);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180002a18  push    rbx
0x180002a1a  sub     rsp, 30h
0x180002a1e  mov     rax, r9
0x180002a21  mov     r10, r8
0x180002a24  mov     r11, rdx
0x180002a27  mov     rbx, rcx
0x180002a2a  mov     r9, [rsp+38h+arg_20]
0x180002a2f  mov     r9, [r9]
0x180002a32  mov     r8d, [rax]
0x180002a35  mov     rdx, [r10]
0x180002a38  mov     rcx, [r11]
0x180002a3b  mov     rax, rbx
0x180002a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a43  mov     ebx, eax
0x180002a45  test    eax, eax
0x180002a47  jns     short loc_180002A66
0x180002a49  mov     rcx, [rsp+38h]; this
0x180002a4e  mov     r9d, eax; char *
0x180002a51  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002a58  mov     edx, 56h ; 'V'; void *
0x180002a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a62  mov     eax, ebx
0x180002a64  jmp     short loc_180002A8B
0x180002a66  xor     eax, eax
0x180002a68  jmp     short loc_180002A8B
0x180002a6a  test    eax, eax
0x180002a6c  jz      short loc_180002A89
0x180002a6e  mov     rcx, [rsp+38h]; this
0x180002a73  mov     r9d, eax; char *
0x180002a76  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002a7d  mov     edx, 5Ch ; '\'; void *
0x180002a82  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002a87  jmp     short loc_180002A8B
0x180002a89  xor     eax, eax
0x180002a8b  add     rsp, 30h
0x180002a8f  pop     rbx
0x180002a90  retn
```
