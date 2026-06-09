# SvrImpl_FWDeleteAllCryptoSets(void *,void *,_tag_FW_IPSEC_PHASE)

- ea: `0x18009de48`
- end: `0x18009e1d0`
- name: `?SvrImpl_FWDeleteAllCryptoSets@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@@Z`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800c76b0`

## callees

- `0x180005b70`
- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18003ec48`
- `0x180059714`
- `0x18006e578`
- `0x1800729c0`
- `0x18008bc14`
- `0x18008c4b8`
- `0x18008f870`
- `0x18009de48`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009e0e2`
- `fwbase!FwHResultToWindowsError` at `0x18009e151`
- `fwbase!FwHResultToWindowsError` at `0x18009e1a7`
- `fwbase!FwHResultToWindowsError` at `0x18009e0e2`
- `fwbase!FwHResultToWindowsError` at `0x18009e151`
- `fwbase!FwHResultToWindowsError` at `0x18009e1a7`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009df34`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009df34`
- `fwbase!FwChangeSourceSignal` at `0x18009e0d4`
- `fwbase!FwChangeSourceSignal` at `0x18009e0d4`
- `fwbase!FwFree` at `0x18009e188`
- `fwbase!FwFree` at `0x18009e199`
- `fwbase!FwFree` at `0x18009e188`
- `fwbase!FwFree` at `0x18009e199`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009e011`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x18009e011`

## string_xrefs

- `0x18009deb2`: `SvrImpl_FWDeleteAllCryptoSets`
- `0x18009ded1`: `SvrImpl_FWDeleteAllCryptoSets`
- `0x18009e0b5`: `SvrImpl_FWDeleteAllCryptoSets`
- `0x18009e0c4`: `SvrImpl_FWDeleteAllCryptoSets`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 363, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
      WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v13);
LABEL_40:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllCryptoSets");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllCryptoSets");
      if ( (v10 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v15 = FwHResultToWindowsError(v10);
      v16 = &qword_1800FBFF0;
      v17 = &qword_1800FBFF0;
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
              v14 = FwStringTableFind(&dword_1801341D0, 23173);
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
0x18009de48  push    rbx
0x18009de4a  push    rbp
0x18009de4b  push    rsi
0x18009de4c  push    rdi
0x18009de4d  push    r12
0x18009de4f  push    r13
0x18009de51  push    r14
0x18009de53  sub     rsp, 60h
0x18009de57  mov     rax, cs:__security_cookie
0x18009de5e  xor     rax, rsp
0x18009de61  mov     [rsp+98h+var_48], rax
0x18009de66  mov     r14d, r8d
0x18009de69  mov     [rsp+98h+var_58], 0
0x18009de72  mov     rdi, rdx
0x18009de75  mov     [rsp+98h+var_50], 0
0x18009de7e  mov     rbp, rcx
0x18009de81  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de88  lea     r12, WPP_GLOBAL_Control
0x18009de8f  lea     r13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009de96  cmp     rcx, r12
0x18009de99  jz      short loc_18009DEB2
0x18009de9b  test    byte ptr [rcx+1Ch], 8
0x18009de9f  jz      short loc_18009DEB2
0x18009dea1  mov     rcx, [rcx+10h]
0x18009dea5  mov     edx, 16Bh
0x18009deaa  mov     r8, r13
0x18009dead  call    WPP_SF_
0x18009deb2  lea     rcx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x18009deb9  call    FwAcquireRPCSharedLock
0x18009debe  test    eax, eax
0x18009dec0  js      loc_18009E1B3
0x18009dec6  call    FwLock
0x18009decb  mov     ebx, eax
0x18009decd  test    eax, eax
0x18009decf  jns     short loc_18009DEE4
0x18009ded1  lea     rcx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x18009ded8  call    FwReleaseRPCSharedLock
0x18009dedd  mov     eax, ebx
0x18009dedf  jmp     loc_18009E1B3
0x18009dee4  lea     rdx, [rsp+98h+var_58]
0x18009dee9  mov     rcx, rbp
0x18009deec  xor     esi, esi
0x18009deee  call    ExtractRPCClientSID
0x18009def3  mov     ebx, eax
0x18009def5  test    eax, eax
0x18009def7  jns     short loc_18009DF2C
0x18009def9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df00  cmp     rcx, r12
0x18009df03  jz      loc_18009E0B5
0x18009df09  test    byte ptr [rcx+1Ch], 1
0x18009df0d  jz      loc_18009E0B5
0x18009df13  mov     edx, 16Ch
0x18009df18  mov     r9d, eax
0x18009df1b  mov     rcx, [rcx+10h]
0x18009df1f  mov     r8, r13
0x18009df22  call    WPP_SF_d
0x18009df27  jmp     loc_18009E0B5
0x18009df2c  lea     rdx, [rsp+98h+var_50]
0x18009df31  mov     rcx, rbp
0x18009df34  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009df3b  nop     dword ptr [rax+rax+00h]
0x18009df40  mov     r9d, [rdi+18h]
0x18009df44  cmp     r9d, 2
0x18009df48  jz      short loc_18009DF93
0x18009df4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df51  cmp     rcx, r12
0x18009df54  jz      short loc_18009DF71
0x18009df56  test    byte ptr [rcx+1Ch], 1
0x18009df5a  jz      short loc_18009DF71
0x18009df5c  mov     rcx, [rcx+10h]
0x18009df60  mov     edx, 16Dh
0x18009df65  call    WPP_SF_l
0x18009df6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df71  mov     ebx, 80070005h
0x18009df76  cmp     rcx, r12
0x18009df79  jz      loc_18009E0B5
0x18009df7f  test    byte ptr [rcx+1Ch], 1
0x18009df83  jz      loc_18009E0B5
0x18009df89  mov     edx, 16Eh
0x18009df8e  mov     r9d, ebx
0x18009df91  jmp     short loc_18009DF1B
0x18009df93  mov     esi, [rdi+10h]
0x18009df96  cmp     esi, 2
0x18009df99  jz      short loc_18009DFC6
0x18009df9b  cmp     esi, 5
0x18009df9e  jz      short loc_18009DFC6
0x18009dfa0  mov     ebx, 80070032h
0x18009dfa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dfac  cmp     rcx, r12
0x18009dfaf  jz      loc_18009E0B5
0x18009dfb5  test    byte ptr [rcx+1Ch], 1
0x18009dfb9  jz      loc_18009E0B5
0x18009dfbf  mov     edx, 16Fh
0x18009dfc4  jmp     short loc_18009DF8E
0x18009dfc6  mov     rcx, [rdi+8]
0x18009dfca  mov     r8d, r14d
0x18009dfcd  mov     edx, 1
0x18009dfd2  call    FwAnyNonDefaultSetsAreInUse
0x18009dfd7  test    eax, eax
0x18009dfd9  jz      short loc_18009E001
0x18009dfdb  mov     ebx, 80070962h
0x18009dfe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dfe7  cmp     rcx, r12
0x18009dfea  jz      loc_18009E0B5
0x18009dff0  test    byte ptr [rcx+1Ch], 1
0x18009dff4  jz      loc_18009E0B5
0x18009dffa  mov     edx, 170h
0x18009dfff  jmp     short loc_18009DF8E
0x18009e001  mov     rcx, [rdi]
0x18009e004  test    rcx, rcx
0x18009e007  jz      short loc_18009E043
0x18009e009  mov     r8d, r14d
0x18009e00c  mov     edx, 1
0x18009e011  call    cs:__imp_FwDeleteAllSets
0x18009e018  nop     dword ptr [rax+rax+00h]
0x18009e01d  mov     ebx, eax
0x18009e01f  test    eax, eax
0x18009e021  jns     short loc_18009E043
0x18009e023  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e02a  cmp     rcx, r12
0x18009e02d  jz      loc_18009E0B5
0x18009e033  test    byte ptr [rcx+1Ch], 1
0x18009e037  jz      short loc_18009E0B5
0x18009e039  mov     edx, 171h
0x18009e03e  jmp     loc_18009DF18
0x18009e043  mov     edx, [rdi+10h]
0x18009e046  mov     r9d, r14d
0x18009e049  mov     rcx, [rdi+8]
0x18009e04d  mov     r8d, 1
0x18009e053  call    FwIncrmDeleteAllSets
0x18009e058  mov     ebx, eax
0x18009e05a  test    eax, eax
0x18009e05c  jns     short loc_18009E07A
0x18009e05e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e065  cmp     rcx, r12
0x18009e068  jz      short loc_18009E0B5
0x18009e06a  test    byte ptr [rcx+1Ch], 1
0x18009e06e  jz      short loc_18009E0B5
0x18009e070  mov     edx, 172h
0x18009e075  jmp     loc_18009DF18
0x18009e07a  mov     edx, 5A85h
0x18009e07f  lea     rcx, dword_1801341D0
0x18009e086  call    FwStringTableFind
0x18009e08b  mov     rcx, [rsp+98h+var_58]
0x18009e090  mov     r9d, 1
0x18009e096  mov     [rsp+98h+var_70], 0
0x18009e09f  mov     edx, 7FFFFFFFh
0x18009e0a4  mov     [rsp+98h+var_78], rax
0x18009e0a9  mov     rcx, [rcx]
0x18009e0ac  lea     r8d, [r9+2]
0x18009e0b0  call    FwAuditLogRuleChange
0x18009e0b5  lea     rdx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x18009e0bc  mov     rcx, rbp; void *
0x18009e0bf  call    FwUnlockInternal
0x18009e0c4  lea     rcx, aSvrimplFwdelet_6; "SvrImpl_FWDeleteAllCryptoSets"
0x18009e0cb  call    FwReleaseRPCSharedLock
0x18009e0d0  test    ebx, ebx
0x18009e0d2  js      short loc_18009E0E0
0x18009e0d4  call    cs:__imp_FwChangeSourceSignal
0x18009e0db  nop     dword ptr [rax+rax+00h]
0x18009e0e0  mov     ecx, ebx
0x18009e0e2  call    cs:__imp_FwHResultToWindowsError
0x18009e0e9  nop     dword ptr [rax+rax+00h]
0x18009e0ee  mov     rcx, [rsp+98h+var_50]
0x18009e0f3  lea     rdi, qword_1800FBFF0
0x18009e0fa  mov     rdx, [rsp+98h+var_58]
0x18009e0ff  test    rcx, rcx
0x18009e102  mov     r8, rdi
0x18009e105  cmovnz  r8, rcx
0x18009e109  test    rdx, rdx
0x18009e10c  jz      short loc_18009E113
0x18009e10e  mov     rdx, [rdx]
0x18009e111  jmp     short loc_18009E11A
0x18009e113  lea     rdx, aS100; "S-1-0-0"
0x18009e11a  mov     dword ptr [rsp+98h+var_70], eax
0x18009e11e  lea     rcx, WFAllCryptoSetsDeletedEvent0
0x18009e125  mov     r9d, r14d
0x18009e128  mov     dword ptr [rsp+98h+var_78], esi
0x18009e12c  call    ?FwLogBatchUpdateCSObjects@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_IPSEC_PHASE@@W4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdateCSObjects(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_IPSEC_PHASE,_tag_FW_STORE_TYPE,ulong)
0x18009e131  mov     rax, cs:WPP_GLOBAL_Control
0x18009e138  cmp     rax, r12
0x18009e13b  jz      short loc_18009E183
0x18009e13d  test    byte ptr [rax+1Ch], 4
0x18009e141  jz      short loc_18009E183
0x18009e143  mov     rax, [rsp+98h+var_50]
0x18009e148  mov     ecx, ebx
0x18009e14a  test    rax, rax
0x18009e14d  cmovnz  rdi, rax
0x18009e151  call    cs:__imp_FwHResultToWindowsError
0x18009e158  nop     dword ptr [rax+rax+00h]
0x18009e15d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e164  mov     edx, 173h
0x18009e169  mov     [rsp+98h+var_68], esi
0x18009e16d  mov     r9d, eax
0x18009e170  mov     dword ptr [rsp+98h+var_70], r14d
0x18009e175  mov     [rsp+98h+var_78], rdi
0x18009e17a  mov     rcx, [rcx+10h]
0x18009e17e  call    WPP_SF_DSDD
0x18009e183  mov     rcx, [rsp+98h+var_58]
0x18009e188  call    cs:__imp_FwFree
0x18009e18f  nop     dword ptr [rax+rax+00h]
0x18009e194  mov     rcx, [rsp+98h+var_50]
0x18009e199  call    cs:__imp_FwFree
0x18009e1a0  nop     dword ptr [rax+rax+00h]
0x18009e1a5  mov     ecx, ebx
0x18009e1a7  call    cs:__imp_FwHResultToWindowsError
0x18009e1ae  nop     dword ptr [rax+rax+00h]
0x18009e1b3  mov     rcx, [rsp+98h+var_48]
0x18009e1b8  xor     rcx, rsp; StackCookie
0x18009e1bb  call    __security_check_cookie
0x18009e1c0  add     rsp, 60h
0x18009e1c4  pop     r14
0x18009e1c6  pop     r13
0x18009e1c8  pop     r12
0x18009e1ca  pop     rdi
0x18009e1cb  pop     rsi
0x18009e1cc  pop     rbp
0x18009e1cd  pop     rbx
0x18009e1ce  retn
```
