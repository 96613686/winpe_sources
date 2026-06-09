# CDShowTransPinInt::EndOfStream(void)

- ea: `0x180053be0`
- end: `0x180053db8`
- name: `?EndOfStream@CDShowTransPinInt@@UEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDShowTransPinInt *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x18001c5a0`
- `0x18002d514`
- `0x18002e8a0`
- `0x180032a50`
- `0x180036f50`
- `0x180051ce4`
- `0x180053be0`
- `0x180053dc0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053d98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053d98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053cc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053cc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDShowTransPinInt::EndOfStream(CDShowTransPinInt *this)
{
  __int64 v2; // rax
  struct CDShowTransRoot *RootObj; // rax
  __int64 v4; // rcx
  CallStackTracing *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v10; // rcx
  char v12; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+58h] [rbp+10h]

  v13 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "CDShowTransPinInt::EndOfStream", 783);
  v2 = *((_QWORD *)this + 2);
  if ( !*(_DWORD *)(v2 + 80) )
  {
    *(_DWORD *)(v2 + 12) = 2;
    if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 18, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this);
    CDShowTransInputPin::QueueOutputSample(*((RTL_SRWLOCK **)this + 2), 0);
    RootObj = CDShowTransPin::GetRootObj(*((CDShowTransPin **)this + 2), 1);
    if ( RootObj )
    {
      v4 = *((_QWORD *)RootObj + 3);
      if ( *(_DWORD *)(v4 + 272) )
      {
        v13 = CMediaEventGenerator::QueueEvent(
                (CMediaEventGenerator *)(v4 + 88),
                0x25Au,
                &GUID_00000000_0000_0000_0000_000000000000,
                0,
                0);
        if ( v13 < 0 )
        {
          v5 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v6;
            if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
            {
              v5 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v5 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v5 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
            if ( v13 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v13 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransPinInt::EndOfStream", 798, v13);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              &WPP_e67ca36682193615575df34b6326caef_Traceguids,
              this,
              v13);
        }
      }
      v8 = *(_QWORD *)(*((_QWORD *)this + 2) + 48LL);
      CurrentThreadId = GetCurrentThreadId();
      v10 = (CMFSRWLock *)(v8 + 80);
      if ( *(_DWORD *)(v8 + 88) == CurrentThreadId )
        CMFSRWLock::UnlockExclusive(v10);
      else
        ReleaseSRWLockShared((PSRWLOCK)v10);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return 0;
}

```

## disassembly

