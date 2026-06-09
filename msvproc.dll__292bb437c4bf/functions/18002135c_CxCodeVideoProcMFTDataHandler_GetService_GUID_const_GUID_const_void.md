# CxCodeVideoProcMFTDataHandler::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x18002135c`
- end: `0x18002177b`
- name: `?GetService@CxCodeVideoProcMFTDataHandler@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1055`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180021130`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18002135c`
- `0x18003639c`
- `0x180054140`
- `0x180059920`
- `0x18007355c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800214a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021576`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021636`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800216bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800214a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021576`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021636`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800216bf`

## string_xrefs

- `0x18002137d`: `CxCodeVideoProcMFTDataHandler::GetService`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::GetService(
        CxCodeVideoProcMFTDataHandler *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 *v11; // rax
  __int128 v12; // xmm0
  __int64 v13; // rax
  int v14; // ebx
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 (__fastcall ***v17)(_QWORD, const struct _GUID *, void **); // r9
  int v18; // eax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  _BYTE v33[8]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v34[16]; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v33,
    "CxCodeVideoProcMFTDataHandler::GetService",
    7050);
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v11 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 388) + 280LL))(
                        *((_QWORD *)this + 388),
                        v34);
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v12 = *v11;
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v12;
  }
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MR_VIDEO_ACCELERATION_SERVICE.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MR_VIDEO_ACCELERATION_SERVICE.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)MR_VIDEO_ACCELERATION_SERVICE.Data4;
  if ( v13 )
  {
    v14 = -1072875846;
    if ( !v8 )
    {
      CallStackTracing::InitInstance();
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v15 + 499) != -1072875846 )
        CallStackContext::TraceFailure(v15, "CxCodeVideoProcMFTDataHandler::GetService", 7057, -1072875846);
    }
    if ( g_wppLevels )
    {
      v16 = 332;
LABEL_64:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, v14);
    }
  }
  else
  {
    v17 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 389);
    if ( v17 )
    {
      v22 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IMFDXGIDeviceManager.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IMFDXGIDeviceManager.Data1 )
        v22 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IMFDXGIDeviceManager.Data4;
      if ( v22 )
      {
        v26 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IMFVideoSampleAllocatorEx.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IMFVideoSampleAllocatorEx.Data1 )
          v26 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IMFVideoSampleAllocatorEx.Data4;
        if ( v26 )
        {
          v14 = -2147467262;
          if ( !v8 )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v8 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v8 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v8 + 8) )
          {
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
            if ( *((_DWORD *)v31 + 499) != -2147467262 )
              CallStackContext::TraceFailure(v31, "CxCodeVideoProcMFTDataHandler::GetService", 7076, -2147467262);
          }
          if ( g_wppLevels )
          {
            v16 = 336;
            goto LABEL_64;
          }
        }
        else
        {
          v14 = dlMFCreateVideoSampleAllocatorEx((__int64)a3, (__int64)a4);
          if ( v14 < 0 )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v28;
              if ( v28
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v27 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
              if ( *((_DWORD *)v29 + 499) != v14 )
                CallStackContext::TraceFailure(v29, "CxCodeVideoProcMFTDataHandler::GetService", 7072, v14);
            }
            if ( g_wppLevels )
            {
              v16 = 335;
              goto LABEL_64;
            }
          }
        }
      }
      else
      {
        v14 = (**v17)(*((_QWORD *)this + 389), a3, a4);
        if ( v14 < 0 )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v14 )
              CallStackContext::TraceFailure(v25, "CxCodeVideoProcMFTDataHandler::GetService", 7066, v14);
          }
          if ( g_wppLevels )
          {
            v16 = 334;
            goto LABEL_64;
          }
        }
      }
    }
    else
    {
      v18 = MF::OriginateError<38>(3222091450LL, L"Invalid/NULL DXGIDeviceManager Object");
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      v14 = v18;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( v14 < 0 && *((_DWORD *)v21 + 499) != v14 )
          CallStackContext::TraceFailure(v21, "CxCodeVideoProcMFTDataHandler::GetService", 7061, v14);
      }
      if ( g_wppLevels )
      {
        v16 = 333;
        goto LABEL_64;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002135c  push    rbx
0x18002135e  push    rbp
0x18002135f  push    rsi
0x180021360  push    rdi
0x180021361  push    r13
0x180021363  push    r14
0x180021365  push    r15
0x180021367  sub     rsp, 50h
0x18002136b  mov     rax, cs:__security_cookie
0x180021372  xor     rax, rsp
0x180021375  mov     [rsp+88h+var_40], rax
0x18002137a  mov     r14, r8
0x18002137d  lea     r13, aCxcodevideopro_16; "CxCodeVideoProcMFTDataHandler::GetServi"...
0x180021384  mov     r15, rdx
0x180021387  mov     rsi, rcx
0x18002138a  mov     rdx, r13; char *
0x18002138d  lea     rcx, [rsp+88h+var_58]; this
0x180021392  mov     r8d, 1B8Ah; int
0x180021398  mov     rbp, r9
0x18002139b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800213a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800213a7  cmp     byte ptr [rcx+8], 0
0x1800213ab  jz      short loc_18002140A
0x1800213ad  cmp     qword ptr [rsi+0C20h], 0
0x1800213b5  jz      short loc_18002140A
0x1800213b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800213bc  mov     rcx, [rsi+0C20h]
0x1800213c3  mov     rdi, rax
0x1800213c6  mov     rdx, [rcx]
0x1800213c9  mov     rax, [rdx+128h]
0x1800213d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213d5  mov     rcx, [rsi+0C20h]
0x1800213dc  mov     ebx, eax
0x1800213de  mov     rdx, [rcx]
0x1800213e1  mov     rax, [rdx+118h]
0x1800213e8  lea     rdx, [rsp+88h+var_50]
0x1800213ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800213f9  movups  xmm0, xmmword ptr [rax]
0x1800213fc  mov     [rdi+7E0h], ebx
0x180021402  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18002140a  mov     rax, [r15]
0x18002140d  sub     rax, qword ptr cs:MR_VIDEO_ACCELERATION_SERVICE.Data1
0x180021414  jnz     short loc_180021421
0x180021416  mov     rax, [r15+8]
0x18002141a  sub     rax, qword ptr cs:MR_VIDEO_ACCELERATION_SERVICE.Data4
0x180021421  test    rax, rax
0x180021424  jz      short loc_18002147A
0x180021426  mov     ebx, 0C00D36BAh
0x18002142b  test    rcx, rcx
0x18002142e  jnz     short loc_18002143C
0x180021430  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180021435  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002143c  cmp     byte ptr [rcx+8], 0
0x180021440  jz      short loc_180021463
0x180021442  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021447  cmp     [rax+7CCh], ebx
0x18002144d  jz      short loc_180021463
0x18002144f  mov     r9d, ebx; int
0x180021452  mov     r8d, 1B91h; int
0x180021458  mov     rdx, r13; char *
0x18002145b  mov     rcx, rax; this
0x18002145e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021463  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002146a  jb      loc_180021753
0x180021470  mov     edx, 14Ch
0x180021475  jmp     loc_180021735
0x18002147a  mov     r9, [rsi+0C28h]
0x180021481  test    r9, r9
0x180021484  jnz     loc_18002152C
0x18002148a  lea     rdx, aInvalidNullDxg; "Invalid/NULL DXGIDeviceManager Object"
0x180021491  mov     ecx, 0C00D36BAh
0x180021496  call    ??$OriginateError@$0CG@@MF@@YAJJAEAY0CG@$$CBG@Z; MF::OriginateError<38>(long,ushort const (&)[38])
0x18002149b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800214a2  mov     ebx, eax
0x1800214a4  test    rcx, rcx
0x1800214a7  jnz     short loc_1800214EA
0x1800214a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800214af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800214b6  mov     rcx, rax
0x1800214b9  test    rax, rax
0x1800214bc  jz      short loc_1800214DC
0x1800214be  mov     rdx, [rax]
0x1800214c1  mov     rax, [rdx+8]
0x1800214c5  mov     edx, 7F0h
0x1800214ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214cf  test    eax, eax
0x1800214d1  jz      short loc_1800214DC
0x1800214d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800214da  jmp     short loc_1800214EA
0x1800214dc  lea     rcx, qword_180153440; this
0x1800214e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800214ea  cmp     byte ptr [rcx+8], 0
0x1800214ee  jz      short loc_180021515
0x1800214f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800214f5  test    ebx, ebx
0x1800214f7  jns     short loc_180021515
0x1800214f9  cmp     [rax+7CCh], ebx
0x1800214ff  jz      short loc_180021515
0x180021501  mov     r9d, ebx; int
0x180021504  mov     r8d, 1B95h; int
0x18002150a  mov     rdx, r13; char *
0x18002150d  mov     rcx, rax; this
0x180021510  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021515  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002151c  jb      loc_180021753
0x180021522  mov     edx, 14Dh
0x180021527  jmp     loc_180021735
0x18002152c  mov     rax, [r14]
0x18002152f  sub     rax, qword ptr cs:IID_IMFDXGIDeviceManager.Data1
0x180021536  jnz     short loc_180021543
0x180021538  mov     rax, [r14+8]
0x18002153c  sub     rax, qword ptr cs:IID_IMFDXGIDeviceManager.Data4
0x180021543  test    rax, rax
0x180021546  jnz     loc_1800215F5
0x18002154c  mov     rax, [r9]
0x18002154f  mov     r8, rbp
0x180021552  mov     rdx, r14
0x180021555  mov     rcx, r9
0x180021558  mov     rax, [rax]
0x18002155b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021560  mov     ebx, eax
0x180021562  test    eax, eax
0x180021564  jns     loc_180021753
0x18002156a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021571  test    rcx, rcx
0x180021574  jnz     short loc_1800215B7
0x180021576  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002157c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021583  mov     rcx, rax
0x180021586  test    rax, rax
0x180021589  jz      short loc_1800215A9
0x18002158b  mov     rax, [rax]
0x18002158e  mov     edx, 7F0h
0x180021593  mov     rax, [rax+8]
0x180021597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002159c  test    eax, eax
0x18002159e  jz      short loc_1800215A9
0x1800215a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800215a7  jmp     short loc_1800215B7
0x1800215a9  lea     rcx, qword_180153440; this
0x1800215b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800215b7  cmp     byte ptr [rcx+8], 0
0x1800215bb  jz      short loc_1800215DE
0x1800215bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800215c2  cmp     [rax+7CCh], ebx
0x1800215c8  jz      short loc_1800215DE
0x1800215ca  mov     r9d, ebx; int
0x1800215cd  mov     r8d, 1B9Ah; int
0x1800215d3  mov     rdx, r13; char *
0x1800215d6  mov     rcx, rax; this
0x1800215d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800215de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800215e5  jb      loc_180021753
0x1800215eb  mov     edx, 14Eh
0x1800215f0  jmp     loc_180021735
0x1800215f5  mov     rax, [r14]
0x1800215f8  sub     rax, qword ptr cs:IID_IMFVideoSampleAllocatorEx.Data1
0x1800215ff  jnz     short loc_18002160C
0x180021601  mov     rax, [r14+8]
0x180021605  sub     rax, qword ptr cs:IID_IMFVideoSampleAllocatorEx.Data4
0x18002160c  test    rax, rax
0x18002160f  jnz     loc_1800216B5
0x180021615  mov     rdx, rbp
0x180021618  mov     rcx, r14
0x18002161b  call    dlMFCreateVideoSampleAllocatorEx
0x180021620  mov     ebx, eax
0x180021622  test    eax, eax
0x180021624  jns     loc_180021753
0x18002162a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021631  test    rcx, rcx
0x180021634  jnz     short loc_180021677
0x180021636  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002163c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021643  mov     rcx, rax
0x180021646  test    rax, rax
0x180021649  jz      short loc_180021669
0x18002164b  mov     rax, [rax]
0x18002164e  mov     edx, 7F0h
0x180021653  mov     rax, [rax+8]
0x180021657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002165c  test    eax, eax
0x18002165e  jz      short loc_180021669
0x180021660  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021667  jmp     short loc_180021677
0x180021669  lea     rcx, qword_180153440; this
0x180021670  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021677  cmp     byte ptr [rcx+8], 0
0x18002167b  jz      short loc_18002169E
0x18002167d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021682  cmp     [rax+7CCh], ebx
0x180021688  jz      short loc_18002169E
0x18002168a  mov     r9d, ebx; int
0x18002168d  mov     r8d, 1BA0h; int
0x180021693  mov     rdx, r13; char *
0x180021696  mov     rcx, rax; this
0x180021699  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002169e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800216a5  jb      loc_180021753
0x1800216ab  mov     edx, 14Fh
0x1800216b0  jmp     loc_180021735
0x1800216b5  mov     ebx, 80004002h
0x1800216ba  test    rcx, rcx
0x1800216bd  jnz     short loc_180021700
0x1800216bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800216c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800216cc  mov     rcx, rax
0x1800216cf  test    rax, rax
0x1800216d2  jz      short loc_1800216F2
0x1800216d4  mov     rax, [rax]
0x1800216d7  mov     edx, 7F0h
0x1800216dc  mov     rax, [rax+8]
0x1800216e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216e5  test    eax, eax
0x1800216e7  jz      short loc_1800216F2
0x1800216e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800216f0  jmp     short loc_180021700
0x1800216f2  lea     rcx, qword_180153440; this
0x1800216f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021700  cmp     byte ptr [rcx+8], 0
0x180021704  jz      short loc_180021727
0x180021706  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002170b  cmp     [rax+7CCh], ebx
0x180021711  jz      short loc_180021727
0x180021713  mov     r9d, ebx; int
0x180021716  mov     r8d, 1BA4h; int
0x18002171c  mov     rdx, r13; char *
0x18002171f  mov     rcx, rax; this
0x180021722  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021727  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002172e  jb      short loc_180021753
0x180021730  mov     edx, 150h
0x180021735  mov     rcx, cs:WPP_GLOBAL_Control
0x18002173c  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180021743  mov     r9, rsi
0x180021746  mov     [rsp+88h+var_68], ebx
0x18002174a  mov     rcx, [rcx+10h]
0x18002174e  call    WPP_SF_qD
0x180021753  lea     rcx, [rsp+88h+var_58]; this
0x180021758  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002175d  mov     eax, ebx
0x18002175f  mov     rcx, [rsp+88h+var_40]
0x180021764  xor     rcx, rsp; StackCookie
0x180021767  call    __security_check_cookie
0x18002176c  add     rsp, 50h
0x180021770  pop     r15
0x180021772  pop     r14
0x180021774  pop     r13
0x180021776  pop     rdi
0x180021777  pop     rsi
0x180021778  pop     rbp
0x180021779  pop     rbx
0x18002177a  retn
```
