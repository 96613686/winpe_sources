# BLTQUEUE::BltQueueWorker(void)

- ea: `0x140095b30`
- end: `0x140096880`
- name: `?BltQueueWorker@BLTQUEUE@@QEAAXXZ`
- size: `3408`
- prototype: `void __fastcall __noreturn(BLTQUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1403e8ad0`

## callees

- `0x140015940`
- `0x140018244`
- `0x1400198d8`
- `0x14001a1f0`
- `0x14001a38c`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001d1a0`
- `0x14001f630`
- `0x14002ee60`
- `0x14003731c`
- `0x140044920`
- `0x140044fb4`
- `0x140047ad4`
- `0x140058918`
- `0x140095b30`
- `0x140096a00`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14018a118`
- `0x14019d3e0`
- `0x1401e5fd0`
- `0x1401e6068`
- `0x1401e6100`
- `0x140307e0c`
- `0x14030817c`
- `0x1403087c8`
- `0x140308a30`
- `0x140309530`
- `0x1403097b8`
- `0x14038000c`
- `0x140392554`
- `0x1403cadb4`
- `0x1403cae50`
- `0x1403d9308`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140095b82`
- `ntoskrnl!KeInitializeEvent` at `0x140095b99`
- `ntoskrnl!KeInitializeEvent` at `0x140095b82`
- `ntoskrnl!KeInitializeEvent` at `0x140095b99`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140096119`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140096119`
- `ntoskrnl!KeSetEvent` at `0x140095bc1`
- `ntoskrnl!KeSetEvent` at `0x140095bc1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095c2d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009620b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140096672`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400967da`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095c2d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009620b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140096672`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400967da`
- `ntoskrnl!KeReleaseMutex` at `0x140095c46`
- `ntoskrnl!KeReleaseMutex` at `0x140096265`
- `ntoskrnl!KeReleaseMutex` at `0x1400966bd`
- `ntoskrnl!KeReleaseMutex` at `0x1400967f7`
- `ntoskrnl!KeReleaseMutex` at `0x140095c46`
- `ntoskrnl!KeReleaseMutex` at `0x140096265`
- `ntoskrnl!KeReleaseMutex` at `0x1400966bd`
- `ntoskrnl!KeReleaseMutex` at `0x1400967f7`
- `ntoskrnl!ExDeleteTimer` at `0x1400965d2`
- `ntoskrnl!ExDeleteTimer` at `0x1400965d2`
- `ntoskrnl!ExSetTimer` at `0x140095ed3`
- `ntoskrnl!ExSetTimer` at `0x14009603e`
- `ntoskrnl!ExSetTimer` at `0x140095ed3`
- `ntoskrnl!ExSetTimer` at `0x14009603e`
- `HAL!KeQueryPerformanceCounter` at `0x140095e1c`
- `HAL!KeQueryPerformanceCounter` at `0x140095fa3`
- `HAL!KeQueryPerformanceCounter` at `0x1400966cb`
- `HAL!KeQueryPerformanceCounter` at `0x140095e1c`
- `HAL!KeQueryPerformanceCounter` at `0x140095fa3`
- `HAL!KeQueryPerformanceCounter` at `0x1400966cb`
- `watchdog!WdLogSingleEntry0` at `0x140095d7e`
- `watchdog!WdLogSingleEntry0` at `0x140095d7e`
- `watchdog!WdLogSingleEntry1` at `0x1400962a6`
- `watchdog!WdLogSingleEntry1` at `0x1400962f9`
- `watchdog!WdLogSingleEntry1` at `0x1400963f6`
- `watchdog!WdLogSingleEntry1` at `0x1400964c5`
- `watchdog!WdLogSingleEntry1` at `0x1400962a6`
- `watchdog!WdLogSingleEntry1` at `0x1400962f9`
- `watchdog!WdLogSingleEntry1` at `0x1400963f6`
- `watchdog!WdLogSingleEntry1` at `0x1400964c5`

## string_xrefs

- `0x140096305`: `BLTQUEUE 0x%I64x : worker thread alerted`

## pseudocode

