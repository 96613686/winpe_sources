# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000ce20`
- end: `0x18000d229`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `1033`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180001484`
- `0x180001ef4`
- `0x1800020bd`
- `0x180008510`
- `0x18000ccdc`
- `0x18000ce20`
- `0x18000d230`
- `0x18000d460`
- `0x18001117c`
- `0x1800180ec`
- `0x18001a5ac`
- `0x18001ca3e`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d0e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d0e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000cfe7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d14b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000cfe7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d14b`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CWiGigDAFProviderAssociation *v7; // rbx
  int ProvidersIfNeeded; // esi
  _QWORD *v9; // rcx
  CWiGigDAFProviderQuery *v10; // rax
  CWiGigDAFProviderAssociation *v11; // rcx
  CWiGigDAFProviderAssociation *v12; // rax
  __int64 v13; // rax
  char *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  int Ptr; // edi
  __int64 v21; // rax
  _QWORD *v22; // rax
  const char *v23; // rdx
  PSRWLOCK pExceptionObject; // [rsp+28h] [rbp-20h] BYREF
  char v25; // [rsp+30h] [rbp-18h]

  v7 = 0;
  if ( !a4 )
  {
    ProvidersIfNeeded = -2147024809;
    goto LABEL_58;
  }
  *a4 = 0;
  if ( a2 )
  {
    ProvidersIfNeeded = -2147221232;
    goto LABEL_58;
  }
  v9 = (_QWORD *)*((_QWORD *)this + 2);
  if ( *v9 != 0x42579711B21858C6LL || v9[1] != 0xE1BCBE84005CC899uLL )
  {
    ProvidersIfNeeded = -2147221231;
    goto LABEL_58;
  }
  ProvidersIfNeeded = CClassFactory::CreateProvidersIfNeeded(this, 0);
  if ( ProvidersIfNeeded >= 0 )
  {
    ProvidersIfNeeded = CClassFactory::CreateDockCacheIfNeeded(this, a3);
    if ( ProvidersIfNeeded >= 0 )
    {
      if ( *(_QWORD *)&IID_IAepQuery.Data1 == *(_QWORD *)&a3->Data1
        && *(_QWORD *)IID_IAepQuery.Data4 == *(_QWORD *)a3->Data4 )
      {
        v10 = (CWiGigDAFProviderQuery *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v10 )
          v11 = CWiGigDAFProviderQuery::CWiGigDAFProviderQuery(
                  v10,
                  *((struct DockingProviders **)this + 8),
                  *((struct DockCache **)this + 9));
        else
          v11 = 0;
      }
      else
      {
        if ( *(_QWORD *)&IID_IAepAssociation.Data1 != *(_QWORD *)&a3->Data1
          || *(_QWORD *)IID_IAepAssociation.Data4 != *(_QWORD *)a3->Data4 )
        {
          if ( *(_QWORD *)&IID_IAepDevnodeManagement.Data1 == *(_QWORD *)&a3->Data1
            && *(_QWORD *)IID_IAepDevnodeManagement.Data4 == *(_QWORD *)a3->Data4 )
          {
            v14 = (char *)operator new(0x2C8u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v14 )
            {
              v15 = *((_QWORD *)this + 9);
              v16 = *((_QWORD *)this + 8);
              *(_QWORD *)v14 = &CWiGigDAFProviderDevnodeManagement::`vftable';
              *((_DWORD *)v14 + 2) = 0;
              *((_QWORD *)v14 + 75) = 0;
              *((_QWORD *)v14 + 76) = 0;
              *((_QWORD *)v14 + 77) = v16;
              if ( v16 )
                _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
              *((_QWORD *)v14 + 78) = v15;
              if ( v15 )
                _InterlockedIncrement((volatile signed __int32 *)(v15 + 96));
              InitializeCriticalSection((LPCRITICAL_SECTION)(v14 + 632));
              v14[672] = 0;
              *((_QWORD *)v14 + 85) = 0;
              *((_DWORD *)v14 + 172) = 0;
              *((_QWORD *)v14 + 87) = 0;
              *((_QWORD *)v14 + 88) = 0;
              _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
            }
            else
            {
              v14 = 0;
            }
          }
          else if ( *(_QWORD *)&IID_IAepDevicePresenceChallenge.Data1 == *(_QWORD *)&a3->Data1
                 && *(_QWORD *)IID_IAepDevicePresenceChallenge.Data4 == *(_QWORD *)a3->Data4 )
          {
            v14 = (char *)operator new(0x700u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v14 )
            {
              v17 = *((_QWORD *)this + 9);
              v18 = *((_QWORD *)this + 8);
              *(_QWORD *)v14 = &CWiGigDAFProviderChallenge::`vftable';
              *((_DWORD *)v14 + 2) = 0;
              *((_QWORD *)v14 + 2) = 0;
              *((_QWORD *)v14 + 3) = v18;
              if ( v18 )
                _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
              *((_QWORD *)v14 + 4) = 0;
              v14[40] = 0;
              *((_QWORD *)v14 + 223) = v17;
              if ( v17 )
                _InterlockedIncrement((volatile signed __int32 *)(v17 + 96));
              memset_0(v14 + 42, 0, 0x24Au);
              _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
            }
            else
            {
              v14 = 0;
            }
          }
          else
          {
            if ( *(_QWORD *)&GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef.Data1 != *(_QWORD *)&a3->Data1
              || *(_QWORD *)GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef.Data4 != *(_QWORD *)a3->Data4 )
            {
              ProvidersIfNeeded = -2147221231;
LABEL_52:
              if ( ProvidersIfNeeded >= 0 )
              {
                if ( v7 )
                  ProvidersIfNeeded = (**(__int64 (__fastcall ***)(CWiGigDAFProviderAssociation *, const struct _GUID *, void **))v7)(
                                        v7,
                                        a3,
                                        a4);
                else
                  ProvidersIfNeeded = -2147024882;
              }
              goto LABEL_58;
            }
            pExceptionObject = (PSRWLOCK)*((_QWORD *)this + 8);
            AcquireSRWLockShared(pExceptionObject);
            v25 = 1;
            Ptr = (int)pExceptionObject[2].Ptr;
            ReadLock::~ReadLock((ReadLock *)&pExceptionObject);
            if ( !Ptr )
              return 2147746065LL;
            v14 = (char *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v14 )
            {
              v21 = *((_QWORD *)this + 8);
              *(_QWORD *)v14 = &CDockInterface::`vftable';
              *((_DWORD *)v14 + 2) = 0;
              *((_QWORD *)v14 + 2) = v21;
              if ( v21 )
                _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
              InitializeCriticalSection((LPCRITICAL_SECTION)(v14 + 24));
              *((_QWORD *)v14 + 9) = 0;
              v22 = operator new(0x18u);
              if ( !v22 )
              {
                std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject, v23);
                throw (std::bad_alloc *)&pExceptionObject;
              }
              *((_QWORD *)v14 + 8) = v22;
              *v22 = v22;
              *(_QWORD *)(*((_QWORD *)v14 + 8) + 8LL) = *((_QWORD *)v14 + 8);
              *((_QWORD *)v14 + 11) = 0;
              WorkItems::WorkItems((WorkItems *)(v14 + 96));
              _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
            }
            else
            {
              v14 = 0;
            }
          }
          if ( !v14 )
            goto LABEL_52;
          v7 = (CWiGigDAFProviderAssociation *)v14;
          v13 = *(_QWORD *)v14;
          v11 = (CWiGigDAFProviderAssociation *)v14;
LABEL_50:
          (*(void (__fastcall **)(CWiGigDAFProviderAssociation *))(v13 + 8))(v11);
          goto LABEL_52;
        }
        v12 = (CWiGigDAFProviderAssociation *)operator new(0xCF0u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v12 )
          v11 = CWiGigDAFProviderAssociation::CWiGigDAFProviderAssociation(
                  v12,
                  *((struct DockingProviders **)this + 8),
                  *((struct DockCache **)this + 9));
        else
          v11 = 0;
      }
      if ( !v11 )
        goto LABEL_52;
      v7 = v11;
      v13 = *(_QWORD *)v11;
      goto LABEL_50;
    }
  }
LABEL_58:
  if ( v7 )
    (*(void (__fastcall **)(CWiGigDAFProviderAssociation *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)ProvidersIfNeeded;
}

```

## disassembly

```asm
0x18000ce20  push    rbp
0x18000ce22  push    rbx
0x18000ce23  push    rsi
0x18000ce24  push    rdi
0x18000ce25  push    r12
0x18000ce27  push    r13
0x18000ce29  push    r14
0x18000ce2b  push    r15
0x18000ce2d  mov     rbp, rsp
0x18000ce30  sub     rsp, 48h
0x18000ce34  mov     r12, r9
0x18000ce37  mov     r15, r8
0x18000ce3a  mov     r14, rcx
0x18000ce3d  xor     r13d, r13d
0x18000ce40  mov     ebx, r13d
0x18000ce43  mov     [rbp+arg_18], rbx
0x18000ce47  test    r9, r9
0x18000ce4a  jz      loc_18000D1E2
0x18000ce50  mov     [r9], r13
0x18000ce53  test    rdx, rdx
0x18000ce56  jz      short loc_18000CE62
0x18000ce58  mov     esi, 80040110h
0x18000ce5d  jmp     loc_18000D1E7
0x18000ce62  mov     rcx, [rcx+10h]
0x18000ce66  mov     rax, cs:qword_1800214C0
0x18000ce6d  cmp     rax, [rcx]
0x18000ce70  jnz     loc_18000D1DB
0x18000ce76  mov     rax, cs:qword_1800214C8
0x18000ce7d  cmp     rax, [rcx+8]
0x18000ce81  jnz     loc_18000D1DB
0x18000ce87  mov     rcx, r14; this
0x18000ce8a  call    ?CreateProvidersIfNeeded@CClassFactory@@AEAAJAEBU_GUID@@@Z; CClassFactory::CreateProvidersIfNeeded(_GUID const &)
0x18000ce8f  mov     esi, eax
0x18000ce91  test    eax, eax
0x18000ce93  js      loc_18000D1E7
0x18000ce99  mov     rdx, r15; struct _GUID *
0x18000ce9c  mov     rcx, r14; this
0x18000ce9f  call    ?CreateDockCacheIfNeeded@CClassFactory@@AEAAJAEBU_GUID@@@Z; CClassFactory::CreateDockCacheIfNeeded(_GUID const &)
0x18000cea4  mov     esi, eax
0x18000cea6  test    eax, eax
0x18000cea8  js      loc_18000D1E7
0x18000ceae  mov     rax, qword ptr cs:IID_IAepQuery.Data1
0x18000ceb5  cmp     rax, [r15]
0x18000ceb8  jnz     short loc_18000CEFB
0x18000ceba  mov     rax, qword ptr cs:IID_IAepQuery.Data4
0x18000cec1  cmp     rax, [r15+8]
0x18000cec5  jnz     short loc_18000CEFB
0x18000cec7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cece  mov     ecx, 0D0h; unsigned __int64
0x18000ced3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ced8  mov     [rbp+var_28], rax
0x18000cedc  test    rax, rax
0x18000cedf  jz      short loc_18000CEF6
0x18000cee1  mov     r8, [r14+48h]; struct DockCache *
0x18000cee5  mov     rdx, [r14+40h]; struct DockingProviders *
0x18000cee9  mov     rcx, rax; this
0x18000ceec  call    ??0CWiGigDAFProviderQuery@@QEAA@PEAVDockingProviders@@PEAVDockCache@@@Z; CWiGigDAFProviderQuery::CWiGigDAFProviderQuery(DockingProviders *,DockCache *)
0x18000cef1  mov     rcx, rax
0x18000cef4  jmp     short loc_18000CEF9
0x18000cef6  mov     rcx, r13
0x18000cef9  jmp     short loc_18000CF46
0x18000cefb  mov     rax, qword ptr cs:IID_IAepAssociation.Data1
0x18000cf02  cmp     rax, [r15]
0x18000cf05  jnz     short loc_18000CF5E
0x18000cf07  mov     rax, qword ptr cs:IID_IAepAssociation.Data4
0x18000cf0e  cmp     rax, [r15+8]
0x18000cf12  jnz     short loc_18000CF5E
0x18000cf14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cf1b  mov     ecx, 0CF0h; unsigned __int64
0x18000cf20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cf25  mov     [rbp+var_28], rax
0x18000cf29  test    rax, rax
0x18000cf2c  jz      short loc_18000CF43
0x18000cf2e  mov     r8, [r14+48h]; struct DockCache *
0x18000cf32  mov     rdx, [r14+40h]; struct DockingProviders *
0x18000cf36  mov     rcx, rax; this
0x18000cf39  call    ??0CWiGigDAFProviderAssociation@@QEAA@PEAVDockingProviders@@PEAVDockCache@@@Z; CWiGigDAFProviderAssociation::CWiGigDAFProviderAssociation(DockingProviders *,DockCache *)
0x18000cf3e  mov     rcx, rax
0x18000cf41  jmp     short loc_18000CF46
0x18000cf43  mov     rcx, r13
0x18000cf46  test    rcx, rcx
0x18000cf49  jz      loc_18000D1B3
0x18000cf4f  mov     rbx, rcx
0x18000cf52  mov     [rbp+arg_18], rcx
0x18000cf56  mov     rax, [rcx]
0x18000cf59  jmp     loc_18000D1A3
0x18000cf5e  mov     rax, qword ptr cs:IID_IAepDevnodeManagement.Data1
0x18000cf65  cmp     rax, [r15]
0x18000cf68  jnz     loc_18000D020
0x18000cf6e  mov     rax, qword ptr cs:IID_IAepDevnodeManagement.Data4
0x18000cf75  cmp     rax, [r15+8]
0x18000cf79  jnz     loc_18000D020
0x18000cf7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cf86  mov     ecx, 2C8h; unsigned __int64
0x18000cf8b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cf90  mov     rdi, rax
0x18000cf93  mov     [rbp+var_28], rax
0x18000cf97  test    rax, rax
0x18000cf9a  jz      short loc_18000D018
0x18000cf9c  mov     rax, [r14+48h]
0x18000cfa0  mov     rcx, [r14+40h]
0x18000cfa4  lea     rdx, ??_7CWiGigDAFProviderDevnodeManagement@@6B@; const CWiGigDAFProviderDevnodeManagement::`vftable'
0x18000cfab  mov     [rdi], rdx
0x18000cfae  mov     [rdi+8], r13d
0x18000cfb2  mov     [rdi+258h], r13
0x18000cfb9  mov     [rdi+260h], r13
0x18000cfc0  mov     [rdi+268h], rcx
0x18000cfc7  test    rcx, rcx
0x18000cfca  jz      short loc_18000CFD0
0x18000cfcc  lock inc dword ptr [rcx+8]
0x18000cfd0  mov     [rdi+270h], rax
0x18000cfd7  test    rax, rax
0x18000cfda  jz      short loc_18000CFE0
0x18000cfdc  lock inc dword ptr [rax+60h]
0x18000cfe0  lea     rcx, [rdi+278h]; lpCriticalSection
0x18000cfe7  call    cs:__imp_InitializeCriticalSection
0x18000cfed  nop
0x18000cfee  mov     [rdi+2A0h], r13b
0x18000cff5  lea     rax, [rdi+2A8h]
0x18000cffc  mov     [rbp+var_28], rax
0x18000d000  mov     [rax], r13
0x18000d003  mov     [rax+8], r13d
0x18000d007  mov     [rax+10h], r13
0x18000d00b  mov     [rax+18h], r13
0x18000d00f  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000d016  jmp     short loc_18000D01B
0x18000d018  mov     rdi, r13
0x18000d01b  jmp     loc_18000D191
0x18000d020  mov     rax, qword ptr cs:IID_IAepDevicePresenceChallenge.Data1
0x18000d027  cmp     rax, [r15]
0x18000d02a  jnz     loc_18000D0BB
0x18000d030  mov     rax, qword ptr cs:IID_IAepDevicePresenceChallenge.Data4
0x18000d037  cmp     rax, [r15+8]
0x18000d03b  jnz     short loc_18000D0BB
0x18000d03d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d044  mov     ecx, 700h; unsigned __int64
0x18000d049  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d04e  mov     rdi, rax
0x18000d051  mov     [rbp+var_28], rax
0x18000d055  test    rax, rax
0x18000d058  jz      short loc_18000D0B3
0x18000d05a  mov     rax, [r14+48h]
0x18000d05e  mov     rcx, [r14+40h]
0x18000d062  lea     rdx, ??_7CWiGigDAFProviderChallenge@@6B@; const CWiGigDAFProviderChallenge::`vftable'
0x18000d069  mov     [rdi], rdx
0x18000d06c  mov     [rdi+8], r13d
0x18000d070  mov     [rdi+10h], r13
0x18000d074  mov     [rdi+18h], rcx
0x18000d078  test    rcx, rcx
0x18000d07b  jz      short loc_18000D081
0x18000d07d  lock inc dword ptr [rcx+8]
0x18000d081  mov     [rdi+20h], r13
0x18000d085  mov     [rdi+28h], r13b
0x18000d089  mov     [rdi+6F8h], rax
0x18000d090  test    rax, rax
0x18000d093  jz      short loc_18000D099
0x18000d095  lock inc dword ptr [rax+60h]
0x18000d099  lea     rcx, [rdi+2Ah]; void *
0x18000d09d  xor     edx, edx; Val
0x18000d09f  mov     r8d, 24Ah; Size
0x18000d0a5  call    memset_0
0x18000d0aa  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000d0b1  jmp     short loc_18000D0B6
0x18000d0b3  mov     rdi, r13
0x18000d0b6  jmp     loc_18000D191
0x18000d0bb  mov     rax, qword ptr cs:_GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef.Data1
0x18000d0c2  cmp     rax, [r15]
0x18000d0c5  jnz     loc_18000D1AE
0x18000d0cb  mov     rax, qword ptr cs:_GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef.Data4
0x18000d0d2  cmp     rax, [r15+8]
0x18000d0d6  jnz     loc_18000D1AE
0x18000d0dc  mov     rdi, [r14+40h]
0x18000d0e0  mov     [rbp+pExceptionObject], rdi
0x18000d0e4  mov     rcx, rdi; SRWLock
0x18000d0e7  call    cs:__imp_AcquireSRWLockShared
0x18000d0ed  mov     [rbp+var_18], 1
0x18000d0f1  mov     edi, [rdi+10h]
0x18000d0f4  lea     rcx, [rbp+pExceptionObject]; this
0x18000d0f8  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x18000d0fd  test    edi, edi
0x18000d0ff  jnz     short loc_18000D10B
0x18000d101  mov     eax, 80040111h
0x18000d106  jmp     loc_18000D1FE
0x18000d10b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d112  mov     ecx, 0B0h; unsigned __int64
0x18000d117  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d11c  mov     rdi, rax
0x18000d11f  mov     [rbp+var_28], rax
0x18000d123  test    rax, rax
0x18000d126  jz      short loc_18000D18E
0x18000d128  mov     rax, [r14+40h]
0x18000d12c  lea     rcx, ??_7CDockInterface@@6B@; const CDockInterface::`vftable'
0x18000d133  mov     [rdi], rcx
0x18000d136  mov     [rdi+8], r13d
0x18000d13a  mov     [rdi+10h], rax
0x18000d13e  test    rax, rax
0x18000d141  jz      short loc_18000D147
0x18000d143  lock inc dword ptr [rax+8]
0x18000d147  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d14b  call    cs:__imp_InitializeCriticalSection
0x18000d151  nop
0x18000d152  mov     [rdi+48h], r13
0x18000d156  mov     ecx, 18h; Size
0x18000d15b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d160  test    rax, rax
0x18000d163  jz      loc_18000D20F
0x18000d169  mov     [rdi+40h], rax
0x18000d16d  mov     [rax], rax
0x18000d170  mov     rax, [rdi+40h]
0x18000d174  mov     [rax+8], rax
0x18000d178  mov     [rdi+58h], r13
0x18000d17c  lea     rcx, [rdi+60h]; this
0x18000d180  call    ??0WorkItems@@QEAA@XZ; WorkItems::WorkItems(void)
0x18000d185  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000d18c  jmp     short loc_18000D191
0x18000d18e  mov     rdi, r13
0x18000d191  test    rdi, rdi
0x18000d194  jz      short loc_18000D1B3
0x18000d196  mov     rbx, rdi
0x18000d199  mov     [rbp+arg_18], rbx
0x18000d19d  mov     rax, [rdi]
0x18000d1a0  mov     rcx, rdi
0x18000d1a3  mov     rax, [rax+8]
0x18000d1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ac  jmp     short loc_18000D1B3
0x18000d1ae  mov     esi, 80040111h
0x18000d1b3  test    esi, esi
0x18000d1b5  js      short loc_18000D1E7
0x18000d1b7  test    rbx, rbx
0x18000d1ba  jnz     short loc_18000D1C3
0x18000d1bc  mov     esi, 8007000Eh
0x18000d1c1  jmp     short loc_18000D1E7
0x18000d1c3  mov     rax, [rbx]
0x18000d1c6  mov     r8, r12
0x18000d1c9  mov     rdx, r15
0x18000d1cc  mov     rcx, rbx
0x18000d1cf  mov     rax, [rax]
0x18000d1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d7  mov     esi, eax
0x18000d1d9  jmp     short loc_18000D1E7
0x18000d1db  mov     esi, 80040111h
0x18000d1e0  jmp     short loc_18000D1E7
0x18000d1e2  mov     esi, 80070057h
0x18000d1e7  test    rbx, rbx
0x18000d1ea  jz      short loc_18000D1FC
0x18000d1ec  mov     rax, [rbx]
0x18000d1ef  mov     rcx, rbx
0x18000d1f2  mov     rax, [rax+10h]
0x18000d1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1fb  nop
0x18000d1fc  mov     eax, esi
0x18000d1fe  add     rsp, 48h
0x18000d202  pop     r15
0x18000d204  pop     r14
0x18000d206  pop     r13
0x18000d208  pop     r12
0x18000d20a  pop     rdi
0x18000d20b  pop     rsi
0x18000d20c  pop     rbx
0x18000d20d  pop     rbp
0x18000d20e  retn
0x18000d20f  lea     rcx, [rbp+pExceptionObject]; this
0x18000d213  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000d218  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000d21f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d223  call    _CxxThrowException_0
```
