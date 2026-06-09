# SvrImpl_FWDeleteAllCryptoSets(void *,void *,_tag_FW_IPSEC_PHASE)

- ea: `0x180098cd8`
- end: `0x18009902f`
- name: `?SvrImpl_FWDeleteAllCryptoSets@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@@Z`
- size: `855`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800c0860`

## callees

- `0x180005bc8`
- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x18003e798`
- `0x18005441c`
- `0x18006b5d8`
- `0x18006f520`
- `0x180087588`
- `0x180087d84`
- `0x18008b040`
- `0x180098cd8`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180098dc4`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180098dc4`
- `fwbase!FwChangeSourceSignal` at `0x180098f58`
- `fwbase!FwChangeSourceSignal` at `0x180098f58`
- `fwbase!FwHResultToWindowsError` at `0x180098f60`
- `fwbase!FwHResultToWindowsError` at `0x180098fc9`
- `fwbase!FwHResultToWindowsError` at `0x18009900d`
- `fwbase!FwHResultToWindowsError` at `0x180098f60`
- `fwbase!FwHResultToWindowsError` at `0x180098fc9`
- `fwbase!FwHResultToWindowsError` at `0x18009900d`
- `fwbase!FwFree` at `0x180098ffa`
- `fwbase!FwFree` at `0x180099005`
- `fwbase!FwFree` at `0x180098ffa`
- `fwbase!FwFree` at `0x180099005`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x180098e9b`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x180098e9b`

## string_xrefs

- `0x180098d42`: `SvrImpl_FWDeleteAllCryptoSets`
- `0x180098d61`: `SvrImpl_FWDeleteAllCryptoSets`
- `0x180098f39`: `SvrImpl_FWDeleteAllCryptoSets`
- `0x180098f48`: `SvrImpl_FWDeleteAllCryptoSets`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAllCryptoSets(void *a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  int v7; // ebx
  int v8; // esi
  int RPCClientSID; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdi
  const unsigned __int16 *v17; // r8
  const wchar_t *v18; // rdx
  int v19; // eax
  int v20; // r8d
  const wchar_t **v21; // [rsp+40h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+48h] [rbp-50h] BYREF

  v21 = 0;
  v22 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 363, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAllCryptoSets");
  if ( (int)result >= 0 )
  {
    v7 = FwLock();
    if ( v7 < 0 )
    {
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllCryptoSets");
      return (unsigned int)v7;
    }
    v8 = 0;
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v21);
    v10 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v12 = 364;
LABEL_11:
      v13 = (unsigned int)RPCClientSID;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v13);
LABEL_40:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllCryptoSets");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllCryptoSets");
      if ( (v10 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v15 = FwHResultToWindowsError(v10);
      v16 = &qword_1800F5F90;
      v17 = &qword_1800F5F90;
      if ( v22 )
        v17 = v22;
      if ( v21 )
        v18 = *v21;
      else
        v18 = L"S-1-0-0";
      FwLogBatchUpdateCSObjects(WFAllCryptoSetsDeletedEvent0, v18, v17, a3, v8, v15);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v22 )
          v16 = v22;
        v19 = FwHResultToWindowsError(v10);
        WPP_SF_DSDD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 371, v20, v19, (__int64)v16, a3, v8);
      }
      FwFree(v21);
      FwFree(v22);
      return FwHResultToWindowsError(v10);
    }
    FwGetRpcCallersProcessImageName(a1, &v22);
    if ( *(_DWORD *)(a2 + 24) == 2 )
    {
      v8 = *(_DWORD *)(a2 + 16);
      if ( v8 == 2 || v8 == 5 )
      {
        if ( !(unsigned int)FwAnyNonDefaultSetsAreInUse(*(_QWORD *)(a2 + 8), 1, a3) )
        {
          if ( *(_QWORD *)a2
            && (RPCClientSID = FwDeleteAllSets(*(_QWORD *)a2, 1, a3), v10 = RPCClientSID, RPCClientSID < 0) )
          {
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 369;
          }
          else
          {
            RPCClientSID = FwIncrmDeleteAllSets(*(_QWORD *)(a2 + 8), *(unsigned int *)(a2 + 16), 1, a3);
            v10 = RPCClientSID;
            if ( RPCClientSID >= 0 )
            {
              v14 = FwStringTableFind(&dword_18012E020, 23173);
              FwAuditLogRuleChange((unsigned int)*v21, 0x7FFFFFFF, 3, 1, v14, 0);
              goto LABEL_40;
            }
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 370;
          }
          goto LABEL_11;
        }
        v10 = -2147022494;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 368;
      }
      else
      {
        v10 = -2147024846;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 367;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 365);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = -2147024891;
      if ( (_UNKNOWN *)v11 == &WPP_GLOBAL_Control || (*(_BYTE *)(v11 + 28) & 1) == 0 )
        goto LABEL_40;
      v12 = 366;
    }
    v13 = v10;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x180098cd8  push    rbx
