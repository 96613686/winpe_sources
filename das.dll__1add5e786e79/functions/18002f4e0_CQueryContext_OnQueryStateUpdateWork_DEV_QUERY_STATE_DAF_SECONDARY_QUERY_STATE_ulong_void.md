# CQueryContext::OnQueryStateUpdateWork(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,ulong,void *)

- ea: `0x18002f4e0`
- end: `0x18002f92a`
- name: `?OnQueryStateUpdateWork@CQueryContext@@SAXW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@KPEAX@Z`
- size: `1098`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004a4b0`
- `0x180052b30`

## callees

- `0x180009434`
- `0x18001a268`
- `0x18001efb0`
- `0x180024024`
- `0x1800243c4`
- `0x18002f4e0`
- `0x1800302b4`
- `0x1800306d8`
- `0x1800335bc`
- `0x18003bc80`
- `0x18003c79c`
- `0x180045df0`
- `0x180045f1c`
- `0x180053bd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f8a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f8a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f554`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f554`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f76d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f76d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f81a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f81a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f829`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f829`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f58d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f58d`

## string_xrefs

- `0x18002f711`: `onecore\base\devices\association\service\lib\querycontext.cpp`
- `0x18002f878`: `onecore\base\devices\association\service\lib\querycontext.cpp`

## pseudocode

```c
void __fastcall CQueryContext::OnQueryStateUpdateWork(int a1, int a2, int a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v6; // rsi
  int v8; // r15d
  const wchar_t **v9; // rbx
  void *v10; // rbp
  unsigned int v11; // edi
  int v12; // eax
  const GUID *v13; // r8
  const wchar_t *v14; // rax
  const wchar_t *v15; // rdi
  const wchar_t *v16; // rax
  int ProcessName; // eax
  int v18; // edx
  int v19; // ecx
  int v20; // r15d
  int v21; // edi
  __int64 *v22; // rdx
  int v23; // eax
  bool v24; // zf
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  const wchar_t *v28; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v30; // rax
  int v31; // eax
  int v32; // edx
  int v33; // r8d
  HANDLE v34; // rax
  int MessageGuid; // [rsp+20h] [rbp-2B8h]
  int ResultsForAllCacheEntries; // [rsp+40h] [rbp-298h]
  std::_Ref_count_base *v38[2]; // [rsp+48h] [rbp-290h] BYREF
  const wchar_t **v39; // [rsp+58h] [rbp-280h] BYREF
  std::_Ref_count_base *v40; // [rsp+60h] [rbp-278h]
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-270h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = *(_QWORD *)(a4 + 64);
  v6 = *(_QWORD *)(a4 + 16);
  ResultsForAllCacheEntries = 0;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v8 = a3 - 1;
  v9 = *(const wchar_t ***)(a4 + 56);
  v10 = 0;
  v38[0] = *(std::_Ref_count_base **)(a4 + 64);
  v11 = 0;
  v40 = v38[0];
  SRWLock = (PSRWLOCK)(v6 + 40);
  v39 = v9;
  while ( 1 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v6 + 40));
    v12 = *(_DWORD *)(v6 + 444);
    v13 = &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids;
    if ( v12 == v8 )
    {
      *(_DWORD *)(v6 + 444) = v12 + 1;
      goto LABEL_13;
    }
    if ( v11 > 0xA )
      break;
    ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 40));
    Sleep(100 * v11 * v11);
    ++v11;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)&WPP_RECORDER_INITIALIZED,
      (int)&WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      64,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      *(_QWORD *)(a4 + 16));
  *(_OWORD *)v38 = 0;
  std::shared_ptr<ProviderContext>::operator=(&v39, v38, v13);
  if ( v38[1] )
    std::_Ref_count_base::_Decref(v38[1]);
  v9 = v39;
  v13 = &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids;
  v38[0] = v40;
  a1 = 2;
