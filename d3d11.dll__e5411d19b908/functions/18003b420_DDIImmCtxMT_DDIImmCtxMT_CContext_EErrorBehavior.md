# DDIImmCtxMT::DDIImmCtxMT(CContext *,EErrorBehavior)

- ea: `0x18003b420`
- end: `0x18003b6fb`
- name: `??0DDIImmCtxMT@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z`
- size: `731`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `71`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006f28`
- `0x1800072cc`
- `0x18000887c`
- `0x180008be8`
- `0x180009a64`
- `0x18000a2d4`
- `0x180015a50`
- `0x180016010`
- `0x1800303a0`
- `0x18003a3e0`
- `0x18003ad80`
- `0x18003baa0`
- `0x18003bfa0`
- `0x18003c8e0`
- `0x18003ce70`
- `0x18003d814`
- `0x18003e1c0`
- `0x18003e380`
- `0x18003ee58`
- `0x18003f040`
- `0x18003f22c`
- `0x18003f524`
- `0x180040240`
- `0x180040640`
- `0x180040e40`
- `0x180040fa0`
- `0x180041590`
- `0x18004c880`
- `0x18004f7a0`
- `0x180054720`
- `0x180054930`
- `0x18005e4f0`
- `0x18005eecc`
- `0x18005fb84`
- `0x18006034c`
- `0x180061a20`
- `0x18006430c`
- `0x1800654ec`
- `0x1800659cc`
- `0x180066e1c`
- `0x180070c30`
- `0x18007128c`
- `0x18007425c`
- `0x180074ed8`
- `0x18007538c`
- `0x1800782a0`
- `0x180079dac`
- `0x18007b770`
- `0x18007b960`
- `0x18007bbac`

## callees

- `0x1800112b0`
- `0x18003b420`
- `0x18003b704`
- `0x18003cc70`
- `0x18009da0c`
- `0x1800a0ef8`
- `0x1800bc1e8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003b624`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003b624`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b45d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b45d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b5d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b5d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b492`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b492`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DDIImmCtxMT::DDIImmCtxMT(__int64 a1, __int64 a2, char a3)
{
  _QWORD *v5; // r14
  DWORD CurrentThreadId; // ebp
  RTL_SRWLOCK *v7; // rbx
  RTL_SRWLOCK *v8; // rdi
  RTL_SRWLOCK *v9; // r15
  __int64 *v10; // rax
  __int64 v11; // rcx
  RTL_SRWLOCK *v12; // r12
  __int64 Ptr; // r13
  __int64 v14; // rax
  __int64 v15; // r14
  _QWORD *v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rdx
  float v20; // xmm0_4
  __int64 v21; // rcx
  float v22; // xmm1_4
  __int64 *v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rcx
  PVOID v26; // r8
  __int64 v28; // rax
  _QWORD *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  DWORD v33; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v34; // [rsp+28h] [rbp-50h]
  RTL_SRWLOCK *v35; // [rsp+30h] [rbp-48h]
  __int64 v36; // [rsp+38h] [rbp-40h]
  char v37; // [rsp+88h] [rbp+10h] BYREF
  DWORD v38; // [rsp+90h] [rbp+18h] BYREF

  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 12) = a3;
  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v5 = (_QWORD *)(a1 + 32);
  *(_BYTE *)(a1 + 32) = a3;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)(a1 + 40) = a1 + 32;
  *(_QWORD *)(a1 + 48) = 0;
  CurrentThreadId = GetCurrentThreadId();
  v38 = CurrentThreadId;
  if ( !*(_BYTE *)(a2 + 3709) )
  {
    *(_QWORD *)(a1 + 40) = a2 + 3692;
    *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 3688);
    *(_QWORD *)(a1 + 12) = *(_QWORD *)(a2 + 3692);
    *(_DWORD *)(a2 + 3688) = CurrentThreadId;
    *(_QWORD *)(a2 + 3692) = *v5;
    return a1;
  }
  v7 = *(RTL_SRWLOCK **)(a2 + 160);
  v8 = v7 + 437;
  AcquireSRWLockExclusive(v7 + 437);
  v9 = v7 + 438;
  v10 = (__int64 *)std::_Hash<std::_Umap_traits<unsigned long,SDDIErrorCtx *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SDDIErrorCtx *>>,0>>::find(
                     &v7[438],
                     &v37,
                     &v38);
  v11 = *v10;
  *(_QWORD *)(a1 + 48) = *v10;
  v12 = v7 + 439;
  Ptr = (__int64)v7[439].Ptr;
  if ( v11 == Ptr )
  {
    v33 = CurrentThreadId;
    v34 = v5;
    v14 = std::_Conditionally_enabled_hash<unsigned long,1>::operator()(&v33);
    v15 = v14;
    v16 = v7[441].Ptr;
    v17 = v16[2 * ((__int64)v7[444].Ptr & v14) + 1];
    if ( v17 != Ptr )
    {
      v31 = v16[2 * ((__int64)v9[6].Ptr & v14)];
      while ( CurrentThreadId != *(_DWORD *)(v17 + 16) )
      {
        if ( v17 == v31 )
        {
          Ptr = v17;
          goto LABEL_4;
        }
        v17 = *(_QWORD *)(v17 + 8);
      }
      goto LABEL_13;
    }
LABEL_4:
    if ( v9[2].Ptr == (PVOID)0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v35 = v9 + 1;
    v36 = 0;
    v17 = std::_Allocate<16,std::_Default_allocate_traits>(32);
    v36 = v17;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>,void *>>>::construct<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>,std::pair<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *>>(
      v18,
      v17 + 16,
      &v33);
    v19 = (__int64)v9[2].Ptr + 1;
    if ( v19 < 0 )
      v20 = (float)(v19 & 1 | (unsigned int)((unsigned __int64)v19 >> 1))
          + (float)(v19 & 1 | (unsigned int)((unsigned __int64)v19 >> 1));
    else
      v20 = (float)(int)v19;
    v21 = (__int64)v9[7].Ptr;
    if ( v21 < 0 )
    {
      v32 = (__int64)v9[7].Ptr & 1 | ((unsigned __int64)v21 >> 1);
      v22 = (float)(int)v32 + (float)(int)v32;
    }
    else
    {
      v22 = (float)(int)v21;
    }
    if ( (float)(v20 / v22) > *(float *)&v9->Ptr )
    {
      v28 = std::_Hash<std::_Umap_traits<SmallDepthStencilStateDesc const *,CDepthStencilState *,std::_Uhash_compare<SmallDepthStencilStateDesc const *,HashDeref<SmallDepthStencilStateDesc>,EqualToDeref<SmallDepthStencilStateDesc>>,std::allocator<std::pair<SmallDepthStencilStateDesc const * const,CDepthStencilState *>>,0>>::_Desired_grow_bucket_count(v9);
      std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::_Forced_rehash(
        v9,
        v28);
      v29 = v9[3].Ptr;
      v30 = v29[2 * (v15 & (__int64)v9[6].Ptr) + 1];
      Ptr = (__int64)v12->Ptr;
      if ( (PVOID)v30 != v12->Ptr )
      {
        while ( 1 )
        {
          if ( *(_DWORD *)(v17 + 16) == *(_DWORD *)(v30 + 16) )
          {
            Ptr = *(_QWORD *)v30;
            goto LABEL_10;
          }
          if ( v30 == v29[2 * (v15 & (__int64)v9[6].Ptr)] )
            break;
          v30 = *(_QWORD *)(v30 + 8);
        }
        Ptr = v30;
      }
    }
LABEL_10:
    v23 = *(__int64 **)(Ptr + 8);
    ++v9[2].Ptr;
    *(_QWORD *)v17 = Ptr;
    *(_QWORD *)(v17 + 8) = v23;
    *v23 = v17;
    *(_QWORD *)(Ptr + 8) = v17;
    v24 = 2 * (v15 & (__int64)v9[6].Ptr);
    v25 = v9[3].Ptr;
    v26 = (PVOID)v25[2 * (v15 & (__int64)v9[6].Ptr)];
    if ( v26 == v12->Ptr )
    {
      v25[2 * (v15 & (__int64)v9[6].Ptr)] = v17;
    }
    else
    {
      if ( v26 == (PVOID)Ptr )
      {
        v25[2 * (v15 & (__int64)v9[6].Ptr)] = v17;
        goto LABEL_13;
      }
      if ( (__int64 *)v25[2 * (v15 & (__int64)v9[6].Ptr) + 1] != v23 )
        goto LABEL_13;
    }
    v25[v24 + 1] = v17;
LABEL_13:
    *(_QWORD *)(a1 + 48) = v17;
    goto LABEL_15;
  }
  *(_QWORD *)(a1 + 24) = *(_QWORD *)(v11 + 24);
  *(_QWORD *)(v11 + 24) = v5;
LABEL_15:
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  return a1;
}

