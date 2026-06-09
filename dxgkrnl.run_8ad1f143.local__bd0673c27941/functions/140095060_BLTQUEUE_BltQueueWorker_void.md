# BLTQUEUE::BltQueueWorker(void)

- ea: `0x140095060`
- end: `0x140095db0`
- name: `?BltQueueWorker@BLTQUEUE@@QEAAXXZ`
- size: `3408`
- prototype: `void __fastcall __noreturn(BLTQUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1403e87a0`

## callees

- `0x140015780`
- `0x1400181a4`
- `0x140019838`
- `0x14001a150`
- `0x14001a2ec`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001d070`
- `0x14001f460`
- `0x14002ec90`
- `0x14003714c`
- `0x1400446c0`
- `0x140044d54`
- `0x1400478d4`
- `0x1400586a8`
- `0x140095060`
- `0x140095f30`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140186118`
- `0x1401993e0`
- `0x1401e3c5c`
- `0x1401e3cf4`
- `0x1401e3d8c`
- `0x14030109c`
- `0x14030140c`
- `0x140301a58`
- `0x140301cc0`
- `0x1403027c0`
- `0x140302a48`
- `0x14037e7ec`
- `0x1403935b4`
- `0x1403cae94`
- `0x1403caf30`
- `0x1403d8ee8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400950b2`
- `ntoskrnl!KeInitializeEvent` at `0x1400950c9`
- `ntoskrnl!KeInitializeEvent` at `0x1400950b2`
- `ntoskrnl!KeInitializeEvent` at `0x1400950c9`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140095649`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140095649`
- `ntoskrnl!KeSetEvent` at `0x1400950f1`
- `ntoskrnl!KeSetEvent` at `0x1400950f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009515d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009573b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095ba2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095d0a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009515d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009573b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095ba2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095d0a`
- `ntoskrnl!KeReleaseMutex` at `0x140095176`
- `ntoskrnl!KeReleaseMutex` at `0x140095795`
- `ntoskrnl!KeReleaseMutex` at `0x140095bed`
- `ntoskrnl!KeReleaseMutex` at `0x140095d27`
- `ntoskrnl!KeReleaseMutex` at `0x140095176`
- `ntoskrnl!KeReleaseMutex` at `0x140095795`
- `ntoskrnl!KeReleaseMutex` at `0x140095bed`
- `ntoskrnl!KeReleaseMutex` at `0x140095d27`
- `ntoskrnl!ExDeleteTimer` at `0x140095b02`
- `ntoskrnl!ExDeleteTimer` at `0x140095b02`
- `ntoskrnl!ExSetTimer` at `0x140095403`
- `ntoskrnl!ExSetTimer` at `0x14009556e`
- `ntoskrnl!ExSetTimer` at `0x140095403`
- `ntoskrnl!ExSetTimer` at `0x14009556e`
- `HAL!KeQueryPerformanceCounter` at `0x14009534c`
- `HAL!KeQueryPerformanceCounter` at `0x1400954d3`
- `HAL!KeQueryPerformanceCounter` at `0x140095bfb`
- `HAL!KeQueryPerformanceCounter` at `0x14009534c`
- `HAL!KeQueryPerformanceCounter` at `0x1400954d3`
- `HAL!KeQueryPerformanceCounter` at `0x140095bfb`
- `watchdog!WdLogSingleEntry0` at `0x1400952ae`
- `watchdog!WdLogSingleEntry0` at `0x1400952ae`
- `watchdog!WdLogSingleEntry1` at `0x1400957d6`
- `watchdog!WdLogSingleEntry1` at `0x140095829`
- `watchdog!WdLogSingleEntry1` at `0x140095926`
- `watchdog!WdLogSingleEntry1` at `0x1400959f5`
- `watchdog!WdLogSingleEntry1` at `0x1400957d6`
- `watchdog!WdLogSingleEntry1` at `0x140095829`
- `watchdog!WdLogSingleEntry1` at `0x140095926`
- `watchdog!WdLogSingleEntry1` at `0x1400959f5`

## string_xrefs

