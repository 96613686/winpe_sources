# Dns64UdpTransportRefillPostedRequests

- ea: `0x18006ae10`
- end: `0x18006b1e7`
- name: `Dns64UdpTransportRefillPostedRequests`
- size: `983`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006abc4`
- `0x18006b1f0`
- `0x18006b6f8`
- `0x18006b974`

## callees

- `0x1800159d4`
- `0x180045d64`
- `0x18004c188`
- `0x1800616b4`
- `0x18006ae10`
- `0x18006bbb4`
- `0x18006c7bc`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b022`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b0b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b022`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b0b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ae3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b064`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b0f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b10a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ae3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b064`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b0f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b10a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006aede`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b07b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b146`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b156`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b1c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006aede`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b07b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b146`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b156`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b1c9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006b003`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006b003`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006afab`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006afab`
- `WS2_32!__imp_WSAGetLastError` at `0x18006afe0`
- `WS2_32!__imp_WSAGetLastError` at `0x18006afe0`

## string_xrefs

- `0x18006aeb3`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006af81`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b037`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b0c9`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b16b`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b1a6`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`

## pseudocode

```c
void __fastcall Dns64UdpTransportRefillPostedRequests(__int64 a1, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  _DWORD *v7; // rbp
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rdi
  volatile signed __int32 *v11; // r15
  int v12; // ecx
  int v13; // ecx
  int Error; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // ebp
  __int64 *v18; // rsi
  __int64 v19; // rax
  int v20; // ecx
  int v21; // ecx
  __int64 v22; // [rsp+80h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 56);
  v22 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  v7 = (_DWORD *)(a1 + 96);
  if ( a2 )
    --*v7;
  if ( a3 )
    --*(_DWORD *)(a1 + 100);
  if ( !*(_DWORD *)a1 || *v7 || *(_DWORD *)(a1 + 100) >= 0x2710u )
    goto LABEL_40;
  Dns64RequestAllocateEx(a1 - 152, 0, &v22);
  v10 = v22;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psqp_EventWriteTransfer(
      v9,
      v8,
      v22,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
      179,
      a1 + 104);
  if ( v10 )
  {
    ++*(_DWORD *)(a1 + 100);
    ++*v7;
    LeaveCriticalSection(v3);
    v11 = (volatile signed __int32 *)(a1 + 24);
    if ( !(unsigned __int8)RoReferenceEx(a1 + 24) )
    {
LABEL_22:
      EnterCriticalSection(v3);
      --*(_DWORD *)(a1 + 100);
      --*v7;
      LeaveCriticalSection(v3);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v16,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          v10,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
          24);
LABEL_39:
      Dns64RequestDereferenceEx(v10);
      return;
    }
    memset_0((void *)(v10 - 1152), 0, 0x400u);
    *(_QWORD *)(v10 - 112) = v10 - 1152;
    *(_DWORD *)(v10 - 120) = 1024;
    *(_DWORD *)(v10 - 128) = 0;
    *(_QWORD *)(v10 - 88) = v10 - 120;
    *(_DWORD *)(v10 - 80) = 1;
    memset_0((void *)(v10 - 1216), 0, 0x40u);
    *(_QWORD *)(v10 - 64) = v10 - 1216;
    *(_QWORD *)(v10 - 104) = v10 - 1264;
    *(_DWORD *)(v10 - 72) = 64;
    *(_DWORD *)(v10 - 56) = 0;
    *(_DWORD *)(v10 - 96) = 28;
    *(_OWORD *)(v10 - 48) = 0;
    *(_OWORD *)(v10 - 32) = 0;
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v12,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
        206);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 736), 1u);
    StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(a1 + 104))(
           *(_QWORD *)(a1 + 8),
           v10 - 104,
           0,
           v10 - 48,
           0) )
    {
      Error = WSAGetLastError();
      if ( Error )
      {
        if ( Error != 997 )
        {
          CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
          if ( _InterlockedExchangeAdd(v11, 0xFFFFFFFE) == 3 )
            SetEvent(*(HANDLE *)(a1 + 32));
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v15,
              (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
              v10,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
              233);
          Dns64RequestDereferenceEx(v10);
          goto LABEL_22;
        }
      }
    }
    v17 = 0;
    if ( _InterlockedExchangeAdd(v11, 0xFFFFFFFE) == 3 )
      SetEvent(*(HANDLE *)(a1 + 32));
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v13,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
        244);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 736), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    if ( !*(_DWORD *)(v10 - 1272) )
    {
      EnterCriticalSection(v3);
      if ( *(_DWORD *)a1 )
      {
        v18 = (__int64 *)(a1 + 40);
        v19 = *v18;
        if ( *(__int64 **)(*v18 + 8) != v18 )
          __fastfail(3u);
        *(_QWORD *)v10 = v19;
        v17 = 1;
        *(_QWORD *)(v10 + 8) = v18;
        *(_QWORD *)(v19 + 8) = v10;
        *v18 = v10;
        *(_DWORD *)(v10 + 16) = 1;
      }
      LeaveCriticalSection(v3);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v20,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
        4);
    Dns64RequestDereferenceEx(v10);
    if ( !v17 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v21,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          v10,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
          14);
      goto LABEL_39;
    }
  }
  else
  {
LABEL_40:
    LeaveCriticalSection(v3);
  }
}

