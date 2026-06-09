# SvrImpl_FWDeleteAllAuthenticationSets(void *,void *,_tag_FW_IPSEC_PHASE)

- ea: `0x18009866c`
- end: `0x1800989b6`
- name: `?SvrImpl_FWDeleteAllAuthenticationSets@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@@Z`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800c06e0`

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
- `0x18009866c`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180098758`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180098758`
- `fwbase!FwChangeSourceSignal` at `0x1800988df`
- `fwbase!FwChangeSourceSignal` at `0x1800988df`
- `fwbase!FwHResultToWindowsError` at `0x1800988e7`
- `fwbase!FwHResultToWindowsError` at `0x180098950`
- `fwbase!FwHResultToWindowsError` at `0x180098994`
- `fwbase!FwHResultToWindowsError` at `0x1800988e7`
- `fwbase!FwHResultToWindowsError` at `0x180098950`
- `fwbase!FwHResultToWindowsError` at `0x180098994`
- `fwbase!FwFree` at `0x180098981`
- `fwbase!FwFree` at `0x18009898c`
- `fwbase!FwFree` at `0x180098981`
- `fwbase!FwFree` at `0x18009898c`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x180098829`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x180098829`

## string_xrefs

- `0x1800986d6`: `SvrImpl_FWDeleteAllAuthenticationSets`
- `0x1800986f5`: `SvrImpl_FWDeleteAllAuthenticationSets`
- `0x1800988c0`: `SvrImpl_FWDeleteAllAuthenticationSets`
- `0x1800988cf`: `SvrImpl_FWDeleteAllAuthenticationSets`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAllAuthenticationSets(void *a1, __int64 a2, unsigned int a3)
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 315, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAllAuthenticationSets");
  if ( (int)result >= 0 )
  {
    v7 = FwLock();
    if ( v7 < 0 )
    {
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllAuthenticationSets");
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
      v12 = 316;
LABEL_11:
      v13 = (unsigned int)RPCClientSID;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v13);
LABEL_40:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllAuthenticationSets");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllAuthenticationSets");
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
      FwLogBatchUpdateCSObjects(WFAllAuthenticationSetsDeletedEvent0, v18, v17, a3, v8, v15);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v22 )
          v16 = v22;
        v19 = FwHResultToWindowsError(v10);
        WPP_SF_DSDD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 323, v20, v19, (__int64)v16, a3, v8);
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
        if ( !(unsigned int)FwAnyNonDefaultSetsAreInUse(*(_QWORD *)(a2 + 8), 0, a3) )
        {
          if ( *(_QWORD *)a2
            && (RPCClientSID = FwDeleteAllSets(*(_QWORD *)a2, 0, a3), v10 = RPCClientSID, RPCClientSID < 0) )
          {
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 321;
          }
          else
          {
            RPCClientSID = FwIncrmDeleteAllSets(*(_QWORD *)(a2 + 8), *(unsigned int *)(a2 + 16), 0, a3);
            v10 = RPCClientSID;
            if ( RPCClientSID >= 0 )
            {
              v14 = FwStringTableFind(&dword_18012E020, 23173);
              FwAuditLogRuleChange((unsigned int)*v21, 0x7FFFFFFF, 4, 1, v14, 0);
              goto LABEL_40;
            }
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 322;
          }
          goto LABEL_11;
        }
        v10 = -2147022494;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 320;
      }
      else
      {
        v10 = -2147024846;
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 319;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 317);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = -2147024891;
      if ( (_UNKNOWN *)v11 == &WPP_GLOBAL_Control || (*(_BYTE *)(v11 + 28) & 1) == 0 )
        goto LABEL_40;
      v12 = 318;
    }
    v13 = v10;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009866c  push    rbx
0x18009866e  push    rbp
0x18009866f  push    rsi
0x180098670  push    rdi
0x180098671  push    r12
0x180098673  push    r13
0x180098675  push    r14
0x180098677  sub     rsp, 60h
0x18009867b  mov     rax, cs:__security_cookie
0x180098682  xor     rax, rsp
0x180098685  mov     [rsp+98h+var_48], rax
0x18009868a  mov     r14d, r8d
0x18009868d  mov     [rsp+98h+var_58], 0
0x180098696  mov     rdi, rdx
0x180098699  mov     [rsp+98h+var_50], 0
0x1800986a2  mov     rbp, rcx
0x1800986a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800986ac  lea     r12, WPP_GLOBAL_Control
0x1800986b3  lea     r13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800986ba  cmp     rcx, r12
0x1800986bd  jz      short loc_1800986D6
0x1800986bf  test    byte ptr [rcx+1Ch], 8
0x1800986c3  jz      short loc_1800986D6
0x1800986c5  mov     rcx, [rcx+10h]
0x1800986c9  mov     edx, 13Bh
0x1800986ce  mov     r8, r13
0x1800986d1  call    WPP_SF_
0x1800986d6  lea     rcx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x1800986dd  call    FwAcquireRPCSharedLock
0x1800986e2  test    eax, eax
0x1800986e4  js      loc_18009899A
0x1800986ea  call    FwLock
0x1800986ef  mov     ebx, eax
0x1800986f1  test    eax, eax
0x1800986f3  jns     short loc_180098708
0x1800986f5  lea     rcx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x1800986fc  call    FwReleaseRPCSharedLock
0x180098701  mov     eax, ebx
0x180098703  jmp     loc_18009899A
0x180098708  lea     rdx, [rsp+98h+var_58]
0x18009870d  mov     rcx, rbp
0x180098710  xor     esi, esi
0x180098712  call    ExtractRPCClientSID
0x180098717  mov     ebx, eax
0x180098719  test    eax, eax
0x18009871b  jns     short loc_180098750
0x18009871d  mov     rcx, cs:WPP_GLOBAL_Control
0x180098724  cmp     rcx, r12
0x180098727  jz      loc_1800988C0
0x18009872d  test    byte ptr [rcx+1Ch], 1
0x180098731  jz      loc_1800988C0
0x180098737  mov     edx, 13Ch
0x18009873c  mov     r9d, eax
0x18009873f  mov     rcx, [rcx+10h]
0x180098743  mov     r8, r13
0x180098746  call    WPP_SF_d
0x18009874b  jmp     loc_1800988C0
0x180098750  lea     rdx, [rsp+98h+var_50]
0x180098755  mov     rcx, rbp
0x180098758  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009875e  mov     r9d, [rdi+18h]
0x180098762  cmp     r9d, 2
0x180098766  jz      short loc_1800987B1
0x180098768  mov     rcx, cs:WPP_GLOBAL_Control
0x18009876f  cmp     rcx, r12
0x180098772  jz      short loc_18009878F
0x180098774  test    byte ptr [rcx+1Ch], 1
0x180098778  jz      short loc_18009878F
0x18009877a  mov     rcx, [rcx+10h]
0x18009877e  mov     edx, 13Dh
0x180098783  call    WPP_SF_l
0x180098788  mov     rcx, cs:WPP_GLOBAL_Control
0x18009878f  mov     ebx, 80070005h
0x180098794  cmp     rcx, r12
0x180098797  jz      loc_1800988C0
0x18009879d  test    byte ptr [rcx+1Ch], 1
0x1800987a1  jz      loc_1800988C0
0x1800987a7  mov     edx, 13Eh
0x1800987ac  mov     r9d, ebx
0x1800987af  jmp     short loc_18009873F
0x1800987b1  mov     esi, [rdi+10h]
0x1800987b4  cmp     esi, 2
0x1800987b7  jz      short loc_1800987E4
0x1800987b9  cmp     esi, 5
0x1800987bc  jz      short loc_1800987E4
0x1800987be  mov     ebx, 80070032h
0x1800987c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800987ca  cmp     rcx, r12
0x1800987cd  jz      loc_1800988C0
0x1800987d3  test    byte ptr [rcx+1Ch], 1
0x1800987d7  jz      loc_1800988C0
0x1800987dd  mov     edx, 13Fh
0x1800987e2  jmp     short loc_1800987AC
0x1800987e4  mov     rcx, [rdi+8]
0x1800987e8  mov     r8d, r14d
0x1800987eb  xor     edx, edx
0x1800987ed  call    FwAnyNonDefaultSetsAreInUse
0x1800987f2  test    eax, eax
0x1800987f4  jz      short loc_18009881C
0x1800987f6  mov     ebx, 80070962h
0x1800987fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180098802  cmp     rcx, r12
0x180098805  jz      loc_1800988C0
0x18009880b  test    byte ptr [rcx+1Ch], 1
0x18009880f  jz      loc_1800988C0
0x180098815  mov     edx, 140h
0x18009881a  jmp     short loc_1800987AC
0x18009881c  mov     rcx, [rdi]
0x18009881f  test    rcx, rcx
0x180098822  jz      short loc_180098851
0x180098824  mov     r8d, r14d
0x180098827  xor     edx, edx
0x180098829  call    cs:__imp_FwDeleteAllSets
0x18009882f  mov     ebx, eax
0x180098831  test    eax, eax
0x180098833  jns     short loc_180098851
0x180098835  mov     rcx, cs:WPP_GLOBAL_Control
0x18009883c  cmp     rcx, r12
0x18009883f  jz      short loc_1800988C0
0x180098841  test    byte ptr [rcx+1Ch], 1
0x180098845  jz      short loc_1800988C0
0x180098847  mov     edx, 141h
0x18009884c  jmp     loc_18009873C
0x180098851  mov     edx, [rdi+10h]
0x180098854  mov     r9d, r14d
0x180098857  mov     rcx, [rdi+8]
0x18009885b  xor     r8d, r8d
0x18009885e  call    FwIncrmDeleteAllSets
0x180098863  mov     ebx, eax
0x180098865  test    eax, eax
0x180098867  jns     short loc_180098885
0x180098869  mov     rcx, cs:WPP_GLOBAL_Control
0x180098870  cmp     rcx, r12
0x180098873  jz      short loc_1800988C0
0x180098875  test    byte ptr [rcx+1Ch], 1
0x180098879  jz      short loc_1800988C0
0x18009887b  mov     edx, 142h
0x180098880  jmp     loc_18009873C
0x180098885  mov     edx, 5A85h
0x18009888a  lea     rcx, dword_18012E020
0x180098891  call    FwStringTableFind
0x180098896  mov     rcx, [rsp+98h+var_58]
0x18009889b  mov     r9d, 1
0x1800988a1  mov     [rsp+98h+var_70], 0
0x1800988aa  mov     edx, 7FFFFFFFh
0x1800988af  mov     [rsp+98h+var_78], rax
0x1800988b4  mov     rcx, [rcx]
0x1800988b7  lea     r8d, [r9+3]
0x1800988bb  call    FwAuditLogRuleChange
0x1800988c0  lea     rdx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x1800988c7  mov     rcx, rbp; void *
0x1800988ca  call    FwUnlockInternal
0x1800988cf  lea     rcx, aSvrimplFwdelet_2; "SvrImpl_FWDeleteAllAuthenticationSets"
0x1800988d6  call    FwReleaseRPCSharedLock
0x1800988db  test    ebx, ebx
0x1800988dd  js      short loc_1800988E5
0x1800988df  call    cs:__imp_FwChangeSourceSignal
0x1800988e5  mov     ecx, ebx
0x1800988e7  call    cs:__imp_FwHResultToWindowsError
0x1800988ed  mov     rcx, [rsp+98h+var_50]
0x1800988f2  lea     rdi, qword_1800F5F90
0x1800988f9  mov     rdx, [rsp+98h+var_58]
0x1800988fe  test    rcx, rcx
0x180098901  mov     r8, rdi
0x180098904  cmovnz  r8, rcx
0x180098908  test    rdx, rdx
0x18009890b  jz      short loc_180098912
0x18009890d  mov     rdx, [rdx]
0x180098910  jmp     short loc_180098919
0x180098912  lea     rdx, aS100; "S-1-0-0"
0x180098919  mov     dword ptr [rsp+98h+var_70], eax
0x18009891d  lea     rcx, WFAllAuthenticationSetsDeletedEvent0
0x180098924  mov     r9d, r14d
0x180098927  mov     dword ptr [rsp+98h+var_78], esi
0x18009892b  call    ?FwLogBatchUpdateCSObjects@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_IPSEC_PHASE@@W4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdateCSObjects(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_IPSEC_PHASE,_tag_FW_STORE_TYPE,ulong)
0x180098930  mov     rax, cs:WPP_GLOBAL_Control
0x180098937  cmp     rax, r12
0x18009893a  jz      short loc_18009897C
0x18009893c  test    byte ptr [rax+1Ch], 4
0x180098940  jz      short loc_18009897C
0x180098942  mov     rax, [rsp+98h+var_50]
0x180098947  mov     ecx, ebx
0x180098949  test    rax, rax
0x18009894c  cmovnz  rdi, rax
0x180098950  call    cs:__imp_FwHResultToWindowsError
0x180098956  mov     rcx, cs:WPP_GLOBAL_Control
0x18009895d  mov     edx, 143h
0x180098962  mov     [rsp+98h+var_68], esi
0x180098966  mov     r9d, eax
0x180098969  mov     dword ptr [rsp+98h+var_70], r14d
0x18009896e  mov     [rsp+98h+var_78], rdi
0x180098973  mov     rcx, [rcx+10h]
0x180098977  call    WPP_SF_DSDD
0x18009897c  mov     rcx, [rsp+98h+var_58]
0x180098981  call    cs:__imp_FwFree
0x180098987  mov     rcx, [rsp+98h+var_50]
0x18009898c  call    cs:__imp_FwFree
0x180098992  mov     ecx, ebx
0x180098994  call    cs:__imp_FwHResultToWindowsError
0x18009899a  mov     rcx, [rsp+98h+var_48]
0x18009899f  xor     rcx, rsp; StackCookie
0x1800989a2  call    __security_check_cookie
0x1800989a7  add     rsp, 60h
0x1800989ab  pop     r14
0x1800989ad  pop     r13
0x1800989af  pop     r12
0x1800989b1  pop     rdi
0x1800989b2  pop     rsi
0x1800989b3  pop     rbp
0x1800989b4  pop     rbx
0x1800989b5  retn
```
