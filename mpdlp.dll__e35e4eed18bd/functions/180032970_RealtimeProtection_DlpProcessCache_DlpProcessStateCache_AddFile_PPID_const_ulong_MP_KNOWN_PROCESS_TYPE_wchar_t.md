# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFile(PPID const &,ulong,_MP_KNOWN_PROCESS_TYPE,wchar_t const *,bool,wchar_t const *,wchar_t const *,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,ulong,DlpAction *,RealtimeProtection::MpDlpPolicyTraceInfo const &,DlpAppGroupInfo const &,bool,EndpointDlp::Client::ExtendedAttributes const &,bool)

- ea: `0x180032970`
- end: `0x1800330a5`
- name: `?AddFile@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@KW4_MP_KNOWN_PROCESS_TYPE@@PEB_W_N22AEBV?$optional@VFileUniqueId@RealtimeProtection@@@std@@KKPEAUDlpAction@@AEBUMpDlpPolicyTraceInfo@3@AEBUDlpAppGroupInfo@@3AEBUExtendedAttributes@Client@EndpointDlp@@3@Z`
- size: `1845`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801d6f7c`

## callees

- `0x18001bad0`
- `0x180020180`
- `0x18002bda4`
- `0x180032970`
- `0x180034800`
- `0x18006ad2c`
- `0x18006b2fc`
- `0x18006b350`
- `0x18006b4c8`
- `0x18006b500`
- `0x18006bb8c`
- `0x18006c3c0`
- `0x18006c458`
- `0x1800809d0`
- `0x180107874`
- `0x180109324`
- `0x18010cb40`
- `0x18010ce44`
- `0x18023a310`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180032a3b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180032a3b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032d0d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032f4c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032fe4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032d0d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032f4c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032fe4`
- `KERNEL32!CompareFileTime` at `0x180032c05`
- `KERNEL32!CompareFileTime` at `0x180032c05`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFile(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        _WORD *Src,
        char a6,
        wchar_t *a7,
        std::_Ref_count_base *a8,
        struct RealtimeProtection::FileUniqueId *a9,
        int a10,
        unsigned int a11,
        __int64 a12,
        void *a13,
        void *a14,
        char a15,
        __int64 a16,
        char a17)
{
  RTL_SRWLOCK *v21; // r15
  int v22; // r14d
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rcx
  char *v27; // rdi
  char *v28; // rbx
  __int64 v29; // rdx
  float v30; // xmm0_4
  __int64 v31; // rcx
  float v32; // xmm1_4
  __int64 v33; // rcx
  __int64 v34; // rbx
  char **v35; // r8
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r9
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rax
  _WORD *v43; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // [rsp+90h] [rbp-B8h] BYREF
  int v47; // [rsp+98h] [rbp-B0h]
  int v48; // [rsp+9Ch] [rbp-ACh]
  __int64 v49; // [rsp+A0h] [rbp-A8h]
  __int64 v50; // [rsp+A8h] [rbp-A0h]
  __int64 v51; // [rsp+B0h] [rbp-98h]
  __int64 v52; // [rsp+B8h] [rbp-90h]
  __int64 v53; // [rsp+C0h] [rbp-88h]
  __int64 v54; // [rsp+C8h] [rbp-80h]
  __int64 v55; // [rsp+D0h] [rbp-78h]
  __int64 v56; // [rsp+D8h] [rbp-70h] BYREF
  char *v57; // [rsp+E0h] [rbp-68h]
  __int64 v58; // [rsp+E8h] [rbp-60h] BYREF
  char v59; // [rsp+F0h] [rbp-58h]
  unsigned int v60; // [rsp+100h] [rbp-48h] BYREF

  v47 = a4;
  v48 = a3;
  v55 = (__int64)a7;
  v54 = (__int64)a8;
  v53 = (__int64)a9;
  v52 = a12;
  v51 = (__int64)a13;
  v50 = (__int64)a14;
  v49 = a16;
  v21 = (RTL_SRWLOCK *)(a1 + 464);
  v58 = a1 + 464;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 464));
  v59 = 1;
  v22 = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFileInternal(
          (_QWORD *)a1,
          a2,
          a3,
          a4,
          Src,
          a6,
          a7,
          a8,
          a9,
          a10,
          a11,
          a12,
          a13,
          a14,
          a15,
          a16,
          a17);
  if ( v22 >= 0 )
  {
    _mm_lfence();
    v23 = *(_QWORD *)(a1 + 288);
    v24 = *(_QWORD *)(v23
                    + 16
                    * (*(_QWORD *)(a1 + 312)
                     & (0x100000001B3LL
                      * (*(unsigned __int8 *)(a2 + 11)
                       ^ (0x100000001B3LL
                        * (*(unsigned __int8 *)(a2 + 10)
                         ^ (0x100000001B3LL
                          * (*(unsigned __int8 *)(a2 + 9)
                           ^ (0x100000001B3LL * (*(unsigned __int8 *)(a2 + 8) ^ 0xCBF29CE484222325uLL)))))))))
                    + 8);
    if ( v24 == *(_QWORD *)(a1 + 272) )
    {
LABEL_3:
      v24 = 0;
    }
    else
    {
      while ( *(_DWORD *)(a2 + 8) != *(_DWORD *)(v24 + 16) )
      {
        if ( v24 == *(_QWORD *)(v23
                              + 16
                              * (*(_QWORD *)(a1 + 312)
                               & (0x100000001B3LL
                                * (*(unsigned __int8 *)(a2 + 11)
                                 ^ (0x100000001B3LL
                                  * (*(unsigned __int8 *)(a2 + 10)
                                   ^ (0x100000001B3LL
                                    * (*(unsigned __int8 *)(a2 + 9)
                                     ^ (0x100000001B3LL * (*(unsigned __int8 *)(a2 + 8) ^ 0xCBF29CE484222325uLL)))))))))) )
          goto LABEL_3;
        v24 = *(_QWORD *)(v24 + 8);
      }
    }
    if ( v24
      && v24 != *(_QWORD *)(a1 + 272)
      && (*(_DWORD *)(v24 + 32) != *(_DWORD *)(a2 + 4) || *(_DWORD *)(v24 + 28) != *(_DWORD *)a2) )
    {
      v46 = std::_Uhash_compare<EndpointDlp::PPID,EndpointDlp::PPIDHasher,EndpointDlp::PPIDComparer>::operator()<EndpointDlp::PPID>(
              2
            * (*(_QWORD *)(a1 + 312)
             & (0x100000001B3LL
              * (*(unsigned __int8 *)(a2 + 11)
               ^ (0x100000001B3LL
                * (*(unsigned __int8 *)(a2 + 10)
                 ^ (0x100000001B3LL
                  * (*(unsigned __int8 *)(a2 + 9)
                   ^ (0x100000001B3LL * (*(unsigned __int8 *)(a2 + 8) ^ 0xCBF29CE484222325uLL))))))))),
              v24 + 28);
      v40 = *(_QWORD *)(std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                          a1 + 200,
                          &v56,
                          v24 + 28,
                          v46)
                      + 8);
      if ( v40 )
      {
        std::_Hash<std::_Umap_traits<unsigned long,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>>>,0>>::_Erase_bucket(
          a1 + 200,
          v40,
          v46 & *(_QWORD *)(a1 + 248));
        std::list<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>::_Unchecked_erase(a1 + 208);
      }
      v42 = std::_Uhash_compare<enum DlpActionType,std::hash<enum DlpActionType>,std::equal_to<enum DlpActionType>>::operator()<enum DlpActionType>(
              v41,
              v24 + 16);
      std::_Hash<std::_Umap_traits<unsigned long,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Erase_bucket(
        a1 + 264,
        v24,
        v42 & *(_QWORD *)(a1 + 312));
      std::list<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>::_Unchecked_erase(a1 + 272);
    }
    v60 = 0;
    MpHashCrc32(&v60, 12);
    v25 = 2 * (v60 & *(_QWORD *)(a1 + 248));
    v26 = *(_QWORD *)(a1 + 224);
    v27 = *(char **)(v26 + 16 * (v60 & *(_QWORD *)(a1 + 248)) + 8);
    v46 = *(_QWORD *)(a1 + 208);
    if ( v27 != (char *)v46 )
    {
      v28 = *(char **)(v26 + 8 * v25);
      while ( *(_DWORD *)(a2 + 8) != *((_DWORD *)v27 + 6)
           || CompareFileTime((const FILETIME *)a2, (const FILETIME *)v27 + 2) )
      {
        if ( v27 == v28 )
        {
          v46 = (__int64)v27;
          goto LABEL_27;
        }
        v27 = (char *)*((_QWORD *)v27 + 1);
      }
      goto LABEL_24;
    }
