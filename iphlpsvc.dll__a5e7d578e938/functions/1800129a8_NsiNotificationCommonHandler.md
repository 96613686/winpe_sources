# NsiNotificationCommonHandler

- ea: `0x1800129a8`
- end: `0x180012dc3`
- name: `NsiNotificationCommonHandler`
- size: `1051`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180050710`
- `0x180050750`
- `0x180050790`
- `0x1800507d0`
- `0x180050be0`

## callees

- `0x180004c64`
- `0x180004f60`
- `0x1800077e8`
- `0x180009010`
- `0x18000d7c0`
- `0x1800129a8`
- `0x180012dcc`
- `0x1800159d4`
- `0x180024250`
- `0x180025400`
- `0x180082274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012cd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012cd0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012cb5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012cb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012a6e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012a6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c8a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180012c34`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180012c34`

## string_xrefs

- `0x180012a38`: `NsiNotificationCommonHandler`
- `0x180012aa7`: `NsiNotificationCommonHandler`
- `0x180012cf2`: `NsiNotificationCommonHandler`
- `0x1800129da`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012ae9`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012b27`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012d49`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012d5e`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012af5`: `ReferenceCompartment: 0x%p: ++%d @ %ls:%u`
- `0x1800129fa`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180012a44`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012a86`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012ce0`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`

## pseudocode

```c
void __fastcall NsiNotificationCommonHandler(__int64 a1, int a2, int a3, __int64 a4)
{
  int v7; // esi
  int v8; // eax
  HANDLE v9; // rdi
  DWORD v10; // eax
  const wchar_t *v11; // rdx
  DWORD v12; // ebx
  __int64 v13; // r15
  _QWORD *v14; // rdi
  __int64 Compartment; // rax
  __int64 v16; // rbp
  int v17; // esi
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  _QWORD *v23; // rax
  HANDLE v24; // rbx
  __int64 v25; // r8
  __int64 v26; // [rsp+28h] [rbp-70h]
  __int64 v27; // [rsp+28h] [rbp-70h]
  __int64 v28; // [rsp+28h] [rbp-70h]
  __int64 v29; // [rsp+30h] [rbp-68h]

  if ( g_StopServiceEventSet )
    return;
  EventWrite0(
    0x40000,
    L"ReferenceService: ++%u (%hs) @ %ls:%u",
    ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
    "Nsi Event",
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    4203);
  v7 = 1;
  do
  {
    v8 = g_Reference;
    if ( (g_Reference & 1) != 0 )
      return;
  }
  while ( v8 != _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) );
  v9 = g_6to4Lock;
  LODWORD(v26) = 4207;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_6to4Lock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    "NsiNotificationCommonHandler",
    v26);
  v10 = WaitForSingleObject(v9, 0xFFFFFFFF);
  v11 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  v12 = v10;
  LODWORD(v27) = 4207;
  if ( v10 )
    v11 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  EventWrite0(
    0x800000,
    v11,
    v9,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    "NsiNotificationCommonHandler",
    v27,
    v10);
  if ( v12 )
  {
    v25 = 4208;
LABEL_39:
    DereferenceServiceEx("Nsi Event", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c", v25);
    return;
  }
  v13 = 0;
  v14 = 0;
  Compartment = FindOrCreateCompartment(1, &g_ProtocolState6to4);
  v16 = Compartment;
  if ( Compartment )
  {
    LODWORD(v28) = 4220;
    EventWrite0(
      0x100000,
      L"ReferenceCompartment: 0x%p: ++%d @ %ls:%u",
      Compartment,
      *(unsigned int *)(Compartment + 20),
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
      v28);
    v18 = *(_DWORD *)(v16 + 20);
    v19 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 32), 1u) & 0x3F);
    *(_DWORD *)(v16 + 8 * v19 + 40) = v18;
    *(_QWORD *)(v16 + 8 * v19 + 48) = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c";
    *(_DWORD *)(v16 + 8 * v19 + 72) = 0;
    *(_QWORD *)(v16 + 8 * v19 + 64) = 0;
    *(_DWORD *)(v16 + 8 * v19 + 56) = 4220;
    _InterlockedAdd((volatile signed __int32 *)(v16 + 20), 1u);
    if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
      McTemplateU0z_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
        L"Entered: Queueing Worker for Nsi Event");
    v20 = MALLOC(*(unsigned int *)(a1 + 8) + 56LL);
    v21 = v20;
    if ( !v20 )
      goto LABEL_14;
    v13 = v20;
    *(_OWORD *)(v20 + 16) = *(_OWORD *)a1;
    *(_QWORD *)(v20 + 48) = v20 + 56;
    *(_QWORD *)(v20 + 16) = v20 + 56;
    *(_DWORD *)(v20 + 40) = *(_DWORD *)(a1 + 8);
    memcpy_0((void *)(v20 + 56), *(const void **)a1, *(unsigned int *)(a1 + 8));
    *(_DWORD *)(v21 + 32) = a2;
    *(_QWORD *)v21 = v16;
    v22 = MALLOC(0x30u);
    v14 = (_QWORD *)v22;
    if ( v22 )
    {
      *(_QWORD *)(v22 + 40) = v21;
      *(_DWORD *)(v22 + 32) = a3;
      if ( (unsigned __int8)RoReferenceEx(&dword_1800C9FF0) )
      {
        EnterCriticalSection(&CriticalSection);
        if ( dword_1800CA000
          || (dword_1800CA000 = TrySubmitThreadpoolCallback(WorkQueueCallback, &CriticalSection, pcbe),
              (v7 = dword_1800CA000) != 0) )
        {
          v14[3] = a4;
          v14[2] = &CriticalSection;
          v23 = (_QWORD *)qword_1800CA010;
          if ( *(__int64 **)qword_1800CA010 != &qword_1800CA008 )
            __fastfail(3u);
          *v14 = &qword_1800CA008;
          v14[1] = v23;
          *v23 = v14;
          qword_1800CA010 = (__int64)v14;
        }
        LeaveCriticalSection(&CriticalSection);
        if ( v7 )
        {
          v17 = 0;
          goto LABEL_26;
        }
        if ( _InterlockedExchangeAdd(&dword_1800C9FF0, 0xFFFFFFFE) == 3 )
          SetEvent(qword_1800C9FF8);
      }
      v17 = 31;
    }
    else
    {
LABEL_14:
      EventWrite0(0x1000000, L"Malloc failed while duplicating NSI data");
      v17 = 8;
    }
  }
  else
  {
    v17 = 1168;
  }
