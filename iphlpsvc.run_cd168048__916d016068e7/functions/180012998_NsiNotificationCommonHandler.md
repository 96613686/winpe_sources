# NsiNotificationCommonHandler

- ea: `0x180012998`
- end: `0x180012db3`
- name: `NsiNotificationCommonHandler`
- size: `1051`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180050750`
- `0x180050790`
- `0x1800507d0`
- `0x180050810`
- `0x180050c20`

## callees

- `0x180004c54`
- `0x180004f50`
- `0x1800077d8`
- `0x180009000`
- `0x18000d7b0`
- `0x180012998`
- `0x180012dbc`
- `0x1800159c4`
- `0x180024240`
- `0x1800253f0`
- `0x180082084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012cc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012cc0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012ca5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012ca5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012a5e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012a5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c7a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180012c24`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180012c24`

## string_xrefs

- `0x180012a28`: `NsiNotificationCommonHandler`
- `0x180012a97`: `NsiNotificationCommonHandler`
- `0x180012ce2`: `NsiNotificationCommonHandler`
- `0x1800129ca`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012ad9`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012b17`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012d39`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012d4e`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012ae5`: `ReferenceCompartment: 0x%p: ++%d @ %ls:%u`
- `0x1800129ea`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180012a34`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012a76`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180012cd0`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`

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
0x180012998  mov     [rsp+arg_18], r9
0x18001299d  push    rbx
0x18001299e  push    rbp
0x18001299f  push    rsi
0x1800129a0  push    rdi
0x1800129a1  push    r12
0x1800129a3  push    r13
0x1800129a5  push    r14
0x1800129a7  push    r15
0x1800129a9  sub     rsp, 58h
0x1800129ad  cmp     cs:g_StopServiceEventSet, 0
0x1800129b4  mov     r12d, r8d
0x1800129b7  mov     r13d, edx
0x1800129ba  mov     r14, rcx
0x1800129bd  jnz     loc_180012DA1
0x1800129c3  mov     r8d, cs:g_Reference
0x1800129ca  lea     r15, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800129d1  shr     r8d, 1
0x1800129d4  lea     r9, aNsiEvent; "Nsi Event"
0x1800129db  and     r8d, 3FFFFFFFh
0x1800129e2  mov     dword ptr [rsp+98h+var_70], 106Bh
0x1800129ea  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x1800129f1  mov     [rsp+98h+var_78], r15
0x1800129f6  mov     ecx, 40000h
0x1800129fb  call    EventWrite0
0x180012a00  mov     esi, 1
0x180012a05  mov     eax, cs:g_Reference
0x180012a0b  test    sil, al
0x180012a0e  jnz     loc_180012DA1
0x180012a14  lea     ecx, [rax+2]
0x180012a17  lock cmpxchg cs:g_Reference, ecx
0x180012a1f  jnz     short loc_180012A05
0x180012a21  mov     rdi, cs:g_6to4Lock
0x180012a28  lea     rax, aNsinotificatio; "NsiNotificationCommonHandler"
0x180012a2f  mov     ebp, 106Fh
0x180012a34  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012a3b  mov     dword ptr [rsp+98h+var_70], ebp
0x180012a3f  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180012a46  mov     r8, rdi
0x180012a49  mov     [rsp+98h+var_78], rax
0x180012a4e  mov     ecx, 800000h
0x180012a53  call    EventWrite0
0x180012a58  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012a5b  mov     rcx, rdi; hHandle
0x180012a5e  call    cs:__imp_WaitForSingleObject
0x180012a65  nop     dword ptr [rax+rax+00h]
0x180012a6a  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180012a71  mov     r8, rdi
0x180012a74  mov     ebx, eax
0x180012a76  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012a7d  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180012a84  mov     dword ptr [rsp+98h+var_68], ebx
0x180012a88  test    ebx, ebx
0x180012a8a  mov     dword ptr [rsp+98h+var_70], ebp
0x180012a8e  mov     ecx, 800000h
0x180012a93  cmovnz  rdx, rax
0x180012a97  lea     rax, aNsinotificatio; "NsiNotificationCommonHandler"
0x180012a9e  mov     [rsp+98h+var_78], rax
0x180012aa3  call    EventWrite0
0x180012aa8  test    ebx, ebx
0x180012aaa  jnz     loc_180012D8C
0x180012ab0  lea     rdx, g_ProtocolState6to4
0x180012ab7  mov     ecx, esi
0x180012ab9  xor     r15d, r15d
0x180012abc  xor     edi, edi
0x180012abe  call    FindOrCreateCompartment
0x180012ac3  mov     rbp, rax
0x180012ac6  test    rax, rax
0x180012ac9  jnz     short loc_180012AD5
0x180012acb  mov     esi, 490h
0x180012ad0  jmp     loc_180012CB6
0x180012ad5  mov     r9d, [rbp+14h]
0x180012ad9  lea     rax, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012ae0  mov     ebx, 107Ch
0x180012ae5  lea     rdx, aReferencecompa; "ReferenceCompartment: 0x%p: ++%d @ %ls:"...
0x180012aec  mov     dword ptr [rsp+98h+var_70], ebx
0x180012af0  mov     r8, rbp
0x180012af3  mov     ecx, 100000h
0x180012af8  mov     [rsp+98h+var_78], rax
0x180012afd  call    EventWrite0
0x180012b02  mov     edx, [rbp+14h]
0x180012b05  mov     eax, esi
0x180012b07  lock xadd [rbp+20h], eax
0x180012b0c  add     eax, esi
0x180012b0e  sub     eax, esi
0x180012b10  and     eax, 3Fh
0x180012b13  lea     rcx, [rax+rax*4]
0x180012b17  lea     rax, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012b1e  mov     [rbp+rcx*8+28h], edx
0x180012b22  mov     [rbp+rcx*8+30h], rax
0x180012b27  xor     eax, eax
0x180012b29  mov     [rbp+rcx*8+48h], eax
0x180012b2d  mov     [rbp+rcx*8+40h], rax
0x180012b32  mov     [rbp+rcx*8+38h], ebx
0x180012b36  lock add [rbp+14h], esi
0x180012b3a  cmp     cs:IpHlpSvcEtwEnabled, al
0x180012b40  jz      short loc_180012B64
0x180012b42  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, al
0x180012b48  jge     short loc_180012B64
0x180012b4a  lea     r8, aEnteredQueuein_0; "Entered: Queueing Worker for Nsi Event"
0x180012b51  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180012b58  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180012b5f  call    McTemplateU0z_EventWriteTransfer
0x180012b64  mov     ecx, [r14+8]
0x180012b68  add     rcx, 38h ; '8'; dwBytes
0x180012b6c  call    MALLOC
0x180012b71  mov     rbx, rax
0x180012b74  test    rax, rax
0x180012b77  jnz     short loc_180012B94
0x180012b79  lea     rdx, aMallocFailedWh; "Malloc failed while duplicating NSI dat"...
0x180012b80  mov     ecx, 1000000h
0x180012b85  call    EventWrite0
0x180012b8a  mov     esi, 8
0x180012b8f  jmp     loc_180012CB6
0x180012b94  movups  xmm0, xmmword ptr [r14]
0x180012b98  lea     rcx, [rax+38h]; void *
0x180012b9c  mov     r15, rbx
0x180012b9f  movdqu  xmmword ptr [rax+10h], xmm0
0x180012ba4  mov     [rax+30h], rcx
0x180012ba8  mov     [rax+10h], rcx
0x180012bac  mov     eax, [r14+8]
0x180012bb0  mov     [rbx+28h], eax
0x180012bb3  mov     r8d, [r14+8]; Size
0x180012bb7  mov     rdx, [r14]; Src
0x180012bba  call    memcpy_0
0x180012bbf  mov     ecx, 30h ; '0'; dwBytes
0x180012bc4  mov     [rbx+20h], r13d
0x180012bc8  mov     [rbx], rbp
0x180012bcb  call    MALLOC
0x180012bd0  mov     rdi, rax
0x180012bd3  test    rax, rax
0x180012bd6  jz      short loc_180012B79
0x180012bd8  lea     rcx, dword_1800C9FF0
0x180012bdf  mov     [rax+28h], rbx
0x180012be3  mov     [rax+20h], r12d
0x180012be7  call    RoReferenceEx
0x180012bec  test    al, al
0x180012bee  jz      loc_180012CB1
0x180012bf4  lea     rbx, CriticalSection
0x180012bfb  mov     rcx, rbx; lpCriticalSection
0x180012bfe  call    cs:__imp_EnterCriticalSection
0x180012c05  nop     dword ptr [rax+rax+00h]
0x180012c0a  cmp     cs:dword_1800CA000, 0
0x180012c11  jnz     short loc_180012C3C
0x180012c13  mov     r8, cs:pcbe; pcbe
0x180012c1a  lea     rcx, WorkQueueCallback; pfns
0x180012c21  mov     rdx, rbx; pv
0x180012c24  call    cs:__imp_TrySubmitThreadpoolCallback
0x180012c2b  nop     dword ptr [rax+rax+00h]
0x180012c30  mov     cs:dword_1800CA000, eax
0x180012c36  mov     esi, eax
0x180012c38  test    eax, eax
0x180012c3a  jz      short loc_180012C77
0x180012c3c  mov     rax, [rsp+98h+arg_18]
0x180012c44  lea     rcx, qword_1800CA008
0x180012c4b  mov     [rdi+18h], rax
0x180012c4f  mov     [rdi+10h], rbx
0x180012c53  mov     rax, cs:qword_1800CA010
0x180012c5a  cmp     [rax], rcx
0x180012c5d  jz      short loc_180012C66
0x180012c5f  mov     ecx, 3
0x180012c64  int     29h; Win8: RtlFailFast(ecx)
0x180012c66  mov     [rdi], rcx
0x180012c69  mov     [rdi+8], rax
0x180012c6d  mov     [rax], rdi
0x180012c70  mov     cs:qword_1800CA010, rdi
0x180012c77  mov     rcx, rbx; lpCriticalSection
0x180012c7a  call    cs:__imp_LeaveCriticalSection
0x180012c81  nop     dword ptr [rax+rax+00h]
0x180012c86  test    esi, esi
0x180012c88  jnz     loc_180012D57
0x180012c8e  lea     eax, [rsi-2]
0x180012c91  lock xadd cs:dword_1800C9FF0, eax
0x180012c99  cmp     eax, 3
0x180012c9c  jnz     short loc_180012CB1
0x180012c9e  mov     rcx, cs:qword_1800C9FF8; hEvent
0x180012ca5  call    cs:__imp_SetEvent
0x180012cac  nop     dword ptr [rax+rax+00h]
0x180012cb1  mov     esi, 1Fh
0x180012cb6  mov     rbx, cs:g_6to4Lock
0x180012cbd  mov     rcx, rbx; hMutex
0x180012cc0  call    cs:__imp_ReleaseMutex
0x180012cc7  nop     dword ptr [rax+rax+00h]
0x180012ccc  mov     dword ptr [rsp+98h+var_68], eax
0x180012cd0  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012cd7  mov     dword ptr [rsp+98h+var_70], 10B7h
0x180012cdf  mov     r8, rbx
0x180012ce2  lea     rax, aNsinotificatio; "NsiNotificationCommonHandler"
0x180012ce9  mov     ecx, 800000h
0x180012cee  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180012cf5  mov     [rsp+98h+var_78], rax
0x180012cfa  call    EventWrite0
0x180012cff  test    esi, esi
0x180012d01  jz      short loc_180012D5E
0x180012d03  lea     rdx, aLeavingFailedT_0; "Leaving: Failed to queue worker for Nsi"...
0x180012d0a  mov     ecx, 20000h
0x180012d0f  call    EventWriteLeaveEx
0x180012d14  test    rdi, rdi
0x180012d17  jz      short loc_180012D21
0x180012d19  mov     rcx, rdi
0x180012d1c  call    FREE
0x180012d21  test    r15, r15
0x180012d24  jz      short loc_180012D2E
0x180012d26  mov     rcx, r15
0x180012d29  call    FREE
0x180012d2e  test    rbp, rbp
0x180012d31  jz      short loc_180012D48
0x180012d33  mov     r8d, 10C6h
0x180012d39  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012d40  mov     rcx, rbp
0x180012d43  call    DereferenceCompartmentEx
0x180012d48  mov     r8d, 10C8h
0x180012d4e  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180012d55  jmp     short loc_180012D95
0x180012d57  xor     esi, esi
0x180012d59  jmp     loc_180012CB6
0x180012d5e  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180012d65  jz      short loc_180012DA1
0x180012d67  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180012d6e  jge     short loc_180012DA1
0x180012d70  lea     r8, aLeavingQueuedW; "Leaving: Queued worker for Nsi Event"
0x180012d77  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180012d7e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180012d85  call    McTemplateU0z_EventWriteTransfer
0x180012d8a  jmp     short loc_180012DA1
0x180012d8c  mov     r8d, 1070h
0x180012d92  mov     rdx, r15
0x180012d95  lea     rcx, aNsiEvent; "Nsi Event"
0x180012d9c  call    DereferenceServiceEx
0x180012da1  add     rsp, 58h
0x180012da5  pop     r15
0x180012da7  pop     r14
0x180012da9  pop     r13
0x180012dab  pop     r12
0x180012dad  pop     rdi
0x180012dae  pop     rsi
0x180012daf  pop     rbp
0x180012db0  pop     rbx
0x180012db1  retn
```