```c
void __fastcall __noreturn BLTQUEUE::BltQueueWorker(BLTQUEUE *this)
{
  struct DXGPUSHLOCK *v2; // r12
  bool v3; // r15
  struct DXGPUSHLOCK *v4; // r14
  struct _KMUTANT *v5; // rsi
  __int32 v6; // ebx
  struct _KEVENT *v7; // rax
  ULONG v8; // r13d
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  void *v14; // rax
  __int64 v15; // rcx
  ULONG v16; // r13d
  __int64 v17; // r12
  LONGLONG v18; // r15
  LARGE_INTEGER v19; // rbx
  __int64 v20; // r8
  __int64 v21; // r14
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // r11
  unsigned __int64 v26; // r10
  LONGLONG v27; // rdx
  __int64 v28; // r15
  LONGLONG v29; // r14
  LARGE_INTEGER v30; // rax
  LARGE_INTEGER v31; // rdx
  LARGE_INTEGER v32; // rcx
  LARGE_INTEGER v33; // r8
  __int64 v34; // r9
  char LowPart; // bl
  __int64 v36; // r11
  unsigned __int64 v37; // r10
  LONGLONG v38; // rdx
  NTSTATUS v39; // eax
  BLTQUEUE *v40; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  int v42; // ebx
  int v43; // r8d
  int v44; // r8d
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // ebx
  const wchar_t *v49; // r9
  PVOID v50; // r14
  unsigned __int64 j; // rsi
  __int64 v52; // rax
  unsigned __int64 v53; // rbx
  struct DXGADAPTER *v54; // r14
  __int64 v55; // rcx
  __int64 v56; // r8
  int v57; // eax
  __int64 v58; // rdx
  BLTQUEUE *v59; // rcx
  unsigned int v60; // eax
  __int64 v61; // rdx
  unsigned __int64 i; // rbx
  __int64 v63; // rax
  unsigned __int64 v64; // r10
  __int64 v65; // rdx
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  bool v70; // zf
  __int32 v71; // eax
  char v72; // bl
  char v73; // [rsp+50h] [rbp-B0h]
  DXGPUSHLOCK *v74[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v75; // [rsp+68h] [rbp-98h]
  DXGPUSHLOCK *v76[2]; // [rsp+70h] [rbp-90h] BYREF
  int v77; // [rsp+80h] [rbp-80h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+88h] [rbp-78h] BYREF
  union _LARGE_INTEGER v79; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v80[8]; // [rsp+98h] [rbp-68h] BYREF
  DXGPUSHLOCK *v81; // [rsp+A0h] [rbp-60h]
  int v82; // [rsp+A8h] [rbp-58h]
  struct _KEVENT v83; // [rsp+C8h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v85[144]; // [rsp+100h] [rbp+0h] BYREF
  PVOID Object[12]; // [rsp+190h] [rbp+90h] BYREF
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+1F0h] [rbp+F0h] BYREF

  memset(&Event, 0, sizeof(Event));
  memset(&v83, 0, sizeof(v83));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  KeInitializeEvent(&v83, SynchronizationEvent, 0);
  *((_QWORD *)this + 90) = KeGetCurrentThread();
  KeSetEvent((PRKEVENT)this + 22, 0, 0);
  v2 = (BLTQUEUE *)((char *)this + 2984);
  *(_OWORD *)v76 = 0;
  v3 = 0;
  while ( 1 )
  {
    v4 = (BLTQUEUE *)((char *)this + 424);
    v5 = (struct _KMUTANT *)((char *)this + 600);
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            memset(Object, 0, sizeof(Object));
            if ( (unsigned int)Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline() )
            {
              KeWaitForSingleObject(v5, Executive, 0, 0, 0);
              v6 = _InterlockedExchange((volatile __int32 *)this + 167, 0);
              KeReleaseMutex(v5, 0);
            }
            else
            {
              v6 = _InterlockedExchange((volatile __int32 *)this + 167, 0);
            }
            if ( v6 )
              BLTQUEUE::DisableHwVSyncWorker(this);
            v7 = &v83;
            Object[0] = (char *)this + 552;
            if ( ((__int64)v76[0] & 1) != 0 )
              v7 = (struct _KEVENT *)v76[1];
            Object[1] = v7;
            if ( ((LODWORD(v76[0]) >> 1) & 1) != 0 || ((__int64)v76[0] & 1) != 0 )
              BLTQUEUE::StartVSync(this, 0, (unsigned int)(((__int64)v76[0] & 2) == 0) + 1);
            v8 = 2;
            if ( (*((_DWORD *)this + 268) & 2) != 0 )
            {
              DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v76, v2, 0);
              DXGPUSHLOCK::AcquireShared(v76[1]);
              v9 = *((_QWORD *)this + 379);
              v10 = 0;
              v11 = 0;
              v77 = 1;
              do
              {
                v12 = v11 << 6;
                if ( *(_QWORD *)((v11 << 6) + v9 + 48) && !*(_BYTE *)(v12 + v9 + 56) && *(_BYTE *)(v12 + v9 + 57) == 1 )
                {
                  v13 = v8++;
                  Object[v13] = *(PVOID *)(v12 + v9);
                }
                ++v11;
              }
              while ( v11 < 8 );
              DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v76);
              if ( v8 <= 2 )
              {
                v73 = 1;
                v14 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 16LL))(*((_QWORD *)this + 16));
                v15 = v8;
                v16 = v8 + 1;
                Object[v15] = v14;
                Object[v16] = (PVOID)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 24LL))(*((_QWORD *)this + 16));
                v8 = v16 + 1;
              }
              else
              {
                v73 = 0;
              }
              if ( v8 > 0xC )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 2458;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"nObjects <= NumWaitBlocks", 2458, 0, 0, 0, 0);
              }
              if ( (unsigned int)Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline()
                && (unsigned int)Feature_DodVsyncEnsureLocked__private_IsEnabledDeviceUsageNoInline() )
              {
                DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v74, v4, 0);
                DXGPUSHLOCK::AcquireExclusive(v74[1]);
                v75 = 2;
                DXGPUSHLOCK::AcquireShared(v76[1]);
                v77 = 1;
                LOBYTE(v17) = 0;
                PerformanceFrequency.QuadPart = 0;
                v18 = 0;
                v19 = KeQueryPerformanceCounter(&PerformanceFrequency);
                DXGAUTOSPINLOCK::DXGAUTOSPINLOCK((DXGAUTOSPINLOCK *)v80, (BLTQUEUE *)((char *)this + 456), 1u);
                v20 = *((_QWORD *)this + 62);
                v21 = *((_QWORD *)this + 60);
                if ( v20 > 0 && v21 > 0 && v19.QuadPart > v21 )
                {
                  v17 = v20 + v19.QuadPart - (v19.QuadPart - v21) % v20;
                  v18 = 10000000 * ((v19.QuadPart - v21) % v20 - v20) / PerformanceFrequency.QuadPart;
                }
                DXGAUTOSPINLOCK::~DXGAUTOSPINLOCK((DXGAUTOSPINLOCK *)v80);
                do
                {
                  v25 = *((_QWORD *)this + 379);
                  v26 = v10 << 6;
                  if ( *(_QWORD *)((v10 << 6) + v25 + 48)
                    && !*(_BYTE *)(v26 + v25 + 56)
                    && *(_BYTE *)(v26 + v25 + 57) == 1 )
                  {
                    v27 = 0;
                    if ( v18 + *(_QWORD *)(v26 + v25 + 32) <= 0 )
                      v27 = v18 + *(_QWORD *)(v26 + v25 + 32);
                    ExSetTimer(*(_QWORD *)(v26 + v25), v27, 0, 0);
                  }
                  ++v10;
                }
                while ( v10 < 8 );
                if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                  McTemplateK0iiiiii_EtwWriteTransfer(
                    v23,
                    v22,
                    v24,
                    v18,
                    v17,
                    v19.QuadPart,
                    PerformanceFrequency.QuadPart,
                    v21,
                    *((_QWORD *)this + 62));
                (*(void (__fastcall **)(_QWORD, LONGLONG))(**((_QWORD **)this + 16) + 56LL))(
                  *((_QWORD *)this + 16),
                  v18);
                DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v76);
                DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v74);
                DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v74);
                v2 = (BLTQUEUE *)((char *)this + 2984);
              }
              else
              {
                DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v74, v4, 0);
                DXGPUSHLOCK::AcquireExclusive(v74[1]);
                v75 = 2;
                DXGPUSHLOCK::AcquireShared(v76[1]);
                v77 = 1;
                LOBYTE(v28) = 0;
                v79.QuadPart = 0;
                v29 = 0;
                v30 = KeQueryPerformanceCounter(&v79);
                v34 = *((_QWORD *)this + 62);
                LowPart = v30.LowPart;
                if ( v34 > 0 )
                {
                  v33 = *(LARGE_INTEGER *)((char *)this + 480);
                  if ( v33.QuadPart > 0 && v30.QuadPart > v33.QuadPart )
                  {
                    v32.QuadPart = v30.QuadPart - v33.QuadPart - (v30.QuadPart - v33.QuadPart) % v34;
                    v28 = v34 + v30.QuadPart - (v30.QuadPart - v33.QuadPart) % v34;
                    v31.QuadPart = 10000000 * ((v30.QuadPart - v33.QuadPart) % v34 - v34) % v79.QuadPart;
                    v29 = 10000000 * ((v30.QuadPart - v33.QuadPart) % v34 - v34) / v79.QuadPart;
                  }
                }
                do
                {
                  v36 = *((_QWORD *)this + 379);
                  v37 = v10 << 6;
                  if ( *(_QWORD *)((v10 << 6) + v36 + 48)
                    && !*(_BYTE *)(v37 + v36 + 56)
                    && *(_BYTE *)(v37 + v36 + 57) == 1 )
                  {
                    v38 = 0;
                    if ( v29 + *(_QWORD *)(v37 + v36 + 32) <= 0 )
                      v38 = v29 + *(_QWORD *)(v37 + v36 + 32);
                    ExSetTimer(*(_QWORD *)(v37 + v36), v38, 0, 0);
                  }
                  ++v10;
                }
                while ( v10 < 8 );
                if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                  McTemplateK0iiiiii_EtwWriteTransfer(
                    v32.LowPart,
                    v31.LowPart,
                    v33.LowPart,
                    v29,
                    v28,
                    LowPart,
                    v79.QuadPart,
                    *((_QWORD *)this + 60),
                    *((_QWORD *)this + 62));
                (*(void (__fastcall **)(_QWORD, LONGLONG))(**((_QWORD **)this + 16) + 56LL))(
                  *((_QWORD *)this + 16),
                  v29);
                DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v76);
                DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v74);
                DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v74);
              }
              DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v76);
              v3 = v73;
              v5 = (struct _KMUTANT *)((char *)this + 600);
              v4 = (BLTQUEUE *)((char *)this + 424);
            }
            v39 = KeWaitForMultipleObjects(v8, Object, WaitAny, Executive, 0, 1u, 0, &WaitBlockArray);
            *(_OWORD *)v76 = 0;
            *(_OWORD *)v74 = 0;
            BLTQUEUE::BltQueueWorkerDecodeEvent(v40, v3, v39, (struct BLTQUEUE::_BltQueueWaitEvent *)v74);
            IsEnabledDeviceUsageNoInline = Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline();
            v42 = (int)v74[0];
            if ( IsEnabledDeviceUsageNoInline )
            {
              KeWaitForSingleObject(v5, Executive, 0, 0, 0);
              if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                McTemplateK0xqttt_EtwWriteTransfer(
                  (*((_DWORD *)this + 169) >> 2) & 1,
                  (*((_DWORD *)this + 169) >> 3) & 1,
                  v44,
                  *((_QWORD *)this + 31),
                  v42,
                  (*((_DWORD *)this + 169) & 8) != 0,
                  (*((_DWORD *)this + 169) & 4) != 0,
                  *((_BYTE *)this + 661));
              KeReleaseMutex(v5, 0);
            }
            else if ( (unsigned int)Feature_AccessEnableVSyncEventAtomically__private_IsEnabledDeviceUsageNoInline() )
            {
              if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                McTemplateK0xqttt_EtwWriteTransfer(
                  0,
                  *((unsigned __int8 *)this + 661),
                  *((unsigned __int8 *)this + 658),
                  *((_QWORD *)this + 31),
                  v42,
                  _InterlockedCompareExchange((volatile signed __int32 *)this + 168, 0, 0),
                  *((_BYTE *)this + 658),
                  *((_BYTE *)this + 661));
            }
            else if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
            {
              McTemplateK0xqttt_EtwWriteTransfer(
                *((unsigned __int8 *)this + 658),
                *((unsigned __int8 *)this + 659),
                v43,
                *((_QWORD *)this + 31),
                v42,
                *((_BYTE *)this + 659),
                *((_BYTE *)this + 658),
                *((_BYTE *)this + 661));
            }
            if ( v42 )
              break;
            if ( (unsigned int)Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline() )
            {
              KeWaitForSingleObject(v5, Executive, 0, 0, 0);
              v68 = *((_OWORD *)this + 42);
              *((_OWORD *)this + 56) = *((_OWORD *)this + 41);
              v69 = *((_OWORD *)this + 43);
              *((_OWORD *)this + 57) = v68;
              *(_QWORD *)&v68 = *((_QWORD *)this + 88);
              *((_OWORD *)this + 58) = v69;
              *((_QWORD *)this + 118) = v68;
              KeReleaseMutex(v5, 0);
            }
            else
            {
              v66 = *((_OWORD *)this + 42);
              *((_OWORD *)this + 56) = *((_OWORD *)this + 41);
              v67 = *((_OWORD *)this + 43);
              *((_OWORD *)this + 57) = v66;
              *(_QWORD *)&v66 = *((_QWORD *)this + 88);
              *((_OWORD *)this + 58) = v67;
              *((_QWORD *)this + 118) = v66;
            }
            *((LARGE_INTEGER *)this + 111) = KeQueryPerformanceCounter(0);
            if ( (unsigned int)Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline() )
            {
              KeWaitForSingleObject(v5, Executive, 0, 0, 0);
              v74[0] = *(DXGPUSHLOCK **)((char *)this + 676);
              KeReleaseMutex(v5, 0);
              v72 = (char)v74[0];
              if ( ((__int64)v74[0] & 1) != 0 )
              {
                BLTQUEUE::AcquireOwnershipWorker(this);
              }
              else if ( ((__int64)v74[0] & 2) != 0 )
              {
                BLTQUEUE::ResetWorker(this);
              }
              else if ( ((__int64)v74[0] & 0x10) != 0 )
              {
                BLTQUEUE::CleanupWorker(this);
              }
              else if ( ((__int64)v74[0] & 4) != 0 )
              {
                BLTQUEUE::UpdateDisplayModeInfoWorker(this);
              }
              else if ( ((__int64)v74[0] & 8) != 0 )
              {
                BLTQUEUE::EnableVSyncEventWorker(this);
              }
              else if ( ((__int64)v74[0] & 0x100) != 0 )
              {
                BLTQUEUE::GlobalVmBusStatusChangeWorker(this);
              }
              else if ( ((__int64)v74[0] & 0x200) != 0 )
              {
                BLTQUEUE::HostMonitorPowerStateWorker(this);
              }
              if ( v72 >= 0 )
                goto LABEL_154;
LABEL_138:
              BLTQUEUE::RestartQueueWorker(this);
            }
            else
            {
              if ( (unsigned int)Feature_AccessEnableVSyncEventAtomically__private_IsEnabledDeviceUsageNoInline() )
              {
                v71 = _InterlockedExchange((volatile __int32 *)this + 168, 0);
                if ( *((_BYTE *)this + 656) )
                {
LABEL_136:
                  BLTQUEUE::AcquireOwnershipWorker(this);
                  goto LABEL_137;
                }
                if ( *((_BYTE *)this + 657) )
                {
LABEL_135:
                  BLTQUEUE::ResetWorker(this);
                  goto LABEL_137;
                }
                if ( *((_BYTE *)this + 660) )
                {
LABEL_134:
                  BLTQUEUE::CleanupWorker(this);
                  goto LABEL_137;
                }
                if ( *((_BYTE *)this + 658) )
                {
LABEL_133:
                  BLTQUEUE::UpdateDisplayModeInfoWorker(this);
                  goto LABEL_137;
                }
                v70 = v71 == 0;
              }
              else
              {
                if ( *((_BYTE *)this + 656) )
                  goto LABEL_136;
                if ( *((_BYTE *)this + 657) )
                  goto LABEL_135;
                if ( *((_BYTE *)this + 660) )
                  goto LABEL_134;
                if ( *((_BYTE *)this + 658) )
                  goto LABEL_133;
                v70 = *((_BYTE *)this + 659) == 0;
              }
              if ( v70 )
              {
                if ( *((_BYTE *)this + 664) )
                {
                  BLTQUEUE::GlobalVmBusStatusChangeWorker(this);
                }
                else if ( *((_BYTE *)this + 665) )
                {
                  BLTQUEUE::HostMonitorPowerStateWorker(this);
                }
              }
              else
              {
                BLTQUEUE::EnableVSyncEventWorker(this);
              }
LABEL_137:
              if ( *((_BYTE *)this + 663) )
                goto LABEL_138;
LABEL_154:
              v65 = 0;
LABEL_111:
              BLTQUEUE::ProcessBltQueue(this, v65, v76);
            }
          }
          v45 = v42 - 1;
          if ( !v45 )
          {
            v65 = 2;
            goto LABEL_111;
          }
          v46 = v45 - 1;
          if ( v46 )
            break;
          if ( g_TdrForceDodVSyncTimeout && TdrIsDodVSyncTimeoutForcedFlip() )
          {
            BLTQUEUE::ProcessVSyncTdrWorker(this, 1u);
          }
          else
          {
            BLTQUEUE::ProcessBltQueue(this, 1, v76);
            if ( !*((_DWORD *)this + 103) && ((__int64)v76[0] & 3) == 0 )
            {
              v60 = *((_DWORD *)this + 104) + 1;
              *((_DWORD *)this + 104) = v60;
              if ( v60 > 0xA )
                BLTQUEUE::StopVSync(this, 0, 8);
            }
          }
          DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v80, v2, 0);
          DXGPUSHLOCK::AcquireShared(v81);
          v82 = 1;
          for ( i = 0; i < 8; ++i )
          {
            v63 = *((_QWORD *)this + 379);
            v64 = i << 6;
            if ( *(_QWORD *)((i << 6) + v63 + 48) )
            {
              if ( *(_BYTE *)(v64 + v63 + 56) == 1 )
              {
                *(_QWORD *)(v64 + v63 + 48) = 0;
                LOBYTE(v61) = 1;
                *(_BYTE *)(v64 + *((_QWORD *)this + 379) + 56) = 0;
                ExDeleteTimer(*(_QWORD *)(v64 + *((_QWORD *)this + 379)), v61, 0, 0);
              }
              else
              {
                *(_BYTE *)(v64 + v63 + 57) = 1;
              }
            }
          }
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v80);
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v80);
        }
        v47 = v46 - 1;
        if ( v47 )
          break;
        v57 = *((_DWORD *)this + 34);
        if ( v57 == 1 )
        {
          BLTQUEUE::ProcessVSyncTdrWorker(this, 0);
        }
        else if ( v57 == 3 )
        {
          BLTQUEUE::StopVSync(this, 0, 3);
          LOBYTE(v58) = 1;
          BLTQUEUE::RecreateVsyncSource(this, v58, 3);
          BLTQUEUE::StartVSync(this, 0, 3);
          BLTQUEUE::LogRemoteVsyncTimeout(v59);
        }
        else
        {
          WdLogSingleEntry1(1, *((int *)this + 34));
          WdLogGlobalForLineNumber = 2897;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"Not expecting Vsync TDR for type 0x%I64x",
            *((int *)this + 34),
            0,
            0,
            0,
            0);
        }
      }
      v48 = v47 - 1;
      if ( !v48 )
        break;
      WdLogSingleEntry1(2, this);
      if ( v48 == 1 )
      {
        v49 = L"BLTQUEUE 0x%I64x : worker thread alerted";
        WdLogGlobalForLineNumber = 2910;
      }
      else
      {
        v49 = L"BLTQUEUE 0x%I64x : Received invalid WaitStatus";
        WdLogGlobalForLineNumber = 2964;
      }
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v49, (__int64)this, 0, 0, 0, 0);
    }
    v50 = Object[(__int64)v74[1]];
    DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v80, v2, 0);
    DXGPUSHLOCK::AcquireShared(v81);
    v82 = 1;
    for ( j = 0; ; ++j )
    {
      if ( j >= 8 )
        goto LABEL_90;
      v52 = *((_QWORD *)this + 379);
      v53 = j << 6;
      if ( *(PVOID *)((j << 6) + v52) == v50 && *(_BYTE *)(v53 + v52 + 57) == 1 )
        break;
    }
    v54 = *(struct DXGADAPTER **)(v53 + v52 + 16);
    COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v85, v54, 0);
    if ( (int)COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v85, 0) >= 0 )
    {
      v55 = *((_QWORD *)v54 + 407);
      v56 = *((_QWORD *)this + 379);
      v74[0] = (DXGPUSHLOCK *)(unsigned int)(*((_DWORD *)this + 744) + 1);
      if ( (int)VIDSCH_EXPORT::VidSchSignalSyncObjectsFromCpu(
                  *(VIDSCH_EXPORT **)(v55 + 736),
                  1u,
                  (struct _VIDSCH_SYNC_OBJECT **)(v53 + v56 + 8),
                  0,
                  (const unsigned __int64 *)v74) < 0 )
      {
        WdLogSingleEntry1(2, j);
        WdLogGlobalForLineNumber = 2950;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to signal pending dod periodic frame notification id: %lu",
          j,
          0,
          0,
          0,
          0);
      }
      else
      {
        *(DXGPUSHLOCK **)(v53 + *((_QWORD *)this + 379) + 40) = v74[0];
      }
    }
    *(_BYTE *)(v53 + *((_QWORD *)this + 379) + 57) = 0;
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v85);
LABEL_90:
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v80);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v80);
  }
}

```