```asm
0x180053be0  push    rbx
0x180053be2  sub     rsp, 40h
0x180053be6  mov     rbx, rcx
0x180053be9  mov     [rsp+48h+arg_8], 0
0x180053bf1  mov     r8d, 30Fh; int
0x180053bf7  lea     rdx, aCdshowtranspin_6; "CDShowTransPinInt::EndOfStream"
0x180053bfe  lea     rcx, [rsp+48h+arg_0]; this
0x180053c03  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180053c08  nop
0x180053c09  mov     [rsp+48h+var_18], 0
0x180053c12  lea     rax, [rsp+48h+arg_8]
0x180053c17  mov     [rsp+48h+var_10], rax
0x180053c1c  mov     rax, [rbx+10h]
0x180053c20  cmp     dword ptr [rax+50h], 0
0x180053c24  jnz     loc_180053DA5
0x180053c2a  mov     dword ptr [rax+0Ch], 2
0x180053c31  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180053c38  jb      short loc_180053C5C
0x180053c3a  mov     edx, 12h
0x180053c3f  mov     r9, rbx
0x180053c42  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x180053c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c50  mov     rcx, [rcx+88h]
0x180053c57  call    WPP_SF_q
0x180053c5c  xor     edx, edx; struct IMediaSample *
0x180053c5e  mov     rcx, [rbx+10h]; this
0x180053c62  call    ?QueueOutputSample@CDShowTransInputPin@@QEAAJPEAUIMediaSample@@@Z; CDShowTransInputPin::QueueOutputSample(IMediaSample *)
0x180053c67  mov     edx, 1; int
0x180053c6c  mov     rcx, [rbx+10h]; this
0x180053c70  call    ?GetRootObj@CDShowTransPin@@QEAAPEAVCDShowTransRoot@@H@Z; CDShowTransPin::GetRootObj(int)
0x180053c75  test    rax, rax
0x180053c78  jz      loc_180053DA5
0x180053c7e  mov     rcx, [rax+18h]
0x180053c82  cmp     dword ptr [rcx+110h], 0
0x180053c89  jz      loc_180053D72
0x180053c8f  add     rcx, 58h ; 'X'; this
0x180053c93  mov     [rsp+48h+var_28], 0; struct tagPROPVARIANT *
0x180053c9c  xor     r9d, r9d; int
0x180053c9f  lea     r8, _GUID_00000000_0000_0000_0000_000000000000; struct _GUID *
0x180053ca6  mov     edx, 25Ah; unsigned int
0x180053cab  call    ?QueueEvent@CMediaEventGenerator@@UEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z; CMediaEventGenerator::QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)
0x180053cb0  mov     [rsp+48h+arg_8], eax
0x180053cb4  test    eax, eax
0x180053cb6  jns     loc_180053D72
0x180053cbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053cc3  test    rcx, rcx
0x180053cc6  jnz     short loc_180053D0F
0x180053cc8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053ccf  nop     dword ptr [rax+rax+00h]
0x180053cd4  mov     rcx, rax
0x180053cd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053cde  test    rax, rax
0x180053ce1  jz      short loc_180053D01
0x180053ce3  mov     rax, [rax]
0x180053ce6  mov     edx, 7F0h
0x180053ceb  mov     rax, [rax+8]
0x180053cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cf4  test    eax, eax
0x180053cf6  jz      short loc_180053D01
0x180053cf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053cff  jmp     short loc_180053D0F
0x180053d01  lea     rcx, qword_1800EB130; this
0x180053d08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053d0f  cmp     byte ptr [rcx+8], 0
0x180053d13  jz      short loc_180053D42
0x180053d15  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053d1a  mov     r9d, [rsp+48h+arg_8]; int
0x180053d1f  test    r9d, r9d
0x180053d22  jns     short loc_180053D42
0x180053d24  cmp     [rax+7CCh], r9d
0x180053d2b  jz      short loc_180053D42
0x180053d2d  mov     r8d, 31Eh; int
0x180053d33  lea     rdx, aCdshowtranspin_6; "CDShowTransPinInt::EndOfStream"
0x180053d3a  mov     rcx, rax; this
0x180053d3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053d42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053d49  jb      short loc_180053D72
0x180053d4b  mov     edx, 13h
0x180053d50  mov     eax, [rsp+48h+arg_8]
0x180053d54  mov     dword ptr [rsp+48h+var_28], eax
0x180053d58  mov     r9, rbx
0x180053d5b  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x180053d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d69  mov     rcx, [rcx+10h]
0x180053d6d  call    WPP_SF_qD
0x180053d72  mov     rax, [rbx+10h]
0x180053d76  mov     rbx, [rax+30h]
0x180053d7a  call    cs:__imp_GetCurrentThreadId
0x180053d81  nop     dword ptr [rax+rax+00h]
0x180053d86  mov     edx, [rbx+58h]
0x180053d89  lea     rcx, [rbx+50h]; this
0x180053d8d  cmp     edx, eax
0x180053d8f  jnz     short loc_180053D98
0x180053d91  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x180053d96  jmp     short loc_180053DA5
0x180053d98  call    cs:__imp_ReleaseSRWLockShared
0x180053d9f  nop     dword ptr [rax+rax+00h]
0x180053da4  nop
0x180053da5  lea     rcx, [rsp+48h+arg_0]; this
0x180053daa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180053daf  xor     eax, eax
0x180053db1  add     rsp, 40h
0x180053db5  pop     rbx
0x180053db6  retn
```