- `0x140095835`: `BLTQUEUE 0x%I64x : worker thread alerted`

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
          WdLogSingleEntry1(1);
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
      WdLogSingleEntry1(2);
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
      v55 = *((_QWORD *)v54 + 405);
      v56 = *((_QWORD *)this + 379);
      v74[0] = (DXGPUSHLOCK *)(unsigned int)(*((_DWORD *)this + 744) + 1);
      if ( (int)VIDSCH_EXPORT::VidSchSignalSyncObjectsFromCpu(
                  *(VIDSCH_EXPORT **)(v55 + 736),
                  1u,
                  (struct _VIDSCH_SYNC_OBJECT **)(v53 + v56 + 8),
                  0,
                  (const unsigned __int64 *)v74) < 0 )
      {
        WdLogSingleEntry1(2);
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
0x140095060  push    rbp
0x140095062  push    rbx
0x140095063  push    rsi
0x140095064  push    rdi
0x140095065  push    r12
0x140095067  push    r13
0x140095069  push    r14
0x14009506b  push    r15
0x14009506d  lea     rbp, [rsp-348h]
0x140095075  sub     rsp, 448h
0x14009507c  mov     rax, cs:__security_cookie
0x140095083  xor     rax, rsp
0x140095086  mov     [rbp+380h+var_50], rax
0x14009508d  xor     eax, eax
0x14009508f  mov     rdi, rcx
0x140095092  xorps   xmm0, xmm0
0x140095095  mov     [rbp+380h+Event.Header.WaitListHead.Blink], rax
0x140095099  xorps   xmm1, xmm1
0x14009509c  mov     [rbp+380h+var_3B8.Header.WaitListHead.Blink], rax
0x1400950a0  xor     r8d, r8d; State
0x1400950a3  lea     rcx, [rbp+380h+Event]; Event
0x1400950a7  lea     edx, [rax+1]; Type
0x1400950aa  movups  xmmword ptr [rbp+380h+Event.Header], xmm0
0x1400950ae  movups  xmmword ptr [rbp+380h+var_3B8.Header], xmm1
0x1400950b2  call    cs:__imp_KeInitializeEvent
0x1400950b9  nop     dword ptr [rax+rax+00h]
0x1400950be  xor     r8d, r8d; State
0x1400950c1  lea     rcx, [rbp+380h+var_3B8]; Event
0x1400950c5  lea     edx, [r8+1]; Type
0x1400950c9  call    cs:__imp_KeInitializeEvent
0x1400950d0  nop     dword ptr [rax+rax+00h]
0x1400950d5  mov     rax, gs:188h
0x1400950de  lea     rcx, [rdi+210h]; Event
0x1400950e5  xor     r8d, r8d; Wait
0x1400950e8  mov     [rdi+2D0h], rax
0x1400950ef  xor     edx, edx; Increment
0x1400950f1  call    cs:__imp_KeSetEvent
0x1400950f8  nop     dword ptr [rax+rax+00h]
0x1400950fd  xorps   xmm0, xmm0
0x140095100  lea     r12, [rdi+0BA8h]
0x140095107  movups  xmmword ptr [rsp+480h+var_410], xmm0
0x14009510c  xor     r15b, r15b
0x14009510f  lea     r14, [rdi+1A8h]
0x140095116  lea     rsi, [rdi+258h]
0x14009511d  xor     edx, edx; Val
0x14009511f  lea     rcx, [rbp+380h+Object]; void *
0x140095126  lea     r13, [rdi+228h]
0x14009512d  lea     r8d, [rdx+60h]; Size
0x140095131  call    memset
0x140095136  call    Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline
0x14009513b  test    eax, eax
0x14009513d  jnz     short loc_140095149
0x14009513f  xor     ebx, ebx
0x140095141  xchg    ebx, [rdi+29Ch]
0x140095147  jmp     short loc_140095182
0x140095149  xor     r9d, r9d; Alertable
0x14009514c  mov     [rsp+480h+Timeout], 0; Timeout
0x140095155  xor     r8d, r8d; WaitMode
0x140095158  xor     edx, edx; WaitReason
0x14009515a  mov     rcx, rsi; Object
0x14009515d  call    cs:__imp_KeWaitForSingleObject
0x140095164  nop     dword ptr [rax+rax+00h]
0x140095169  xor     ebx, ebx
0x14009516b  xor     edx, edx; Wait
0x14009516d  xchg    ebx, [rdi+29Ch]
0x140095173  mov     rcx, rsi; Mutex
0x140095176  call    cs:__imp_KeReleaseMutex
0x14009517d  nop     dword ptr [rax+rax+00h]
0x140095182  test    ebx, ebx
0x140095184  jz      short loc_14009518E
0x140095186  mov     rcx, rdi; this
0x140095189  call    ?DisableHwVSyncWorker@BLTQUEUE@@AEAAXXZ; BLTQUEUE::DisableHwVSyncWorker(void)
0x14009518e  mov     r8d, dword ptr [rsp+480h+var_410]
0x140095193  lea     rax, [rbp+380h+var_3B8]
0x140095197  mov     ecx, r8d
0x14009519a  mov     [rbp+380h+Object], r13
0x1400951a1  and     ecx, 1
0x1400951a4  cmovnz  rax, [rsp+480h+var_410+8]
0x1400951aa  shr     r8d, 1
0x1400951ad  mov     [rbp+380h+var_2E8], rax
0x1400951b4  and     r8d, 1
0x1400951b8  jnz     short loc_1400951BE
0x1400951ba  test    ecx, ecx
0x1400951bc  jz      short loc_1400951CF
0x1400951be  xor     r8d, 1
0x1400951c2  xor     edx, edx
0x1400951c4  inc     r8d
0x1400951c7  mov     rcx, rdi
0x1400951ca  call    ?StartVSync@BLTQUEUE@@AEAAX_NW4VsyncEvent@1@@Z; BLTQUEUE::StartVSync(bool,BLTQUEUE::VsyncEvent)
0x1400951cf  mov     eax, [rdi+430h]
0x1400951d5  mov     ebx, 2
0x1400951da  mov     r13d, ebx
0x1400951dd  test    bl, al
0x1400951df  jz      loc_140095619
0x1400951e5  xor     r8d, r8d; bool
0x1400951e8  lea     rcx, [rsp+480h+var_410]; this
0x1400951ed  mov     rdx, r12; struct DXGPUSHLOCK *
0x1400951f0  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x1400951f5  mov     rcx, [rsp+480h+var_410+8]; this
0x1400951fa  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x1400951ff  mov     rdx, [rdi+0BD8h]
0x140095206  xor     esi, esi
0x140095208  mov     r8d, esi
0x14009520b  mov     [rbp+380h+var_400], 1
0x140095212  mov     rax, r8
0x140095215  shl     rax, 6
0x140095219  cmp     [rax+rdx+30h], rsi
0x14009521e  jz      short loc_140095240
0x140095220  cmp     [rax+rdx+38h], sil
0x140095225  jnz     short loc_140095240
0x140095227  cmp     byte ptr [rax+rdx+39h], 1
0x14009522c  jnz     short loc_140095240
0x14009522e  mov     rax, [rax+rdx]
0x140095232  mov     ecx, r13d
0x140095235  inc     r13d
0x140095238  mov     [rbp+rcx*8+380h+Object], rax
0x140095240  inc     r8
0x140095243  cmp     r8, 8
0x140095247  jb      short loc_140095212
0x140095249  lea     rcx, [rsp+480h+var_410]; this
0x14009524e  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095253  cmp     r13d, ebx
0x140095256  jbe     short loc_14009525F
0x140095258  mov     [rsp+480h+var_430], sil
0x14009525d  jmp     short loc_1400952A3
0x14009525f  mov     rcx, [rdi+80h]
0x140095266  mov     [rsp+480h+var_430], 1
0x14009526b  mov     rax, [rcx]
0x14009526e  mov     rax, [rax+10h]
0x140095272  call    _guard_dispatch_icall
0x140095277  mov     ecx, r13d
0x14009527a  inc     r13d
0x14009527d  mov     [rbp+rcx*8+380h+Object], rax
0x140095285  mov     rcx, [rdi+80h]
0x14009528c  mov     rax, [rcx]
0x14009528f  mov     rax, [rax+18h]
0x140095293  call    _guard_dispatch_icall
0x140095298  mov     [rbp+r13*8+380h+Object], rax
0x1400952a0  inc     r13d
0x1400952a3  cmp     r13d, 0Ch
0x1400952a7  jbe     short loc_1400952F5
0x1400952a9  mov     ecx, 1
0x1400952ae  call    cs:__imp_WdLogSingleEntry0
0x1400952b5  nop     dword ptr [rax+rax+00h]
0x1400952ba  mov     [rsp+480h+var_440], rsi
0x1400952bf  lea     r9, aNobjectsNumwai; "nObjects <= NumWaitBlocks"
0x1400952c6  mov     [rsp+480h+WaitBlockArray], rsi
0x1400952cb  mov     eax, 99Ah
0x1400952d0  mov     [rsp+480h+var_450], rsi
0x1400952d5  or      r8d, 0FFFFFFFFh
0x1400952d9  mov     qword ptr [rsp+480h+Alertable], rsi
0x1400952de  mov     edx, 40002h
0x1400952e3  xor     ecx, ecx
0x1400952e5  mov     [rsp+480h+Timeout], rax
0x1400952ea  mov     cs:WdLogGlobalForLineNumber, eax
0x1400952f0  call    DxgkLogInternalTriageEvent
0x1400952f5  call    Feature_SafeDodBltQueueAccesses__private_IsEnabledDeviceUsageNoInline
0x1400952fa  test    eax, eax
0x1400952fc  jz      loc_140095496
0x140095302  call    Feature_DodVsyncEnsureLocked__private_IsEnabledDeviceUsageNoInline
0x140095307  test    eax, eax
0x140095309  jz      loc_140095496
0x14009530f  xor     r8d, r8d; bool
0x140095312  lea     rcx, [rsp+480h+var_428]; this
0x140095317  mov     rdx, r14; struct DXGPUSHLOCK *
0x14009531a  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x14009531f  mov     rcx, [rsp+480h+var_428+8]; this
0x140095324  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140095329  mov     rcx, [rsp+480h+var_410+8]; this
0x14009532e  mov     [rsp+480h+var_418], ebx
0x140095332  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140095337  lea     rcx, [rbp+380h+PerformanceFrequency]; PerformanceFrequency
0x14009533b  mov     [rbp+380h+var_400], 1
0x140095342  mov     r12, rsi
0x140095345  mov     qword ptr [rbp+380h+PerformanceFrequency], rsi
0x140095349  mov     r15, rsi
0x14009534c  call    cs:__imp_KeQueryPerformanceCounter
0x140095353  nop     dword ptr [rax+rax+00h]
0x140095358  mov     r8b, 1; unsigned __int8
0x14009535b  lea     rdx, [rdi+1C8h]; struct DXGSPINLOCK *
0x140095362  lea     rcx, [rbp+380h+var_3E8]; this
0x140095366  mov     rbx, rax
0x140095369  call    ??0DXGAUTOSPINLOCK@@QEAA@QEAVDXGSPINLOCK@@E@Z; DXGAUTOSPINLOCK::DXGAUTOSPINLOCK(DXGSPINLOCK * const,uchar)
0x14009536e  mov     r8, [rdi+1F0h]
0x140095375  mov     r14, [rdi+1E0h]
0x14009537c  test    r8, r8
0x14009537f  jle     short loc_1400953B9
0x140095381  test    r14, r14
0x140095384  jle     short loc_1400953B9
0x140095386  cmp     rbx, r14
0x140095389  jle     short loc_1400953B9
0x14009538b  mov     rcx, rbx
0x14009538e  sub     rcx, r14
0x140095391  mov     rax, rcx
0x140095394  cqo
0x140095396  idiv    r8
0x140095399  mov     rax, rbx
0x14009539c  sub     rcx, rdx
0x14009539f  lea     r12, [r8+rcx]
0x1400953a3  add     r12, r14
0x1400953a6  sub     rax, r12
0x1400953a9  imul    rax, 989680h
0x1400953b0  cqo
0x1400953b2  idiv    qword ptr [rbp+380h+PerformanceFrequency]
0x1400953b6  mov     r15, rax
0x1400953b9  lea     rcx, [rbp+380h+var_3E8]; this
0x1400953bd  call    ??1DXGAUTOSPINLOCK@@QEAA@XZ; DXGAUTOSPINLOCK::~DXGAUTOSPINLOCK(void)
0x1400953c2  mov     r11, [rdi+0BD8h]
0x1400953c9  mov     r10, rsi
0x1400953cc  shl     r10, 6
0x1400953d0  cmp     qword ptr [r10+r11+30h], 0
0x1400953d6  jz      short loc_14009540F
0x1400953d8  cmp     byte ptr [r10+r11+38h], 0
0x1400953de  jnz     short loc_14009540F
0x1400953e0  cmp     byte ptr [r10+r11+39h], 1
0x1400953e6  jnz     short loc_14009540F
0x1400953e8  mov     rcx, [r10+r11+20h]
0x1400953ed  xor     edx, edx
0x1400953ef  add     rcx, r15
0x1400953f2  test    rcx, rcx
0x1400953f5  cmovle  rdx, rcx
0x1400953f9  mov     rcx, [r10+r11]
0x1400953fd  xor     r9d, r9d
0x140095400  xor     r8d, r8d
0x140095403  call    cs:__imp_ExSetTimer
0x14009540a  nop     dword ptr [rax+rax+00h]
0x14009540f  inc     rsi
0x140095412  cmp     rsi, 8
0x140095416  jb      short loc_1400953C2
0x140095418  cmp     cs:bTracingEnabled, 0
0x14009541f  jz      short loc_140095456
0x140095421  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140095428  jz      short loc_140095456
0x14009542a  mov     rax, [rdi+1F0h]
0x140095431  mov     r9, r15
0x140095434  mov     [rsp+480h+var_440], rax
0x140095439  mov     rax, qword ptr [rbp+380h+PerformanceFrequency]
0x14009543d  mov     [rsp+480h+WaitBlockArray], r14
0x140095442  mov     [rsp+480h+var_450], rax
0x140095447  mov     qword ptr [rsp+480h+Alertable], rbx
0x14009544c  mov     [rsp+480h+Timeout], r12
0x140095451  call    McTemplateK0iiiiii_EtwWriteTransfer
0x140095456  mov     rcx, [rdi+80h]
0x14009545d  mov     rdx, r15
0x140095460  mov     rax, [rcx]
0x140095463  mov     rax, [rax+38h]
0x140095467  call    _guard_dispatch_icall
0x14009546c  lea     rcx, [rsp+480h+var_410]; this
0x140095471  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095476  lea     rcx, [rsp+480h+var_428]; this
0x14009547b  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140095480  lea     rcx, [rsp+480h+var_428]; this
0x140095485  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14009548a  lea     r12, [rdi+0BA8h]
0x140095491  jmp     loc_1400955FC
0x140095496  xor     r8d, r8d; bool
0x140095499  lea     rcx, [rsp+480h+var_428]; this
0x14009549e  mov     rdx, r14; struct DXGPUSHLOCK *
0x1400954a1  call    ??0DXGAUTOPUSHLOCK@@QEAA@QEAVDXGPUSHLOCK@@_N@Z; DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK(DXGPUSHLOCK * const,bool)
0x1400954a6  mov     rcx, [rsp+480h+var_428+8]; this
0x1400954ab  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1400954b0  mov     rcx, [rsp+480h+var_410+8]; this
0x1400954b5  mov     [rsp+480h+var_418], ebx
0x1400954b9  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x1400954be  lea     rcx, [rbp+380h+var_3F0]; PerformanceFrequency
0x1400954c2  mov     [rbp+380h+var_400], 1
0x1400954c9  mov     r15, rsi
0x1400954cc  mov     qword ptr [rbp+380h+var_3F0], rsi
0x1400954d0  mov     r14, rsi
0x1400954d3  call    cs:__imp_KeQueryPerformanceCounter
0x1400954da  nop     dword ptr [rax+rax+00h]
0x1400954df  mov     r9, [rdi+1F0h]
0x1400954e6  mov     rbx, rax
0x1400954e9  test    r9, r9
0x1400954ec  jle     short loc_14009552D
0x1400954ee  mov     r8, [rdi+1E0h]
0x1400954f5  test    r8, r8
0x1400954f8  jle     short loc_14009552D
0x1400954fa  cmp     rax, r8
0x1400954fd  jle     short loc_14009552D
0x1400954ff  mov     rcx, rax
0x140095502  sub     rcx, r8
0x140095505  mov     rax, rcx
0x140095508  cqo
0x14009550a  idiv    r9
0x14009550d  mov     rax, rbx
0x140095510  sub     rcx, rdx
0x140095513  lea     r15, [r9+rcx]
0x140095517  add     r15, r8
0x14009551a  sub     rax, r15
0x14009551d  imul    rax, 989680h
0x140095524  cqo
0x140095526  idiv    qword ptr [rbp+380h+var_3F0]
0x14009552a  mov     r14, rax
0x14009552d  mov     r11, [rdi+0BD8h]
0x140095534  mov     r10, rsi
0x140095537  shl     r10, 6
0x14009553b  cmp     qword ptr [r10+r11+30h], 0
0x140095541  jz      short loc_14009557A
0x140095543  cmp     byte ptr [r10+r11+38h], 0
  ... truncated ...
```
