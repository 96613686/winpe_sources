# HandleDemandDialEvent

- ea: `0x180010260`
- end: `0x180010699`
- name: `HandleDemandDialEvent`
- size: `1081`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x18000f868`
- `0x18000fe0c`
- `0x180010260`
- `0x180010b80`
- `0x180010cd8`
- `0x18001121c`
- `0x180011790`
- `0x18005281c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180010364`
- `ntdll!RtlAcquireResourceExclusive` at `0x180010364`
- `ntdll!RtlReleaseResource` at `0x1800103e0`
- `ntdll!RtlReleaseResource` at `0x180010522`
- `ntdll!RtlReleaseResource` at `0x1800103e0`
- `ntdll!RtlReleaseResource` at `0x180010522`
- `KERNEL32!HeapFree` at `0x1800103f9`
- `KERNEL32!HeapFree` at `0x18001040b`
- `KERNEL32!HeapFree` at `0x1800103f9`
- `KERNEL32!HeapFree` at `0x18001040b`
- `KERNEL32!LeaveCriticalSection` at `0x180010511`
- `KERNEL32!LeaveCriticalSection` at `0x18001065d`
- `KERNEL32!LeaveCriticalSection` at `0x180010511`
- `KERNEL32!LeaveCriticalSection` at `0x18001065d`
- `KERNEL32!EnterCriticalSection` at `0x1800104fc`
- `KERNEL32!EnterCriticalSection` at `0x18001064e`
- `KERNEL32!EnterCriticalSection` at `0x1800104fc`
- `KERNEL32!EnterCriticalSection` at `0x18001064e`

## string_xrefs

- `0x180010554`: `HandleDemandDialEvent: QueueWorkItemInThreadPool failed with error %d`

## pseudocode

```c
void __fastcall HandleDemandDialEvent(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)
{
  char v4; // al
  unsigned int v5; // ebx
  unsigned int *v6; // r14
  __int64 v7; // rax
  __int64 v8; // r15
  void *v9; // r8
  const wchar_t *v10; // r8
  __int64 *v11; // rdx
  __int128 *v12; // r9
  int v13; // edi
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int128 *v18; // r9
  struct _RTL_CRITICAL_SECTION *v19; // rax
  struct _RTL_CRITICAL_SECTION *v20; // rdi
  struct _RTL_CRITICAL_SECTION *v21; // rbx
  __int128 v22; // [rsp+38h] [rbp-880h] BYREF
  int v23; // [rsp+48h] [rbp-870h] BYREF
  __int128 v24; // [rsp+4Ch] [rbp-86Ch]
  __int128 v25; // [rsp+5Ch] [rbp-85Ch]
  int v26; // [rsp+6Ch] [rbp-84Ch]
  int v27; // [rsp+70h] [rbp-848h] BYREF
  _BYTE v28[2044]; // [rsp+74h] [rbp-844h] BYREF

  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v23 = 0;
  v26 = 0;
  v4 = Microsoft_Windows_RRASEnableBits;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Entered: %ws", L"HandleDemandDialEvent");
    v4 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v27);
      v4 = Microsoft_Windows_RRASEnableBits;
    }
  }
  v5 = *(_DWORD *)Context;
  v6 = (unsigned int *)Context[1];
  if ( v4 < 0 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"HandleDemandDialEvent: InterfaceLookupByICBSeqNumber: %d, Event: %d", v6[1], *v6);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v27);
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  v7 = InterfaceLookupByICBSeqNumber(v6[1]);
  v8 = v7;
  if ( *v6 > 2 )
  {
    if ( *v6 == 3 )
    {
      HandleDialOutLinkUp(v5, (__int64)v6);
      goto LABEL_14;
    }
    if ( *v6 == 4 )
    {
      HandleDialOutLinkDown(v5, (__int64)v6);
      goto LABEL_14;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_14;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"HandleDemandDialEvent: Illegal event %d from WanArp", *v6);
LABEL_12:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v27);
    goto LABEL_14;
  }
  if ( !v7 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_14;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"HandleDemandDialEvent: Event %d, could not find interface with ICB %d", *v6, v6[1]);
    goto LABEL_12;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v27) = 0;
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v27, L"HandleDemandDialEvent: PICB Found with V4=%d", *(unsigned int *)(v7 + 516));
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v12 = &v22;
      if ( v8 != -688 )
        LODWORD(v12) = v8 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v27,
        (_DWORD)v12,
        *(_QWORD *)(v8 + 72),
        (__int64)&v23);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 720));
  v13 = *((_DWORD *)Context + 1);
  v14 = *(_DWORD *)(v8 + 764);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 720));
  if ( v13 == v14 )
  {
    if ( *v6 )
    {
      if ( *v6 == 1 )
      {
        HandleConnectionNotification(v8, v6);
      }
      else if ( *v6 == 2 )
      {
        HandleDisconnectionNotification((LPVOID)v8);
      }
      else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v27) = 0;
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v27, L"HandleDemandDialEvent: Illegal event %d from WanArp", *v6);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v18 = &v22;
          if ( v8 != -688 )
            LODWORD(v18) = v8 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v27,
            (_DWORD)v18,
            *(_QWORD *)(v8 + 72),
            (__int64)&v23);
        }
      }
    }
    else
    {
      HandleConnectionRequest(v8, (__int64)v6);
    }
    v19 = (struct _RTL_CRITICAL_SECTION *)InterfaceLookupByICBSeqNumber(v6[1]);
    v20 = v19;
    if ( v19 )
    {
      v21 = v19 + 18;
      EnterCriticalSection(v19 + 18);
      ++HIDWORD(v20[19].DebugInfo);
      LeaveCriticalSection(v21);
    }
