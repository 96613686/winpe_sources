# LuafvRemoveEcp

- ea: `0x140014a90`
- end: `0x140014b15`
- name: `LuafvRemoveEcp`
- size: `133`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400224ec`
- `0x140025350`
- `0x1400258a0`

## callees

- `0x140014a90`

## import_xrefs

- `FLTMGR!FltFreeExtraCreateParameter` at `0x140014b03`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140014b03`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140014ae7`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140014ae7`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140014ab5`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140014ab5`

## pseudocode

```c
void __fastcall LuafvRemoveEcp(PFLT_CALLBACK_DATA CallbackData)
{
  PECP_LIST EcpList; // [rsp+48h] [rbp+10h] BYREF
  PVOID EcpContext; // [rsp+50h] [rbp+18h] BYREF

  EcpList = 0;
  EcpContext = 0;
  FltGetEcpListFromCallbackData(LuafvDriverData, CallbackData, &EcpList);
  if ( EcpList )
  {
    if ( FltRemoveExtraCreateParameter(LuafvDriverData, EcpList, &LuafvEcpType, &EcpContext, 0) >= 0 )
      FltFreeExtraCreateParameter(LuafvDriverData, EcpContext);
  }
}

```

## disassembly

```asm
0x140014a90  sub     rsp, 38h
0x140014a94  mov     rdx, rcx; CallbackData
0x140014a97  mov     [rsp+38h+EcpList], 0
0x140014aa0  mov     rcx, cs:LuafvDriverData; Filter
0x140014aa7  lea     r8, [rsp+38h+EcpList]; EcpList
0x140014aac  mov     [rsp+38h+EcpContext], 0
0x140014ab5  call    cs:__imp_FltGetEcpListFromCallbackData
0x140014abc  nop     dword ptr [rax+rax+00h]
0x140014ac1  mov     rdx, [rsp+38h+EcpList]; EcpList
0x140014ac6  test    rdx, rdx
0x140014ac9  jz      short loc_140014B0F
0x140014acb  mov     rcx, cs:LuafvDriverData; Filter
0x140014ad2  lea     r9, [rsp+38h+EcpContext]; EcpContext
0x140014ad7  lea     r8, LuafvEcpType; EcpType
0x140014ade  mov     [rsp+38h+EcpContextSize], 0; EcpContextSize
0x140014ae7  call    cs:__imp_FltRemoveExtraCreateParameter
0x140014aee  nop     dword ptr [rax+rax+00h]
0x140014af3  test    eax, eax
0x140014af5  js      short loc_140014B0F
0x140014af7  mov     rdx, [rsp+38h+EcpContext]; EcpContext
0x140014afc  mov     rcx, cs:LuafvDriverData; Filter
0x140014b03  call    cs:__imp_FltFreeExtraCreateParameter
0x140014b0a  nop     dword ptr [rax+rax+00h]
0x140014b0f  add     rsp, 38h
0x140014b13  retn
```
