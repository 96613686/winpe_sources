# EdpRpcPurgeAppLearningEvents

- ea: `0x180004c70`
- end: `0x180004d1e`
- name: `EdpRpcPurgeAppLearningEvents`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180004c70`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004c83`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004c83`
- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x180004cbd`
- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x180004cbd`

## pseudocode

```c
__int64 __fastcall EdpRpcPurgeAppLearningEvents(void *a1)
{
  RPC_STATUS IsClientLocal; // eax
  __int64 v2; // rcx
  int v3; // ebx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  unsigned int ClientLocalFlag; // [rsp+48h] [rbp+10h] BYREF

  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(a1, &ClientLocalFlag);
  v3 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v3 = (unsigned __int16)IsClientLocal | 0x80070000;
    goto LABEL_14;
  }
  if ( !ClientLocalFlag )
  {
    v3 = -2147024891;
LABEL_14:
    fnEfsLogTrace1(v2, (__int64)EFS_API_ERROR, v3, 6, 176);
    return (unsigned int)v3;
  }
  v4 = EfsEnforceClientAuthentication();
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 >= 0 )
  {
    v6 = EdpDllPurgeAppLearningEvents();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( v3 < 0 )
      fnEfsLogTrace1(v7, (__int64)EFS_API_ERROR, v3, 6, 186);
  }
  else
  {
    fnEfsLogTrace1(v5, (__int64)EFS_API_ERROR, v3, 6, 181);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004c70  push    rbx
0x180004c72  sub     rsp, 30h
0x180004c76  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x180004c7b  mov     [rsp+38h+ClientLocalFlag], 0
0x180004c83  call    cs:__imp_I_RpcBindingIsClientLocal
0x180004c8a  nop     dword ptr [rax+rax+00h]
0x180004c8f  mov     ebx, eax
0x180004c91  test    eax, eax
0x180004c93  jnz     short loc_180004CED
0x180004c95  cmp     [rsp+38h+ClientLocalFlag], eax
0x180004c99  jz      short loc_180004CE6
0x180004c9b  call    EfsEnforceClientAuthentication
0x180004ca0  mov     ebx, eax
0x180004ca2  test    eax, eax
0x180004ca4  jle     short loc_180004CAF
0x180004ca6  movzx   ebx, ax
0x180004ca9  or      ebx, 80070000h
0x180004caf  test    ebx, ebx
0x180004cb1  jns     short loc_180004CBD
0x180004cb3  mov     [rsp+38h+var_18], 11B5h
0x180004cbb  jmp     short loc_180004D00
0x180004cbd  call    cs:__imp_EdpDllPurgeAppLearningEvents
0x180004cc4  nop     dword ptr [rax+rax+00h]
0x180004cc9  mov     ebx, eax
0x180004ccb  test    eax, eax
0x180004ccd  jle     short loc_180004CD8
0x180004ccf  movzx   ebx, ax
0x180004cd2  or      ebx, 80070000h
0x180004cd8  test    ebx, ebx
0x180004cda  jns     short loc_180004D15
0x180004cdc  mov     [rsp+38h+var_18], 11BAh
0x180004ce4  jmp     short loc_180004D00
0x180004ce6  mov     ebx, 80070005h
0x180004ceb  jmp     short loc_180004CF8
0x180004ced  jle     short loc_180004CF8
0x180004cef  movzx   ebx, ax
0x180004cf2  or      ebx, 80070000h
0x180004cf8  mov     [rsp+38h+var_18], 11B0h
0x180004d00  mov     r9d, 6
0x180004d06  lea     rdx, EFS_API_ERROR
0x180004d0d  mov     r8d, ebx
0x180004d10  call    fnEfsLogTrace1
0x180004d15  mov     eax, ebx
0x180004d17  add     rsp, 30h
0x180004d1b  pop     rbx
0x180004d1c  retn
```
