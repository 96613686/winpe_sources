# Windows::Compat::Ids::IdsEtwEvent::Notify(void *)

- ea: `0x1800d7234`
- end: `0x1800d7579`
- name: `?Notify@IdsEtwEvent@Ids@Compat@Windows@@AEAAKPEAX@Z`
- size: `837`
- prototype: `unsigned int(Windows::Compat::Ids::IdsEtwEvent *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d67c0`

## callees

- `0x180012920`
- `0x180019c84`
- `0x18007a6e8`
- `0x1800b9ca8`
- `0x1800bbb40`
- `0x1800bc7b0`
- `0x1800c3bec`
- `0x1800d68b0`
- `0x1800d7234`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800d731f`
- `ntdll!RtlAllocateHeap` at `0x1800d731f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d74df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d74df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d72fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d737c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d72fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d737c`
- `wevtapi!EvtRender` at `0x1800d72ec`
- `wevtapi!EvtRender` at `0x1800d7372`
- `wevtapi!EvtRender` at `0x1800d72ec`
- `wevtapi!EvtRender` at `0x1800d7372`
- `wevtapi!EvtCreateRenderContext` at `0x1800d728b`
- `wevtapi!EvtCreateRenderContext` at `0x1800d728b`
- `wevtapi!EvtClose` at `0x1800d754c`
- `wevtapi!EvtClose` at `0x1800d754c`

## string_xrefs

- `0x1800d73e8`: `GetEventProcessPath failed to get process path [%d]`
- `0x1800d7275`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d72ac`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d733a`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d738f`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d73bf`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d73f9`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d7479`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d74b2`: `Windows::Compat::Ids::IdsEtwEvent::Notify`
- `0x1800d7500`: `Windows::Compat::Ids::IdsEtwEvent::Notify`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Ids::IdsEtwEvent::Notify(Windows::Compat::Ids::IdsEtwEvent *this, void *a2)
{
  unsigned __int16 *v4; // rsi
  EVT_HANDLE RenderContext; // r12
  DWORD LastError; // ebx
  struct Windows::Compat::Ids::IdsEventData *v7; // rdi
  PVOID Buffer; // r14
  struct Windows::Compat::Ids::IdsEventData *v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // edx
  unsigned int v13; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-18h] BYREF
  struct _GUID v15; // [rsp+50h] [rbp-10h] BYREF
  DWORD BufferSize; // [rsp+B0h] [rbp+50h] BYREF
  DWORD PropertyCount; // [rsp+B8h] [rbp+58h] BYREF

  BufferSize = 0;
  PropertyCount = 0;
  v13 = 0;
  v14 = 0;
  v4 = 0;
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
    205,
    (unsigned int)"Received callback notification %p\n");
  RenderContext = EvtCreateRenderContext(0, 0, 2u);
  if ( !RenderContext )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      213,
      (unsigned int)"Failed to get render context [%d]\n");
    return LastError;
  }
  v7 = 0;
  if ( EvtRender(RenderContext, a2, 0, 0, 0, &BufferSize, &PropertyCount) || GetLastError() != 122 )
  {
    Buffer = 0;
    LastError = 87;
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      228,
      (unsigned int)"Unexpected error.\n");
LABEL_19:
    if ( v4 )
      AslFree(NtCurrentPeb()->ProcessHeap, v4);
    if ( !Buffer )
      goto LABEL_23;
    goto LABEL_22;
  }
  LastError = 8;
  Buffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, BufferSize);
  if ( !Buffer )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      236,
      (unsigned int)"Failed to allocate EVT_VARIANT buffer\n");
    goto LABEL_23;
  }
  if ( !EvtRender(RenderContext, a2, 0, BufferSize, Buffer, &BufferSize, &PropertyCount) )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      251,
      (unsigned int)"EvtRender failed with [%d]\n");
