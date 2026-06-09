# Dns64TcpTransportRefillPostedAcceptRequests

- ea: `0x18006eb68`
- end: `0x18006eef0`
- name: `Dns64TcpTransportRefillPostedAcceptRequests`
- size: `904`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006df00`
- `0x18006e680`
- `0x18006eef8`
- `0x18006f430`
- `0x18006f6b8`

## callees

- `0x1800159c4`
- `0x180045da4`
- `0x180061694`
- `0x18006bb94`
- `0x18006c79c`
- `0x18006eb68`
- `0x18006f368`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ed2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006edbe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ed2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006edbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006eb92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ed68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006edfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ee11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006eb92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ed68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006edfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ee11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ec35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ed7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eed2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ec35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ed7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eed2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006ed0f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006ed0f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006ec9b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006ec9b`
- `WS2_32!__imp_WSAGetLastError` at `0x18006ecec`
- `WS2_32!__imp_WSAGetLastError` at `0x18006ecec`

## string_xrefs

- `0x18006ebf9`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006edd3`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006ee73`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006eeaf`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

## pseudocode

```c
void __fastcall Dns64TcpTransportRefillPostedAcceptRequests(__int64 a1, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  _DWORD *v7; // rsi
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rbx
  __int64 v11; // r15
  volatile signed __int32 *v12; // r14
  int v13; // ecx
  int v14; // ecx
  int Error; // eax
  int v16; // ecx
  int v17; // ecx
  int v18; // r12d
  __int64 *v19; // rdi
  __int64 v20; // rax
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // [rsp+A0h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 72);
  v23 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  v7 = (_DWORD *)(a1 + 112);
  if ( a2 )
    --*v7;
  if ( a3 )
    --*(_DWORD *)(a1 + 116);
  if ( !*(_DWORD *)a1 || *v7 || *(_DWORD *)(a1 + 116) >= 0x2710u )
    goto LABEL_41;
  Dns64RequestAllocateEx(a1 - 272, 1, &v23);
  v10 = v23;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psqp_EventWriteTransfer(
      v9,
      v8,
      v23,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      220,
      a1 - 16);
  if ( v10 )
  {
    ++*(_DWORD *)(a1 + 116);
    ++*v7;
    LeaveCriticalSection(v3);
    v11 = v10 - 232;
    if ( (unsigned int)Dns64TcpTransportRequestPrepareReceiveSocket(v10 - 232)
      || (v12 = (volatile signed __int32 *)(a1 + 24), !(unsigned __int8)RoReferenceEx(a1 + 24)) )
    {
LABEL_23:
      EnterCriticalSection(v3);
      --*(_DWORD *)(a1 + 116);
      --*v7;
      LeaveCriticalSection(v3);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v17,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          v10,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
          92);
LABEL_40:
      Dns64RequestDereferenceEx(v10);
      return;
    }
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v13,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        252);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 736), 1u);
    StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
    if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int, int, __int64, __int64))(a1 + 120))(
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(v11 + 24),
            v11 + 72,
            0,
            44,
            44,
            v11 + 160,
            v11 + 192) )
    {
      Error = WSAGetLastError();
      if ( Error )
      {
        if ( Error != 997 )
        {
          CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
          if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFE) == 3 )
            SetEvent(*(HANDLE *)(a1 + 32));
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v16,
              (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
              v10,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
              36);
          Dns64RequestDereferenceEx(v10);
          goto LABEL_23;
        }
      }
    }
    v18 = 0;
    if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFE) == 3 )
      SetEvent(*(HANDLE *)(a1 + 32));
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v14,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        54);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 736), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    if ( !*(_DWORD *)v11 )
    {
      EnterCriticalSection(v3);
      if ( *(_DWORD *)a1 )
      {
        v19 = (__int64 *)(a1 + 40);
        v20 = *v19;
        if ( *(__int64 **)(*v19 + 8) != v19 )
          __fastfail(3u);
        *(_QWORD *)v10 = v20;
        v18 = 1;
        *(_QWORD *)(v10 + 8) = v19;
        *(_QWORD *)(v20 + 8) = v10;
        *v19 = v10;
        *(_DWORD *)(v10 + 16) = 1;
      }
      LeaveCriticalSection(v3);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v21,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        72);
    Dns64RequestDereferenceEx(v10);
    if ( !v18 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v22,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          v10,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
          82);
      goto LABEL_40;
    }
  }
  else
  {
LABEL_41:
    LeaveCriticalSection(v3);
  }
}

