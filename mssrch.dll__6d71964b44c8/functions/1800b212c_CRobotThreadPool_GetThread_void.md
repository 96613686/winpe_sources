# CRobotThreadPool::GetThread(void)

- ea: `0x1800b212c`
- end: `0x1800b2346`
- name: `?GetThread@CRobotThreadPool@@QEAAPEAVCRobotThread@@XZ`
- size: `538`
- prototype: `struct CRobotThread *__fastcall(CRobotThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000c7b4`

## callees

- `0x1800139a0`
- `0x180019bb0`
- `0x180061f78`
- `0x1800b212c`
- `0x1800b234c`
- `0x1800bff80`
- `0x1800d268c`
- `0x180124d80`
- `0x1801837bc`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b221c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b2326`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b221c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b2326`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b218f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b21e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b2285`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b22df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b218f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b21e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b2285`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b22df`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct CRobotThread *__fastcall CRobotThreadPool::GetThread(CRobotThreadPool *this)
{
  CRobotThread *v3; // rsi
  __int64 v4; // rax
  CRobotThread *v5; // rdi
  CRobotThread *v6; // rax
  __int64 v7; // rax
  CRobotThread *v8; // rax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::GetImpl'::`2'::impl) )
  {
    CSyncReadWrite::GetWriteAccess(this);
    if ( *((_DWORD *)this + 28) )
    {
LABEL_3:
      CSyncReadWrite::ReleaseWriteAccess(this);
      return 0;
    }
    v3 = 0;
    v4 = CTPtrSList<CRobotThread>::RemoveFirst((char *)this + 120);
    v5 = (CRobotThread *)v4;
    if ( v4 )
    {
      ++*((_DWORD *)this + 61);
      *(_DWORD *)(v4 + 56) = 0;
      *(_DWORD *)(v4 + 60) = GetTickCount();
    }
    else if ( *((_DWORD *)this + 48) < *((_DWORD *)this + 62) )
    {
      v6 = (CRobotThread *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
        v5 = CRobotThread::CRobotThread(v6);
      else
        v5 = 0;
      if ( v5 )
      {
        *((_DWORD *)v5 + 14) = 0;
        *((_DWORD *)v5 + 15) = GetTickCount();
        if ( (int)TThread<CRobotThread>::StartThread(v5) >= 0 )
        {
          CTPtrSList<CRobotThread>::Append((char *)this + 160, v5);
          ++*((_DWORD *)this + 61);
          SetThreadPriority(*((HANDLE *)v5 + 2), *((_DWORD *)this + 63));
        }
        else
        {
          v3 = v5;
          v5 = 0;
        }
      }
    }
    CSyncReadWrite::ReleaseWriteAccess(this);
    if ( v3 )
      (**(void (__fastcall ***)(CRobotThread *, __int64))v3)(v3, 1);
  }
  else
  {
    CSyncReadWrite::GetWriteAccess(this);
    if ( *((_DWORD *)this + 28) )
      goto LABEL_3;
    v7 = CTPtrSList<CRobotThread>::RemoveFirst((char *)this + 120);
    v5 = (CRobotThread *)v7;
    if ( v7 )
    {
      ++*((_DWORD *)this + 61);
      *(_DWORD *)(v7 + 56) = 0;
      *(_DWORD *)(v7 + 60) = GetTickCount();
    }
    else if ( *((_DWORD *)this + 48) < *((_DWORD *)this + 62) )
    {
      v8 = (CRobotThread *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v8 ? CRobotThread::CRobotThread(v8) : 0LL;
      if ( v5 )
      {
        *((_DWORD *)v5 + 14) = 0;
        *((_DWORD *)v5 + 15) = GetTickCount();
        if ( (int)TThread<CRobotThread>::StartThread(v5) >= 0 )
        {
          CTPtrSList<CRobotThread>::Append((char *)this + 160, v5);
          ++*((_DWORD *)this + 61);
          SetThreadPriority(*((HANDLE *)v5 + 2), *((_DWORD *)this + 63));
        }
        else
        {
          (**(void (__fastcall ***)(CRobotThread *, __int64))v5)(v5, 1);
          v5 = 0;
        }
      }
    }
    CSyncReadWrite::ReleaseWriteAccess(this);
  }
  return v5;
}

```

## disassembly

```asm
0x1800b212c  mov     [rsp+arg_0], rbx
0x1800b2131  push    rbp
0x1800b2132  push    rsi
0x1800b2133  push    rdi
0x1800b2134  sub     rsp, 20h
0x1800b2138  mov     rbx, rcx
0x1800b213b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix> `wil::Feature<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::GetImpl(void)'::`2'::impl
0x1800b2142  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::__private_IsEnabled(void)
0x1800b2147  mov     [rsp+38h+arg_8], rbx
0x1800b214c  mov     rcx, rbx; this
0x1800b214f  test    al, al
0x1800b2151  jz      loc_1800B224D
0x1800b2157  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x1800b215c  nop
0x1800b215d  cmp     dword ptr [rbx+70h], 0
0x1800b2161  jz      short loc_1800B2173
0x1800b2163  mov     rcx, rbx; this
0x1800b2166  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800b216b  nop
0x1800b216c  xor     eax, eax
0x1800b216e  jmp     loc_1800B2339
0x1800b2173  xor     esi, esi
0x1800b2175  lea     rcx, [rbx+78h]
0x1800b2179  call    ?RemoveFirst@?$CTPtrSList@VCRobotThread@@@@QEAAPEAVCRobotThread@@XZ; CTPtrSList<CRobotThread>::RemoveFirst(void)
0x1800b217e  mov     rdi, rax
0x1800b2181  test    rax, rax
0x1800b2184  jz      short loc_1800B219D
0x1800b2186  inc     dword ptr [rbx+0F4h]
0x1800b218c  mov     [rax+38h], esi
0x1800b218f  call    cs:__imp_GetTickCount
0x1800b2195  mov     [rdi+3Ch], eax
0x1800b2198  jmp     loc_1800B2223
0x1800b219d  lea     rbp, [rbx+0A0h]
0x1800b21a4  mov     eax, [rbx+0F8h]
0x1800b21aa  cmp     [rbp+20h], eax
0x1800b21ad  jnb     short loc_1800B2223
0x1800b21af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b21b6  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800b21bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b21c0  mov     [rsp+38h+arg_10], rax
0x1800b21c5  test    rax, rax
0x1800b21c8  jz      short loc_1800B21D7
0x1800b21ca  mov     rcx, rax; this
0x1800b21cd  call    ??0CRobotThread@@QEAA@XZ; CRobotThread::CRobotThread(void)
0x1800b21d2  mov     rdi, rax
0x1800b21d5  jmp     short loc_1800B21D9
0x1800b21d7  xor     edi, edi
0x1800b21d9  test    rdi, rdi
0x1800b21dc  jz      short loc_1800B2223
0x1800b21de  mov     dword ptr [rdi+38h], 0
0x1800b21e5  call    cs:__imp_GetTickCount
0x1800b21eb  mov     [rdi+3Ch], eax
0x1800b21ee  mov     rcx, rdi; lpParameter
0x1800b21f1  call    ?StartThread@?$TThread@VCRobotThread@@@@QEAAJK@Z; TThread<CRobotThread>::StartThread(ulong)
0x1800b21f6  test    eax, eax
0x1800b21f8  jns     short loc_1800B2201
0x1800b21fa  mov     rsi, rdi
0x1800b21fd  xor     edi, edi
0x1800b21ff  jmp     short loc_1800B2223
0x1800b2201  mov     rdx, rdi
0x1800b2204  mov     rcx, rbp
0x1800b2207  call    ?Append@?$CTPtrSList@VCRobotThread@@@@QEAAXPEAVCRobotThread@@@Z; CTPtrSList<CRobotThread>::Append(CRobotThread *)
0x1800b220c  inc     dword ptr [rbx+0F4h]
0x1800b2212  mov     edx, [rbx+0FCh]; nPriority
0x1800b2218  mov     rcx, [rdi+10h]; hThread
0x1800b221c  call    cs:__imp_SetThreadPriority
0x1800b2222  nop
0x1800b2223  mov     rcx, rbx; this
0x1800b2226  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800b222b  nop
0x1800b222c  test    rsi, rsi
0x1800b222f  jz      loc_1800B2336
0x1800b2235  mov     rax, [rsi]
0x1800b2238  mov     edx, 1
0x1800b223d  mov     rcx, rsi
0x1800b2240  mov     rax, [rax]
0x1800b2243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2248  jmp     loc_1800B2336
0x1800b224d  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x1800b2252  nop
0x1800b2253  cmp     dword ptr [rbx+70h], 0
0x1800b2257  jz      short loc_1800B2267
0x1800b2259  mov     rcx, rbx; this
0x1800b225c  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800b2261  nop
0x1800b2262  jmp     loc_1800B216C
0x1800b2267  lea     rcx, [rbx+78h]
0x1800b226b  call    ?RemoveFirst@?$CTPtrSList@VCRobotThread@@@@QEAAPEAVCRobotThread@@XZ; CTPtrSList<CRobotThread>::RemoveFirst(void)
0x1800b2270  mov     rdi, rax
0x1800b2273  test    rax, rax
0x1800b2276  jz      short loc_1800B2293
0x1800b2278  inc     dword ptr [rbx+0F4h]
0x1800b227e  mov     dword ptr [rax+38h], 0
0x1800b2285  call    cs:__imp_GetTickCount
0x1800b228b  mov     [rdi+3Ch], eax
0x1800b228e  jmp     loc_1800B232D
0x1800b2293  lea     rsi, [rbx+0A0h]
0x1800b229a  mov     eax, [rbx+0F8h]
0x1800b22a0  cmp     [rsi+20h], eax
0x1800b22a3  jnb     loc_1800B232D
0x1800b22a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b22b0  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800b22b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b22ba  mov     [rsp+38h+arg_10], rax
0x1800b22bf  test    rax, rax
0x1800b22c2  jz      short loc_1800B22D1
0x1800b22c4  mov     rcx, rax; this
0x1800b22c7  call    ??0CRobotThread@@QEAA@XZ; CRobotThread::CRobotThread(void)
0x1800b22cc  mov     rdi, rax
0x1800b22cf  jmp     short loc_1800B22D3
0x1800b22d1  xor     edi, edi
0x1800b22d3  test    rdi, rdi
0x1800b22d6  jz      short loc_1800B232D
0x1800b22d8  mov     dword ptr [rdi+38h], 0
0x1800b22df  call    cs:__imp_GetTickCount
0x1800b22e5  mov     [rdi+3Ch], eax
0x1800b22e8  mov     rcx, rdi; lpParameter
0x1800b22eb  call    ?StartThread@?$TThread@VCRobotThread@@@@QEAAJK@Z; TThread<CRobotThread>::StartThread(ulong)
0x1800b22f0  test    eax, eax
0x1800b22f2  jns     short loc_1800B230B
0x1800b22f4  mov     rax, [rdi]
0x1800b22f7  mov     edx, 1
0x1800b22fc  mov     rcx, rdi
0x1800b22ff  mov     rax, [rax]
0x1800b2302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2307  xor     edi, edi
0x1800b2309  jmp     short loc_1800B232D
0x1800b230b  mov     rdx, rdi
0x1800b230e  mov     rcx, rsi
0x1800b2311  call    ?Append@?$CTPtrSList@VCRobotThread@@@@QEAAXPEAVCRobotThread@@@Z; CTPtrSList<CRobotThread>::Append(CRobotThread *)
0x1800b2316  inc     dword ptr [rbx+0F4h]
0x1800b231c  mov     edx, [rbx+0FCh]; nPriority
0x1800b2322  mov     rcx, [rdi+10h]; hThread
0x1800b2326  call    cs:__imp_SetThreadPriority
0x1800b232c  nop
0x1800b232d  mov     rcx, rbx; this
0x1800b2330  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800b2335  nop
0x1800b2336  mov     rax, rdi
0x1800b2339  mov     rbx, [rsp+38h+arg_0]
0x1800b233e  add     rsp, 20h
0x1800b2342  pop     rdi
0x1800b2343  pop     rsi
0x1800b2344  pop     rbp
0x1800b2345  retn
```
