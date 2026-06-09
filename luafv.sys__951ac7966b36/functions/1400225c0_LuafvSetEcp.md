# LuafvSetEcp

- ea: `0x1400225c0`
- end: `0x1400226fd`
- name: `LuafvSetEcp`
- size: `317`
- prototype: `NTSTATUS __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400224ec`

## callees

- `0x1400225c0`

## import_xrefs

- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002269a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002269a`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140022674`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140022674`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x1400226ec`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x1400226ec`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400226ce`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400226ce`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140022632`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140022632`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400225fe`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400225fe`
- `FLTMGR!FltReferenceContext` at `0x1400226a9`
- `FLTMGR!FltReferenceContext` at `0x1400226a9`

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
0x1400225c0  mov     [rsp-8+arg_0], rbx
0x1400225c5  mov     [rsp-8+arg_8], rdi
0x1400225ca  push    rbp
0x1400225cb  mov     rbp, rsp
0x1400225ce  sub     rsp, 50h
0x1400225d2  mov     rbx, rdx
0x1400225d5  mov     [rbp+EcpList], 0
0x1400225dd  mov     rdx, rcx; CallbackData
0x1400225e0  mov     [rbp+EcpContext], 0
0x1400225e8  mov     rdi, rcx
0x1400225eb  mov     [rbp+arg_18], 0
0x1400225f3  mov     rcx, cs:LuafvDriverData; Filter
0x1400225fa  lea     r8, [rbp+EcpList]; EcpList
0x1400225fe  call    cs:__imp_FltGetEcpListFromCallbackData
0x140022605  nop     dword ptr [rax+rax+00h]
0x14002260a  mov     rdx, [rbp+EcpList]; EcpList
0x14002260e  mov     rcx, cs:LuafvDriverData; Filter
0x140022615  test    rdx, rdx
0x140022618  jz      loc_1400226C8
0x14002261e  lea     r9, [rbp+EcpContext]; EcpContext
0x140022622  mov     [rsp+50h+EcpContextSize], 0; EcpContextSize
0x14002262b  lea     r8, LuafvEcpType; EcpType
0x140022632  call    cs:__imp_FltFindExtraCreateParameter
0x140022639  nop     dword ptr [rax+rax+00h]
0x14002263e  test    eax, eax
0x140022640  jns     short loc_1400226B5
0x140022642  mov     rcx, cs:LuafvDriverData; Filter
0x140022649  lea     rax, [rbp+arg_18]
0x14002264d  mov     [rsp+50h+var_20], rax; EcpContext
0x140022652  lea     rdx, LuafvEcpType; EcpType
0x140022659  xor     r9d, r9d; Flags
0x14002265c  mov     [rsp+50h+PoolTag], 6661754Ch; PoolTag
0x140022664  lea     rax, LuafvCleanUpEcp
0x14002266b  mov     [rsp+50h+EcpContextSize], rax; CleanupCallback
0x140022670  lea     r8d, [r9+8]; SizeOfContext
0x140022674  call    cs:__imp_FltAllocateExtraCreateParameter
0x14002267b  nop     dword ptr [rax+rax+00h]
0x140022680  test    eax, eax
0x140022682  js      short loc_1400226B7
0x140022684  mov     rax, [rbp+arg_18]
0x140022688  mov     [rax], rbx
0x14002268b  mov     r8, [rbp+arg_18]; EcpContext
0x14002268f  mov     rdx, [rbp+EcpList]; EcpList
0x140022693  mov     rcx, cs:LuafvDriverData; Filter
0x14002269a  call    cs:__imp_FltInsertExtraCreateParameter
0x1400226a1  nop     dword ptr [rax+rax+00h]
0x1400226a6  mov     rcx, rbx; Context
0x1400226a9  call    cs:__imp_FltReferenceContext
0x1400226b0  nop     dword ptr [rax+rax+00h]
0x1400226b5  xor     eax, eax
0x1400226b7  mov     rbx, [rsp+50h+arg_0]
0x1400226bc  mov     rdi, [rsp+50h+arg_8]
0x1400226c1  add     rsp, 50h
0x1400226c5  pop     rbp
0x1400226c6  retn
0x1400226c8  lea     r8, [rbp+EcpList]; EcpList
0x1400226cc  xor     edx, edx; Flags
0x1400226ce  call    cs:__imp_FltAllocateExtraCreateParameterList
0x1400226d5  nop     dword ptr [rax+rax+00h]
0x1400226da  test    eax, eax
0x1400226dc  js      short loc_1400226B7
0x1400226de  mov     r8, [rbp+EcpList]; EcpList
0x1400226e2  mov     rdx, rdi; CallbackData
0x1400226e5  mov     rcx, cs:LuafvDriverData; Filter
0x1400226ec  call    cs:__imp_FltSetEcpListIntoCallbackData
0x1400226f3  nop     dword ptr [rax+rax+00h]
0x1400226f8  jmp     loc_140022642
```
