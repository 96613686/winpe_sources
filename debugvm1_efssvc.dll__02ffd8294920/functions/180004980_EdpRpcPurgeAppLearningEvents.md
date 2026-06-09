# EdpRpcPurgeAppLearningEvents

- ea: `0x180004980`
- end: `0x180004a21`
- name: `EdpRpcPurgeAppLearningEvents`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x180004980`
- `0x18000b308`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004993`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004993`
- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x1800049c7`
- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x1800049c7`

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
0x180004980  push    rbx
0x180004982  sub     rsp, 30h
0x180004986  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x18000498b  mov     [rsp+38h+ClientLocalFlag], 0
0x180004993  call    cs:__imp_I_RpcBindingIsClientLocal
0x180004999  mov     ebx, eax
0x18000499b  test    eax, eax
0x18000499d  jnz     short loc_1800049F1
0x18000499f  cmp     [rsp+38h+ClientLocalFlag], eax
0x1800049a3  jz      short loc_1800049EA
0x1800049a5  call    EfsEnforceClientAuthentication
0x1800049aa  mov     ebx, eax
0x1800049ac  test    eax, eax
0x1800049ae  jle     short loc_1800049B9
0x1800049b0  movzx   ebx, ax
0x1800049b3  or      ebx, 80070000h
0x1800049b9  test    ebx, ebx
0x1800049bb  jns     short loc_1800049C7
0x1800049bd  mov     [rsp+38h+var_18], 11B5h
0x1800049c5  jmp     short loc_180004A04
0x1800049c7  call    cs:__imp_EdpDllPurgeAppLearningEvents
0x1800049cd  mov     ebx, eax
0x1800049cf  test    eax, eax
0x1800049d1  jle     short loc_1800049DC
0x1800049d3  movzx   ebx, ax
0x1800049d6  or      ebx, 80070000h
0x1800049dc  test    ebx, ebx
0x1800049de  jns     short loc_180004A19
0x1800049e0  mov     [rsp+38h+var_18], 11BAh
0x1800049e8  jmp     short loc_180004A04
0x1800049ea  mov     ebx, 80070005h
0x1800049ef  jmp     short loc_1800049FC
0x1800049f1  jle     short loc_1800049FC
0x1800049f3  movzx   ebx, ax
0x1800049f6  or      ebx, 80070000h
0x1800049fc  mov     [rsp+38h+var_18], 11B0h
0x180004a04  mov     r9d, 6
0x180004a0a  lea     rdx, EFS_API_ERROR
0x180004a11  mov     r8d, ebx
0x180004a14  call    fnEfsLogTrace1
0x180004a19  mov     eax, ebx
0x180004a1b  add     rsp, 30h
0x180004a1f  pop     rbx
0x180004a20  retn
```
