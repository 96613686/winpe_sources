# Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FILE_PROPERTIES *,ushort const *),void *,_CMS_MAPPED_FILE_PROPERTIES * &,ushort const * &>(long (*)(void *,_CMS_MAPPED_FILE_PROPERTIES *,ushort const *),void * &&,_CMS_MAPPED_FILE_PROPERTIES * &,ushort const * &)

- ea: `0x180002670`
- end: `0x1800026d8`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_CMS_MAPPED_FILE_PROPERTIES@@PEBG@ZPEAXAEAPEAU1@AEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_MAPPED_FILE_PROPERTIES@@PEBG@Z$$QEAPEAXAEAPEAU3@AEAPEBG@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800083e0`

## callees

- `0x180002670`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e33c`

## string_xrefs

- `0x180002698`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800026bd`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MAPPED_FILE_PROPERTIES *,unsigned short const *),void *,_CMS_MAPPED_FILE_PROPERTIES * &,unsigned short const * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = CmsRpcClt_MapFileToContainer(*a2, *a3, *a4);
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
0x180002670  push    rbx; int
0x180002672  sub     rsp, 20h
0x180002676  mov     rax, r8
0x180002679  mov     r10, rdx
0x18000267c  mov     r8, [r9]
0x18000267f  mov     rdx, [rax]
0x180002682  mov     rcx, [r10]
0x180002685  call    CmsRpcClt_MapFileToContainer
0x18000268a  mov     ebx, eax
0x18000268c  test    eax, eax
0x18000268e  jns     short loc_1800026AD
0x180002690  mov     rcx, [rsp+28h]; this
0x180002695  mov     r9d, eax; char *
0x180002698  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000269f  mov     edx, 56h ; 'V'; void *
0x1800026a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800026a9  mov     eax, ebx
0x1800026ab  jmp     short loc_1800026D2
0x1800026ad  xor     eax, eax
0x1800026af  jmp     short loc_1800026D2
0x1800026b1  test    eax, eax
0x1800026b3  jz      short loc_1800026D0
0x1800026b5  mov     rcx, [rsp+28h]; this
0x1800026ba  mov     r9d, eax; char *
0x1800026bd  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800026c4  mov     edx, 5Ch ; '\'; void *
0x1800026c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800026ce  jmp     short loc_1800026D2
0x1800026d0  xor     eax, eax
0x1800026d2  add     rsp, 20h
0x1800026d6  pop     rbx
0x1800026d7  retn
```