LABEL_27:
    if ( *(_QWORD *)(a1 + 216) == 0x41041041041041LL )
      std::_Xlength_error("unordered_map/set too long");
    v56 = a1 + 208;
    v57 = 0;
    v27 = (char *)operator new(0x3F0u);
    v57 = v27;
    *((_QWORD *)v27 + 2) = *(_QWORD *)a2;
    *((_DWORD *)v27 + 6) = *(_DWORD *)(a2 + 8);
    memset(v27 + 32, 0, 0x3D0u);
    RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor::ProcessEnforcementDescriptor((RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *)(v27 + 32));
    v29 = *(_QWORD *)(a1 + 216) + 1LL;
    if ( v29 < 0 )
      v30 = (float)(v29 & 1 | (unsigned int)((unsigned __int64)v29 >> 1))
          + (float)(v29 & 1 | (unsigned int)((unsigned __int64)v29 >> 1));
    else
      v30 = (float)(int)v29;
    v31 = *(_QWORD *)(a1 + 256);
    if ( v31 < 0 )
    {
      v44 = *(_QWORD *)(a1 + 256) & 1LL | ((unsigned __int64)v31 >> 1);
      v32 = (float)(int)v44 + (float)(int)v44;
    }
    else
    {
      v32 = (float)(int)v31;
    }
    if ( (float)(v30 / v32) > *(float *)(a1 + 200) )
    {
      v45 = std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::_Desired_grow_bucket_count(a1 + 200);
      std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::PauseResumeProcessInfo,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::PauseResumeProcessInfo>>,0>>::_Forced_rehash(
        a1 + 200,
        v45);
      v34 = v60;
      v33 = *(_QWORD *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                         a1 + 200,
                         &v58,
                         v27 + 16,
                         v60);
    }
    else
    {
      v33 = v46;
      v34 = v60;
    }
    v35 = *(char ***)(v33 + 8);
    ++*(_QWORD *)(a1 + 216);
    *(_QWORD *)v27 = v33;
    *((_QWORD *)v27 + 1) = v35;
    *v35 = v27;
    *(_QWORD *)(v33 + 8) = v27;
    v36 = 2 * (v34 & *(_QWORD *)(a1 + 248));
    v37 = *(_QWORD *)(a1 + 224);
    v38 = *(_QWORD *)(v37 + 16 * (v34 & *(_QWORD *)(a1 + 248)));
    if ( v38 == *(_QWORD *)(a1 + 208) )
    {
      *(_QWORD *)(v37 + 16 * (v34 & *(_QWORD *)(a1 + 248))) = v27;
LABEL_23:
      *(_QWORD *)(v37 + 8 * v36 + 8) = v27;
      goto LABEL_24;
    }
    if ( v38 == v33 )
    {
      *(_QWORD *)(v37 + 16 * (v34 & *(_QWORD *)(a1 + 248))) = v27;
    }
    else if ( *(char ***)(v37 + 16 * (v34 & *(_QWORD *)(a1 + 248)) + 8) == v35 )
    {
      goto LABEL_23;
    }
