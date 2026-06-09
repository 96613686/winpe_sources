# EdpRpcWriteLogSiteLearningEvents

- ea: `0x1800054b0`
- end: `0x18000556c`
- name: `EdpRpcWriteLogSiteLearningEvents`
- size: `188`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003604`
- `0x1800054b0`
- `0x18000b308`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800054ca`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800054ca`
- `EFSCORE!EdpWriteSiteLearningLog` at `0x18000550d`
- `EFSCORE!EdpWriteSiteLearningLog` at `0x18000550d`

## pseudocode

```c
__int64 __fastcall EdpRpcWriteLogSiteLearningEvents(void *a1, __int64 a2)
{
  RPC_STATUS IsClientLocal; // eax
  int v4; // ecx
  signed int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
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
    fnEfsLogTrace1(v4, (unsigned int)EFS_API_ERROR, v5, 6, 248);
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
        fnEfsLogTrace1(v9, (unsigned int)EFS_API_ERROR, v5, 6, 3);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, v5, 6, 253);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800054b0  mov     [rsp+arg_0], rbx
0x1800054b5  push    rsi
0x1800054b6  sub     rsp, 30h
0x1800054ba  mov     rsi, rdx
0x1800054bd  mov     [rsp+38h+ClientLocalFlag], 0
0x1800054c5  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x1800054ca  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800054d0  mov     ebx, eax
0x1800054d2  test    eax, eax
0x1800054d4  jnz     short loc_180005537
0x1800054d6  cmp     [rsp+38h+ClientLocalFlag], eax
0x1800054da  jz      short loc_180005530
0x1800054dc  call    EfsEnforceClientAuthentication
0x1800054e1  mov     ebx, eax
0x1800054e3  test    eax, eax
0x1800054e5  jle     short loc_1800054F0
0x1800054e7  movzx   ebx, ax
0x1800054ea  or      ebx, 80070000h
0x1800054f0  test    ebx, ebx
0x1800054f2  jns     short loc_1800054FE
0x1800054f4  mov     [rsp+38h+var_18], 11FDh
0x1800054fc  jmp     short loc_18000554A
0x1800054fe  test    rsi, rsi
0x180005501  jnz     short loc_18000550A
0x180005503  mov     ebx, 80070057h
0x180005508  jmp     short loc_18000555F
0x18000550a  mov     rcx, rsi
0x18000550d  call    cs:__imp_EdpWriteSiteLearningLog
0x180005513  mov     ebx, eax
0x180005515  test    eax, eax
0x180005517  jle     short loc_180005522
0x180005519  movzx   ebx, ax
0x18000551c  or      ebx, 80070000h
0x180005522  test    ebx, ebx
0x180005524  jns     short loc_18000555F
0x180005526  mov     [rsp+38h+var_18], 1203h
0x18000552e  jmp     short loc_18000554A
0x180005530  mov     ebx, 80070005h
0x180005535  jmp     short loc_180005542
0x180005537  jle     short loc_180005542
0x180005539  movzx   ebx, ax
0x18000553c  or      ebx, 80070000h
0x180005542  mov     [rsp+38h+var_18], 11F8h
0x18000554a  mov     r9d, 6
0x180005550  lea     rdx, EFS_API_ERROR
0x180005557  mov     r8d, ebx
0x18000555a  call    fnEfsLogTrace1
0x18000555f  mov     eax, ebx
0x180005561  mov     rbx, [rsp+38h+arg_0]
0x180005566  add     rsp, 30h
0x18000556a  pop     rsi
0x18000556b  retn
```