```

## disassembly

```asm
0x18006ae10  mov     rax, rsp
0x18006ae13  push    rbx
0x18006ae14  push    rbp
0x18006ae15  push    rsi
0x18006ae16  push    rdi
0x18006ae17  push    r12
0x18006ae19  push    r13
0x18006ae1b  push    r14
0x18006ae1d  push    r15
0x18006ae1f  sub     rsp, 38h
0x18006ae23  lea     r14, [rcx+38h]
0x18006ae27  mov     qword ptr [rax+8], 0
0x18006ae2f  mov     rsi, rcx
0x18006ae32  mov     edi, r8d
0x18006ae35  mov     rcx, r14; lpCriticalSection
0x18006ae38  mov     ebx, edx
0x18006ae3a  call    cs:__imp_EnterCriticalSection
0x18006ae41  nop     dword ptr [rax+rax+00h]
0x18006ae46  or      r12d, 0FFFFFFFFh
0x18006ae4a  lea     rbp, [rsi+60h]
0x18006ae4e  test    ebx, ebx
0x18006ae50  jz      short loc_18006AE56
0x18006ae52  add     [rbp+0], r12d
0x18006ae56  test    edi, edi
0x18006ae58  jz      short loc_18006AE5E
0x18006ae5a  add     [rsi+64h], r12d
0x18006ae5e  cmp     dword ptr [rsi], 0
0x18006ae61  jz      loc_18006B1C6
0x18006ae67  mov     r13d, 1
0x18006ae6d  cmp     [rbp+0], r13d
0x18006ae71  jnb     loc_18006B1C6
0x18006ae77  cmp     dword ptr [rsi+64h], 2710h
0x18006ae7e  jnb     loc_18006B1C6
0x18006ae84  lea     rbx, [rsi-98h]
0x18006ae8b  xor     edx, edx
0x18006ae8d  mov     rcx, rbx
0x18006ae90  lea     r8, [rsp+78h+arg_0]
0x18006ae98  call    Dns64RequestAllocateEx
0x18006ae9d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006aea4  mov     rdi, [rsp+78h+arg_0]
0x18006aeac  jz      short loc_18006AECA
0x18006aeae  mov     [rsp+78h+var_50], rbx
0x18006aeb3  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006aeba  mov     r8, rdi
0x18006aebd  mov     dword ptr [rsp+78h+var_58], 2B3h
0x18006aec5  call    McTemplateU0psqp_EventWriteTransfer
0x18006aeca  test    rdi, rdi
0x18006aecd  jz      loc_18006B1C6
0x18006aed3  add     [rsi+64h], r13d
0x18006aed7  mov     rcx, r14; lpCriticalSection
0x18006aeda  add     [rbp+0], r13d
0x18006aede  call    cs:__imp_LeaveCriticalSection
0x18006aee5  nop     dword ptr [rax+rax+00h]
0x18006aeea  lea     r15, [rsi+18h]
0x18006aeee  mov     rcx, r15
0x18006aef1  call    RoReferenceEx
0x18006aef6  test    al, al
0x18006aef8  jz      loc_18006B061
0x18006aefe  lea     rbx, [rdi-480h]
0x18006af05  mov     r12d, 400h
0x18006af0b  mov     r8d, r12d; Size
0x18006af0e  mov     rcx, rbx; void *
0x18006af11  xor     edx, edx; Val
0x18006af13  call    memset_0
0x18006af18  lea     rax, [rdi-78h]
0x18006af1c  mov     [rdi-70h], rbx
0x18006af20  mov     [rax], r12d
0x18006af23  lea     rbx, [rdi-4C0h]
0x18006af2a  mov     r12d, 40h ; '@'
0x18006af30  mov     dword ptr [rdi-80h], 0
0x18006af37  mov     r8d, r12d; Size
0x18006af3a  mov     [rdi-58h], rax
0x18006af3e  xor     edx, edx; Val
0x18006af40  mov     [rdi-50h], r13d
0x18006af44  mov     rcx, rbx; void *
0x18006af47  call    memset_0
0x18006af4c  mov     [rdi-40h], rbx
0x18006af50  lea     rax, [rdi-4F0h]
0x18006af57  mov     [rdi-68h], rax
0x18006af5b  xorps   xmm0, xmm0
0x18006af5e  mov     [rdi-48h], r12d
0x18006af62  mov     dword ptr [rdi-38h], 0
0x18006af69  mov     dword ptr [rdi-60h], 1Ch
0x18006af70  movups  xmmword ptr [rdi-30h], xmm0
0x18006af74  movups  xmmword ptr [rdi-20h], xmm0
0x18006af78  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006af7f  jz      short loc_18006AF9F
0x18006af81  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006af88  mov     dword ptr [rsp+78h+var_58], 2CEh
0x18006af90  mov     r8, rdi
0x18006af93  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006af9a  call    McTemplateU0psq_EventWriteTransfer
0x18006af9f  lock add [rdi+2E0h], r13d
0x18006afa7  mov     rcx, [rsi+10h]; pio
0x18006afab  call    cs:__imp_StartThreadpoolIo
0x18006afb2  nop     dword ptr [rax+rax+00h]
0x18006afb7  mov     rcx, [rsi+8]
0x18006afbb  lea     r9, [rdi-30h]
0x18006afbf  mov     rax, [rsi+68h]
0x18006afc3  lea     rdx, [rdi-68h]
0x18006afc7  xor     r8d, r8d
0x18006afca  mov     [rsp+78h+var_58], 0
0x18006afd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afd8  test    eax, eax
0x18006afda  jz      loc_18006B0A1
0x18006afe0  call    cs:__imp_WSAGetLastError
0x18006afe7  nop     dword ptr [rax+rax+00h]
0x18006afec  test    eax, eax
0x18006afee  jz      loc_18006B0A1
0x18006aff4  cmp     eax, 3E5h
0x18006aff9  jz      loc_18006B0A1
0x18006afff  mov     rcx, [rsi+10h]; pio
0x18006b003  call    cs:__imp_CancelThreadpoolIo
0x18006b00a  nop     dword ptr [rax+rax+00h]
0x18006b00f  mov     eax, 0FFFFFFFEh
0x18006b014  lock xadd [r15], eax
0x18006b019  cmp     eax, 3
0x18006b01c  jnz     short loc_18006B02E
0x18006b01e  mov     rcx, [rsi+20h]; hEvent
0x18006b022  call    cs:__imp_SetEvent
0x18006b029  nop     dword ptr [rax+rax+00h]
0x18006b02e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b035  jz      short loc_18006B055
0x18006b037  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b03e  mov     dword ptr [rsp+78h+var_58], 2E9h
0x18006b046  mov     r8, rdi
0x18006b049  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b050  call    McTemplateU0psq_EventWriteTransfer
0x18006b055  mov     rcx, rdi
0x18006b058  call    Dns64RequestDereferenceEx
0x18006b05d  or      r12d, 0FFFFFFFFh
0x18006b061  mov     rcx, r14; lpCriticalSection
0x18006b064  call    cs:__imp_EnterCriticalSection
0x18006b06b  nop     dword ptr [rax+rax+00h]
0x18006b070  add     [rsi+64h], r12d
0x18006b074  mov     rcx, r14; lpCriticalSection
0x18006b077  add     [rbp+0], r12d
0x18006b07b  call    cs:__imp_LeaveCriticalSection
0x18006b082  nop     dword ptr [rax+rax+00h]
0x18006b087  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b08e  jz      loc_18006B1BC
0x18006b094  mov     dword ptr [rsp+78h+var_58], 318h
0x18006b09c  jmp     loc_18006B1A6
0x18006b0a1  xor     ebp, ebp
0x18006b0a3  lea     eax, [rbp-2]
0x18006b0a6  lock xadd [r15], eax
0x18006b0ab  cmp     eax, 3
0x18006b0ae  jnz     short loc_18006B0C0
0x18006b0b0  mov     rcx, [rsi+20h]; hEvent
0x18006b0b4  call    cs:__imp_SetEvent
0x18006b0bb  nop     dword ptr [rax+rax+00h]
0x18006b0c0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b0c7  jz      short loc_18006B0E7
0x18006b0c9  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b0d0  mov     dword ptr [rsp+78h+var_58], 2F4h
0x18006b0d8  mov     r8, rdi
0x18006b0db  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006b0e2  call    McTemplateU0psq_EventWriteTransfer
0x18006b0e7  lock add [rdi+2E0h], r13d
0x18006b0ef  lea     rcx, [rdi+18h]; lpCriticalSection
0x18006b0f3  call    cs:__imp_EnterCriticalSection
0x18006b0fa  nop     dword ptr [rax+rax+00h]
0x18006b0ff  cmp     [rdi-4F8h], ebp
0x18006b105  jnz     short loc_18006B152
0x18006b107  mov     rcx, r14; lpCriticalSection
0x18006b10a  call    cs:__imp_EnterCriticalSection
0x18006b111  nop     dword ptr [rax+rax+00h]
0x18006b116  cmp     [rsi], ebp
0x18006b118  jz      short loc_18006B143
0x18006b11a  add     rsi, 28h ; '('
0x18006b11e  mov     rax, [rsi]
0x18006b121  cmp     [rax+8], rsi
0x18006b125  jz      short loc_18006B12E
0x18006b127  mov     ecx, 3
0x18006b12c  int     29h; Win8: RtlFailFast(ecx)
0x18006b12e  mov     [rdi], rax
0x18006b131  mov     ebp, r13d
0x18006b134  mov     [rdi+8], rsi
0x18006b138  mov     [rax+8], rdi
0x18006b13c  mov     [rsi], rdi
0x18006b13f  mov     [rdi+10h], r13d
0x18006b143  mov     rcx, r14; lpCriticalSection
0x18006b146  call    cs:__imp_LeaveCriticalSection
0x18006b14d  nop     dword ptr [rax+rax+00h]
0x18006b152  lea     rcx, [rdi+18h]; lpCriticalSection
0x18006b156  call    cs:__imp_LeaveCriticalSection
0x18006b15d  nop     dword ptr [rax+rax+00h]
0x18006b162  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b169  jz      short loc_18006B189
0x18006b16b  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b172  mov     dword ptr [rsp+78h+var_58], 304h
0x18006b17a  mov     r8, rdi
0x18006b17d  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b184  call    McTemplateU0psq_EventWriteTransfer
0x18006b189  mov     rcx, rdi
0x18006b18c  call    Dns64RequestDereferenceEx
0x18006b191  test    ebp, ebp
0x18006b193  jnz     short loc_18006B1D5
0x18006b195  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b19c  jz      short loc_18006B1BC
0x18006b19e  mov     dword ptr [rsp+78h+var_58], 30Eh
0x18006b1a6  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b1ad  mov     r8, rdi
0x18006b1b0  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b1b7  call    McTemplateU0psq_EventWriteTransfer
0x18006b1bc  mov     rcx, rdi
0x18006b1bf  call    Dns64RequestDereferenceEx
0x18006b1c4  jmp     short loc_18006B1D5
0x18006b1c6  mov     rcx, r14; lpCriticalSection
0x18006b1c9  call    cs:__imp_LeaveCriticalSection
0x18006b1d0  nop     dword ptr [rax+rax+00h]
0x18006b1d5  add     rsp, 38h
0x18006b1d9  pop     r15
0x18006b1db  pop     r14
0x18006b1dd  pop     r13
0x18006b1df  pop     r12
0x18006b1e1  pop     rdi
0x18006b1e2  pop     rsi
0x18006b1e3  pop     rbp
0x18006b1e4  pop     rbx
0x18006b1e5  retn
```
