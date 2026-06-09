# Dns64UdpTransportRefillPostedRequests

- ea: `0x18006adf0`
- end: `0x18006b1c7`
- name: `Dns64UdpTransportRefillPostedRequests`
- size: `983`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006aba4`
- `0x18006b1d0`
- `0x18006b6d8`
- `0x18006b954`

## callees

- `0x1800159c4`
- `0x180045da4`
- `0x18004c1c8`
- `0x180061694`
- `0x18006adf0`
- `0x18006bb94`
- `0x18006c79c`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b002`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b094`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b002`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ae1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b044`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b0d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b0ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ae1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b044`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b0d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b0ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006aebe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b05b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b136`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006aebe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b05b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b136`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b1a9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006afe3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006afe3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006af8b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006af8b`
- `WS2_32!__imp_WSAGetLastError` at `0x18006afc0`
- `WS2_32!__imp_WSAGetLastError` at `0x18006afc0`

## string_xrefs

- `0x18006ae93`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006af61`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b017`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b0a9`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b14b`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b186`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`

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
0x18006adf0  mov     rax, rsp
0x18006adf3  push    rbx
0x18006adf4  push    rbp
0x18006adf5  push    rsi
0x18006adf6  push    rdi
0x18006adf7  push    r12
0x18006adf9  push    r13
0x18006adfb  push    r14
0x18006adfd  push    r15
0x18006adff  sub     rsp, 38h
0x18006ae03  lea     r14, [rcx+38h]
0x18006ae07  mov     qword ptr [rax+8], 0
0x18006ae0f  mov     rsi, rcx
0x18006ae12  mov     edi, r8d
0x18006ae15  mov     rcx, r14; lpCriticalSection
0x18006ae18  mov     ebx, edx
0x18006ae1a  call    cs:__imp_EnterCriticalSection
0x18006ae21  nop     dword ptr [rax+rax+00h]
0x18006ae26  or      r12d, 0FFFFFFFFh
0x18006ae2a  lea     rbp, [rsi+60h]
0x18006ae2e  test    ebx, ebx
0x18006ae30  jz      short loc_18006AE36
0x18006ae32  add     [rbp+0], r12d
0x18006ae36  test    edi, edi
0x18006ae38  jz      short loc_18006AE3E
0x18006ae3a  add     [rsi+64h], r12d
0x18006ae3e  cmp     dword ptr [rsi], 0
0x18006ae41  jz      loc_18006B1A6
0x18006ae47  mov     r13d, 1
0x18006ae4d  cmp     [rbp+0], r13d
0x18006ae51  jnb     loc_18006B1A6
0x18006ae57  cmp     dword ptr [rsi+64h], 2710h
0x18006ae5e  jnb     loc_18006B1A6
0x18006ae64  lea     rbx, [rsi-98h]
0x18006ae6b  xor     edx, edx
0x18006ae6d  mov     rcx, rbx
0x18006ae70  lea     r8, [rsp+78h+arg_0]
0x18006ae78  call    Dns64RequestAllocateEx
0x18006ae7d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ae84  mov     rdi, [rsp+78h+arg_0]
0x18006ae8c  jz      short loc_18006AEAA
0x18006ae8e  mov     [rsp+78h+var_50], rbx
0x18006ae93  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ae9a  mov     r8, rdi
0x18006ae9d  mov     dword ptr [rsp+78h+var_58], 2B3h
0x18006aea5  call    McTemplateU0psqp_EventWriteTransfer
0x18006aeaa  test    rdi, rdi
0x18006aead  jz      loc_18006B1A6
0x18006aeb3  add     [rsi+64h], r13d
0x18006aeb7  mov     rcx, r14; lpCriticalSection
0x18006aeba  add     [rbp+0], r13d
0x18006aebe  call    cs:__imp_LeaveCriticalSection
0x18006aec5  nop     dword ptr [rax+rax+00h]
0x18006aeca  lea     r15, [rsi+18h]
0x18006aece  mov     rcx, r15
0x18006aed1  call    RoReferenceEx
0x18006aed6  test    al, al
0x18006aed8  jz      loc_18006B041
0x18006aede  lea     rbx, [rdi-480h]
0x18006aee5  mov     r12d, 400h
0x18006aeeb  mov     r8d, r12d; Size
0x18006aeee  mov     rcx, rbx; void *
0x18006aef1  xor     edx, edx; Val
0x18006aef3  call    memset_0
0x18006aef8  lea     rax, [rdi-78h]
0x18006aefc  mov     [rdi-70h], rbx
0x18006af00  mov     [rax], r12d
0x18006af03  lea     rbx, [rdi-4C0h]
0x18006af0a  mov     r12d, 40h ; '@'
0x18006af10  mov     dword ptr [rdi-80h], 0
0x18006af17  mov     r8d, r12d; Size
0x18006af1a  mov     [rdi-58h], rax
0x18006af1e  xor     edx, edx; Val
0x18006af20  mov     [rdi-50h], r13d
0x18006af24  mov     rcx, rbx; void *
0x18006af27  call    memset_0
0x18006af2c  mov     [rdi-40h], rbx
0x18006af30  lea     rax, [rdi-4F0h]
0x18006af37  mov     [rdi-68h], rax
0x18006af3b  xorps   xmm0, xmm0
0x18006af3e  mov     [rdi-48h], r12d
0x18006af42  mov     dword ptr [rdi-38h], 0
0x18006af49  mov     dword ptr [rdi-60h], 1Ch
0x18006af50  movups  xmmword ptr [rdi-30h], xmm0
0x18006af54  movups  xmmword ptr [rdi-20h], xmm0
0x18006af58  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006af5f  jz      short loc_18006AF7F
0x18006af61  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006af68  mov     dword ptr [rsp+78h+var_58], 2CEh
0x18006af70  mov     r8, rdi
0x18006af73  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006af7a  call    McTemplateU0psq_EventWriteTransfer
0x18006af7f  lock add [rdi+2E0h], r13d
0x18006af87  mov     rcx, [rsi+10h]; pio
0x18006af8b  call    cs:__imp_StartThreadpoolIo
0x18006af92  nop     dword ptr [rax+rax+00h]
0x18006af97  mov     rcx, [rsi+8]
0x18006af9b  lea     r9, [rdi-30h]
0x18006af9f  mov     rax, [rsi+68h]
0x18006afa3  lea     rdx, [rdi-68h]
0x18006afa7  xor     r8d, r8d
0x18006afaa  mov     [rsp+78h+var_58], 0
0x18006afb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afb8  test    eax, eax
0x18006afba  jz      loc_18006B081
0x18006afc0  call    cs:__imp_WSAGetLastError
0x18006afc7  nop     dword ptr [rax+rax+00h]
0x18006afcc  test    eax, eax
0x18006afce  jz      loc_18006B081
0x18006afd4  cmp     eax, 3E5h
0x18006afd9  jz      loc_18006B081
0x18006afdf  mov     rcx, [rsi+10h]; pio
0x18006afe3  call    cs:__imp_CancelThreadpoolIo
0x18006afea  nop     dword ptr [rax+rax+00h]
0x18006afef  mov     eax, 0FFFFFFFEh
0x18006aff4  lock xadd [r15], eax
0x18006aff9  cmp     eax, 3
0x18006affc  jnz     short loc_18006B00E
0x18006affe  mov     rcx, [rsi+20h]; hEvent
0x18006b002  call    cs:__imp_SetEvent
0x18006b009  nop     dword ptr [rax+rax+00h]
0x18006b00e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b015  jz      short loc_18006B035
0x18006b017  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b01e  mov     dword ptr [rsp+78h+var_58], 2E9h
0x18006b026  mov     r8, rdi
0x18006b029  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b030  call    McTemplateU0psq_EventWriteTransfer
0x18006b035  mov     rcx, rdi
0x18006b038  call    Dns64RequestDereferenceEx
0x18006b03d  or      r12d, 0FFFFFFFFh
0x18006b041  mov     rcx, r14; lpCriticalSection
0x18006b044  call    cs:__imp_EnterCriticalSection
0x18006b04b  nop     dword ptr [rax+rax+00h]
0x18006b050  add     [rsi+64h], r12d
0x18006b054  mov     rcx, r14; lpCriticalSection
0x18006b057  add     [rbp+0], r12d
0x18006b05b  call    cs:__imp_LeaveCriticalSection
0x18006b062  nop     dword ptr [rax+rax+00h]
0x18006b067  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b06e  jz      loc_18006B19C
0x18006b074  mov     dword ptr [rsp+78h+var_58], 318h
0x18006b07c  jmp     loc_18006B186
0x18006b081  xor     ebp, ebp
0x18006b083  lea     eax, [rbp-2]
0x18006b086  lock xadd [r15], eax
0x18006b08b  cmp     eax, 3
0x18006b08e  jnz     short loc_18006B0A0
0x18006b090  mov     rcx, [rsi+20h]; hEvent
0x18006b094  call    cs:__imp_SetEvent
0x18006b09b  nop     dword ptr [rax+rax+00h]
0x18006b0a0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b0a7  jz      short loc_18006B0C7
0x18006b0a9  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b0b0  mov     dword ptr [rsp+78h+var_58], 2F4h
0x18006b0b8  mov     r8, rdi
0x18006b0bb  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006b0c2  call    McTemplateU0psq_EventWriteTransfer
0x18006b0c7  lock add [rdi+2E0h], r13d
0x18006b0cf  lea     rcx, [rdi+18h]; lpCriticalSection
0x18006b0d3  call    cs:__imp_EnterCriticalSection
0x18006b0da  nop     dword ptr [rax+rax+00h]
0x18006b0df  cmp     [rdi-4F8h], ebp
0x18006b0e5  jnz     short loc_18006B132
0x18006b0e7  mov     rcx, r14; lpCriticalSection
0x18006b0ea  call    cs:__imp_EnterCriticalSection
0x18006b0f1  nop     dword ptr [rax+rax+00h]
0x18006b0f6  cmp     [rsi], ebp
0x18006b0f8  jz      short loc_18006B123
0x18006b0fa  add     rsi, 28h ; '('
0x18006b0fe  mov     rax, [rsi]
0x18006b101  cmp     [rax+8], rsi
0x18006b105  jz      short loc_18006B10E
0x18006b107  mov     ecx, 3
0x18006b10c  int     29h; Win8: RtlFailFast(ecx)
0x18006b10e  mov     [rdi], rax
0x18006b111  mov     ebp, r13d
0x18006b114  mov     [rdi+8], rsi
0x18006b118  mov     [rax+8], rdi
0x18006b11c  mov     [rsi], rdi
0x18006b11f  mov     [rdi+10h], r13d
0x18006b123  mov     rcx, r14; lpCriticalSection
0x18006b126  call    cs:__imp_LeaveCriticalSection
0x18006b12d  nop     dword ptr [rax+rax+00h]
0x18006b132  lea     rcx, [rdi+18h]; lpCriticalSection
0x18006b136  call    cs:__imp_LeaveCriticalSection
0x18006b13d  nop     dword ptr [rax+rax+00h]
0x18006b142  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b149  jz      short loc_18006B169
0x18006b14b  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b152  mov     dword ptr [rsp+78h+var_58], 304h
0x18006b15a  mov     r8, rdi
0x18006b15d  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b164  call    McTemplateU0psq_EventWriteTransfer
0x18006b169  mov     rcx, rdi
0x18006b16c  call    Dns64RequestDereferenceEx
0x18006b171  test    ebp, ebp
0x18006b173  jnz     short loc_18006B1B5
0x18006b175  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006b17c  jz      short loc_18006B19C
0x18006b17e  mov     dword ptr [rsp+78h+var_58], 30Eh
0x18006b186  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b18d  mov     r8, rdi
0x18006b190  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b197  call    McTemplateU0psq_EventWriteTransfer
0x18006b19c  mov     rcx, rdi
0x18006b19f  call    Dns64RequestDereferenceEx
0x18006b1a4  jmp     short loc_18006B1B5
0x18006b1a6  mov     rcx, r14; lpCriticalSection
0x18006b1a9  call    cs:__imp_LeaveCriticalSection
0x18006b1b0  nop     dword ptr [rax+rax+00h]
0x18006b1b5  add     rsp, 38h
0x18006b1b9  pop     r15
0x18006b1bb  pop     r14
0x18006b1bd  pop     r13
0x18006b1bf  pop     r12
0x18006b1c1  pop     rdi
0x18006b1c2  pop     rsi
0x18006b1c3  pop     rbp
0x18006b1c4  pop     rbx
0x18006b1c5  retn
```