LABEL_26:
  v24 = g_6to4Lock;
  LODWORD(v29) = ReleaseMutex(g_6to4Lock);
  LODWORD(v28) = 4279;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v24,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    "NsiNotificationCommonHandler",
    v28,
    v29);
  if ( v17 )
  {
    EventWriteLeaveEx(0x20000, L"Leaving: Failed to queue worker for Nsi Event");
    if ( v14 )
      FREE(v14);
    if ( v13 )
      FREE(v13);
    if ( v16 )
      DereferenceCompartmentEx(v16, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c", 4294);
    v25 = 4296;
    goto LABEL_39;
  }
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Leaving: Queued worker for Nsi Event");
}

```

## disassembly

```asm
0x1800129a8  mov     [rsp+arg_18], r9
0x1800129ad  push    rbx
0x1800129ae  push    rbp
0x1800129af  push    rsi
0x1800129b0  push    rdi
0x1800129b1  push    r12
0x1800129b3  push    r13
0x1800129b5  push    r14
0x1800129b7  push    r15
0x1800129b9  sub     rsp, 58h
0x1800129bd  cmp     cs:g_StopServiceEventSet, 0
0x1800129c4  mov     r12d, r8d
0x1800129c7  mov     r13d, edx
0x1800129ca  mov     r14, rcx
0x1800129cd  jnz     loc_180012DB1
0x1800129d3  mov     r8d, cs:g_Reference
0x1800129da  lea     r15, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800129e1  shr     r8d, 1
0x1800129e4  lea     r9, aNsiEvent; "Nsi Event"
0x1800129eb  and     r8d, 3FFFFFFFh
0x1800129f2  mov     dword ptr [rsp+98h+var_70], 106Bh
0x1800129fa  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180012a01  mov     [rsp+98h+var_78], r15
0x180012a06  mov     ecx, 40000h
0x180012a0b  call    EventWrite0
0x180012a10  mov     esi, 1
0x180012a15  mov     eax, cs:g_Reference
0x180012a1b  test    sil, al
0x180012a1e  jnz     loc_180012DB1
0x180012a24  lea     ecx, [rax+2]
0x180012a27  lock cmpxchg cs:g_Reference, ecx
0x180012a2f  jnz     short loc_180012A15
0x180012a31  mov     rdi, cs:g_6to4Lock
0x180012a38  lea     rax, aNsinotificatio; "NsiNotificationCommonHandler"
0x180012a3f  mov     ebp, 106Fh
0x180012a44  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012a4b  mov     dword ptr [rsp+98h+var_70], ebp
0x180012a4f  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180012a56  mov     r8, rdi
0x180012a59  mov     [rsp+98h+var_78], rax
0x180012a5e  mov     ecx, 800000h
0x180012a63  call    EventWrite0
0x180012a68  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012a6b  mov     rcx, rdi; hHandle
0x180012a6e  call    cs:__imp_WaitForSingleObject
0x180012a75  nop     dword ptr [rax+rax+00h]
0x180012a7a  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180012a81  mov     r8, rdi
0x180012a84  mov     ebx, eax
0x180012a86  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012a8d  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180012a94  mov     dword ptr [rsp+98h+var_68], ebx
0x180012a98  test    ebx, ebx
0x180012a9a  mov     dword ptr [rsp+98h+var_70], ebp
0x180012a9e  mov     ecx, 800000h
0x180012aa3  cmovnz  rdx, rax
0x180012aa7  lea     rax, aNsinotificatio; "NsiNotificationCommonHandler"
0x180012aae  mov     [rsp+98h+var_78], rax
0x180012ab3  call    EventWrite0
0x180012ab8  test    ebx, ebx
0x180012aba  jnz     loc_180012D9C
0x180012ac0  lea     rdx, g_ProtocolState6to4
0x180012ac7  mov     ecx, esi
0x180012ac9  xor     r15d, r15d
0x180012acc  xor     edi, edi
0x180012ace  call    FindOrCreateCompartment
0x180012ad3  mov     rbp, rax
0x180012ad6  test    rax, rax
0x180012ad9  jnz     short loc_180012AE5
0x180012adb  mov     esi, 490h
0x180012ae0  jmp     loc_180012CC6
0x180012ae5  mov     r9d, [rbp+14h]
0x180012ae9  lea     rax, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012af0  mov     ebx, 107Ch
0x180012af5  lea     rdx, aReferencecompa; "ReferenceCompartment: 0x%p: ++%d @ %ls:"...
0x180012afc  mov     dword ptr [rsp+98h+var_70], ebx
0x180012b00  mov     r8, rbp
0x180012b03  mov     ecx, 100000h
0x180012b08  mov     [rsp+98h+var_78], rax
0x180012b0d  call    EventWrite0
0x180012b12  mov     edx, [rbp+14h]
0x180012b15  mov     eax, esi
0x180012b17  lock xadd [rbp+20h], eax
0x180012b1c  add     eax, esi
0x180012b1e  sub     eax, esi
0x180012b20  and     eax, 3Fh
0x180012b23  lea     rcx, [rax+rax*4]
0x180012b27  lea     rax, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012b2e  mov     [rbp+rcx*8+28h], edx
0x180012b32  mov     [rbp+rcx*8+30h], rax
0x180012b37  xor     eax, eax
0x180012b39  mov     [rbp+rcx*8+48h], eax
0x180012b3d  mov     [rbp+rcx*8+40h], rax
0x180012b42  mov     [rbp+rcx*8+38h], ebx
0x180012b46  lock add [rbp+14h], esi
0x180012b4a  cmp     cs:IpHlpSvcEtwEnabled, al
0x180012b50  jz      short loc_180012B74
0x180012b52  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, al
0x180012b58  jge     short loc_180012B74
0x180012b5a  lea     r8, aEnteredQueuein_0; "Entered: Queueing Worker for Nsi Event"
0x180012b61  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180012b68  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180012b6f  call    McTemplateU0z_EventWriteTransfer
0x180012b74  mov     ecx, [r14+8]
0x180012b78  add     rcx, 38h ; '8'; dwBytes
0x180012b7c  call    MALLOC
0x180012b81  mov     rbx, rax
0x180012b84  test    rax, rax
0x180012b87  jnz     short loc_180012BA4
0x180012b89  lea     rdx, aMallocFailedWh; "Malloc failed while duplicating NSI dat"...
0x180012b90  mov     ecx, 1000000h
0x180012b95  call    EventWrite0
0x180012b9a  mov     esi, 8
0x180012b9f  jmp     loc_180012CC6
0x180012ba4  movups  xmm0, xmmword ptr [r14]
0x180012ba8  lea     rcx, [rax+38h]; void *
0x180012bac  mov     r15, rbx
0x180012baf  movdqu  xmmword ptr [rax+10h], xmm0
0x180012bb4  mov     [rax+30h], rcx
0x180012bb8  mov     [rax+10h], rcx
0x180012bbc  mov     eax, [r14+8]
0x180012bc0  mov     [rbx+28h], eax
0x180012bc3  mov     r8d, [r14+8]; Size
0x180012bc7  mov     rdx, [r14]; Src
0x180012bca  call    memcpy_0
0x180012bcf  mov     ecx, 30h ; '0'; dwBytes
0x180012bd4  mov     [rbx+20h], r13d
0x180012bd8  mov     [rbx], rbp
0x180012bdb  call    MALLOC
0x180012be0  mov     rdi, rax
0x180012be3  test    rax, rax
0x180012be6  jz      short loc_180012B89
0x180012be8  lea     rcx, dword_1800C9FF0
0x180012bef  mov     [rax+28h], rbx
0x180012bf3  mov     [rax+20h], r12d
0x180012bf7  call    RoReferenceEx
0x180012bfc  test    al, al
0x180012bfe  jz      loc_180012CC1
0x180012c04  lea     rbx, CriticalSection
0x180012c0b  mov     rcx, rbx; lpCriticalSection
0x180012c0e  call    cs:__imp_EnterCriticalSection
0x180012c15  nop     dword ptr [rax+rax+00h]
0x180012c1a  cmp     cs:dword_1800CA000, 0
0x180012c21  jnz     short loc_180012C4C
0x180012c23  mov     r8, cs:pcbe; pcbe
0x180012c2a  lea     rcx, WorkQueueCallback; pfns
0x180012c31  mov     rdx, rbx; pv
0x180012c34  call    cs:__imp_TrySubmitThreadpoolCallback
0x180012c3b  nop     dword ptr [rax+rax+00h]
0x180012c40  mov     cs:dword_1800CA000, eax
0x180012c46  mov     esi, eax
0x180012c48  test    eax, eax
0x180012c4a  jz      short loc_180012C87
0x180012c4c  mov     rax, [rsp+98h+arg_18]
0x180012c54  lea     rcx, qword_1800CA008
0x180012c5b  mov     [rdi+18h], rax
0x180012c5f  mov     [rdi+10h], rbx
0x180012c63  mov     rax, cs:qword_1800CA010
0x180012c6a  cmp     [rax], rcx
0x180012c6d  jz      short loc_180012C76
0x180012c6f  mov     ecx, 3
0x180012c74  int     29h; Win8: RtlFailFast(ecx)
0x180012c76  mov     [rdi], rcx
0x180012c79  mov     [rdi+8], rax
0x180012c7d  mov     [rax], rdi
0x180012c80  mov     cs:qword_1800CA010, rdi
0x180012c87  mov     rcx, rbx; lpCriticalSection
0x180012c8a  call    cs:__imp_LeaveCriticalSection
0x180012c91  nop     dword ptr [rax+rax+00h]
0x180012c96  test    esi, esi
0x180012c98  jnz     loc_180012D67
0x180012c9e  lea     eax, [rsi-2]
0x180012ca1  lock xadd cs:dword_1800C9FF0, eax
0x180012ca9  cmp     eax, 3
0x180012cac  jnz     short loc_180012CC1
0x180012cae  mov     rcx, cs:qword_1800C9FF8; hEvent
0x180012cb5  call    cs:__imp_SetEvent
0x180012cbc  nop     dword ptr [rax+rax+00h]
0x180012cc1  mov     esi, 1Fh
0x180012cc6  mov     rbx, cs:g_6to4Lock
0x180012ccd  mov     rcx, rbx; hMutex
0x180012cd0  call    cs:__imp_ReleaseMutex
0x180012cd7  nop     dword ptr [rax+rax+00h]
0x180012cdc  mov     dword ptr [rsp+98h+var_68], eax
0x180012ce0  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012ce7  mov     dword ptr [rsp+98h+var_70], 10B7h
0x180012cef  mov     r8, rbx
0x180012cf2  lea     rax, aNsinotificatio; "NsiNotificationCommonHandler"
0x180012cf9  mov     ecx, 800000h
0x180012cfe  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180012d05  mov     [rsp+98h+var_78], rax
0x180012d0a  call    EventWrite0
0x180012d0f  test    esi, esi
0x180012d11  jz      short loc_180012D6E
0x180012d13  lea     rdx, aLeavingFailedT_0; "Leaving: Failed to queue worker for Nsi"...
0x180012d1a  mov     ecx, 20000h
0x180012d1f  call    EventWriteLeaveEx
0x180012d24  test    rdi, rdi
0x180012d27  jz      short loc_180012D31
0x180012d29  mov     rcx, rdi
0x180012d2c  call    FREE
0x180012d31  test    r15, r15
0x180012d34  jz      short loc_180012D3E
0x180012d36  mov     rcx, r15
0x180012d39  call    FREE
0x180012d3e  test    rbp, rbp
0x180012d41  jz      short loc_180012D58
0x180012d43  mov     r8d, 10C6h
0x180012d49  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012d50  mov     rcx, rbp
0x180012d53  call    DereferenceCompartmentEx
0x180012d58  mov     r8d, 10C8h
0x180012d5e  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012d65  jmp     short loc_180012DA5
0x180012d67  xor     esi, esi
0x180012d69  jmp     loc_180012CC6
0x180012d6e  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180012d75  jz      short loc_180012DB1
0x180012d77  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180012d7e  jge     short loc_180012DB1
0x180012d80  lea     r8, aLeavingQueuedW; "Leaving: Queued worker for Nsi Event"
0x180012d87  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180012d8e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180012d95  call    McTemplateU0z_EventWriteTransfer
0x180012d9a  jmp     short loc_180012DB1
0x180012d9c  mov     r8d, 1070h
0x180012da2  mov     rdx, r15
0x180012da5  lea     rcx, aNsiEvent; "Nsi Event"
0x180012dac  call    DereferenceServiceEx
0x180012db1  add     rsp, 58h
0x180012db5  pop     r15
0x180012db7  pop     r14
0x180012db9  pop     r13
0x180012dbb  pop     r12
0x180012dbd  pop     rdi
0x180012dbe  pop     rsi
0x180012dbf  pop     rbp
0x180012dc0  pop     rbx
0x180012dc1  retn
```
