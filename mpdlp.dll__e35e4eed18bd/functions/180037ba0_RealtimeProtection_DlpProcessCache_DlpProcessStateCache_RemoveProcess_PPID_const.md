# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveProcess(PPID const &)

- ea: `0x180037ba0`
- end: `0x180038328`
- name: `?RemoveProcess@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@@Z`
- size: `1928`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002f7f4`

## callees

- `0x180024ac0`
- `0x18002ba50`
- `0x180037754`
- `0x180037a14`
- `0x180037ba0`
- `0x180038328`
- `0x18006b2fc`
- `0x18006b350`
- `0x18006b4c8`
- `0x18006b500`
- `0x18006bb8c`
- `0x18006c3c0`
- `0x18006c458`
- `0x1800809d0`
- `0x180088980`
- `0x1800893f0`
- `0x180089534`
- `0x1800899a4`
- `0x180089bdc`
- `0x1800949a0`
- `0x1800a4a5c`
- `0x180107874`
- `0x180109324`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010ce44`
- `0x180119428`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180037bf9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180037bf9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180037ffb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800380da`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180037ffb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800380da`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180038051`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180038051`
- `KERNEL32!CompareFileTime` at `0x180037f9d`
- `KERNEL32!CompareFileTime` at `0x180037fcd`
- `KERNEL32!CompareFileTime` at `0x180037f9d`
- `KERNEL32!CompareFileTime` at `0x180037fcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveProcess(
        RTL_SRWLOCK *this,
        FILETIME *a2)
{
  FILETIME *v2; // r14
  RTL_SRWLOCK *v3; // r15
  int v4; // edi
  __int64 dwLowDateTime_high; // rax
  _QWORD *v6; // r8
  _QWORD *v7; // rcx
  _QWORD *v8; // r8
  _QWORD *v9; // rax
  __int64 v10; // rdx
  char *v11; // rbx
  char *v12; // r13
  unsigned __int64 v13; // rdi
  _QWORD *v14; // r14
  unsigned __int64 v15; // rsi
  size_t v16; // rcx
  void *v17; // r12
  FILETIME *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  bool v21; // zf
  const struct std::nothrow_t *v22; // rdx
  _BYTE *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // r15
  struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *ProcessFromCacheUnsafe; // rbx
  __int64 v30; // rdx
  PVOID Ptr; // rax
  __int64 v32; // rax
  int updated; // eax
  __int64 v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // rdx
  int v40; // [rsp+30h] [rbp-E8h]
  RTL_SRWLOCK *SRWLock; // [rsp+38h] [rbp-E0h]
  RTL_SRWLOCK *v42; // [rsp+40h] [rbp-D8h] BYREF
  RTL_SRWLOCK *v43; // [rsp+50h] [rbp-C8h] BYREF
  char v44; // [rsp+58h] [rbp-C0h]
  __int128 v45; // [rsp+60h] [rbp-B8h]
  _BYTE v46[12]; // [rsp+70h] [rbp-A8h]
  unsigned int v47; // [rsp+88h] [rbp-90h] BYREF
  FILETIME *lpFileTime1; // [rsp+90h] [rbp-88h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-68h]
  __int128 v51; // [rsp+B8h] [rbp-60h]
  unsigned __int64 v52; // [rsp+C8h] [rbp-50h]
  __int64 v53; // [rsp+D0h] [rbp-48h]
  char v54; // [rsp+D8h] [rbp-40h]

  v2 = a2;
  lpFileTime1 = a2;
  v3 = this;
  v42 = this;
  v4 = 0;
  v40 = 0;
  SRWLock = this + 58;
  v43 = this + 58;
  AcquireSRWLockExclusive(this + 58);
  v44 = 1;
  _mm_lfence();
  dwLowDateTime_high = HIBYTE(v2[1].dwLowDateTime);
  v6 = (char *)v3[20].Ptr
     + 16
     * ((unsigned __int64)v3[23].Ptr
      & (0x100000001B3LL
       * (dwLowDateTime_high
        ^ (0x100000001B3LL
         * (BYTE2(v2[1].dwLowDateTime)
          ^ (0x100000001B3LL
           * (BYTE1(v2[1].dwLowDateTime) ^ (0x100000001B3LL * (LOBYTE(v2[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL)))))))));
  v7 = (_QWORD *)v6[1];
  if ( v7 == v3[18].Ptr )
  {
LABEL_4:
    v7 = 0;
  }
  else
  {
    while ( v2[1].dwLowDateTime != *((_DWORD *)v7 + 4) )
    {
      if ( v7 == (_QWORD *)*v6 )
        goto LABEL_4;
      v7 = (_QWORD *)v7[1];
    }
  }
  if ( v7 )
  {
    v8 = (char *)v3[20].Ptr
       + 16
       * ((unsigned __int64)v3[23].Ptr
        & (0x100000001B3LL
         * (dwLowDateTime_high
          ^ (0x100000001B3LL
           * (BYTE2(v2[1].dwLowDateTime)
            ^ (0x100000001B3LL
             * (BYTE1(v2[1].dwLowDateTime) ^ (0x100000001B3LL * (LOBYTE(v2[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL)))))))));
    v9 = (_QWORD *)*v8;
    if ( (_QWORD *)v8[1] == v7 )
    {
      if ( v9 == v7 )
      {
        Ptr = v3[18].Ptr;
        *v8 = Ptr;
      }
      else
      {
        Ptr = (PVOID)v7[1];
      }
      v8[1] = Ptr;
    }
    else if ( v9 == v7 )
    {
      *v8 = *v7;
    }
    v10 = *v7;
    --v3[19].Ptr;
    *(_QWORD *)v7[1] = v10;
    *(_QWORD *)(v10 + 8) = v7[1];
    std::_Deallocate<16>(v7, 32);
  }
  v11 = *(char **)v3[70].Ptr;
LABEL_11:
  v12 = v11;
  if ( v11 != v3[70].Ptr )
  {
    v49 = *((_OWORD *)v11 + 1);
    v50 = *((_QWORD *)v11 + 4);
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v13 = *((_QWORD *)v11 + 7);
    v14 = v11 + 40;
    if ( *((_QWORD *)v11 + 8) > 7u )
      v14 = (_QWORD *)*v14;
    if ( v13 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v13 <= 7 )
    {
      v52 = *((_QWORD *)v11 + 7);
      v15 = 7;
      v53 = 7;
      v51 = *(_OWORD *)v14;
      v17 = (void *)v51;
      goto LABEL_24;
    }
    v15 = v13 | 7;
    if ( (v13 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v15 = 0x7FFFFFFFFFFFFFFELL;
      v16 = -2;
    }
    else
    {
      if ( v15 < 0xA )
        v15 = 10;
      if ( v15 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v16 = 2 * (v15 + 1);
      if ( !v16 )
      {
        v17 = 0;
LABEL_23:
        *(_QWORD *)&v51 = v17;
        v52 = v13;
        v53 = v15;
        memmove(v17, v14, 2 * v13 + 2);
LABEL_24:
        v54 = v11[72];
        v47 = 0;
        MpHashCrc32(&v47, 12);
        v18 = (FILETIME *)(2 * (v47 & *((_QWORD *)v11 + 16)));
        v19 = *((_QWORD *)v11 + 13);
        v20 = *(_QWORD *)(v19 + 16 * (v47 & *((_QWORD *)v11 + 16)) + 8);
        if ( v20 == *((_QWORD *)v11 + 11) )
        {
LABEL_25:
          v20 = 0;
          goto LABEL_26;
        }
        v27 = *(_QWORD *)(v19 + 16 * (v47 & *((_QWORD *)v11 + 16)));
        v18 = lpFileTime1;
        while ( 1 )
        {
          if ( v18[1].dwLowDateTime == *(_DWORD *)(v20 + 24) )
          {
            if ( !CompareFileTime(v18, (const FILETIME *)(v20 + 16)) )
            {
              v3 = v42;
LABEL_26:
              if ( !v20 )
                v20 = *((_QWORD *)v11 + 11);
              if ( v20 != *((_QWORD *)v11 + 11) )
                std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Erase<PPID>(
                  v11 + 80,
                  lpFileTime1);
              v21 = *((_QWORD *)v11 + 12) == 0;
              v11 = *(char **)v11;
              if ( v21 )
              {
                v32 = std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>::operator()<RealtimeProtection::FileUniqueId>(
                        v18,
                        v12 + 16);
                std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::BypassDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::BypassDescriptor>>,0>>::_Erase_bucket(
                  &v3[69],
                  v12,
                  v32 & (__int64)v3[75].Ptr);
                std::list<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>::_Unchecked_erase(&v3[70]);
                if ( !RealtimeProtection::DlpProcessCache::DlpProcessStateCache::IsFileCurrentlyProtectedUnsafe(
                        (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)v3,
                        (const struct RealtimeProtection::FileUniqueId *)&v49) )
                {
                  updated = RealtimeProtection::DlpQuarantineEngine::UpdateQuarantineItemProtectionStatus(
                              (RealtimeProtection::DlpQuarantineEngine *)&v3[77],
                              (const struct RealtimeProtection::FileUniqueId *)&v49,
                              0);
                  v40 = updated;
                  if ( updated < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        99,
                        &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
                        (unsigned int)updated);
                    v40 = 0;
                  }
                }
                v17 = (void *)v51;
                v15 = v53;
              }
              v2 = lpFileTime1;
              v4 = v40;
              if ( v15 > 7 )
              {
                v22 = (const struct std::nothrow_t *)(2 * v15 + 2);
                v23 = v17;
                if ( (unsigned __int64)v22 >= 0x1000 )
                {
                  v22 = (const struct std::nothrow_t *)(2 * v15 + 41);
                  v17 = (void *)*((_QWORD *)v17 - 1);
                  if ( (unsigned __int64)(v23 - (_BYTE *)v17 - 8) > 0x1F )
                    invoke_watson(0, 0, 0, 0, 0);
                }
                operator delete(v17, v22);
              }
              goto LABEL_11;
            }
            v18 = lpFileTime1;
          }
          if ( v20 == v27 )
          {
            v3 = v42;
            goto LABEL_25;
          }
          v20 = *(_QWORD *)(v20 + 8);
        }
      }
    }
    _mm_lfence();
    if ( v16 >= 0x1000 )
      v17 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v16, 0x7FFFFFFFFFFFFFFFLL);
    else
      v17 = operator new(v16);
    goto LABEL_23;
  }
  if ( ((__int64)v3[108].Ptr & 1) != 0 )
  {
    v34 = std::_Uhash_compare<enum DlpActionType,std::hash<enum DlpActionType>,std::equal_to<enum DlpActionType>>::operator()<enum DlpActionType>(
            0x7FFFFFFFFFFFFFFELL,
            &v2[1]);
    v36 = *(_QWORD *)(std::_Hash<std::_Umap_traits<unsigned long,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Find_last<unsigned long>(
                        &v3[33],
                        &v43,
                        v35,
                        v34)
                    + 8);
    if ( v36 )
    {
      std::_Hash<std::_Umap_traits<unsigned long,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Erase_bucket(
        &v3[33],
        v36,
        v34 & (__int64)v3[39].Ptr);
      std::list<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>::_Unchecked_erase(&v3[34]);
    }
    v38 = std::_Uhash_compare<EndpointDlp::PPID,EndpointDlp::PPIDHasher,EndpointDlp::PPIDComparer>::operator()<EndpointDlp::PPID>(
            v37,
            v2);
    v39 = *(_QWORD *)(std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                        &v3[25],
                        &v43,
                        v2,
                        v38)
                    + 8);
    if ( v39 )
    {
      std::_Hash<std::_Umap_traits<unsigned long,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>>>,0>>::_Erase_bucket(
        &v3[25],
        v39,
        v38 & (__int64)v3[31].Ptr);
      std::list<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>::_Unchecked_erase(&v3[26]);
    }
    v4 = v40;
  }
  else
  {
    v47 = 0;
    MpHashCrc32(&v47, 12);
    v24 = v3[28].Ptr;
    v25 = v24[2 * (v47 & (__int64)v3[31].Ptr) + 1];
    if ( (PVOID)v25 != v3[26].Ptr )
    {
      v26 = v24[2 * (v47 & (__int64)v3[31].Ptr)];
      while ( 1 )
      {
        if ( v2[1].dwLowDateTime == *(_DWORD *)(v25 + 24) && !CompareFileTime(v2, (const FILETIME *)(v25 + 16)) )
        {
          v4 = v40;
          goto LABEL_54;
        }
        if ( v25 == v26 )
          break;
        v25 = *(_QWORD *)(v25 + 8);
      }
      v4 = v40;
    }
    v25 = 0;
LABEL_54:
    if ( !v25 || (PVOID)v25 == v3[26].Ptr )
    {
      ReleaseSRWLockExclusive(SRWLock);
      return 1;
    }
    ProcessFromCacheUnsafe = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetProcessFromCacheUnsafe(
                               (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)v3,
                               (const struct PPID *)v2);
    lpFileTime1 = 0;
    GetSystemTimeAsFileTime((LPFILETIME)&lpFileTime1);
    *(_QWORD *)((char *)ProcessFromCacheUnsafe + 636) = lpFileTime1;
    if ( !*((_BYTE *)ProcessFromCacheUnsafe + 644) )
      *((_BYTE *)ProcessFromCacheUnsafe + 644) = 1;
    *(_QWORD *)&v45 = *(_QWORD *)((char *)ProcessFromCacheUnsafe + 132);
    *((FILETIME *)&v45 + 1) = *v2;
    *(_DWORD *)v46 = v2[1].dwLowDateTime;
    *(_QWORD *)&v46[4] = lpFileTime1;
    v30 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Try_emplace<unsigned long const &,>(
                       &v3[33],
                       &v42,
                       &v2[1]);
    *(_OWORD *)(v30 + 20) = v45;
    *(_QWORD *)(v30 + 36) = *(_QWORD *)v46;
    *(_DWORD *)(v30 + 44) = *(_DWORD *)&v46[8];
  }
  ReleaseSRWLockExclusive(SRWLock);
  if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180037ba0  mov     [rsp+arg_10], rbx
0x180037ba5  mov     [rsp+arg_18], rsi
0x180037baa  push    rdi
0x180037bab  push    r12
0x180037bad  push    r13
0x180037baf  push    r14
0x180037bb1  push    r15
0x180037bb3  sub     rsp, 0F0h
0x180037bba  mov     rax, cs:__security_cookie
0x180037bc1  xor     rax, rsp
0x180037bc4  mov     [rsp+118h+var_38], rax
0x180037bcc  mov     r14, rdx
0x180037bcf  mov     [rsp+118h+lpFileTime1], rdx
0x180037bd7  mov     r15, rcx
0x180037bda  mov     [rsp+118h+var_D8], rcx
0x180037bdf  xor     edi, edi
0x180037be1  mov     [rsp+118h+var_E8], edi
0x180037be5  lea     rax, [rcx+1D0h]
0x180037bec  mov     [rsp+118h+SRWLock], rax
0x180037bf1  mov     [rsp+118h+var_C8], rax
0x180037bf6  mov     rcx, rax; SRWLock
0x180037bf9  call    cs:__imp_AcquireSRWLockExclusive
0x180037bff  mov     al, 1
0x180037c01  mov     [rsp+118h+var_C0], al
0x180037c05  lfence
0x180037c08  movzx   edx, byte ptr [r14+8]
0x180037c0d  mov     rax, 0CBF29CE484222325h
0x180037c17  xor     rdx, rax
0x180037c1a  mov     rcx, 100000001B3h
0x180037c24  imul    rdx, rcx
0x180037c28  movzx   eax, byte ptr [r14+9]
0x180037c2d  xor     rdx, rax
0x180037c30  imul    rdx, rcx
0x180037c34  movzx   eax, byte ptr [r14+0Ah]
0x180037c39  xor     rdx, rax
0x180037c3c  imul    rdx, rcx
0x180037c40  movzx   eax, byte ptr [r14+0Bh]
0x180037c45  xor     rdx, rax
0x180037c48  imul    rdx, rcx
0x180037c4c  mov     r8, rdx
0x180037c4f  and     r8, [r15+0B8h]
0x180037c56  shl     r8, 4
0x180037c5a  add     r8, [r15+0A0h]
0x180037c61  mov     rcx, [r8+8]
0x180037c65  cmp     rcx, [r15+90h]
0x180037c6c  jz      short loc_180037C80
0x180037c6e  mov     eax, [rcx+10h]
0x180037c71  cmp     [r14+8], eax
0x180037c75  jz      short loc_180037C82
0x180037c77  cmp     rcx, [r8]
0x180037c7a  jnz     loc_1800381B7
0x180037c80  xor     ecx, ecx
0x180037c82  test    rcx, rcx
0x180037c85  jz      short loc_180037CD5
0x180037c87  and     rdx, [r15+0B8h]
0x180037c8e  shl     rdx, 4
0x180037c92  mov     r8, [r15+0A0h]
0x180037c99  add     r8, rdx
0x180037c9c  mov     rax, [r8]
0x180037c9f  cmp     [r8+8], rcx
0x180037ca3  jz      loc_1800380F0
0x180037ca9  cmp     rax, rcx
0x180037cac  jz      loc_1800381F3
0x180037cb2  mov     rdx, [rcx]
0x180037cb5  dec     qword ptr [r15+98h]
0x180037cbc  mov     rax, [rcx+8]
0x180037cc0  mov     [rax], rdx
0x180037cc3  mov     rax, [rcx+8]
0x180037cc7  mov     [rdx+8], rax
0x180037ccb  mov     edx, 20h ; ' '
0x180037cd0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180037cd5  mov     rbx, [r15+230h]
0x180037cdc  mov     rbx, [rbx]
0x180037cdf  mov     r8d, 0Ah
0x180037ce5  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180037cef  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180037cf9  mov     r13, rbx
0x180037cfc  cmp     rbx, [r15+230h]
0x180037d03  jz      loc_180037EB3
0x180037d09  movups  xmm0, xmmword ptr [rbx+10h]
0x180037d0d  movaps  [rsp+118h+var_78], xmm0
0x180037d15  mov     rax, [rbx+20h]
0x180037d19  mov     [rsp+118h+var_68], rax
0x180037d21  xorps   xmm0, xmm0
0x180037d24  movups  [rsp+118h+var_60], xmm0
0x180037d2c  xor     eax, eax
0x180037d2e  mov     [rsp+118h+var_50], rax
0x180037d36  mov     [rsp+118h+var_48], rax
0x180037d3e  mov     rdi, [rbx+38h]
0x180037d42  lea     r14, [rbx+28h]
0x180037d46  cmp     qword ptr [rbx+40h], 7
0x180037d4b  jbe     short loc_180037D50
0x180037d4d  mov     r14, [r14]
0x180037d50  cmp     rdi, rcx
0x180037d53  ja      loc_1800382A2
0x180037d59  cmp     rdi, 7
0x180037d5d  jbe     loc_180037F5D
0x180037d63  mov     rsi, rdi
0x180037d66  or      rsi, 7
0x180037d6a  cmp     rsi, rcx
0x180037d6d  ja      loc_180037F88
0x180037d73  cmp     rsi, 0Ah
0x180037d77  cmovb   rsi, r8
0x180037d7b  lea     rcx, [rsi+1]
0x180037d7f  cmp     rcx, rdx
0x180037d82  ja      loc_1800382AE
0x180037d88  add     rcx, rcx; Size
0x180037d8b  jz      loc_180037FC2
0x180037d91  lfence
0x180037d94  cmp     rcx, 1000h
0x180037d9b  jnb     loc_180037FB5
0x180037da1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037da6  mov     r12, rax
0x180037da9  mov     qword ptr [rsp+118h+var_60], r12
0x180037db1  mov     [rsp+118h+var_50], rdi
0x180037db9  mov     [rsp+118h+var_48], rsi
0x180037dc1  lea     r8, ds:2[rdi*2]; Size
0x180037dc9  mov     rdx, r14; Src
0x180037dcc  mov     rcx, r12; void *
0x180037dcf  call    memmove
0x180037dd4  movzx   eax, byte ptr [rbx+48h]
0x180037dd8  mov     [rsp+118h+var_40], al
0x180037ddf  mov     [rsp+118h+var_90], 0
0x180037dea  mov     r8, [rsp+118h+lpFileTime1]
0x180037df2  mov     edx, 0Ch
0x180037df7  lea     rcx, [rsp+118h+var_90]
0x180037dff  call    MpHashCrc32
0x180037e04  mov     eax, [rsp+118h+var_90]
0x180037e0b  mov     rcx, [rbx+80h]
0x180037e12  and     rcx, rax
0x180037e15  add     rcx, rcx
0x180037e18  mov     rax, [rbx+68h]
0x180037e1c  mov     rdi, [rax+rcx*8+8]
0x180037e21  cmp     rdi, [rbx+58h]
0x180037e25  jnz     loc_180037F32
0x180037e2b  xor     edi, edi
0x180037e2d  test    rdi, rdi
0x180037e30  jz      loc_180037F94
0x180037e36  cmp     rdi, [rbx+58h]
0x180037e3a  jz      short loc_180037E4D
0x180037e3c  mov     rdx, [rsp+118h+lpFileTime1]
0x180037e44  lea     rcx, [rbx+50h]
0x180037e48  call    ??$_Erase@UPPID@@@?$_Hash@V?$_Umap_traits@UPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@AEAA_KAEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Erase<PPID>(PPID const &)
0x180037e4d  mov     rax, [rbx]
0x180037e50  cmp     qword ptr [rbx+60h], 0
0x180037e55  mov     rbx, rax
0x180037e58  jz      loc_18003810C
0x180037e5e  cmp     rsi, 7
0x180037e62  mov     r14, [rsp+118h+lpFileTime1]
0x180037e6a  mov     edi, [rsp+118h+var_E8]
0x180037e6e  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180037e78  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180037e82  mov     r8d, 0Ah
0x180037e88  jbe     loc_180037CF9
0x180037e8e  lea     rdx, ds:2[rsi*2]; struct std::nothrow_t *
0x180037e96  mov     rax, r12
0x180037e99  cmp     rdx, 1000h
0x180037ea0  jnb     loc_1800381C0
0x180037ea6  mov     rcx, r12; void *
0x180037ea9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180037eae  jmp     loc_180037CDF
0x180037eb3  mov     eax, [r15+360h]
0x180037eba  nop
0x180037ebb  test    al, 1
0x180037ebd  jnz     loc_1800381FE
0x180037ec3  xor     esi, esi
0x180037ec5  mov     [rsp+118h+var_90], esi
0x180037ecc  mov     r8, r14
0x180037ecf  mov     edx, 0Ch
0x180037ed4  lea     rcx, [rsp+118h+var_90]
0x180037edc  call    MpHashCrc32
0x180037ee1  mov     eax, [rsp+118h+var_90]
0x180037ee8  mov     rcx, [r15+0F8h]
0x180037eef  and     rcx, rax
0x180037ef2  add     rcx, rcx
0x180037ef5  mov     rax, [r15+0E0h]
0x180037efc  mov     rbx, [rax+rcx*8+8]
0x180037f01  cmp     rbx, [r15+0D0h]
0x180037f08  jz      loc_180037FE5
0x180037f0e  mov     rdi, [rax+rcx*8]
0x180037f12  lea     rdx, [rbx+10h]; lpFileTime2
0x180037f16  mov     eax, [rdx+8]
0x180037f19  cmp     [r14+8], eax
0x180037f1d  jz      loc_180037FCA
0x180037f23  cmp     rbx, rdi
0x180037f26  jz      loc_180037FE1
0x180037f2c  mov     rbx, [rbx+8]
0x180037f30  jmp     short loc_180037F12
0x180037f32  mov     r15, [rax+rcx*8]
0x180037f36  mov     rcx, [rsp+118h+lpFileTime1]; lpFileTime1
0x180037f3e  lea     rdx, [rdi+10h]; lpFileTime2
0x180037f42  mov     eax, [rdx+8]
0x180037f45  cmp     [rcx+8], eax
0x180037f48  jz      short loc_180037F9D
0x180037f4a  cmp     rdi, r15
0x180037f4d  jnz     loc_1800381A5
0x180037f53  mov     r15, [rsp+118h+var_D8]
0x180037f58  jmp     loc_180037E2B
0x180037f5d  mov     [rsp+118h+var_50], rdi
0x180037f65  mov     esi, 7
0x180037f6a  mov     [rsp+118h+var_48], rsi
0x180037f72  movups  xmm0, xmmword ptr [r14]
0x180037f76  movups  [rsp+118h+var_60], xmm0
0x180037f7e  movq    r12, xmm0
0x180037f83  jmp     loc_180037DD4
0x180037f88  mov     rsi, rcx
0x180037f8b  lea     rcx, [rdx+rdx]
0x180037f8f  jmp     loc_180037D91
0x180037f94  mov     rdi, [rbx+58h]
0x180037f98  jmp     loc_180037E36
0x180037f9d  call    cs:__imp_CompareFileTime
0x180037fa3  test    eax, eax
0x180037fa5  jnz     loc_1800382B3
0x180037fab  mov     r15, [rsp+118h+var_D8]
0x180037fb0  jmp     loc_180037E2D
0x180037fb5  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180037fba  mov     r12, rax
0x180037fbd  jmp     loc_180037DA9
0x180037fc2  mov     r12, rax
0x180037fc5  jmp     loc_180037DA9
0x180037fca  mov     rcx, r14; lpFileTime1
0x180037fcd  call    cs:__imp_CompareFileTime
0x180037fd3  test    eax, eax
0x180037fd5  jnz     loc_180037F23
0x180037fdb  mov     edi, [rsp+118h+var_E8]
0x180037fdf  jmp     short loc_180037FE8
0x180037fe1  mov     edi, [rsp+118h+var_E8]
0x180037fe5  mov     rbx, rsi
0x180037fe8  test    rbx, rbx
0x180037feb  jz      short loc_180037FF6
0x180037fed  cmp     rbx, [r15+0D0h]
0x180037ff4  jnz     short loc_180038033
0x180037ff6  mov     rcx, [rsp+118h+SRWLock]; SRWLock
0x180037ffb  call    cs:__imp_ReleaseSRWLockExclusive
0x180038001  mov     eax, 1
0x180038006  mov     rcx, [rsp+118h+var_38]
0x18003800e  xor     rcx, rsp; StackCookie
0x180038011  call    __security_check_cookie
0x180038016  lea     r11, [rsp+118h+var_28]
0x18003801e  mov     rbx, [r11+40h]
0x180038022  mov     rsi, [r11+48h]
0x180038026  mov     rsp, r11
0x180038029  pop     r15
0x18003802b  pop     r14
0x18003802d  pop     r13
0x18003802f  pop     r12
0x180038031  pop     rdi
0x180038032  retn
0x180038033  mov     rdx, r14; struct PPID *
0x180038036  mov     rcx, r15; this
0x180038039  call    ?GetProcessFromCacheUnsafe@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAAEAUProcessEnforcementDescriptor@123@AEBUPPID@@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetProcessFromCacheUnsafe(PPID const &)
0x18003803e  mov     rbx, rax
0x180038041  mov     [rsp+118h+lpFileTime1], rsi
0x180038049  lea     rcx, [rsp+118h+lpFileTime1]; lpSystemTimeAsFileTime
0x180038051  call    cs:__imp_GetSystemTimeAsFileTime
0x180038057  mov     rax, [rsp+118h+lpFileTime1]
0x18003805f  mov     [rbx+27Ch], rax
0x180038066  cmp     [rbx+284h], sil
0x18003806d  jnz     short loc_180038076
0x18003806f  mov     byte ptr [rbx+284h], 1
0x180038076  mov     rax, [rbx+84h]
0x18003807d  mov     qword ptr [rsp+118h+var_B8], rax
0x180038082  movsd   xmm0, qword ptr [r14]
0x180038087  movsd   qword ptr [rsp+118h+var_B8+8], xmm0
0x18003808d  mov     eax, [r14+8]
0x180038091  mov     dword ptr [rsp+118h+var_A8], eax
0x180038095  mov     rax, [rsp+118h+lpFileTime1]
0x18003809d  mov     [rsp+118h+var_A8+4], rax
0x1800380a2  lea     rcx, [r15+108h]
0x1800380a9  lea     r8, [r14+8]
0x1800380ad  lea     rdx, [rsp+118h+var_D8]
0x1800380b2  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x1800380b7  mov     rdx, [rax]
0x1800380ba  movups  xmm0, [rsp+118h+var_B8]
0x1800380bf  movups  xmmword ptr [rdx+14h], xmm0
0x1800380c3  movsd   xmm1, [rsp+118h+var_A8]
0x1800380c9  movsd   qword ptr [rdx+24h], xmm1
0x1800380ce  mov     eax, [rsp+118h+var_A0]
0x1800380d2  mov     [rdx+2Ch], eax
0x1800380d5  mov     rcx, [rsp+118h+SRWLock]; SRWLock
0x1800380da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800380e0  nop
0x1800380e1  test    edi, edi
0x1800380e3  js      loc_1800382EA
0x1800380e9  mov     eax, edi
0x1800380eb  jmp     loc_180038006
0x1800380f0  cmp     rax, rcx
0x1800380f3  jnz     loc_1800381AE
0x1800380f9  mov     rax, [r15+90h]
0x180038100  mov     [r8], rax
0x180038103  mov     [r8+8], rax
0x180038107  jmp     loc_180037CB2
0x18003810c  lea     rdx, [r13+10h]
0x180038110  call    ??$?RVFileUniqueId@RealtimeProtection@@@?$_Uhash_compare@VFileUniqueId@RealtimeProtection@@UFileUniqueIdHasher@2@UFileUniqueIdComparer@2@@std@@QEBA_KAEBVFileUniqueId@RealtimeProtection@@@Z; std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>::operator()<RealtimeProtection::FileUniqueId>(RealtimeProtection::FileUniqueId const &)
0x180038115  mov     r8, [r15+258h]
0x18003811c  and     r8, rax
0x18003811f  mov     rdx, r13
0x180038122  lea     rcx, [r15+228h]
0x180038129  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UBypassDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UBypassDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UBypassDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::BypassDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::BypassDescriptor>>,0>>::_Erase_bucket(std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::BypassDescriptor>,void *> *,unsigned __int64)
0x18003812e  lea     rcx, [r15+230h]
  ... truncated ...
```