LABEL_13:
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( v9 )
      v14 = *v9;
    else
      v14 = L"DAS";
    WPP_RECORDER_SF_SDq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)&WPP_RECORDER_INITIALIZED,
      (int)&WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      65,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      (__int64)v14,
      a1,
      *(_QWORD *)(a4 + 16));
  }
  *(_DWORD *)(a4 + 48) = a1;
  if ( *(_DWORD *)(v6 + 200) != 2 )
  {
    if ( a1 == 2 )
    {
      v15 = L"internal DAS error";
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        if ( v9 )
          v16 = *v9;
        else
          v16 = L"internal DAS error";
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)&WPP_RECORDER_INITIALIZED,
          (int)v13,
          66,
          &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
          (__int64)v16,
          *(_QWORD *)(a4 + 16));
      }
      if ( a2 != 3 )
      {
        memset_0(Filename, 0, 0x208u);
        ProcessName = GetProcessName(*(_DWORD *)(v6 + 400), Filename);
        if ( ProcessName < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16B8,
            (int)"onecore\\base\\devices\\association\\service\\lib\\querycontext.cpp",
            (const char *)(unsigned int)ProcessName);
        if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) != 0 )
        {
          if ( v9 )
            v15 = *v9;
          McTemplateU0zzqq_EventWriteTransfer(v19, v18, (_DWORD)v15, (unsigned int)Filename, *(_DWORD *)(v6 + 400), a2);
        }
      }
LABEL_44:
      if ( (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 40LL) & 1) != 0
        || a1 != 1
        || (ResultsForAllCacheEntries = CQueryContext::MakeResultsForAllCacheEntries((CQueryContext *)v6),
            ResultsForAllCacheEntries >= 0) )
      {
        ProcessHeap = GetProcessHeap();
        v30 = HeapAlloc(ProcessHeap, 0, 0x38u);
        v10 = v30;
        if ( v30 )
        {
          *(_DWORD *)(v6 + 200) = a1;
          *v30 = 0;
          v30[1] = 0;
          v30[2] = 0;
          *((_QWORD *)v30 + 6) = 0;
          *((_DWORD *)v30 + 6) = a1;
          v31 = CQueryContext::AddToResultSet((PSRWLOCK)v6, (struct _QUERY_RESULT *)v30);
          if ( v31 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x16D7,
              (int)"onecore\\base\\devices\\association\\service\\lib\\querycontext.cpp",
              (const char *)(unsigned int)v31);
        }
        else
        {
          ResultsForAllCacheEntries = -2147024882;
        }
      }
      goto LABEL_51;
    }
    v20 = 0;
    v21 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 144));
    v22 = *(__int64 **)(v6 + 184);
    while ( v22 != (__int64 *)(v6 + 184) )
    {
      v23 = v21 + 1;
      ++v20;
      v24 = *((_DWORD *)v22 + 12) == 1;
      v22 = (__int64 *)*v22;
      if ( !v24 )
        v23 = v21;
      v21 = v23;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 144));
    if ( v21 == v20 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        if ( v9 )
          v28 = *v9;
        else
          v28 = L"AEP Store";
        WPP_RECORDER_SF_dSq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v25,
          v26,
          v27,
          MessageGuid,
          a1,
          (__int64)v28,
          *(_QWORD *)(a4 + 16));
      }
      goto LABEL_44;
    }
  }
LABEL_51:
  ReleaseSRWLockExclusive(SRWLock);
  if ( ResultsForAllCacheEntries )
  {
    if ( v10 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v10);
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v32,
        v33,
        68,
        &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
        *(_QWORD *)(a4 + 16));
  }
  if ( v38[0] )
    std::_Ref_count_base::_Decref(v38[0]);
}

