# LuafvSetEcp

- ea: `0x140022570`
- end: `0x1400226ad`
- name: `LuafvSetEcp`
- size: `317`
- prototype: `NTSTATUS __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002249c`

## callees

- `0x140022570`

## import_xrefs

- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002264a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002264a`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140022624`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140022624`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14002269c`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14002269c`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002267e`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002267e`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400225e2`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400225e2`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400225ae`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400225ae`
- `FLTMGR!FltReferenceContext` at `0x140022659`
- `FLTMGR!FltReferenceContext` at `0x140022659`

## pseudocode

```c
NTSTATUS __fastcall LuafvSetEcp(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)
{
  NTSTATUS result; // eax
  PVOID EcpContext; // [rsp+40h] [rbp-10h] BYREF
  PECP_LIST EcpList; // [rsp+70h] [rbp+20h] BYREF
  PVOID v7; // [rsp+78h] [rbp+28h] BYREF

  EcpList = 0;
  EcpContext = 0;
  v7 = 0;
  FltGetEcpListFromCallbackData(LuafvDriverData, CallbackData, &EcpList);
  if ( EcpList )
  {
    if ( FltFindExtraCreateParameter(LuafvDriverData, EcpList, &LuafvEcpType, &EcpContext, 0) >= 0 )
      return 0;
LABEL_3:
    result = FltAllocateExtraCreateParameter(LuafvDriverData, &LuafvEcpType, 8u, 0, LuafvCleanUpEcp, 0x6661754Cu, &v7);
    if ( result < 0 )
      return result;
    *(_QWORD *)v7 = Context;
    FltInsertExtraCreateParameter(LuafvDriverData, EcpList, v7);
    FltReferenceContext(Context);
    return 0;
  }
  result = FltAllocateExtraCreateParameterList(LuafvDriverData, 0, &EcpList);
  if ( result >= 0 )
  {
    FltSetEcpListIntoCallbackData(LuafvDriverData, CallbackData, EcpList);
    goto LABEL_3;
  }
  return result;
}

```

## disassembly

```asm
0x140022570  mov     [rsp-8+arg_0], rbx
0x140022575  mov     [rsp-8+arg_8], rdi
0x14002257a  push    rbp
0x14002257b  mov     rbp, rsp
0x14002257e  sub     rsp, 50h
0x140022582  mov     rbx, rdx
0x140022585  mov     [rbp+EcpList], 0
0x14002258d  mov     rdx, rcx; CallbackData
0x140022590  mov     [rbp+EcpContext], 0
0x140022598  mov     rdi, rcx
0x14002259b  mov     [rbp+arg_18], 0
0x1400225a3  mov     rcx, cs:LuafvDriverData; Filter
0x1400225aa  lea     r8, [rbp+EcpList]; EcpList
0x1400225ae  call    cs:__imp_FltGetEcpListFromCallbackData
0x1400225b5  nop     dword ptr [rax+rax+00h]
0x1400225ba  mov     rdx, [rbp+EcpList]; EcpList
0x1400225be  mov     rcx, cs:LuafvDriverData; Filter
0x1400225c5  test    rdx, rdx
0x1400225c8  jz      loc_140022678
0x1400225ce  lea     r9, [rbp+EcpContext]; EcpContext
0x1400225d2  mov     [rsp+50h+EcpContextSize], 0; EcpContextSize
0x1400225db  lea     r8, LuafvEcpType; EcpType
0x1400225e2  call    cs:__imp_FltFindExtraCreateParameter
0x1400225e9  nop     dword ptr [rax+rax+00h]
0x1400225ee  test    eax, eax
0x1400225f0  jns     short loc_140022665
0x1400225f2  mov     rcx, cs:LuafvDriverData; Filter
0x1400225f9  lea     rax, [rbp+arg_18]
0x1400225fd  mov     [rsp+50h+var_20], rax; EcpContext
0x140022602  lea     rdx, LuafvEcpType; EcpType
0x140022609  xor     r9d, r9d; Flags
0x14002260c  mov     [rsp+50h+PoolTag], 6661754Ch; PoolTag
0x140022614  lea     rax, LuafvCleanUpEcp
0x14002261b  mov     [rsp+50h+EcpContextSize], rax; CleanupCallback
0x140022620  lea     r8d, [r9+8]; SizeOfContext
0x140022624  call    cs:__imp_FltAllocateExtraCreateParameter
0x14002262b  nop     dword ptr [rax+rax+00h]
0x140022630  test    eax, eax
0x140022632  js      short loc_140022667
0x140022634  mov     rax, [rbp+arg_18]
0x140022638  mov     [rax], rbx
0x14002263b  mov     r8, [rbp+arg_18]; EcpContext
0x14002263f  mov     rdx, [rbp+EcpList]; EcpList
0x140022643  mov     rcx, cs:LuafvDriverData; Filter
0x14002264a  call    cs:__imp_FltInsertExtraCreateParameter
0x140022651  nop     dword ptr [rax+rax+00h]
0x140022656  mov     rcx, rbx; Context
0x140022659  call    cs:__imp_FltReferenceContext
0x140022660  nop     dword ptr [rax+rax+00h]
0x140022665  xor     eax, eax
0x140022667  mov     rbx, [rsp+50h+arg_0]
0x14002266c  mov     rdi, [rsp+50h+arg_8]
0x140022671  add     rsp, 50h
0x140022675  pop     rbp
0x140022676  retn
0x140022678  lea     r8, [rbp+EcpList]; EcpList
0x14002267c  xor     edx, edx; Flags
0x14002267e  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140022685  nop     dword ptr [rax+rax+00h]
0x14002268a  test    eax, eax
0x14002268c  js      short loc_140022667
0x14002268e  mov     r8, [rbp+EcpList]; EcpList
0x140022692  mov     rdx, rdi; CallbackData
0x140022695  mov     rcx, cs:LuafvDriverData; Filter
0x14002269c  call    cs:__imp_FltSetEcpListIntoCallbackData
0x1400226a3  nop     dword ptr [rax+rax+00h]
0x1400226a8  jmp     loc_1400225F2
```