0x180098cda  push    rbp
0x180098cdb  push    rsi
0x180098cdc  push    rdi
0x180098cdd  push    r12
0x180098cdf  push    r13
0x180098ce1  push    r14
0x180098ce3  sub     rsp, 60h
0x180098ce7  mov     rax, cs:__security_cookie
0x180098cee  xor     rax, rsp
0x180098cf1  mov     [rsp+98h+var_48], rax
0x180098cf6  mov     r14d, r8d
0x180098cf9  mov     [rsp+98h+var_58], 0
0x180098d02  mov     rdi, rdx
0x180098d05  mov     [rsp+98h+var_50], 0
0x180098d0e  mov     rbp, rcx
0x180098d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180098d18  lea     r12, WPP_GLOBAL_Control
0x180098d1f  lea     r13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180098d26  cmp     rcx, r12
0x180098d29  jz      short loc_180098D42
0x180098d2b  test    byte ptr [rcx+1Ch], 8
0x180098d2f  jz      short loc_180098D42
0x180098d31  mov     rcx, [rcx+10h]
0x180098d35  mov     edx, 16Bh
0x180098d3a  mov     r8, r13
0x180098d3d  call    WPP_SF_
0x180098d42  lea     rcx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x180098d49  call    FwAcquireRPCSharedLock
0x180098d4e  test    eax, eax
0x180098d50  js      loc_180099013
0x180098d56  call    FwLock
0x180098d5b  mov     ebx, eax
0x180098d5d  test    eax, eax
0x180098d5f  jns     short loc_180098D74
0x180098d61  lea     rcx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x180098d68  call    FwReleaseRPCSharedLock
0x180098d6d  mov     eax, ebx
0x180098d6f  jmp     loc_180099013
0x180098d74  lea     rdx, [rsp+98h+var_58]
0x180098d79  mov     rcx, rbp
0x180098d7c  xor     esi, esi
0x180098d7e  call    ExtractRPCClientSID
0x180098d83  mov     ebx, eax
0x180098d85  test    eax, eax
0x180098d87  jns     short loc_180098DBC
0x180098d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180098d90  cmp     rcx, r12
0x180098d93  jz      loc_180098F39
0x180098d99  test    byte ptr [rcx+1Ch], 1
0x180098d9d  jz      loc_180098F39
0x180098da3  mov     edx, 16Ch
0x180098da8  mov     r9d, eax
0x180098dab  mov     rcx, [rcx+10h]
0x180098daf  mov     r8, r13
0x180098db2  call    WPP_SF_d
0x180098db7  jmp     loc_180098F39
0x180098dbc  lea     rdx, [rsp+98h+var_50]
0x180098dc1  mov     rcx, rbp
0x180098dc4  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180098dca  mov     r9d, [rdi+18h]
0x180098dce  cmp     r9d, 2
0x180098dd2  jz      short loc_180098E1D
0x180098dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180098ddb  cmp     rcx, r12
0x180098dde  jz      short loc_180098DFB
0x180098de0  test    byte ptr [rcx+1Ch], 1
0x180098de4  jz      short loc_180098DFB
0x180098de6  mov     rcx, [rcx+10h]
0x180098dea  mov     edx, 16Dh
0x180098def  call    WPP_SF_l
0x180098df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180098dfb  mov     ebx, 80070005h
0x180098e00  cmp     rcx, r12
0x180098e03  jz      loc_180098F39
0x180098e09  test    byte ptr [rcx+1Ch], 1
0x180098e0d  jz      loc_180098F39
0x180098e13  mov     edx, 16Eh
0x180098e18  mov     r9d, ebx
0x180098e1b  jmp     short loc_180098DAB
0x180098e1d  mov     esi, [rdi+10h]
0x180098e20  cmp     esi, 2
0x180098e23  jz      short loc_180098E50
0x180098e25  cmp     esi, 5
0x180098e28  jz      short loc_180098E50
0x180098e2a  mov     ebx, 80070032h
0x180098e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e36  cmp     rcx, r12
0x180098e39  jz      loc_180098F39
0x180098e3f  test    byte ptr [rcx+1Ch], 1
0x180098e43  jz      loc_180098F39
0x180098e49  mov     edx, 16Fh
0x180098e4e  jmp     short loc_180098E18
0x180098e50  mov     rcx, [rdi+8]
0x180098e54  mov     r8d, r14d
0x180098e57  mov     edx, 1
0x180098e5c  call    FwAnyNonDefaultSetsAreInUse
0x180098e61  test    eax, eax
0x180098e63  jz      short loc_180098E8B
0x180098e65  mov     ebx, 80070962h
0x180098e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e71  cmp     rcx, r12
0x180098e74  jz      loc_180098F39
0x180098e7a  test    byte ptr [rcx+1Ch], 1
0x180098e7e  jz      loc_180098F39
0x180098e84  mov     edx, 170h
0x180098e89  jmp     short loc_180098E18
0x180098e8b  mov     rcx, [rdi]
0x180098e8e  test    rcx, rcx
0x180098e91  jz      short loc_180098EC7
0x180098e93  mov     r8d, r14d
0x180098e96  mov     edx, 1
0x180098e9b  call    cs:__imp_FwDeleteAllSets
0x180098ea1  mov     ebx, eax
0x180098ea3  test    eax, eax
0x180098ea5  jns     short loc_180098EC7
0x180098ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180098eae  cmp     rcx, r12
0x180098eb1  jz      loc_180098F39
0x180098eb7  test    byte ptr [rcx+1Ch], 1
0x180098ebb  jz      short loc_180098F39
0x180098ebd  mov     edx, 171h
0x180098ec2  jmp     loc_180098DA8
0x180098ec7  mov     edx, [rdi+10h]
0x180098eca  mov     r9d, r14d
0x180098ecd  mov     rcx, [rdi+8]
0x180098ed1  mov     r8d, 1
0x180098ed7  call    FwIncrmDeleteAllSets
0x180098edc  mov     ebx, eax
0x180098ede  test    eax, eax
0x180098ee0  jns     short loc_180098EFE
0x180098ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180098ee9  cmp     rcx, r12
0x180098eec  jz      short loc_180098F39
0x180098eee  test    byte ptr [rcx+1Ch], 1
0x180098ef2  jz      short loc_180098F39
0x180098ef4  mov     edx, 172h
0x180098ef9  jmp     loc_180098DA8
0x180098efe  mov     edx, 5A85h
0x180098f03  lea     rcx, dword_18012E020
0x180098f0a  call    FwStringTableFind
0x180098f0f  mov     rcx, [rsp+98h+var_58]
0x180098f14  mov     r9d, 1
0x180098f1a  mov     [rsp+98h+var_70], 0
0x180098f23  mov     edx, 7FFFFFFFh
0x180098f28  mov     [rsp+98h+var_78], rax
0x180098f2d  mov     rcx, [rcx]
0x180098f30  lea     r8d, [r9+2]
0x180098f34  call    FwAuditLogRuleChange
0x180098f39  lea     rdx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x180098f40  mov     rcx, rbp; void *
0x180098f43  call    FwUnlockInternal
0x180098f48  lea     rcx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x180098f4f  call    FwReleaseRPCSharedLock
0x180098f54  test    ebx, ebx
0x180098f56  js      short loc_180098F5E
0x180098f58  call    cs:__imp_FwChangeSourceSignal
0x180098f5e  mov     ecx, ebx
0x180098f60  call    cs:__imp_FwHResultToWindowsError
0x180098f66  mov     rcx, [rsp+98h+var_50]
0x180098f6b  lea     rdi, qword_1800F5F90
0x180098f72  mov     rdx, [rsp+98h+var_58]
0x180098f77  test    rcx, rcx
0x180098f7a  mov     r8, rdi
0x180098f7d  cmovnz  r8, rcx
0x180098f81  test    rdx, rdx
0x180098f84  jz      short loc_180098F8B
0x180098f86  mov     rdx, [rdx]
0x180098f89  jmp     short loc_180098F92
0x180098f8b  lea     rdx, aS100; "S-1-0-0"
0x180098f92  mov     dword ptr [rsp+98h+var_70], eax
0x180098f96  lea     rcx, WFAllCryptoSetsDeletedEvent0
0x180098f9d  mov     r9d, r14d
0x180098fa0  mov     dword ptr [rsp+98h+var_78], esi
0x180098fa4  call    ?FwLogBatchUpdateCSObjects@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_IPSEC_PHASE@@W4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdateCSObjects(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_IPSEC_PHASE,_tag_FW_STORE_TYPE,ulong)
0x180098fa9  mov     rax, cs:WPP_GLOBAL_Control
0x180098fb0  cmp     rax, r12
0x180098fb3  jz      short loc_180098FF5
0x180098fb5  test    byte ptr [rax+1Ch], 4
0x180098fb9  jz      short loc_180098FF5
0x180098fbb  mov     rax, [rsp+98h+var_50]
0x180098fc0  mov     ecx, ebx
0x180098fc2  test    rax, rax
0x180098fc5  cmovnz  rdi, rax
0x180098fc9  call    cs:__imp_FwHResultToWindowsError
0x180098fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180098fd6  mov     edx, 173h
0x180098fdb  mov     [rsp+98h+var_68], esi
0x180098fdf  mov     r9d, eax
0x180098fe2  mov     dword ptr [rsp+98h+var_70], r14d
0x180098fe7  mov     [rsp+98h+var_78], rdi
0x180098fec  mov     rcx, [rcx+10h]
0x180098ff0  call    WPP_SF_DSDD
0x180098ff5  mov     rcx, [rsp+98h+var_58]
0x180098ffa  call    cs:__imp_FwFree
0x180099000  mov     rcx, [rsp+98h+var_50]
0x180099005  call    cs:__imp_FwFree
0x18009900b  mov     ecx, ebx
0x18009900d  call    cs:__imp_FwHResultToWindowsError
0x180099013  mov     rcx, [rsp+98h+var_48]
0x180099018  xor     rcx, rsp; StackCookie
0x18009901b  call    __security_check_cookie
0x180099020  add     rsp, 60h
0x180099024  pop     r14
0x180099026  pop     r13
0x180099028  pop     r12
0x18009902a  pop     rdi
0x18009902b  pop     rsi
0x18009902c  pop     rbp
0x18009902d  pop     rbx
0x18009902e  retn
```