LABEL_22:
    AslFree(NtCurrentPeb()->ProcessHeap, Buffer);
    goto LABEL_23;
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
    255,
    (unsigned int)"Property count [%d]\n");
  if ( GetEventProcessPath(a2, *((const unsigned __int16 **)this + 5), &v13, &v14) )
    AslLogCallPrintf(
      3,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      264,
      (unsigned int)"GetEventProcessPath failed to get process path [%d]");
  v9 = (struct Windows::Compat::Ids::IdsEventData *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)&v15.Data1 = v9;
  v7 = v9;
  if ( !v9 )
  {
    v7 = 0;
    v4 = v14;
    goto LABEL_19;
  }
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 4) = 0;
  v4 = v14;
  v15 = *(struct _GUID *)((char *)this + 8);
  LastError = Windows::Compat::Ids::IdsEventData::Initialize(v9, &v15, Buffer, v13, v14);
  if ( LastError )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      277,
      (unsigned int)"IdsEtwEvent: Failed to initialize IdsEventData [%d]");
    goto LABEL_19;
  }
  LastError = Windows::Compat::Ids::IdsEngine::QueueEventData(*((Windows::Compat::Ids::IdsEngine **)this + 7), v7);
  if ( LastError )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsEtwEvent::Notify",
      286,
      (unsigned int)"IdsEtwEvent: Failed to queue event data [%d]");
  }
  else
  {
    v7 = 0;
    LOBYTE(v10) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaIntelligentDetection>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_PcaIntelligentDetection>::GetImpl'::`2'::impl,
      v10);
    SetEvent(Windows::Compat::Ids::IdsEngine::sWorkQueued);
    LastError = 0;
  }
LABEL_23:
  EvtClose(RenderContext);
  if ( v7 )
    Windows::Compat::Ids::IdsEventData::`scalar deleting destructor'(v7, v11);
  return LastError;
}

```

## disassembly

