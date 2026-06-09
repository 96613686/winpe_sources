# MkvMfSourceLib::MkvMfSource::OnRead(IMFAsyncResult *)

- ea: `0x180016520`
- end: `0x180016838`
- name: `?OnRead@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncResult@@@Z`
- size: `792`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015240`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180016520`
- `0x18001a6d0`
- `0x18001b8b0`
- `0x180021b9c`
- `0x18004411c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016788`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016788`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800165f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800166da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800165f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800166da`

## string_xrefs

- `0x180016556`: `MkvMfSourceLib::MkvMfSource::OnRead`
- `0x18001665b`: `MkvMfSourceLib::MkvMfSource::OnRead`
- `0x180016744`: `MkvMfSourceLib::MkvMfSource::OnRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::OnRead(MkvMfSourceLib::MkvMfSource *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  unsigned int Operations; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  char v19; // bl
  int v21; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v22[4]; // [rsp+34h] [rbp-2Ch] BYREF
  MkvMfSourceLib::MkvMfSource *v23; // [rsp+38h] [rbp-28h]
  int *v24; // [rsp+40h] [rbp-20h]
  char *v25; // [rsp+48h] [rbp-18h] BYREF

  v21 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v22, "MkvMfSourceLib::MkvMfSource::OnRead", 1346);
  v7 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            &v25);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v23 = this;
  v24 = &v21;
  if ( a2 )
  {
    v25 = (char *)this + 104;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    if ( *((_QWORD *)this + 18) )
    {
      v19 = *((_BYTE *)this + 192);
      *((_DWORD *)this + 120) = MkvReader::AsyncReadCompletion((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), a2);
      if ( v19 )
      {
        *((_BYTE *)this + 486) = 0;
        if ( !*((_BYTE *)this + 485) )
        {
          *((_BYTE *)this + 485) = 1;
          MkvMfSourceLib::MkvMfSource::QueueOperation(this, (struct IMFAsyncCallback *)this + 63);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
        Operations = 0;
      }
      else
      {
        Operations = MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations((struct IMFAsyncCallback *)this, a2);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      }
    }
    else
    {
      v21 = -1072873851;
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( v21 < 0 && *((_DWORD *)v18 + 499) != v21 )
          CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfSource::OnRead", 1356, v21);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v21);
      Operations = v21;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    }
  }
  else
  {
    v21 = -2147024809;
    if ( !v7 )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( v21 < 0 && *((_DWORD *)v11 + 499) != v21 )
        CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::OnRead", 1350, v21);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v21);
    Operations = v21;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  return Operations;
}

```

## disassembly

