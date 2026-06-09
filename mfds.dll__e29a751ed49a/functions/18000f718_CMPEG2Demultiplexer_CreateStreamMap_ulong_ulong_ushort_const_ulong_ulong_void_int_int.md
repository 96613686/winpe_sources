# CMPEG2Demultiplexer::CreateStreamMap_(ulong,ulong *,ushort const *,ulong,ulong,void *,int,int)

- ea: `0x18000f718`
- end: `0x18000f9f8`
- name: `?CreateStreamMap_@CMPEG2Demultiplexer@@AEAAJKPEAKPEBGKKPEAXHH@Z`
- size: `736`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this, unsigned int, unsigned int *, const unsigned __int16 *, unsigned int, unsigned int, void *, int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800436f0`
- `0x18009deb0`
- `0x1800b7ca0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x18000deac`
- `0x18000e2f8`
- `0x18000f718`
- `0x18000fa00`
- `0x1800140b0`
- `0x18002d514`
- `0x180032a50`
- `0x180051ce4`
- `0x180074160`
- `0x180074a06`
- `0x1800a7d34`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f98d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f98d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f7d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f7d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f9c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f9c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f8eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000f8eb`

## string_xrefs

- `0x18000f76d`: `CMPEG2Demultiplexer::CreateStreamMap_`
- `0x18000f948`: `CMPEG2Demultiplexer::CreateStreamMap_`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::CreateStreamMap_(
        struct _RTL_CRITICAL_SECTION **this,
        unsigned int a2,
        unsigned int *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        void *a7,
        int a8,
        int a9)
{
  __int64 v13; // rdx
  __int64 v14; // r8
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  int PinRecordLocked; // eax
  int v17; // ebx
  __int64 v18; // rdx
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v23[8]; // [rsp+50h] [rbp-79h] BYREF
  struct DEMUX_PIN_RECORD *v24; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v25[32]; // [rsp+60h] [rbp-69h] BYREF
  int v26; // [rsp+80h] [rbp-49h]
  int v27; // [rsp+88h] [rbp-41h]
  int v28; // [rsp+A8h] [rbp-21h]
  LPVOID pv; // [rsp+B0h] [rbp-19h]

  v24 = 0;
  memset_0(v25, 0, 0x58u);
  v27 = 1;
  v26 = 1;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "CMPEG2Demultiplexer::CreateStreamMap_", 3513);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDqqDD(*((_QWORD *)WPP_GLOBAL_Control + 17), v13, v14, this, a2, a3, a4, a5, a6);
  v15 = this[10];
  v24 = 0;
  EnterCriticalSection(v15);
  v24 = 0;
  PinRecordLocked = CMPEG2Demultiplexer::FindPinRecordLocked_((CMPEG2Demultiplexer *)this, a4, &v24, 0);
  v17 = PinRecordLocked;
  if ( PinRecordLocked < 0 )
  {
    if ( !byte_1800EACCB )
      goto LABEL_24;
    v18 = 86;
    goto LABEL_6;
  }
  if ( *((_DWORD *)v24 + 3) == 1 )
  {
    PinRecordLocked = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))(**(_QWORD **)v24 + 104LL))(
                        *(_QWORD *)v24,
                        0,
                        v25);
    v17 = PinRecordLocked;
    if ( PinRecordLocked )
    {
      if ( byte_1800EACCB )
      {
        v18 = 88;
LABEL_6:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          v18,
          &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids,
          this,
          PinRecordLocked);
      }
    }
    else
    {
      v17 = CMPEG2Demultiplexer::MapStreamToPinLocked_(
              (CMPEG2Demultiplexer *)this,
              a2,
              a3,
              a6,
              *(struct CMPEG2DemuxOutputPin **)v24,
              a5,
              a7,
              a8,
              a9);
      if ( v17 < 0 )
      {
        v19 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v19);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v17 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CMPEG2Demultiplexer::CreateStreamMap_", 3568, v17);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids,
            this,
            v17);
      }
    }
  }
  else
  {
    v17 = -2147467259;
    if ( byte_1800EACCB )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 87, &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids, this);
  }