```asm
0x1800d7234  mov     [rsp-38h+arg_0], rbx
0x1800d7239  push    rbp
0x1800d723a  push    rsi
0x1800d723b  push    rdi
0x1800d723c  push    r12
0x1800d723e  push    r13
0x1800d7240  push    r14
0x1800d7242  push    r15
0x1800d7244  mov     rbp, rsp
0x1800d7247  sub     rsp, 60h
0x1800d724b  xor     ebx, ebx
0x1800d724d  mov     [rsp+60h+Buffer], rdx
0x1800d7252  mov     r15, rdx
0x1800d7255  mov     [rbp+BufferSize], ebx
0x1800d7258  mov     r13, rcx
0x1800d725b  mov     [rbp+arg_18], ebx
0x1800d725e  lea     r9, aReceivedCallba; "Received callback notification %p\n"
0x1800d7265  mov     [rbp+var_20], ebx
0x1800d7268  lea     ecx, [rbx+3]
0x1800d726b  mov     [rbp+var_18], rbx
0x1800d726f  mov     r8d, 0CDh
0x1800d7275  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d727c  mov     esi, ebx
0x1800d727e  call    AslLogCallPrintf
0x1800d7283  xor     edx, edx; ValuePaths
0x1800d7285  lea     r8d, [rbx+2]; Flags
0x1800d7289  xor     ecx, ecx; ValuePathsCount
0x1800d728b  call    cs:__imp_EvtCreateRenderContext
0x1800d7291  mov     r12, rax
0x1800d7294  test    rax, rax
0x1800d7297  jnz     short loc_1800D72C6
0x1800d7299  call    cs:__imp_GetLastError
0x1800d729f  lea     r9, aFailedToGetRen; "Failed to get render context [%d]\n"
0x1800d72a6  mov     r8d, 0D5h
0x1800d72ac  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d72b3  mov     dword ptr [rsp+60h+Buffer], eax
0x1800d72b7  lea     ecx, [rsi+1]
0x1800d72ba  mov     ebx, eax
0x1800d72bc  call    AslLogCallPrintf
0x1800d72c1  jmp     loc_1800D755F
0x1800d72c6  lea     rax, [rbp+arg_18]
0x1800d72ca  xor     r9d, r9d; BufferSize
0x1800d72cd  mov     [rsp+60h+PropertyCount], rax; PropertyCount
0x1800d72d2  xor     r8d, r8d; Flags
0x1800d72d5  lea     rax, [rbp+BufferSize]
0x1800d72d9  mov     rdx, r15; Fragment
0x1800d72dc  mov     [rsp+60h+BufferUsed], rax; BufferUsed
0x1800d72e1  mov     rcx, r12; Context
0x1800d72e4  mov     [rsp+60h+Buffer], rbx; Buffer
0x1800d72e9  mov     rdi, rbx
0x1800d72ec  call    cs:__imp_EvtRender
0x1800d72f2  test    eax, eax
0x1800d72f4  jnz     loc_1800D74F1
0x1800d72fa  call    cs:__imp_GetLastError
0x1800d7300  cmp     eax, 7Ah ; 'z'
0x1800d7303  jnz     loc_1800D74F1
0x1800d7309  mov     rcx, gs:60h
0x1800d7312  lea     ebx, [rax-72h]
0x1800d7315  mov     r8d, [rbp+BufferSize]; Size
0x1800d7319  mov     edx, ebx; Flags
0x1800d731b  mov     rcx, [rcx+30h]; HeapHandle
0x1800d731f  call    cs:__imp_RtlAllocateHeap
0x1800d7325  mov     r14, rax
0x1800d7328  test    rax, rax
0x1800d732b  jnz     short loc_1800D734E
0x1800d732d  lea     r9, aFailedToAlloca_4; "Failed to allocate EVT_VARIANT buffer\n"
0x1800d7334  mov     r8d, 0ECh
0x1800d733a  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d7341  lea     ecx, [rbx-5]
0x1800d7344  call    AslLogCallPrintf
0x1800d7349  jmp     loc_1800D7549
0x1800d734e  mov     r9d, [rbp+BufferSize]; BufferSize
0x1800d7352  lea     rax, [rbp+arg_18]
0x1800d7356  mov     [rsp+60h+PropertyCount], rax; PropertyCount
0x1800d735b  xor     r8d, r8d; Flags
0x1800d735e  lea     rax, [rbp+BufferSize]
0x1800d7362  mov     rdx, r15; Fragment
0x1800d7365  mov     [rsp+60h+BufferUsed], rax; BufferUsed
0x1800d736a  mov     rcx, r12; Context
0x1800d736d  mov     [rsp+60h+Buffer], r14; Buffer
0x1800d7372  call    cs:__imp_EvtRender
0x1800d7378  test    eax, eax
0x1800d737a  jnz     short loc_1800D73AB
0x1800d737c  call    cs:__imp_GetLastError
0x1800d7382  lea     r9, aEvtrenderFaile; "EvtRender failed with [%d]\n"
0x1800d7389  mov     r8d, 0FBh
0x1800d738f  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d7396  mov     dword ptr [rsp+60h+Buffer], eax
0x1800d739a  mov     ecx, 1
0x1800d739f  mov     ebx, eax
0x1800d73a1  call    AslLogCallPrintf
0x1800d73a6  jmp     loc_1800D7534
0x1800d73ab  mov     eax, [rbp+arg_18]
0x1800d73ae  lea     r9, aPropertyCountD; "Property count [%d]\n"
0x1800d73b5  mov     r8d, 0FFh
0x1800d73bb  mov     dword ptr [rsp+60h+Buffer], eax
0x1800d73bf  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d73c6  mov     ecx, 3
0x1800d73cb  call    AslLogCallPrintf
0x1800d73d0  mov     rdx, [r13+28h]; unsigned __int16 *
0x1800d73d4  lea     r9, [rbp+var_18]; unsigned __int16 **
0x1800d73d8  lea     r8, [rbp+var_20]; unsigned int *
0x1800d73dc  mov     rcx, r15; Fragment
0x1800d73df  call    ?GetEventProcessPath@@YAKPEAXPEBGPEAKPEAPEAG@Z; GetEventProcessPath(void *,ushort const *,ulong *,ushort * *)
0x1800d73e4  test    eax, eax
0x1800d73e6  jz      short loc_1800D740A
0x1800d73e8  lea     r9, aGeteventproces_2; "GetEventProcessPath failed to get proce"...
0x1800d73ef  mov     dword ptr [rsp+60h+Buffer], eax
0x1800d73f3  mov     r8d, 108h
0x1800d73f9  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d7400  mov     ecx, 3
0x1800d7405  call    AslLogCallPrintf
0x1800d740a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d7411  mov     ecx, 30h ; '0'; unsigned __int64
0x1800d7416  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d741b  mov     qword ptr [rbp+var_10.Data1], rax
0x1800d741f  mov     rdi, rax
0x1800d7422  test    rax, rax
0x1800d7425  jz      loc_1800D74E9
0x1800d742b  mov     [rax+10h], rsi
0x1800d742f  mov     [rax+20h], rsi
0x1800d7433  test    rax, rax
0x1800d7436  jz      loc_1800D74EB
0x1800d743c  movups  xmm0, xmmword ptr [r13+8]
0x1800d7441  mov     rsi, [rbp+var_18]
0x1800d7445  lea     rdx, [rbp+var_10]; struct _GUID *
0x1800d7449  mov     r9d, [rbp+var_20]; unsigned int
0x1800d744d  mov     r8, r14; void *
0x1800d7450  mov     rcx, rax; this
0x1800d7453  mov     [rsp+60h+Buffer], rsi; unsigned __int16 *
0x1800d7458  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x1800d745d  call    ?Initialize@IdsEventData@Ids@Compat@Windows@@QEAAKU_GUID@@PEAXKPEBG@Z; Windows::Compat::Ids::IdsEventData::Initialize(_GUID,void *,ulong,ushort const *)
0x1800d7462  mov     ebx, eax
0x1800d7464  test    eax, eax
0x1800d7466  jz      short loc_1800D748F
0x1800d7468  lea     r9, aIdsetweventFai_3; "IdsEtwEvent: Failed to initialize IdsEv"...
0x1800d746f  mov     dword ptr [rsp+60h+Buffer], eax
0x1800d7473  mov     r8d, 115h
0x1800d7479  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d7480  mov     ecx, 1
0x1800d7485  call    AslLogCallPrintf
0x1800d748a  jmp     loc_1800D7515
0x1800d748f  mov     rcx, [r13+38h]; this
0x1800d7493  mov     rdx, rdi; struct Windows::Compat::Ids::IdsEventData *
0x1800d7496  call    ?QueueEventData@IdsEngine@Ids@Compat@Windows@@QEAAKPEAVIdsEventData@234@@Z; Windows::Compat::Ids::IdsEngine::QueueEventData(Windows::Compat::Ids::IdsEventData *)
0x1800d749b  mov     ebx, eax
0x1800d749d  test    eax, eax
0x1800d749f  jz      short loc_1800D74C8
0x1800d74a1  lea     r9, aIdsetweventFai_1; "IdsEtwEvent: Failed to queue event data"...
0x1800d74a8  mov     dword ptr [rsp+60h+Buffer], eax
0x1800d74ac  mov     r8d, 11Eh
0x1800d74b2  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d74b9  mov     ecx, 1
0x1800d74be  call    AslLogCallPrintf
0x1800d74c3  jmp     loc_1800D7549
0x1800d74c8  xor     edi, edi
0x1800d74ca  mov     dl, 1
0x1800d74cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcaIntelligentDetection@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcaIntelligentDetection@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaIntelligentDetection> `wil::Feature<__WilFeatureTraits_Feature_PcaIntelligentDetection>::GetImpl(void)'::`2'::impl
0x1800d74d3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PcaIntelligentDetection@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaIntelligentDetection>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800d74d8  mov     rcx, cs:?sWorkQueued@IdsEngine@Ids@Compat@Windows@@2PEAXEA; hEvent
0x1800d74df  call    cs:__imp_SetEvent
0x1800d74e5  xor     ebx, ebx
0x1800d74e7  jmp     short loc_1800D7549
0x1800d74e9  xor     edi, edi
0x1800d74eb  mov     rsi, [rbp+var_18]
0x1800d74ef  jmp     short loc_1800D7515
0x1800d74f1  mov     r14, rbx
0x1800d74f4  lea     r9, aUnexpectedErro; "Unexpected error.\n"
0x1800d74fb  mov     ebx, 57h ; 'W'
0x1800d7500  lea     rdx, aWindowsCompatI_60; "Windows::Compat::Ids::IdsEtwEvent::Noti"...
0x1800d7507  mov     r8d, 0E4h
0x1800d750d  lea     ecx, [rbx-56h]
0x1800d7510  call    AslLogCallPrintf
0x1800d7515  test    rsi, rsi
0x1800d7518  jz      short loc_1800D752F
0x1800d751a  mov     rcx, gs:60h
0x1800d7523  mov     rdx, rsi
0x1800d7526  mov     rcx, [rcx+30h]
0x1800d752a  call    AslFree
0x1800d752f  test    r14, r14
0x1800d7532  jz      short loc_1800D7549
0x1800d7534  mov     rcx, gs:60h
0x1800d753d  mov     rdx, r14
0x1800d7540  mov     rcx, [rcx+30h]
0x1800d7544  call    AslFree
0x1800d7549  mov     rcx, r12; Object
0x1800d754c  call    cs:__imp_EvtClose
0x1800d7552  test    rdi, rdi
0x1800d7555  jz      short loc_1800D755F
0x1800d7557  mov     rcx, rdi; this
0x1800d755a  call    ??_GIdsEventData@Ids@Compat@Windows@@QEAAPEAXI@Z; Windows::Compat::Ids::IdsEventData::`scalar deleting destructor'(uint)
0x1800d755f  mov     eax, ebx
0x1800d7561  mov     rbx, [rsp+60h+arg_0]
0x1800d7569  add     rsp, 60h
0x1800d756d  pop     r15
0x1800d756f  pop     r14
0x1800d7571  pop     r13
0x1800d7573  pop     r12
0x1800d7575  pop     rdi
0x1800d7576  pop     rsi
0x1800d7577  pop     rbp
0x1800d7578  retn
```