LABEL_14:
    RtlReleaseResource(&Resource);
    v9 = (void *)Context[1];
    if ( v9 )
      HeapFree(IPRouterHeap, 0, v9);
    HeapFree(IPRouterHeap, 0, Context);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v10 = L"Leaving: HandleDemandDialEvent";
      v11 = RasRtrmgrTraceInfo;
LABEL_18:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v11, v10);
      return;
    }
    return;
  }
  RtlReleaseResource(&Resource);
  v17 = QueueWorkItemInThreadPool(v16, v15, Context);
  if ( v17 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v27, L"HandleDemandDialEvent: QueueWorkItemInThreadPool failed with error %d", v17);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v10 = (const wchar_t *)&v27;
        v11 = RasRtrMgrTraceError;
        goto LABEL_18;
      }
    }
  }
}

```

## disassembly

```asm
0x180010260  push    rbx
0x180010262  push    rsi
0x180010263  push    rdi
0x180010264  push    r12
0x180010266  push    r14
0x180010268  push    r15
0x18001026a  sub     rsp, 888h
0x180010271  mov     rax, cs:__security_cookie
0x180010278  xor     rax, rsp
0x18001027b  mov     [rsp+8B8h+var_48], rax
0x180010283  mov     r12, rdx
0x180010286  lea     rcx, [rsp+8B8h+var_844]; void *
0x18001028b  xor     eax, eax
0x18001028d  xor     edx, edx; Val
0x18001028f  mov     r8d, 7FCh; Size
0x180010295  mov     [rsp+8B8h+var_848], eax
0x180010299  call    memset_0
0x18001029e  xor     eax, eax
0x1800102a0  xorps   xmm0, xmm0
0x1800102a3  mov     [rsp+8B8h+var_870], eax
0x1800102a7  mov     [rsp+8B8h+var_84C], eax
0x1800102ab  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800102b2  movups  [rsp+8B8h+var_86C], xmm0
0x1800102b7  movups  [rsp+8B8h+var_85C], xmm0
0x1800102bc  movups  [rsp+8B8h+var_880], xmm0
0x1800102c1  test    al, al
0x1800102c3  jns     short loc_18001030E
0x1800102c5  xor     eax, eax
0x1800102c7  lea     r8, aHandledemanddi_4; "HandleDemandDialEvent"
0x1800102ce  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800102d5  mov     word ptr [rsp+8B8h+var_848], ax
0x1800102da  lea     rcx, [rsp+8B8h+var_848]
0x1800102df  call    FormatRRASErrorString
0x1800102e4  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800102eb  test    al, al
0x1800102ed  jns     short loc_18001030E
0x1800102ef  lea     r8, [rsp+8B8h+var_848]
0x1800102f4  lea     rdx, RasRtrmgrTraceInfo
0x1800102fb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010302  call    McTemplateU0z_EventWriteTransfer
0x180010307  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001030e  mov     ebx, [r12]
0x180010312  mov     r14, [r12+8]
0x180010317  test    al, al
0x180010319  jns     short loc_18001035B
0x18001031b  xor     eax, eax
0x18001031d  lea     rdx, aHandledemanddi_3; "HandleDemandDialEvent: InterfaceLookupB"...
0x180010324  mov     word ptr [rsp+8B8h+var_848], ax
0x180010329  lea     rcx, [rsp+8B8h+var_848]
0x18001032e  mov     r9d, [r14]
0x180010331  mov     r8d, [r14+4]
0x180010335  call    FormatRRASErrorString
0x18001033a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180010341  jge     short loc_18001035B
0x180010343  lea     r8, [rsp+8B8h+var_848]
0x180010348  lea     rdx, RasRtrmgrTraceInfo
0x18001034f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010356  call    McTemplateU0z_EventWriteTransfer
0x18001035b  mov     dl, 1; Wait
0x18001035d  lea     rcx, Resource; Resource
0x180010364  call    cs:__imp_RtlAcquireResourceExclusive
0x18001036a  mov     ecx, [r14+4]
0x18001036e  call    InterfaceLookupByICBSeqNumber
0x180010373  mov     ecx, [r14]
0x180010376  mov     r15, rax
0x180010379  cmp     ecx, 2
0x18001037c  jbe     loc_180010475
0x180010382  sub     ecx, 3
0x180010385  jz      loc_180010466
0x18001038b  cmp     ecx, 1
0x18001038e  jz      loc_180010457
0x180010394  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001039b  jge     short loc_1800103D9
0x18001039d  xor     eax, eax
0x18001039f  lea     rdx, aHandledemanddi_1; "HandleDemandDialEvent: Illegal event %d"...
0x1800103a6  mov     word ptr [rsp+8B8h+var_848], ax
0x1800103ab  lea     rcx, [rsp+8B8h+var_848]
0x1800103b0  mov     r8d, [r14]
0x1800103b3  call    FormatRRASErrorString
0x1800103b8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800103bf  jge     short loc_1800103D9
0x1800103c1  lea     r8, [rsp+8B8h+var_848]
0x1800103c6  lea     rdx, RasRtrmgrTraceInfo
0x1800103cd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800103d4  call    McTemplateU0z_EventWriteTransfer
0x1800103d9  lea     rcx, Resource; Resource
0x1800103e0  call    cs:__imp_RtlReleaseResource
0x1800103e6  mov     r8, [r12+8]; lpMem
0x1800103eb  test    r8, r8
0x1800103ee  jz      short loc_1800103FF
0x1800103f0  mov     rcx, cs:IPRouterHeap; hHeap
0x1800103f7  xor     edx, edx; dwFlags
0x1800103f9  call    cs:__imp_HeapFree
0x1800103ff  mov     rcx, cs:IPRouterHeap; hHeap
0x180010406  mov     r8, r12; lpMem
0x180010409  xor     edx, edx; dwFlags
0x18001040b  call    cs:__imp_HeapFree
0x180010411  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180010418  jz      short loc_180010434
0x18001041a  lea     r8, aLeavingHandled; "Leaving: HandleDemandDialEvent"
0x180010421  lea     rdx, RasRtrmgrTraceInfo
0x180010428  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001042f  call    McTemplateU0z_EventWriteTransfer
0x180010434  xor     eax, eax
0x180010436  mov     rcx, [rsp+8B8h+var_48]
0x18001043e  xor     rcx, rsp; StackCookie
0x180010441  call    __security_check_cookie
0x180010446  add     rsp, 888h
0x18001044d  pop     r15
0x18001044f  pop     r14
0x180010451  pop     r12
0x180010453  pop     rdi
0x180010454  pop     rsi
0x180010455  pop     rbx
0x180010456  retn
0x180010457  mov     rdx, r14
0x18001045a  mov     ecx, ebx
0x18001045c  call    HandleDialOutLinkDown
0x180010461  jmp     loc_1800103D9
0x180010466  mov     rdx, r14
0x180010469  mov     ecx, ebx; int
0x18001046b  call    HandleDialOutLinkUp
0x180010470  jmp     loc_1800103D9
0x180010475  test    r15, r15
0x180010478  jz      loc_180010668
0x18001047e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180010485  jge     short loc_1800104F2
0x180010487  xor     eax, eax
0x180010489  lea     rdx, aHandledemanddi_9; "HandleDemandDialEvent: PICB Found with "...
0x180010490  mov     word ptr [rsp+8B8h+var_848], ax
0x180010495  lea     rcx, [rsp+8B8h+var_848]
0x18001049a  mov     word ptr [rsp+8B8h+var_870], ax
0x18001049f  mov     r8d, [r15+204h]
0x1800104a6  call    FormatRRASErrorString
0x1800104ab  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800104b2  jge     short loc_1800104F2
0x1800104b4  lea     rax, [r15+2B0h]
0x1800104bb  test    rax, rax
0x1800104be  lea     r9, [rsp+8B8h+var_880]
0x1800104c3  lea     r8, [rsp+8B8h+var_848]
0x1800104c8  cmovnz  r9, rax
0x1800104cc  lea     rdx, RasRtrmgrParamTraceInfo
0x1800104d3  lea     rax, [rsp+8B8h+var_870]
0x1800104d8  mov     [rsp+8B8h+var_890], rax
0x1800104dd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800104e4  mov     rax, [r15+48h]
0x1800104e8  mov     [rsp+8B8h+var_898], rax
0x1800104ed  call    McTemplateU0zjzz_EventWriteTransfer
0x1800104f2  lea     rsi, [r15+2D0h]
0x1800104f9  mov     rcx, rsi; lpCriticalSection
0x1800104fc  call    cs:__imp_EnterCriticalSection
0x180010502  mov     edi, [r12+4]
0x180010507  mov     rcx, rsi; lpCriticalSection
0x18001050a  mov     ebx, [r15+2FCh]
0x180010511  call    cs:__imp_LeaveCriticalSection
0x180010517  cmp     edi, ebx
0x180010519  jz      short loc_18001057E
0x18001051b  lea     rcx, Resource; Resource
0x180010522  call    cs:__imp_RtlReleaseResource
0x180010528  mov     r8, r12
0x18001052b  call    QueueWorkItemInThreadPool
0x180010530  test    eax, eax
0x180010532  jz      loc_180010434
0x180010538  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001053f  jz      loc_180010434
0x180010545  xor     edx, edx
0x180010547  lea     rcx, [rsp+8B8h+var_848]
0x18001054c  mov     word ptr [rsp+8B8h+var_848], dx
0x180010551  mov     r8d, eax
0x180010554  lea     rdx, aHandledemanddi; "HandleDemandDialEvent: QueueWorkItemInT"...
0x18001055b  call    FormatRRASErrorString
0x180010560  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180010567  jz      loc_180010434
0x18001056d  lea     r8, [rsp+8B8h+var_848]
0x180010572  lea     rdx, RasRtrMgrTraceError
0x180010579  jmp     loc_180010428
0x18001057e  mov     ecx, [r14]
0x180010581  test    ecx, ecx
0x180010583  jz      loc_180010624
0x180010589  sub     ecx, 1
0x18001058c  jz      loc_180010617
0x180010592  cmp     ecx, 1
0x180010595  jz      short loc_18001060D
0x180010597  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001059e  jge     loc_18001062F
0x1800105a4  xor     eax, eax
0x1800105a6  lea     rdx, aHandledemanddi_1; "HandleDemandDialEvent: Illegal event %d"...
0x1800105ad  mov     word ptr [rsp+8B8h+var_848], ax
0x1800105b2  lea     rcx, [rsp+8B8h+var_848]
0x1800105b7  mov     word ptr [rsp+8B8h+var_870], ax
0x1800105bc  mov     r8d, [r14]
0x1800105bf  call    FormatRRASErrorString
0x1800105c4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800105cb  jge     short loc_18001062F
0x1800105cd  lea     rax, [r15+2B0h]
0x1800105d4  test    rax, rax
0x1800105d7  lea     r9, [rsp+8B8h+var_880]
0x1800105dc  lea     r8, [rsp+8B8h+var_848]
0x1800105e1  cmovnz  r9, rax
0x1800105e5  lea     rdx, RasRtrmgrParamTraceInfo
0x1800105ec  lea     rax, [rsp+8B8h+var_870]
0x1800105f1  mov     [rsp+8B8h+var_890], rax
0x1800105f6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800105fd  mov     rax, [r15+48h]
0x180010601  mov     [rsp+8B8h+var_898], rax
0x180010606  call    McTemplateU0zjzz_EventWriteTransfer
0x18001060b  jmp     short loc_18001062F
0x18001060d  mov     rcx, r15; lpMem
0x180010610  call    HandleDisconnectionNotification
0x180010615  jmp     short loc_18001062F
0x180010617  mov     rdx, r14
0x18001061a  mov     rcx, r15
0x18001061d  call    HandleConnectionNotification
0x180010622  jmp     short loc_18001062F
0x180010624  mov     rdx, r14
0x180010627  mov     rcx, r15
0x18001062a  call    HandleConnectionRequest
0x18001062f  mov     ecx, [r14+4]
0x180010633  call    InterfaceLookupByICBSeqNumber
0x180010638  mov     rdi, rax
0x18001063b  test    rax, rax
0x18001063e  jz      loc_1800103D9
0x180010644  lea     rbx, [rax+2D0h]
0x18001064b  mov     rcx, rbx; lpCriticalSection
0x18001064e  call    cs:__imp_EnterCriticalSection
0x180010654  inc     dword ptr [rdi+2FCh]
0x18001065a  mov     rcx, rbx; lpCriticalSection
0x18001065d  call    cs:__imp_LeaveCriticalSection
0x180010663  jmp     loc_1800103D9
0x180010668  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001066f  jge     loc_1800103D9
0x180010675  xor     eax, eax
0x180010677  lea     rdx, aHandledemanddi_5; "HandleDemandDialEvent: Event %d, could "...
0x18001067e  mov     word ptr [rsp+8B8h+var_848], ax
0x180010683  lea     rcx, [rsp+8B8h+var_848]
0x180010688  mov     r9d, [r14+4]
0x18001068c  mov     r8d, [r14]
0x18001068f  call    FormatRRASErrorString
0x180010694  jmp     loc_1800103B8
```