```asm
0x180016520  mov     [rsp-18h+arg_10], rbx
0x180016525  mov     [rsp-18h+arg_18], rsi
0x18001652a  push    rbp
0x18001652b  push    rdi
0x18001652c  push    r14
0x18001652e  mov     rbp, rsp
0x180016531  sub     rsp, 60h
0x180016535  mov     rax, cs:__security_cookie
0x18001653c  xor     rax, rsp
0x18001653f  mov     [rbp+var_8], rax
0x180016543  mov     r14, rdx
0x180016546  mov     rsi, rcx
0x180016549  mov     [rbp+var_30], 0
0x180016550  mov     r8d, 542h; int
0x180016556  lea     rdx, aMkvmfsourcelib_26; "MkvMfSourceLib::MkvMfSource::OnRead"
0x18001655d  lea     rcx, [rbp+var_2C]; this
0x180016561  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016566  nop
0x180016567  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001656e  cmp     byte ptr [rcx+8], 0
0x180016572  jz      short loc_1800165D0
0x180016574  cmp     qword ptr [rsi+2B0h], 0
0x18001657c  jz      short loc_1800165D0
0x18001657e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016583  mov     rdi, rax
0x180016586  mov     rcx, [rsi+2B0h]
0x18001658d  mov     rdx, [rcx]
0x180016590  mov     rax, [rdx+128h]
0x180016597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659c  mov     ebx, eax
0x18001659e  mov     rcx, [rsi+2B0h]
0x1800165a5  mov     rdx, [rcx]
0x1800165a8  mov     rax, [rdx+118h]
0x1800165af  lea     rdx, [rbp+var_18]
0x1800165b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b8  movups  xmm0, xmmword ptr [rax]
0x1800165bb  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800165c3  mov     [rdi+7E0h], ebx
0x1800165c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800165d0  mov     [rbp+var_28], rsi
0x1800165d4  lea     rax, [rbp+var_30]
0x1800165d8  mov     [rbp+var_20], rax
0x1800165dc  test    r14, r14
0x1800165df  jnz     loc_1800166A1
0x1800165e5  mov     [rbp+var_30], 80070057h
0x1800165ec  test    rcx, rcx
0x1800165ef  jnz     short loc_180016638
0x1800165f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800165f8  nop     dword ptr [rax+rax+00h]
0x1800165fd  mov     rcx, rax
0x180016600  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016607  test    rax, rax
0x18001660a  jz      short loc_18001662A
0x18001660c  mov     rax, [rax]
0x18001660f  mov     edx, 7F0h
0x180016614  mov     rax, [rax+8]
0x180016618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001661d  test    eax, eax
0x18001661f  jz      short loc_18001662A
0x180016621  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016628  jmp     short loc_180016638
0x18001662a  lea     rcx, qword_1800DBF70; this
0x180016631  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016638  cmp     byte ptr [rcx+8], 0
0x18001663c  jz      short loc_18001666A
0x18001663e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016643  mov     r9d, [rbp+var_30]; int
0x180016647  test    r9d, r9d
0x18001664a  jns     short loc_18001666A
0x18001664c  cmp     [rax+7CCh], r9d
0x180016653  jz      short loc_18001666A
0x180016655  mov     r8d, 546h; int
0x18001665b  lea     rdx, aMkvmfsourcelib_26; "MkvMfSourceLib::MkvMfSource::OnRead"
0x180016662  mov     rcx, rax; this
0x180016665  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001666a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016671  jb      short loc_180016699
0x180016673  mov     edx, 94h
0x180016678  mov     eax, [rbp+var_30]
0x18001667b  mov     [rsp+60h+var_40], eax
0x18001667f  mov     r9, rsi
0x180016682  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180016689  mov     rcx, cs:WPP_GLOBAL_Control
0x180016690  mov     rcx, [rcx+10h]
0x180016694  call    WPP_SF_qD
0x180016699  mov     ebx, [rbp+var_30]
0x18001669c  jmp     loc_180016795
0x1800166a1  lea     rdi, [rsi+68h]
0x1800166a5  mov     [rbp+var_18], rdi
0x1800166a9  mov     rcx, rdi; lpCriticalSection
0x1800166ac  call    cs:__imp_EnterCriticalSection
0x1800166b3  nop     dword ptr [rax+rax+00h]
0x1800166b8  nop
0x1800166b9  cmp     qword ptr [rsi+90h], 0
0x1800166c1  jnz     loc_180016797
0x1800166c7  mov     [rbp+var_30], 0C00D3E85h
0x1800166ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800166d5  test    rcx, rcx
0x1800166d8  jnz     short loc_180016721
0x1800166da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800166e1  nop     dword ptr [rax+rax+00h]
0x1800166e6  mov     rcx, rax
0x1800166e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800166f0  test    rax, rax
0x1800166f3  jz      short loc_180016713
0x1800166f5  mov     rax, [rax]
0x1800166f8  mov     edx, 7F0h
0x1800166fd  mov     rax, [rax+8]
0x180016701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016706  test    eax, eax
0x180016708  jz      short loc_180016713
0x18001670a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016711  jmp     short loc_180016721
0x180016713  lea     rcx, qword_1800DBF70; this
0x18001671a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016721  cmp     byte ptr [rcx+8], 0
0x180016725  jz      short loc_180016753
0x180016727  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001672c  mov     r9d, [rbp+var_30]; int
0x180016730  test    r9d, r9d
0x180016733  jns     short loc_180016753
0x180016735  cmp     [rax+7CCh], r9d
0x18001673c  jz      short loc_180016753
0x18001673e  mov     r8d, 54Ch; int
0x180016744  lea     rdx, aMkvmfsourcelib_26; "MkvMfSourceLib::MkvMfSource::OnRead"
0x18001674b  mov     rcx, rax; this
0x18001674e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016753  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001675a  jb      short loc_180016782
0x18001675c  mov     edx, 95h
0x180016761  mov     eax, [rbp+var_30]
0x180016764  mov     [rsp+60h+var_40], eax
0x180016768  mov     r9, rsi
0x18001676b  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180016772  mov     rcx, cs:WPP_GLOBAL_Control
0x180016779  mov     rcx, [rcx+10h]
0x18001677d  call    WPP_SF_qD
0x180016782  mov     ebx, [rbp+var_30]
0x180016785  mov     rcx, rdi; lpCriticalSection
0x180016788  call    cs:__imp_LeaveCriticalSection
0x18001678f  nop     dword ptr [rax+rax+00h]
0x180016794  nop
0x180016795  jmp     short loc_18001680B
0x180016797  lea     rcx, [rsi+0B8h]; this
0x18001679e  mov     bl, [rcx+8]
0x1800167a1  mov     rdx, r14; struct IMFAsyncResult *
0x1800167a4  call    ?AsyncReadCompletion@MkvReader@@QEAAJPEAUIMFAsyncResult@@@Z; MkvReader::AsyncReadCompletion(IMFAsyncResult *)
0x1800167a9  mov     [rsi+1E0h], eax
0x1800167af  test    bl, bl
0x1800167b1  jz      short loc_1800167EE
0x1800167b3  mov     byte ptr [rsi+1E6h], 0
0x1800167ba  cmp     byte ptr [rsi+1E5h], 0
0x1800167c1  jnz     short loc_1800167DA
0x1800167c3  mov     byte ptr [rsi+1E5h], 1
0x1800167ca  lea     rdx, [rsi+1F8h]; struct IMFAsyncCallback *
0x1800167d1  mov     rcx, rsi; this
0x1800167d4  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x1800167d9  nop
0x1800167da  mov     rcx, rdi; lpCriticalSection
0x1800167dd  call    cs:__imp_LeaveCriticalSection
0x1800167e4  nop     dword ptr [rax+rax+00h]
0x1800167e9  nop
0x1800167ea  xor     ebx, ebx
0x1800167ec  jmp     short loc_18001680B
0x1800167ee  mov     rdx, r14; struct IMFAsyncResult *
0x1800167f1  mov     rcx, rsi; this
0x1800167f4  call    ?ProcessAsyncReadOperations@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncResult@@@Z; MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations(IMFAsyncResult *)
0x1800167f9  mov     ebx, eax
0x1800167fb  mov     rcx, rdi; lpCriticalSection
0x1800167fe  call    cs:__imp_LeaveCriticalSection
0x180016805  nop     dword ptr [rax+rax+00h]
0x18001680a  nop
0x18001680b  lea     rcx, [rbp+var_2C]; this
0x18001680f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180016814  mov     eax, ebx
0x180016816  mov     rcx, [rbp+var_8]
0x18001681a  xor     rcx, rsp; StackCookie
0x18001681d  call    __security_check_cookie
0x180016822  lea     r11, [rsp+60h+var_s0]
0x180016827  mov     rbx, [r11+30h]
0x18001682b  mov     rsi, [r11+38h]
0x18001682f  mov     rsp, r11
0x180016832  pop     r14
0x180016834  pop     rdi
0x180016835  pop     rbp
0x180016836  retn
```