## disassembly

```asm
0x140095b30  push    rbp
0x140095b32  push    rbx
0x140095b33  push    rsi
0x140095b34  push    rdi
0x140095b35  push    r12
0x140095b37  push    r13
0x140095b39  push    r14
0x140095b3b  push    r15
0x140095b3d  lea     rbp, [rsp-348h]
0x140095b45  sub     rsp, 448h
0x140095b4c  mov     rax, cs:__security_cookie
0x140095b53  xor     rax, rsp
0x140095b56  mov     [rbp+380h+var_50], rax
0x140095b5d  xor     eax, eax
0x140095b5f  mov     rdi, rcx
0x140095b62  xorps   xmm0, xmm0
0x140095b65  mov     [rbp+380h+Event.Header.WaitListHead.Blink], rax
0x140095b69  xorps   xmm1, xmm1
0x140095b6c  mov     [rbp+380h+var_3B8.Header.WaitListHead.Blink], rax
0x140095b70  xor     r8d, r8d; State
0x140095b73  lea     rcx, [rbp+380h+Event]; Event
0x140095b77  lea     edx, [rax+1]; Type
0x140095b7a  movups  xmmword ptr [rbp+380h+Event.Header], xmm0
0x140095b7e  movups  xmmword ptr [rbp+380h+var_3B8.Header], xmm1
0x140095b82  call    cs:__imp_KeInitializeEvent
0x140095b89  nop     dword ptr [rax+rax+00h]
0x140095b8e  xor     r8d, r8d; State
0x140095b91  lea     rcx, [rbp+380h+var_3B8]; Event
0x140095b95  lea     edx, [r8+1]; Type
0x140095b99  call    cs:__imp_KeInitializeEvent
0x140095ba0  nop     dword ptr [rax+rax+00h]
0x140095ba5  mov     rax, gs:188h
0x140095bae  lea     rcx, [rdi+210h]; Event
0x140095bb5  xor     r8d, r8d; Wait
0x140095bb8  mov     [rdi+2D0h], rax
0x140095bbf  xor     edx, edx; Increment
0x140095bc1  call    cs:__imp_KeSetEvent
0x140095bc8  nop     dword ptr [rax+rax+00h]
0x140095bcd  xorps   xmm0, xmm0
0x140095bd0  lea     r12, [rdi+0BA8h]
0x140095bd7  movups  xmmword ptr [rsp+480h+var_410], xmm0
0x140095bdc  xor     r15b, r15b
0x140095bdf  lea     r14, [rdi+1A8h]
0x140095be6  lea     rsi, [rdi+258h]
0x140095bed  xor     edx, edx; Val
0x140095bef  lea     rcx, [rbp+380h+Object]; void *
0x140095bf6  lea     r13, [rdi+228h]
0x140095bfd  lea     r8d, [rdx+60h]; Size
0x140095c01  call    memset
0x140095c06  call    Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline
0x140095c0b  test    eax, eax
0x140095c0d  jnz     short loc_140095C19
0x140095c0f  xor     ebx, ebx
0x140095c11  xchg    ebx, [rdi+29Ch]
0x140095c17  jmp     short loc_140095C52
0x140095c19  xor     r9d, r9d; Alertable
0x140095c1c  mov     [rsp+480h+Timeout], 0; Timeout
0x140095c25  xor     r8d, r8d; WaitMode
0x140095c28  xor     edx, edx; WaitReason
0x140095c2a  mov     rcx, rsi; Object
0x140095c2d  call    cs:__imp_KeWaitForSingleObject
0x140095c34  nop     dword ptr [rax+rax+00h]
0x140095c39  xor     ebx, ebx
0x140095c3b  xor     edx, edx; Wait
0x140095c3d  xchg    ebx, [rdi+29Ch]
0x140095c43  mov     rcx, rsi; Mutex
0x140095c46  call    cs:__imp_KeReleaseMutex
0x140095c4d  nop     dword ptr [rax+rax+00h]
0x140095c52  test    ebx, ebx
0x140095c54  jz      short loc_140095C5E
0x140095c56  mov     rcx, rdi; this
0x140095c59  call    ?DisableHwVSyncWorker@BLTQUEUE@@AEAAXXZ; BLTQUEUE::DisableHwVSyncWorker(void)
0x140095c5e  mov     r8d, dword ptr [rsp+480h+var_410]
0x140095c63  lea     rax, [rbp+380h+var_3B8]
0x140095c67  mov     ecx, r8d
0x140095c6a  mov     [rbp+380h+Object], r13
0x140095c71  and     ecx, 1
0x140095c74  cmovnz  rax, [rsp+480h+var_410+8]
0x140095c7a  shr     r8d, 1
0x140095c7d  mov     [rbp+380h+var_2E8], rax
0x140095c84  and     r8d, 1
0x140095c88  jnz     short loc_140095C8E
0x140095c8a  test    ecx, ecx
0x140095c8c  jz      short loc_140095C9F
0x140095c8e  xor     r8d, 1
0x140095c92  xor     edx, edx
0x140095c94  inc     r8d
0x140095c97  mov     rcx, rdi
0x140095c9a  call    ?StartVSync@BLTQUEUE@@AEAAX_NW4VsyncEvent@1@@Z; BLTQUEUE::StartVSync(bool,BLTQUEUE::VsyncEvent)
0x140095c9f  mov     eax, [rdi+430h]
0x140095ca5  mov     ebx, 2
0x140095caa  mov     r13d, ebx
0x140095cad  test    bl, al
0x140095caf  jz      loc_1400960E9
0x140095cb5  xor     r8d, r8d; bool
0x140095cb8  lea     rcx, [rsp+480h+var_410]; this
0x140095cbd  mov     rdx, r12; struct DXGPUSHLOCK *
0x140095cc0  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x140095cc5  mov     rcx, [rsp+480h+var_410+8]; this
0x140095cca  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140095ccf  mov     rdx, [rdi+0BD8h]
0x140095cd6  xor     esi, esi
0x140095cd8  mov     r8d, esi
0x140095cdb  mov     [rbp+380h+var_400], 1
0x140095ce2  mov     rax, r8
0x140095ce5  shl     rax, 6
0x140095ce9  cmp     [rax+rdx+30h], rsi
0x140095cee  jz      short loc_140095D10
0x140095cf0  cmp     [rax+rdx+38h], sil
0x140095cf5  jnz     short loc_140095D10
0x140095cf7  cmp     byte ptr [rax+rdx+39h], 1
0x140095cfc  jnz     short loc_140095D10
0x140095cfe  mov     rax, [rax+rdx]
0x140095d02  mov     ecx, r13d
0x140095d05  inc     r13d
0x140095d08  mov     [rbp+rcx*8+380h+Object], rax
0x140095d10  inc     r8
0x140095d13  cmp     r8, 8
0x140095d17  jb      short loc_140095CE2
0x140095d19  lea     rcx, [rsp+480h+var_410]; this
0x140095d1e  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095d23  cmp     r13d, ebx
0x140095d26  jbe     short loc_140095D2F
0x140095d28  mov     [rsp+480h+var_430], sil
0x140095d2d  jmp     short loc_140095D73
0x140095d2f  mov     rcx, [rdi+80h]
0x140095d36  mov     [rsp+480h+var_430], 1
0x140095d3b  mov     rax, [rcx]
0x140095d3e  mov     rax, [rax+10h]
0x140095d42  call    _guard_dispatch_icall
0x140095d47  mov     ecx, r13d
0x140095d4a  inc     r13d
0x140095d4d  mov     [rbp+rcx*8+380h+Object], rax
0x140095d55  mov     rcx, [rdi+80h]
0x140095d5c  mov     rax, [rcx]
0x140095d5f  mov     rax, [rax+18h]
0x140095d63  call    _guard_dispatch_icall
0x140095d68  mov     [rbp+r13*8+380h+Object], rax
0x140095d70  inc     r13d
0x140095d73  cmp     r13d, 0Ch
0x140095d77  jbe     short loc_140095DC5
0x140095d79  mov     ecx, 1
0x140095d7e  call    cs:__imp_WdLogSingleEntry0
0x140095d85  nop     dword ptr [rax+rax+00h]
0x140095d8a  mov     [rsp+480h+var_440], rsi
0x140095d8f  lea     r9, aNobjectsNumwai; "nObjects <= NumWaitBlocks"
0x140095d96  mov     [rsp+480h+WaitBlockArray], rsi
0x140095d9b  mov     eax, 99Ah
0x140095da0  mov     [rsp+480h+var_450], rsi
0x140095da5  or      r8d, 0FFFFFFFFh
0x140095da9  mov     qword ptr [rsp+480h+Alertable], rsi
0x140095dae  mov     edx, 40002h
0x140095db3  xor     ecx, ecx
0x140095db5  mov     [rsp+480h+Timeout], rax
0x140095dba  mov     cs:WdLogGlobalForLineNumber, eax
0x140095dc0  call    DxgkLogInternalTriageEvent
0x140095dc5  call    Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline
0x140095dca  test    eax, eax
0x140095dcc  jz      loc_140095F66
0x140095dd2  call    Feature_DodVsyncEnsureLocked__private_IsEnabledDeviceUsageNoInline
0x140095dd7  test    eax, eax
0x140095dd9  jz      loc_140095F66
0x140095ddf  xor     r8d, r8d; bool
0x140095de2  lea     rcx, [rsp+480h+var_428]; this
0x140095de7  mov     rdx, r14; struct DXGPUSHLOCK *
0x140095dea  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x140095def  mov     rcx, [rsp+480h+var_428+8]; this
0x140095df4  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140095df9  mov     rcx, [rsp+480h+var_410+8]; this
0x140095dfe  mov     [rsp+480h+var_418], ebx
0x140095e02  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140095e07  lea     rcx, [rbp+380h+PerformanceFrequency]; PerformanceFrequency
0x140095e0b  mov     [rbp+380h+var_400], 1
0x140095e12  mov     r12, rsi
0x140095e15  mov     qword ptr [rbp+380h+PerformanceFrequency], rsi
0x140095e19  mov     r15, rsi
0x140095e1c  call    cs:__imp_KeQueryPerformanceCounter
0x140095e23  nop     dword ptr [rax+rax+00h]
0x140095e28  mov     r8b, 1; unsigned __int8
0x140095e2b  lea     rdx, [rdi+1C8h]; struct DXGSPINLOCK *
0x140095e32  lea     rcx, [rbp+380h+var_3E8]; this
0x140095e36  mov     rbx, rax
0x140095e39  call    ??0DXGAUTOSPINLOCK@@QEAA@QEAVDXGSPINLOCK@@E@Z; DXGAUTOSPINLOCK::DXGAUTOSPINLOCK(DXGSPINLOCK * const,uchar)
0x140095e3e  mov     r8, [rdi+1F0h]
0x140095e45  mov     r14, [rdi+1E0h]
0x140095e4c  test    r8, r8
0x140095e4f  jle     short loc_140095E89
0x140095e51  test    r14, r14
0x140095e54  jle     short loc_140095E89
0x140095e56  cmp     rbx, r14
0x140095e59  jle     short loc_140095E89
0x140095e5b  mov     rcx, rbx
0x140095e5e  sub     rcx, r14
0x140095e61  mov     rax, rcx
0x140095e64  cqo
0x140095e66  idiv    r8
0x140095e69  mov     rax, rbx
0x140095e6c  sub     rcx, rdx
0x140095e6f  lea     r12, [r8+rcx]
0x140095e73  add     r12, r14
0x140095e76  sub     rax, r12
0x140095e79  imul    rax, 989680h
0x140095e80  cqo
0x140095e82  idiv    qword ptr [rbp+380h+PerformanceFrequency]
0x140095e86  mov     r15, rax
0x140095e89  lea     rcx, [rbp+380h+var_3E8]; this
0x140095e8d  call    ??1DXGAUTOSPINLOCK@@QEAA@XZ; DXGAUTOSPINLOCK::~DXGAUTOSPINLOCK(void)
0x140095e92  mov     r11, [rdi+0BD8h]
0x140095e99  mov     r10, rsi
0x140095e9c  shl     r10, 6
0x140095ea0  cmp     qword ptr [r10+r11+30h], 0
0x140095ea6  jz      short loc_140095EDF
0x140095ea8  cmp     byte ptr [r10+r11+38h], 0
0x140095eae  jnz     short loc_140095EDF
0x140095eb0  cmp     byte ptr [r10+r11+39h], 1
0x140095eb6  jnz     short loc_140095EDF
0x140095eb8  mov     rcx, [r10+r11+20h]
0x140095ebd  xor     edx, edx
0x140095ebf  add     rcx, r15
0x140095ec2  test    rcx, rcx
0x140095ec5  cmovle  rdx, rcx
0x140095ec9  mov     rcx, [r10+r11]
0x140095ecd  xor     r9d, r9d
0x140095ed0  xor     r8d, r8d
0x140095ed3  call    cs:__imp_ExSetTimer
0x140095eda  nop     dword ptr [rax+rax+00h]
0x140095edf  inc     rsi
0x140095ee2  cmp     rsi, 8
0x140095ee6  jb      short loc_140095E92
0x140095ee8  cmp     cs:bTracingEnabled, 0
0x140095eef  jz      short loc_140095F26
0x140095ef1  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140095ef8  jz      short loc_140095F26
0x140095efa  mov     rax, [rdi+1F0h]
0x140095f01  mov     r9, r15
0x140095f04  mov     [rsp+480h+var_440], rax
0x140095f09  mov     rax, qword ptr [rbp+380h+PerformanceFrequency]
0x140095f0d  mov     [rsp+480h+WaitBlockArray], r14
0x140095f12  mov     [rsp+480h+var_450], rax
0x140095f17  mov     qword ptr [rsp+480h+Alertable], rbx
0x140095f1c  mov     [rsp+480h+Timeout], r12
0x140095f21  call    McTemplateK0iiiiii_EtwWriteTransfer
0x140095f26  mov     rcx, [rdi+80h]
0x140095f2d  mov     rdx, r15
0x140095f30  mov     rax, [rcx]
0x140095f33  mov     rax, [rax+38h]
0x140095f37  call    _guard_dispatch_icall
0x140095f3c  lea     rcx, [rsp+480h+var_410]; this
0x140095f41  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095f46  lea     rcx, [rsp+480h+var_428]; this
0x140095f4b  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095f50  lea     rcx, [rsp+480h+var_428]; this
0x140095f55  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095f5a  lea     r12, [rdi+0BA8h]
0x140095f61  jmp     loc_1400960CC
0x140095f66  xor     r8d, r8d; bool
0x140095f69  lea     rcx, [rsp+480h+var_428]; this
0x140095f6e  mov     rdx, r14; struct DXGPUSHLOCK *
0x140095f71  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x140095f76  mov     rcx, [rsp+480h+var_428+8]; this
0x140095f7b  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140095f80  mov     rcx, [rsp+480h+var_410+8]; this
0x140095f85  mov     [rsp+480h+var_418], ebx
0x140095f89  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140095f8e  lea     rcx, [rbp+380h+var_3F0]; PerformanceFrequency
0x140095f92  mov     [rbp+380h+var_400], 1
0x140095f99  mov     r15, rsi
0x140095f9c  mov     qword ptr [rbp+380h+var_3F0], rsi
0x140095fa0  mov     r14, rsi
0x140095fa3  call    cs:__imp_KeQueryPerformanceCounter
0x140095faa  nop     dword ptr [rax+rax+00h]
0x140095faf  mov     r9, [rdi+1F0h]
0x140095fb6  mov     rbx, rax
0x140095fb9  test    r9, r9
0x140095fbc  jle     short loc_140095FFD
0x140095fbe  mov     r8, [rdi+1E0h]
0x140095fc5  test    r8, r8
0x140095fc8  jle     short loc_140095FFD
0x140095fca  cmp     rax, r8
0x140095fcd  jle     short loc_140095FFD
0x140095fcf  mov     rcx, rax
0x140095fd2  sub     rcx, r8
0x140095fd5  mov     rax, rcx
0x140095fd8  cqo
0x140095fda  idiv    r9
0x140095fdd  mov     rax, rbx
0x140095fe0  sub     rcx, rdx
0x140095fe3  lea     r15, [r9+rcx]
0x140095fe7  add     r15, r8
0x140095fea  sub     rax, r15
0x140095fed  imul    rax, 989680h
0x140095ff4  cqo
0x140095ff6  idiv    qword ptr [rbp+380h+var_3F0]
0x140095ffa  mov     r14, rax
0x140095ffd  mov     r11, [rdi+0BD8h]
0x140096004  mov     r10, rsi
0x140096007  shl     r10, 6
0x14009600b  cmp     qword ptr [r10+r11+30h], 0
0x140096011  jz      short loc_14009604A
0x140096013  cmp     byte ptr [r10+r11+38h], 0
  ... truncated ...
```