```

## disassembly

```asm
0x18006eb68  mov     rax, rsp
0x18006eb6b  push    rbx
0x18006eb6c  push    rbp
0x18006eb6d  push    rsi
0x18006eb6e  push    rdi
0x18006eb6f  push    r12
0x18006eb71  push    r13
0x18006eb73  push    r14
0x18006eb75  push    r15
0x18006eb77  sub     rsp, 58h
0x18006eb7b  lea     rbp, [rcx+48h]
0x18006eb7f  mov     qword ptr [rax+8], 0
0x18006eb87  mov     rdi, rcx
0x18006eb8a  mov     r14d, r8d
0x18006eb8d  mov     rcx, rbp; lpCriticalSection
0x18006eb90  mov     ebx, edx
0x18006eb92  call    cs:__imp_EnterCriticalSection
0x18006eb99  nop     dword ptr [rax+rax+00h]
0x18006eb9e  or      eax, 0FFFFFFFFh
0x18006eba1  lea     rsi, [rdi+70h]
0x18006eba5  test    ebx, ebx
0x18006eba7  jz      short loc_18006EBAB
0x18006eba9  add     [rsi], eax
0x18006ebab  test    r14d, r14d
0x18006ebae  jz      short loc_18006EBB3
0x18006ebb0  add     [rdi+74h], eax
0x18006ebb3  cmp     dword ptr [rdi], 0
0x18006ebb6  jz      loc_18006EECF
0x18006ebbc  mov     r13d, 1
0x18006ebc2  cmp     [rsi], r13d
0x18006ebc5  jnb     loc_18006EECF
0x18006ebcb  cmp     dword ptr [rdi+74h], 2710h
0x18006ebd2  jnb     loc_18006EECF
0x18006ebd8  lea     r14, [rdi-110h]
0x18006ebdf  mov     edx, r13d
0x18006ebe2  mov     rcx, r14
0x18006ebe5  lea     r8, [rsp+98h+arg_0]
0x18006ebed  call    Dns64RequestAllocateEx
0x18006ebf2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ebf9  lea     r12, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ec00  mov     rbx, [rsp+98h+arg_0]
0x18006ec08  jz      short loc_18006EC22
0x18006ec0a  mov     [rsp+98h+var_70], r14
0x18006ec0f  mov     r9, r12
0x18006ec12  mov     r8, rbx
0x18006ec15  mov     [rsp+98h+var_78], 1DCh
0x18006ec1d  call    McTemplateU0psqp_EventWriteTransfer
0x18006ec22  test    rbx, rbx
0x18006ec25  jz      loc_18006EECF
0x18006ec2b  add     [rdi+74h], r13d
0x18006ec2f  mov     rcx, rbp; lpCriticalSection
0x18006ec32  add     [rsi], r13d
0x18006ec35  call    cs:__imp_LeaveCriticalSection
0x18006ec3c  nop     dword ptr [rax+rax+00h]
0x18006ec41  lea     r15, [rbx-0E8h]
0x18006ec48  mov     rcx, r15
0x18006ec4b  call    Dns64TcpTransportRequestPrepareReceiveSocket
0x18006ec50  test    eax, eax
0x18006ec52  jnz     loc_18006ED65
0x18006ec58  lea     r14, [rdi+18h]
0x18006ec5c  mov     rcx, r14
0x18006ec5f  call    RoReferenceEx
0x18006ec64  test    al, al
0x18006ec66  jz      loc_18006ED65
0x18006ec6c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ec73  jz      short loc_18006EC8F
0x18006ec75  mov     r9, r12
0x18006ec78  mov     [rsp+98h+var_78], 1FCh
0x18006ec80  mov     r8, rbx
0x18006ec83  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006ec8a  call    McTemplateU0psq_EventWriteTransfer
0x18006ec8f  lock add [rbx+2E0h], r13d
0x18006ec97  mov     rcx, [rdi+10h]; pio
0x18006ec9b  call    cs:__imp_StartThreadpoolIo
0x18006eca2  nop     dword ptr [rax+rax+00h]
0x18006eca7  mov     eax, 2Ch ; ','
0x18006ecac  lea     rcx, [r15+0C0h]
0x18006ecb3  mov     [rsp+98h+var_60], rcx
0x18006ecb8  lea     rdx, [r15+0A0h]
0x18006ecbf  mov     rcx, [rdi+8]
0x18006ecc3  lea     r8, [r15+48h]
0x18006ecc7  mov     [rsp+98h+var_68], rdx
0x18006eccc  xor     r9d, r9d
0x18006eccf  mov     rdx, [r15+18h]
0x18006ecd3  mov     dword ptr [rsp+98h+var_70], eax
0x18006ecd7  mov     [rsp+98h+var_78], eax
0x18006ecdb  mov     rax, [rdi+78h]
0x18006ecdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ece4  test    eax, eax
0x18006ece6  jnz     loc_18006EDA8
0x18006ecec  call    cs:__imp_WSAGetLastError
0x18006ecf3  nop     dword ptr [rax+rax+00h]
0x18006ecf8  test    eax, eax
0x18006ecfa  jz      loc_18006EDA8
0x18006ed00  cmp     eax, 3E5h
0x18006ed05  jz      loc_18006EDA8
0x18006ed0b  mov     rcx, [rdi+10h]; pio
0x18006ed0f  call    cs:__imp_CancelThreadpoolIo
0x18006ed16  nop     dword ptr [rax+rax+00h]
0x18006ed1b  mov     eax, 0FFFFFFFEh
0x18006ed20  lock xadd [r14], eax
0x18006ed25  cmp     eax, 3
0x18006ed28  jnz     short loc_18006ED3A
0x18006ed2a  mov     rcx, [rdi+20h]; hEvent
0x18006ed2e  call    cs:__imp_SetEvent
0x18006ed35  nop     dword ptr [rax+rax+00h]
0x18006ed3a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ed41  jz      short loc_18006ED5D
0x18006ed43  mov     r9, r12
0x18006ed46  mov     [rsp+98h+var_78], 224h
0x18006ed4e  mov     r8, rbx
0x18006ed51  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006ed58  call    McTemplateU0psq_EventWriteTransfer
0x18006ed5d  mov     rcx, rbx
0x18006ed60  call    Dns64RequestDereferenceEx
0x18006ed65  mov     rcx, rbp; lpCriticalSection
0x18006ed68  call    cs:__imp_EnterCriticalSection
0x18006ed6f  nop     dword ptr [rax+rax+00h]
0x18006ed74  or      eax, 0FFFFFFFFh
0x18006ed77  mov     rcx, rbp; lpCriticalSection
0x18006ed7a  add     [rdi+74h], eax
0x18006ed7d  add     [rsi], eax
0x18006ed7f  call    cs:__imp_LeaveCriticalSection
0x18006ed86  nop     dword ptr [rax+rax+00h]
0x18006ed8b  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ed92  jz      loc_18006EEC5
0x18006ed98  mov     [rsp+98h+var_78], 25Ch
0x18006eda0  mov     r9, r12
0x18006eda3  jmp     loc_18006EEB6
0x18006eda8  xor     r12d, r12d
0x18006edab  lea     eax, [r12-2]
0x18006edb0  lock xadd [r14], eax
0x18006edb5  cmp     eax, 3
0x18006edb8  jnz     short loc_18006EDCA
0x18006edba  mov     rcx, [rdi+20h]; hEvent
0x18006edbe  call    cs:__imp_SetEvent
0x18006edc5  nop     dword ptr [rax+rax+00h]
0x18006edca  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006edd1  jz      short loc_18006EDF1
0x18006edd3  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006edda  mov     [rsp+98h+var_78], 236h
0x18006ede2  mov     r8, rbx
0x18006ede5  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006edec  call    McTemplateU0psq_EventWriteTransfer
0x18006edf1  lock add [rbx+2E0h], r13d
0x18006edf9  lea     rcx, [rbx+18h]; lpCriticalSection
0x18006edfd  call    cs:__imp_EnterCriticalSection
0x18006ee04  nop     dword ptr [rax+rax+00h]
0x18006ee09  cmp     [r15], r12d
0x18006ee0c  jnz     short loc_18006EE5A
0x18006ee0e  mov     rcx, rbp; lpCriticalSection
0x18006ee11  call    cs:__imp_EnterCriticalSection
0x18006ee18  nop     dword ptr [rax+rax+00h]
0x18006ee1d  cmp     [rdi], r12d
0x18006ee20  jz      short loc_18006EE4B
0x18006ee22  add     rdi, 28h ; '('
0x18006ee26  mov     rax, [rdi]
0x18006ee29  cmp     [rax+8], rdi
0x18006ee2d  jz      short loc_18006EE36
0x18006ee2f  mov     ecx, 3
0x18006ee34  int     29h; Win8: RtlFailFast(ecx)
0x18006ee36  mov     [rbx], rax
0x18006ee39  mov     r12d, r13d
0x18006ee3c  mov     [rbx+8], rdi
0x18006ee40  mov     [rax+8], rbx
0x18006ee44  mov     [rdi], rbx
0x18006ee47  mov     [rbx+10h], r13d
0x18006ee4b  mov     rcx, rbp; lpCriticalSection
0x18006ee4e  call    cs:__imp_LeaveCriticalSection
0x18006ee55  nop     dword ptr [rax+rax+00h]
0x18006ee5a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18006ee5e  call    cs:__imp_LeaveCriticalSection
0x18006ee65  nop     dword ptr [rax+rax+00h]
0x18006ee6a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ee71  jz      short loc_18006EE91
0x18006ee73  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ee7a  mov     [rsp+98h+var_78], 248h
0x18006ee82  mov     r8, rbx
0x18006ee85  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006ee8c  call    McTemplateU0psq_EventWriteTransfer
0x18006ee91  mov     rcx, rbx
0x18006ee94  call    Dns64RequestDereferenceEx
0x18006ee99  test    r12d, r12d
0x18006ee9c  jnz     short loc_18006EEDE
0x18006ee9e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006eea5  jz      short loc_18006EEC5
0x18006eea7  mov     [rsp+98h+var_78], 252h
0x18006eeaf  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006eeb6  mov     r8, rbx
0x18006eeb9  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006eec0  call    McTemplateU0psq_EventWriteTransfer
0x18006eec5  mov     rcx, rbx
0x18006eec8  call    Dns64RequestDereferenceEx
0x18006eecd  jmp     short loc_18006EEDE
0x18006eecf  mov     rcx, rbp; lpCriticalSection
0x18006eed2  call    cs:__imp_LeaveCriticalSection
0x18006eed9  nop     dword ptr [rax+rax+00h]
0x18006eede  add     rsp, 58h
0x18006eee2  pop     r15
0x18006eee4  pop     r14
0x18006eee6  pop     r13
0x18006eee8  pop     r12
0x18006eeea  pop     rdi
0x18006eeeb  pop     rsi
0x18006eeec  pop     rbp
0x18006eeed  pop     rbx
0x18006eeee  retn
```
