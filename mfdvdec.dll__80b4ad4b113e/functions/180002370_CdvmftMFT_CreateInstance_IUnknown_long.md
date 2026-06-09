# CdvmftMFT::CreateInstance(IUnknown *,long *)

- ea: `0x180002370`
- end: `0x18000252e`
- name: `?CreateInstance@CdvmftMFT@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `446`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180001120`
- `0x180001ec8`
- `0x180002200`
- `0x180002370`
- `0x180004818`
- `0x180006950`
- `0x1800082ec`
- `0x180008358`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800023cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800023cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002450`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002450`

## pseudocode

```c
struct CUnknown *__fastcall CdvmftMFT::CreateInstance(struct IUnknown *a1, int *a2)
{
  char *v4; // rax
  CdvmftMFT *v5; // rbx
  struct IUnknown *v6; // r8
  int v7; // edi
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  int v12; // ecx
  int v13; // ecx
  char v15; // [rsp+50h] [rbp+18h] BYREF

  v4 = (char *)operator new(0x80u);
  v5 = (CdvmftMFT *)v4;
  if ( !v4 )
    return 0;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  v6 = (struct IUnknown *)v4;
  *((_QWORD *)v4 + 4) = 0;
  *((_QWORD *)v4 + 5) = 0;
  if ( a1 )
    v6 = a1;
  *((_QWORD *)v4 + 1) = v6;
  *((_DWORD *)v4 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
  *(_QWORD *)v5 = &CdvmftMFT::`vftable'{for `CUnknown'};
  *((_QWORD *)v5 + 3) = &CdvmftMFT::`vftable'{for `CMFTBase'};
  *((_QWORD *)v5 + 11) = &CdvmftMFT::`vftable'{for `IMFQualityAdvise2'};
  *((_QWORD *)v5 + 12) = &CdvmftMFT::`vftable'{for `IMFQualityAdviseLimits'};
  *((_QWORD *)v5 + 13) = &CdvmftMFT::`vftable'{for `IMFRateControl'};
  *((_QWORD *)v5 + 14) = &CdvmftMFT::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)v5 + 15) = &CdvmftMFT::`vftable'{for `IMFGetService'};
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v15, "CdvmftMFT::CdvmftMFT", 125);
  v7 = CdvmftMFT::Initialize(v5);
  if ( v7 < 0 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( !v8 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v9 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v9 + 499) != v7 )
        CallStackContext::TraceFailure(v9, "CdvmftMFT::CdvmftMFT", 125, v7);
    }
    if ( g_wppLevels )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids, v5, v7);
  }
  v10 = CallStackTracing::s_wpInstance;
  *a2 = v7;
  if ( *((_BYTE *)v10 + 8) )
  {
    v11 = CallStackTracing::Context(v10);
    v12 = *((_DWORD *)v11 + 497);
    if ( v12 )
    {
      v13 = v12 - 1;
      *((_DWORD *)v11 + 497) = v13;
      if ( !v13 )
        CallStackContext::ClearState((GUID *)v11);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002370  mov     [rsp+arg_0], rbx
0x180002375  mov     [rsp+arg_8], rsi
0x18000237a  push    rdi
0x18000237b  sub     rsp, 30h
0x18000237f  mov     rdi, rcx
0x180002382  mov     rsi, rdx
0x180002385  mov     ecx, 80h; Size
0x18000238a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000238f  mov     rbx, rax
0x180002392  test    rax, rax
0x180002395  jz      loc_180002519
0x18000239b  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800023a2  mov     r8, rax
0x1800023a5  mov     qword ptr [rax+20h], 0
0x1800023ad  test    rdi, rdi
0x1800023b0  mov     qword ptr [rax+28h], 0
0x1800023b8  lea     rcx, [rax+30h]; lpCriticalSection
0x1800023bc  cmovnz  r8, rdi
0x1800023c0  mov     [rax+8], r8
0x1800023c4  mov     dword ptr [rax+10h], 0
0x1800023cb  call    cs:__imp_InitializeCriticalSection
0x1800023d1  lea     rax, ??_7CdvmftMFT@@6BCUnknown@@@; const CdvmftMFT::`vftable'{for `CUnknown'}
0x1800023d8  mov     r8d, 7Dh ; '}'; int
0x1800023de  mov     [rbx], rax
0x1800023e1  lea     rdx, aCdvmftmftCdvmf; "CdvmftMFT::CdvmftMFT"
0x1800023e8  lea     rax, ??_7CdvmftMFT@@6BCMFTBase@@@; const CdvmftMFT::`vftable'{for `CMFTBase'}
0x1800023ef  mov     [rbx+18h], rax
0x1800023f3  lea     rcx, [rsp+38h+arg_10]; this
0x1800023f8  lea     rax, ??_7CdvmftMFT@@6BIMFQualityAdvise2@@@; const CdvmftMFT::`vftable'{for `IMFQualityAdvise2'}
0x1800023ff  mov     [rbx+58h], rax
0x180002403  lea     rax, ??_7CdvmftMFT@@6BIMFQualityAdviseLimits@@@; const CdvmftMFT::`vftable'{for `IMFQualityAdviseLimits'}
0x18000240a  mov     [rbx+60h], rax
0x18000240e  lea     rax, ??_7CdvmftMFT@@6BIMFRateControl@@@; const CdvmftMFT::`vftable'{for `IMFRateControl'}
0x180002415  mov     [rbx+68h], rax
0x180002419  lea     rax, ??_7CdvmftMFT@@6BIMFRateSupport@@@; const CdvmftMFT::`vftable'{for `IMFRateSupport'}
0x180002420  mov     [rbx+70h], rax
0x180002424  lea     rax, ??_7CdvmftMFT@@6BIMFGetService@@@; const CdvmftMFT::`vftable'{for `IMFGetService'}
0x18000242b  mov     [rbx+78h], rax
0x18000242f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180002434  mov     rcx, rbx; this
0x180002437  call    ?Initialize@CdvmftMFT@@QEAAJXZ; CdvmftMFT::Initialize(void)
0x18000243c  mov     edi, eax
0x18000243e  test    eax, eax
0x180002440  jns     loc_1800024E6
0x180002446  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18000244e  jnz     short loc_180002488
0x180002450  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180002456  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000245d  mov     rcx, rax
0x180002460  test    rax, rax
0x180002463  jz      short loc_18000247A
0x180002465  mov     rdx, [rax]
0x180002468  mov     rax, [rdx+8]
0x18000246c  mov     edx, 7F0h
0x180002471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002476  test    eax, eax
0x180002478  jnz     short loc_180002488
0x18000247a  lea     rax, off_180022080
0x180002481  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002488  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000248f  cmp     byte ptr [rcx+8], 0
0x180002493  jz      short loc_1800024BA
0x180002495  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x18000249a  cmp     [rax+7CCh], edi
0x1800024a0  jz      short loc_1800024BA
0x1800024a2  mov     r9d, edi; int
0x1800024a5  lea     rdx, aCdvmftmftCdvmf; "CdvmftMFT::CdvmftMFT"
0x1800024ac  mov     r8d, 7Dh ; '}'; int
0x1800024b2  mov     rcx, rax; this
0x1800024b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800024ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800024c1  jb      short loc_1800024E6
0x1800024c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024ca  lea     r8, WPP_eab3d75b25033173348b4e1d8c19ad3b_Traceguids
0x1800024d1  mov     edx, 0Ah
0x1800024d6  mov     [rsp+38h+var_18], edi
0x1800024da  mov     r9, rbx
0x1800024dd  mov     rcx, [rcx+10h]
0x1800024e1  call    WPP_SF_qd
0x1800024e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800024ed  mov     [rsi], edi
0x1800024ef  cmp     byte ptr [rcx+8], 0
0x1800024f3  jz      short loc_18000251B
0x1800024f5  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800024fa  mov     ecx, [rax+7C4h]
0x180002500  test    ecx, ecx
0x180002502  jz      short loc_18000251B
0x180002504  sub     ecx, 1
0x180002507  mov     [rax+7C4h], ecx
0x18000250d  jnz     short loc_18000251B
0x18000250f  mov     rcx, rax; this
0x180002512  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180002517  jmp     short loc_18000251B
0x180002519  xor     ebx, ebx
0x18000251b  mov     rsi, [rsp+38h+arg_8]
0x180002520  mov     rax, rbx
0x180002523  mov     rbx, [rsp+38h+arg_0]
0x180002528  add     rsp, 30h
0x18000252c  pop     rdi
0x18000252d  retn
```
