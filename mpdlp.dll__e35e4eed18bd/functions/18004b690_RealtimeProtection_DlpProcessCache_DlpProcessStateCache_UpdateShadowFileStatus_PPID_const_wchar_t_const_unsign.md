# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateShadowFileStatus(PPID const &,wchar_t const *,unsigned __int64,bool)

- ea: `0x18004b690`
- end: `0x18004bafb`
- name: `?UpdateShadowFileStatus@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@PEB_W_K_N@Z`
- size: `1131`
- prototype: `int(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, const wchar_t *, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b9554`

## callees

- `0x18002c150`
- `0x18002c990`
- `0x180034420`
- `0x180038450`
- `0x180042594`
- `0x18004b3bc`
- `0x18004b690`
- `0x18004bafc`
- `0x18004bc88`
- `0x18004c04c`
- `0x1800809d0`
- `0x18009f730`
- `0x1800ac090`
- `0x1800b2790`
- `0x180107874`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18004b6d8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004b6d8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004b7a1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004b8bf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004b7a1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004b8bf`
- `KERNEL32!GetTickCount64` at `0x18004b785`
- `KERNEL32!GetTickCount64` at `0x18004b814`
- `KERNEL32!GetTickCount64` at `0x18004b785`
- `KERNEL32!GetTickCount64` at `0x18004b814`
- `KERNEL32!CompareFileTime` at `0x18004b740`
- `KERNEL32!CompareFileTime` at `0x18004b740`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateShadowFileStatus(
        RTL_SRWLOCK *this,
        const FILETIME *a2,
        wchar_t *a3,
        ULONGLONG a4,
        bool a5)
{
  RTL_SRWLOCK *v9; // rsi
  _QWORD *Ptr; // rax
  __int64 v11; // rdi
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // rsi
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rbx
  _QWORD *v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  PVOID v24; // rcx
  _QWORD *v25; // r9
  _QWORD *v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rsi
  RTL_SRWLOCK *v31; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v32[40]; // [rsp+40h] [rbp-108h] BYREF
  RTL_SRWLOCK *v33; // [rsp+68h] [rbp-E0h]
  char v34; // [rsp+70h] [rbp-D8h]
  _QWORD *v35; // [rsp+78h] [rbp-D0h] BYREF
  _OWORD Src[2]; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v37[64]; // [rsp+A0h] [rbp-A8h] BYREF
  char v38; // [rsp+E0h] [rbp-68h]
  char v39; // [rsp+E8h] [rbp-60h]
  ULONGLONG TickCount64; // [rsp+F0h] [rbp-58h]

  v9 = this + 58;
  v31 = this + 58;
  v33 = this + 58;
  AcquireSRWLockExclusive(this + 58);
  v34 = 1;
  LODWORD(v35) = 0;
  MpHashCrc32(&v35, 12);
  Ptr = this[28].Ptr;
  v11 = Ptr[2 * ((unsigned int)v35 & (__int64)this[31].Ptr) + 1];
  if ( (PVOID)v11 != this[26].Ptr )
  {
    v12 = Ptr[2 * ((unsigned int)v35 & (__int64)this[31].Ptr)];
    while ( 1 )
    {
      if ( a2[1].dwLowDateTime == *(_DWORD *)(v11 + 24) && !CompareFileTime(a2, (const FILETIME *)(v11 + 16)) )
      {
        v9 = this + 58;
        goto LABEL_10;
      }
      if ( v11 == v12 )
        break;
      v11 = *(_QWORD *)(v11 + 8);
    }
    v9 = this + 58;
  }
  v11 = 0;
LABEL_10:
  if ( !v11 || (PVOID)v11 == this[26].Ptr )
  {
    ReleaseSRWLockExclusive(v9);
    return 1;
  }
  else
  {
    v13 = *(_QWORD **)(v11 + 312);
LABEL_13:
    v13 = (_QWORD *)*v13;
    while ( v13 != *(_QWORD **)(v11 + 312) )
    {
      v14 = v13[20];
      if ( GetTickCount64() - v14 <= a4 )
      {
        v9 = v31;
        goto LABEL_13;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v25 = v13 + 2;
        if ( v13[5] > 7u )
          v25 = (_QWORD *)*v25;
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
          (_DWORD)v25,
          a2[1].dwLowDateTime);
      }
      v26 = (_QWORD *)(*(_QWORD *)(v11 + 328)
                     + 16
                     * (std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(
                          v24,
                          v13 + 2)
                      & *(_QWORD *)(v11 + 352)));
      v28 = (_QWORD *)*v26;
      if ( (_QWORD *)v26[1] == v13 )
      {
        if ( v28 == v13 )
        {
          v29 = *(_QWORD *)(v11 + 312);
          *v26 = v29;
        }
        else
        {
          v29 = v13[1];
        }
        v26[1] = v29;
      }
      else if ( v28 == v13 )
      {
        *v26 = *v13;
      }
      v30 = (_QWORD *)*v13;
      --*(_QWORD *)(v11 + 320);
      *(_QWORD *)v13[1] = v30;
      v30[1] = v13[1];
      std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>>>(
        v27,
        v13);
      v13 = v30;
      v9 = v31;
    }
    if ( a5 )
    {
      v35 = 0;
      std::wstring::wstring(v32, a3);
      std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>>,0>>::find(
        v11 + 304,
        &v35,
        v32);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v32);
      v19 = v35;
      if ( v35 != *(_QWORD **)(v11 + 312) )
      {
        v20 = (_QWORD *)(*(_QWORD *)(v11 + 328)
                       + 16
                       * (std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(
                            v18,
                            v35 + 2)
                        & *(_QWORD *)(v11 + 352)));
        v21 = (_QWORD *)*v20;
        if ( (_QWORD *)v20[1] == v19 )
        {
          if ( v21 == v19 )
          {
            v22 = *(_QWORD *)(v11 + 312);
            *v20 = v22;
          }
          else
          {
            v22 = v19[1];
          }
          v20[1] = v22;
        }
        else if ( v21 == v19 )
        {
          *v20 = *v19;
        }
        v23 = *v19;
        --*(_QWORD *)(v11 + 320);
        *(_QWORD *)v19[1] = v23;
        *(_QWORD *)(v23 + 8) = v19[1];
        std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>>>(
          v23,
          v19);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
            (_DWORD)a3,
            a2[1].dwLowDateTime);
      }
    }
    else
    {
      Src[0] = 0;
      Src[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Src[0]) = 0;
      v38 = 0;
      v39 = 0;
      TickCount64 = 0;
      std::wstring::assign(Src, a3);
      v39 = 1;
      TickCount64 = GetTickCount64();
      std::wstring::wstring(v32, a3);
      v16 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>>,0>>::_Try_emplace<std::wstring,>(
                         v11 + 304,
                         &v31,
                         v32);
      std::wstring::operator=((void *)(v16 + 48), Src);
      v17 = v16 + 80;
      if ( v38 )
        std::_Optional_construct_base<RealtimeProtection::FileUniqueId>::_Assign<RealtimeProtection::FileUniqueId const &>(
          v17,
          v37);
      else
        std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::reset(v17);
      *(_BYTE *)(v16 + 152) = v39;
      *(_QWORD *)(v16 + 160) = TickCount64;
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v32);
      std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v37);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    }
    ReleaseSRWLockExclusive(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x18004b690  push    rbx
0x18004b692  push    rsi
0x18004b693  push    rdi
0x18004b694  push    r12
0x18004b696  push    r13
0x18004b698  push    r14
0x18004b69a  push    r15
0x18004b69c  sub     rsp, 110h
0x18004b6a3  mov     rax, cs:__security_cookie
0x18004b6aa  xor     rax, rsp
0x18004b6ad  mov     [rsp+148h+var_48], rax
0x18004b6b5  mov     r14, r9
0x18004b6b8  mov     r12, r8
0x18004b6bb  mov     r13, rdx
0x18004b6be  mov     rbx, rcx
0x18004b6c1  xor     r15d, r15d
0x18004b6c4  lea     rsi, [rcx+1D0h]
0x18004b6cb  mov     [rsp+148h+var_118], rsi
0x18004b6d0  mov     [rsp+148h+var_E0], rsi
0x18004b6d5  mov     rcx, rsi; SRWLock
0x18004b6d8  call    cs:__imp_AcquireSRWLockExclusive
0x18004b6de  mov     al, 1
0x18004b6e0  mov     [rsp+148h+var_D8], al
0x18004b6e4  mov     dword ptr [rsp+148h+var_D0], r15d
0x18004b6e9  mov     r8, r13
0x18004b6ec  mov     edx, 0Ch
0x18004b6f1  lea     rcx, [rsp+148h+var_D0]
0x18004b6f6  call    MpHashCrc32
0x18004b6fb  mov     eax, dword ptr [rsp+148h+var_D0]
0x18004b6ff  mov     rcx, [rbx+0F8h]
0x18004b706  and     rcx, rax
0x18004b709  add     rcx, rcx
0x18004b70c  mov     rax, [rbx+0E0h]
0x18004b713  mov     rdi, [rax+rcx*8+8]
0x18004b718  cmp     rdi, [rbx+0D0h]
0x18004b71f  jz      short loc_18004B75A
0x18004b721  mov     rsi, [rax+rcx*8]
0x18004b725  lea     rdx, [rdi+10h]; lpFileTime2
0x18004b729  mov     eax, [rdx+8]
0x18004b72c  cmp     [r13+8], eax
0x18004b730  jz      short loc_18004B73D
0x18004b732  cmp     rdi, rsi
0x18004b735  jz      short loc_18004B753
0x18004b737  mov     rdi, [rdi+8]
0x18004b73b  jmp     short loc_18004B725
0x18004b73d  mov     rcx, r13; lpFileTime1
0x18004b740  call    cs:__imp_CompareFileTime
0x18004b746  test    eax, eax
0x18004b748  jnz     short loc_18004B732
0x18004b74a  lea     rsi, [rbx+1D0h]
0x18004b751  jmp     short loc_18004B75D
0x18004b753  lea     rsi, [rbx+1D0h]
0x18004b75a  mov     rdi, r15
0x18004b75d  test    rdi, rdi
0x18004b760  jz      short loc_18004B79E
0x18004b762  cmp     rdi, [rbx+0D0h]
0x18004b769  jz      short loc_18004B79E
0x18004b76b  mov     rbx, [rdi+138h]
0x18004b772  mov     rbx, [rbx]
0x18004b775  cmp     rbx, [rdi+138h]
0x18004b77c  jz      short loc_18004B7B1
0x18004b77e  mov     rsi, [rbx+0A0h]
0x18004b785  call    cs:__imp_GetTickCount64
0x18004b78b  sub     rax, rsi
0x18004b78e  cmp     rax, r14
0x18004b791  ja      loc_18004B9E9
0x18004b797  mov     rsi, [rsp+148h+var_118]
0x18004b79c  jmp     short loc_18004B772
0x18004b79e  mov     rcx, rsi; SRWLock
0x18004b7a1  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b7a7  mov     eax, 1
0x18004b7ac  jmp     loc_18004B8C9
0x18004b7b1  cmp     [rsp+148h+arg_20], 0
0x18004b7b9  jnz     loc_18004B8F3
0x18004b7bf  xorps   xmm0, xmm0
0x18004b7c2  movups  [rsp+148h+Src], xmm0
0x18004b7ca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004b7d2  movdqa  [rsp+148h+var_B8], xmm1
0x18004b7db  mov     word ptr [rsp+148h+Src], r15w
0x18004b7e4  mov     [rsp+148h+var_68], 0
0x18004b7ec  mov     [rsp+148h+var_60], 0
0x18004b7f4  mov     [rsp+148h+var_58], r15
0x18004b7fc  mov     rdx, r12; Src
0x18004b7ff  lea     rcx, [rsp+148h+Src]; void *
0x18004b807  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18004b80c  mov     [rsp+148h+var_60], 1
0x18004b814  call    cs:__imp_GetTickCount64
0x18004b81a  mov     [rsp+148h+var_58], rax
0x18004b822  mov     rdx, r12
0x18004b825  lea     rcx, [rsp+148h+var_108]
0x18004b82a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18004b82f  nop
0x18004b830  lea     r8, [rsp+148h+var_108]
0x18004b835  lea     rdx, [rsp+148h+var_118]
0x18004b83a  lea     rcx, [rdi+130h]
0x18004b841  call    ??$_Try_emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18004b846  mov     rbx, [rax]
0x18004b849  lea     rcx, [rbx+30h]; void *
0x18004b84d  lea     rdx, [rsp+148h+Src]; Src
0x18004b855  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004b85a  lea     rcx, [rbx+50h]
0x18004b85e  cmp     [rsp+148h+var_68], 0
0x18004b866  jz      loc_18004B8EC
0x18004b86c  lea     rdx, [rsp+148h+var_A8]
0x18004b874  call    ??$_Assign@AEBVFileUniqueId@RealtimeProtection@@@?$_Optional_construct_base@VFileUniqueId@RealtimeProtection@@@std@@QEAAXAEBVFileUniqueId@RealtimeProtection@@@Z; std::_Optional_construct_base<RealtimeProtection::FileUniqueId>::_Assign<RealtimeProtection::FileUniqueId const &>(RealtimeProtection::FileUniqueId const &)
0x18004b879  movzx   eax, [rsp+148h+var_60]
0x18004b881  mov     [rbx+98h], al
0x18004b887  mov     rax, [rsp+148h+var_58]
0x18004b88f  mov     [rbx+0A0h], rax
0x18004b896  lea     rcx, [rsp+148h+var_108]; void *
0x18004b89b  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18004b8a0  nop
0x18004b8a1  lea     rcx, [rsp+148h+var_A8]
0x18004b8a9  call    ??1?$_Optional_destruct_base@VFileUniqueId@RealtimeProtection@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(void)
0x18004b8ae  lea     rcx, [rsp+148h+Src]; void *
0x18004b8b6  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18004b8bb  nop
0x18004b8bc  mov     rcx, rsi; SRWLock
0x18004b8bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b8c5  nop
0x18004b8c6  mov     eax, r15d
0x18004b8c9  mov     rcx, [rsp+148h+var_48]
0x18004b8d1  xor     rcx, rsp; StackCookie
0x18004b8d4  call    __security_check_cookie
0x18004b8d9  add     rsp, 110h
0x18004b8e0  pop     r15
0x18004b8e2  pop     r14
0x18004b8e4  pop     r13
0x18004b8e6  pop     r12
0x18004b8e8  pop     rdi
0x18004b8e9  pop     rsi
0x18004b8ea  pop     rbx
0x18004b8eb  retn
0x18004b8ec  call    ?reset@?$_Optional_destruct_base@VFileUniqueId@RealtimeProtection@@$0A@@std@@QEAAXXZ; std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::reset(void)
0x18004b8f1  jmp     short loc_18004B879
0x18004b8f3  mov     [rsp+148h+var_D0], r15
0x18004b8f8  mov     rdx, r12
0x18004b8fb  lea     rcx, [rsp+148h+var_108]
0x18004b900  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18004b905  nop
0x18004b906  lea     r8, [rsp+148h+var_108]
0x18004b90b  lea     rdx, [rsp+148h+var_D0]
0x18004b910  lea     rcx, [rdi+130h]
0x18004b917  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>>,0>>::find(std::wstring const &)
0x18004b91c  nop
0x18004b91d  lea     rcx, [rsp+148h+var_108]; void *
0x18004b922  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18004b927  mov     rbx, [rsp+148h+var_D0]
0x18004b92c  cmp     rbx, [rdi+138h]
0x18004b933  jz      short loc_18004B8BC
0x18004b935  lea     rdx, [rbx+10h]
0x18004b939  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(std::wstring const &)
0x18004b93e  mov     rdx, [rdi+160h]
0x18004b945  and     rdx, rax
0x18004b948  shl     rdx, 4
0x18004b94c  add     rdx, [rdi+148h]
0x18004b953  mov     rax, [rdx]
0x18004b956  cmp     [rdx+8], rbx
0x18004b95a  jnz     short loc_18004B977
0x18004b95c  cmp     rax, rbx
0x18004b95f  jnz     short loc_18004B96D
0x18004b961  mov     rax, [rdi+138h]
0x18004b968  mov     [rdx], rax
0x18004b96b  jmp     short loc_18004B971
0x18004b96d  mov     rax, [rbx+8]
0x18004b971  mov     [rdx+8], rax
0x18004b975  jmp     short loc_18004B982
0x18004b977  cmp     rax, rbx
0x18004b97a  jnz     short loc_18004B982
0x18004b97c  mov     rax, [rbx]
0x18004b97f  mov     [rdx], rax
0x18004b982  mov     rcx, [rbx]
0x18004b985  dec     qword ptr [rdi+140h]
0x18004b98c  mov     rax, [rbx+8]
0x18004b990  mov     [rax], rcx
0x18004b993  mov     rax, [rbx+8]
0x18004b997  mov     [rcx+8], rax
0x18004b99b  mov     rdx, rbx
0x18004b99e  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>> &,std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *> *)
0x18004b9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9aa  lea     rax, WPP_GLOBAL_Control
0x18004b9b1  cmp     rcx, rax
0x18004b9b4  jz      loc_18004B8BC
0x18004b9ba  test    byte ptr [rcx+1Ch], 10h
0x18004b9be  jz      loc_18004B8BC
0x18004b9c4  mov     edx, 29h ; ')'
0x18004b9c9  mov     eax, [r13+8]
0x18004b9cd  mov     [rsp+148h+var_128], eax
0x18004b9d1  mov     r9, r12
0x18004b9d4  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18004b9db  mov     rcx, [rcx+10h]
0x18004b9df  call    WPP_SF_SD
0x18004b9e4  jmp     loc_18004B8BC
0x18004b9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9f0  lea     rax, WPP_GLOBAL_Control
0x18004b9f7  cmp     rcx, rax
0x18004b9fa  jz      short loc_18004BA2D
0x18004b9fc  test    byte ptr [rcx+1Ch], 10h
0x18004ba00  jz      short loc_18004BA2D
0x18004ba02  mov     eax, [r13+8]
0x18004ba06  lea     r9, [rbx+10h]
0x18004ba0a  cmp     qword ptr [rbx+28h], 7
0x18004ba0f  jbe     short loc_18004BA14
0x18004ba11  mov     r9, [r9]
0x18004ba14  mov     edx, 28h ; '('
0x18004ba19  mov     [rsp+148h+var_128], eax
0x18004ba1d  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18004ba24  mov     rcx, [rcx+10h]
0x18004ba28  call    WPP_SF_SD
0x18004ba2d  lea     rdx, [rbx+10h]
0x18004ba31  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(std::wstring const &)
0x18004ba36  mov     rdx, [rdi+160h]
0x18004ba3d  and     rdx, rax
0x18004ba40  shl     rdx, 4
0x18004ba44  add     rdx, [rdi+148h]
0x18004ba4b  mov     rax, [rdx]
0x18004ba4e  cmp     [rdx+8], rbx
0x18004ba52  jnz     short loc_18004BA6F
0x18004ba54  cmp     rax, rbx
0x18004ba57  jnz     short loc_18004BA65
0x18004ba59  mov     rax, [rdi+138h]
0x18004ba60  mov     [rdx], rax
0x18004ba63  jmp     short loc_18004BA69
0x18004ba65  mov     rax, [rbx+8]
0x18004ba69  mov     [rdx+8], rax
0x18004ba6d  jmp     short loc_18004BA7A
0x18004ba6f  cmp     rax, rbx
0x18004ba72  jnz     short loc_18004BA7A
0x18004ba74  mov     rax, [rbx]
0x18004ba77  mov     [rdx], rax
0x18004ba7a  mov     rsi, [rbx]
0x18004ba7d  dec     qword ptr [rdi+140h]
0x18004ba84  mov     rax, [rbx+8]
0x18004ba88  mov     [rax], rsi
0x18004ba8b  mov     rax, [rbx+8]
0x18004ba8f  mov     [rsi+8], rax
0x18004ba93  mov     rdx, rbx
0x18004ba96  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UShadowFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *>> &,std::_List_node<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ShadowFileEnforcementDescriptor>,void *> *)
0x18004ba9b  mov     rbx, rsi
0x18004ba9e  mov     rsi, [rsp+148h+var_118]
0x18004baa3  jmp     loc_18004B775
0x18004baa8  mov     r15d, dword ptr [rsp+148h+var_D0]
0x18004baad  jmp     short loc_18004BABD
0x18004baaf  mov     r15d, dword ptr [rsp+148h+var_D0]
0x18004bab4  test    r15d, r15d
0x18004bab7  jns     loc_18004B8C6
0x18004babd  lea     rax, WPP_GLOBAL_Control
0x18004bac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bacb  cmp     rcx, rax
0x18004bace  jz      loc_18004B8C6
0x18004bad4  test    byte ptr [rcx+1Ch], 1
0x18004bad8  jz      loc_18004B8C6
0x18004bade  mov     edx, 2Ah ; '*'
0x18004bae3  mov     r9d, r15d
0x18004bae6  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18004baed  mov     rcx, [rcx+10h]
0x18004baf1  call    WPP_SF_d
0x18004baf6  jmp     loc_18004B8C6
```