```

## disassembly

```asm
0x18002f4e0  push    rbx
0x18002f4e2  push    rbp
0x18002f4e3  push    rsi
0x18002f4e4  push    rdi
0x18002f4e5  push    r12
0x18002f4e7  push    r13
0x18002f4e9  push    r14
0x18002f4eb  push    r15
0x18002f4ed  sub     rsp, 298h
0x18002f4f4  mov     rax, cs:__security_cookie
0x18002f4fb  xor     rax, rsp
0x18002f4fe  mov     [rsp+2D8h+var_58], rax
0x18002f506  mov     rax, [r9+40h]
0x18002f50a  mov     r14, r9
0x18002f50d  mov     rsi, [r9+10h]
0x18002f511  mov     r12d, ecx
0x18002f514  mov     [rsp+2D8h+var_294], edx
0x18002f518  mov     [rsp+2D8h+var_298], 0
0x18002f520  test    rax, rax
0x18002f523  jz      short loc_18002F529
0x18002f525  lock inc dword ptr [rax+8]
0x18002f529  mov     r13, [r9+40h]
0x18002f52d  lea     r15d, [r8-1]
0x18002f531  mov     rbx, [r9+38h]
0x18002f535  xor     ebp, ebp
0x18002f537  mov     [rsp+2D8h+var_290], r13
0x18002f53c  xor     edi, edi
0x18002f53e  mov     [rsp+2D8h+var_278], r13
0x18002f543  lea     r13, [rsi+28h]
0x18002f547  mov     [rsp+2D8h+SRWLock], r13
0x18002f54c  mov     [rsp+2D8h+var_280], rbx
0x18002f551  mov     rcx, r13; SRWLock
0x18002f554  call    cs:__imp_AcquireSRWLockExclusive
0x18002f55a  mov     eax, [rsi+1BCh]
0x18002f560  lea     rdx, WPP_RECORDER_INITIALIZED; int
0x18002f567  lea     r8, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids; int
0x18002f56e  cmp     eax, r15d
0x18002f571  jz      loc_18002F610
0x18002f577  cmp     edi, 0Ah
0x18002f57a  ja      short loc_18002F597
0x18002f57c  mov     rcx, r13; SRWLock
0x18002f57f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f585  mov     eax, edi
0x18002f587  imul    eax, edi
0x18002f58a  imul    ecx, eax, 64h ; 'd'; dwMilliseconds
0x18002f58d  call    cs:__imp_Sleep
0x18002f593  inc     edi
0x18002f595  jmp     short loc_18002F551
0x18002f597  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18002f59e  jz      short loc_18002F5C4
0x18002f5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5a7  mov     r9d, 40h ; '@'; int
0x18002f5ad  mov     rax, [r14+10h]
0x18002f5b1  mov     qword ptr [rsp+2D8h+var_2B0], rax; char
0x18002f5b6  mov     [rsp+2D8h+MessageGuid], r8; MessageGuid
0x18002f5bb  mov     rcx, [rcx+28h]; int
0x18002f5bf  call    WPP_RECORDER_SF_q
0x18002f5c4  xorps   xmm0, xmm0
0x18002f5c7  lea     rdx, [rsp+2D8h+var_290]
0x18002f5cc  lea     rcx, [rsp+2D8h+var_280]
0x18002f5d1  movdqu  xmmword ptr [rsp+2D8h+var_290], xmm0
0x18002f5d7  call    ??4?$shared_ptr@VProviderContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ProviderContext>::operator=(std::shared_ptr<ProviderContext> &&)
0x18002f5dc  mov     rcx, [rsp+2D8h+var_290+8]; this
0x18002f5e1  test    rcx, rcx
0x18002f5e4  jz      short loc_18002F5EB
0x18002f5e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f5eb  mov     rax, [rsp+2D8h+var_278]
0x18002f5f0  lea     rdx, WPP_RECORDER_INITIALIZED
0x18002f5f7  mov     rbx, [rsp+2D8h+var_280]
0x18002f5fc  lea     r8, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18002f603  mov     [rsp+2D8h+var_290], rax
0x18002f608  mov     r12d, 2
0x18002f60e  jmp     short loc_18002F618
0x18002f610  inc     eax
0x18002f612  mov     [rsi+1BCh], eax
0x18002f618  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18002f61f  jz      short loc_18002F667
0x18002f621  mov     rcx, [r14+10h]
0x18002f625  test    rbx, rbx
0x18002f628  jz      short loc_18002F62F
0x18002f62a  mov     rax, [rbx]
0x18002f62d  jmp     short loc_18002F636
0x18002f62f  lea     rax, aDas; "DAS"
0x18002f636  mov     qword ptr [rsp+2D8h+var_2A0], rcx; char
0x18002f63b  mov     r9d, 41h ; 'A'; int
0x18002f641  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f648  mov     dword ptr [rsp+2D8h+var_2A8], r12d; char
0x18002f64d  mov     qword ptr [rsp+2D8h+var_2B0], rax; __int64
0x18002f652  mov     [rsp+2D8h+MessageGuid], r8; int
0x18002f657  mov     rcx, [rcx+28h]; int
0x18002f65b  call    WPP_RECORDER_SF_SDq
0x18002f660  lea     rdx, WPP_RECORDER_INITIALIZED; int
0x18002f667  mov     [r14+30h], r12d
0x18002f66b  cmp     dword ptr [rsi+0C8h], 2
0x18002f672  jz      loc_18002F88E
0x18002f678  cmp     r12d, 2
0x18002f67c  jnz     loc_18002F75E
0x18002f682  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18002f689  lea     rdi, aInternalDasErr; "internal DAS error"
0x18002f690  jz      short loc_18002F6D1
0x18002f692  mov     rcx, [r14+10h]
0x18002f696  test    rbx, rbx
0x18002f699  jz      short loc_18002F6A0
0x18002f69b  mov     rax, [rbx]
0x18002f69e  jmp     short loc_18002F6A3
0x18002f6a0  mov     rax, rdi
0x18002f6a3  mov     qword ptr [rsp+2D8h+var_2A8], rcx; char
0x18002f6a8  lea     r13, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18002f6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6b6  mov     r9d, 42h ; 'B'; int
0x18002f6bc  mov     qword ptr [rsp+2D8h+var_2B0], rax; __int64
0x18002f6c1  mov     [rsp+2D8h+MessageGuid], r13; MessageGuid
0x18002f6c6  mov     rcx, [rcx+28h]; int
0x18002f6ca  call    WPP_RECORDER_SF_Sq
0x18002f6cf  jmp     short loc_18002F6D8
0x18002f6d1  lea     r13, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18002f6d8  mov     r15d, [rsp+2D8h+var_294]
0x18002f6dd  cmp     r15d, 3
0x18002f6e1  jz      short loc_18002F752
0x18002f6e3  xor     edx, edx; Val
0x18002f6e5  lea     rcx, [rsp+2D8h+Filename]; void *
0x18002f6ea  mov     r8d, 208h; Size
0x18002f6f0  call    memset_0
0x18002f6f5  mov     ecx, [rsi+190h]; dwProcessId
0x18002f6fb  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x18002f700  call    ?GetProcessName@@YAJKQEAG@Z; GetProcessName(ulong,ushort * const)
0x18002f705  test    eax, eax
0x18002f707  jns     short loc_18002F725
0x18002f709  mov     rcx, [rsp+2D8h]; this
0x18002f711  lea     r8, aOnecoreBaseDev_15; "onecore\\base\\devices\\association\\se"...
0x18002f718  mov     r9d, eax; char *
0x18002f71b  mov     edx, 16B8h; void *
0x18002f720  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f725  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 2
0x18002f72c  jz      short loc_18002F752
0x18002f72e  mov     eax, [rsi+190h]
0x18002f734  test    rbx, rbx
0x18002f737  jz      short loc_18002F73C
0x18002f739  mov     rdi, [rbx]
0x18002f73c  mov     dword ptr [rsp+2D8h+var_2B0], r15d
0x18002f741  lea     r9, [rsp+2D8h+Filename]
0x18002f746  mov     r8, rdi
0x18002f749  mov     dword ptr [rsp+2D8h+MessageGuid], eax
0x18002f74d  call    McTemplateU0zzqq_EventWriteTransfer
0x18002f752  lea     rdi, WPP_RECORDER_INITIALIZED
0x18002f759  jmp     loc_18002F7F3
0x18002f75e  lea     r13, [rsi+90h]
0x18002f765  xor     r15d, r15d
0x18002f768  mov     rcx, r13; lpCriticalSection
0x18002f76b  xor     edi, edi
0x18002f76d  call    cs:__imp_EnterCriticalSection
0x18002f773  lea     r8, [rsi+0B8h]
0x18002f77a  mov     rdx, [r8]
0x18002f77d  jmp     short loc_18002F791
0x18002f77f  lea     eax, [rdi+1]
0x18002f782  inc     r15d
0x18002f785  cmp     dword ptr [rdx+30h], 1
0x18002f789  mov     rdx, [rdx]
0x18002f78c  cmovnz  eax, edi
0x18002f78f  mov     edi, eax
0x18002f791  cmp     rdx, r8
0x18002f794  jnz     short loc_18002F77F
0x18002f796  mov     rcx, r13; lpCriticalSection
0x18002f799  call    cs:__imp_LeaveCriticalSection
0x18002f79f  cmp     edi, r15d
0x18002f7a2  jnz     loc_18002F88E
0x18002f7a8  lea     rdi, WPP_RECORDER_INITIALIZED
0x18002f7af  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18002f7b6  jz      short loc_18002F7EC
0x18002f7b8  mov     rcx, [r14+10h]
0x18002f7bc  test    rbx, rbx
0x18002f7bf  jz      short loc_18002F7C6
0x18002f7c1  mov     rax, [rbx]
0x18002f7c4  jmp     short loc_18002F7CD
0x18002f7c6  lea     rax, aAepStore; "AEP Store"
0x18002f7cd  mov     qword ptr [rsp+2D8h+var_2A0], rcx
0x18002f7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7d9  mov     qword ptr [rsp+2D8h+var_2A8], rax
0x18002f7de  mov     dword ptr [rsp+2D8h+var_2B0], r12d
0x18002f7e3  mov     rcx, [rcx+28h]
0x18002f7e7  call    WPP_RECORDER_SF_dSq
0x18002f7ec  lea     r13, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18002f7f3  mov     rax, [rsi+88h]
0x18002f7fa  test    byte ptr [rax+28h], 1
0x18002f7fe  jnz     short loc_18002F81A
0x18002f800  cmp     r12d, 1
0x18002f804  jnz     short loc_18002F81A
0x18002f806  mov     rcx, rsi; this
0x18002f809  call    ?MakeResultsForAllCacheEntries@CQueryContext@@IEAAJXZ; CQueryContext::MakeResultsForAllCacheEntries(void)
0x18002f80e  mov     [rsp+2D8h+var_298], eax
0x18002f812  test    eax, eax
0x18002f814  js      loc_18002F89C
0x18002f81a  call    cs:__imp_GetProcessHeap
0x18002f820  xor     edx, edx; dwFlags
0x18002f822  mov     rcx, rax; hHeap
0x18002f825  lea     r8d, [rdx+38h]; dwBytes
0x18002f829  call    cs:__imp_HeapAlloc
0x18002f82f  mov     rbp, rax
0x18002f832  test    rax, rax
0x18002f835  jnz     short loc_18002F841
0x18002f837  mov     [rsp+2D8h+var_298], 8007000Eh
0x18002f83f  jmp     short loc_18002F89C
0x18002f841  mov     [rsi+0C8h], r12d
0x18002f848  xorps   xmm0, xmm0
0x18002f84b  movups  xmmword ptr [rbp+0], xmm0
0x18002f84f  xor     eax, eax
0x18002f851  mov     rdx, rbp; struct _QUERY_RESULT *
0x18002f854  movups  xmmword ptr [rbp+10h], xmm0
0x18002f858  mov     rcx, rsi; SRWLock
0x18002f85b  movups  xmmword ptr [rbp+20h], xmm0
0x18002f85f  mov     [rbp+30h], rax
0x18002f863  mov     [rbp+18h], r12d
0x18002f867  call    ?AddToResultSet@CQueryContext@@QEAAJPEAU_QUERY_RESULT@@@Z; CQueryContext::AddToResultSet(_QUERY_RESULT *)
0x18002f86c  test    eax, eax
0x18002f86e  jns     short loc_18002F89C
0x18002f870  mov     rcx, [rsp+2D8h]; this
0x18002f878  lea     r8, aOnecoreBaseDev_15; "onecore\\base\\devices\\association\\se"...
0x18002f87f  mov     r9d, eax; char *
0x18002f882  mov     edx, 16D7h; void *
0x18002f887  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f88c  jmp     short loc_18002F89C
0x18002f88e  lea     r13, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18002f895  lea     rdi, WPP_RECORDER_INITIALIZED
0x18002f89c  mov     rcx, [rsp+2D8h+SRWLock]; SRWLock
0x18002f8a1  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f8a7  cmp     [rsp+2D8h+var_298], 0
0x18002f8ac  jz      short loc_18002F8F4
0x18002f8ae  test    rbp, rbp
0x18002f8b1  jz      short loc_18002F8C7
0x18002f8b3  call    cs:__imp_GetProcessHeap
0x18002f8b9  mov     r8, rbp; lpMem
0x18002f8bc  xor     edx, edx; dwFlags
0x18002f8be  mov     rcx, rax; hHeap
0x18002f8c1  call    cs:__imp_HeapFree
0x18002f8c7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18002f8ce  jz      short loc_18002F8F4
0x18002f8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8d7  mov     r9d, 44h ; 'D'; int
0x18002f8dd  mov     rax, [r14+10h]
0x18002f8e1  mov     qword ptr [rsp+2D8h+var_2B0], rax; char
0x18002f8e6  mov     [rsp+2D8h+MessageGuid], r13; MessageGuid
0x18002f8eb  mov     rcx, [rcx+28h]; int
0x18002f8ef  call    WPP_RECORDER_SF_q
0x18002f8f4  mov     rax, [rsp+2D8h+var_290]
0x18002f8f9  test    rax, rax
0x18002f8fc  jz      short loc_18002F906
0x18002f8fe  mov     rcx, rax; this
0x18002f901  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f906  mov     rcx, [rsp+2D8h+var_58]
0x18002f90e  xor     rcx, rsp; StackCookie
0x18002f911  call    __security_check_cookie
0x18002f916  add     rsp, 298h
0x18002f91d  pop     r15
0x18002f91f  pop     r14
0x18002f921  pop     r13
0x18002f923  pop     r12
0x18002f925  pop     rdi
0x18002f926  pop     rsi
0x18002f927  pop     rbp
0x18002f928  pop     rbx
0x18002f929  retn
```