```

## disassembly

```asm
0x18003b420  mov     [rsp+arg_18], rbx
0x18003b425  push    rbp
0x18003b426  push    rsi
0x18003b427  push    rdi
0x18003b428  push    r12
0x18003b42a  push    r13
0x18003b42c  push    r14
0x18003b42e  push    r15
0x18003b430  sub     rsp, 40h
0x18003b434  mov     rbx, rdx
0x18003b437  mov     rsi, rcx
0x18003b43a  mov     [rcx], rdx
0x18003b43d  mov     [rcx+0Ch], r8b
0x18003b441  xor     eax, eax
0x18003b443  mov     [rcx+10h], eax
0x18003b446  mov     [rcx+18h], rax
0x18003b44a  lea     r14, [rcx+20h]
0x18003b44e  mov     [r14], r8b
0x18003b451  mov     [r14+4], eax
0x18003b455  mov     [rcx+28h], r14
0x18003b459  mov     [rcx+30h], rax
0x18003b45d  call    cs:__imp_GetCurrentThreadId
0x18003b463  mov     ebp, eax
0x18003b465  mov     [rsp+78h+arg_10], eax
0x18003b46c  cmp     byte ptr [rbx+0E7Dh], 0
0x18003b473  jz      loc_18003B5F4
0x18003b479  mov     rbx, [rbx+0A0h]
0x18003b480  lea     rdi, [rbx+0DA8h]
0x18003b487  mov     [rsp+78h+arg_0], rdi
0x18003b48f  mov     rcx, rdi; SRWLock
0x18003b492  call    cs:__imp_AcquireSRWLockExclusive
0x18003b498  nop
0x18003b499  lea     r15, [rbx+0DB0h]
0x18003b4a0  lea     r8, [rsp+78h+arg_10]
0x18003b4a8  lea     rdx, [rsp+78h+arg_8]
0x18003b4b0  mov     rcx, r15
0x18003b4b3  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSDDIErrorCtx@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSDDIErrorCtx@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSDDIErrorCtx@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SDDIErrorCtx *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SDDIErrorCtx *>>,0>>::find(ulong const &)
0x18003b4b8  mov     rcx, [rax]
0x18003b4bb  mov     [rsi+30h], rcx
0x18003b4bf  lea     r12, [r15+8]
0x18003b4c3  mov     r13, [r12]
0x18003b4c7  cmp     rcx, r13
0x18003b4ca  jnz     loc_18003B5BF
0x18003b4d0  mov     [rsp+78h+var_58], ebp
0x18003b4d4  mov     [rsp+78h+var_50], r14
0x18003b4d9  lea     rcx, [rsp+78h+var_58]
0x18003b4de  call    ??R?$_Conditionally_enabled_hash@K$00@std@@SA_KAEBK@Z; std::_Conditionally_enabled_hash<ulong,1>::operator()(ulong const &)
0x18003b4e3  mov     r14, rax
0x18003b4e6  mov     rcx, rax
0x18003b4e9  and     rcx, [r15+30h]
0x18003b4ed  add     rcx, rcx
0x18003b4f0  mov     rdx, [r15+18h]
0x18003b4f4  mov     rbx, [rdx+rcx*8+8]
0x18003b4f9  cmp     rbx, r13
0x18003b4fc  jnz     loc_18003B672
0x18003b502  mov     rax, 7FFFFFFFFFFFFFFh
0x18003b50c  cmp     [r15+10h], rax
0x18003b510  jz      loc_18003B61D
0x18003b516  mov     [rsp+78h+var_48], r12
0x18003b51b  mov     [rsp+78h+var_40], 0
0x18003b524  mov     ecx, 20h ; ' '
0x18003b529  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003b52e  mov     rbx, rax
0x18003b531  mov     [rsp+78h+var_40], rax
0x18003b536  lea     rdx, [rax+10h]
0x18003b53a  lea     r8, [rsp+78h+var_58]
0x18003b53f  call    ??$construct@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@U?$pair@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@1@$$QEAU?$pair@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>,void *>>>::construct<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>,std::pair<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *>>(std::allocator<std::_List_node<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>,void *>> &,std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *> * const,std::pair<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *> &&)
0x18003b544  nop
0x18003b545  mov     rdx, [r15+10h]
0x18003b549  add     rdx, 1
0x18003b54d  xorps   xmm0, xmm0
0x18003b550  js      loc_18003B6C3
0x18003b556  cvtsi2ss xmm0, rdx
0x18003b55b  mov     rcx, [r15+38h]
0x18003b55f  xorps   xmm1, xmm1
0x18003b562  test    rcx, rcx
0x18003b565  js      loc_18003B6E0
0x18003b56b  cvtsi2ss xmm1, rcx
0x18003b570  divss   xmm0, xmm1
0x18003b574  comiss  xmm0, dword ptr [r15]
0x18003b578  ja      loc_18003B62B
0x18003b57e  mov     rdx, [r13+8]
0x18003b582  inc     qword ptr [r15+10h]
0x18003b586  mov     [rbx], r13
0x18003b589  mov     [rbx+8], rdx
0x18003b58d  mov     [rdx], rbx
0x18003b590  mov     [r13+8], rbx
0x18003b594  mov     rax, [r15+30h]
0x18003b598  and     rax, r14
0x18003b59b  add     rax, rax
0x18003b59e  mov     rcx, [r15+18h]
0x18003b5a2  mov     r8, [rcx+rax*8]
0x18003b5a6  cmp     r8, [r12]
0x18003b5aa  jnz     loc_18003B699
0x18003b5b0  mov     [rcx+rax*8], rbx
0x18003b5b4  mov     [rcx+rax*8+8], rbx
0x18003b5b9  mov     [rsi+30h], rbx
0x18003b5bd  jmp     short loc_18003B5CB
0x18003b5bf  mov     rax, [rcx+18h]
0x18003b5c3  mov     [rsi+18h], rax
0x18003b5c7  mov     [rcx+18h], r14
0x18003b5cb  test    rdi, rdi
0x18003b5ce  jz      short loc_18003B5D9
0x18003b5d0  mov     rcx, rdi; SRWLock
0x18003b5d3  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b5d9  mov     rax, rsi
0x18003b5dc  mov     rbx, [rsp+78h+arg_18]
0x18003b5e4  add     rsp, 40h
0x18003b5e8  pop     r15
0x18003b5ea  pop     r14
0x18003b5ec  pop     r13
0x18003b5ee  pop     r12
0x18003b5f0  pop     rdi
0x18003b5f1  pop     rsi
0x18003b5f2  pop     rbp
0x18003b5f3  retn
0x18003b5f4  lea     rcx, [rbx+0E6Ch]
0x18003b5fb  mov     [rsi+28h], rcx
0x18003b5ff  mov     eax, [rbx+0E68h]
0x18003b605  mov     [rsi+8], eax
0x18003b608  mov     rax, [rcx]
0x18003b60b  mov     [rsi+0Ch], rax
0x18003b60f  mov     [rbx+0E68h], ebp
0x18003b615  mov     rax, [r14]
0x18003b618  mov     [rcx], rax
0x18003b61b  jmp     short loc_18003B5D9
0x18003b61d  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18003b624  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18003b62b  mov     rcx, r15
0x18003b62e  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@PEBVSmallDepthStencilStateDesc@@PEAVCDepthStencilState@@V?$_Uhash_compare@PEBVSmallDepthStencilStateDesc@@V?$HashDeref@VSmallDepthStencilStateDesc@@@@V?$EqualToDeref@VSmallDepthStencilStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallDepthStencilStateDesc@@PEAVCDepthStencilState@@@std@@@4@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<SmallDepthStencilStateDesc const *,CDepthStencilState *,std::_Uhash_compare<SmallDepthStencilStateDesc const *,HashDeref<SmallDepthStencilStateDesc>,EqualToDeref<SmallDepthStencilStateDesc>>,std::allocator<std::pair<SmallDepthStencilStateDesc const * const,CDepthStencilState *>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18003b633  mov     rdx, rax
0x18003b636  mov     rcx, r15
0x18003b639  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::_Forced_rehash(unsigned __int64)
0x18003b63e  mov     rax, [r15+30h]
0x18003b642  and     rax, r14
0x18003b645  add     rax, rax
0x18003b648  mov     rdx, [r15+18h]
0x18003b64c  mov     rcx, [rdx+rax*8+8]
0x18003b651  mov     r13, [r12]
0x18003b655  cmp     rcx, r13
0x18003b658  jz      loc_18003B57E
0x18003b65e  mov     r8, [rdx+rax*8]
0x18003b662  mov     eax, [rbx+10h]
0x18003b665  cmp     eax, [rcx+10h]
0x18003b668  jnz     short loc_18003B68C
0x18003b66a  mov     r13, [rcx]
0x18003b66d  jmp     loc_18003B57E
0x18003b672  mov     rax, [rdx+rcx*8]
0x18003b676  cmp     ebp, [rbx+10h]
0x18003b679  jz      loc_18003B5B9
0x18003b67f  cmp     rbx, rax
0x18003b682  jnz     short loc_18003B6B7
0x18003b684  mov     r13, rbx
0x18003b687  jmp     loc_18003B502
0x18003b68c  cmp     rcx, r8
0x18003b68f  jnz     short loc_18003B6BD
0x18003b691  mov     r13, rcx
0x18003b694  jmp     loc_18003B57E
0x18003b699  cmp     r8, r13
0x18003b69c  jnz     short loc_18003B6A7
0x18003b69e  mov     [rcx+rax*8], rbx
0x18003b6a2  jmp     loc_18003B5B9
0x18003b6a7  cmp     [rcx+rax*8+8], rdx
0x18003b6ac  jz      loc_18003B5B4
0x18003b6b2  jmp     loc_18003B5B9
0x18003b6b7  mov     rbx, [rbx+8]
0x18003b6bb  jmp     short loc_18003B676
0x18003b6bd  mov     rcx, [rcx+8]
0x18003b6c1  jmp     short loc_18003B665
0x18003b6c3  mov     rcx, rdx
0x18003b6c6  shr     rcx, 1
0x18003b6c9  mov     rax, rdx
0x18003b6cc  and     eax, 1
0x18003b6cf  or      rcx, rax
0x18003b6d2  cvtsi2ss xmm0, rcx
0x18003b6d7  addss   xmm0, xmm0
0x18003b6db  jmp     loc_18003B55B
0x18003b6e0  mov     rax, rcx
0x18003b6e3  shr     rax, 1
0x18003b6e6  and     ecx, 1
0x18003b6e9  or      rax, rcx
0x18003b6ec  cvtsi2ss xmm1, rax
0x18003b6f1  addss   xmm1, xmm1
0x18003b6f5  jmp     loc_18003B570
```