LABEL_24:
    if ( *((_DWORD *)v27 + 110) == 1 )
    {
      v46 = 0;
      std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
        a1 + 200,
        &v46,
        v27 + 448);
      if ( v46 != *(_QWORD *)(a1 + 208) )
      {
        v43 = (_WORD *)(v46 + 96);
        if ( *(_QWORD *)(v46 + 120) > 7u )
          v43 = *(_WORD **)v43;
        v22 = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFileInternal(
                (_QWORD *)a1,
                v46 + 16,
                v48,
                v47,
                v43,
                *(_BYTE *)(v46 + 172),
                (wchar_t *)v55,
                (std::_Ref_count_base *)v54,
                (struct RealtimeProtection::FileUniqueId *)v53,
                a10,
                a11,
                v52,
                (void *)v51,
                (void *)v50,
                a15,
                v49,
                a17);
        if ( v22 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
            (unsigned int)v22);
      }
    }
    ReleaseSRWLockExclusive(v21);
    return (unsigned int)v22;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      (unsigned int)v22);
  ReleaseSRWLockExclusive(v21);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180032970  push    rbx
0x180032972  push    rsi
0x180032973  push    rdi
0x180032974  push    r12
0x180032976  push    r13
0x180032978  push    r14
0x18003297a  push    r15
0x18003297c  sub     rsp, 110h
0x180032983  mov     rax, cs:__security_cookie
0x18003298a  xor     rax, rsp
0x18003298d  mov     [rsp+148h+var_40], rax
0x180032995  mov     r14d, r9d
0x180032998  mov     [rsp+148h+var_B0], r9d
0x1800329a0  mov     edi, r8d
0x1800329a3  mov     [rsp+148h+var_AC], r8d
0x1800329ab  mov     rsi, rdx
0x1800329ae  mov     r13, rcx
0x1800329b1  mov     rbx, [rsp+148h+arg_20]
0x1800329b9  mov     r12, [rsp+148h+arg_30]
0x1800329c1  mov     [rsp+148h+var_78], r12
0x1800329c9  mov     rax, [rsp+148h+arg_38]
0x1800329d1  mov     [rsp+148h+var_80], rax
0x1800329d9  mov     rax, [rsp+148h+arg_40]
0x1800329e1  mov     [rsp+148h+var_88], rax
0x1800329e9  mov     rax, [rsp+148h+arg_58]
0x1800329f1  mov     [rsp+148h+var_90], rax
0x1800329f9  mov     rax, [rsp+148h+arg_60]
0x180032a01  mov     [rsp+148h+var_98], rax
0x180032a09  mov     rax, [rsp+148h+arg_68]
0x180032a11  mov     [rsp+148h+var_A0], rax
0x180032a19  mov     rax, [rsp+148h+arg_78]
0x180032a21  mov     [rsp+148h+var_A8], rax
0x180032a29  lea     r15, [rcx+1D0h]
0x180032a30  mov     [rsp+148h+var_60], r15
0x180032a38  mov     rcx, r15; SRWLock
0x180032a3b  call    cs:__imp_AcquireSRWLockExclusive
0x180032a41  mov     [rsp+148h+var_58], 1
0x180032a49  movzx   eax, [rsp+148h+arg_80]
0x180032a51  mov     [rsp+148h+var_C8], al; char
0x180032a58  mov     rax, [rsp+148h+var_A8]
0x180032a60  mov     [rsp+148h+var_D0], rax; __int64
0x180032a65  movzx   eax, [rsp+148h+arg_70]
0x180032a6d  mov     [rsp+148h+var_D8], al; char
0x180032a71  mov     rax, [rsp+148h+var_A0]
0x180032a79  mov     [rsp+148h+var_E0], rax; __int64
0x180032a7e  mov     rax, [rsp+148h+var_98]
0x180032a86  mov     [rsp+148h+var_E8], rax; __int64
0x180032a8b  mov     rax, [rsp+148h+var_90]
0x180032a93  mov     [rsp+148h+var_F0], rax; __int64
0x180032a98  mov     eax, [rsp+148h+arg_50]
0x180032a9f  mov     [rsp+148h+var_F8], eax; int
0x180032aa3  mov     eax, [rsp+148h+arg_48]
0x180032aaa  mov     [rsp+148h+var_100], eax; int
0x180032aae  mov     rax, [rsp+148h+var_88]
0x180032ab6  mov     [rsp+148h+var_108], rax; __int64
0x180032abb  mov     rax, [rsp+148h+var_80]
0x180032ac3  mov     [rsp+148h+var_110], rax; __int64
0x180032ac8  mov     [rsp+148h+var_118], r12; __int64
0x180032acd  movzx   eax, [rsp+148h+arg_28]
0x180032ad5  mov     [rsp+148h+var_120], al; char
0x180032ad9  mov     [rsp+148h+Src], rbx; Src
0x180032ade  mov     r9d, r14d; int
0x180032ae1  mov     r8d, edi; int
0x180032ae4  mov     rdx, rsi; int
0x180032ae7  mov     rcx, r13; int
0x180032aea  call    ?AddFileInternal@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAJAEBUPPID@@KW4_MP_KNOWN_PROCESS_TYPE@@PEB_W_N22AEBV?$optional@VFileUniqueId@RealtimeProtection@@@std@@KKPEAUDlpAction@@AEBUMpDlpPolicyTraceInfo@3@AEBUDlpAppGroupInfo@@3AEBUExtendedAttributes@Client@EndpointDlp@@3@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFileInternal(PPID const &,ulong,_MP_KNOWN_PROCESS_TYPE,wchar_t const *,bool,wchar_t const *,wchar_t const *,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,ulong,DlpAction *,RealtimeProtection::MpDlpPolicyTraceInfo const &,DlpAppGroupInfo const &,bool,EndpointDlp::Client::ExtendedAttributes const &,bool)
0x180032aef  mov     r14d, eax
0x180032af2  test    eax, eax
0x180032af4  js      loc_180032FAF
0x180032afa  lfence
0x180032afd  movzx   ecx, byte ptr [rsi+8]
0x180032b01  mov     rax, 0CBF29CE484222325h
0x180032b0b  xor     rcx, rax
0x180032b0e  mov     rdx, 100000001B3h
0x180032b18  imul    rcx, rdx
0x180032b1c  movzx   eax, byte ptr [rsi+9]
0x180032b20  xor     rcx, rax
0x180032b23  imul    rcx, rdx
0x180032b27  movzx   eax, byte ptr [rsi+0Ah]
0x180032b2b  xor     rcx, rax
0x180032b2e  imul    rcx, rdx
0x180032b32  movzx   eax, byte ptr [rsi+0Bh]
0x180032b36  xor     rcx, rax
0x180032b39  imul    rcx, rdx
0x180032b3d  and     rcx, [r13+138h]
0x180032b44  add     rcx, rcx
0x180032b47  mov     rax, [r13+120h]
0x180032b4e  mov     rdi, [rax+rcx*8+8]
0x180032b53  cmp     rdi, [r13+110h]
0x180032b5a  jnz     loc_180032BE3
0x180032b60  xor     edi, edi
0x180032b62  test    rdi, rdi
0x180032b65  jnz     loc_180032D6E
0x180032b6b  lea     r12, [r13+0C8h]
0x180032b72  mov     [rsp+148h+var_48], 0
0x180032b7d  mov     r8, rsi
0x180032b80  mov     edx, 0Ch
0x180032b85  lea     rcx, [rsp+148h+var_48]
0x180032b8d  call    MpHashCrc32
0x180032b92  mov     ecx, [rsp+148h+var_48]
0x180032b99  mov     rax, [r12+30h]
0x180032b9e  and     rax, rcx
0x180032ba1  add     rax, rax
0x180032ba4  mov     rcx, [r12+18h]
0x180032ba9  mov     rdi, [rcx+rax*8+8]
0x180032bae  mov     rdx, [r12+8]
0x180032bb3  mov     [rsp+148h+var_B8], rdx
0x180032bbb  cmp     rdi, rdx
0x180032bbe  jz      loc_180032D4B
0x180032bc4  mov     rbx, [rcx+rax*8]
0x180032bc8  lea     rdx, [rdi+10h]; lpFileTime2
0x180032bcc  mov     eax, [rdx+8]
0x180032bcf  cmp     [rsi+8], eax
0x180032bd2  jz      short loc_180032C02
0x180032bd4  cmp     rdi, rbx
0x180032bd7  jz      loc_180032D43
0x180032bdd  mov     rdi, [rdi+8]
0x180032be1  jmp     short loc_180032BC8
0x180032be3  mov     rdx, [rax+rcx*8]
0x180032be7  mov     eax, [rdi+10h]
0x180032bea  cmp     [rsi+8], eax
0x180032bed  jz      loc_180032B62
0x180032bf3  cmp     rdi, rdx
0x180032bf6  jz      loc_180032B60
0x180032bfc  mov     rdi, [rdi+8]
0x180032c00  jmp     short loc_180032BE7
0x180032c02  mov     rcx, rsi; lpFileTime1
0x180032c05  call    cs:__imp_CompareFileTime
0x180032c0b  test    eax, eax
0x180032c0d  jz      loc_180032CFD
0x180032c13  jmp     short loc_180032BD4
0x180032c15  lea     rax, [r12+8]
0x180032c1a  mov     [rsp+148h+var_70], rax
0x180032c22  mov     [rsp+148h+var_68], 0
0x180032c2e  mov     ecx, 3F0h; Size
0x180032c33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032c38  mov     rdi, rax
0x180032c3b  mov     [rsp+148h+var_68], rax
0x180032c43  movsd   xmm0, qword ptr [rsi]
0x180032c47  movsd   qword ptr [rax+10h], xmm0
0x180032c4c  mov     ecx, [rsi+8]
0x180032c4f  mov     [rax+18h], ecx
0x180032c52  lea     rbx, [rax+20h]
0x180032c56  xor     edx, edx; Val
0x180032c58  mov     r8d, 3D0h; Size
0x180032c5e  mov     rcx, rbx; void *
0x180032c61  call    memset
0x180032c66  mov     rcx, rbx; this
0x180032c69  call    ??0ProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAA@XZ; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor::ProcessEnforcementDescriptor(void)
0x180032c6e  nop
0x180032c6f  mov     rdx, [r13+0D8h]
0x180032c76  add     rdx, 1
0x180032c7a  xorps   xmm0, xmm0
0x180032c7d  js      loc_180032F78
0x180032c83  cvtsi2ss xmm0, rdx
0x180032c88  mov     rcx, [r12+38h]
0x180032c8d  xorps   xmm1, xmm1
0x180032c90  test    rcx, rcx
0x180032c93  js      loc_180032F95
0x180032c99  cvtsi2ss xmm1, rcx
0x180032c9e  divss   xmm0, xmm1
0x180032ca2  comiss  xmm0, dword ptr [r12]
0x180032ca7  ja      loc_180032FF2
0x180032cad  mov     rcx, [rsp+148h+var_B8]
0x180032cb5  mov     ebx, [rsp+148h+var_48]
0x180032cbc  mov     r8, [rcx+8]
0x180032cc0  inc     qword ptr [r13+0D8h]
0x180032cc7  mov     [rdi], rcx
0x180032cca  mov     [rdi+8], r8
0x180032cce  mov     [r8], rdi
0x180032cd1  mov     [rcx+8], rdi
0x180032cd5  mov     rax, [r12+30h]
0x180032cda  and     rax, rbx
0x180032cdd  add     rax, rax
0x180032ce0  mov     rdx, [r12+18h]
0x180032ce5  mov     r9, [rdx+rax*8]
0x180032ce9  cmp     r9, [r12+8]
0x180032cee  jnz     loc_180032F5A
0x180032cf4  mov     [rdx+rax*8], rdi
0x180032cf8  mov     [rdx+rax*8+8], rdi
0x180032cfd  cmp     dword ptr [rdi+1B8h], 1
0x180032d04  jz      loc_180032E1D
0x180032d0a  mov     rcx, r15; SRWLock
0x180032d0d  call    cs:__imp_ReleaseSRWLockExclusive
0x180032d13  nop
0x180032d14  test    r14d, r14d
0x180032d17  js      loc_180033067
0x180032d1d  mov     eax, r14d
0x180032d20  mov     rcx, [rsp+148h+var_40]
0x180032d28  xor     rcx, rsp; StackCookie
0x180032d2b  call    __security_check_cookie
0x180032d30  add     rsp, 110h
0x180032d37  pop     r15
0x180032d39  pop     r14
0x180032d3b  pop     r13
0x180032d3d  pop     r12
0x180032d3f  pop     rdi
0x180032d40  pop     rsi
0x180032d41  pop     rbx
0x180032d42  retn
0x180032d43  mov     [rsp+148h+var_B8], rdi
0x180032d4b  mov     rax, 41041041041041h
0x180032d55  cmp     [r13+0D8h], rax
0x180032d5c  jnz     loc_180032C15
0x180032d62  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180032d69  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180032d6e  cmp     rdi, [r13+110h]
0x180032d75  jz      loc_180032B6B
0x180032d7b  mov     eax, [rsi+4]
0x180032d7e  cmp     [rdi+20h], eax
0x180032d81  jnz     short loc_180032D8E
0x180032d83  mov     eax, [rsi]
0x180032d85  cmp     [rdi+1Ch], eax
0x180032d88  jz      loc_180032B6B
0x180032d8e  lea     rdx, [rdi+1Ch]
0x180032d92  call    ??$?RUPPID@EndpointDlp@@@?$_Uhash_compare@UPPID@EndpointDlp@@UPPIDHasher@2@UPPIDComparer@2@@std@@QEBA_KAEBUPPID@EndpointDlp@@@Z; std::_Uhash_compare<EndpointDlp::PPID,EndpointDlp::PPIDHasher,EndpointDlp::PPIDComparer>::operator()<EndpointDlp::PPID>(EndpointDlp::PPID const &)
0x180032d97  mov     [rsp+148h+var_B8], rax
0x180032d9f  mov     r9, rax
0x180032da2  lea     r8, [rdi+1Ch]
0x180032da6  lea     rdx, [rsp+148h+var_70]
0x180032dae  lea     rcx, [r13+0C8h]
0x180032db5  call    ??$_Find_last@UPPID@@@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@@1@AEBUPPID@@_K@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(PPID const &,unsigned __int64)
0x180032dba  mov     rdx, [rax+8]
0x180032dbe  test    rdx, rdx
0x180032dc1  jz      short loc_180032DEA
0x180032dc3  mov     r8, [r13+0F8h]
0x180032dca  and     r8, [rsp+148h+var_B8]
0x180032dd2  lea     rcx, [r13+0C8h]
0x180032dd9  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@KU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBKU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<ulong,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>>>,0>>::_Erase_bucket(std::_List_node<std::pair<ulong const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>>,void *> *,unsigned __int64)
0x180032dde  lea     rcx, [r13+0D0h]
0x180032de5  call    ?_Unchecked_erase@?$list@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>::_Unchecked_erase(std::_List_node<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>,void *> * const)
0x180032dea  lea     rdx, [rdi+10h]
0x180032dee  call    ??$?RW4DlpActionType@@@?$_Uhash_compare@W4DlpActionType@@U?$hash@W4DlpActionType@@@std@@U?$equal_to@W4DlpActionType@@@3@@std@@QEBA_KAEBW4DlpActionType@@@Z; std::_Uhash_compare<DlpActionType,std::hash<DlpActionType>,std::equal_to<DlpActionType>>::operator()<DlpActionType>(DlpActionType const &)
0x180032df3  mov     r8, [r13+138h]
0x180032dfa  and     r8, rax
0x180032dfd  mov     rdx, rdi
0x180032e00  lea     rcx, [r13+108h]
0x180032e07  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@KUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@6@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<ulong,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Erase_bucket(std::_List_node<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>,void *> *,unsigned __int64)
0x180032e0c  lea     rcx, [r13+110h]
0x180032e13  call    ?_Unchecked_erase@?$list@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@V?$allocator@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>::_Unchecked_erase(std::_List_node<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>,void *> * const)
0x180032e18  jmp     loc_180032B6B
0x180032e1d  mov     [rsp+148h+var_B8], 0
0x180032e29  lea     rcx, [r13+0C8h]
0x180032e30  lea     r8, [rdi+1C0h]
0x180032e37  lea     rdx, [rsp+148h+var_B8]
0x180032e3f  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x180032e44  mov     rax, [rsp+148h+var_B8]
0x180032e4c  cmp     rax, [r13+0D0h]
0x180032e53  jz      loc_180032D0A
0x180032e59  lea     rdx, [rax+10h]; int
0x180032e5d  movzx   ecx, byte ptr [rdx+9Ch]
0x180032e64  lea     rax, [rdx+50h]
0x180032e68  cmp     qword ptr [rax+18h], 7
0x180032e6d  jbe     short loc_180032E72
0x180032e6f  mov     rax, [rax]
0x180032e72  movzx   r8d, [rsp+148h+arg_80]
0x180032e7b  mov     [rsp+148h+var_C8], r8b; char
0x180032e83  mov     r8, [rsp+148h+var_A8]
0x180032e8b  mov     [rsp+148h+var_D0], r8; __int64
0x180032e90  movzx   r8d, [rsp+148h+arg_70]
0x180032e99  mov     [rsp+148h+var_D8], r8b; char
0x180032e9e  mov     r8, [rsp+148h+var_A0]
0x180032ea6  mov     [rsp+148h+var_E0], r8; __int64
0x180032eab  mov     r8, [rsp+148h+var_98]
0x180032eb3  mov     [rsp+148h+var_E8], r8; __int64
0x180032eb8  mov     r8, [rsp+148h+var_90]
0x180032ec0  mov     [rsp+148h+var_F0], r8; __int64
0x180032ec5  mov     r8d, [rsp+148h+arg_50]
0x180032ecd  mov     [rsp+148h+var_F8], r8d; int
0x180032ed2  mov     r8d, [rsp+148h+arg_48]
0x180032eda  mov     [rsp+148h+var_100], r8d; int
0x180032edf  mov     r8, [rsp+148h+var_88]
0x180032ee7  mov     [rsp+148h+var_108], r8; __int64
0x180032eec  mov     r8, [rsp+148h+var_80]
0x180032ef4  mov     [rsp+148h+var_110], r8; __int64
0x180032ef9  mov     r8, [rsp+148h+var_78]
0x180032f01  mov     [rsp+148h+var_118], r8; __int64
0x180032f06  mov     [rsp+148h+var_120], cl; char
0x180032f0a  mov     [rsp+148h+Src], rax; Src
0x180032f0f  mov     r9d, [rsp+148h+var_B0]; int
0x180032f17  mov     r8d, [rsp+148h+var_AC]; int
0x180032f1f  mov     rcx, r13; int
0x180032f22  call    ?AddFileInternal@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAJAEBUPPID@@KW4_MP_KNOWN_PROCESS_TYPE@@PEB_W_N22AEBV?$optional@VFileUniqueId@RealtimeProtection@@@std@@KKPEAUDlpAction@@AEBUMpDlpPolicyTraceInfo@3@AEBUDlpAppGroupInfo@@3AEBUExtendedAttributes@Client@EndpointDlp@@3@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::AddFileInternal(PPID const &,ulong,_MP_KNOWN_PROCESS_TYPE,wchar_t const *,bool,wchar_t const *,wchar_t const *,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,ulong,DlpAction *,RealtimeProtection::MpDlpPolicyTraceInfo const &,DlpAppGroupInfo const &,bool,EndpointDlp::Client::ExtendedAttributes const &,bool)
0x180032f27  mov     r14d, eax
0x180032f2a  test    eax, eax
0x180032f2c  jns     loc_180032D0A
0x180032f32  lea     rax, WPP_GLOBAL_Control
0x180032f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f40  cmp     rcx, rax
0x180032f43  jnz     loc_18003302B
0x180032f49  mov     rcx, r15; SRWLock
0x180032f4c  call    cs:__imp_ReleaseSRWLockExclusive
0x180032f52  mov     eax, r14d
0x180032f55  jmp     loc_180032D20
0x180032f5a  cmp     r9, rcx
0x180032f5d  jnz     short loc_180032F68
0x180032f5f  mov     [rdx+rax*8], rdi
0x180032f63  jmp     loc_180032CFD
0x180032f68  cmp     [rdx+rax*8+8], r8
0x180032f6d  jnz     loc_180032CFD
  ... truncated ...
```
