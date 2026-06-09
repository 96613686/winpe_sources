# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetOwnerFromFilePasteInformation(PPID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x1801e46ec`
- end: `0x1801e49a2`
- name: `?GetOwnerFromFilePasteInformation@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEBA?AV?$optional@UPPID@@@std@@AEBUPPID@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@_N@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801d7aa0`

## callees

- `0x18001bad0`
- `0x1800809d0`
- `0x18008ac70`
- `0x1800abfc8`
- `0x1800b7ed0`
- `0x18010cb40`
- `0x1801e46ec`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1801e48e8`
- `KERNEL32!CompareStringOrdinal` at `0x1801e48e8`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e47a8`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e47cd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4830`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4855`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e48a2`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4911`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4930`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e47a8`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e47cd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4830`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4855`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e48a2`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4911`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e4930`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801e4876`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801e4876`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetOwnerFromFilePasteInformation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5)
{
  __int64 v10; // rsi
  unsigned __int64 v11; // r9
  __int64 v12; // r14
  __int64 v13; // r15
  const WCHAR *v14; // r8
  const WCHAR *v15; // rcx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-68h] BYREF
  char v17; // [rsp+38h] [rbp-60h]
  __int64 v18; // [rsp+40h] [rbp-58h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-48h] BYREF

  v18 = a2;
  if ( !(unsigned __int8)Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::ClipboardFlags,void,void>(a1, 2) )
  {
LABEL_40:
    *(_BYTE *)(a2 + 12) = 0;
    return a2;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(
    &SRWLock,
    a1 + 464);
  SystemTimeAsFileTime = 0;
  std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
    a1 + 200,
    &SystemTimeAsFileTime,
    a3);
  if ( SystemTimeAsFileTime == *(_QWORD *)(a1 + 208) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
        *(unsigned int *)(a3 + 8));
    *(_BYTE *)(a2 + 12) = 0;
    if ( v17 )
      ReleaseSRWLockShared(SRWLock);
    return a2;
  }
  if ( *(_DWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 160LL) != 20 )
  {
    *(_BYTE *)(a2 + 12) = 0;
    if ( v17 )
      ReleaseSRWLockShared(SRWLock);
    return a2;
  }
  v10 = (a5 != 0 ? 0x38 : 0) + *(_QWORD *)&SystemTimeAsFileTime + 880LL;
  if ( !*(_BYTE *)(v10 + 64) )
  {
LABEL_38:
    if ( v17 )
      ReleaseSRWLockShared(SRWLock);
    goto LABEL_40;
  }
  SystemTimeAsFileTime = 0;
  std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
    a1 + 200,
    &SystemTimeAsFileTime,
    v10 + 16);
  if ( SystemTimeAsFileTime == *(_QWORD *)(a1 + 208) )
  {
    *(_BYTE *)(a2 + 12) = 0;
    if ( v17 )
      ReleaseSRWLockShared(SRWLock);
    return a2;
  }
  if ( *(_DWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 160LL) != 12 )
  {
    *(_BYTE *)(a2 + 12) = 0;
    if ( v17 )
      ReleaseSRWLockShared(SRWLock);
    return a2;
  }
  if ( !a5
    || (SystemTimeAsFileTime = 0,
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
        (int)RealtimeProtection::DlpUtils::CompareFileTimeByMs(
               (RealtimeProtection::DlpUtils *)(v10 + 28),
               &SystemTimeAsFileTime,
               (const struct _FILETIME *)0x2710,
               v11) >= 0) )
  {
    v12 = *(_QWORD *)(v10 + 40);
    v13 = *(_QWORD *)(v10 + 48);
    while ( v12 != v13 )
    {
      v14 = (const WCHAR *)a4;
      if ( *(_QWORD *)(a4 + 24) > 7u )
        v14 = *(const WCHAR **)a4;
      v15 = (const WCHAR *)v12;
      if ( *(_QWORD *)(v12 + 24) > 7u )
        v15 = *(const WCHAR **)v12;
      if ( CompareStringOrdinal(v15, -1, v14, -1, 1) == 2 )
      {
        *(_QWORD *)a2 = *(_QWORD *)(v10 + 16);
        *(_DWORD *)(a2 + 8) = *(_DWORD *)(v10 + 24);
        *(_BYTE *)(a2 + 12) = 1;
        if ( v17 )
          ReleaseSRWLockShared(SRWLock);
        return a2;
      }
      v12 += 144;
    }
    goto LABEL_38;
  }
  *(_BYTE *)(a2 + 12) = 0;
  if ( v17 )
    ReleaseSRWLockShared(SRWLock);
  return a2;
}

```

## disassembly