LABEL_24:
  LeaveCriticalSection(this[10]);
  if ( v24 )
  {
    DEMUX_PIN_RECORD::Release(v24);
    v24 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
  if ( v28 )
    CoTaskMemFree(pv);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000f718  mov     [rsp-8+arg_8], rbx
0x18000f71d  push    rbp
0x18000f71e  push    rsi
0x18000f71f  push    rdi
0x18000f720  push    r12
0x18000f722  push    r13
0x18000f724  push    r14
0x18000f726  push    r15
0x18000f728  lea     rbp, [rsp-7]
0x18000f72d  sub     rsp, 0D0h
0x18000f734  mov     rax, cs:__security_cookie
0x18000f73b  xor     rax, rsp
0x18000f73e  mov     [rbp+37h+var_40], rax
0x18000f742  mov     r13, [rbp+37h+arg_30]
0x18000f746  mov     esi, edx
0x18000f748  xor     edx, edx; Val
0x18000f74a  mov     [rbp+37h+var_A8], 0
0x18000f752  mov     r14, r8
0x18000f755  mov     rdi, rcx
0x18000f758  lea     rcx, [rbp+37h+var_A0]; void *
0x18000f75c  mov     rbx, r9
0x18000f75f  lea     r8d, [rdx+58h]; Size
0x18000f763  call    memset_0
0x18000f768  mov     eax, 1
0x18000f76d  lea     rdx, aCmpeg2demultip_5; "CMPEG2Demultiplexer::CreateStreamMap_"
0x18000f774  mov     r8d, 0DB9h; int
0x18000f77a  mov     [rbp+37h+var_78], eax
0x18000f77d  lea     rcx, [rbp+37h+var_B0]; this
0x18000f781  mov     [rbp+37h+var_80], eax
0x18000f784  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000f789  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000f790  mov     r15d, [rbp+37h+arg_28]
0x18000f794  mov     r12d, [rbp+37h+arg_20]
0x18000f798  jb      short loc_18000F7C8
0x18000f79a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7a1  mov     r9, rdi
0x18000f7a4  mov     [rsp+100h+var_C0], r15d
0x18000f7a9  mov     [rsp+100h+var_C8], r12d
0x18000f7ae  mov     [rsp+100h+var_D0], rbx
0x18000f7b3  mov     rcx, [rcx+88h]
0x18000f7ba  mov     qword ptr [rsp+100h+var_D8], r14
0x18000f7bf  mov     dword ptr [rsp+100h+var_E0], esi
0x18000f7c3  call    WPP_SF_qDqqDD
0x18000f7c8  mov     rcx, [rdi+50h]; lpCriticalSection
0x18000f7cc  mov     [rbp+37h+var_A8], 0
0x18000f7d4  call    cs:__imp_EnterCriticalSection
0x18000f7db  nop     dword ptr [rax+rax+00h]
0x18000f7e0  xor     r9d, r9d; unsigned int *
0x18000f7e3  mov     [rbp+37h+var_A8], 0
0x18000f7eb  lea     r8, [rbp+37h+var_A8]; struct DEMUX_PIN_RECORD **
0x18000f7ef  mov     rdx, rbx; unsigned __int16 *
0x18000f7f2  mov     rcx, rdi; this
0x18000f7f5  call    ?FindPinRecordLocked_@CMPEG2Demultiplexer@@AEAAJPEBGPEAPEAUDEMUX_PIN_RECORD@@PEAK@Z; CMPEG2Demultiplexer::FindPinRecordLocked_(ushort const *,DEMUX_PIN_RECORD * *,ulong *)
0x18000f7fa  mov     ebx, eax
0x18000f7fc  test    eax, eax
0x18000f7fe  jns     short loc_18000F829
0x18000f800  cmp     cs:byte_1800EACCB, 1
0x18000f807  jb      loc_18000F989
0x18000f80d  mov     edx, 56h ; 'V'
0x18000f812  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f819  mov     dword ptr [rsp+100h+var_E0], eax
0x18000f81d  mov     rcx, [rcx+88h]
0x18000f824  jmp     loc_18000F97A
0x18000f829  mov     rcx, [rbp+37h+var_A8]
0x18000f82d  cmp     dword ptr [rcx+0Ch], 1
0x18000f831  jz      short loc_18000F86C
0x18000f833  mov     ebx, 80004005h
0x18000f838  cmp     cs:byte_1800EACCB, 1
0x18000f83f  jb      loc_18000F989
0x18000f845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f84c  lea     r8, WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids
0x18000f853  mov     edx, 57h ; 'W'
0x18000f858  mov     r9, rdi
0x18000f85b  mov     rcx, [rcx+88h]
0x18000f862  call    WPP_SF_q
0x18000f867  jmp     loc_18000F989
0x18000f86c  mov     rcx, [rcx]
0x18000f86f  lea     r8, [rbp+37h+var_A0]
0x18000f873  xor     edx, edx
0x18000f875  mov     rax, [rcx]
0x18000f878  mov     rax, [rax+68h]
0x18000f87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f881  mov     ebx, eax
0x18000f883  test    eax, eax
0x18000f885  jz      short loc_18000F89E
0x18000f887  cmp     cs:byte_1800EACCB, 1
0x18000f88e  jb      loc_18000F989
0x18000f894  mov     edx, 58h ; 'X'
0x18000f899  jmp     loc_18000F812
0x18000f89e  mov     eax, [rbp+37h+arg_40]
0x18000f8a4  mov     r9d, r15d; unsigned int
0x18000f8a7  mov     [rsp+100h+var_C0], eax; int
0x18000f8ab  mov     r8, r14; unsigned int *
0x18000f8ae  mov     eax, [rbp+37h+arg_38]
0x18000f8b1  mov     edx, esi; unsigned int
0x18000f8b3  mov     [rsp+100h+var_C8], eax; int
0x18000f8b7  mov     rax, [rbp+37h+var_A8]
0x18000f8bb  mov     [rsp+100h+var_D0], r13; void *
0x18000f8c0  mov     [rsp+100h+var_D8], r12d; unsigned int
0x18000f8c5  mov     rcx, [rax]
0x18000f8c8  mov     [rsp+100h+var_E0], rcx; struct CMPEG2DemuxOutputPin *
0x18000f8cd  mov     rcx, rdi; this
0x18000f8d0  call    ?MapStreamToPinLocked_@CMPEG2Demultiplexer@@AEAAJKPEAKKPEAVCMPEG2DemuxOutputPin@@KPEAXHH@Z; CMPEG2Demultiplexer::MapStreamToPinLocked_(ulong,ulong *,ulong,CMPEG2DemuxOutputPin *,ulong,void *,int,int)
0x18000f8d5  mov     ebx, eax
0x18000f8d7  test    eax, eax
0x18000f8d9  jns     loc_18000F989
0x18000f8df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f8e6  test    rcx, rcx
0x18000f8e9  jnz     short loc_18000F932
0x18000f8eb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000f8f2  nop     dword ptr [rax+rax+00h]
0x18000f8f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f8fe  mov     rcx, rax
0x18000f901  test    rax, rax
0x18000f904  jz      short loc_18000F924
0x18000f906  mov     rax, [rax]
0x18000f909  mov     edx, 7F0h
0x18000f90e  mov     rax, [rax+8]
0x18000f912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f917  test    eax, eax
0x18000f919  jz      short loc_18000F924
0x18000f91b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f922  jmp     short loc_18000F932
0x18000f924  lea     rcx, qword_1800EB130; this
0x18000f92b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000f932  cmp     byte ptr [rcx+8], 0
0x18000f936  jz      short loc_18000F95D
0x18000f938  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000f93d  cmp     [rax+7CCh], ebx
0x18000f943  jz      short loc_18000F95D
0x18000f945  mov     r9d, ebx; int
0x18000f948  lea     rdx, aCmpeg2demultip_5; "CMPEG2Demultiplexer::CreateStreamMap_"
0x18000f94f  mov     r8d, 0DF0h; int
0x18000f955  mov     rcx, rax; this
0x18000f958  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000f95d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f964  jb      short loc_18000F989
0x18000f966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f96d  mov     edx, 59h ; 'Y'
0x18000f972  mov     dword ptr [rsp+100h+var_E0], ebx
0x18000f976  mov     rcx, [rcx+10h]
0x18000f97a  mov     r9, rdi
0x18000f97d  lea     r8, WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids
0x18000f984  call    WPP_SF_qD
0x18000f989  mov     rcx, [rdi+50h]; lpCriticalSection
0x18000f98d  call    cs:__imp_LeaveCriticalSection
0x18000f994  nop     dword ptr [rax+rax+00h]
0x18000f999  mov     rcx, [rbp+37h+var_A8]; this
0x18000f99d  test    rcx, rcx
0x18000f9a0  jz      short loc_18000F9AF
0x18000f9a2  call    ?Release@DEMUX_PIN_RECORD@@QEAAKXZ; DEMUX_PIN_RECORD::Release(void)
0x18000f9a7  mov     [rbp+37h+var_A8], 0
0x18000f9af  lea     rcx, [rbp+37h+var_B0]; this
0x18000f9b3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000f9b8  cmp     [rbp+37h+var_58], 0
0x18000f9bc  jz      short loc_18000F9CE
0x18000f9be  mov     rcx, [rbp+37h+pv]; pv
0x18000f9c2  call    cs:__imp_CoTaskMemFree
0x18000f9c9  nop     dword ptr [rax+rax+00h]
0x18000f9ce  mov     eax, ebx
0x18000f9d0  mov     rcx, [rbp+37h+var_40]
0x18000f9d4  xor     rcx, rsp; StackCookie
0x18000f9d7  call    __security_check_cookie
0x18000f9dc  mov     rbx, [rsp+100h+arg_8]
0x18000f9e4  add     rsp, 0D0h
0x18000f9eb  pop     r15
0x18000f9ed  pop     r14
0x18000f9ef  pop     r13
0x18000f9f1  pop     r12
0x18000f9f3  pop     rdi
0x18000f9f4  pop     rsi
0x18000f9f5  pop     rbp
0x18000f9f6  retn
```
