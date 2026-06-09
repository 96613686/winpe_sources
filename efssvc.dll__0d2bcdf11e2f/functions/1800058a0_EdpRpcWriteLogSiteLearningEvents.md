# EdpRpcWriteLogSiteLearningEvents

- ea: `0x1800058a0`
- end: `0x180005969`
- name: `EdpRpcWriteLogSiteLearningEvents`
- size: `201`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800037b8`
- `0x1800058a0`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800058ba`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800058ba`
- `EFSCORE!EdpWriteSiteLearningLog` at `0x180005903`
- `EFSCORE!EdpWriteSiteLearningLog` at `0x180005903`

## pseudocode

```c
__int64 __fastcall EdpRpcWriteLogSiteLearningEvents(void *a1, __int64 a2)
{
  RPC_STATUS IsClientLocal; // eax
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  unsigned int ClientLocalFlag; // [rsp+50h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(a1, &ClientLocalFlag);
  v5 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v5 = (unsigned __int16)IsClientLocal | 0x80070000;
    goto LABEL_16;
  }
  if ( !ClientLocalFlag )
  {
    v5 = -2147024891;
LABEL_16:
    fnEfsLogTrace1(v4, (__int64)EFS_API_ERROR, v5, 6, 248);
    return (unsigned int)v5;
  }
  v6 = EfsEnforceClientAuthentication();
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( v5 >= 0 )
  {
    if ( a2 )
    {
      v8 = EdpWriteSiteLearningLog(a2);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 < 0 )
        fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v5, 6, 3);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    fnEfsLogTrace1(v7, (__int64)EFS_API_ERROR, v5, 6, 253);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800058a0  mov     [rsp+arg_0], rbx
0x1800058a5  push    rsi
0x1800058a6  sub     rsp, 30h
0x1800058aa  mov     rsi, rdx
0x1800058ad  mov     [rsp+38h+ClientLocalFlag], 0
0x1800058b5  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x1800058ba  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800058c1  nop     dword ptr [rax+rax+00h]
0x1800058c6  mov     ebx, eax
0x1800058c8  test    eax, eax
0x1800058ca  jnz     short loc_180005933
0x1800058cc  cmp     [rsp+38h+ClientLocalFlag], eax
0x1800058d0  jz      short loc_18000592C
0x1800058d2  call    EfsEnforceClientAuthentication
0x1800058d7  mov     ebx, eax
0x1800058d9  test    eax, eax
0x1800058db  jle     short loc_1800058E6
0x1800058dd  movzx   ebx, ax
0x1800058e0  or      ebx, 80070000h
0x1800058e6  test    ebx, ebx
0x1800058e8  jns     short loc_1800058F4
0x1800058ea  mov     [rsp+38h+var_18], 11FDh
0x1800058f2  jmp     short loc_180005946
0x1800058f4  test    rsi, rsi
0x1800058f7  jnz     short loc_180005900
0x1800058f9  mov     ebx, 80070057h
0x1800058fe  jmp     short loc_18000595B
0x180005900  mov     rcx, rsi
0x180005903  call    cs:__imp_EdpWriteSiteLearningLog
0x18000590a  nop     dword ptr [rax+rax+00h]
0x18000590f  mov     ebx, eax
0x180005911  test    eax, eax
0x180005913  jle     short loc_18000591E
0x180005915  movzx   ebx, ax
0x180005918  or      ebx, 80070000h
0x18000591e  test    ebx, ebx
0x180005920  jns     short loc_18000595B
0x180005922  mov     [rsp+38h+var_18], 1203h
0x18000592a  jmp     short loc_180005946
0x18000592c  mov     ebx, 80070005h
0x180005931  jmp     short loc_18000593E
0x180005933  jle     short loc_18000593E
0x180005935  movzx   ebx, ax
0x180005938  or      ebx, 80070000h
0x18000593e  mov     [rsp+38h+var_18], 11F8h
0x180005946  mov     r9d, 6
0x18000594c  lea     rdx, EFS_API_ERROR
0x180005953  mov     r8d, ebx
0x180005956  call    fnEfsLogTrace1
0x18000595b  mov     eax, ebx
0x18000595d  mov     rbx, [rsp+38h+arg_0]
0x180005962  add     rsp, 30h
0x180005966  pop     rsi
0x180005967  retn
```
