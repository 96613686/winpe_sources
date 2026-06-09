# RootRpcSecurityCallback(void *,void *)

- ea: `0x180023730`
- end: `0x1800237f8`
- name: `?RootRpcSecurityCallback@@YAJPEAX0@Z`
- size: `200`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018b58`
- `0x180018bb4`
- `0x1800231b8`
- `0x180023730`
- `0x1800238a4`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18002378d`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18002378d`

## pseudocode

```c
__int64 __fastcall RootRpcSecurityCallback(void *a1, void *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  unsigned int v4; // eax
  unsigned int ClientLocalFlag; // [rsp+50h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  v2 = 5;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids, WPP_pszIndent);
  }
  if ( !I_RpcBindingIsClientLocal(0, &ClientLocalFlag) )
  {
    if ( ClientLocalFlag )
    {
      v4 = CheckCallerPrivilege();
      v3 = 0;
      if ( !v4 )
        v2 = 0;
    }
  }
  WppTraceIndent(v3, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids,
      (_DWORD)WPP_pszIndent,
      v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180023730  mov     [rsp+arg_0], rbx
0x180023735  push    rdi
0x180023736  sub     rsp, 30h
0x18002373a  xor     edx, edx
0x18002373c  mov     [rsp+38h+ClientLocalFlag], 0
0x180023744  mov     ebx, 5
0x180023749  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002374e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023755  lea     rdi, WPP_GLOBAL_Control
0x18002375c  cmp     rcx, rdi
0x18002375f  jz      short loc_180023786
0x180023761  test    byte ptr [rcx+1Ch], 2
0x180023765  jz      short loc_180023786
0x180023767  cmp     [rcx+19h], bl
0x18002376a  jb      short loc_180023786
0x18002376c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023773  lea     edx, [rbx+5]
0x180023776  mov     rcx, [rcx+10h]
0x18002377a  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x180023781  call    WPP_SF_s
0x180023786  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x18002378b  xor     ecx, ecx; BindingHandle
0x18002378d  call    cs:__imp_I_RpcBindingIsClientLocal
0x180023793  test    eax, eax
0x180023795  jnz     short loc_1800237A9
0x180023797  cmp     [rsp+38h+ClientLocalFlag], eax
0x18002379b  jz      short loc_1800237A9
0x18002379d  call    ?CheckCallerPrivilege@@YAKXZ; CheckCallerPrivilege(void)
0x1800237a2  xor     ecx, ecx
0x1800237a4  test    eax, eax
0x1800237a6  cmovz   ebx, ecx
0x1800237a9  mov     edx, 1
0x1800237ae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800237b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237ba  cmp     rcx, rdi
0x1800237bd  jz      short loc_1800237EB
0x1800237bf  test    byte ptr [rcx+1Ch], 2
0x1800237c3  jz      short loc_1800237EB
0x1800237c5  cmp     byte ptr [rcx+19h], 5
0x1800237c9  jb      short loc_1800237EB
0x1800237cb  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800237d2  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x1800237d9  mov     rcx, [rcx+10h]
0x1800237dd  mov     edx, 0Bh
0x1800237e2  mov     [rsp+38h+var_18], ebx
0x1800237e6  call    WPP_SF_sD
0x1800237eb  mov     eax, ebx
0x1800237ed  mov     rbx, [rsp+38h+arg_0]
0x1800237f2  add     rsp, 30h
0x1800237f6  pop     rdi
0x1800237f7  retn
```