```asm
0x1801e46ec  push    rbx
0x1801e46ee  push    rsi
0x1801e46ef  push    rdi
0x1801e46f0  push    r12
0x1801e46f2  push    r14
0x1801e46f4  push    r15
0x1801e46f6  sub     rsp, 68h
0x1801e46fa  mov     rax, cs:__security_cookie
0x1801e4701  xor     rax, rsp
0x1801e4704  mov     [rsp+98h+var_40], rax
0x1801e4709  mov     r12, r9
0x1801e470c  mov     rsi, r8
0x1801e470f  mov     rdi, rdx
0x1801e4712  mov     r14, rcx
0x1801e4715  mov     [rsp+98h+var_58], rdx
0x1801e471a  mov     edx, 2
0x1801e471f  call    ??$GetFlag@W4ClipboardFlags@FeatureControl@Dlp@@XX@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@W4ClipboardFlags@01@@Z; Dlp::FeatureControl::GetFlag<Dlp::FeatureControl::ClipboardFlags,void,void>(FeatureControlEnum,Dlp::FeatureControl::ClipboardFlags)
0x1801e4724  xor     ebx, ebx
0x1801e4726  test    al, al
0x1801e4728  jz      loc_1801E4981
0x1801e472e  lea     rdx, [r14+1D0h]
0x1801e4735  lea     rcx, [rsp+98h+SRWLock]
0x1801e473a  call    ??0?$CGenericAutoLock@U?$CMpReadLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x1801e473f  nop
0x1801e4740  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1801e4745  lea     r15, [r14+0C8h]
0x1801e474c  mov     r8, rsi
0x1801e474f  lea     rdx, [rsp+98h+SystemTimeAsFileTime]
0x1801e4754  mov     rcx, r15
0x1801e4757  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x1801e475c  mov     rax, qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x1801e4761  cmp     rax, [r14+0D0h]
0x1801e4768  jnz     short loc_1801E47B6
0x1801e476a  lea     rax, WPP_GLOBAL_Control
0x1801e4771  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e4778  cmp     rcx, rax
0x1801e477b  jz      short loc_1801E479A
0x1801e477d  test    byte ptr [rcx+1Ch], 2
0x1801e4781  jz      short loc_1801E479A
0x1801e4783  lea     edx, [rbx+7Ah]
0x1801e4786  mov     r9d, [rsi+8]
0x1801e478a  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1801e4791  mov     rcx, [rcx+10h]
0x1801e4795  call    WPP_SF_d
0x1801e479a  mov     [rdi+0Ch], bl
0x1801e479d  cmp     [rsp+98h+var_60], bl
0x1801e47a1  jz      short loc_1801E47AE
0x1801e47a3  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e47a8  call    cs:__imp_ReleaseSRWLockShared
0x1801e47ae  mov     rax, rdi
0x1801e47b1  jmp     loc_1801E4987
0x1801e47b6  cmp     dword ptr [rax+0A0h], 14h
0x1801e47bd  jz      short loc_1801E47DB
0x1801e47bf  mov     [rdi+0Ch], bl
0x1801e47c2  cmp     [rsp+98h+var_60], bl
0x1801e47c6  jz      short loc_1801E47D3
0x1801e47c8  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e47cd  call    cs:__imp_ReleaseSRWLockShared
0x1801e47d3  mov     rax, rdi
0x1801e47d6  jmp     loc_1801E4987
0x1801e47db  mov     dl, [rsp+98h+arg_20]
0x1801e47e2  neg     dl
0x1801e47e4  sbb     r8, r8
0x1801e47e7  and     r8d, 38h
0x1801e47eb  lea     rsi, [rax+370h]
0x1801e47f2  add     rsi, r8
0x1801e47f5  cmp     [rsi+40h], bl
0x1801e47f8  jz      loc_1801E4925
0x1801e47fe  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1801e4803  lea     r8, [rsi+10h]
0x1801e4807  lea     rdx, [rsp+98h+SystemTimeAsFileTime]
0x1801e480c  mov     rcx, r15
0x1801e480f  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x1801e4814  mov     rax, qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x1801e4819  cmp     rax, [r14+0D0h]
0x1801e4820  jnz     short loc_1801E483E
0x1801e4822  mov     [rdi+0Ch], bl
0x1801e4825  cmp     [rsp+98h+var_60], bl
0x1801e4829  jz      short loc_1801E4836
0x1801e482b  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e4830  call    cs:__imp_ReleaseSRWLockShared
0x1801e4836  mov     rax, rdi
0x1801e4839  jmp     loc_1801E4987
0x1801e483e  cmp     dword ptr [rax+0A0h], 0Ch
0x1801e4845  jz      short loc_1801E4863
0x1801e4847  mov     [rdi+0Ch], bl
0x1801e484a  cmp     [rsp+98h+var_60], bl
0x1801e484e  jz      short loc_1801E485B
0x1801e4850  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e4855  call    cs:__imp_ReleaseSRWLockShared
0x1801e485b  mov     rax, rdi
0x1801e485e  jmp     loc_1801E4987
0x1801e4863  cmp     [rsp+98h+arg_20], bl
0x1801e486a  jz      short loc_1801E48B0
0x1801e486c  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1801e4871  lea     rcx, [rsp+98h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801e4876  call    cs:__imp_GetSystemTimeAsFileTime
0x1801e487c  lea     rcx, [rsi+1Ch]; this
0x1801e4880  mov     r8d, 2710h; struct _FILETIME *
0x1801e4886  lea     rdx, [rsp+98h+SystemTimeAsFileTime]; struct _FILETIME *
0x1801e488b  call    ?CompareFileTimeByMs@DlpUtils@RealtimeProtection@@YAHAEBU_FILETIME@@0_K@Z; RealtimeProtection::DlpUtils::CompareFileTimeByMs(_FILETIME const &,_FILETIME const &,unsigned __int64)
0x1801e4890  test    eax, eax
0x1801e4892  jns     short loc_1801E48B0
0x1801e4894  mov     [rdi+0Ch], bl
0x1801e4897  cmp     [rsp+98h+var_60], bl
0x1801e489b  jz      short loc_1801E48A8
0x1801e489d  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e48a2  call    cs:__imp_ReleaseSRWLockShared
0x1801e48a8  mov     rax, rdi
0x1801e48ab  jmp     loc_1801E4987
0x1801e48b0  mov     r14, [rsi+28h]
0x1801e48b4  mov     r15, [rsi+30h]
0x1801e48b8  cmp     r14, r15
0x1801e48bb  jz      short loc_1801E4925
0x1801e48bd  mov     r8, r12
0x1801e48c0  cmp     qword ptr [r12+18h], 7
0x1801e48c6  jbe     short loc_1801E48CC
0x1801e48c8  mov     r8, [r12]; lpString2
0x1801e48cc  mov     rcx, r14
0x1801e48cf  cmp     qword ptr [r14+18h], 7
0x1801e48d4  jbe     short loc_1801E48D9
0x1801e48d6  mov     rcx, [r14]; lpString1
0x1801e48d9  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x1801e48e1  or      r9d, 0FFFFFFFFh; cchCount2
0x1801e48e5  or      edx, r9d; cchCount1
0x1801e48e8  call    cs:__imp_CompareStringOrdinal
0x1801e48ee  cmp     eax, 2
0x1801e48f1  jnz     short loc_1801E491C
0x1801e48f3  movsd   xmm0, qword ptr [rsi+10h]
0x1801e48f8  movsd   qword ptr [rdi], xmm0
0x1801e48fc  mov     eax, [rsi+18h]
0x1801e48ff  mov     [rdi+8], eax
0x1801e4902  mov     byte ptr [rdi+0Ch], 1
0x1801e4906  cmp     [rsp+98h+var_60], bl
0x1801e490a  jz      short loc_1801E4917
0x1801e490c  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e4911  call    cs:__imp_ReleaseSRWLockShared
0x1801e4917  mov     rax, rdi
0x1801e491a  jmp     short loc_1801E4987
0x1801e491c  add     r14, 90h
0x1801e4923  jmp     short loc_1801E48B8
0x1801e4925  cmp     [rsp+98h+var_60], bl
0x1801e4929  jz      short loc_1801E4937
0x1801e492b  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1801e4930  call    cs:__imp_ReleaseSRWLockShared
0x1801e4936  nop
0x1801e4937  jmp     short loc_1801E4981
0x1801e4939  xor     ebx, ebx
0x1801e493b  mov     r9d, [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x1801e4940  jmp     short loc_1801E494E
0x1801e4942  mov     r9d, [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x1801e4947  xor     ebx, ebx
0x1801e4949  test    r9d, r9d
0x1801e494c  jns     short loc_1801E497C
0x1801e494e  lea     rax, WPP_GLOBAL_Control
0x1801e4955  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e495c  cmp     rcx, rax
0x1801e495f  jz      short loc_1801E497C
0x1801e4961  test    byte ptr [rcx+1Ch], 1
0x1801e4965  jz      short loc_1801E497C
0x1801e4967  mov     edx, 7Bh ; '{'
0x1801e496c  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1801e4973  mov     rcx, [rcx+10h]
0x1801e4977  call    WPP_SF_d
0x1801e497c  mov     rdi, [rsp+98h+var_58]
0x1801e4981  mov     [rdi+0Ch], bl
0x1801e4984  mov     rax, rdi
0x1801e4987  mov     rcx, [rsp+98h+var_40]
0x1801e498c  xor     rcx, rsp; StackCookie
0x1801e498f  call    __security_check_cookie
0x1801e4994  add     rsp, 68h
0x1801e4998  pop     r15
0x1801e499a  pop     r14
0x1801e499c  pop     r12
0x1801e499e  pop     rdi
0x1801e499f  pop     rsi
0x1801e49a0  pop     rbx
0x1801e49a1  retn
```
